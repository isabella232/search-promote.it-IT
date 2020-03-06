---
description: Utilizzate il menu Rewrite Rules (Regole di riscrittura) per impostare la ricerca per indicizzazione e le regole dell'URL e del titolo.
seo-description: Utilizzate il menu Rewrite Rules (Regole di riscrittura) per impostare la ricerca per indicizzazione e le regole dell'URL e del titolo.
seo-title: Informazioni sul menu Riscrittura regole
solution: Target
subtopic: Rewrite Rules
title: Informazioni sul menu Riscrittura regole
topic: Settings,Site search and merchandising
uuid: 77ee84dd-fdba-4d34-ae8e-2fe786599800
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# Informazioni sul menu Riscrittura regole {#about-the-rewrite-rules-menu}

Utilizzate il menu Rewrite Rules (Regole di riscrittura) per impostare la ricerca per indicizzazione e le regole dell&#39;URL e del titolo.

## Informazioni sulle regole URL per l&#39;elenco di ricerca per indicizzazione {#concept_B71CF4C8030A4A74A22C3BFE4DE3B865}

Regole URL per ricerca per indicizzazione specificano in che modo gli URL che incontra all&#39;interno del contenuto Web vengono riscritti. Potete specificare un numero illimitato di regole e condizioni e manipolare qualsiasi parte degli URL incontrati.

<!-- 

c_about_crawl_list_store_url_rules.xml

 -->

Le regole di ricerca per indicizzazione sono particolarmente utili per riscrittura di parti dinamiche di un URL, ad esempio un identificatore di sessione univoco per ogni cliente che visita il sito Web. Potete inoltre utilizzare le regole di riscrittura per nascondere parti di un URL, come parametri di query, dal robot di ricerca. Per impostazione predefinita, non vengono specificate regole e non viene eseguita alcuna riscrittura URL.

Quando un sito Web viene sottoposto a ricerca per indicizzazione, gli URL del contenuto incorporato vengono memorizzati in un elenco temporaneo di ulteriori pagine Web da sottoporre a ricerca per indicizzazione. Prima di aggiungere un URL a questo elenco, vengono applicate le regole di riscrittura store. In genere, le regole di riscrittura store vengono utilizzate per rimuovere un ID sessione da un URL o per applicare un ID sessione specifico per la ricerca per indicizzazione. Quando il robot di ricerca recupera un URL dall’elenco, le regole di riscrittura Recupera vengono utilizzate per manipolare nuovamente parti di tale URL. In genere, le regole di recupero vengono utilizzate per inserire nuovamente nell’URL dati sensibili in base al tempo. È questo URL finale che viene utilizzato per recuperare la pagina dal sito Web.

Consultate [Informazioni Sulle Regole](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA)Per Il Recupero Degli URL Per L’Elenco Di Ricerca Per indicizzazione.

In genere, si utilizzano esclusivamente le regole URL store. Recupera regole URL sono necessarie solo se gli URL contengono dati dinamici, come un ID sessione, e se tali dati dinamici cambiano nel tempo per restare validi. In questo caso, utilizzate le regole URL store per ottenere lo stato più recente dei dati dagli URL incontrati. Quindi utilizzate le regole di recupero URL per aggiungere quei dati a ogni URL quando il robot di ricerca tenta di recuperare la pagina.

Ogni regola è specificata con una direttiva di riscrittura regola (RewriteRule) e una o più condizioni di riscrittura facoltative (RewriteCond). L&#39;ordine delle regole è importante. Il set di regole viene ripetuto a ciclo continuo per regola. Quando una regola corrisponde, viene ripetuto a ciclo continuo in tutte le condizioni di riscrittura corrispondenti. Una regola URL di ricerca per indicizzazione viene specificata nel modo seguente:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

Quando viene rilevato un URL incorporato, il robot di ricerca tenta di corrispondere l&#39;URL al Pattern di ciascuna regola di ricerca per indicizzazione. Se il pattern corrisponde, il motore di riscrittura cerca le direttive RewriteCond corrispondenti. Se non sono presenti condizioni, l&#39;URL viene sostituito con un nuovo valore costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se esistono, le condizioni vengono elaborate nell&#39;ordine in cui sono elencate. Il motore di riscrittura tenta di far corrispondere un pattern di condizione (CondPattern) a una stringa di prova (TestString). Se i due valori corrispondono, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l&#39;URL viene sostituito con la Sostituzione specificata nella regola. Se la condizione non è soddisfatta, l&#39;intero insieme di condizioni e la regola corrispondente non riesce.

## Informazioni sulle direttive RewriteRule {#section_162122340BB34F12BB9A36DC9349092B}

Una direttiva RewriteRule ha il seguente modulo:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` può essere un&#39;espressione regolare POSIX applicata all&#39;URL corrente. L&#39;&quot;URL corrente&quot; può essere diverso dall&#39;URL originale richiesto, perché le regole precedenti potrebbero aver già trovato una corrispondenza e aver modificato l&#39;URL.

Consultate Espressioni [](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)regolari.

Non è possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per applicare il prefisso al pattern. Il carattere &quot;not&quot; consente di negare un pattern, ovvero di essere true solo se l&#39;URL corrente NON corrisponde a questo pattern. Il carattere &quot;not&quot; può essere utilizzato quando è meglio corrispondere a un pattern negativo, o come regola predefinita finale.

>[!NOTE]
>
>Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato se la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento in background nel pattern, a cui possono fare riferimento i campi Sostituzione e CondPattern.

**Sostituzione** L’URL viene sostituito dalla stringa di sostituzione, che contiene quanto segue:

Testo normale: Testo passato inalterato.

I riferimenti posteriori consentono di accedere alle parti raggruppate (parentesi interne) del Pattern o del Pattern di CondPattern. Di seguito sono riportati i due tipi di riferimenti a posteriori:

* **RiscriviRiferimenti** RewriteRule Questi corrispondono a riferimenti posteriori nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* **RewriteCond BackReferences** Questi corrispondono a riferimenti indietro nell&#39;ultimo pattern di cond RewriteCond corrispondente e si presentano come %N (0 &lt;= N &lt;= 9).

Variabili: Si tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE è una stringa per il nome di una variabile definita. Per ulteriori informazioni sull&#39;impostazione delle variabili di ambiente, vedere `*[E]*` il flag .

Funzioni: Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è il seguente:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .
* escape URL codifica tutti i caratteri nella *chiave*.
* I caratteri &#39;a&#39;...z&#39;, &#39;A&#39;...Z&#39;, &#39;0&#39;...9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati; gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel relativo equivalente con codifica URL %xx.
* unescape riconforma &#39;+&#39; nello spazio e tutti i caratteri con codifica URL %xx in caratteri singoli.

>[!NOTE]
>
>Esiste una stringa di sostituzione speciale: significa `'-'` &quot;NO replace&quot;. La `'-'` stringa viene spesso utilizzata con il flag C (catena), consentendo la corrispondenza di un URL con diversi pattern prima che si verifichi una sostituzione.

**Flag**

(Facoltativo) Racchiudere i flag tra parentesi `[]`. I flag multipli sono separati da virgola.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Ultima regola. </p> <p>Interrompe il processo di riscrittura e non applica ulteriori regole di riscrittura. Usate questo flag per impedire ulteriori elaborazioni dell’URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Il prossimo giro. </p> <p> Esegue di nuovo il processo di riscrittura (iniziando nuovamente con la prima regola di riscrittura) utilizzando l'URL dell'ultima regola di riscrittura (non l'URL originale). Fai attenzione a non creare un ciclo di vita! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Concatenato con la regola successiva. </p> <p>Connette la regola corrente alla regola successiva (che può essere collegata anche alla regola seguente, e così via). Se una regola corrisponde, il processo di sostituzione continua normalmente. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p> Fa sì che il pattern non faccia distinzione tra maiuscole e minuscole (ovvero, non esiste alcuna differenza tra 'A-Z' e 'a-z') quando il pattern viene confrontato con l'URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole num successive nel set di regole. Utilizzate questo flag per creare costrutti pseudo if-then-else. L'ultima regola della clausola then diventa un skip=N dove N è il numero di regole nella clausola else. </p> <p> <p>Nota:  Questo flag non è lo stesso del flag 'chain|C'!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Imposta la variabile ambientale. </p> <p>Crea una variabile ambientale "VAR" impostata sul valore VAL, in cui VAL può contenere riferimenti a posteriori di espressioni regolari, $N e %N, espansi. È possibile utilizzare questo flag più volte per impostare più variabili. Le variabili possono essere successivamente eliminate dal riferimento in un pattern RewriteCond seguente tramite %{VAR}. </p> <p>Usate questo flag per rimuovere e ricordare le informazioni dagli URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le regole di riscrittura store e le regole di riscrittura Recupera condividono i valori delle variabili. A causa di questo comportamento, potete impostare una variabile su un valore sessionid sensibile all&#39;ora quando un URL incorporato viene rilevato e memorizzato. Quando l’URL successivo viene recuperato dall’elenco di memorizzazione temporanea, prima di recuperare la pagina è possibile aggiungere ad esso il valore dell’ID sessione più recente.

**Esempio di RewriteRule con una funzione**

Si supponga di disporre di un server sensibile alle maiuscole/minuscole, che gestisce le stringhe `"www.mydomain.com"` e `"www.MyDomain.com"` in modo diverso. Per il corretto funzionamento del server, assicurarsi che il dominio sia sempre `"www.mydomain.com"` anche se alcuni documenti contengono collegamenti che fanno riferimento a `"www.MyDomain.com."` A tal fine, è possibile utilizzare la regola seguente:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

Questa regola di riscrittura utilizza la funzione `tolower` per riscrivere la porzione di dominio di un URL in modo da garantire che sia sempre minuscola, come nell’esempio seguente:

1. Il pattern `(^https://([^/]*)(.*)$)` contiene un riferimento di sfondo `([^/]*)` che corrisponde a tutti i caratteri compresi tra `https://` e il primo `/` nell&#39;URL. Il pattern contiene anche un secondo riferimento di sfondo `(.*)` che corrisponde a tutti i caratteri rimanenti nell&#39;URL.

1. La sostituzione `(https://${tolower:$1}$2)` indica al motore di ricerca di riscrivere l’URL utilizzando la `tolower` funzione sul primo riferimento `(https:// ${tolower:$1}$2)` lasciando invariato il resto dell’URL `(https://${tolower:$1} $2)`.

Pertanto, un URL del modulo `https://www.MyDomain.com/INTRO/index.Html` viene riscritto come `https://www.mydomain.com/INTRO/index.Html`.

## Informazioni sulle direttive RewriteCond {#section_CD5A19B2D3204F73B645411931FC34A1}

La direttiva RewriteCond definisce una condizione di regola. Quando un oggetto RewriteCond precede un oggetto RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e si applicano le condizioni aggiuntive. Le condizioni di riscrittura hanno la seguente forma:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` è una stringa che può contenere i seguenti costrutti:

Testo normale: Testo passato inalterato.

I riferimenti posteriori consentono di accedere alle parti raggruppate (parentesi interne) del Pattern o del Pattern di CondPattern. Di seguito sono riportati i due tipi di riferimenti a posteriori:

* **RiscriviRiferimenti** RewriteRule Questi corrispondono a riferimenti posteriori nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`.

* **RewriteCond BackReferences** Questi corrispondono a riferimenti indietro nell&#39;ultimo pattern di cond RewriteCond corrispondente e si presentano come %N (0&lt;= N &lt;= 9).

Variabili: Sono variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull&#39;impostazione delle variabili, vedere il flag Riscrittura *`[E]`* regola.

Funzioni: Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è il seguente:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .
* l’URL escape codifica tutti i caratteri nella chiave. I caratteri &#39;a&#39;...z&#39;, &#39;A&#39;...Z&#39;, &#39;0&#39;...9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel loro equivalente con codifica `%xx` URL.
* unescape riconforma &#39;+&#39; nello spazio e tutti i caratteri di codifica `%xx` URL in caratteri singoli.

**CondPattern** è un’espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un `!` carattere (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, è possibile utilizzare una delle seguenti varianti speciali:

>[!NOTE]
>
>È inoltre possibile assegnare un prefisso a tutti questi test con un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lessicamente meno. </p> <p> Considera CondPattern come una stringa semplice e lo confronta in modo lessicale con TestString. True se TestString è lessicalmente minore di CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lessicamente più grande. </p> <p> Considera CondPattern come una stringa semplice e lo confronta in modo lessicale con TestString. True se TestString è lessicalmente maggiore di CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexicamente uguale. </p> <p> Considera CondPattern come una stringa semplice e lo confronta in modo lessicale con TestString. True se TestString è lessicalmente uguale a CondPattern, ovvero, le due stringhe sono esattamente uguali (carattere per carattere). Se CondPattern è solo "" (due virgolette), questo confronta TestString con la stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag**(facoltativo) Racchiudono i flag tra parentesi `[]`. I flag multipli sono separati da virgola.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Nessun caso. </p> <p>Questo flag fa sì che il test non faccia distinzione tra maiuscole e minuscole, ovvero non esiste alcuna differenza tra 'A-Z' e 'a-z' sia nella TestString espansa che nel CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>O la condizione successiva. </p> <p>Utilizzate questo flag per combinare le condizioni della regola con un operatore OR locale invece dell'operatore AND implicito. Senza questa bandiera, si dovrebbe scrivere più volte la regola/cond. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

Alcune pagine Web assegnano una variabile CGI &quot;sessionid&quot; la prima volta che un visitatore arriva a un sito. Questa variabile viene utilizzata per identificare il visitatore e, mentre il visitatore naviga nel sito, la variabile viene passata. Poiché il robot di ricerca sembra un visitatore del sito, gli viene assegnato un numero &quot;sessionid&quot;. Il robot di ricerca mantiene questo singolo valore &quot;sessionid&quot;, anche se una seconda pagina del sito tenta di assegnare un nuovo valore. A questo scopo, è necessario riscrivere due regole.

La prima regola viene utilizzata per identificare e memorizzare la variabile sessionid:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule utilizza un flag E `([E=sessionid:$1])` per assegnare il valore corrente del parametro CGI sessionid alla variabile `sessionid`. Il riferimento `$1` fa riferimento al primo riferimento di sfondo, contenuto tra il primo set di parentesi nel Pattern di RewriteRule `([^&#]+)`.

L&#39;espressione regolare `^&#]+` corrisponde alla porzione di un URL tra la parola `sessionid` e il `**&**or**#**` carattere successivo. Poiché questa regola di riscrittura viene utilizzata solo per creare il valore iniziale per la variabile sessionid, non viene riscritta. Il campo Sostituzione della regola è impostato in modo `-` da indicare che non è richiesta alcuna riscrittura.

RewriteCond esamina la variabile `sessionid` ( `%{sessionid}`). Se non ha nemmeno un singolo carattere (!.+), quindi la regola RewriteRule corrisponde.

Utilizzando questa regola, l&#39;URL viene letto come `https://www.domain.com/home/?sessionid=1234&function=start` e assegna il valore `1234` alla variabile `sessionid`.

La seconda regola viene utilizzata per riscrivere tutti gli URL che corrispondono al seguente pattern RewriteRule:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

Il pattern RewriteRule contiene due riferimenti a posteriori: `(.+)` e `(.*)`. Il primo riferimento di sfondo corrisponde a tutti i caratteri precedenti `sessionid`. Il secondo backreference corrisponde a tutti i caratteri dopo il termine `&` o `#`.

Il pattern di sostituzione riscrive l’URL utilizzando il primo riferimento di sfondo, seguito dalla stringa &quot;sessionid=&quot;, seguita dal valore della variabile ID di sessione definita dalla prima regola `%{sessionid}`, seguita dal secondo riferimento di sfondo. `($1sessionid=%{sessionid} $2)`

Tenere presente che questa regola di riscrittura non contiene un RewriteCond. Di conseguenza, viene generato un riscrittura per tutti gli URL che corrispondono al *pattern* RewriteRule. Pertanto, se il valore della variabile sessionid ( `%{sessionid}`) è `1234`, un URL del modulo `https://www.domain.com/products/?sessionid=5678&function=buy` viene riscritto come `https://www.domain.com/products/?sessionid=1234&function=buy`

## Riconoscimento {#section_B17088EF38244496BC1DDD4ECF75EB5B}

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta di una regola per l’URL dell’archivio degli elenchi di ricerca per indicizzazione {#task_22DD40DF95584B12BE8E6ECFBF579BCD}

Potete aggiungere regole per l’URL dell’archivio degli elenchi di ricerca per indicizzazione per specificare in che modo vengono riscritti gli URL che si incontrano all’interno del contenuto Web. Potete specificare un numero illimitato di regole e condizioni e manipolare qualsiasi parte degli URL incontrati.

<!-- 

t_adding_a_crawl_list_store_url_rule.xml

 -->

**Per aggiungere regole per l&#39;URL dell&#39;archivio di elenchi di ricerca per indicizzazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Store URL Rules]**.
1. Nel [!DNL Crawl List Store URL Rules] campo, immettere le regole desiderate.

   Sono consentite righe vuote e righe di commento che iniziano con il carattere &quot;#&quot; (hash).
1. (Facoltativo) Nella [!DNL Crawl List Store URL Rules] pagina, nel [!DNL Test Crawl List Store URL Rules] campo, immettete un URL di prova di cui desiderate verificare le regole di ricerca per indicizzazione, quindi fate clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL Crawl List Store URL Rules] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sulle regole URL per il recupero dell&#39;elenco di ricerca per indicizzazione {#concept_EC8E2E48B99A458D8567B526C9827CBA}

Regole URL per ricerca per indicizzazione specificano in che modo vengono riscritti gli URL che si trovano all&#39;interno del contenuto Web. Potete specificare un numero illimitato di regole e condizioni e manipolare qualsiasi parte degli URL incontrati.

<!-- 

c_about_crawl_list_retrieve_url_rules.xml

 -->

Prima che gli effetti delle regole siano visibili ai clienti, accertatevi di ricreare l&#39;indice del sito.

Le regole di ricerca per indicizzazione sono particolarmente utili per riscrittura di parti dinamiche di un URL, ad esempio un identificatore di sessione univoco per ogni cliente che visita il sito Web. Potete inoltre utilizzare le regole di riscrittura per nascondere parti di un URL, come parametri di query, dal robot di ricerca. Per impostazione predefinita, non vengono specificate regole e non viene eseguita alcuna riscrittura URL.

Quando un sito Web viene sottoposto a ricerca per indicizzazione, gli URL del contenuto incorporato vengono memorizzati in un elenco temporaneo di ulteriori pagine Web da sottoporre a ricerca per indicizzazione. Quando il robot di ricerca recupera un URL dall’elenco, le regole di riscrittura recupero vengono utilizzate per manipolare parti di tale URL. In genere, le regole di recupero vengono utilizzate per inserire dati sensibili in base al tempo in un URL. È questo URL finale che viene utilizzato per recuperare la pagina dal sito Web.

Recupera regole di riscrittura sono necessarie solo se gli URL contengono dati dinamici, come un ID sessione, e se tali dati dinamici cambiano nel tempo per restare validi. In questo caso, utilizzate le regole di riscrittura store per ottenere lo stato più recente dei dati dagli URL riscontrati. Quindi, utilizzate le regole di riscrittura recupero per aggiungere tali dati a ogni URL quando i robot di ricerca recuperano la pagina.

Ogni regola è specificata con una direttiva di riscrittura regola (RewriteRule) e una o più condizioni di riscrittura facoltative (RewriteCond). L&#39;ordine delle regole è importante. Il set di regole viene ripetuto a ciclo continuo per regola. Quando una regola corrisponde, viene ripetuto a ciclo continuo in tutte le condizioni di riscrittura corrispondenti. Una regola URL di ricerca per indicizzazione viene specificata nel modo seguente:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

Quando viene rilevato un URL incorporato, il robot di ricerca tenta di corrispondere l&#39;URL al Pattern di ciascuna regola di ricerca per indicizzazione. Se il pattern corrisponde, il motore di riscrittura cerca le direttive RewriteCond corrispondenti. Se non sono presenti condizioni, l&#39;URL viene sostituito con un nuovo valore costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se esistono, le condizioni vengono elaborate nell&#39;ordine in cui sono elencate. Il motore di riscrittura tenta di far corrispondere un pattern di condizione (CondPattern) a una stringa di prova (TestString). Se i due valori corrispondono, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l&#39;URL viene sostituito con la Sostituzione specificata nella regola. Se la condizione non è soddisfatta, l&#39;intero insieme di condizioni e la regola corrispondente non riesce.

## Informazioni sulle direttive RewriteRule {#section_32B24B29627946398AFBC5F869A610CB}

Una direttiva RewriteRule ha il seguente modulo:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` può essere un&#39;espressione regolare POSIX applicata all&#39;URL corrente. L&#39;&quot;URL corrente&quot; può essere diverso dall&#39;URL originale richiesto, perché le regole precedenti potrebbero aver già trovato una corrispondenza e aver modificato l&#39;URL.

Consultate Espressioni [](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)regolari.

Non è possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per applicare il prefisso al pattern. Il carattere &quot;not&quot; consente di negare un pattern, ovvero di essere true solo se l&#39;URL corrente NON corrisponde a questo pattern. Il carattere &quot;not&quot; può essere utilizzato quando è meglio corrispondere a un pattern negativo, o come regola predefinita finale.

>[!NOTE]
>
>Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato se la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento in background nel pattern, a cui possono fare riferimento i campi Sostituzione e CondPattern.

**Sostituzione** L’URL viene sostituito dalla stringa di sostituzione, che contiene quanto segue:

Testo normale: Testo passato inalterato.

I riferimenti posteriori consentono di accedere alle parti raggruppate (parentesi interne) del Pattern o del Pattern di CondPattern. Di seguito sono riportati i due tipi di riferimenti a posteriori:

* **RiscriviRiferimenti** RewriteRule Questi corrispondono a riferimenti posteriori nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* ** RewriteCond BackReferences** Questi corrispondono a riferimenti posteriori nell&#39;ultimo pattern di cond RewriteCond corrispondente e assumono la forma %N (0 &lt;= N &lt;= 9).

Variabili: Si tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE è una stringa per il nome di una variabile definita. Per ulteriori informazioni sull&#39;impostazione delle variabili di ambiente, vedere il flag *[E]* .

Funzioni: Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è il seguente:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .
* escape URL codifica tutti i caratteri nella *chiave*.
* I caratteri &#39;a&#39;...z&#39;, &#39;A&#39;...Z&#39;, &#39;0&#39;...9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati; gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel relativo equivalente con codifica URL %xx.
* unescape riconforma &#39;+&#39; nello spazio e tutti i caratteri con codifica URL %xx in caratteri singoli.

>[!NOTE]
>
>Esiste una stringa di sostituzione speciale: &#39;-&#39; significa &quot;NO replace&quot;. La stringa &#39;-&#39; viene spesso utilizzata con il flag C (catena), consentendo di associare un URL a diversi pattern prima che si verifichi una sostituzione.

**Flag**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Ultima regola. </p> <p>Interrompe il processo di riscrittura e non applica ulteriori regole di riscrittura. Usate questo flag per impedire ulteriori elaborazioni dell’URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Il prossimo giro. </p> <p> Esegue di nuovo il processo di riscrittura (iniziando nuovamente con la prima regola di riscrittura) utilizzando l'URL dell'ultima regola di riscrittura (non l'URL originale). Fai attenzione a non creare un ciclo di vita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Concatenato con la regola successiva. </p> <p>Connette la regola corrente alla regola successiva (che può essere collegata anche alla regola seguente, e così via). Se una regola corrisponde, il processo di sostituzione continua normalmente. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p> Fa sì che il pattern non faccia distinzione tra maiuscole e minuscole (ovvero, non esiste alcuna differenza tra 'A-Z' e 'a-z') quando il pattern viene confrontato con l'URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole num successive nel set di regole. Utilizzate questo flag per creare costrutti pseudo if-then-else. L'ultima regola della clausola then diventa un skip=N dove N è il numero di regole nella clausola else. </p> <p> <p>Nota:  Questo flag non è lo stesso del flag 'chain|C'!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Imposta la variabile ambientale. </p> <p>Crea una variabile ambientale "VAR" impostata sul valore VAL, in cui VAL può contenere riferimenti a posteriori di espressioni regolari, $N e %N, espansi. È possibile utilizzare questo flag più volte per impostare più variabili. Le variabili possono essere successivamente eliminate dal riferimento in un pattern RewriteCond seguente tramite %{VAR}. </p> <p>Usate questo flag per rimuovere e ricordare le informazioni dagli URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le regole di riscrittura store e le regole di riscrittura Recupera condividono i valori delle variabili. A causa di questo comportamento, potete impostare una variabile su un valore sessionid sensibile all&#39;ora quando un URL incorporato viene rilevato e memorizzato. Quando l’URL successivo viene recuperato dall’elenco di memorizzazione temporanea, prima di recuperare la pagina è possibile aggiungere ad esso il valore dell’ID sessione più recente.

**Esempio di RewriteRule con una funzione**

Si supponga di disporre di un server sensibile alle maiuscole/minuscole, che gestisce le stringhe &quot;www.mydomain.com&quot; e &quot;www.MyDomain.com&quot; in modo diverso. Per il corretto funzionamento del server, accertatevi che il dominio sia sempre &quot;www.mydomain.com&quot; anche se alcuni documenti contengono collegamenti che fanno riferimento a &quot;www.MyDomain.com&quot;. A tal fine, potete utilizzare la seguente regola:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

Questa regola di riscrittura utilizza la funzione `tolower` per riscrivere la porzione di dominio di un URL in modo da garantire che sia sempre minuscola, come nell’esempio seguente:

1. Il pattern `(^https://([^/]*)(.*)$)` contiene un riferimento di sfondo ** `([^/]*)`** che corrisponde a tutti i caratteri compresi tra `https://` e il primo `/` nell&#39;URL. Il pattern contiene anche un secondo riferimento di sfondo `(.*)` che corrisponde a tutti i caratteri rimanenti nell&#39;URL.
1. La sostituzione `(https://${tolower:$1}$2)` indica al motore di ricerca di riscrivere l’URL utilizzando la `tolower` funzione sul primo riferimento `(https:// ${tolower:$1}$2)` lasciando invariato il resto dell’URL `(https://${tolower:$1} $2)`.

Pertanto, un URL del modulo `https://www.MyDomain.com/INTRO/index.Html` viene riscritto come `https://www.mydomain.com/INTRO/index.Html`.

## Informazioni sulle direttive RewriteCond {#section_ADD642A24B68452CB98294A0BD687EC3}

La direttiva RewriteCond definisce una condizione di regola. Quando un oggetto RewriteCond precede un oggetto RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e si applicano le condizioni aggiuntive. Le condizioni di riscrittura hanno la seguente forma:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` è una stringa che può contenere i seguenti costrutti:

Testo normale: Testo passato inalterato.

I riferimenti posteriori consentono di accedere alle parti raggruppate (parentesi interne) del Pattern o del Pattern di CondPattern. Di seguito sono riportati i due tipi di riferimenti a posteriori:

* **RiscriviRiferimenti** RewriteRule Questi corrispondono a riferimenti posteriori nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`.

* **RewriteCond BackReferences** Questi corrispondono a riferimenti indietro nell&#39;ultimo pattern di cond RewriteCond corrispondente e si presentano come %N (0&lt;= N &lt;= 9).

Variabili: Sono variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull&#39;impostazione delle variabili, vedere il flag Riscrittura *`[E]`* regola.

Funzioni: Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è il seguente:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .
* l’URL escape codifica tutti i caratteri nella chiave. I caratteri &#39;a&#39;...z&#39;, &#39;A&#39;...Z&#39;, &#39;0&#39;...9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel relativo equivalente con codifica URL %xx.
* unescape riconforma &#39;+&#39; nello spazio e tutti i caratteri di codifica URL %xx in caratteri singoli.

**CondPattern** è un’espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un &#39;!&#39; carattere (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, è possibile utilizzare una delle seguenti varianti speciali:

>[!NOTE]
>
>È inoltre possibile assegnare un prefisso a tutti questi test con un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lessicamente meno. </p> <p> Considera CondPattern come una stringa semplice e lo confronta in modo lessicale con TestString. True se TestString è lessicalmente minore di CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lessicamente più grande. </p> <p> Considera CondPattern come una stringa semplice e lo confronta in modo lessicale con TestString. True se TestString è lessicalmente maggiore di CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexicamente uguale. </p> <p> Considera CondPattern come una stringa semplice e lo confronta in modo lessicale con TestString. True se TestString è lessicalmente uguale a CondPattern, ovvero, le due stringhe sono esattamente uguali (carattere per carattere). Se CondPattern è solo "" (due virgolette), questo confronta TestString con la stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag**(facoltativo) Racchiudono i flag tra parentesi `[]`. I flag multipli sono separati da virgola.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Nessun caso. </p> <p>Questo flag fa sì che il test non faccia distinzione tra maiuscole e minuscole, ovvero non esiste alcuna differenza tra 'A-Z' e 'a-z' sia nella TestString espansa che nel CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>O la condizione successiva. </p> <p>Utilizzate questo flag per combinare le condizioni della regola con un operatore OR locale invece dell'operatore AND implicito. Senza questa bandiera, si dovrebbe scrivere più volte la regola/cond. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

Alcune pagine Web assegnano una variabile CGI &quot;sessionid&quot; la prima volta che un visitatore arriva a un sito. Questa variabile viene utilizzata per identificare il visitatore e, mentre il visitatore naviga nel sito, la variabile viene passata. Poiché il robot di ricerca sembra un visitatore del sito, gli viene assegnato un numero &quot;sessionid&quot;. Il robot di ricerca mantiene questo singolo valore &quot;sessionid&quot;, anche se una seconda pagina del sito tenta di assegnare un nuovo valore. A questo scopo, è necessario riscrivere due regole.

La prima regola viene utilizzata per identificare e memorizzare la variabile sessionid:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule utilizza un flag E `([E=sessionid:$1])` per assegnare il valore corrente del parametro CGI sessionid alla variabile `sessionid`. Il riferimento `$1` fa riferimento al primo riferimento di sfondo, contenuto tra il primo set di parentesi nel Pattern di RewriteRule `([^&#]+)`.

L&#39;espressione regolare `^&#]+` corrisponde alla parte di un URL compresa tra la parola `sessionid` e il carattere successivo**&amp;**o**#**. Poiché questa regola di riscrittura viene utilizzata solo per creare il valore iniziale per la variabile sessionid, non viene riscritta. Il campo Sostituzione della regola è impostato in modo `-` da indicare che non è richiesta alcuna riscrittura.

RewriteCond esamina la variabile `sessionid` ( `%{sessionid}`). Se non ha nemmeno un singolo carattere (!.+), quindi la regola RewriteRule corrisponde.

Utilizzando questa regola, l&#39;URL viene letto come `https://www.domain.com/home/?sessionid=1234&function=start` e assegna il valore `1234` alla variabile `sessionid`.

La seconda regola viene utilizzata per riscrivere tutti gli URL che corrispondono al seguente pattern RewriteRule:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

Il pattern RewriteRule contiene due riferimenti a posteriori: `(.+)` e `(.*)`. Il primo riferimento di sfondo corrisponde a tutti i caratteri precedenti `sessionid`. Il secondo backreference corrisponde a tutti i caratteri dopo il termine `&` o `#`.

Il pattern di sostituzione riscrive l’URL utilizzando il primo riferimento di sfondo, seguito dalla stringa &quot;sessionid=&quot;, seguita dal valore della variabile ID di sessione definita dalla prima regola `%{sessionid}`, seguita dal secondo riferimento di sfondo. `($1sessionid=%{sessionid} $2)`

Tenere presente che questa regola di riscrittura non contiene un RewriteCond. Di conseguenza, viene generato un riscrittura per tutti gli URL che corrispondono al *pattern* RewriteRule. Pertanto, se il valore della variabile sessionid ( `%{sessionid}`) è `1234`, un URL del modulo `https://www.domain.com/products/?sessionid=5678&function=buy` viene riscritto come `https://www.domain.com/products/?sessionid=1234&function=buy`

## Riconoscimento {#section_EC3A1DAEB5A54C93A265CB119DF91E9F}

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta di regole URL per recuperare l’elenco di ricerca per indicizzazione {#task_94A28ED7DC404BFF9767DBB5ADEE6B7A}

Potete aggiungere delle regole per recuperare gli URL dall’elenco di ricerca per indicizzazione per specificare in che modo vengono riscritti gli URL riscontrati all’interno del contenuto Web. Recupera regole di riscrittura sono necessarie solo se gli URL contengono dati dinamici, come un ID sessione, e se tali dati dinamici cambiano nel tempo per restare validi.

<!-- 

t_adding_crawl_list_retrieve_url_rules.xml

 -->

**Per aggiungere l’elenco di ricerca per indicizzazione, recuperare le regole URL**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**.
1. Nel [!DNL Crawl List Retrieve URL Rules] campo, immettere le regole desiderate.

   Sono consentite righe vuote e righe di commento che iniziano con il carattere &quot;#&quot; (hash).
1. (Facoltativo) Nella [!DNL Crawl List Retrieve URL Rules] pagina, nel [!DNL Test Crawl List Retrieve URL Rules] campo, immettete un URL di prova di cui desiderate verificare le regole di ricerca per indicizzazione, quindi fate clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL Crawl List Retrieve URL Rules] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sulle regole del titolo della ricerca per indicizzazione {#concept_BD3A576987DA4D93A998B0B9CDDC3C79}

Le regole del titolo della ricerca per indicizzazione specificano il modo in cui i titoli rilevati all&#39;interno del contenuto Web vengono riscritti prima che vengano memorizzati nell&#39;indice di ricerca.

<!-- 

c_about_crawl_title_rules.xml

 -->

Ad esempio, potete utilizzare una regola di riscrittura per rimuovere una parte di un titolo, ad esempio un nome organizzazione. Quando un sito Web viene sottoposto a ricerca per indicizzazione, i titoli rilevati vengono memorizzati in un buffer temporaneo. Tuttavia, prima che un titolo venga aggiunto al buffer, le regole del titolo vengono applicate. Per impostazione predefinita, la ricerca nel sito/merchandising non dispone di regole del titolo per la ricerca per indicizzazione e non apporta alcuna modifica al titolo.

Prima che gli effetti delle regole siano visibili ai clienti, ricreate l&#39;indice del sito.

È possibile ripristinare rapidamente le modifiche apportate alle regole del titolo per indicizzazione utilizzando la funzione Cronologia.

Le regole possono essere composte da due elementi principali: RewriteRule e il parametro opzionale RewriteCond. È possibile specificare un numero illimitato di regole e condizioni. L&#39;ordine di queste regole è importante perché il set di regole viene ripetuto a ciclo continuo per regola. Quando una regola corrisponde, viene ripetuta a ciclo continuo in tutte le condizioni di riscrittura (facoltative) corrispondenti. Le regole URL di ricerca per indicizzazione sono specificate nel modo seguente:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

Quando viene rilevato un titolo, il robot di ricerca tenta di far corrispondere il titolo al Pattern di ciascuna regola di ricerca per indicizzazione. Se il pattern corrisponde, il motore di riscrittura cerca le direttive RewriteCond corrispondenti. Se non sono presenti condizioni, l&#39;URL viene sostituito con un nuovo valore costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se esistono, le condizioni vengono elaborate nell&#39;ordine in cui sono elencate. Il motore di riscrittura tenta di far corrispondere un pattern di condizione (CondPattern) a una stringa di prova (TestString). Se i due valori corrispondono, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l&#39;URL viene sostituito con la Sostituzione specificata nella regola. Se la condizione non è soddisfatta, l&#39;intero insieme di condizioni e la regola corrispondente non riesce.

Immettete le regole per l’URL di ricerca per indicizzazione nella casella di testo, quindi fate clic su Salva modifiche. Sono consentite righe vuote e righe di commento che iniziano con il carattere &quot;#&quot; (hash). Per verificare le regole di ricerca, potete immettere un URL di prova nella casella di testo &quot;Regole di riscrittura test&quot;, quindi fare clic su Test.

## RewriteRule, direttiva {#section_669445C505754E838E14029D6583D9B6}

Ogni direttiva RewriteRule definisce una regola di riscrittura. Le regole vengono applicate nell&#39;ordine in cui sono elencate. Una regola di riscrittura ha la seguente forma:

```
RewriteRule Pattern Substitution [Flags]
```

**Il pattern** può essere un&#39;espressione regolare POSIX applicata al titolo corrente. Il &quot;titolo corrente&quot; è diverso dal titolo originale, perché le regole precedenti lo hanno già associato e modificato.

Consultate Espressioni [](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)regolari.

È possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per applicare il prefisso al pattern. Il carattere &quot;not&quot; consente di negare un pattern, ovvero di essere vero solo se il titolo corrente NON corrisponde al pattern. Il carattere &quot;not&quot; può essere utilizzato quando è meglio corrispondere a un pattern negativo, o come regola predefinita finale. Nota: Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato se la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento di sfondo a cui possono fare riferimento i campi Sostituzione e CondPattern.

**Sostituzione** Il titolo viene sostituito dalla stringa di sostituzione. La stringa può contenere quanto segue:

Testo normale: testo passato attraverso non modificato.

I riferimenti posteriori consentono di accedere alle parti raggruppate (parentesi interne) del Pattern o del Pattern di CondPattern. Di seguito sono riportati due tipi di riferimenti indietro:

* RewriteRule BackReferences

   Questi corrispondono ai riferimenti indietro nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond BackReferences

   Tali riferimenti indietro corrispondono all&#39;ultimo pattern di cond RewriteCond corrispondente e assumono la forma %N (0 &lt;= N &lt;= 9).

Variabili: variabili del formato %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull&#39;impostazione delle variabili di ambiente, vedere `[E]` il flag .

Funzioni Queste sono funzioni del modulo ${NAME_OF_FUNCTION: key} dove NAME_OF_FUNCTION è:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .

>[!NOTE]
>
>Esiste una stringa di sostituzione speciale: &#39;-&#39; significa &quot;NO replace&quot;. La stringa &#39;-&#39; è spesso utile con il flag C (catena), che consente di far corrispondere un titolo a diversi pattern prima che si verifichi una sostituzione.

**Flag** (facoltativo)

I flag sono racchiusi tra parentesi `[]`e più contrassegni sono separati da virgola:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Ultima regola. </p> <p> Interrompe il processo di riscrittura e non applica ulteriori regole di riscrittura. Usate questo flag per impedire ulteriori elaborazioni del titolo corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Il prossimo giro. </p> <p> Esegue di nuovo il processo di riscrittura (a partire dalla prima regola di riscrittura) utilizzando il titolo dell'ultima regola di riscrittura, non il titolo originale. Fai attenzione a non creare un loop senza uscita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Concatenato con la regola successiva. </p> <p>Connette la regola corrente alla regola successiva (che può essere collegata anche alla regola seguente, e così via). Se una regola corrisponde, il processo di sostituzione continua normalmente. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p>Fa sì che il pattern non faccia distinzione tra maiuscole e minuscole (ovvero, non esiste alcuna differenza tra 'A-Z' e 'a-z') quando il pattern viene confrontato con il titolo corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole num successive nel set di regole. Utilizzate questa opzione per creare costrutti pseudo if-then-else. L'ultima regola della clausola then diventa un skip=N dove N è il numero di regole nella clausola else. (Nota: Questo non è lo stesso del flag 'chain|C'!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Impostate la variabile di ambiente. </p> <p> Crea una variabile ambientale "VAR" impostata sul valore VAL, in cui VAL può contenere riferimenti a posteriori di espressioni regolari, $N e %N, che è espanso. È possibile utilizzare questo flag più volte per impostare più variabili. È possibile fare riferimento alle variabili in un secondo momento in un pattern RewriteCond seguente tramite %{VAR}. Usate questo flag per rimuovere e ricordare le informazioni dai titoli. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Direttiva RewriteCond (facoltativo) {#section_D664B71DE3884E0790531804C49A3222}

La direttiva RewriteCond definisce una condizione di regola. Quando un oggetto RewriteCond precede un oggetto RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e si applicano le condizioni aggiuntive.

Le direttive sulle condizioni di riscrittura hanno la seguente forma:

```
RewriteCond TestString CondPattern [Flags] 
```

**TestString** è una stringa che può contenere i seguenti costrutti:

Testo normale: testo passato attraverso non modificato.

I riferimenti posteriori consentono di accedere alle parti raggruppate (parentesi interne) del Pattern o del Pattern di CondPattern. Esistono due tipi di riferimenti indietro:

* RewriteRule BackReferences Questi corrispondono ai riferimenti posteriori nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RiscriviCondRiferimentiCorrispondenti ai riferimenti posteriori nell&#39;ultimo pattern di condCondRewriteCond corrispondente e assumere il formato %N (0 &lt;= N &lt;= 9).

Variabili: variabili del formato %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili di ambiente, vedere `[E]` il flag .

Funzioni Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} dove NAME_OF_FUNCTION è:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .
* l’URL escape codifica tutti i caratteri nella chiave.
* I caratteri &#39;a&#39;...z&#39;, &#39;A&#39;...Z&#39;, &#39;0&#39;...9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel relativo equivalente con codifica URL %xx.
* unescape riconforma &#39;+&#39; nello spazio e tutti i caratteri con codifica URL %xx in caratteri singoli.

**CondPattern** è un’espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un &#39;!&#39; carattere (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, è possibile utilizzare una delle seguenti varianti speciali.

>[!NOTE]
>
>È possibile assegnare un prefisso a tutti questi test con un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente minore. </p> <p>Considera il <i>CondPattern</i> come una stringa semplice e lo confronta in modo lessicale con <i>TestString</i>. True se <i>TestString</i> è lessicamente minore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicalmente maggiore. </p> <p>Considera il <i>CondPattern</i> come una stringa semplice e lo confronta in modo lessicale con <i>TestString</i>. True se <i>TestString</i> è lessicamente maggiore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p> È lessicalmente uguale. </p> <p>Considera il <i>CondPattern</i> come una stringa semplice e lo confronta in modo lessicale con <i>TestString</i>. True se <i>TestString</i> è lessicamente uguale a <i>CondPattern</i>, ovvero, le due stringhe sono esattamente uguali (carattere per carattere). Se <i>CondPattern</i> è solo "" (due virgolette), questo confronta <i>TestString</i> con la stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag** (facoltativo)

I flag sono racchiusi tra parentesi `[]`e più contrassegni sono separati da virgola:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p> Rende il test non sensibile. In altre parole, non c'è differenza tra 'A-Z' e 'a-z' sia nella <i>TestString</i> espansa che nel <i>CondPattern.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p> O la condizione successiva. </p> <p>Utilizzate questo flag per combinare le condizioni della regola con un operatore OR locale invece dell'operatore AND implicito. Senza questa bandiera, si dovrebbe scrivere più volte la regola/cond. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

Si supponga di disporre di un sito Web aziendale con un formato titolo standard: &quot;La mia azienda&quot; seguita da un trattino e quindi da una descrizione specifica della pagina ( ad esempio &quot;La mia azienda - Benvenuto&quot; o &quot;La mia azienda - Notizie&quot;). Si desidera rimuovere &quot;La mia azienda -&quot; dal titolo e convertire l&#39;intero titolo in lettere maiuscole quando indicizza il sito.

La seguente regola di riscrittura utilizza il contagocce della funzione per riscrivere solo la parte descrittiva di un titolo in maiuscolo:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>}
```

Il pattern della regola `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` contiene un riferimento di sfondo `(.*)` che corrisponde al contenuto del titolo che segue &quot;Società&quot;. Ricordare che intorno a una parte di un pattern con parentesi ( ) viene creato un riferimento di sfondo a cui può fare riferimento la Sostituzione. In questo esempio, la sostituzione (${toupper:**$1**}) riscrive tale riferimento (**$1**) utilizzando la funzione del contagocce.

Pertanto, un titolo del modulo &quot;La mia azienda - Benvenuto&quot; viene riscritto come &quot;BENVENUTO&quot;.

**Riconoscimento**

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta di regole per il titolo per indicizzazione {#task_272BB4C603BA4C9ABDBEEB398798B101}

Potete aggiungere regole per il titolo della ricerca per indicizzazione per specificare come i titoli rilevati all’interno del contenuto Web vengono riscritti prima che vengano memorizzati nell’indice di ricerca.

<!-- 

t_adding_crawl_title_rules.xml

 -->

**Per aggiungere regole del titolo per indicizzazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl Title Rules]**.
1. Nel [!DNL Crawl Title Rules] campo, immettere le regole desiderate.

   Sono consentite righe vuote e righe di commento che iniziano con il carattere &quot;#&quot; (hash).
1. (Facoltativo) Nella [!DNL Crawl Title Rules] pagina, nel [!DNL Test Crawl Title Rules] campo, immettete un URL di test di cui desiderate verificare le regole di ricerca, quindi fate clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL Crawl Title Rules] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sulle regole di ricerca URL {#concept_017EC95E68844B6C8CC9F874F0EC8D3C}

Regole URL di ricerca specifica in che modo devono essere visualizzati gli URL nei risultati di ricerca del sito Web. Le regole funzionano sugli URL completi. È possibile manipolare qualsiasi parte dell’URL, compresi gli argomenti di query in cui vengono spesso mantenute le informazioni ID sessione.

<!-- 

c_about_search_url_rules.xml

 -->

In genere, le regole dell&#39;URL di ricerca vengono utilizzate per inserire un ID sessione in un URL. Tuttavia, potete anche utilizzare le regole dell&#39;URL di ricerca per modificare il nome di dominio visualizzato con i risultati. Per impostazione predefinita, non vengono specificate regole e non viene eseguita alcuna modifica URL.

Le regole URL di ricerca possono essere composte da due elementi principali: RewriteRule e il parametro opzionale RewriteCond. Quando un URL viene incluso come parte di un risultato di ricerca, le regole vengono utilizzate per manipolarlo. Potete specificare un numero illimitato di regole e condizioni per l’URL di ricerca. L&#39;ordine di queste regole è importante perché il set di regole viene ripetuto a ciclo continuo, regola per regola. Quando una regola corrisponde, il software esegue un ciclo continuo tra eventuali condizioni di riscrittura (facoltative) corrispondenti. Le regole URL di ricerca per indicizzazione sono specificate nel modo seguente:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

Durante l&#39;elaborazione di un URL, la ricerca nel sito/merchandising tenta di trovare una corrispondenza con il pattern di ciascuna regola di ricerca. Se la corrispondenza non riesce, il motore di riscrittura interrompe immediatamente l&#39;elaborazione della regola e continua con la regola successiva nell&#39;insieme. Se il pattern corrisponde, il motore di riscrittura cerca le istruzioni RewriteCond corrispondenti. Se non esistono condizioni, l’URL viene sostituito con un nuovo valore. Questo valore è costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se le condizioni esistono, l&#39;ordine in cui sono elencate è il modo in cui vengono elaborate. Il motore di riscrittura tenta di far corrispondere un pattern di condizione (CondPattern) a una stringa di prova (TestString). Se i due valori corrispondono, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l&#39;URL viene sostituito con la Sostituzione specificata nella regola. Se la condizione non è soddisfatta, l&#39;intero insieme di condizioni e la regola corrispondente non riesce.

## Informazioni sulla direttiva RewriteRule {#section_A3473B5B90B74DA1970213113A90591E}

Una regola di riscrittura ha la seguente forma:

```
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

**Il pattern** può essere un&#39;espressione regolare POSIX, che viene applicata all&#39;URL corrente. L&#39;&quot;URL corrente&quot; potrebbe essere diverso dall&#39;URL originale, perché le regole precedenti potrebbero già corrispondere e modificarlo.

Consultate Espressioni [](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)regolari.

È possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per applicare il prefisso al pattern. Il carattere &quot;not&quot; consente di negare un pattern. In altre parole, è vero solo se l&#39;URL corrente NON corrisponde al pattern. È possibile utilizzare il carattere &quot;not&quot; quando è meglio corrispondere a un pattern negativo, o come regola predefinita finale. Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato se la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento di sfondo a cui possono fare riferimento i campi Sostituzione e CondPattern.

**Sostituzione** L’URL viene completamente sostituito dalla stringa di sostituzione, che può contenere quanto segue:

Testo normale - Testo trasmesso inalterato.

Riferimenti posteriori Consente di accedere alle parti raggruppate (parentesi interne) del Pattern o del CondPattern. Esistono due tipi di riferimenti indietro:

RewriteRule BackReferences Questi corrispondono ai riferimenti posteriori nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

RewriteCond BackReferences: questi corrispondono a riferimenti indietro nell&#39;ultimo pattern di cond RewriteCond corrispondente e assumono la forma %N (0 &lt;= N &lt;= 9).

Funzioni: Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .
* escape URL codifica tutti i caratteri nella *chiave*.
* I caratteri &#39;a&#39;...z&#39;, &#39;A&#39;...Z&#39;, &#39;0&#39;...9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati; gli spazi sono convertiti in &#39;+&#39;; tutti gli altri caratteri vengono trasformati nel relativo equivalente con codifica URL %xx.
* unescape riconforma &#39;+&#39; nello spazio e tutti i caratteri con codifica URL %xx in caratteri singoli.

>[!NOTE]
>
>Esiste una stringa di sostituzione speciale: &#39;-&#39; significa &quot;NO replace&quot;. La stringa &#39;-&#39; è spesso utile insieme al flag C (chain). Consente di associare un URL a diversi pattern prima che venga effettuata una sostituzione.

**Flag** (facoltativo)

I flag sono racchiusi tra parentesi `[]`e più contrassegni sono separati da virgola:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Ultima regola. </p> <p> Arrestate il processo di riscrittura e non applicate alcuna regola di riscrittura aggiuntiva. Usate questo flag per impedire ulteriori elaborazioni dell’URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p> Il prossimo giro. </p> <p>Eseguite nuovamente il processo di riscrittura (iniziando nuovamente con la prima regola di riscrittura) utilizzando l'URL dell'ultima regola di riscrittura (non l'URL originale). Fai attenzione a non creare un loop senza uscita! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p> Concatenato con la regola successiva. </p> <p>Questo flag consente di allineare la regola corrente alla regola successiva, che può anche essere collegata alla regola seguente, e così via. Se una regola corrisponde, il processo di sostituzione continua normalmente. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p>Questo flag rende il pattern senza distinzione tra maiuscole e minuscole. In altre parole, non c'è differenza tra 'A-Z' e 'a-z' quando il pattern viene confrontato con l'URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole num successive nel set di regole. Utilizzate questa opzione per creare costrutti pseudo if-then-else. L'ultima regola della clausola then diventa un skip=N dove N è il numero di regole nella clausola else. (Nota: Questo non è lo stesso del flag 'chain|C'!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Impostate la variabile ambientale. </p> <p> Questo flag crea una variabile ambientale "VAR" impostata sul valore VAL. VAL può contenere riferimenti a posteriori di espressioni regolari, $N e %N, espansi. È possibile utilizzare questo flag più volte per impostare più variabili. Le variabili possono essere successivamente eliminate dal riferimento in un pattern RewriteCond seguente tramite %{VAR}. Usate questo flag per rimuovere e ricordare le informazioni dagli URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

Le regole di riscrittura store e le regole di riscrittura Recupera condividono i valori delle variabili. Per questo motivo, potete impostare una variabile su un valore sessionid sensibile all&#39;ora quando un URL incorporato viene rilevato e memorizzato. Quando l’URL successivo viene recuperato dall’elenco di memorizzazione temporanea, prima di recuperare la pagina è possibile aggiungere ad esso il valore dell’ID sessione più recente.

**Esempio**

Supponete di disporre di un server sensibile alle maiuscole/minuscole. Gestisce le stringhe &quot;www.mydomain.com&quot; e &quot;www.MyDomain.com&quot; in modo diverso. Affinché il server funzioni correttamente, è necessario assicurarsi che il dominio sia sempre &quot;www.mydomain.com&quot; anche se alcuni documenti contengono collegamenti che fanno riferimento a &quot;www.MyDomain.com&quot;. A tal fine, potete utilizzare la seguente regola:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2 
```

Questa regola di riscrittura utilizza la funzione &quot;tower&quot; per riscrivere la porzione di dominio di un URL in modo da garantire che sia sempre minuscola:

1. Il pattern `(^https://([^/]*)(.*)$)` contiene un riferimento di sfondo **`([^/]*)`** che corrisponde a tutti i caratteri compresi tra &quot;https://&quot; e il primo &quot;/&quot; nell&#39;URL. Il pattern contiene anche un secondo riferimento di sfondo **(.*)** che corrisponde a tutti i caratteri rimanenti nell&#39;URL.

1. La sostituzione `(https://${tolower:$1}$2)` indica al motore di ricerca di riscrivere l’URL utilizzando la funzione **topower** sul primo riferimento di sfondo, `(https://**${tolower:$1**}$2)` lasciando invariato il resto dell’URL `(https://${tolower:$1}*$2*)`.

Pertanto, un URL del modulo `https://www.MyDomain.com/INTRO/index.Html` viene riscritto come `https://www.mydomain.com/INTRO/index.Html`

**Direttiva** RewriteCond (facoltativo)

La direttiva RewriteCond definisce una condizione di regola. Quando un oggetto RewriteCond precede un oggetto RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e si applicano le condizioni aggiuntive.

Le direttive sulle condizioni di riscrittura hanno la seguente forma:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i>
```

*TestString* è una stringa che può contenere i seguenti costrutti:

Testo normale: Testo passato inalterato.

I riferimenti posteriori consentono di accedere alle parti raggruppate (parentesi interne) del Pattern o del Pattern di CondPattern. Esistono due tipi di riferimenti indietro:

* ** RewriteRule BackReferences** Questi corrispondono ai riferimenti posteriori nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond BackReferences** Questi corrispondono a riferimenti indietro nell&#39;ultimo pattern di cond RewriteCond corrispondente e si presentano come %N (0 &lt;= N &lt;= 9).

Variabili: variabili del formato %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull&#39;impostazione delle variabili, vedere il flag Riscrittura *`[E]`* regola.

>[!NOTE]
>
>Le regole di riscrittura generalmente utilizzano le variabili. Tutti i parametri CGI dell’URL corrente vengono automaticamente trasformati in variabili. Ad esempio, l&#39;URL di ricerca `"https://search.atomz.com/search/?sp_a=sp00000000&sp_q="Product"&session=1234&id=5678"` fornirà automaticamente quattro variabili, alle quali è possibile fare riferimento nelle regole di riscrittura. In questo esempio, una variabile è denominata &quot;session&quot; e il suo valore è &quot;1234&quot;, mentre un&#39;altra è denominata &quot;id&quot; e il suo valore è &quot;5678&quot;. (Le altre due variabili sono `sp_a` e `sp_q`.) È necessario trasmettere tutte le variabili necessarie come campi nascosti dal modulo di ricerca sulla pagina Web. In questo esempio, è necessario trasmettere i valori &quot;session&quot; e &quot;id&quot;, che identificano l&#39;utente del sito Web che esegue la ricerca. Per passare un campo nascosto al modulo di ricerca, utilizzare un tag come `<input type=hidden name="session" value="1234">`.

Funzioni Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} dove NAME_OF_FUNCTION è:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .
* escape URL codifica tutti i caratteri nella *chiave*. I caratteri &#39;a&#39;...z&#39;, &#39;A&#39;...Z&#39;, &#39;0&#39;...9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel relativo equivalente con codifica URL %xx.
* unescape riconforma &#39;+&#39; nello spazio e tutti i caratteri di codifica URL %xx in caratteri singoli.

**CondPattern** è un’espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un &#39;!&#39; carattere (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, è possibile utilizzare una delle seguenti varianti speciali.

È possibile assegnare un prefisso a tutti questi test utilizzando un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente minore. </p> <p> Considera il <i>CondPattern</i> come una stringa semplice e lo confronta in modo lessicale con <i>TestString</i>. True se <i>TestString</i> è lessicamente minore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicalmente maggiore. </p> <p> Considera il <i>CondPattern</i> come una stringa semplice e lo confronta in modo lessicale con <i>TestString</i>. True se <i>TestString</i> è lessicamente maggiore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicalmente uguale. </p> <p> Considera il <i>CondPattern</i> come una stringa semplice e lo confronta in modo lessicale con <i>TestString</i>. True se <i>TestString</i> è lessicalmente uguale a <i>CondPattern</i>. ovvero, le due stringhe sono esattamente uguali (carattere per carattere). Se <i>CondPattern</i> è solo "" (due virgolette), questo confronta <i>TestString</i> con la stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag** (facoltativo)

I flag sono racchiusi tra parentesi `[]`e più contrassegni sono separati da virgola:

&#39;nocase|NC&#39; (nessun caso): In questo modo il test non fa distinzione tra maiuscole e minuscole. In altre parole, non c&#39;è differenza tra &#39;A-Z&#39; e &#39;a-z&#39; sia nella *TestString* espansa che nel *CondPattern*.

&#39;ornext|OR&#39; (o condizione successiva): Utilizzate questa opzione per combinare le condizioni della regola con un operatore OR locale invece dell&#39;operatore AND implicito. Senza questo flag si dovrebbe scrivere più volte la regola/cond.

**Esempio**

Alcune pagine Web assegnano una variabile CGI &quot;sessionid&quot; la prima volta che un cliente arriva a un sito. Questa variabile viene utilizzata per identificare il cliente e, mentre il cliente naviga nel sito, la variabile viene passata. Poiché il robot di ricerca sembra un cliente per il sito, gli viene assegnato un numero &quot;sessionid&quot;. Il robot di ricerca mantiene questo singolo valore &quot;sessionid&quot;, anche se una seconda pagina del sito tenta di assegnare un nuovo valore. A questo scopo, è necessario riscrivere la regola seguente:

```
RewriteCond  %{sessionid}  .+ 
RewriteRule  ^ 
<b>(.+)</b>sessionid=[^&#]+ 
<i>(.*)</i>$   
<b>$1</b>sessionid=%{sessionid} 
<i>$2</i>
```

Il pattern RewriteRule contiene due riferimenti a posteriori: (.+) e (.*). Il primo backreference corrisponde a tutti i caratteri prima di &quot;sessionid=&quot;. Il secondo backreference corrisponde a tutti i caratteri dopo il termine &#39;&amp;&#39; o &#39;#&#39; dell&#39;sessionid.

Il pattern Sostituzione riscrive l’URL utilizzando il primo riferimento di sfondo, seguito dalla stringa &quot;sessionid=&quot;, seguita dal valore della variabile ID sessione, che è stata passata come parametro CGI nell’URL, seguito dal secondo riferimento di sfondo. `($1sessionid=%{sessionid}$2)`.

La variabile **RewriteCond** esamina la variabile sessionid `(%{sessionid})`. Se contiene almeno un carattere (.+), quindi la regola RewriteRule corrisponde.

Pertanto, se la query di ricerca è `"https://search.atomz.com/search/?sp_a=sp99999999&sp_q=word&sessionid=5678"`, tutti gli URL dei risultati della ricerca verranno riscritti in modo che il valore &quot;sessionid&quot; sia &quot;5678&quot; invece del valore &quot;sessionid&quot; che il robot di ricerca ha rilevato quando ha fatto scorrere il sito e salvato i collegamenti.

**Riconoscimento**

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta di regole URL di ricerca {#task_50C77D1B53804AEEB20896F74265BD6F}

Potete aggiungere regole per l’URL di ricerca per specificare come vengono visualizzati gli URL nei risultati di ricerca nel sito Web. Le regole funzionano sugli URL completi. Potete manipolare qualsiasi parte dell’URL, inclusi gli argomenti di query in cui vengono spesso mantenute le informazioni ID sessione.

<!-- 

t_adding_search_url_rules.xml

 -->

**Aggiunta di regole per l&#39;URL di ricerca**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search URL Rules]**.
1. Nel [!DNL Search URL Rules] campo, immettere le regole desiderate.

   Sono consentite righe vuote e righe di commento che iniziano con il carattere &quot;#&quot; (hash).
1. (Facoltativo) Nella [!DNL Search URL Rules] pagina, nel [!DNL Test Search URL Rules] campo, immettete un URL di prova di cui desiderate verificare le regole di ricerca per indicizzazione, quindi fate clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL Search URL Rules] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sulle regole del titolo di ricerca {#concept_C72D20F8DFF64EDE809AF4B72797E858}

Regole del titolo di ricerca specifica in che modo vengono visualizzati i titoli nei risultati della ricerca nel sito Web. È possibile modificare qualsiasi parte del titolo.

<!-- 

c_about_search_title_rules.xml

 -->

Una regola di riscrittura può essere utilizzata per rimuovere una parte di un titolo, ad esempio un nome organizzazione. Per impostazione predefinita, la ricerca nel sito/merchandising non dispone di regole per il titolo e non apporta alcuna modifica al titolo.

Le regole del titolo possono essere composte da due elementi principali: RewriteRule e RewriteCond facoltativi. È possibile specificare un numero illimitato di regole e condizioni. L&#39;ordine di queste regole è importante, perché il set di regole viene ripetuto a ciclo continuo per regola. Quando una regola corrisponde, il software esegue un ciclo continuo tra eventuali condizioni di riscrittura (facoltative) corrispondenti. Le regole del titolo di ricerca sono specificate nel modo seguente:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

Quando viene rilevato un titolo, la ricerca del sito/merchandising tenta di trovare una corrispondenza con il pattern di ciascuna regola di ricerca per indicizzazione. Se il pattern corrisponde, il motore di riscrittura cerca le direttive RewriteCond corrispondenti. Se non sono presenti condizioni, il titolo viene sostituito con un nuovo valore costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se esistono, le condizioni vengono elaborate nell&#39;ordine in cui sono elencate. Il motore di riscrittura tenta di far corrispondere un pattern di condizione (CondPattern) a una stringa di prova (TestString). Se i due valori corrispondono, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l&#39;URL viene sostituito con la Sostituzione specificata nella regola. Se la condizione non è soddisfatta, l&#39;intero insieme di condizioni e la regola corrispondente non riesce.

## Direttiva RewriteRule {#section_3BF2B0FF89F74A26AE79D68FA3184B9B}

Ogni direttiva RewriteRule definisce una regola di riscrittura. Le regole vengono applicate nell&#39;ordine in cui sono elencate. Una regola di riscrittura ha la seguente forma:

```
RewriteRule Pattern Substitution [Flags]
```

**Pattern** Un&#39;espressione regolare POSIX, che viene applicata al titolo corrente. Il &quot;titolo corrente&quot; può essere diverso dal titolo originale, perché le regole precedenti potrebbero già corrispondere e modificarlo.

Consultate Espressioni [](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)regolari.

È possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per applicare il prefisso al pattern. Il carattere &quot;not&quot; consente di negare un pattern. Questo è vero solo se il titolo corrente NON corrisponde al pattern. Il carattere &quot;not&quot; può essere utilizzato quando è meglio corrispondere a un pattern negativo, o come regola predefinita finale. Nota: Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato se la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento di sfondo a cui possono fare riferimento i campi Sostituzione e CondPattern.

**Sostituzione** Il titolo è completamente sostituito dalla stringa di sostituzione, che può contenere quanto segue:

Testo normale: testo passato attraverso non modificato.

**Riferimenti** posteriori Consente di accedere alle parti raggruppate (parentesi interne) del Pattern o del Pattern di CondPattern. Di seguito sono riportati due tipi di riferimenti indietro:

* **RiscriviRiferimenti** RewriteRule Questi corrispondono a riferimenti posteriori nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* ** RewriteCond BackReferences** Questi corrispondono a riferimenti posteriori nell&#39;ultimo pattern di cond RewriteCond corrispondente e assumono la forma %N (0 &lt;= N &lt;= 9).

**Variabili** : variabili del formato %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull&#39;impostazione delle variabili di ambiente, vedere il flag [E] . Le variabili possono essere definite anche nel modulo di ricerca che ha generato i risultati della ricerca.

**Funzioni** Queste sono funzioni del modulo ${NAME_OF_FUNCTION: key} dove NAME_OF_FUNCTION è:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .

Esiste una stringa di sostituzione speciale: &#39;-&#39; significa &quot;NO replace&quot;. La stringa &#39;-&#39; è spesso utile insieme al flag C (catena), per consentire la corrispondenza di un titolo con diversi pattern prima di una sostituzione.

**Flag** (facoltativo)

I flag sono racchiusi tra parentesi `[]`e più flag sono separati da virgola:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p> Ultima regola. </p> <p> Arrestate il processo di riscrittura e non applicate alcuna regola di riscrittura aggiuntiva. Usate questo flag per impedire ulteriori elaborazioni del titolo corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Il prossimo giro. </p> <p> Eseguire nuovamente il processo di riscrittura (iniziando nuovamente con la prima regola di riscrittura) utilizzando il titolo dell'ultima regola di riscrittura (non il titolo originale!). Fai attenzione a non creare un loop senza uscita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Concatenato con la regola successiva. </p> <p> Questo flag catena la regola corrente alla regola successiva (che può anche essere collegata alla regola seguente, e così via). Se una regola corrisponde, il processo di sostituzione continua normalmente. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Nessun caso. </p> <p> Questo flag rende il pattern senza distinzione tra maiuscole e minuscole. In altre parole, non c'è differenza tra 'A-Z' e 'a-z' quando il pattern viene confrontato con il titolo corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p> Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole num successive nel set di regole. Utilizzate questa opzione per creare costrutti pseudo if-then-else. L'ultima regola della clausola then diventa un skip=N dove N è il numero di regole nella clausola else. (non equivale al flag 'chain|C'!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Impostate la variabile di ambiente. </p> <p> Questo flag crea una variabile ambientale "VAR" impostata sul valore VAL, in cui VAL può contenere riferimenti a posteriori di espressioni regolari, $N e %N, che verrà espansa. È possibile utilizzare questo flag più volte per impostare più variabili. È possibile fare riferimento alle variabili in un secondo momento in un pattern RewriteCond seguente tramite %{VAR}. Usate questo flag per rimuovere e ricordare le informazioni dai titoli. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Direttiva RewriteCond (facoltativo) {#section_9D72B2AB454849A7B681BC39C506AAA3}

La direttiva RewriteCond definisce una condizione di regola. Quando un oggetto RewriteCond precede un oggetto RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e si applicano le condizioni aggiuntive.

Le direttive sulle condizioni di riscrittura hanno la seguente forma:

```
RewriteCond TestString CondPattern [Flags]
```

**TestString** è una stringa che può contenere i seguenti costrutti:

Testo normale: testo passato attraverso non modificato.

I riferimenti posteriori consentono di accedere alle parti raggruppate (parentesi interne) del Pattern o del Pattern di CondPattern. Esistono due tipi di riferimenti indietro:

* **RiscriviRiferimenti** RewriteRule Questi corrispondono a riferimenti posteriori nel pattern RewriteRule corrispondente e assumono la forma $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond BackReferences** Questi corrispondono a riferimenti indietro nell&#39;ultimo pattern di cond RewriteCond corrispondente e si presentano come %N (0 &lt;= N &lt;= 9).

**Variabili** : variabili del formato %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull&#39;impostazione delle variabili di ambiente, vedere `[E]` il flag . Le variabili possono essere definite anche nel modulo di ricerca che ha generato i risultati della ricerca.

**Funzioni** Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è:

* tolwer rende tutti i caratteri in caratteri *minuscoli* .
* il contagocce rende tutti i caratteri maiuscoli *con la chiave* .
* escape URL codifica tutti i caratteri nella *chiave*.
* I caratteri &#39;a&#39;...z&#39;, &#39;A&#39;...Z&#39;, &#39;0&#39;...9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel relativo equivalente con codifica URL %xx.
* unescape riconforma &#39;+&#39; nello spazio e tutti i caratteri con codifica URL %xx in caratteri singoli.

Esiste una stringa di sostituzione speciale: &#39;-&#39; significa &quot;NO replace&quot;. La stringa &#39;-&#39; è spesso utile insieme al flag C (catena), per consentire la corrispondenza di un URL con diversi pattern prima che si verifichi una sostituzione.

**CondPattern** Un&#39;espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un &#39;!&#39; carattere (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, è possibile utilizzare una delle seguenti varianti speciali.

Tutti questi test possono anche essere preceduti da un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente minore. </p> <p> Considera il <i>CondPattern</i> come una stringa semplice e lo confronta in modo lessicale con <i>TestString</i>. True se <i>TestString</i> è lessicamente minore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p> È lessicalmente maggiore. </p> <p> Considera il <i>CondPattern</i> come una stringa semplice e lo confronta in modo lessicale con <i>TestString</i>. True se <i>TestString</i> è lessicamente maggiore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicalmente uguale. </p> <p> Considera il <i>CondPattern</i> come una stringa semplice e lo confronta in modo lessicale con <i>TestString</i>. True se <i>TestString</i> è lessicalmente uguale a <i>CondPattern</i>. ovvero, le due stringhe sono esattamente uguali (carattere per carattere). Se <i>CondPattern</i> è solo "" (due virgolette), questo confronta <i>TestString</i> con la stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag** (facoltativo)

I flag sono racchiusi tra parentesi`[]`e più contrassegni sono separati da virgola:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' (nessun caso) </p> </td> 
   <td colname="col2"> <p>Rende il test non sensibile. In altre parole, non c'è differenza tra 'A-Z' e 'a-z' sia nella <i>TestString</i> espansa che nel <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' (o condizione successiva) </p> </td> 
   <td colname="col2"> <p> Utilizzate questa opzione per combinare le condizioni della regola con un operatore OR locale invece dell'operatore AND implicito. Senza questo flag si dovrebbe scrivere più volte la regola/cond. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempio {#section_E7454FFE169E459AABD9D033651939CB}

Si supponga di disporre di un sito Web aziendale con un formato titolo standard: &quot;La mia azienda&quot; seguita da un trattino e quindi da una descrizione specifica della pagina ( ad esempio &quot;La mia azienda - Benvenuto&quot; o &quot;La mia azienda - Notizie&quot;). Si desidera togliere &quot;La mia azienda -&quot; dal titolo e convertire l&#39;intero titolo in lettere maiuscole quando indicizza il sito.

La seguente regola di riscrittura utilizza il contagocce della funzione per riscrivere solo la parte descrittiva di un titolo in maiuscolo:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>} 
```

Il pattern della regola `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` contiene un riferimento di sfondo **`(.*)`** che corrisponde al contenuto del titolo che segue &quot;Società&quot;. Ricordare che intorno a una parte di un pattern con parentesi ( ) viene creato un riferimento di sfondo a cui può fare riferimento la Sostituzione. In questo esempio, la sostituzione (${toupper:**$1**}) riscrive tale riferimento (**$1**) utilizzando la funzione del contagocce.

Pertanto, un titolo del modulo &quot;La mia azienda - Benvenuto&quot; viene riscritto come &quot;BENVENUTO&quot;.

**Riconoscimento**

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta delle regole del titolo di ricerca {#task_155CECB74BE3444384EDBBD04F41515E}

Potete aggiungere delle regole per il titolo di ricerca per specificare come vengono visualizzati i titoli nei risultati della ricerca nel sito Web. Potete manipolare qualsiasi parte del titolo.

<!-- 

t_adding_search_title_rules.xml

 -->

**Per aggiungere le regole del titolo di ricerca**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search Title Rules]**.
1. Nel [!DNL Search Title Rules] campo, immettere le regole desiderate.

   Sono consentite righe vuote e righe di commento che iniziano con il carattere &quot;#&quot; (hash).
1. (Facoltativo) Nella [!DNL Search Title Rules] pagina, nel [!DNL Test Search Title Rules] campo, immettete un titolo di test, quindi fate clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL Search Title Rules] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

