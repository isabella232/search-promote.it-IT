---
description: Utilizzare il menu Filtro per utilizzare gli script che modificano il contenuto di un documento Web prima dell'indicizzazione.
solution: Target
subtopic: Filtering
title: Informazioni sul menu Filtro
topic: Impostazioni, Ricerca nel sito e merchandising
uuid: ebb08fa8-4e17-417d-868b-11fc2af9f284
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '4008'
ht-degree: 1%

---


# Informazioni sul menu Filtro{#about-the-filtering-menu}

Utilizzare il menu Filtro per utilizzare gli script che modificano il contenuto di un documento Web prima dell&#39;indicizzazione.

## Informazioni sul filtro degli script {#concept_E56B73D625854AB2A899EF2D56CFCB47}

È possibile utilizzare [!DNL Filtering Script] per modificare il contenuto di un documento Web prima che venga indicizzato.

È possibile inserire tag HTML, rimuovere contenuti irrilevanti e persino creare nuovi metadati HTML in base all’URL di un documento, al tipo MIME e al contenuto esistente. Lo script di filtraggio è uno script Perl, che fornisce una potente gestione delle stringhe e la flessibilità della corrispondenza delle espressioni regolari. Lo script di filtraggio viene utilizzato con uno script di inizializzazione, uno script di terminazione, uno script di maschere URL e un URL di test.

Lo script di filtro viene eseguito ogni volta che un documento viene letto dal sito web. Lo script viene eseguito come filtro standard. In altre parole, legge i dati da STDIN, in qualche modo trasforma tali dati e scrive i risultati in STDOUT. È possibile utilizzare lo script di filtraggio per stampare i messaggi di stato dallo script di filtraggio al registro degli indici. È possibile stampare i messaggi su STDERR oppure tramite la subroutine `_search_debug_log()`.

Alcune opzioni di differenze GNU che è possibile utilizzare in modalità **[!UICONTROL Expert (diff)]** nella pagina Script di filtraggio pianificato, includono:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Opzione differenze GNU </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> Ignora le modifiche nella quantità di spazio vuoto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> Ignora le modifiche che inseriscono o eliminano righe vuote. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output del contesto, che mostra tre righe di contesto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C linee  </span> </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output del contesto, mostrando le righe (un numero intero) di contesto, o tre se non sono date righe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> Ignora le modifiche nel caso; considera le lettere maiuscole e minuscole equivalenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> Esegue un output simile a uno script ed con modifiche nell’ordine in cui appaiono nel file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> Trasmette diffusori in formato RCS; come <span class="codeph"> -f </span> tranne per il fatto che ogni comando specifica il numero di righe interessate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output unificato, che mostra tre righe di contesto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> - Linee U  </span> </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output unificato, che mostra le righe (un numero intero) del contesto, o tre se non sono date righe. </p> </td> 
  </tr> 
 </tbody> 
</table>

È possibile utilizzare variabili locali, variabili globali o entrambi in questi script. Tutte le variabili globali sono precedute dallo spazio dei nomi &quot;main::&quot;. Quando si avvia lo script di filtro, il relativo ambiente contiene i seguenti handle di file standard:

* STDIN - nulla (restituisce immediatamente EOF in lettura)
* STDOUT - HTML di sostituzione (se i dati vengono stampati su STDOUT, vengono utilizzati al posto del documento originale)
* STDERR - i dati stampati su STDERR vengono stampati nel log indice come un errore

Inoltre, è possibile scrivere messaggi personalizzati nel registro dell&#39;indice utilizzando la subroutine `_search_debug_log()`, come nell&#39;esempio seguente:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Questi messaggi vengono visualizzati con la parola `DEBUG` come prefisso e non vengono registrati come errori.

Di seguito è riportato un esempio di filtro. I campi della pagina Web `<title>` spesso iniziano con il nome dell’azienda. Anche se queste informazioni sono utili per la navigazione nel sito, non sono pertinenti durante la ricerca. Se i titoli di tutte le pagine web MegaCorp iniziano con una stringa comune, ad esempio:

```
<title>MegaCorp -- meaningful title 
here</title>
```

Rimuovere &quot; `MegaCorp --`&quot; dall&#39;inizio di ciascun titolo del documento e contare ogni documento elaborato con lo script di filtro. A questo scopo, è possibile utilizzare il seguente script:

```
# Make sure this is an HTML document. 
if ($main::ws_content_type =~ /^text\/html/) { 
    # Read the entire document into a local scalar variable. 
    my @docarray = <>; 
    my $doc = join("", @docarray); 
 
    # Remove "MegaCorp -- " from the title. 
    $doc =~ s/(<TITLE>)MegaCorp -- /$1/gis; 
 
    # Print the resulting document. 
    print $doc; 
 
    # Count that we've filtered one more document. 
    $main::doc_count++; 
}
```

## Variabili globali {#global-variables}

È possibile utilizzare le seguenti variabili in qualsiasi script di filtro:

| Variabile | Descrizione |
|--- |--- |
| `$main::search_crawl_type` | Il valore di `$main::search_crawl_type` indica il tipo di operazione di indice in corso.  Modulo obsoleto: `$main::ws_crawl_type` Le operazioni di indice e i valori associati includono quanto segue: <ul><li>Indice completo: Manuale - `manual`</li><li>Indice completo: Pianificato - `auto`</li><li>Indice completo: Controllo remoto - `CGI`</li><li>Indice incrementale: Manuale - `manual-incremental`</li><li>Indice incrementale: Pianificato - `auto-incremental` </li><li>Indice incrementale: Controllo remoto - `CGI-incremental`</li><li>Indice con script: Manuale - `manual-indexlist.txt` </li><li>Indice con script: Pianificato - `auto-indexlist.txt`</li><li>Indice con script: Controllo remoto - `CGI-indexlist.txt`</li><li>Rigenera - `manual-upgrade`</li></ul> |
| `$main::search_clear_cache` | Il valore indica se è stata richiesta l&#39;opzione di indicizzazione &quot;Clear index cache&quot; per l&#39;operazione di indicizzazione corrente. Se è stato richiesto &quot;Clear index cache&quot;, il valore di `$main::search_clear_cache` è &quot; `1`&quot;.  Forma obsoleta: `$main::ws_clear_cache` |
| `$main::search_fields` | Il valore contiene un elenco separato da tabulazioni dei campi di metadati definiti nell’account. Per impostazione predefinita, il valore è:   `url title desc keys target body alt date charset language` Modulo obsoleto: `$main::ws_fields` |
| `$main::search_collections` | Il valore contiene un elenco separato da tabulazioni delle Raccolte definite nell’account.  Forma obsoleta: `$main::ws_collections` |
| `$main::search_url` | Il valore è l’URL completo del documento.  Forma obsoleta: `$main::ws_url` |
| `$main::search_content_type` | Il valore è il tipo di contenuto del documento recuperato dal tag meta http-equiv. Un valore tipico è &quot;text/html; charset=iso-8859-1&quot;.  Forma obsoleta: `$main::ws_content_type` |
| `$main::search_content_class` | Il valore è la classe di contenuto del documento, come derivato dal campo del tipo di contenuto.  Forma obsoleta: `$main::ws_content_class` |
| `$main::search_syntax_check` | Il valore riflette l’utilizzo del pulsante &quot;Controlla sintassi&quot;. Se l’utente fa clic su di esso, il valore è 1 (uno); in caso contrario, il relativo valore è 0 (zero).  Forma obsoleta: `$main::ws_syntax_check` |
| `$main::search_last_mod_date` | Se fornito dal server web, questo valore contiene la rappresentazione epoch (secondi dal 1° gennaio 1970) della data dell&#39;ultima modifica del documento.  Puoi formattare questo valore utilizzando la chiamata alla libreria Perl localtime() . |

### Suggerimenti rapidi {#section_89A5C16911744AF98E232DF608C6A1F5}

* Tutte le variabili globali sono precedute dallo spazio dei nomi &quot;main::&quot;: `$main::doc_count = 0;`
* Tutte le variabili locali sono dichiarate con &quot;my&quot;: `my $i = 0;`
* Le sottorubriche sono definite nello script di inizializzazione. Non è necessario un namespace esplicito &quot;main::&quot;: `sub my_sub {` `...`

   `}`

* Testa `$main::search_content_type` prima di apportare modifiche a un file. Il test può aiutare a evitare di apportare modifiche imprudenti ai file binari, come i file SWF o i file PDF:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* L’ `$main::search_content_type` è l’intestazione Content-Type completa consegnata dal server. A volte può contenere un semplice tipo MIME, ad esempio &quot;text/html&quot;. Oppure può contenere un tipo MIME seguito da altre informazioni, come la codifica del set di caratteri del documento, ad esempio &quot;text/html; charset=iso-8859-1&quot;.
* Per ogni tipo di documento non HTML, `$main::search_content_type` può assumere diversi valori. Il test di ogni valore nello script diventa ingombrante. Ad esempio, alcuni documenti Word presentano valori di tipo di contenuto &quot;application/mspada&quot;, &quot;application/vnd.ms-word&quot; o &quot;application/x-mspada&quot;. In questi casi, `$main::search_content_class` può assumere i seguenti valori:

   * html
   * pdf
   * word
   * eccellere
   * powerpoint
   * mp3
   * text

* Nell’esempio, il test di `$main::search_content_class` per &quot;word&quot; corrisponderebbe a uno dei tre possibili valori di tipo di contenuto.
* Se non viene stampato nulla a STDOUT dallo script di filtraggio, il documento viene utilizzato esattamente come è stato scaricato. In altre parole, se non è necessario modificare nulla in un documento, non è necessario copiare STDIN in STDOUT per quel documento.
* Se si desidera rimuovere tutto il testo da un documento, stampare un file STDOUT valido. Ad esempio, per rimuovere completamente tutto il testo da un documento HTML, eseguire le operazioni seguenti: `print "<html></html>";`

## Aggiunta di uno script di filtro {#task_0AB84FD1133F47F9AA069A79BEA13A22}

Lo script di filtraggio è uno script Perl che viene eseguito per ogni documento scaricato dal sito web.

Utilizza lo script di filtro in combinazione con uno script di inizializzazione, uno script di terminazione e uno script di maschere URL.

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati dello script di filtraggio siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Per aggiungere uno script di filtraggio**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Filtering Script]**.
1. (Facoltativo) Nella pagina [!DNL Filtering Script] , immetti l’URL di un documento sul sito web nel campo [!DNL Test URL] .

   Fai clic su un&#39;opzione di test per visualizzare le modifiche al testo HTML non elaborato.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Campo URL di prova </p> </td> 
      <td colname="col2"> <p>Consente di inserire l’URL di un documento sul sito web. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Verifica l’URL rispetto agli script di filtraggio e alle maschere URL. </p> <p>Viene scaricato il documento dell’URL di test, che viene quindi utilizzato come input STDIN per lo script di filtro. Vengono quindi eseguiti gli script di inizializzazione, filtro e terminazione. Se è presente un output STDOUT dallo script di filtraggio, tale output viene visualizzato in una nuova finestra del browser. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Solo test </p> </td> 
      <td colname="col2"> <p>Verifica solo il funzionamento dello script. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Anteprima </p> </td> 
      <td colname="col2"> <p>Consente di visualizzare la pagina. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visiva completa </p> </td> 
      <td colname="col2"> <p>Genera una visualizzazione completa dei documenti prima e dopo la tabella. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visualizzazione a breve </p> </td> 
      <td colname="col2"> <p>Mostra solo le differenze tra le viste prima e dopo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Esperto (diff) </p> </td> 
      <td colname="col2"> <p>Visualizza l'output non elaborato del comando GNU diff utilizzato per confrontare i file, utilizzando le opzioni della riga di comando fornite. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Script di filtro </p> </td> 
      <td colname="col2"> <p>Consente di incollare lo script di filtro nel campo fornito. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Salva le modifiche </p> </td> 
      <td colname="col2"> <p>Salva lo script di filtro. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Controlla sintassi </p> </td> 
      <td colname="col2"> <p>Consente di eseguire un controllo rapido della sintassi dello script eseguendo gli script di inizializzazione, filtraggio e terminazione. Non aggiorna e salva lo script. </p> <p>Vengono stampati tutti gli errori e gli avvisi del compilatore Perl e tutti gli output STDERR. </p> <p>Prima che gli effetti dello script siano visibili ai clienti, è necessario ricostruire l'indice del sito. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **Opzioni della riga di comando GNU diff**

   Alcune opzioni di differenze GNU che è possibile utilizzare in modalità **[!UICONTROL Expert (diff)]** nella pagina Script di filtraggio pianificato, includono:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione della riga di comando GNU diff </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
      <td colname="col2"> <p> Ignora le modifiche nella quantità di spazio vuoto. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
      <td colname="col2"> <p> Ignora le modifiche che inseriscono o eliminano righe vuote. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
      <td colname="col2"> <p> Utilizza il formato di output del contesto, che mostra tre righe di contesto. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -C linee  </span> </p> </td> 
      <td colname="col2"> <p> Utilizza il formato di output del contesto, mostrando le righe (un numero intero) di contesto, o tre se non sono date righe. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
      <td colname="col2"> <p> Ignora le modifiche nel caso; considera le lettere maiuscole e minuscole equivalenti. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
      <td colname="col2"> <p> Esegue un output simile a uno script ed con modifiche nell’ordine in cui appaiono nel file. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
      <td colname="col2"> <p> Trasmette diffusori in formato RCS; come <span class="codeph"> -f </span> tranne per il fatto che ogni comando specifica il numero di righe interessate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>-u </p> </td> 
      <td colname="col2"> <p> Utilizza il formato di output unificato, che mostra tre righe di contesto. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> - Linee U  </span> </p> </td> 
      <td colname="col2"> <p> Utilizza il formato di output unificato, che mostra le righe (un numero intero) del contesto, o tre se non sono date righe. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Fai clic su **[!UICONTROL Test]** per eseguire il test rispetto agli script di filtro e alle maschere URL.

   Se si fa clic su **[!UICONTROL Test]** non viene aggiornato e salvato lo script di filtro.
1. Nel campo [!DNL Filtering Script] , incolla lo script.
1. (Facoltativo) Fai clic su **[!UICONTROL Check Syntax]** per eseguire un controllo rapido della sintassi dello script eseguendo gli script di filtro, inizializzazione e terminazione.

   **[!UICONTROL Check Syntax]** non aggiorna e salva lo script.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Filtering Script] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sullo script di inizializzazione {#concept_048B4C8BC9F74BE8BB6162C490C201A3}

È possibile utilizzare [!DNL Initialization Script] per modificare il contenuto di un documento Web prima che venga indicizzato.

È possibile inserire tag HTML, rimuovere contenuti irrilevanti e persino creare nuovi metadati HTML in base all’URL di un documento, al tipo MIME e al contenuto esistente. Lo script di inizializzazione è uno script Perl, che fornisce una potente gestione delle stringhe e la flessibilità della corrispondenza delle espressioni regolari. Utilizza lo script di inizializzazione con uno script di filtro, uno script di terminazione, uno script di maschere URL e un URL di prova.

Lo script di inizializzazione viene eseguito una volta prima dell&#39;inizio dell&#39;indicizzazione. Usare questo script per inizializzare le variabili globali e le sottoroutine utilizzate dallo script di filtro. È possibile utilizzare lo script di inizializzazione per stampare i messaggi di stato dallo script di filtraggio al registro dell&#39;indice. È possibile stampare i messaggi su STDERR oppure tramite la subroutine `_search_debug_log()`.

Alcune opzioni di differenze GNU utilizzabili in modalità **[!UICONTROL Expert (diff)]** nella pagina Script di inizializzazione temporanea includono:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Opzione differenze GNU </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> Ignora le modifiche nella quantità di spazio vuoto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> Ignora le modifiche che inseriscono o eliminano righe vuote. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output del contesto, che mostra tre righe di contesto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C linee  </span> </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output del contesto, mostrando le righe (un numero intero) di contesto, o tre se non sono date righe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> Ignora le modifiche nel caso; considera le lettere maiuscole e minuscole equivalenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> Esegue un output simile a uno script ed con modifiche nell’ordine in cui appaiono nel file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> Trasmette diffusori in formato RCS; come <span class="codeph"> -f </span> tranne per il fatto che ogni comando specifica il numero di righe interessate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output unificato, che mostra tre righe di contesto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> - Linee U  </span> </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output unificato, che mostra le righe (un numero intero) del contesto, o tre se non sono date righe. </p> </td> 
  </tr> 
 </tbody> 
</table>

È possibile utilizzare variabili locali, variabili globali o entrambi in questi script. Tutte le variabili globali sono precedute dallo spazio dei nomi &quot;main::&quot;. Quando si avvia lo script di inizializzazione, il relativo ambiente contiene i seguenti handle di file standard:

* STDIN - nulla (restituisce immediatamente EOF in lettura)
* STDOUT - niente (se i dati vengono stampati su STDOUT, vengono scartati)
* STDERR - i dati stampati su STDERR vengono stampati nel log indice come un errore

Inoltre, è possibile scrivere messaggi personalizzati nel registro dell&#39;indice utilizzando la subroutine `_search_debug_log()`, come nell&#39;esempio seguente:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Questi messaggi vengono visualizzati con la parola `DEBUG` come prefisso e non vengono registrati come errori.

Un esempio di script di inizializzazione è il seguente:

```
# My subroutine to do something. 
sub my_sub_for_the_filtering_script { 
    my ($param1, $param2) = @_; 
    ... 
} 
 
# Initialize the document counter. 
$main::doc_count = 0;
```

Vedere [Variabili globali](#global-variables)

### Suggerimenti rapidi {#section_A2CC0302CAF14135BF8EF6171FB184F1}

* Tutte le variabili globali sono precedute dallo spazio dei nomi &quot;main::&quot;: `$main::doc_count = 0;`
* Tutte le variabili locali sono dichiarate con &quot;my&quot;: `my $i = 0;`
* Le sottorubriche sono definite nello script di inizializzazione. Non è necessario un namespace esplicito &quot;main::&quot;: `sub my_sub {` `...`

   `}`

* Testa `$main::search_content_type` prima di apportare modifiche a un file. Il test può aiutare a evitare di apportare modifiche imprudenti ai file binari, come i file SWF o i file PDF:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* L’ `$main::search_content_type` è l’intestazione Content-Type completa consegnata dal server. A volte può contenere un semplice tipo MIME, ad esempio &quot;text/html&quot;. Oppure può contenere un tipo MIME seguito da altre informazioni, come la codifica del set di caratteri del documento, ad esempio &quot;text/html; charset=iso-8859-1&quot;.
* Per ogni tipo di documento non HTML, `$main::search_content_type` può assumere diversi valori. Il test di ogni valore nello script diventa ingombrante. Ad esempio, alcuni documenti Word presentano valori di tipo di contenuto &quot;application/mspada&quot;, &quot;application/vnd.ms-word&quot; o &quot;application/x-mspada&quot;. In questi casi, `$main::search_content_class` può assumere i seguenti valori:

   * html
   * pdf
   * word
   * eccellere
   * powerpoint
   * mp3
   * text

* Nell’esempio, il test di `$main::search_content_class` per &quot;word&quot; corrisponderebbe a uno dei tre possibili valori di tipo di contenuto.
* Se non viene stampato nulla a STDOUT dallo script di filtraggio, il documento viene utilizzato esattamente come è stato scaricato. In altre parole, se non è necessario modificare nulla in un documento, non è necessario copiare STDIN in STDOUT per quel documento.
* Se si desidera rimuovere tutto il testo da un documento, stampare un file STDOUT valido. Ad esempio, per rimuovere completamente tutto il testo da un documento HTML, eseguire le operazioni seguenti: `print "<html></html>";`

## Aggiunta di uno script di inizializzazione {#task_5A03B8D0C46E4674B7CE88203515803B}

Lo script di inizializzazione è uno script Perl che viene eseguito una volta prima dell&#39;indicizzazione di qualsiasi documento.

Utilizza lo script di inizializzazione insieme a uno script di filtro, script di terminazione e script di maschere URL.

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati dello script di inizializzazione siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Per aggiungere uno script di inizializzazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Initialization Script]**.
1. (Facoltativo) Nella pagina [!DNL Initialization Script] , immetti l’URL di un documento sul sito web nel campo [!DNL Test URL] .

   Fai clic su un&#39;opzione di test per visualizzare le modifiche al testo HTML non elaborato.

   Vedi la tabella delle opzioni di filtro in **Aggiunta di uno script di filtro**.

   Fai clic su **[!UICONTROL Test]** per eseguire il test rispetto agli script di filtro e alle maschere URL.

   Se si fa clic su **[!UICONTROL Test]** non viene aggiornato e salvato lo script di inizializzazione.
1. Nel campo [!DNL Initialization Script] , incolla lo script.
1. (Facoltativo) Fai clic su **[!UICONTROL Check Syntax]** per eseguire un controllo rapido della sintassi dello script eseguendo gli script di filtro, inizializzazione e terminazione.

   **[!UICONTROL Check Syntax]** non aggiorna e salva lo script.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Initialization Script] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sullo script di terminazione {#concept_AAD6B3B0E7124874AD0947096FC42F47}

È possibile utilizzare [!DNL Termination Script] per modificare il contenuto di un documento Web prima che venga indicizzato.

È possibile inserire tag HTML, rimuovere contenuti irrilevanti e persino creare nuovi metadati HTML in base all’URL di un documento, al tipo MIME e al contenuto esistente. Lo script di inizializzazione è uno script Perl, che fornisce una potente gestione delle stringhe e la flessibilità della corrispondenza delle espressioni regolari. Lo script di terminazione viene utilizzato con uno script di inizializzazione, uno script di filtraggio, uno script di terminazione, uno script di maschere URL e un URL di test.

Lo script di terminazione viene eseguito una volta che tutti i documenti sono indicizzati. È possibile utilizzare lo script di terminazione per stampare i messaggi di stato dallo script di filtraggio al registro dell&#39;indice. È possibile stampare i messaggi su STDERR oppure tramite la subroutine `_search_debug_log()`.

Alcune opzioni della riga di comando GNU diff che è possibile utilizzare in modalità **[!UICONTROL Expert (diff)]** nella pagina Script di terminazione temporanea includono:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Opzione della riga di comando GNU diff </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> Ignora le modifiche nella quantità di spazio vuoto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> Ignora le modifiche che inseriscono o eliminano righe vuote. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output del contesto, che mostra tre righe di contesto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C linee  </span> </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output del contesto, mostrando le righe (un numero intero) di contesto, o tre se non sono date righe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> Ignora le modifiche nel caso; considera le lettere maiuscole e minuscole equivalenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> Esegue un output simile a uno script ed con modifiche nell’ordine in cui appaiono nel file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> Trasmette diffusori in formato RCS; come <span class="codeph"> -f </span> tranne per il fatto che ogni comando specifica il numero di righe interessate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output unificato, che mostra tre righe di contesto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> - Linee U  </span> </p> </td> 
   <td colname="col2"> <p> Utilizza il formato di output unificato, che mostra le righe (un numero intero) del contesto, o tre se non sono date righe. </p> </td> 
  </tr> 
 </tbody> 
</table>

È possibile utilizzare variabili locali, variabili globali o entrambi in questi script. Tutte le variabili globali sono precedute dallo spazio dei nomi &quot;main::&quot;. Quando si avvia lo script di terminazione, il relativo ambiente contiene i seguenti handle di file standard:

* STDIN - nulla (restituisce immediatamente EOF in lettura)
* STDOUT - niente (se i dati vengono stampati su STDOUT, vengono scartati)
* STDERR - i dati stampati su STDERR vengono stampati nel registro dell&#39;indice come un errore

Inoltre, è possibile scrivere messaggi personalizzati nel registro dell&#39;indice utilizzando la subroutine `_search_debug_log()`, come nell&#39;esempio seguente:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Questi messaggi vengono visualizzati con la parola `DEBUG` come prefisso e non vengono registrati come errori.

Per visualizzare il numero di documenti elaborati dallo script di filtraggio come riga di errore nel registro degli indici, è possibile utilizzare il seguente script di terminazione:

```
# Print the value of the document counter. 
print STDERR "Total docs: $main::doc_count\n"; 
# Or, using the log subroutine: 
_search_debug_log("Total docs: " . $main::doc_count);
```

Vedere [Variabili globali](#global-variables)

### Suggerimenti rapidi {#section_5790EA7ACAC046CBA01F759F88E2460F}

* Tutte le variabili globali sono precedute dallo spazio dei nomi &quot;main::&quot;: `$main::doc_count = 0;`
* Tutte le variabili locali sono dichiarate con &quot;my&quot;: `my $i = 0;`
* Le sottorubriche sono definite nello script di inizializzazione. Non è necessario un namespace esplicito &quot;main::&quot;: `sub my_sub {` `...`

   `}`

* Testa `$main::search_content_type` prima di apportare modifiche a un file. Il test può aiutare a evitare di apportare modifiche imprudenti ai file binari, come i file SWF o i file PDF:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* L’ `$main::search_content_type` è l’intestazione Content-Type completa consegnata dal server. A volte può contenere un semplice tipo MIME, ad esempio &quot;text/html&quot;. Oppure può contenere un tipo MIME seguito da altre informazioni, come la codifica del set di caratteri del documento, ad esempio &quot;text/html; charset=iso-8859-1&quot;.
* Per ogni tipo di documento non HTML, `$main::search_content_type` può assumere diversi valori. Il test di ogni valore nello script diventa ingombrante. Ad esempio, alcuni documenti Word presentano valori di tipo di contenuto &quot;application/mspada&quot;, &quot;application/vnd.ms-word&quot; o &quot;application/x-mspada&quot;. In questi casi, `$main::search_content_class` può assumere i seguenti valori:

   * html
   * pdf
   * word
   * eccellere
   * powerpoint
   * mp3
   * text

* Nell’esempio, il test di `$main::search_content_class` per &quot;word&quot; corrisponderebbe a uno dei tre possibili valori di tipo di contenuto.
* Se non viene stampato nulla a STDOUT dallo script di filtraggio, il documento viene utilizzato esattamente come è stato scaricato. In altre parole, se non è necessario modificare nulla in un documento, non è necessario copiare STDIN in STDOUT per quel documento.
* Se si desidera rimuovere tutto il testo da un documento, stampare un file STDOUT valido. Ad esempio, per rimuovere completamente tutto il testo da un documento HTML, eseguire le operazioni seguenti: `print "<html></html>";`

## Aggiunta di uno script di terminazione {#task_F0CFB412871642CFBC88132889C5B6F9}

Lo script di terminazione è uno script Perl che viene eseguito una volta che tutti i documenti sono indicizzati.

Lo script di terminazione viene utilizzato insieme a uno script di filtraggio, uno script di terminazione e uno script di maschere URL.

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati dello script di inizializzazione siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Per aggiungere uno script di terminazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Termination Script]**.
1. (Facoltativo) Nella pagina [!DNL Termination Script] , immetti l’URL di un documento sul sito web nel campo [!DNL Test URL] .

   Fai clic su un&#39;opzione di test per visualizzare le modifiche al testo HTML non elaborato.

   Vedi la tabella delle opzioni di filtro in **Aggiunta di uno script di filtro**.

   Fai clic su **[!UICONTROL Test]** per eseguire il test rispetto agli script di filtro e alle maschere URL.

   Facendo clic su **[!UICONTROL Test]** non si aggiorna e si salva lo script di terminazione.
1. Nel campo [!DNL Termination Script] , incolla lo script.
1. (Facoltativo) Fai clic su **[!UICONTROL Check Syntax]** per eseguire un controllo rapido della sintassi dello script eseguendo gli script di inizializzazione, filtraggio e terminazione.

   **[!UICONTROL Check Syntax]** non aggiorna e salva lo script.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Termination Script] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sullo script delle maschere URL {#concept_384F32EA18F84853A7BA99A04009330B}

Con il filtro, è possibile modificare il contenuto di un documento web prima che venga indicizzato. È possibile inserire tag HTML, rimuovere contenuti irrilevanti e persino creare nuovi metadati HTML in base all’URL di un documento, al tipo MIME e al contenuto esistente. Lo script delle maschere URL è uno script Perl che fornisce una gestione efficace delle stringhe e la flessibilità della corrispondenza delle espressioni regolari.

Per modificare il contenuto dei documenti esistenti solo in una parte specifica del sito web, puoi specificare maschere URL, maschere URL escluse o entrambe per definire le pagine appropriate.

Se si desidera modificare solo i documenti in `"https://www.mysite.com/faqs/"`, è possibile utilizzare il seguente set di maschere:

```
include https://www.mysite.com/faqs/ 
exclude *
```

Puoi anche utilizzare l’espressione regolare in uno script di maschera URL come nell’esempio seguente:

```
include regexp ^https://www\.mysite\.com.*/faqs/.*$ 
exclude *
```

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Le maschere URL con script vengono considerate nell’ordine in cui sono state inserite nel campo [!DNL URL Masks] . Quando un URL di un documento corrisponde a una maschera, il documento viene incluso o escluso in base al tipo di maschera. Se l’URL di un documento non corrisponde ad alcuna maschera URL, il documento viene incluso solo se il relativo tipo MIME è &quot;text/html&quot;. Sono esclusi tutti gli altri tipi MIME.

## Aggiunta di uno script di maschera URL {#task_D18F2A496C1C45C997B5DA650AAF5D59}

L’URL include maschere ed esclude maschere per modificare il contenuto dei documenti esistenti solo in una parte specifica del sito web.

Prima che gli effetti delle impostazioni delle maschere URL siano visibili ai visitatori, ricostruisci l&#39;indice del sito.

**Per aggiungere uno script di maschera URL**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL URL Masks]**.
1. (Facoltativo) Nella pagina [!DNL URL Masks], nel campo [!DNL Test URL] immetti un URL di un documento sul sito web, quindi fai clic su **[!UICONTROL Test]** per verificare l’URL rispetto agli script e alle maschere di filtraggio.

   Viene scaricato il documento dell’URL di test, utilizzato come input STDIN per lo script di filtraggio. Vengono quindi eseguiti gli script di filtro, inizializzazione e terminazione. Se c&#39;è un output STDOUT dallo script di filtraggio che l&#39;output viene visualizzato in una nuova finestra del browser.

   Se si fa clic su **[!UICONTROL Test]** non si aggiorna e si salva lo script.
1. Nel campo [!DNL URL Masks] , immetti una maschera URL per riga.
1. (Facoltativo) Fai clic su **[!UICONTROL Check Syntax]** per eseguire un controllo rapido della sintassi delle maschere URL eseguendo gli script di filtro, inizializzazione e terminazione.

   **[!UICONTROL Check Syntax]** non aggiorna e salva lo script.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL URL Masks] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sui tipi di contenuto nel filtro {#concept_E3EFF4A148EA4D21AFD0A5453A00427E}

Consente di selezionare i tipi di contenuto che si desidera filtrare per questo account.

Il testo trovato all’interno dei tipi di contenuto selezionati viene convertito in HTML e quindi elaborato utilizzando lo script specificato in Script di filtraggio.

Vedere [Informazioni sul filtro di script](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

I tipi di contenuto selezionabili sono i seguenti:

* documenti PDF
* Documenti di testo
* Adobe di film di Flash
* File di Microsoft Word
* File di Microsoft Office (OpenXML)
* File di Microsoft Excel
* File Microsoft Powerpoint
* Testo in file musicali MP3

Prima che gli effetti delle impostazioni o delle modifiche dei tipi di contenuto siano visibili ai clienti, è necessario ricreare l&#39;indice del sito.

## Selezione dei tipi di contenuto filtrati {#task_C46081FA425A43EC8FDE6EA4A52A170A}

Selezionare i tipi di contenuto che si desidera passare allo script specificato in Script di filtraggio.

Vedere [Informazioni sul filtro di script](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

**Selezione dei tipi di contenuto filtrati**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Content Types]**.
1. Nella pagina [!DNL Content Types] , controlla i tipi di contenuto che desideri passare allo script del filtro.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Content Types] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
