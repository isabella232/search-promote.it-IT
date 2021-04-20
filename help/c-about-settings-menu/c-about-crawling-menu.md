---
description: Utilizza il set di date e URL del menu di ricerca per indicizzazione, le maschere, le password, i tipi di contenuto, le connessioni, le definizioni dei moduli e i punti di ingresso URL.
solution: Target
subtopic: Crawling
title: Informazioni sul menu di ricerca per indicizzazione
topic: Settings,Site search and merchandising
uuid: a58c03bf-90f7-4b5b-91ff-988b95c246b0
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '11016'
ht-degree: 0%

---


# Informazioni sul menu di ricerca per indicizzazione{#about-the-crawling-menu}

Utilizza il set di date e URL del menu di ricerca per indicizzazione, le maschere, le password, i tipi di contenuto, le connessioni, le definizioni dei moduli e i punti di ingresso URL.

## Informazioni sui punti di ingresso URL {#concept_5D857E3B5C124E85BC0B5AE77A509573}

La maggior parte dei siti web dispone di un punto di ingresso principale o di una home page che un cliente visita inizialmente. Questo punto di ingresso principale è l&#39;indirizzo URL da cui il robot di ricerca inizia la ricerca per indicizzazione. Tuttavia, se il sito web dispone di più domini o sottodomini o se parti del sito non sono collegate dal punto di ingresso principale, puoi utilizzare i punti di ingresso URL per aggiungere altri punti di ingresso.

Vengono indicizzate tutte le pagine del sito web al di sotto di ciascun punto di ingresso URL specificato. È possibile combinare punti di ingresso URL con maschere per controllare esattamente quali parti di un sito web si desidera indicizzare. È necessario ricreare l’indice del sito web prima che gli effetti delle impostazioni dei punti di ingresso URL siano visibili ai clienti.

Il punto di ingresso principale è in genere l’URL del sito web che si desidera indicizzare e cercare. Puoi configurare questo punto di ingresso principale in Impostazioni account.

Consulta [Configurazione delle impostazioni account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Dopo aver specificato il punto di ingresso dell’URL principale, è possibile specificare facoltativamente altri punti di ingresso che si desidera sottoporre a ricerca per indicizzazione in ordine. Nella maggior parte dei casi si specificano punti di ingresso aggiuntivi per le pagine web non collegate da pagine sotto il punto di ingresso principale. Specifica punti di ingresso aggiuntivi quando il sito web si estende su più domini, come nell’esempio seguente:

`https://www.domain.com/`

`https://www.domain.com/not_linked/but_search_me_too/`

`https://more.domain.com/`

È possibile qualificare ogni punto di ingresso con una o più delle seguenti parole chiave separate da spazio nella tabella seguente. Queste parole chiave influiscono sulla modalità di indicizzazione della pagina.

**Importante**: Assicurarsi di separare una determinata parola chiave dal punto di ingresso e l&#39;uno dall&#39;altro tramite uno spazio; una virgola non è un separatore valido.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Parola chiave </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> Se non si desidera indicizzare il testo nella pagina del punto di ingresso, ma si desidera seguire i collegamenti della pagina, aggiungere 
     <code>
       noindex 
     </code> dopo il punto di ingresso. </p> <p>Separa la parola chiave dal punto di ingresso con uno spazio come nell'esempio seguente: </p> <p> <code> https://www.my-additional-domain.com/more_pages/main.html&amp;nbsp;noindex </code> </p> <p>Questa parola chiave equivale a un tag meta di robot con 
     <code>
       content="noindex" 
     </code>) tra 
     <code>
       &lt;head&gt; 
     </code>... 
     Tag <code>
       &lt;/head&gt; 
     </code> della pagina del punto di ingresso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Se si desidera indicizzare il testo nella pagina del punto di ingresso ma non si desidera seguire i collegamenti della pagina, aggiungere 
     <code>
       nofollow 
     </code> dopo il punto di ingresso. </p> <p>Separa la parola chiave dal punto di ingresso con uno spazio come nell'esempio seguente: </p> <p> <code> https://www.domain.com/not_linked/directory_listing&amp;nbsp;nofollow </code> </p> <p>Questa parola chiave equivale a un tag meta di robot con 
     <code>
       content="nofollow" 
     </code> tra 
     <code>
       &lt;head&gt; 
     </code>... 
     Tag <code>
       &lt;/head&gt; 
     </code> di una pagina del punto di ingresso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>modulo </p> </td> 
   <td colname="col2"> <p> Quando il punto di ingresso è una pagina di accesso, 
     <code>
       form 
     </code> viene generalmente utilizzato in modo che il robot di ricerca possa inviare il modulo di login e ricevere i cookie appropriati prima di eseguire la ricerca per indicizzazione del sito web. Quando si utilizza la parola chiave "form", la pagina del punto di ingresso non viene indicizzata e il robot di ricerca non contrassegna la pagina del punto di ingresso come sottoposta a ricerca per indicizzazione. Utilizzo 
     <code>
       nofollow 
     </code> se non desideri che il robot di ricerca segua i collegamenti della pagina. </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulta anche [Informazioni sui tipi di contenuto](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

Vedere anche [Informazioni sul connettore indice](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84).

## Aggiunta di più punti di ingresso URL da indicizzare {#task_2338A47387D74CFDAC4D4EF4A367ED45}

Se il sito web dispone di più domini o sottodomini e desideri che vengano sottoposti a ricerca per indicizzazione, puoi utilizzare i punti di ingresso URL per aggiungere altri URL.

Per impostare il punto di ingresso URL principale del sito web, utilizza Impostazioni account.

Consulta [Configurazione delle impostazioni account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

**Per aggiungere più punti di ingresso URL da indicizzare**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**.
1. Nella pagina [!DNL URL Entrypoints] , immetti un indirizzo URL per riga nel campo [!DNL Entrypoints] .
1. (Facoltativo) Nell&#39;elenco a discesa **[!UICONTROL Add Index Connector Configurations]** , seleziona un connettore indice da aggiungere come punto di ingresso per l&#39;indicizzazione.

   L’elenco a discesa è disponibile solo se in precedenza sono state aggiunte una o più definizioni di connettore indice.

   ![](assets/url_entrypoints_index_connector.png)

   Vedere [Aggiunta di una definizione del connettore indice](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle maschere URL {#concept_8039DFC53FF3410AA494D602F71BA164}

Le maschere URL sono pattern che determinano quale dei documenti del sito web il robot di ricerca indicizza o meno gli indici.

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati delle maschere URL siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Di seguito sono riportati due tipi di maschere URL che puoi utilizzare:

* Includi maschere URL
* Escludere le maschere URL

Includi maschere URL dicono al robot di ricerca di indicizzare tutti i documenti che corrispondono al pattern della maschera.

Le maschere URL di esclusione indicano al robot di ricerca di indicizzare i documenti corrispondenti.

Mentre il robot di ricerca viaggia da un link a un link attraverso il tuo sito web, incontra URL e cerca maschere che corrispondono a quegli URL. La prima corrispondenza determina se includere o escludere tale URL dall’indice. Se nessuna maschera corrisponde a un URL rilevato, tale URL viene scartato dall&#39;indice.

Le maschere URL di inclusione per gli URL del punto di ingresso vengono generate automaticamente. Questo comportamento assicura l’indicizzazione di tutti i documenti presenti sul sito web. Permette inoltre di eliminare comodamente i link che &quot;lasciano&quot; il tuo sito web. Ad esempio, se una pagina indicizzata si collega a https://www.yahoo.com, il robot di ricerca non indicizza tale URL perché non corrisponde alla maschera di inclusione generata automaticamente dall’URL del punto di ingresso.

Ogni maschera URL specificata deve trovarsi su una riga separata.

La maschera può specificare uno dei seguenti elementi:

* Un percorso completo come in `https://www.mydomain.com/products.html`.
* Un percorso parziale come in `https://www.mydomain.com/products`.
* URL che utilizza caratteri jolly come in `https://www.mydomain.com/*.html`.
* Un’espressione regolare (per gli utenti avanzati).

   Per rendere una maschera un&#39;espressione regolare, inserisci la parola chiave `regexp` tra il tipo di maschera ( `exclude` o `include`) e la maschera URL.

Di seguito è riportato un semplice esempio di maschera di esclusione URL:

```
exclude https://www.mydomain.com/photos
```

Poiché questo esempio è una maschera di esclusione URL, qualsiasi documento che corrisponde al pattern non viene indicizzato. Il pattern corrisponde a qualsiasi elemento rilevato, sia file che cartelle, in modo che `https://www.mydomain.com/photos.html` e `https://www.mydomain.com/photos/index.html`, entrambi corrispondenti all’URL di esclusione, non siano indicizzati. Per far corrispondere solo i file presenti nella cartella `/photos/` , la maschera URL deve contenere una barra finale, come nell’esempio seguente:

```
exclude https://www.mydomain.com/photos/
```

L&#39;esempio di maschera di esclusione seguente utilizza un carattere jolly. Indica al robot di ricerca di ignorare i file con l&#39;estensione &quot;.pdf&quot;. Il robot di ricerca non aggiunge questi file all&#39;indice.

```
exclude *.pdf
```

Una semplice maschera URL include è la seguente:

```
include https://www.mydomain.com/news/
```

Sono indicizzati solo i documenti collegati tramite una serie di collegamenti da un punto di ingresso URL o utilizzati come punto di ingresso URL. L’elenco esclusivo dell’URL di un documento come maschera URL di inclusione non indicizza un documento non collegato. Per aggiungere all’indice documenti non collegati, puoi utilizzare la funzione Punti di ingresso URL .

Consulta [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Le maschere di inclusione e di esclusione possono funzionare insieme. Puoi escludere un’ampia parte del sito web dall’indicizzazione creando una maschera di URL esclusa ma includi una o più delle pagine escluse con una maschera URL inclusa. Ad esempio, supponiamo che l’URL del punto di ingresso sia il seguente:

```
https://www.mydomain.com/photos/
```

Il robot di ricerca esegue la ricerca per indicizzazione e indicizza tutte le pagine sotto `/photos/summer/`, `/photos/spring/` e `/photos/fall/` (partendo dal presupposto che siano presenti collegamenti ad almeno una pagina in ciascuna directory dalla cartella `photos`). Questo comportamento si verifica perché i percorsi di collegamento consentono al robot di ricerca di trovare i documenti nelle cartelle `/summer/`, `/spring/` e `/fall/` e gli URL delle cartelle corrispondono alla maschera di inclusione generata automaticamente dall&#39;URL del punto di ingresso.

Puoi scegliere di escludere tutte le pagine della cartella `/fall/` con una maschera di esclusione URL come nell’esempio seguente:

```
exclude https://www.mydomain.com/photos/fall/
```

Oppure, includi in modo selettivo solo `/photos/fall/redleaves4.html` come parte dell&#39;indice con la seguente maschera URL:

```
include https://www.mydomain.com/photos/fall/redleaves4.html
```

Affinché i due esempi di maschera di cui sopra funzionino come previsto, la maschera di inclusione è elencata per prima, come nell&#39;esempio seguente:

```
include https://www.mydomain.com/photos/fall/redleaves4.html 
exclude https://www.mydomain.com/photos/fall/
```

Poiché il robot di ricerca segue le direzioni nell&#39;ordine in cui sono elencate, il robot di ricerca include prima `/photos/fall/redleaves4.html`, quindi esclude il resto dei file presenti nella cartella `/fall`.

Se le istruzioni sono specificate nel modo opposto a quello indicato di seguito:

```
exclude https://www.mydomain.com/photos/fall/ 
include https://www.mydomain.com/photos/fall/redleaves4.html
```

Quindi `/photos/fall/redleaves4.html` non è incluso, anche se la maschera specifica che è incluso.

Una maschera URL che appare per prima ha sempre la precedenza su una maschera URL che appare successivamente nelle impostazioni della maschera. Inoltre, se il robot di ricerca incontra una pagina che corrisponde a una maschera URL di inclusione e una maschera URL di esclusione, la maschera elencata per prima ha sempre la precedenza.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Utilizzo delle parole chiave con le maschere URL {#section_7609A7A6D79B482ABCA8900886541AAB}

È possibile qualificare ogni maschera di inclusione con una o più parole chiave separate da spazio, che influiscono sulla modalità di indicizzazione delle pagine corrispondenti.

Una virgola non è valida come separatore tra la maschera e la parola chiave; puoi usare solo spazi.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Parola chiave </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> Se non desideri indicizzare il testo nelle pagine che corrispondono alla maschera URL, ma desideri seguire i collegamenti alle pagine corrispondenti, aggiungi 
     <code>
       noindex 
     </code> dopo la maschera URL di inclusione. Separa la parola chiave dalla maschera con uno spazio come nell'esempio seguente: </p> <p> <code> include&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>L'esempio precedente specifica che il robot di ricerca segue tutti i collegamenti da file con 
     Estensione <code>
       .swf 
     </code>, ma disabilita l'indicizzazione di tutto il testo contenuto in tali file. </p> <p>La 
     La parola chiave <code>
       noindex 
     </code> equivale a un tag meta robot con 
     <code>
       content="noindex" 
     </code> tra 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code> tag di pagine corrispondenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Se desideri indicizzare il testo nelle pagine che corrispondono alla maschera URL, ma non desideri seguire i collegamenti della pagina corrispondente, aggiungi 
     <code>
       nofollow 
     </code> dopo la maschera URL di inclusione. Separa la parola chiave dalla maschera con uno spazio come nell'esempio seguente: </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>La 
     La parola chiave <code>
       nofollow 
     </code> equivale a un tag meta robot con 
     <code>
       content="nofollow" 
     </code> tra 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code> tag di pagine corrispondenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>rigexp </p> </td> 
   <td colname="col2"> <p>Utilizzata sia per includere che per escludere le maschere. </p> <p>Qualsiasi maschera URL preceduta da 
     <code>
       regexp 
     </code> viene trattato come un’espressione regolare. Se il robot di ricerca rileva documenti che corrispondono a una maschera URL con espressione regolare esclusa, tali documenti non vengono indicizzati. Se il robot di ricerca rileva documenti che corrispondono a una maschera URL con espressione regolare, questi documenti vengono indicizzati. Ad esempio, supponiamo di avere la seguente maschera URL: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*/products/.*\.html$ </code> </p> <p>Il robot di ricerca esclude i file corrispondenti, ad esempio 
     <code>
       https://www.mydomain.com/products/page1.html 
     </code> </p> <p>Se hai avuto la seguente esclusione della maschera URL con espressione regolare: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*\?..*$ </code> </p> <p>Il robot di ricerca non deve includere alcun URL contenente un parametro CGI come 
     <code>
       https://www.mydomain.com/cgi/prog/?arg1=val1&amp;arg2=val2 
     </code>. </p> <p>Se avevi la seguente maschera URL con espressione regolare: </p> <p> <code> include&amp;nbsp;regexp&amp;nbsp;^.*\.swf$&amp;nbsp;noindex </code> </p> <p>Il robot di ricerca segue tutti i collegamenti da file con estensione ".swf". La 
     La parola chiave <code>
       noindex 
     </code> specifica inoltre che il testo dei file corrispondenti non è indicizzato. </p> <p>Consulta <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aggiunta di maschere URL per indicizzare o meno parti del sito web {#task_E1AFC17C746048B8843013D979E082C1}

È possibile utilizzare [!DNL URL Masks] per definire quali parti del sito web si desidera o meno sottoporre a ricerca per indicizzazione e indicizzare.

Utilizza il campo Maschere URL di test per verificare se un documento è incluso o meno dopo l&#39;indicizzazione.

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati delle maschere URL siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Per aggiungere maschere URL per indicizzare o non indicizzare parti del sito web**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**.
1. (Facoltativo) Nella pagina [!DNL URL Masks], nel campo **[!UICONTROL Test URL Masks]** immetti una maschera URL di prova dal sito web, quindi fai clic su **[!UICONTROL Test]**.
1. Nel campo [!DNL URL Masks] , digita `include` (per aggiungere un sito web che desideri sottoporre a ricerca per indicizzazione e indicizzazione) oppure digita `exclude` (per impedire che un sito web venga sottoposto a ricerca per indicizzazione e indicizzazione), seguito dall’indirizzo della maschera URL.

   Immettere un indirizzo di maschera URL per riga. Esempio:

   ```
   include https://www.mycompany.com/summer 
   include https://www.mycompany.com/spring 
   exclude regexp .*\.xml 
   exclude https://www.mycompany.com/fall
   ```

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle maschere di data {#concept_F4F1F58A646F4A86B8650EC46FDCEF66}

È possibile utilizzare le maschere di data per includere o escludere i file dai risultati della ricerca in base all’età del file.

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati delle maschere URL siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Di seguito sono riportati due tipi di maschere data che è possibile utilizzare:

* Includi maschere di data (&quot;include-days&quot; e &quot;include-date&quot;)

   Includi i file di indice delle maschere di data che sono datati alla data specificata o prima di essa.
* Escludere le maschere di data (&quot;giorni di esclusione&quot; e &quot;data di esclusione&quot;)

   Escludere i file di indice delle maschere di data che sono datati alla data specificata o prima di essa.

Per impostazione predefinita, la data del file è determinata dalle informazioni del tag meta. Se non viene trovato alcun tag Meta , la data di un file viene determinata dall’intestazione HTTP ricevuta dal server quando il robot di ricerca scarica un file.

Ogni maschera data specificata deve trovarsi su una riga separata.

La maschera può specificare uno dei seguenti elementi:

* Un percorso completo come in `https://www.mydomain.com/products.html`
* Un percorso parziale come in `https://www.mydomain.com/products`
* URL che utilizza caratteri jolly `https://www.mydomain.com/*.html`
* Un&#39;espressione regolare. Per rendere una maschera un&#39;espressione regolare, inserisci la parola chiave `regexp` prima dell&#39;URL.

Le maschere di data di inclusione e di esclusione possono specificare una data in uno dei due modi seguenti. Le maschere vengono applicate solo se i file corrispondenti sono stati creati alla data specificata o prima di essa:

1. Un numero di giorni. Ad esempio, supponiamo che la maschera data sia la seguente:

   ```
   exclude-days 30 https://www.mydomain.com/docs/archive/)
   ```

   Il numero di giorni specificati viene conteggiato nuovamente. Se il file è datato il o prima della data di arrivo, la maschera viene applicata.

1. Una data effettiva utilizzando il formato AAAA-MM-GG. Ad esempio, supponiamo che la maschera data sia la seguente:

   ```
   include-date 2011-02-15 https://www.mydomain.com/docs/archive/)
   ```

   Se il documento corrispondente è datato alla data specificata o prima di essa, viene applicata la maschera data.

Di seguito è riportato un semplice esempio di maschera di data di esclusione:

```
exclude-days 90 https://www.mydomain.com/docs/archive
```

Poiché si tratta di una maschera di data di esclusione, qualsiasi file che corrisponde al pattern non viene indicizzato ed ha 90 giorni di età o meno. Quando si esclude un documento, non viene indicizzato alcun testo e dal file non vengono seguiti collegamenti. Il file viene effettivamente ignorato. In questo esempio, sia i file che le cartelle potrebbero corrispondere al pattern URL specificato. Tieni presente che sia `https://www.mydomain.com/docs/archive.html` che `https://www.mydomain.com/docs/archive/index.html` corrispondono al pattern e non sono indicizzati se hanno 90 giorni o meno di età. Per far corrispondere solo i file presenti nella cartella `/docs/archive/`, la maschera di data deve contenere una barra finale come illustrato di seguito:

```
exclude-days 90 https://www.mydomain.com/docs/archive/
```

Le maschere di data possono essere utilizzate anche con i caratteri jolly. La seguente maschera di esclusione indica al robot di ricerca di ignorare i file con estensione &quot;.pdf&quot; che sono datati il 2011-02-15 o prima. Il robot di ricerca non aggiunge alcun file corrispondente al tuo indice.

```
exclude-date 2011-02-15 *.pdf
```

Include date mask ha un aspetto simile, solo i file corrispondenti vengono aggiunti all&#39;indice. L&#39;esempio seguente include date mask indica al robot di ricerca di indicizzare il testo da qualsiasi file che abbiano zero giorni di età o meno nell&#39;area `/docs/archive/manual/` del sito web.

```
include-days 0 https://www.mydomain.com/docs/archive/manual/
```

Le maschere di inclusione e di esclusione possono funzionare insieme. Ad esempio, puoi escludere un’ampia parte del sito web dall’indicizzazione creando una maschera di data di esclusione, includendo tuttavia una o più delle pagine escluse con una maschera URL di inclusione. Se l’URL del punto di ingresso è il seguente:

```
https://www.mydomain.com/archive/
```

Il robot di ricerca esegue la ricerca per indicizzazione e indicizza tutte le pagine sotto `/archive/summer/`, `/archive/spring/` e `/archive/fall/` (partendo dal presupposto che siano presenti collegamenti ad almeno una pagina in ciascuna cartella della cartella `archive` ). Questo comportamento si verifica perché i percorsi di collegamento consentono al robot di ricerca di &quot;trovare&quot; i file nelle cartelle `/summer/`, `/spring/` e `/fall/` e gli URL delle cartelle corrispondono alla maschera di inclusione generata automaticamente dall’URL del punto di ingresso.

Consulta [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Consulta [Configurazione delle impostazioni account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

È possibile scegliere di escludere tutte le pagine di età superiore a 90 giorni nella cartella `/fall/` con una maschera di data di esclusione, come illustrato di seguito:

```
exclude-days 90 https://www.mydomain.com/archive/fall/
```

È possibile includere selettivamente solo `/archive/fall/index.html` (indipendentemente dall&#39;età, qualsiasi file di 0 giorni o più vecchi corrisponde) come parte dell&#39;indice con la seguente maschera di data:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html
```

Affinché i due esempi di maschera di cui sopra funzionino come previsto, è necessario elencare prima la maschera di inclusione come nell&#39;esempio seguente:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html 
exclude-days 90 https://www.mydomain.com/archive/fall/
```

Poiché il robot di ricerca segue le indicazioni nell&#39;ordine specificato, il robot di ricerca include prima `/archive/fall/index.html`, quindi esclude il resto dei file nella cartella `/fall`.

Se le istruzioni sono specificate nel modo opposto a quello indicato di seguito:

```
exclude-days 90 https://www.mydomain.com/archive/fall/ 
include-days 0 https://www.mydomain.com/archive/fall/index.html 
```

Quindi `/archive/fall/index.html` non è incluso, anche se la maschera specifica che dovrebbe essere. Una maschera di data che appare per prima ha sempre la precedenza su una maschera di data che potrebbe apparire successivamente nelle impostazioni della maschera. Inoltre, se il robot di ricerca rileva una pagina che corrisponde sia a una maschera di data di inclusione che a una maschera di data di esclusione, la maschera elencata per prima ha sempre la precedenza.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Informazioni sull’utilizzo delle parole chiave con le maschere data {#section_CCBB3E3FDBDE4725B2B571FD6594470C}

È possibile qualificare ogni maschera di inclusione con una o più parole chiave separate da spazio, che influiscono sulla modalità di indicizzazione delle pagine corrispondenti.

Una virgola non è valida come separatore tra la maschera e la parola chiave; puoi usare solo spazi.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Parola chiave </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> Se non si desidera indicizzare il testo nelle pagine che sono date in o prima della data specificata dalla maschera di inclusione, aggiungere 
     <code>
       noindex 
     </code> dopo la maschera di data di inclusione, come illustrato di seguito: </p> <p> <code> include-days&amp;nbsp;10&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>Separa la parola chiave dalla maschera con uno spazio. </p> <p>L'esempio precedente specifica che il robot di ricerca segue tutti i collegamenti da file con estensione ".swf" che hanno 10 giorni o più. Tuttavia, disabilita l’indicizzazione di tutto il testo contenuto in tali file. </p> <p>È possibile assicurarsi che il testo per i file precedenti non sia indicizzato ma segua comunque tutti i collegamenti da tali file. In questi casi, utilizza una maschera data di inclusione con la parola chiave "noindex" invece di utilizzare una maschera data di esclusione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Se si desidera indicizzare il testo nelle pagine che sono date in o prima della data specificata dalla maschera di inclusione, ma non si desidera seguire i collegamenti della pagina corrispondente, aggiungere 
     <code>
       nofollow 
     </code> dopo la maschera di data di inclusione, come illustrato di seguito: </p> <p> <code> include-days&amp;nbsp;8&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>Separa la parola chiave dalla maschera con uno spazio. </p> <p>La 
     La parola chiave <code>
       nofollow 
     </code> equivale a un tag meta robot con 
     <code>
       content="nofollow" 
     </code> tra 
     Tag <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code> di pagine corrispondenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>data server </p> </td> 
   <td colname="col2"> <p>Utilizzata sia per includere che per escludere le maschere. </p> <p>Il robot di ricerca generalmente scarica e analizza ogni file prima di controllare la data di mascheramento. Questo comportamento si verifica perché alcuni tipi di file possono specificare una data all’interno del file stesso. Ad esempio, un documento HTML può includere meta tag che impostano la data del file. </p> <p>Se escludi molti file in base alla loro data e non desideri caricare i server in modo non necessario, puoi utilizzare 
     <code>
       server-date 
     </code> dopo l’URL nella maschera data. </p> <p>Questa parola chiave indica al robot di ricerca di considerare attendibile la data del file restituito dal server anziché analizzare ogni file. Ad esempio, la seguente maschera di data di esclusione ignora le pagine che corrispondono all'URL se i documenti hanno 90 giorni o meno, in base alla data restituita dal server nelle intestazioni HTTP: </p> <p> <code> exclude-days&amp;nbsp;90&amp;nbsp;https://www.mydomain.com/docs/archive&amp;nbsp;server-date </code> </p> <p> Se la data restituita dal server è precedente o superiore a 90 giorni, 
     <code>
       server-date 
     </code> specifica che i documenti esclusi non possono essere scaricati dal server. Il risultato è un tempo di indicizzazione più rapido per i documenti e un carico ridotto posizionato sui server. Se 
     <code>
       server-date 
     </code> non è specificato, il robot di ricerca ignora la data restituita dal server nelle intestazioni HTTP. Invece, ogni file viene scaricato e controllato per vedere se la data è specificata. Se nel file non è specificata alcuna data, il robot di ricerca utilizza la data restituita dal server. </p> <p>Non utilizzare 
     <code>
       server-date 
     </code> se i file contengono comandi che ignorano la data del server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>rigexp </p> </td> 
   <td colname="col2"> <p> Utilizzate sia per includere che per escludere le maschere. </p> <p>Qualsiasi maschera di data preceduta da 
     <code>
       regexp 
     </code> viene trattato come un’espressione regolare. </p> <p>Se il robot di ricerca rileva file che corrispondono a una maschera di data con espressione regolare esclusa, non indicizza tali file. </p> <p>Se il robot di ricerca rileva file che corrispondono a una maschera di data con espressione regolare inclusa, indicizza tali documenti. </p> <p>Ad esempio, supponiamo di avere la seguente maschera data: </p> <p> <code> exclude-days&amp;nbsp;180&amp;nbsp;regexp&amp;nbsp;.*archive.* </code> </p> <p>La maschera dice al robot di ricerca di escludere i file corrispondenti che sono 180 giorni o più. Cioè, file che contengono la parola "archivio" nel loro URL. </p> <p>Consulta <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aggiunta di maschere di data per indicizzare o non indicizzare parti del sito web {#task_0010543C55F648D2B5DEFEFAD60FAF04}

È possibile utilizzare le maschere data per includere o escludere i file dai risultati della ricerca del cliente in base all’età dei file.

Utilizza i campi **[!UICONTROL Test Date]** e **[!UICONTROL Test URL]** per verificare se un file è incluso o meno dopo l’indice.

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati delle maschere URL siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Per aggiungere maschere di data per indicizzare o non indicizzare parti del sito web**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Date Masks]**.
1. (Facoltativo) Nella pagina [!DNL Date Masks], nel campo **[!UICONTROL Test Date]** immettere una data formattata come AAAA-MM-GG (ad esempio, `2011-07-25`); nel campo **[!UICONTROL Test URL]** , immetti una maschera URL dal sito web, quindi fai clic su **[!UICONTROL Test]**.
1. Nel campo [!DNL Date Masks] , immetti un indirizzo maschera data per riga.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle password {#concept_3EDBD731725D46B891F834D4472774DC}

Per accedere a parti del sito Web protette con l&#39;autenticazione HTTP Basic, è possibile aggiungere una o più password.

Prima che gli effetti delle impostazioni Password siano visibili ai clienti, è necessario ricostruire l&#39;indice del sito.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Nella pagina [!DNL Passwords], digita ogni password su una sola riga. La password è costituita da un URL o un realm, un nome utente e una password, come nell’esempio seguente:

```
https://www.mydomain.com/ myname mypassword
```

Invece di usare un percorso URL, come sopra, puoi anche specificare un realm.

Per determinare il realm corretto da utilizzare, aprire una pagina web protetta da password con un browser e guardare la finestra di dialogo &quot;Immettere password di rete&quot;.

![](assets/realms.gif)

Il nome dell&#39;area di autenticazione, in questo caso, è &quot;Area di lavoro del sito personale&quot;.

Utilizzando il nome del realm sopra riportato, la password potrebbe avere l&#39;aspetto seguente:

```
My Site Realm myusername mypassword
```

Se il sito web dispone di più aree di autenticazione, è possibile creare più password immettendo un nome utente e una password per ogni area di autenticazione su una riga separata, come nell&#39;esempio seguente:

```
Realm1 name1 password1 
Realm2 name2 password2 
Realm3 name3 password3
```

È possibile combinare password che contengono URL o realm in modo che l&#39;elenco delle password possa avere l&#39;aspetto seguente:

```
Realm1 name1 password1 
https://www.mysite.com/path1/path2 name2 password2 
Realm3 name3 password3 
Realm4 name4 password4 
https://www.mysite.com/path1/path5 name5 password5 
https://www.mysite.com/path6 name6 password6
```

Nell&#39;elenco precedente, viene utilizzata la prima password che contiene un realm o un URL corrispondente alla richiesta di autenticazione del server. Anche se il file in `https://www.mysite.com/path1/path2/index.html` si trova in `Realm3`, ad esempio, vengono utilizzati `name2` e `password2` perché la password definita con l&#39;URL è elencata sopra quella definita con l&#39;area di autenticazione.

## Aggiunta di password per accedere alle aree del sito web che richiedono autenticazione {#task_DED19D476FF04B48BB6456D5ECB8628A}

Puoi utilizzare Password per accedere alle aree protette da password del tuo sito web a scopo di ricerca per indicizzazione e indicizzazione.

Prima che gli effetti della password siano visibili ai clienti, assicurati di ricostruire il tuo indice del sito

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Per aggiungere password per accedere alle aree del sito web che richiedono autenticazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Passwords]**.
1. Nella pagina [!DNL Passwords], immetti un realm o un URL nel campo **[!UICONTROL Passwords]** e il nome utente e la password associati, separati da uno spazio.

   Esempio di password di un realm e di un URL su righe separate:

   ```
   Realm1 name1 password1 
   https://www.mysite.com/path1/path2 name2 password2
   ```

   Aggiungi una sola password per riga.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sui tipi di contenuto {#concept_6FEA1355C0374500B4C53090C34A8A07}

È possibile utilizzare [!DNL Content Types] per selezionare i tipi di file da esaminare e indicizzare per questo account.

I tipi di contenuto che è possibile scegliere di eseguire ricerche per indicizzazione e indicizzazione includono documenti PDF, documenti di testo, filmati di Flash di Adobe, file da applicazioni di Microsoft Office come Word, Excel e Powerpoint e testo in file MP3. Il testo che si trova all’interno dei tipi di contenuto selezionati viene ricercato insieme a tutto il testo presente sul sito web.

Prima che gli effetti delle impostazioni Tipi di contenuto siano visibili ai clienti, devi ricreare l’indice del sito.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Informazioni sull&#39;indicizzazione dei file musicali MP3 {#section_AD2E28BEEE3E46629E2B05C34A963673}

Se selezioni l&#39;opzione **[!UICONTROL Text in MP3 Music Files]** nella pagina [!DNL Content Types], un file MP3 viene sottoposto a ricerca per indicizzazione e indicizzato in uno dei due modi seguenti. Il primo e il più comune modo è quello di un tag href di ancoraggio in un file HTML come nel seguente:

```
<a href="MP3-file-URL"></a>
```

Il secondo modo è quello di inserire l&#39;URL del file MP3 come punto di ingresso dell&#39;URL.

Consulta [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Un file MP3 è riconosciuto dal suo tipo MIME &quot;audio/mpeg&quot;.

Tieni presente che le dimensioni dei file musicali MP3 possono essere abbastanza grandi, anche se di solito contengono solo una piccola quantità di testo. Ad esempio, i file MP3 possono memorizzare facoltativamente cose come il nome dell&#39;album, il nome dell&#39;artista, il titolo della canzone, il genere della canzone, l&#39;anno di rilascio e un commento. Queste informazioni vengono memorizzate alla fine del file in quello che viene chiamato TAG. I file MP3 contenenti informazioni TAG sono indicizzati nel modo seguente:

* Il titolo della canzone viene trattato come il titolo di una pagina HTML.
* Il commento viene trattato come una descrizione definita per una pagina HTML.
* Il genere viene trattato come una parola chiave definita per una pagina HTML.
* Il nome dell’artista, il nome dell’album e l’anno di rilascio vengono trattati come il corpo di una pagina HTML.

Tieni presente che ogni file MP3 sottoposto a ricerca per indicizzazione e indicizzato sul tuo sito web conta come una pagina.

Se il tuo sito web contiene molti file MP3 di grandi dimensioni, puoi superare il limite di byte di indicizzazione per il tuo account. In questo caso, puoi deselezionare **[!UICONTROL Text in MP3 Music Files]** nella pagina [!DNL Content Types] per impedire l&#39;indicizzazione di tutti i file MP3 sul tuo sito web.

Se si desidera solo impedire l&#39;indicizzazione di alcuni file MP3 sul tuo sito web, è possibile effettuare una delle seguenti operazioni:

* Racchiudi i tag di ancoraggio che collegano ai file MP3 con tag `<nofollow>` e `</nofollow>` . Il robot di ricerca non segue i collegamenti tra questi tag.

* Aggiungi gli URL dei file MP3 come maschere di esclusione.

   Consulta [Informazioni sulle maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

## Selezione dei tipi di contenuto per la ricerca per indicizzazione e l&#39;indice {#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8}

È possibile utilizzare [!DNL Content Types] per selezionare i tipi di file da esaminare e indicizzare per questo account.

I tipi di contenuto che è possibile scegliere di eseguire ricerche per indicizzazione e indicizzazione includono documenti PDF, documenti di testo, filmati di Flash di Adobe, file da applicazioni di Microsoft Office come Word, Excel e Powerpoint e testo in file MP3. Il testo che si trova all’interno dei tipi di contenuto selezionati viene ricercato insieme a tutto il testo presente sul sito web.

Prima che gli effetti delle impostazioni Tipi di contenuto siano visibili ai clienti, devi ricreare l’indice del sito.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Per eseguire la ricerca per indicizzazione dei file MP3 cinesi, giapponesi o coreani, completa i passaggi seguenti. Quindi, in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**, specifica il set di caratteri utilizzato per codificare i file MP3.

Vedere [Informazioni sulle iniezioni](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

**Selezione dei tipi di contenuto da sottoporre a ricerca per indicizzazione e per indicizzazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**.
1. Nella pagina [!DNL Content Types] , controlla i tipi di file che desideri esaminare e indicizzare sul tuo sito web.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle connessioni {#concept_E2F3B7E7521147479E5948A94BB3A40B}

È possibile utilizzare Connessioni per aggiungere fino a dieci connessioni HTTP utilizzate dal robot di ricerca per indicizzare il sito web.

L’aumento del numero di connessioni può ridurre in modo significativo il tempo necessario per completare una ricerca per indicizzazione e per indicizzazione. Tuttavia, tenere presente che ogni connessione aggiuntiva aumenta il carico sul server.

## Aggiunta di connessioni per aumentare la velocità di indicizzazione {#task_3E9B83E43C1842A19066355A15C4A6FB}

È possibile ridurre il tempo necessario per indicizzare il sito web utilizzando Connessioni per aumentare il numero di connessioni HTTP simultanee utilizzate dal crawler. Puoi aggiungere fino a dieci connessioni.

Tieni presente che ogni connessione aggiuntiva aumenta il carico inserito sul server.

**Per aggiungere connessioni per aumentare la velocità di indicizzazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Connections]**.
1. Nella pagina [!DNL Parallel Indexing Connections] , immetti il numero di connessioni (1-10) che desideri aggiungere nel campo **[!UICONTROL Number of Connections]** .
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sull’invio del modulo {#concept_CADD5D7CF373497DAA6F8564D7BC8502}

È possibile utilizzare Invio modulo per riconoscere ed elaborare i moduli sul sito web.

Durante la ricerca per indicizzazione e la ricerca per indicizzazione del sito web, ogni modulo rilevato viene confrontato con le definizioni del modulo aggiunte. Se un modulo corrisponde a una definizione di modulo, il modulo viene inviato per l’indicizzazione. Se un modulo corrisponde a più definizioni, viene inviato una sola volta per ciascuna definizione corrispondente.

## Aggiunta di definizioni di moduli per l’indicizzazione dei moduli sul sito web {#task_62FBCE9E6DBE4BDA8D1249233ADFC00F}

È possibile utilizzare [!DNL Form Submission] per elaborare i moduli riconosciuti sul sito web a scopo di indicizzazione.

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati delle modifiche siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Aggiunta di definizioni di moduli per l’indicizzazione dei moduli sul sito web**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Nella pagina [!DNL Form Submission], fai clic su **[!UICONTROL Add New Form]**.
1. Nella pagina [!DNL Add Form Definition] , imposta le opzioni [!DNL Form Recognition] e [!DNL Form Submission] .

   Le cinque opzioni della sezione [!DNL Form Recognition] nella pagina [!DNL Form Definition] vengono utilizzate per identificare i moduli che possono essere elaborati nelle pagine web.

   Le tre opzioni della sezione [!DNL Form Submission] vengono utilizzate per specificare i parametri e i valori inviati con un modulo al server web.

   Immettere un parametro di riconoscimento o di invio per riga. Ogni parametro deve includere un nome e un valore.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <b>Riconoscimento del modulo</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maschera URL pagina </p> </td> 
      <td colname="col2"> <p>Identificare le pagine web che contengono il modulo. Per identificare un modulo visualizzato su una singola pagina, immetti l’URL della pagina come nell’esempio seguente: </p> <p> <code> https://www.mydomain.com/login.html </code> </p> <p>Per identificare i moduli che vengono visualizzati su più pagine, specificare una maschera URL che utilizzi i caratteri jolly per descrivere le pagine. Per identificare i moduli incontrati in qualsiasi pagina ASP in <code> https://www.mydomain.com/register/ </code>, ad esempio, è necessario specificare quanto segue: </p> <p> <code> https://www.mydomain.com/register/*.asp&amp;nbsp; </code> </p> <p>È inoltre possibile utilizzare un’espressione regolare per identificare più pagine. Basta specificare 
      <code>
        regexp 
      </code> parola chiave prima della maschera URL, come nell’esempio seguente: </p> <p> <code> regexp&amp;nbsp;^https://www\.mydomain\.com/.*/login\.html$ </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maschera URL azione </p> </td> 
      <td colname="col2"> <p>Identifica l'attributo action del 
      Tag <code>
        &lt;form&gt; 
      </code> . </p> <p>Come la maschera URL della pagina, la maschera URL dell’azione può assumere la forma di un singolo URL, un URL con caratteri jolly o un’espressione regolare. </p> <p>La maschera URL può essere una delle seguenti: 
      <ul id="ul_EDFE7688D3DD4C0BBACCE5D4648D8E44"> 
      <li id="li_77550A448D954EF29FF33EE5E8B5E0F5"> Un percorso completo come nel seguente: <code> https://www.mydomain.com/products.html </code> </li> 
      <li id="li_F84E25553BBA41419BE153DC0709E011"> Un percorso parziale come nell’esempio seguente: <code> https://www.mydomain.com/products </code> </li> 
      <li id="li_8DADA1C8604740FCACBA30B4AAADB2A1"> Un URL che utilizza caratteri jolly come nell’esempio seguente: <code> https://www.mydomain.com/*.html </code> </li> 
      <li id="li_1EF637B450654B509AA4B618F7FD3C2B"> Un'espressione regolare come nell'esempio seguente: <code> regexp&amp;nbsp^https://www\.mydomain\.com/.*/login\.html$ </code> </li> 
      </ul> </p> <p>Se non si desidera indicizzare il testo nelle pagine identificate da una maschera URL o da una maschera URL di azione, o se non si desidera che i collegamenti siano seguiti in tali pagine, è possibile utilizzare la 
      <code>
        noindex 
      </code> e 
      <code>
        nofollow 
      </code> parole chiave. Puoi aggiungere queste parole chiave alle maschere utilizzando maschere URL o punti di ingresso. </p> <p>Consulta <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573" type="concept" format="dita" scope="local"> Informazioni sui punti di ingresso URL </a>. </p> <p>Consulta <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> Informazioni sulle maschere URL </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maschera nome modulo </p> </td> 
      <td colname="col2"> <p>Identifica i moduli se la 
      I tag <code>
        &lt;form&gt; 
      </code> presenti nelle pagine web contengono un attributo name. </p> <p>Puoi utilizzare un nome semplice ( 
      <code>
        login_form 
      </code>), un nome con un carattere jolly ( 
      <code>
        form* 
      </code>) o un'espressione regolare ( 
      <code>
        regexp ^.*authorize.*$ 
      </code>). </p> <p>In genere è possibile lasciare vuoto questo campo perché in genere i moduli non dispongono di un attributo nome. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maschera ID modulo </p> </td> 
      <td colname="col2"> <p>Identifica i moduli se la 
      I tag <code>
        &lt;form&gt; 
      </code> nelle pagine web contengono un attributo id . </p> <p>Puoi utilizzare un nome semplice ( 
      <code>
        login_form 
      </code>), un nome con un carattere jolly ( 
      <code>
        form* 
      </code>) o un'espressione regolare ( 
      <code>
        regexp ^.*authorize.*$ 
      </code>). </p> <p>In genere è possibile lasciare vuoto questo campo perché in genere i moduli non dispongono di un attributo nome. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametri </p> </td> 
      <td colname="col2"> <p>Identificare i moduli che contengono o non contengono un parametro denominato o un parametro denominato con un valore specifico. </p> <p>Ad esempio, per identificare un modulo contenente un parametro di posta elettronica preimpostato su rick_brough@mydomain.com, un parametro di password ma non un parametro di nome, è necessario specificare le seguenti impostazioni di parametro, una per riga: </p> <p> <code> email=rick_brough@mydomain.com password  not&nbsp;first-name </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Invio modulo</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignora URL azione </p> </td> 
      <td colname="col2"> <p>Specificare quando la destinazione dell'invio del modulo è diversa da quella specificata nell'attributo action del modulo. </p> <p>Ad esempio, è possibile utilizzare questa opzione quando il modulo viene inviato tramite una funzione JavaScript che crea un valore URL diverso da quello trovato nel modulo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Metodo di sostituzione </p> </td> 
      <td colname="col2"> <p>Specificare quando la destinazione dell'invio del modulo è diversa da quella utilizzata nell'attributo di azione del modulo e quando il JavaScript di invio ha modificato il metodo. </p> <p>I valori predefiniti per tutti i parametri del modulo ( 
      Tag <code>
        &lt;input&gt; 
      </code> , compresi i campi nascosti), impostazione predefinita 
      <code>
        &lt;option&gt; 
      </code> da un 
      Tag <code>
        &lt;select&gt; 
      </code> e testo predefinito compreso tra 
      I tag <code>
        &lt;textarea&gt;...&lt;/textarea&gt; 
      </code> ) vengono letti dalla pagina web. Tuttavia, tutti i parametri elencati nella sezione <span class="wintitle"> Invio modulo </span> nel campo <span class="uicontrol"> Parametri </span> vengono sostituiti con i valori predefiniti del modulo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametri </p> </td> 
      <td colname="col2"> <p>È possibile usare il prefisso "Parametri di invio del modulo" 
      <code>
        not 
      </code> parola chiave. </p> <p>Quando si esegue il prefisso di un parametro con 
      <code>
        not 
      </code>, non viene inviato come parte dell’invio del modulo. Questo comportamento è utile per le caselle di controllo che devono essere inviate deselezionate. </p> <p>Ad esempio, si supponga di voler inviare i seguenti parametri: </p> <p> 
      <ul id="ul_962D12BACF464FF189DB12BFAFCC93A6"> 
      <li id="li_830C6C3EC8D2448388A453BB8EDE5940"> Il parametro e-mail con il valore 
      <code>
        nobody@mydomain.com 
      </code> </li> 
      <li id="li_905497E3FACE472DBDD49392D5B45E01"> Il parametro della password con il valore 
      <code>
        tryme 
      </code> </li> 
      <li id="li_AAA411708ADC464793EADF0D821E282E"> Il parametro mycheck è deselezionato. </li> 
      <li id="li_0D3DDE641E2B4BEF9F570C03FDB40ED2"> <p>Tutti gli altri 
      I parametri <code>
        &lt;form&gt; 
      </code> come valori predefiniti </p> </li> 
      </ul> </p> <p>Il parametro di invio del modulo sarà simile al seguente: </p> <p> <code> email=nobody@mydomain.com 
        password=tryme 
        not&nbsp;mycheckbox </code> </p> <p>L'attributo del metodo 
      Il tag <code>
        &lt;form&gt; 
      </code> nella pagina web viene utilizzato per decidere se i dati vengono inviati al server utilizzando il metodo GET o il metodo POST. </p> <p>Se la 
      Il tag <code>
        &lt;form&gt; 
      </code> non contiene un attributo del metodo, il modulo viene inviato utilizzando il metodo GET. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica della definizione del modulo {#task_9FB34E9C8A814DFE9BF7F8F8F69BF314}

È possibile modificare una definizione di modulo esistente se un modulo sul sito web è stato modificato o se è sufficiente modificarla.

Tenere presente che nella pagina [!DNL Form Submission] non è disponibile alcuna funzione per ripristinare le modifiche apportate alla definizione di un modulo.[!DNL History]

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati delle modifiche siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Per modificare una definizione di un modulo**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Nella pagina [!DNL Form Submission] fare clic su **[!UICONTROL Edit]** a destra di una definizione di modulo che si desidera aggiornare.
1. Nella pagina [!DNL Edit Form Definition] , imposta le opzioni [!DNL Form Recognition] e [!DNL Form Submission] .

   Vedere la tabella delle opzioni in [Aggiunta di definizioni di moduli per l&#39;indicizzazione dei moduli sul sito web](../c-about-settings-menu/c-about-crawling-menu.md#task_62FBCE9E6DBE4BDA8D1249233ADFC00F).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una definizione di modulo {#task_C350FC0CDE344F2786215D544C048B5E}

È possibile eliminare una definizione di modulo esistente se il modulo non esiste più sul sito web o se non si desidera più elaborare e indicizzare un modulo specifico.

Tenere presente che nella pagina [!DNL Form Submission] non è disponibile alcuna funzione per ripristinare le modifiche apportate alla definizione di un modulo.[!DNL History]

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati delle modifiche siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Eliminazione di una definizione di modulo**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Nella pagina [!DNL Form Submission] fare clic su **[!UICONTROL Delete]** a destra della definizione di un modulo che si desidera rimuovere.

   Assicurarsi di scegliere la definizione corretta del modulo da eliminare. Non è disponibile una finestra di dialogo di conferma dell’eliminazione quando fai clic su **[!UICONTROL Delete]** nel passaggio successivo.
1. Nella pagina [!DNL Delete Form Definition], fai clic su **[!UICONTROL Delete]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sul connettore indice {#concept_CA6921E2FBF641F9B4F60C92B32AFA84}

Utilizza [!DNL Index Connector] per definire origini di input aggiuntive per l’indicizzazione di pagine XML o qualsiasi tipo di feed.

È possibile utilizzare un’origine di input per feed di dati per accedere al contenuto memorizzato in un modulo diverso da quello normalmente rilevato su un sito web utilizzando uno dei metodi di ricerca per indicizzazione disponibili. Ogni documento sottoposto a ricerca per indicizzazione e indicizzato corrisponde direttamente a una pagina di contenuto del sito web. Tuttavia, un feed di dati proviene da un documento XML o da un file di testo delimitato da virgole o da tabulazioni e contiene le informazioni sul contenuto da indicizzare.

Un&#39;origine dati XML è costituita da stanzas XML, o record, che contengono informazioni corrispondenti a singoli documenti. Questi singoli documenti vengono aggiunti all&#39;indice. Un feed di dati di testo contiene singoli record delimitati da nuove righe corrispondenti a singoli documenti. Questi singoli documenti vengono aggiunti anche all&#39;indice. In entrambi i casi, una configurazione del connettore indice descrive come interpretare il feed. Ogni configurazione descrive dove si trova il file e come i server vi accedono. La configurazione descrive anche le informazioni di &quot;mappatura&quot;. In altre parole, in che modo gli elementi di ogni record vengono utilizzati per compilare i campi di metadati nell&#39;indice risultante.

Dopo aver aggiunto una definizione del connettore indice alla pagina [!DNL Staged Index Connector Definitions], è possibile modificare qualsiasi impostazione di configurazione, *tranne* per i valori Nome o Tipo.

La pagina [!DNL Index Connector] mostra le seguenti informazioni:

* Nome dei connettori di indice definiti configurati e aggiunti.
* Uno dei seguenti tipi di origine dati per ciascun connettore aggiunto:

   * **Testo** : file semplici &quot;flat&quot;, delimitati da virgole, delimitati da tabulazioni o altri formati delimitati in modo coerente.
   * **Feed**  - Feed XML.
   * **XML**  - Raccolte di documenti XML.

* Se il connettore è abilitato o meno per la ricerca per indicizzazione successiva ed è stata eseguita l’indicizzazione.
* Indirizzo dell&#39;origine dati.

Vedere anche [Informazioni sul connettore indice](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)

## Come funziona il processo di indicizzazione per le configurazioni di testo e feed nel connettore indice {#section_E059A33D61EE4DB0972A37B8A35E9E16}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Passaggio </p> </th> 
   <th colname="col2" class="entry"> <p>Processo </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Scarica l’origine dati. </p> </td> 
   <td colname="col3"> <p>Per le configurazioni Testo e Feed, si tratta di un semplice download di file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Suddividi l’origine dati scaricata in singoli pseudo-documenti. </p> </td> 
   <td colname="col3"> <p>Per <span class="uicontrol"> Testo </span>, ogni riga di testo delimitata da una nuova riga corrisponde a un singolo documento e viene analizzata utilizzando il delimitatore specificato, ad esempio una virgola o una scheda. </p> <p>Per <span class="uicontrol"> Feed </span>, i dati di ciascun documento vengono estratti utilizzando un pattern di espressione regolare nel seguente modulo: </p> <p> <code> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Utilizzando <span class="uicontrol"> Mappa </span> nella pagina <span class="wintitle"> Connettore indice Aggiungi </span> , crea una copia in cache dei dati e quindi crea un elenco di collegamenti per il crawler. I dati vengono memorizzati in una cache locale e compilati con i campi configurati. </p> <p>I dati analizzati vengono scritti nella cache locale. </p> <p>Questa cache viene letta in seguito per creare i documenti HTML semplici necessari al crawler. Ad esempio, </p> <p> <code> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>L’elemento <span class="codeph"> &lt;title&gt; </span> viene generato solo quando esiste una mappatura al campo metadati Titolo. Allo stesso modo, l'elemento <span class="codeph"> &lt;body&gt; </span> viene generato solo quando esiste una mappatura al campo dei metadati Body. </p> <p> <b>Importante</b>: Non è supportato l’assegnazione di valori al tag meta URL predefinito. </p> <p>Per tutte le altre mappature, i tag <span class="codeph"> &lt;meta&gt; </span> vengono generati per ogni campo contenente i dati presenti nel documento originale. </p> <p>I campi di ciascun documento vengono aggiunti alla cache. Per ogni documento scritto nella cache, viene generato anche un collegamento come negli esempi seguenti: </p> <p> <code> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>La mappatura della configurazione deve avere un campo identificato come Chiave primaria. Questa mappatura rappresenta la chiave utilizzata quando i dati vengono recuperati dalla cache. </p> <p>Il crawler riconosce l'indice URL <span class="codeph">: Prefisso schema </span>, che può quindi accedere ai dati memorizzati nella cache locale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Eseguire la ricerca per indicizzazione del set di documenti memorizzati nella cache. </p> </td> 
   <td colname="col3"> <p>Indice <span class="codeph">: I collegamenti </span> vengono aggiunti all’elenco in sospeso del crawler e vengono elaborati nella sequenza di ricerca per indicizzazione normale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Elabora ogni documento. </p> </td> 
   <td colname="col3"> <p>Il valore chiave di ogni collegamento corrisponde a una voce nella cache, pertanto la ricerca per indicizzazione di ogni collegamento fa sì che i dati del documento vengano recuperati dalla cache. Viene quindi "assemblato" in un'immagine HTML che viene elaborata e aggiunta all'indice. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Funzionamento del processo di indicizzazione per le configurazioni XML nel connettore indice {#section_7F1551EA51854C5C99F284CE260526EB}

Il processo di indicizzazione per la configurazione XML è simile al processo per le configurazioni di Testo e Feed con le seguenti modifiche ed eccezioni minori.

Poiché i documenti per le ricerche per indicizzazione XML sono già separati in singoli file, i passaggi 1 e 2 della tabella precedente non si applicano direttamente. Se si specifica un URL nei campi **[!UICONTROL Host Address]** e **[!UICONTROL File Path]** della pagina [!DNL Index Connector Add], questo viene scaricato ed elaborato come un normale documento HTML. Si prevede che il documento di download contenga una raccolta di collegamenti `<a href="{url}"...`, ciascuno dei quali fa riferimento a un documento XML elaborato. Tali collegamenti sono convertiti nel seguente modulo:

```
<a href="index:<ic_config_name>?url="{url}">
```

Ad esempio, se la configurazione dell&#39;Adobe restituiva i seguenti collegamenti:

```
<a href="https://www.adobe.com/somepath/doc1.xml">doc 1</a> 
<a href="https://www.adobe.com/otherpath/doc2.xml">doc 2</a>
```

Nella tabella precedente, il punto 3 non si applica e il punto 4 è completato al momento della ricerca per indicizzazione e indicizzazione.

In alternativa, è possibile combinare i documenti XML con altri documenti scoperti naturalmente attraverso il processo di ricerca per indicizzazione. In questi casi, è possibile utilizzare le regole di riscrittura ( **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**) per modificare gli URL dei documenti XML per indirizzarli al connettore indice.

Consulta [Informazioni sulle regole di recupero URL dell&#39;elenco di ricerca per indicizzazione](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA).

Ad esempio, supponiamo che tu disponga della seguente regola di riscrittura:

```
RewriteRule (^http.*[.]xml$) index:Adobe?key=$1
```

Questa regola traduce qualsiasi URL che termina con `.xml` in un collegamento del connettore indice. Il crawler riconosce e riscrive lo schema URL `index:`. Il processo di download viene reindirizzato attraverso il server Apache del connettore indice sul server primario. Ogni documento scaricato viene esaminato utilizzando lo stesso pattern di espressione regolare utilizzato con Feed. In questo caso, tuttavia, il documento HTML fabbricato non viene salvato nella cache. Viene invece consegnato direttamente al crawler per l’elaborazione dell’indice.

## Come configurare più connettori indice {#section_C2B14C0F06354A57AEF6238FF3814E5D}

Puoi definire più configurazioni del connettore indice per qualsiasi account. Le configurazioni vengono aggiunte automaticamente all’elenco a discesa in **[!UICONTROL Settings]** > **[!UICONTROL Crawl]** > **[!UICONTROL URL Entrypoints]** come illustrato nella figura seguente:

![](assets/url_entrypoints_index_connector.png)

Selezionando una configurazione dall’elenco a discesa, il valore viene aggiunto alla fine dell’elenco dei punti di ingresso URL.

>[!NOTE]
>
>Le configurazioni disabilitate del connettore indice vengono aggiunte all’elenco a discesa, ma non è possibile selezionarle. Se selezioni una seconda volta la stessa configurazione del connettore indice, questa viene aggiunta alla fine dell&#39;elenco e l&#39;istanza precedente viene eliminata.

Per specificare un punto di ingresso del connettore indice per una ricerca per indicizzazione incrementale, è possibile aggiungere voci utilizzando il seguente formato:

```
index:<indexconnector_configuration_name>
```

Il crawler elabora ogni voce aggiunta se si trova nella pagina Connettori indice ed è abilitato.

Nota: Poiché l&#39;URL di ciascun documento è costruito utilizzando il nome di configurazione del connettore indice e la chiave primaria del documento, assicurati di utilizzare lo stesso nome di configurazione del connettore indice durante l&#39;esecuzione degli aggiornamenti incrementali. In questo modo [!DNL Adobe Search&Promote] consente di aggiornare correttamente i documenti indicizzati in precedenza.

Consulta anche [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

**Utilizzo di Mappe di installazione quando si aggiunge un connettore indice**

Al momento dell&#39;aggiunta di un connettore indice, è possibile utilizzare facoltativamente la funzione **[!UICONTROL Setup Maps]** per scaricare un esempio dell&#39;origine dati. I dati vengono esaminati per verificare l&#39;idoneità all&#39;indicizzazione.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Se si sceglie il tipo di connettore indice.. </p> </th> 
   <th colname="col2" class="entry"> <p>La funzione Mappe di installazione... </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Testo </p> </td> 
   <td colname="col2"> <p>Determina il valore del delimitatore provando prima le tabulazioni e poi le barre verticali ( <span class="codeph"> | </span>) e infine virgole ( <span class="codeph"> , </span>). Se prima di fare clic su <span class="uicontrol"> Mappe di installazione </span> hai già specificato un valore di delimitazione, viene utilizzato tale valore. </p> <p>Lo schema di adattamento ottimale si traduce nella compilazione dei campi Mappa con supposizioni in base ai valori Tag e Campo appropriati. Inoltre, viene visualizzato un campione dei dati analizzati. Assicurati di selezionare <span class="uicontrol"> Intestazioni nella prima riga </span> se sai che il file include una riga di intestazione. La funzione di configurazione utilizza queste informazioni per identificare meglio le voci di mappa risultanti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Scarica l’origine dati ed esegue un’analisi XML semplice. </p> <p>Gli identificatori XPath risultanti vengono visualizzati nelle righe Tag della tabella Mappa e valori simili nei campi. Queste righe identificano solo i dati disponibili e non generano le definizioni XPath più complesse. Tuttavia, è ancora utile perché descrive i dati XML e identifica i valori degli elementi tag. </p> <p> <p>Nota:  La funzione Mappe di installazione scarica l'intera sorgente XML per eseguire la sua analisi. Se il file è di grandi dimensioni, l'operazione potrebbe scadere. </p> </p> <p>In caso di esito positivo, questa funzione identifica tutti gli elementi XPath possibili, molti dei quali non sono desiderabili da utilizzare. Esamina le definizioni di mappa risultanti e rimuovi quelle che non sono necessarie o che desideri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XML </p> </td> 
   <td colname="col2"> <p>Scarica l’URL di un singolo documento rappresentativo, non l’elenco di collegamenti principale. Questo singolo documento viene analizzato utilizzando lo stesso meccanismo utilizzato con i feed, e i risultati vengono visualizzati. </p> <p>Prima di fare clic su <span class="uicontrol"> Aggiungi </span> per salvare la configurazione, assicurati di ripristinare l’URL nel documento dell’elenco dei collegamenti principali. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Importante**: La funzione Mappe di installazione potrebbe non funzionare per set di dati XML di grandi dimensioni perché il relativo parser di file tenta di leggere l&#39;intero file in memoria. Di conseguenza, potresti riscontrare una condizione di memoria esaurita. Tuttavia, quando lo stesso documento viene elaborato al momento dell&#39;indicizzazione, non viene letto in memoria. Al contrario, i documenti di grandi dimensioni vengono elaborati &quot;in movimento&quot; e non vengono letti interamente in memoria prima.

**Uso dell&#39;anteprima quando si aggiunge un connettore indice**

Al momento di aggiungere un connettore indice, è possibile utilizzare facoltativamente la funzione **[!UICONTROL Preview]** per convalidare i dati, come se li si stesse salvando. Esegue un test sulla configurazione, ma senza salvare la configurazione nell&#39;account. Il test accede all’origine dati configurata. Tuttavia, scrive la cache di download in una posizione temporanea; non è in conflitto con la cartella cache principale utilizzata dal crawler per l’indicizzazione.

Preview elabora solo un predefinito di cinque documenti come controllato da Acct:IndexConnector-Preview-Max-Documents. I documenti visualizzati in anteprima vengono visualizzati nel modulo di origine, in quanto vengono presentati al crawler di indicizzazione. La visualizzazione è simile alla funzione &quot;Visualizza origine&quot; di un browser Web. Puoi navigare nei documenti del set di anteprima utilizzando collegamenti di navigazione standard.

L&#39;anteprima non supporta le configurazioni XML perché tali documenti vengono elaborati direttamente e non scaricati nella cache.

## Aggiunta di una definizione del connettore indice {#task_96779B651A654E1F871F55D6DBBC8886}

Ogni configurazione del connettore indice definisce un’origine dati e le mappature per collegare gli elementi dati definiti per tale origine ai campi di metadati nell’indice.

Prima che gli effetti della nuova definizione abilitata siano visibili ai clienti, ricostruisci l&#39;indice del sito.

**Per aggiungere una definizione del connettore indice**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella pagina [!DNL Stage Index Connector Definitions], fai clic su **[!UICONTROL Add New Index Connector]**.
1. Nella pagina [!DNL Index Connector Add] , imposta le opzioni del connettore desiderate. Le opzioni disponibili dipendono dal **[!UICONTROL Type]** selezionato.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Nome univoco della configurazione del connettore indice. È possibile utilizzare caratteri alfanumerici. Sono consentiti anche i caratteri "_" e "-". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> <p>Origine dei dati. Il tipo di origine dati selezionato influisce sulle opzioni risultanti disponibili nella pagina <span class="wintitle"> Connettore indice Aggiungi </span> . Puoi scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Testo </span> <p>File di testo semplici, delimitati da virgole, delimitati da tabulazioni o altri formati delimitati in modo coerente. Ogni riga di testo delimitata da una nuova riga corrisponde a un singolo documento ed è analizzata utilizzando il delimitatore specificato. </p> <p>Puoi mappare ogni valore, o colonna, su un campo di metadati, a cui fa riferimento il numero di colonna, a partire da 1 (uno). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Scarica un documento XML primario contenente più "righe" di informazioni. </p> </li> 
      <li id="li_5A61C53522D74D4C9A5F65989604BDEF"> <span class="uicontrol"> XML  </span> <p>Scarica un documento XML primario contenente collegamenti ( 
      <code>
        &lt;a&gt; 
      </code>) a singoli documenti XML. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo di origine dati: Testo</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per eseguire ricerche per indicizzazione e indicizzazione. Oppure, puoi disattivare la configurazione per impedire la ricerca per indicizzazione e indicizzazione. </p> <p> <b>Nota</b>: Le configurazioni del connettore indice disabilitato vengono ignorate se si trovano in un elenco di punti di ingresso. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo dell'host del server in cui si trovano i dati. </p> <p>Se lo desideri, puoi specificare un percorso URI completo (Uniform Resource Identifier) per il documento dell’origine dati, come negli esempi seguenti: </p> <p> <code> https://www.somewhere.com/some_path/some_file.xml </code> </p> <p> oppure  </p> <p> <code> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.xml </code> </p> <p>L’URI viene suddiviso nelle voci appropriate per i campi Indirizzo host, Percorso file, Protocollo e, facoltativamente, Nome utente e Password. </p> <p>Specifica l'indirizzo IP o l'indirizzo URL del sistema host in cui viene trovato il file di origine dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del file di testo semplice, delimitato da virgole, delimitato da tabulazioni o in un altro file di formato delimitato in modo coerente. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file incrementale </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del file di testo semplice, delimitato da virgole, delimitato da tabulazioni o in un altro file di formato delimitato in modo coerente. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni Incremental Index. Se non viene specificato alcun file, viene invece utilizzato il file elencato in Percorso file. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file verticale </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del file di testo semplice, delimitato da virgole, delimitato da tabulazioni o di altro file di formato delimitato in modo coerente da essere utilizzato durante un aggiornamento verticale. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni di aggiornamento verticale. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivare la funzione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elimina percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del file di testo semplice e semplice, contenente un singolo valore di identificatore del documento per riga. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni Incremental Index. I valori trovati in questo file vengono utilizzati per costruire richieste di "eliminazione" per rimuovere documenti precedentemente indicizzati. I valori in questo file devono corrispondere ai valori trovati nei file Percorso file completo o incrementale, nella colonna identificata come Chiave primaria <span class="uicontrol"> </span>. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivare la funzione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Puoi scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTP. </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTPS. </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server FTP. </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server SFTP. </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> File </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Timeout </p> </td> 
      <td colname="col2"> <p>Specifica il timeout, in secondi, per le connessioni FTP, SFTP, HTTP o HTTPS. Questo valore deve essere compreso tra 30 e 300. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nuovi tentativi </p> </td> 
      <td colname="col2"> <p>Specifica il numero massimo di tentativi per connessioni FTP, SFTP, HTTP o HTTPS non riuscite. Questo valore deve essere compreso tra 0 e 10. </p> <p>Un valore pari a zero (0) impedirà i tentativi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Codifica </p> </td> 
      <td colname="col2"> <p>Specifica il sistema di codifica dei caratteri utilizzato nel file di origine dati specificato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimitatore </p> </td> 
      <td colname="col2"> <p>Specifica il carattere da utilizzare per delineare ogni campo nel file di origine dati specificato. </p> <p>La virgola ( <span class="codeph"> , </span>) è un esempio di delimitatore. La virgola funge da delimitatore di campo che consente di separare i campi dati nel file di origine dati specificato. </p> <p>Selezionare la scheda <span class="uicontrol">? </span> per utilizzare il carattere di tabulazione orizzontale come delimitatore. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Intestazioni nella prima riga </p> </td> 
      <td colname="col2"> <p>Indica che la prima riga del file di origine dati contiene solo informazioni di intestazione, non dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero minimo di documenti per l'indicizzazione </p> </td> 
      <td colname="col2"> <p>Se è impostato su un valore positivo, questo specifica il numero minimo di record previsti nel file scaricato. Se vengono ricevuti meno record, l'operazione di indicizzazione viene interrotta. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivare la funzione. </p> <p> <b>Nota</b>: Questa funzione viene utilizzata solo durante le operazioni dell'indice completo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Specifica le mappature da colonna a metadati utilizzando i numeri di colonna. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Colonna </span> <p> Specifica un numero di colonna, con la prima colonna pari a 1 (una). Per aggiungere nuove righe della mappa per ogni colonna, in <span class="wintitle"> Azione </span>, fai clic su <span class="uicontrol"> + </span>. </p> <p>Non è necessario fare riferimento a ciascuna colonna nell’origine dati. È invece possibile scegliere di saltare i valori. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag &lt;meta&gt; generato. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che il campo <span class="uicontrol"> </span> diventi un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l’account corrente. </p> <p>Il valore del campo <span class="uicontrol"> </span> può essere un campo di metadati non definito, se necessario. Un campo di metadati non definito è talvolta utile per creare contenuti utilizzati da <span class="wintitle"> Script di filtro </span>. </p> <p>Consultare <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni sul filtro degli script </a>. </p> <p>Quando il connettore indice elabora documenti XML con più hit su qualsiasi campo mappa, i più valori vengono concatenati in un singolo valore nel documento memorizzato nella cache risultante. Per impostazione predefinita, questi valori vengono combinati utilizzando un delimitatore virgola. Supponiamo tuttavia che il valore corrispondente del campo <span class="wintitle"> </span> sia un campo metadati definito. Inoltre, per quel campo è impostato l'attributo <span class="wintitle"> Elenchi consentiti </span> . In questo caso, il valore Delimitatori elenco del campo, che è il primo delimitatore definito, viene utilizzato nella concatenazione. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Chiave principale?  </span> <p>Solo una definizione di mappa è identificata come chiave primaria. Questo campo diventa il riferimento univoco presentato quando il documento viene aggiunto all'indice. Questo valore viene utilizzato nell’URL del documento nell’indice. </p> <p>I valori <span class="uicontrol"> Chiave primaria </span> devono essere univoci in tutti i documenti rappresentati dalla configurazione del connettore indice. Eventuali duplicati rilevati verranno ignorati. Se i documenti di origine non contengono un singolo valore univoco da utilizzare come <span class="uicontrol"> Chiave primaria </span>, ma due o più campi insieme <i>possono</i> formare un identificatore univoco, puoi definire la <span class="uicontrol"> Chiave primaria </span> combinando più valori <span class="uicontrol"> Colonna </span> con una barra verticale ("|") che delimitano i valori. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> Striscia HTML?  </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo di origine dati: Feed</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per eseguire ricerche per indicizzazione e indicizzazione. Oppure, puoi disattivare la configurazione per impedire la ricerca per indicizzazione e indicizzazione. </p> <p> <b>Nota</b>: Le configurazioni del connettore indice disabilitato vengono ignorate se si trovano in un elenco di punti di ingresso. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo IP o l'indirizzo URL del sistema host in cui viene trovato il file di origine dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML primario contenente più "righe" di informazioni. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file incrementale </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML incrementale contenente più "righe" di informazioni. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni Incremental Index. Se non viene specificato alcun file, viene invece utilizzato il file elencato in Percorso file. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file verticale </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML contenente più "righe" di informazioni sparse da utilizzare durante un aggiornamento verticale. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni di aggiornamento verticale. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivare la funzione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elimina percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del file di testo semplice e semplice, contenente un singolo valore di identificatore del documento per riga. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni Incremental Index. I valori trovati in questo file vengono utilizzati per costruire richieste di "eliminazione" per rimuovere documenti precedentemente indicizzati. I valori in questo file devono corrispondere ai valori trovati nei file Percorso file completo o incrementale, nella colonna identificata come Chiave primaria <span class="uicontrol"> </span>. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivare la funzione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Puoi scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTP. </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTPS. </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server FTP. </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server SFTP. </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> File </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elemento </p> </td> 
      <td colname="col2"> <p>Identifica l'elemento XML che è possibile utilizzare per identificare singole righe XML nel file di origine dati specificato. </p> <p>Ad esempio, nel seguente frammento Feed di un documento XML di Adobe, il valore del tag elemento è <span class="codeph"> record </span>: </p> <p> <code> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt;&lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt;         &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt;         &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt;         &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
        &lt;/record&gt; 
        ... 
        &lt;record&gt; 
        ... 
        &lt;/record&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/group&gt; 
        &lt;/gsafeed&gt; 
        </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero minimo di documenti per l'indicizzazione </p> </td> 
      <td colname="col2"> <p>Se è impostato su un valore positivo, questo specifica il numero minimo di record previsti nel file scaricato. Se vengono ricevuti meno record, l'operazione di indicizzazione viene interrotta. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivare la funzione. </p> <p> <b>Nota</b>: Questa funzione viene utilizzata solo durante le operazioni dell'indice completo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Consente di specificare le mappature XML da elemento a metadati utilizzando le espressioni XPath. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tag </span> <p>Specifica una rappresentazione XPath dei dati XML analizzati. Utilizzando l'esempio di documento XML di Adobe sopra, sotto l'opzione Tag elemento, può essere mappato utilizzando la seguente sintassi: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
      /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>La sintassi di cui sopra si traduce come segue: </p> <p> 
      <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
      <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>L'attributo <span class="codeph"> displayurl </span> del record <span class="codeph"> </span> viene mappato sul campo metadati <span class="codeph"> page-url </span>. </p> </li> 
      <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi elemento <span class="codeph"> meta </span> contenuto all'interno di un elemento <span class="codeph"> metadati </span> contenuto all'interno di un elemento <span class="codeph"> record </span>, il cui attributo name è <span class="codeph"> titolo </span>, viene mappato sul campo metadati <span class="codeph"> titolo </span> </p> </li> 
      <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi elemento <span class="codeph"> meta </span> contenuto all'interno di un elemento <span class="codeph"> metadati </span> contenuto all'interno del record <span class="codeph"> </span>, il cui attributo name è <span class="codeph"> descrizione </span>, è mappato al campo metadati <span class="codeph"> desc </span> </p> </li> 
      <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi elemento <span class="codeph"> meta </span> contenuto all'interno di un elemento <span class="codeph"> metadati </span> contenuto nel record <span class="codeph"> </span>, il cui attributo name è <span class="codeph"> descrizione </span>, viene mappato sul campo metadati <span class="codeph"> corpo </span> </p> </li> 
      </ul> </p> <p>XPath è una notazione relativamente complicata. Ulteriori informazioni sono disponibili nel seguente percorso: </p> <p>Vedere <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag <span class="codeph"> &lt;meta&gt; </span> generato. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che il campo <span class="uicontrol"> </span> diventi un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l’account corrente. </p> <p>Il valore del campo <span class="uicontrol"> </span> può essere un campo di metadati non definito, se necessario. Un campo di metadati non definito è talvolta utile per creare contenuti utilizzati da <span class="wintitle"> Script di filtro </span>. </p> <p>Consultare <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni sul filtro degli script </a>. </p> <p>Quando il connettore indice elabora documenti XML con più hit su qualsiasi campo mappa, i più valori vengono concatenati in un singolo valore nel documento memorizzato nella cache risultante. Per impostazione predefinita, questi valori vengono combinati utilizzando un delimitatore virgola. Supponiamo tuttavia che il valore corrispondente del campo <span class="wintitle"> </span> sia un campo metadati definito. Inoltre, per quel campo è impostato l'attributo <span class="wintitle"> Elenchi consentiti </span> . In questo caso, il valore Delimitatori elenco del campo, che è il primo delimitatore definito, viene utilizzato nella concatenazione. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Chiave principale?  </span> <p>Solo una definizione di mappa è identificata come chiave primaria. Questo campo diventa il riferimento univoco presentato quando il documento viene aggiunto all'indice. Questo valore viene utilizzato nell’URL del documento nell’indice. </p> <p>I valori <span class="uicontrol"> Chiave primaria </span> devono essere univoci in tutti i documenti rappresentati dalla configurazione del connettore indice. Eventuali duplicati rilevati verranno ignorati. Se i documenti di origine non contengono un singolo valore univoco da utilizzare come <span class="uicontrol"> Chiave primaria </span>, ma due o più campi insieme <i>possono</i> formare un identificatore univoco, puoi definire la <span class="uicontrol"> Chiave primaria </span> combinando più definizioni <span class="uicontrol"> Tag </span> con una barra verticale ("|") che delimitano i valori. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC81F"> <span class="uicontrol"> Striscia HTML?  </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_5E829D1D0DBD4BB7AAB5DB983053D248"> <span class="uicontrol"> Utilizzare per eliminare?  </span> <p>Utilizzato solo durante le operazioni dell'indice incrementale. I record che corrispondono a questo modello XPath identificano gli elementi da eliminare. Il valore <span class="uicontrol"> Chiave primaria </span> per ogni record di questo tipo viene utilizzato per costruire richieste di "cancellazione", come con Elimina percorso file. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivare la funzione. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo di origine dati: XML</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per eseguire ricerche per indicizzazione e indicizzazione. Oppure, puoi disattivare la configurazione per impedire la ricerca per indicizzazione e indicizzazione. </p> <p> <b>Nota</b>: Le configurazioni del connettore indice disabilitato vengono ignorate se si trovano in un elenco di punti di ingresso. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo URL del sistema host in cui viene trovato il file di origine dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML principale contenente i collegamenti ( 
      <code>
        &lt;a&gt; 
      </code>) a singoli documenti XML. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Puoi scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_EA4EB7953D68483FAD75753B2EE70E74"> 
      <li id="li_537F24C6B2AB435CB7C14117663D7B3F"> HTTP <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTP. </p> </li> 
      <li id="li_8C13C93C52364FFA8B9B18830CDB223C"> HTTPS <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTPS. </p> </li> 
      <li id="li_2F967B5675254C949B31EAB19910751C"> FTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server FTP. </p> </li> 
      <li id="li_C24BE4C1DE79488AA64C7133D78CD3A6"> SFTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server SFTP. </p> </li> 
      <li id="li_7581C21CFC104986A361F62BD7A370C1"> File </li> 
      </ul> </p> <p> <b>Nota</b>: L'impostazione Protocol viene utilizzata solo quando sono presenti informazioni specificate nei campi Indirizzo host e/o Percorso file . I singoli documenti XML vengono scaricati tramite HTTP o HTTPS, in base alle relative specifiche URL. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elemento </p> </td> 
      <td colname="col2"> <p>Identifica l'elemento XML che definisce una "riga" nel file di origine dati specificato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Consente di specificare le mappature da colonna a metadati utilizzando i numeri di colonna. </p> <p> 
      <ul id="ul_06F50CBA0AA64C7CB1AFAE076E629A64"> 
      <li id="li_0FA2502869BA40DC93D790B79E15A9D2"> <span class="uicontrol"> Tag  </span> <p>Specifica una rappresentazione XPath dei dati XML analizzati. Utilizzando l’esempio di documento XML di Adobe riportato sopra, sotto l’opzione Tag elemento, è possibile mapparlo utilizzando la seguente sintassi: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>La sintassi di cui sopra si traduce come segue: </p> <p> 
      <ul id="ul_F8C536E6E54546D9AA5B22B879C0AF39"> 
      <li id="li_78A35DFFF1B4496CAC6EDC7B1E991F29"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>L'attributo <span class="codeph"> displayurl </span> del record <span class="codeph"> </span> viene mappato sul campo metadati <span class="codeph"> page-url </span>. </p> </li> 
      <li id="li_FA7DF3D1942248B98660F3D0C82F4563"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi elemento <span class="codeph"> meta </span> contenuto all'interno di un elemento <span class="codeph"> metadati </span> contenuto all'interno di un elemento <span class="codeph"> record </span>, il cui attributo name è <span class="codeph"> titolo </span>, viene mappato sul campo metadati <span class="codeph"> titolo </span> </p> </li> 
      <li id="li_D8000A116FF84DE59ED19C656DDD3BC1"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi elemento <span class="codeph"> meta </span> contenuto all'interno di un elemento <span class="codeph"> metadati </span> contenuto all'interno del record <span class="codeph"> </span>, il cui attributo name è <span class="codeph"> descrizione </span>, è mappato al campo metadati <span class="codeph"> desc </span> </p> </li> 
      <li id="li_7FA6A53DFD3D42A98B7BA17CC29DDB81"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi elemento <span class="codeph"> meta </span> contenuto all'interno di un elemento <span class="codeph"> metadati </span> contenuto nel record <span class="codeph"> </span>, il cui attributo name è <span class="codeph"> descrizione </span>, viene mappato sul campo metadati <span class="codeph"> corpo </span> </p> </li> 
      </ul> </p> <p>XPath è una notazione relativamente complicata. Ulteriori informazioni sono disponibili nel seguente percorso: </p> <p>Vedere <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_84999D07E0AE4265BC7928BBB49957B9"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag &lt;meta&gt; generato. </p> </li> 
      <li id="li_E125788D0F5242958BD790E26A675C20"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che il campo <span class="uicontrol"> </span> diventi un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l’account corrente. </p> <p>Il valore del campo <span class="uicontrol"> </span> può essere un campo di metadati non definito, se necessario. Un campo di metadati non definito è talvolta utile per creare contenuti utilizzati da <span class="wintitle"> Script di filtro </span>. </p> <p>Consultare <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni sul filtro degli script </a>. </p> <p>Quando il connettore indice elabora documenti XML con più hit su qualsiasi campo mappa, i più valori vengono concatenati in un singolo valore nel documento memorizzato nella cache risultante. Per impostazione predefinita, questi valori vengono combinati utilizzando un delimitatore virgola. Supponiamo tuttavia che il valore corrispondente del campo <span class="wintitle"> </span> sia un campo metadati definito. Inoltre, per quel campo è impostato l'attributo <span class="wintitle"> Elenchi consentiti </span> . In questo caso, il valore Delimitatori elenco del campo, che è il primo delimitatore definito, viene utilizzato nella concatenazione. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824609F"> <span class="uicontrol"> Chiave principale?  </span> <p>Solo una definizione di mappa è identificata come chiave primaria. Questo campo diventa il riferimento univoco presentato quando il documento viene aggiunto all'indice. Questo valore viene utilizzato nell’URL del documento nell’indice. </p> <p>I valori <span class="uicontrol"> Chiave primaria </span> devono essere univoci in tutti i documenti rappresentati dalla configurazione del connettore indice. Eventuali duplicati rilevati verranno ignorati. Se i documenti di origine non contengono un singolo valore univoco da utilizzare come <span class="uicontrol"> Chiave primaria </span>, ma due o più campi insieme <i>possono</i> formare un identificatore univoco, puoi definire la <span class="uicontrol"> Chiave primaria </span> combinando più definizioni <span class="uicontrol"> Tag </span> con una barra verticale ("|") che delimitano i valori. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824610G"> <span class="uicontrol"> Striscia HTML?  </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_6302D18971AD439FBECE27742649C56B"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Fai clic su **[!UICONTROL Setup Maps]** per scaricare un esempio dell’origine dati. I dati vengono esaminati per verificare l&#39;idoneità all&#39;indicizzazione. Questa funzione è disponibile solo per i tipi di testo e feed.
1. (Facoltativo) Fai clic su **[!UICONTROL Preview]** per verificare il funzionamento effettivo della configurazione. Questa funzione è disponibile solo per i tipi di testo e feed.
1. Fai clic su **[!UICONTROL Add]** per aggiungere la configurazione alla pagina [!DNL Index Connector Definitions] e all’elenco a discesa [!DNL Index Connector Configurations] nella pagina [!DNL URL Entrypoints].

   Consulta [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).
1. Nella pagina [!DNL Index Connector Definitions], fai clic su **[!UICONTROL rebuild your staged site index]**.
1. (Facoltativo) Nella pagina [!DNL Index Connector Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica della definizione del connettore indice {#task_DCFC9C6A9964421DB5AB6C25DEE98DE9}

Puoi modificare un connettore indice esistente definito.

>[!NOTE]
>
>Non tutte le opzioni sono disponibili per la modifica, ad esempio Nome connettore indice o Tipo dall&#39;elenco a discesa [!DNL Type].

**Per modificare una definizione del connettore indice**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella pagina [!DNL Index Connector], sotto l&#39;intestazione della colonna [!DNL Actions], fare clic su **[!UICONTROL Edit]** per il nome di una definizione del connettore indice di cui si desidera modificare le impostazioni.
1. Nella pagina [!DNL Index Connector Edit] , imposta le opzioni desiderate.

   Vedi la tabella delle opzioni in [Aggiunta di una definizione del connettore indice](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella pagina [!DNL Index Connector Definitions], fai clic su **[!UICONTROL rebuild your staged site index]**.
1. (Facoltativo) Nella pagina [!DNL Index Connector Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Visualizzazione delle impostazioni di una definizione del connettore indice {#task_D0B71A7426E54247BDB3468EC576D871}

Puoi controllare le impostazioni di configurazione di una definizione di connettore indice esistente.

Dopo aver aggiunto una definizione del connettore indice alla pagina [!DNL Index Connector Definitions], non è possibile modificarne l&#39;impostazione Tipo. È invece necessario eliminare la definizione e aggiungerne una nuova.

**Per visualizzare le impostazioni di una definizione del connettore indice**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella pagina [!DNL Index Connector], sotto l&#39;intestazione della colonna [!DNL Actions], fare clic su **[!UICONTROL Edit]** per il nome di una definizione del connettore indice di cui si desidera esaminare o modificare le impostazioni.

## Copia della definizione di un connettore indice {#task_3AD55DF07FC44A748D0EFDAB7B35699B}

È possibile copiare una definizione del connettore indice esistente da utilizzare come base per un nuovo connettore indice che si desidera creare.

Quando copi una definizione del connettore indice, la definizione copiata viene disabilitata per impostazione predefinita. Per abilitare o &quot;attivare&quot; la definizione, è necessario modificarla dalla pagina [!DNL Index Connector Edit] e selezionare **[!UICONTROL Enable]**.

Vedere [Modifica della definizione di un connettore indice](../c-about-settings-menu/c-about-crawling-menu.md#task_DCFC9C6A9964421DB5AB6C25DEE98DE9).

**Per copiare una definizione del connettore indice**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella pagina [!DNL Index Connector], sotto l&#39;intestazione della colonna [!DNL Actions], fare clic su **[!UICONTROL Copy]** per il nome di una definizione del connettore indice di cui si desidera duplicare le impostazioni.
1. Nella pagina [!DNL Index Connector Copy] , immetti il nuovo nome della definizione.
1. Clic **[!UICONTROL Copy]**.
1. (Facoltativo) Nella pagina [!DNL Index Connector Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ridenominazione della definizione del connettore indice {#task_5132118FC21B47D99881E0ED425225D7}

È possibile modificare il nome di una definizione del connettore indice esistente.

Dopo aver rinominato la definizione, seleziona **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Assicurati che il nuovo nome della definizione sia riportato nell&#39;elenco a discesa della pagina [!DNL URL Entrypoints].

Consulta [Aggiunta di più punti di ingresso URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

**Per rinominare una definizione del connettore indice**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella pagina [!DNL Index Connector], sotto l&#39;intestazione della colonna [!DNL Actions], fare clic su **[!UICONTROL Rename]** per il nome della definizione del connettore indice che si desidera modificare.
1. Nella pagina [!DNL Index Connector Rename] , immetti il nuovo nome della definizione nel campo [!DNL Name] .
1. Clic **[!UICONTROL Rename]**.
1. Fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Se nell&#39;elenco è presente il nome del connettore indice precedente, rimuoverlo e aggiungere la voce appena rinominata.

   Consulta [Aggiunta di più punti di ingresso URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45). 1. (Facoltativo) Nella pagina [!DNL Index Connector Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una definizione del connettore indice {#task_6B0BD5D0C09F4597A401B0F3AC7C7EA7}

È possibile eliminare una definizione del connettore indice esistente che non è più necessaria o utilizzata.

**Per eliminare una definizione del connettore indice**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella pagina [!DNL Index Connector Definitions], sotto l&#39;intestazione di colonna [!DNL Actions], fare clic su **[!UICONTROL Delete]** per il nome di definizione del connettore indice che si desidera rimuovere.
1. Nella pagina [!DNL Index Connector Delete], fai clic su **[!UICONTROL Delete]**.
