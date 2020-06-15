---
description: Utilizzare la data e le maschere URL del set di menu di ricerca per indicizzazione, le password, i tipi di contenuto, le connessioni, le definizioni dei moduli e i punti di ingresso URL.
seo-description: Utilizzare la data e le maschere URL del set di menu di ricerca per indicizzazione, le password, i tipi di contenuto, le connessioni, le definizioni dei moduli e i punti di ingresso URL.
seo-title: Informazioni sul menu di ricerca per indicizzazione
solution: Target
subtopic: Crawling
title: Informazioni sul menu di ricerca per indicizzazione
topic: Settings,Site search and merchandising
uuid: a58c03bf-90f7-4b5b-91ff-988b95c246b0
translation-type: tm+mt
source-git-commit: e080a61e24a3809beff7c212ff3d088b2a8ad3b6
workflow-type: tm+mt
source-wordcount: '11115'
ht-degree: 0%

---


# Informazioni sul menu di ricerca per indicizzazione{#about-the-crawling-menu}

Utilizzare la data e le maschere URL del set di menu di ricerca per indicizzazione, le password, i tipi di contenuto, le connessioni, le definizioni dei moduli e i punti di ingresso URL.

## Informazioni sui punti di ingresso URL {#concept_5D857E3B5C124E85BC0B5AE77A509573}

La maggior parte dei siti Web ha un punto di ingresso principale o una home page che il cliente visita inizialmente. Questo punto di ingresso principale è l&#39;indirizzo URL dal quale il robot di ricerca inizia la ricerca per indicizzazione. Tuttavia, se il sito Web contiene più domini o sottodomini oppure se parti del sito non sono collegate dal punto di ingresso principale, potete utilizzare i punti di ingresso URL per aggiungere altri punti di ingresso.

Vengono indicizzate tutte le pagine del sito Web al di sotto di ciascun punto di ingresso URL specificato. Potete combinare punti di immissione URL con maschere per controllare esattamente quali porzioni di un sito Web volete indicizzare. È necessario rigenerare l’indice del sito Web prima che gli effetti delle impostazioni dei punti di accesso URL siano visibili ai clienti.

Il punto di ingresso principale è in genere l’URL del sito Web che si desidera indicizzare e cercare. Questo punto di ingresso principale viene configurato in Impostazioni account.

Consultate [Configurazione delle impostazioni](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)dell’account.

Dopo aver specificato il punto di ingresso dell’URL principale, potete specificare facoltativamente altri punti di ingresso che desiderate spostare per indicizzazione in ordine. Nella maggior parte dei casi si specificano punti di ingresso aggiuntivi per le pagine Web che non sono collegate da pagine sotto il punto di ingresso principale. Specificate punti di ingresso aggiuntivi quando il sito Web si estende su più domini, come nell’esempio seguente:

`https://www.domain.com/`

`https://www.domain.com/not_linked/but_search_me_too/`

`https://more.domain.com/`

È possibile assegnare a ciascun punto di ingresso una o più delle seguenti parole chiave separate da spazi nella tabella seguente. Queste parole chiave influiscono sulla modalità di indicizzazione della pagina.

**Importante**: Assicurarsi di separare una determinata parola chiave dal punto di ingresso e l&#39;una dall&#39;altra tramite uno spazio; una virgola non è un separatore valido.

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
     <userinput>
       noindex 
     </userinput> dopo il punto di ingresso. </p> <p>Separate la parola chiave dal punto di ingresso con uno spazio come nell'esempio seguente: </p> <p> <code> https://www.my-additional-domain.com/more_pages/main.html&amp;nbsp;noindex </code> </p> <p>Questa parola chiave equivale a un tag meta robot con 
     <userinput>
       content="noindex" 
     </userinput>) tra 
     <userinput>
       &lt;head&gt; 
     </userinput>... 
     <userinput>
       &lt;/head&gt; 
     </userinput> tag della pagina del punto di ingresso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Se si desidera indicizzare il testo nella pagina del punto di ingresso ma non si desidera seguire i collegamenti della pagina, aggiungere 
     <userinput>
       nofollow 
     </userinput> dopo il punto di ingresso. </p> <p>Separate la parola chiave dal punto di ingresso con uno spazio come nell'esempio seguente: </p> <p> <code> https://www.domain.com/not_linked/directory_listing&amp;nbsp;nofollow </code> </p> <p>Questa parola chiave equivale a un tag meta robot con 
     <userinput>
       content="nofollow" 
     </userinput> tra 
     <userinput>
       &lt;head&gt; 
     </userinput>... 
     <userinput>
       &lt;/head&gt; 
     </userinput> tag di una pagina punto di ingresso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>form </p> </td> 
   <td colname="col2"> <p> Quando il punto di ingresso è una pagina di login, 
     <userinput>
       form 
     </userinput> viene in genere utilizzato in modo che il robot di ricerca possa inviare il modulo di login e ricevere i cookie appropriati prima di eseguire il crawling del sito Web. Quando si utilizza la parola chiave "form", la pagina del punto di ingresso non viene indicizzata e il robot di ricerca non contrassegna la pagina del punto di ingresso come sottoposta a ricerca per indicizzazione. Usa la 
     <userinput>
       nofollow 
     </userinput> se non si desidera che il robot di ricerca segua i collegamenti della pagina. </p> </td> 
  </tr> 
 </tbody> 
</table>

Consultate anche [I tipi](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)di contenuto.

Vedere anche [Informazioni sul connettore](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)indice.

## Aggiunta di più punti di ingresso URL da indicizzare {#task_2338A47387D74CFDAC4D4EF4A367ED45}

Se il sito Web contiene più domini o sottodomini e desiderate che vengano sottoposti a ricerca per indicizzazione, potete utilizzare i punti di ingresso URL per aggiungere altri URL.

Per impostare il punto di accesso dell&#39;URL principale del sito Web, utilizzate le Impostazioni account.

Consultate [Configurazione delle impostazioni](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)dell’account.

**Per aggiungere più punti di ingresso URL da indicizzare**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**.
1. Nella [!DNL URL Entrypoints] pagina, nel [!DNL Entrypoints] campo, immettete un indirizzo URL per riga.
1. (Facoltativo) Nell&#39;elenco a **[!UICONTROL Add Index Connector Configurations]** discesa, selezionare un connettore indice da aggiungere come punto di ingresso per l&#39;indicizzazione.

   L&#39;elenco a discesa è disponibile solo se in precedenza sono state aggiunte una o più definizioni di connettore indice.

   ![](assets/url_entrypoints_index_connector.png)

   Vedere [Aggiunta di una definizione](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886)del connettore indice.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Le maschere URL {#concept_8039DFC53FF3410AA494D602F71BA164}

Le maschere URL sono modelli che determinano quale dei vostri siti Web documenta gli indici dei robot di ricerca o meno.

Assicuratevi di rigenerare l’indice del sito in modo che i risultati delle maschere URL siano visibili ai clienti.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

Di seguito sono riportati due tipi di maschere URL utilizzabili:

* Includi maschere URL
* Escludere le maschere URL

L&#39;inclusione di maschere URL indica al robot di ricerca di indicizzare qualsiasi documento che corrisponda al pattern della maschera.

Le maschere URL di esclusione indicano al robot di ricerca di indicizzare i documenti corrispondenti.

Mentre il robot di ricerca viaggia da un collegamento a un collegamento attraverso il sito Web, incontra gli URL e cerca le maschere che corrispondono a tali URL. La prima corrispondenza determina se includere o escludere tale URL dall’indice. Se nessuna maschera corrisponde a un URL rilevato, tale URL viene eliminato dall&#39;indice.

Includi maschere URL per gli URL del punto di ingresso vengono generati automaticamente. In questo modo tutti i documenti presenti sul sito Web verranno indicizzati. Comodamente si elimina anche con i link che &quot;lasciano&quot; il tuo sito web. Ad esempio, se una pagina indicizzata si collega a https://www.yahoo.com, il robot di ricerca non indicizza tale URL perché non corrisponde alla maschera di inclusione generata automaticamente dall’URL del punto di ingresso.

Ogni maschera URL specificata deve trovarsi su una riga separata.

La maschera può specificare una delle seguenti opzioni:

* Un percorso completo come in `https://www.mydomain.com/products.html`.
* Un percorso parziale come in `https://www.mydomain.com/products`.
* URL che utilizza caratteri jolly come in `https://www.mydomain.com/*.html`.
* Un&#39;espressione regolare (per utenti avanzati).

   Per rendere una maschera un&#39;espressione regolare, inserite la parola chiave `regexp` tra il tipo di maschera ( `exclude` o `include`) e la maschera URL.

Di seguito è riportato un semplice esempio di maschera di esclusione URL:

```
exclude https://www.mydomain.com/photos
```

Poiché questo esempio è una maschera URL di esclusione, qualsiasi documento che corrisponda al pattern non viene indicizzato. Il pattern corrisponde a qualsiasi elemento rilevato, sia file che cartelle, in modo che `https://www.mydomain.com/photos.html` e `https://www.mydomain.com/photos/index.html`, entrambi corrispondenti all&#39;URL di esclusione, non siano indicizzati. Per far corrispondere solo i file nella `/photos/` cartella, la maschera URL deve contenere una barra finale, come nell’esempio seguente:

```
exclude https://www.mydomain.com/photos/
```

L&#39;esempio di maschera di esclusione seguente utilizza una carattere jolly. Indica al robot di ricerca di ignorare i file con l&#39;estensione &quot;.pdf&quot;. Il robot di ricerca non aggiunge questi file all&#39;indice.

```
exclude *.pdf
```

Una semplice maschera URL include è la seguente:

```
include https://www.mydomain.com/news/
```

Vengono indicizzati solo i documenti collegati tramite una serie di collegamenti da un punto di ingresso dell’URL o utilizzati come punto di ingresso dell’URL. L&#39;elenco esclusivo dell&#39;URL di un documento come maschera URL inclusa non indicizza alcun documento non collegato. Per aggiungere documenti non collegati all’indice, potete usare la funzione Punti di ingresso URL.

Consultate [I punti di ingresso](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)URL.

L’inclusione di maschere e l’esclusione di maschere possono funzionare insieme. Potete escludere un’ampia parte del sito Web dall’indicizzazione creando una maschera URL esclusa e tuttavia includendo una o più delle pagine escluse con una maschera URL inclusa. Ad esempio, supponete che l’URL del punto di ingresso sia il seguente:

```
https://www.mydomain.com/photos/
```

Il robot di ricerca si sposta per indicizzazione e indicizza tutte le pagine sotto `/photos/summer/`, `/photos/spring/` e `/photos/fall/` (supponendo che ci siano collegamenti ad almeno una pagina in ogni directory dalla `photos` cartella). Questo comportamento si verifica perché i percorsi di collegamento consentono al robot di ricerca di trovare i documenti nelle cartelle `/summer/`, `/spring/`, `/fall/`e gli URL delle cartelle e corrispondono alla maschera di inclusione generata automaticamente dall’URL del punto di ingresso.

Potete scegliere di escludere tutte le pagine della `/fall/` cartella con una maschera URL di esclusione, come nell’esempio di seguito:

```
exclude https://www.mydomain.com/photos/fall/
```

Oppure, includete solo `/photos/fall/redleaves4.html` come parte dell’indice con la seguente maschera URL:

```
include https://www.mydomain.com/photos/fall/redleaves4.html
```

Affinché i due esempi di maschera di cui sopra funzionino come previsto, la maschera di inclusione è elencata per prima, come illustrato di seguito:

```
include https://www.mydomain.com/photos/fall/redleaves4.html 
exclude https://www.mydomain.com/photos/fall/
```

Poiché il robot di ricerca segue le indicazioni nell&#39;ordine in cui sono elencate, il robot di ricerca prima include `/photos/fall/redleaves4.html`, e poi esclude il resto dei file nella `/fall` cartella.

Se le istruzioni sono specificate nel modo opposto come indicato di seguito:

```
exclude https://www.mydomain.com/photos/fall/ 
include https://www.mydomain.com/photos/fall/redleaves4.html
```

Non `/photos/fall/redleaves4.html` è incluso, anche se la maschera specifica che è incluso.

Una maschera URL che viene visualizzata per prima ha sempre la precedenza su una maschera URL che viene visualizzata successivamente nelle impostazioni della maschera. Inoltre, se il robot di ricerca rileva una pagina che corrisponde a una maschera URL di inclusione e a una maschera URL di esclusione, la maschera elencata per prima ha sempre la precedenza.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

## Utilizzo delle parole chiave con le maschere URL {#section_7609A7A6D79B482ABCA8900886541AAB}

È possibile qualificare ciascuna maschera con una o più parole chiave separate da spazi, che influiscono sulla modalità di indicizzazione delle pagine corrispondenti.

Una virgola non è valida come separatore tra la maschera e la parola chiave; potete usare solo degli spazi.

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
   <td colname="col2"> <p> Se non si desidera indicizzare il testo sulle pagine che corrispondono alla maschera URL, ma si desidera seguire i collegamenti alle pagine corrispondenti, aggiungere 
     <userinput>
       noindex 
     </userinput> dopo la maschera URL di inclusione. Separate la parola chiave dalla maschera con uno spazio, come nell’esempio di seguito: </p> <p> <code> include&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>L'esempio precedente specifica che il robot di ricerca segue tutti i collegamenti da file con 
     <userinput>
       .swf 
     </userinput> , ma disabilita l'indicizzazione di tutto il testo contenuto in tali file. </p> <p>La funzione di 
     <userinput>
       noindex 
     </userinput> è equivalente a un tag meta robot con 
     <userinput>
       content="noindex" 
     </userinput> tra 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> tag di pagine corrispondenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Se desiderate indicizzare il testo sulle pagine che corrispondono alla maschera URL, ma non desiderate seguire i collegamenti della pagina corrispondente, aggiungete 
     <userinput>
       nofollow 
     </userinput> dopo la maschera URL di inclusione. Separate la parola chiave dalla maschera con uno spazio, come nell’esempio di seguito: </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>La funzione di 
     <userinput>
       nofollow 
     </userinput> è equivalente a un tag meta robot con 
     <userinput>
       content="nofollow" 
     </userinput> tra 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> tag di pagine corrispondenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p>Utilizzata sia per includere che per escludere le maschere. </p> <p>Qualsiasi maschera URL preceduta da 
     <userinput>
       regexp 
     </userinput> è trattata come un'espressione regolare. Se il robot di ricerca rileva documenti che corrispondono a una maschera URL con espressione regolare esclusa, tali documenti non vengono indicizzati. Se il robot di ricerca rileva documenti che corrispondono a una maschera URL con espressione regolare, tali documenti vengono indicizzati. Ad esempio, supponete di disporre della seguente maschera URL: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*/products/.*\.html$ </code> </p> <p>Il robot di ricerca esclude i file corrispondenti, come 
     <userinput>
       https://www.mydomain.com/products/page1.html 
     </userinput> </p> <p>Se avevi la seguente maschera URL con espressione regolare esclusa: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*\?..*$ </code> </p> <p>Il robot di ricerca non deve includere alcun URL contenente un parametro CGI come 
     <userinput>
       https://www.mydomain.com/cgi/prog/?arg1=val1&amp;arg2=val2 
     </userinput>. </p> <p>Se avete avuto i seguenti elementi includere una maschera URL con espressione regolare: </p> <p> <code> include&amp;nbsp;regexp&amp;nbsp;^.*\.swf$&amp;nbsp;noindex </code> </p> <p>Il robot di ricerca segue tutti i collegamenti da file con l'estensione ".swf". La funzione di 
     <userinput>
       noindex 
     </userinput> specifica inoltre che il testo dei file associati non è indicizzato. </p> <p>Consultate <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aggiunta di maschere URL per indicizzare o non indicizzare parti del sito Web {#task_E1AFC17C746048B8843013D979E082C1}

Potete definire [!DNL URL Masks] le parti del sito Web che desiderate o che non desiderate includere nella ricerca per indicizzazione.

Utilizzate il campo Test URL Mask (Prova maschere URL) per verificare se un documento è incluso o meno dopo l&#39;indicizzazione.

Assicuratevi di rigenerare l’indice del sito in modo che i risultati delle maschere URL siano visibili ai clienti.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

**Per aggiungere maschere URL per indicizzare o non indicizzare parti del sito Web**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**.
1. (Facoltativo) Nella [!DNL URL Masks] pagina, nel **[!UICONTROL Test URL Masks]** campo, immettete una maschera URL di prova dal sito Web, quindi fate clic su **[!UICONTROL Test]**.
1. Nel [!DNL URL Masks] campo, digitate `include` (per aggiungere un sito Web che si desidera inserire per indicizzazione e ricerca per indicizzazione) oppure digitate `exclude` (per impedire che un sito Web venga sottoposto a ricerca per indicizzazione e indicizzazione), seguito dall’indirizzo della maschera URL.

   Immettete un indirizzo maschera URL per riga. Esempio:

   ```
   include https://www.mycompany.com/summer 
   include https://www.mycompany.com/spring 
   exclude regexp .*\.xml 
   exclude https://www.mycompany.com/fall
   ```

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sulle maschere data {#concept_F4F1F58A646F4A86B8650EC46FDCEF66}

Potete utilizzare le maschere data per includere o escludere i file dai risultati di ricerca in base alla pagina del file.

Assicuratevi di rigenerare l’indice del sito in modo che i risultati delle maschere URL siano visibili ai clienti.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

Di seguito sono riportati due tipi di maschere data utilizzabili:

* Includi maschere data (&quot;includi giorni&quot; e &quot;includi data&quot;)

   Includi file di indice delle maschere di data con data corrispondente o precedente alla data specificata.
* Escludere le maschere di data (&quot;giorni di esclusione&quot; e &quot;data di esclusione&quot;)

   Escludere i file di indice delle maschere di data con data precedente o alla data specificata.

Per impostazione predefinita, la data del file è determinata dalle informazioni del tag meta. Se non viene trovato alcun tag Meta, la data di un file viene determinata dall’intestazione HTTP ricevuta dal server quando il robot di ricerca scarica un file.

Ogni maschera data specificata deve trovarsi su una riga separata.

La maschera può specificare una delle seguenti opzioni:

* Un percorso completo come `https://www.mydomain.com/products.html`
* Un percorso parziale come `https://www.mydomain.com/products`
* Un URL che utilizza caratteri jolly `https://www.mydomain.com/*.html`
* Un&#39;espressione regolare. Per rendere una maschera un&#39;espressione regolare, inserite la parola chiave `regexp` prima dell&#39;URL.

Entrambe le maschere di data includono ed escludono può specificare una data in uno dei due modi seguenti. Le maschere vengono applicate solo se i file corrispondenti sono stati creati alla data specificata o prima di essa:

1. Numero di giorni. Ad esempio, supponiamo che la maschera data sia la seguente:

   ```
   exclude-days 30 https://www.mydomain.com/docs/archive/)
   ```

   Il numero di giorni specificati viene conteggiato di nuovo. Se il file è datato in data o prima della data di arrivo, la maschera viene applicata.

1. Una data effettiva che utilizza il formato AAAA-MM-GG. Ad esempio, supponiamo che la maschera data sia la seguente:

   ```
   include-date 2011-02-15 https://www.mydomain.com/docs/archive/)
   ```

   Se il documento corrispondente è datato alla data specificata o prima di essa, viene applicata la maschera data.

Di seguito è riportato un semplice esempio di maschera per date di esclusione:

```
exclude-days 90 https://www.mydomain.com/docs/archive
```

Poiché si tratta di una maschera data di esclusione, qualsiasi file che corrisponda al pattern non viene indicizzato ed ha 90 giorni o meno. Quando si esclude un documento, il testo non viene indicizzato e non viene seguito alcun collegamento da tale file. Il file viene effettivamente ignorato. In questo esempio, sia i file che le cartelle potrebbero corrispondere al pattern URL specificato. Tenere presente che `https://www.mydomain.com/docs/archive.html` e che `https://www.mydomain.com/docs/archive/index.html` corrispondono al pattern e non sono indicizzati se hanno 90 giorni di età o meno. Per far corrispondere solo i file presenti nella `/docs/archive/` cartella, la maschera data deve contenere una barra finale, come illustrato di seguito:

```
exclude-days 90 https://www.mydomain.com/docs/archive/
```

Le maschere data possono essere utilizzate anche con caratteri jolly. La seguente maschera di esclusione indica al robot di ricerca di ignorare i file con estensione &quot;.pdf&quot; che sono datati il o prima del 2011-02-15. Il robot di ricerca non aggiunge nessun file corrispondente all&#39;indice.

```
exclude-date 2011-02-15 *.pdf
```

Includi maschera data ha un aspetto simile, all&#39;indice vengono aggiunti solo i file corrispondenti. L&#39;esempio seguente include maschera data indica al robot di ricerca di indicizzare il testo da qualsiasi file che abbiano zero giorni di età o meno nell&#39; `/docs/archive/manual/` &#39;area del sito Web.

```
include-days 0 https://www.mydomain.com/docs/archive/manual/
```

L’inclusione di maschere e l’esclusione di maschere possono funzionare insieme. Ad esempio, potete escludere un’ampia porzione del sito Web dall’indicizzazione creando una maschera per date di esclusione, ma includendo una o più di quelle pagine escluse con una maschera URL di inclusione. Se l’URL di ingresso è il seguente:

```
https://www.mydomain.com/archive/
```

Il robot di ricerca ricerca si sposta per indicizzazione e indicizza tutte le pagine sotto `/archive/summer/`, `/archive/spring/`, e `/archive/fall/` (supponendo che ci siano collegamenti ad almeno una pagina in ciascuna cartella dalla `archive` cartella). Questo comportamento si verifica perché i percorsi di collegamento consentono al robot di ricerca di &quot;trovare&quot; i file nelle `/summer/`, `/spring/`e `/fall/` nelle cartelle e gli URL delle cartelle corrispondono alla maschera di inclusione generata automaticamente dall’URL del punto di ingresso.

Consultate [I punti di ingresso](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)URL.

Consultate [Configurazione delle impostazioni](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)dell’account.

Potete scegliere di escludere tutte le pagine con più di 90 giorni di età nella `/fall/` cartella con una maschera data di esclusione come illustrato di seguito:

```
exclude-days 90 https://www.mydomain.com/archive/fall/
```

Potete includere solo in modo selettivo `/archive/fall/index.html` (indipendentemente dalla data di scadenza, ovvero dalla corrispondenza tra file di 0 giorni o più) come parte dell’indice con la seguente maschera data:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html
```

Affinché i due esempi di maschera di cui sopra funzionino come previsto, è necessario elencare prima la maschera di inclusione, come illustrato di seguito:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html 
exclude-days 90 https://www.mydomain.com/archive/fall/
```

Poiché il robot di ricerca segue le indicazioni nell&#39;ordine in cui sono specificate, il robot di ricerca prima include `/archive/fall/index.html`, e poi esclude il resto dei file nella `/fall` cartella.

Se le istruzioni sono specificate nel modo opposto come indicato di seguito:

```
exclude-days 90 https://www.mydomain.com/archive/fall/ 
include-days 0 https://www.mydomain.com/archive/fall/index.html 
```

Non `/archive/fall/index.html` è incluso, anche se la maschera specifica che dovrebbe essere. Una maschera data che compare per prima ha sempre la precedenza su una maschera data che potrebbe essere visualizzata successivamente nelle impostazioni della maschera. Inoltre, se il robot di ricerca rileva una pagina che corrisponde sia a una maschera data di inclusione che a una maschera data di esclusione, la maschera elencata per prima ha sempre la precedenza.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

## Utilizzo delle parole chiave con le maschere data {#section_CCBB3E3FDBDE4725B2B571FD6594470C}

È possibile qualificare ciascuna maschera con una o più parole chiave separate da spazi, che influiscono sulla modalità di indicizzazione delle pagine corrispondenti.

Una virgola non è valida come separatore tra la maschera e la parola chiave; potete usare solo degli spazi.

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
   <td colname="col2"> <p> Se non si desidera indicizzare il testo nelle pagine con data corrispondente o precedente alla data specificata dalla maschera di inclusione, aggiungere 
     <userinput>
       noindex 
     </userinput> dopo la maschera data di inclusione, come illustrato di seguito: </p> <p> <code> include-days&amp;nbsp;10&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>Separate la parola chiave dalla maschera con uno spazio. </p> <p>L'esempio precedente specifica che il robot di ricerca segue tutti i collegamenti da file con estensione ".swf" che hanno un'età di 10 giorni o più. Tuttavia, disabilita l'indicizzazione di tutto il testo contenuto in tali file. </p> <p>Potete verificare che il testo per i file meno recenti non sia indicizzato ma segua comunque tutti i collegamenti da tali file. In questi casi, utilizzate una maschera data di inclusione con la parola chiave "noindex" invece di usare una maschera data di esclusione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Se desiderate indicizzare il testo sulle pagine con data corrispondente o precedente alla data specificata dalla maschera di inclusione, ma non desiderate seguire i collegamenti della pagina corrispondente, aggiungete 
     <userinput>
       nofollow 
     </userinput> dopo la maschera data di inclusione, come illustrato di seguito: </p> <p> <code> include-days&amp;nbsp;8&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>Separate la parola chiave dalla maschera con uno spazio. </p> <p>La funzione di 
     <userinput>
       nofollow 
     </userinput> è equivalente a un tag meta robot con 
     <userinput>
       content="nofollow" 
     </userinput> tra 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> tag di pagine corrispondenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>data server </p> </td> 
   <td colname="col2"> <p>Utilizzata sia per includere che per escludere le maschere. </p> <p>Il robot di ricerca in genere scarica e analizza ogni file prima di controllare le maschere data. Questo comportamento si verifica perché alcuni tipi di file possono specificare una data all'interno del file stesso. Ad esempio, un documento HTML può includere tag meta che impostano la data del file. </p> <p>Se si desidera escludere molti file in base alla data e non si desidera caricare un carico inutile sui server, è possibile utilizzare 
     <userinput>
       data server 
     </userinput> dopo l’URL nella maschera data. </p> <p>Questa parola chiave indica al robot di ricerca di considerare attendibile la data del file restituito dal server invece di analizzare ciascun file. Ad esempio, la maschera data di esclusione seguente ignora le pagine che corrispondono all’URL se i documenti sono di 90 giorni o più, in base alla data restituita dal server nelle intestazioni HTTP: </p> <p> <code> exclude-days&amp;nbsp;90&amp;nbsp;https://www.mydomain.com/docs/archive&amp;nbsp;server-date </code> </p> <p> Se la data restituita dal server è di 90 giorni o più, 
     <userinput>
       data server 
     </userinput> specifica che i documenti esclusi non possono essere scaricati dal server. Ciò comporta tempi di indicizzazione più rapidi per i documenti e un carico ridotto sui server. Se  
     <userinput>
       data server 
     </userinput> non viene specificato, il robot di ricerca ignora la data restituita dal server nelle intestazioni HTTP. Al contrario, ogni file viene scaricato e controllato per verificare se la data è specificata. Se nel file non è specificata alcuna data, il robot di ricerca utilizza la data restituita dal server. </p> <p>Non utilizzare 
     <userinput>
       data server 
     </userinput> se i file contengono comandi che ignorano la data del server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p> Utilizzate sia per includere che escludere le maschere. </p> <p>Qualsiasi maschera data preceduta da 
     <userinput>
       regexp 
     </userinput> è trattata come un'espressione regolare. </p> <p>Se il robot di ricerca rileva file che corrispondono a una maschera data con espressione regolare esclusa, non indicizza tali file. </p> <p>Se il robot di ricerca rileva file che corrispondono a una maschera data con espressione regolare, indicizza tali documenti. </p> <p>Ad esempio, si supponga di disporre della maschera data seguente: </p> <p> <code> exclude-days&amp;nbsp;180&amp;nbsp;regexp&amp;nbsp;.*archive.* </code> </p> <p>La maschera indica al robot di ricerca di escludere i file corrispondenti di almeno 180 giorni. ovvero file che contengono la parola "archivio" nell’URL. </p> <p>Consultate <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aggiunta di maschere data per indicizzare o non indicizzare parti del sito Web {#task_0010543C55F648D2B5DEFEFAD60FAF04}

Potete utilizzare le maschere data per includere o escludere i file dai risultati della ricerca dei clienti in base all’età dei file.

Utilizzare i campi **[!UICONTROL Test Date]** e **[!UICONTROL Test URL]** per verificare se un file è incluso o meno dopo l&#39;indicizzazione.

Assicuratevi di rigenerare l’indice del sito in modo che i risultati delle maschere URL siano visibili ai clienti.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

**Per aggiungere maschere di data per indicizzare o non indicizzare parti del sito Web**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Date Masks]**.
1. (Facoltativo) Sulla [!DNL Date Masks] pagina, nel **[!UICONTROL Test Date]** campo, immettere una data formattata come AAAA-MM-GG (ad esempio, `2011-07-25`); nel **[!UICONTROL Test URL]** campo, inserite una maschera URL dal sito Web e fate clic su **[!UICONTROL Test]**.
1. Nel [!DNL Date Masks] campo, immettere un indirizzo maschera data per riga.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sulle password {#concept_3EDBD731725D46B891F834D4472774DC}

Per accedere a porzioni del sito Web protette dall&#39;autenticazione di base HTTP, potete aggiungere una o più password.

Prima che gli effetti delle impostazioni Password siano visibili ai clienti, dovete ricreare l&#39;indice del sito.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

Sulla [!DNL Passwords] pagina, digitate ogni password su una sola riga. La password è composta da un URL o un realm, un nome utente e una password, come nell&#39;esempio seguente:

```
https://www.mydomain.com/ myname mypassword
```

Invece di usare un percorso URL, come sopra, potete anche specificare un realm.

Per determinare l&#39;area di autenticazione corretta da utilizzare, aprire una pagina Web protetta da password con un browser e consultare la finestra di dialogo &quot;Immettere la password di rete&quot;.

![](assets/realms.gif)

Il nome dell&#39;area di autenticazione, in questo caso, è &quot;Area del sito personale&quot;.

Utilizzando il nome dell&#39;area di autenticazione riportato sopra, la password potrebbe essere simile a quella riportata di seguito:

```
My Site Realm myusername mypassword
```

Se il sito Web ha più aree di autenticazione, è possibile creare più password immettendo un nome utente e una password per ogni area di autenticazione su una riga separata, come nell&#39;esempio seguente:

```
Realm1 name1 password1 
Realm2 name2 password2 
Realm3 name3 password3
```

È possibile utilizzare password che contengono URL o realm, in modo che l&#39;elenco delle password sia simile a quello riportato di seguito:

```
Realm1 name1 password1 
https://www.mysite.com/path1/path2 name2 password2 
Realm3 name3 password3 
Realm4 name4 password4 
https://www.mysite.com/path1/path5 name5 password5 
https://www.mysite.com/path6 name6 password6
```

Nell&#39;elenco di cui sopra, viene utilizzata la prima password che contiene un realm o un URL corrispondente alla richiesta di autenticazione del server. Anche se il file in `https://www.mysite.com/path1/path2/index.html` è in `Realm3`, ad esempio, `name2` e `password2` viene utilizzato perché la password definita con l&#39;URL è elencata sopra quella definita con l&#39;area di autenticazione.

## Aggiunta di password per accedere alle aree del sito Web che richiedono l’autenticazione {#task_DED19D476FF04B48BB6456D5ECB8628A}

Potete utilizzare Password per accedere alle aree protette da password del sito Web a scopo di ricerca per indicizzazione e indicizzazione.

Prima che gli effetti della password siano visibili ai clienti, accertatevi di ricreare l&#39;indice del sito

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

**Aggiunta di password per l&#39;accesso alle aree del sito Web che richiedono l&#39;autenticazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Passwords]**.
1. Nella [!DNL Passwords] pagina, nel **[!UICONTROL Passwords]** campo, immettete un realm o un URL e il nome utente e la password associati, separati da uno spazio.

   Esempio di password di un realm e di una password URL su righe separate:

   ```
   Realm1 name1 password1 
   https://www.mysite.com/path1/path2 name2 password2
   ```

   Aggiungete una sola password per riga.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sui tipi di contenuto {#concept_6FEA1355C0374500B4C53090C34A8A07}

È possibile utilizzare [!DNL Content Types] per selezionare i tipi di file da cercare per indicizzazione e indicizzazione per l&#39;account.

I tipi di contenuto che è possibile scegliere per la ricerca per indicizzazione e per indicizzazione includono documenti PDF, documenti di testo, filmati Adobe Flash, file da applicazioni Microsoft Office come Word, Excel e Powerpoint e testo in file MP3. Il testo che si trova all’interno dei tipi di contenuto selezionati viene cercato insieme a tutto il testo presente nel sito Web.

Prima che gli effetti delle impostazioni Tipi di contenuto siano visibili ai clienti, dovete ricreare l&#39;indice del sito.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

## Informazioni sull&#39;indicizzazione di file musicali MP3 {#section_AD2E28BEEE3E46629E2B05C34A963673}

Se selezionate l&#39;opzione **[!UICONTROL Text in MP3 Music Files]** sulla [!DNL Content Types] pagina, un file MP3 viene sottoposto a ricerca per indicizzazione in uno dei due modi disponibili. Il primo e più comune metodo è rappresentato da un tag href di ancoraggio in un file HTML, come illustrato di seguito:

```
<a href="MP3-file-URL"></a>
```

Il secondo modo consiste nell’inserire l’URL del file MP3 come punto di ingresso dell’URL.

Consultate [I punti di ingresso](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)URL.

Un file MP3 viene riconosciuto dal tipo MIME &quot;audio/mpeg&quot;.

Tenete presente che le dimensioni dei file musicali MP3 possono essere piuttosto grandi, anche se in genere contengono solo una piccola quantità di testo. Ad esempio, i file MP3 possono memorizzare facoltativamente elementi quali il nome dell&#39;album, il nome dell&#39;artista, il titolo della canzone, il genere della canzone, l&#39;anno di rilascio e un commento. Queste informazioni vengono memorizzate alla fine del file in quello che viene chiamato TAG. I file MP3 contenenti informazioni TAG sono indicizzati nel modo seguente:

* Il titolo del brano viene trattato come il titolo di una pagina HTML.
* Il commento viene trattato come una descrizione definita per una pagina HTML.
* Il genere viene trattato come una parola chiave definita per una pagina HTML.
* Il nome dell&#39;artista, il nome dell&#39;album e l&#39;anno di rilascio vengono trattati come il corpo di una pagina HTML.

Ogni file MP3 che viene sottoposto a ricerca per indicizzazione e con scorrimento nel sito Web viene contato come una pagina.

Se il sito Web contiene molti file MP3 di grandi dimensioni, potete superare il limite di byte di indicizzazione per il vostro account. In questo caso, potete deselezionare **[!UICONTROL Text in MP3 Music Files]** sulla [!DNL Content Types] pagina per impedire l’indicizzazione di tutti i file MP3 sul sito Web.

Se desiderate solo impedire l’indicizzazione di alcuni file MP3 sul vostro sito Web, potete effettuare una delle seguenti operazioni:

* Circondare i tag di ancoraggio che collegano ai file MP3 con `<nofollow>` tag e `</nofollow>` tag. Il robot di ricerca non segue i collegamenti tra tali tag.

* Aggiungete gli URL dei file MP3 come maschere di esclusione.

   Consultate [Le maschere](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)URL.

## Selezione dei tipi di contenuto per la ricerca per indicizzazione e l&#39;indicizzazione {#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8}

È possibile utilizzare [!DNL Content Types] per selezionare i tipi di file da cercare per indicizzazione e indicizzazione per l&#39;account.

I tipi di contenuto che è possibile scegliere per la ricerca per indicizzazione e per indicizzazione includono documenti PDF, documenti di testo, filmati Adobe Flash, file da applicazioni Microsoft Office come Word, Excel e Powerpoint e testo in file MP3. Il testo che si trova all’interno dei tipi di contenuto selezionati viene cercato insieme a tutto il testo presente nel sito Web.

Prima che gli effetti delle impostazioni Tipi di contenuto siano visibili ai clienti, dovete ricreare l&#39;indice del sito.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

Per eseguire ricerche per indicizzazione e indicizzazione di file MP3 cinesi, giapponesi o coreani, completare i passaggi descritti di seguito. Quindi, in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**, specificate il set di caratteri utilizzato per codificare i file MP3.

Consulta [Informazioni sulle iniezioni](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

**Per selezionare i tipi di contenuto da sottoporre a ricerca per indicizzazione e**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**.
1. Nella [!DNL Content Types] pagina, controlla i tipi di file che desideri cercare per indicizzazione e indicizzare sul tuo sito Web.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sulle connessioni {#concept_E2F3B7E7521147479E5948A94BB3A40B}

È possibile utilizzare Connessioni per aggiungere fino a dieci connessioni HTTP utilizzate dal robot di ricerca per indicizzare il sito Web.

Aumentare il numero di connessioni può ridurre notevolmente il tempo necessario per completare una ricerca per indicizzazione e un indice. Tuttavia, tenete presente che ogni connessione aggiuntiva aumenta il carico sul server.

## Aggiunta di connessioni per aumentare la velocità di indicizzazione {#task_3E9B83E43C1842A19066355A15C4A6FB}

È possibile ridurre il tempo necessario per indicizzare il sito Web utilizzando Connessioni per aumentare il numero di connessioni HTTP simultanee utilizzate dal crawler. È possibile aggiungere fino a dieci connessioni.

Tenete presente che ogni connessione aggiuntiva aumenta il carico inserito sul server.

**Per aggiungere connessioni per aumentare la velocità di indicizzazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Connections]**.
1. Nella [!DNL Parallel Indexing Connections] pagina, nel **[!UICONTROL Number of Connections]** campo, immettere il numero di connessioni (1-10) che si desidera aggiungere.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sull&#39;invio del modulo {#concept_CADD5D7CF373497DAA6F8564D7BC8502}

È possibile utilizzare l&#39;opzione Invia modulo per riconoscere ed elaborare i moduli sul sito Web.

Durante la ricerca per indicizzazione e l&#39;indicizzazione del sito Web, ogni modulo rilevato viene confrontato con le definizioni del modulo aggiunte. Se un modulo corrisponde alla definizione di un modulo, il modulo viene inviato per l&#39;indicizzazione. Se un modulo corrisponde a più definizioni, viene inviato una volta per ciascuna definizione corrispondente.

## Aggiunta di definizioni di moduli per l&#39;indicizzazione di moduli nel sito Web {#task_62FBCE9E6DBE4BDA8D1249233ADFC00F}

È possibile utilizzare [!DNL Form Submission] per elaborare moduli riconosciuti sul sito Web a scopo di indicizzazione.

Assicuratevi di rigenerare l’indice del sito in modo che i risultati delle modifiche siano visibili ai clienti.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

**Aggiunta di definizioni di moduli per l&#39;indicizzazione dei moduli nel sito Web**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Sulla [!DNL Form Submission] pagina, fate clic su **[!UICONTROL Add New Form]**.
1. Nella [!DNL Add Form Definition] pagina, impostate le [!DNL Form Recognition] opzioni e [!DNL Form Submission] .

   Le cinque opzioni della [!DNL Form Recognition] sezione della [!DNL Form Definition] pagina consentono di identificare i moduli nelle pagine Web che possono essere elaborati.

   Le tre opzioni della [!DNL Form Submission] sezione vengono utilizzate per specificare i parametri e i valori inviati con un modulo al server Web.

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
      <td colname="col1"> <p> <b>Riconoscimento dei moduli</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maschera URL pagina </p> </td> 
      <td colname="col2"> <p>Identificare la pagina Web o le pagine che contengono il modulo. Per identificare un modulo che viene visualizzato su una singola pagina, immettete l’URL della pagina come nell’esempio seguente: </p> <p> <code> https://www.mydomain.com/login.html </code> </p> <p>Per identificare i moduli che vengono visualizzati su più pagine, specificare una maschera URL che utilizza i caratteri jolly per descrivere le pagine. Per identificare i moduli rilevati in qualsiasi pagina ASP, <code> https://www.mydomain.com/register/ </code>ad esempio, è necessario specificare quanto segue: </p> <p> <code> https://www.mydomain.com/register/*.asp&amp;nbsp; </code> </p> <p>È inoltre possibile utilizzare un'espressione regolare per identificare più pagine. È sufficiente specificare 
      <userinput>
        regexp 
      </userinput> prima della maschera URL, come nell'esempio seguente: </p> <p> <code> regexp&amp;nbsp;^https://www\.mydomain\.com/.*/login\.html$ </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL azione </p> </td> 
      <td colname="col2"> <p>Identifica l’attributo action del 
      <userinput>
        &lt;form&gt; 
      </userinput> . </p> <p>Come la maschera URL pagina, la maschera URL azione può assumere la forma di un singolo URL, un URL con caratteri jolly o un'espressione regolare. </p> <p>La maschera URL può essere una delle seguenti: 
      <ul id="ul_EDFE7688D3DD4C0BBACCE5D4648D8E44"> 
      <li id="li_77550A448D954EF29FF33EE5E8B5E0F5"> Un percorso completo come nel seguente: <code> https://www.mydomain.com/products.html </code> </li> 
      <li id="li_F84E25553BBA41419BE153DC0709E011"> Un percorso parziale come nel seguente: <code> https://www.mydomain.com/products </code> </li> 
      <li id="li_8DADA1C8604740FCACBA30B4AAADB2A1"> Un URL che utilizza caratteri jolly come illustrato di seguito: <code> https://www.mydomain.com/*.html </code> </li> 
      <li id="li_1EF637B450654B509AA4B618F7FD3C2B"> Un'espressione regolare come nell'esempio seguente: <code> regexp&amp;nbsp^https://www\.mydomain\.com/.*/login\.html$ </code> </li> 
      </ul> </p> <p>Se non si desidera indicizzare il testo nelle pagine identificate da una maschera URL o da una maschera URL azione, oppure se non si desidera che i collegamenti siano seguiti in tali pagine, è possibile utilizzare la 
      <userinput>
        noindex 
      </userinput> e 
      <userinput>
        nofollow 
      </userinput> parole chiave. Potete aggiungere queste parole chiave alle maschere utilizzando maschere URL o punti di ingresso. </p> <p>Consultate <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573" type="concept" format="dita" scope="local"> I Punti Di Entrata Degli URL </a>. </p> <p>Consultate <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> Le Maschere URL </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maschera nome modulo </p> </td> 
      <td colname="col2"> <p>Identifica i moduli se il 
      <userinput>
        &lt;form&gt; 
      </userinput> nelle pagine Web i tag contengono un attributo nome. </p> <p>È possibile utilizzare un nome semplice ( 
      <userinput>
        login_form 
      </userinput>), un nome con un carattere jolly ( 
      <userinput>
        form* 
      </userinput>) o un'espressione regolare ( 
      <userinput>
        regexp ^.*autorizzare.*$ 
      </userinput>). </p> <p>In genere è possibile lasciare vuoto questo campo perché i moduli in genere non hanno un attributo nome. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maschera ID modulo </p> </td> 
      <td colname="col2"> <p>Identifica i moduli se il 
      <userinput>
        &lt;form&gt; 
      </userinput> i tag presenti nelle pagine Web contengono un attributo id. </p> <p>È possibile utilizzare un nome semplice ( 
      <userinput>
        login_form 
      </userinput>), un nome con un carattere jolly ( 
      <userinput>
        form* 
      </userinput>) o un'espressione regolare ( 
      <userinput>
        regexp ^.*autorizzare.*$ 
      </userinput>). </p> <p>In genere è possibile lasciare vuoto questo campo perché i moduli in genere non hanno un attributo nome. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametri </p> </td> 
      <td colname="col2"> <p>Identificare i moduli che contengono o non contengono parametri denominati con un valore specifico. </p> <p>Ad esempio, per identificare un modulo che contiene un parametro e-mail preimpostato su rick_brough@mydomain.com, un parametro password, ma non un parametro first-name, è necessario specificare le seguenti impostazioni di parametro, una per riga: </p> <p> <code> email=rick_brough@mydomain.com password  not&nbsp;first-name </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Invio modulo</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL azione di esclusione </p> </td> 
      <td colname="col2"> <p>Specificare se la destinazione dell'invio del modulo è diversa da quella specificata nell'attributo action del modulo. </p> <p>Ad esempio, è possibile utilizzare questa opzione quando il modulo viene inviato tramite una funzione JavaScript che crea un valore URL diverso da quello trovato nel modulo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Metodo Override </p> </td> 
      <td colname="col2"> <p>Specificare quando la destinazione dell'invio del modulo è diversa da quella utilizzata nell'attributo action del modulo e quando il codice JavaScript di invio ha modificato il metodo. </p> <p>I valori predefiniti per tutti i parametri del modulo ( 
      <userinput>
        &lt;input&gt; 
      </userinput> tag, inclusi i campi nascosti), impostazione predefinita 
      <userinput>
        &lt;opzione&gt; 
      </userinput> da 
      <userinput>
        &lt;select&gt; 
      </userinput> e testo predefinito compreso tra 
      <userinput>
        &lt;textarea&gt;...&lt;/textarea&gt; 
      </userinput> i tag) sono letti dalla pagina Web. Tuttavia, qualsiasi parametro elencato nella sezione <span class="wintitle"> Invio modulo </span> , nel campo <span class="uicontrol"> Parametri, </span> viene sostituito con le impostazioni predefinite del modulo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametri </p> </td> 
      <td colname="col2"> <p>È possibile assegnare un prefisso ai parametri di invio del modulo 
      <userinput>
        non 
      </userinput> parola chiave. </p> <p>Quando si assegna un prefisso a un parametro con 
      <userinput>
        non 
      </userinput>, non viene inoltrato nell'ambito della presentazione del modulo. Questo comportamento è utile per le caselle di controllo che devono essere inviate deselezionate. </p> <p>Ad esempio, si supponga di voler inviare i seguenti parametri: </p> <p> 
      <ul id="ul_962D12BACF464FF189DB12BFAFCC93A6"> 
      <li id="li_830C6C3EC8D2448388A453BB8EDE5940"> Il parametro e-mail con il valore 
      <userinput>
        nobody@mydomain.com 
      </userinput> </li> 
      <li id="li_905497E3FACE472DBDD49392D5B45E01"> Il parametro password con il valore 
      <userinput>
        provare 
      </userinput> </li> 
      <li id="li_AAA411708ADC464793EADF0D821E282E"> Il parametro myCasella di controllo è deselezionato. </li> 
      <li id="li_0D3DDE641E2B4BEF9F570C03FDB40ED2"> <p>Tutti gli altri 
      <userinput>
        &lt;form&gt; 
      </userinput> parametri come valori predefiniti </p> </li> 
      </ul> </p> <p>Il parametro di invio del modulo sarà simile al seguente: </p> <p> <code> email=nobody@mydomain.com 
        password=tryme 
        not&nbsp;mycheckbox </code> </p> <p>L'attributo metodo della variabile 
      <userinput>
        &lt;form&gt; 
      </userinput> nella pagina Web viene utilizzato per stabilire se i dati vengono inviati al server utilizzando il metodo GET o POST. </p> <p>Se tieni premuto il tasto 
      <userinput>
        &lt;form&gt; 
      </userinput> il tag non contiene un attributo metodo, il modulo viene inviato utilizzando il metodo GET. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica di una definizione di modulo {#task_9FB34E9C8A814DFE9BF7F8F8F69BF314}

È possibile modificare una definizione di modulo esistente se un modulo sul sito Web è stato modificato o se è necessario modificarla.

Tenere presente che non esiste [!DNL History] una funzione sulla [!DNL Form Submission] pagina per ripristinare le modifiche apportate a una definizione del modulo.

Assicuratevi di rigenerare l’indice del sito in modo che i risultati delle modifiche siano visibili ai clienti.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

**Per modificare una definizione di modulo**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Sulla [!DNL Form Submission] pagina fare clic **[!UICONTROL Edit]** a destra della definizione di un modulo da aggiornare.
1. Nella [!DNL Edit Form Definition] pagina, impostate le [!DNL Form Recognition] opzioni e [!DNL Form Submission] .

   Vedere la tabella delle opzioni in [Aggiunta delle definizioni dei moduli per l&#39;indicizzazione dei moduli sul sito Web](../c-about-settings-menu/c-about-crawling-menu.md#task_62FBCE9E6DBE4BDA8D1249233ADFC00F).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di una definizione di modulo {#task_C350FC0CDE344F2786215D544C048B5E}

È possibile eliminare una definizione di modulo esistente se il modulo non esiste più sul sito Web o se non si desidera più elaborare e indicizzare un modulo specifico.

Tenere presente che non esiste [!DNL History] una funzione sulla [!DNL Form Submission] pagina per ripristinare le modifiche apportate a una definizione del modulo.

Assicuratevi di rigenerare l’indice del sito in modo che i risultati delle modifiche siano visibili ai clienti.

Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.

**Per eliminare una definizione di modulo**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Sulla [!DNL Form Submission] pagina fare clic **[!UICONTROL Delete]** a destra della definizione di un modulo da rimuovere.

   Assicurarsi di scegliere la definizione corretta del modulo da eliminare. Quando si fa clic **[!UICONTROL Delete]** nel passaggio successivo non viene visualizzata alcuna finestra di dialogo di conferma.
1. Sulla [!DNL Delete Form Definition] pagina, fate clic su **[!UICONTROL Delete]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sul connettore indice {#concept_CA6921E2FBF641F9B4F60C92B32AFA84}

Utilizzare [!DNL Index Connector] per definire origini di input aggiuntive per l&#39;indicizzazione di pagine XML o qualsiasi tipo di feed.

È possibile utilizzare un&#39;origine di input di feed di dati per accedere al contenuto memorizzato in un modulo diverso da quello di solito scoperto in un sito Web utilizzando uno dei metodi disponibili per la ricerca per indicizzazione. Ogni documento sottoposto a ricerca per indicizzazione e indicizzato corrisponde direttamente a una pagina di contenuto del sito Web. Tuttavia, un feed di dati proviene da un documento XML o da un file di testo delimitato da virgole o da tabulazioni e contiene le informazioni sul contenuto da indicizzare.

Un&#39;origine dati XML è costituita da stanzas XML, o record, che contengono informazioni corrispondenti a singoli documenti. Questi singoli documenti vengono aggiunti all’indice. Un feed di dati di testo contiene singoli record delimitati da nuove righe che corrispondono a singoli documenti. All’indice vengono aggiunti anche questi singoli documenti. In entrambi i casi, una configurazione di connettore indice descrive come interpretare il feed. Ogni configurazione descrive la posizione del file e la modalità di accesso dei server. La configurazione descrive anche le informazioni sulla mappatura. In altre parole, in che modo gli elementi di ciascun record vengono utilizzati per compilare i campi di metadati nell&#39;indice risultante.

Dopo aver aggiunto una definizione del connettore indice alla [!DNL Staged Index Connector Definitions] pagina, è possibile modificare qualsiasi impostazione di configurazione, *ad eccezione* dei valori Nome o Tipo.

La [!DNL Index Connector] pagina mostra le informazioni seguenti:

* Nome dei connettori di indice definiti configurati e aggiunti dall&#39;utente.
* Uno dei seguenti tipi di origini dati per ciascun connettore aggiunto:

   * **Testo** - File semplici, delimitati da virgole, delimitati da tabulazioni o altri formati delimitati in modo coerente.
   * **Feed** - Feed XML.
   * **XML** - Raccolte di documenti XML.

* Indica se il connettore è abilitato o meno per la ricerca per indicizzazione successiva e se l&#39;indicizzazione è stata completata.
* Indirizzo dell&#39;origine dati.

Vedere anche [Informazioni sul connettore indice](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)

## Funzionamento del processo di indicizzazione per le configurazioni di testo e feed nel connettore indice {#section_E059A33D61EE4DB0972A37B8A35E9E16}

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
   <td colname="col2"> <p>Scarica l'origine dati. </p> </td> 
   <td colname="col3"> <p>Per le configurazioni di testo e feed, si tratta di un semplice download di file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Suddivide l'origine dati scaricata in singoli pseudo-documenti. </p> </td> 
   <td colname="col3"> <p>Per <span class="uicontrol"> Testo </span>, ogni riga di testo delimitata da una nuova riga corrisponde a un singolo documento e viene analizzata utilizzando il delimitatore specificato, ad esempio una virgola o una tabulazione. </p> <p>Per <span class="uicontrol"> Feed </span>, i dati di ciascun documento vengono estratti utilizzando un pattern di espressione regolare nel seguente modulo: </p> <p> <code> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Utilizzando <span class="uicontrol"> Mappa </span> nella pagina Aggiungi connettore <span class="wintitle"> </span> indice, create una copia memorizzata nella cache dei dati, quindi create un elenco di collegamenti per il crawler. I dati vengono memorizzati in una cache locale e compilati con i campi configurati. </p> <p>I dati analizzati vengono scritti nella cache locale. </p> <p>Questa cache viene letta in seguito per creare i documenti HTML semplici necessari al crawler. Ad esempio, </p> <p> <code> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>L'elemento <span class="codeph"> &lt;title&gt; </span> viene generato solo quando esiste una mappatura nel campo di metadati Titolo. Analogamente, l'elemento <span class="codeph"> &lt;body&gt; </span> viene generato solo quando esiste una mappatura nel campo di metadati Body. </p> <p> <b>Importante</b>: Non è supportato l'assegnazione di valori al tag meta dell'URL predefinito. </p> <p>Per tutte le altre mappature, vengono generati <span class="codeph"> &lt;meta&gt; </span> tag per ogni campo con dati trovati nel documento originale. </p> <p>I campi per ciascun documento vengono aggiunti alla cache. Per ogni documento scritto nella cache, viene generato anche un collegamento come negli esempi seguenti: </p> <p> <code> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>La mappatura della configurazione deve avere un campo identificato come Chiave primaria. Questa mappatura costituisce la chiave utilizzata quando i dati vengono estratti dalla cache. </p> <p>Il crawler riconosce l’ <span class="codeph"> indice URL: </span> il prefisso dello schema, che può quindi accedere ai dati memorizzati nella cache locale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Eseguire la ricerca per indicizzazione del set di documenti memorizzato nella cache. </p> </td> 
   <td colname="col3"> <p>L' <span class="codeph"> indice: </span> i collegamenti vengono aggiunti all’elenco in sospeso del crawler e vengono elaborati nella normale sequenza di ricerca per indicizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Elabora ogni documento. </p> </td> 
   <td colname="col3"> <p>Il valore chiave di ciascun collegamento corrisponde a una voce nella cache, pertanto la ricerca per indicizzazione di ciascun collegamento determina il recupero dei dati del documento dalla cache. Viene quindi "assemblato" in un’immagine HTML elaborata e aggiunta all’indice. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Funzionamento del processo di indicizzazione per le configurazioni XML nel connettore indice {#section_7F1551EA51854C5C99F284CE260526EB}

Il processo di indicizzazione per la configurazione XML è simile al processo per le configurazioni di testo e feed con le seguenti modifiche ed eccezioni minori.

Poiché i documenti per le ricerche per indicizzazione XML sono già separati in singoli file, i passaggi 1 e 2 della tabella precedente non si applicano direttamente. Se specificate un URL nei campi **[!UICONTROL Host Address]** e **[!UICONTROL File Path]** della [!DNL Index Connector Add] pagina, questo viene scaricato ed elaborato come normale documento HTML. Ci si aspetta che il documento di download contenga una raccolta di `<a href="{url}"...` collegamenti, ciascuno dei quali fa riferimento a un documento XML elaborato. Tali collegamenti sono convertiti nel seguente modulo:

```
<a href="index:<ic_config_name>?url="{url}">
```

Ad esempio, se la configurazione di Adobe ha restituito i seguenti collegamenti:

```
<a href="https://www.adobe.com/somepath/doc1.xml">doc 1</a> 
<a href="https://www.adobe.com/otherpath/doc2.xml">doc 2</a>
```

Nella tabella precedente, il punto 3 non si applica e il punto 4 è completato al momento della ricerca per indicizzazione e dell&#39;indicizzazione.

In alternativa, è possibile combinare i documenti XML con altri documenti scoperti naturalmente attraverso il processo di ricerca per indicizzazione. In tali casi, è possibile utilizzare le regole di riscrittura ( **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**) per modificare gli URL dei documenti XML e indirizzarli a Index Connector.

Consultate [Informazioni Sulle Regole](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA)Per Il Recupero Degli URL Per L’Elenco Di Ricerca Per indicizzazione.

Ad esempio, supponiamo che si disponga della seguente regola di riscrittura:

```
RewriteRule (^http.*[.]xml$) index:Adobe?key=$1
```

Questa regola converte qualsiasi URL che termina con `.xml` un collegamento del connettore indice. Il crawler riconosce e riscrive lo schema `index:` URL. Il processo di download viene reindirizzato attraverso il server Apache del connettore indice sul server principale. Ogni documento scaricato viene esaminato utilizzando lo stesso pattern di espressione regolare utilizzato con Feeds. In questo caso, tuttavia, il documento HTML prodotto non viene salvato nella cache. Viene invece consegnato direttamente al crawler per l’elaborazione dell’indice.

## Come configurare più connettori indice {#section_C2B14C0F06354A57AEF6238FF3814E5D}

È possibile definire più configurazioni del connettore indice per qualsiasi account. Le configurazioni vengono aggiunte automaticamente all&#39;elenco a discesa in **[!UICONTROL Settings]** > **[!UICONTROL Crawl]** > **[!UICONTROL URL Entrypoints]** , come illustrato nella figura seguente:

![](assets/url_entrypoints_index_connector.png)

Selezionando una configurazione dall’elenco a discesa, il valore viene aggiunto alla fine dell’elenco dei punti di ingresso dell’URL.

>[!NOTE]
>
>Le configurazioni del connettore indice disattivate vengono aggiunte all&#39;elenco a discesa, ma non è possibile selezionarle. Se si seleziona una seconda volta la stessa configurazione del connettore indice, questa viene aggiunta alla fine dell&#39;elenco e l&#39;istanza precedente viene eliminata.

Per specificare un punto di ingresso del connettore indice per una ricerca per indicizzazione incrementale, è possibile aggiungere voci utilizzando il formato seguente:

```
index:<indexconnector_configuration_name>
```

Il crawler elabora ogni voce aggiunta se questa si trova nella pagina Connettori indice ed è abilitata.

Nota: Poiché l&#39;URL di ciascun documento è costruito utilizzando il nome di configurazione del connettore indice e la chiave primaria del documento, accertatevi di utilizzare lo stesso nome di configurazione del connettore indice durante l&#39;esecuzione degli aggiornamenti incrementali! In questo modo è possibile [!DNL Adobe Search&Promote] aggiornare correttamente i documenti indicizzati in precedenza.

Consultate anche [I punti di ingresso](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)URL.

**Utilizzo delle mappe di impostazione quando si aggiunge un connettore indice**

Quando si aggiunge un connettore indice, è possibile utilizzare la funzione **[!UICONTROL Setup Maps]** per scaricare un esempio dell&#39;origine dati. I dati vengono esaminati per verificare l&#39;idoneità all&#39;indicizzazione.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Se si sceglie il tipo di connettore indice... </p> </th> 
   <th colname="col2" class="entry"> <p>La funzione Mappe di configurazione... </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Testo </p> </td> 
   <td colname="col2"> <p>Determina il valore del delimitatore provando prima le tabulazioni, poi le barre verticali ( <span class="codeph"> | </span>) e infine virgole ( <span class="codeph"> , </span>). Se avete già specificato un valore di delimitazione prima di aver fatto clic su <span class="uicontrol"> Mappe di installazione </span>, tale valore viene utilizzato. </p> <p>Lo schema di adattamento ottimale si traduce nella compilazione dei campi Mappa con gli specchietti ai valori appropriati di Tag e Campo. Inoltre, viene visualizzato un esempio dei dati analizzati. Accertatevi di selezionare <span class="uicontrol"> Intestazioni nella prima riga </span> se si è certi che il file include una riga di intestazione. La funzione di configurazione utilizza queste informazioni per identificare meglio le voci di mappa risultanti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Scarica l'origine dati ed esegue un'analisi XML semplice. </p> <p>Gli identificatori XPath risultanti vengono visualizzati nelle righe Tag della tabella Mappa e valori simili nei campi. Queste righe identificano solo i dati disponibili e non generano le definizioni XPath più complesse. Tuttavia, è ancora utile perché descrive i dati XML e identifica i valori degli elementi tag. </p> <p> <p>Nota:  La funzione Setup Maps scarica l’intera origine XML per eseguire l’analisi. Se il file è di grandi dimensioni, l'operazione potrebbe non riuscire. </p> </p> <p>In caso di esito positivo, questa funzione identifica tutti gli elementi XPath possibili, molti dei quali non sono desiderabili da utilizzare. Accertatevi di esaminare le definizioni di mappa risultanti e rimuovere quelle non necessarie o desiderate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XML </p> </td> 
   <td colname="col2"> <p>Scarica l’URL di un singolo documento rappresentativo, non l’elenco di collegamenti principale. Questo singolo documento viene analizzato utilizzando lo stesso meccanismo utilizzato con i feed, e i risultati vengono visualizzati. </p> <p>Prima di fare clic su <span class="uicontrol"> Aggiungi </span> per salvare la configurazione, accertati di ripristinare l’URL nel documento dell’elenco di collegamenti principale. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Importante**: La funzione Mappe di installazione potrebbe non funzionare per set di dati XML di grandi dimensioni perché il parser di file tenta di leggere l’intero file in memoria. Di conseguenza, potrebbe verificarsi una condizione di memoria insufficiente. Tuttavia, quando lo stesso documento viene elaborato al momento dell&#39;indicizzazione, non viene letto in memoria. Al contrario, i documenti di grandi dimensioni vengono elaborati &quot;in movimento&quot; e non vengono prima letti completamente nella memoria.

**Utilizzo dell&#39;anteprima quando si aggiunge un connettore indice**

Quando si aggiunge un connettore indice, è possibile utilizzare la funzione **[!UICONTROL Preview]** per convalidare i dati, come se li si stesse salvando. Esegue un test rispetto alla configurazione, ma senza salvare la configurazione nell&#39;account. Il test accede all&#39;origine dati configurata. Tuttavia, scrive la cache di download in un percorso temporaneo; non entra in conflitto con la cartella cache principale utilizzata dal crawler di indicizzazione.

Preview elabora solo un predefinito di cinque documenti, come controllato da Acct:IndexConnector-Preview-Max-Documents. I documenti visualizzati in anteprima vengono visualizzati nel modulo di origine, man mano che vengono presentati al crawler di indicizzazione. La visualizzazione è simile alla funzione &quot;Visualizza origine&quot; di un browser Web. Potete spostarvi tra i documenti del set di anteprima utilizzando i collegamenti di navigazione standard.

L&#39;anteprima non supporta le configurazioni XML perché tali documenti vengono elaborati direttamente e non scaricati nella cache.

## Aggiunta di una definizione del connettore indice {#task_96779B651A654E1F871F55D6DBBC8886}

Ogni configurazione del connettore indice definisce un&#39;origine dati e le mappature per collegare gli elementi dati definiti per tale origine ai campi di metadati nell&#39;indice.

Prima che gli effetti della definizione nuova e abilitata siano visibili ai clienti, ricreate l’indice del sito.

**Per aggiungere una definizione del connettore indice**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Sulla [!DNL Stage Index Connector Definitions] pagina, fate clic su **[!UICONTROL Add New Index Connector]**.
1. Nella [!DNL Index Connector Add] pagina, impostare le opzioni di connettore desiderate. Le opzioni disponibili dipendono dalla selezione **[!UICONTROL Type]** effettuata.

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
      <td colname="col2"> <p>Origine dei dati. Il tipo di origine dati selezionato influisce sulle opzioni risultanti disponibili nella pagina <span class="wintitle"> Index Connector Add </span> . Potete scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Testo </span> <p>File di testo semplici, delimitati da virgole, delimitati da tabulazioni o altri formati delimitati in modo coerente. Ogni riga di testo delimitata da una nuova riga corrisponde a un singolo documento e viene analizzata utilizzando il delimitatore specificato. </p> <p>Potete mappare ciascun valore, o colonna, su un campo di metadati, a cui fa riferimento il numero di colonna, a partire da 1 (uno). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Scarica un documento XML principale che contiene più "righe" di informazioni. </p> </li> 
      <li id="li_5A61C53522D74D4C9A5F65989604BDEF"> <span class="uicontrol"> XML </span> <p>Scarica un documento XML principale contenente collegamenti ( 
      <userinput>
        &lt;a&gt; 
      </userinput>) in singoli documenti XML. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo origine dati: Testo</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per la ricerca per indicizzazione e l’indicizzazione. In alternativa, è possibile disattivare la configurazione per impedire la ricerca per indicizzazione e l'indicizzazione. </p> <p> <b>Nota</b>: Le configurazioni del connettore indice disattivate vengono ignorate se sono presenti in un elenco entrypoint. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo dell'host del server in cui si trovano i dati. </p> <p>Se necessario, è possibile specificare un percorso URI completo (Uniform Resource Identifier) per il documento di origine dati, come negli esempi seguenti: </p> <p> <code> https://www.somewhere.com/some_path/some_file.xml </code> </p> <p> oppure  </p> <p> <code> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.xml </code> </p> <p>L'URI è suddiviso nelle voci appropriate per i campi Indirizzo host, Percorso file, Protocollo e, facoltativamente, Nome utente e Password. </p> <p>Specifica l'indirizzo IP o l'indirizzo URL del sistema host in cui viene trovato il file di origine dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del semplice file di testo semplice, delimitato da virgole, delimitato da tabulazioni o di altro formato delimitato in modo coerente. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file incrementale </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del semplice file di testo semplice, delimitato da virgole, delimitato da tabulazioni o di altro formato delimitato in modo coerente. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni Incremental Index. Se non viene specificato alcun file, viene utilizzato il file elencato in Percorso file. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file verticale </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del semplice file di testo semplice semplice, delimitato da virgole, delimitato da tabulazioni o di altro formato delimitato in modo coerente da utilizzare durante un aggiornamento verticale. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni di aggiornamento verticale. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elimina percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del file di testo semplice semplice semplice e semplice, contenente un singolo valore di identificatore del documento per riga. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni Incremental Index. I valori trovati in questo file vengono utilizzati per creare richieste di eliminazione per rimuovere documenti indicizzati in precedenza. I valori in questo file devono corrispondere ai valori trovati nei file Percorso file completo o Incrementale, nella colonna identificata come Chiave <span class="uicontrol"> primaria </span>. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Potete scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTP. </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTPS. </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>Per accedere al server FTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>Per accedere al server SFTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> File </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Timeout </p> </td> 
      <td colname="col2"> <p>Specifica il timeout, in secondi, per le connessioni FTP, SFTP, HTTP o HTTPS. Il valore deve essere compreso tra 30 e 300. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tentativi </p> </td> 
      <td colname="col2"> <p>Specifica il numero massimo di tentativi per connessioni FTP, SFTP, HTTP o HTTPS non riuscite. Il valore deve essere compreso tra 0 e 10. </p> <p>Un valore pari a zero (0) impedisce i tentativi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Codifica </p> </td> 
      <td colname="col2"> <p>Specifica il sistema di codifica dei caratteri utilizzato nel file di origine dati specificato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimitatore </p> </td> 
      <td colname="col2"> <p>Specifica il carattere da utilizzare per delineare ogni campo nel file di origine dati specificato. </p> <p>Il carattere virgola ( <span class="codeph"> , </span>) è un esempio di carattere di delimitazione. La virgola funge da delimitatore di campo per separare i campi dati nel file di origine dati specificato. </p> <p>Selezionare <span class="uicontrol"> Tab? </span> per utilizzare il carattere di delimitazione della tabulazione orizzontale. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Intestazioni nella prima riga </p> </td> 
      <td colname="col2"> <p>Indica che la prima riga del file di origine dati contiene solo informazioni di intestazione, non dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero minimo di documenti da indicizzare </p> </td> 
      <td colname="col2"> <p>Se è impostato su un valore positivo, questo specifica il numero minimo di record previsti nel file scaricato. Se vengono ricevuti meno record, l'operazione di indice viene interrotta. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. </p> <p> <b>Nota</b>: Questa funzione è utilizzata solo durante le operazioni con l'indice completo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Specifica le mappature tra colonne e metadati utilizzando i numeri di colonna. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Colonna </span> <p> Specifica un numero di colonna, con la prima colonna pari a 1 (una). Per aggiungere nuove righe di mappa per ciascuna colonna, in <span class="wintitle"> Azione </span>fare clic su <span class="uicontrol"> + </span>. </p> <p>Non è necessario fare riferimento a ogni colonna nell'origine dati. È invece possibile scegliere di saltare i valori. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag &lt;meta&gt; generato. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che <span class="uicontrol"> Field diventi </span> un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l'account corrente. </p> <p>Se necessario, il valore <span class="uicontrol"> Campo </span> può essere un campo di metadati non definito. Talvolta, un campo di metadati non definito è utile per creare contenuto utilizzato da <span class="wintitle"> Filtraggio script </span>. </p> <p>Vedere <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni Sul Filtro Degli Script </a>. </p> <p>Quando il connettore indice elabora documenti XML con più hit su qualsiasi campo mappa, i più valori vengono concatenati in un singolo valore nel documento memorizzato nella cache risultante. Per impostazione predefinita, questi valori vengono combinati mediante un delimitatore di virgola. Tuttavia, supponiamo che il valore <span class="wintitle"> Campo corrispondente </span> sia un campo di metadati definito. Inoltre, il campo dispone dell'attributo <span class="wintitle"> Consenti elenchi </span> impostato. In questo caso, il valore Delimitatori elenco del campo, che è il primo delimitatore definito, viene utilizzato nella concatenazione. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Chiave primaria? </span> <p>Una sola definizione di mappa è identificata come chiave primaria. Questo campo diventa il riferimento univoco presentato quando il documento viene aggiunto all'indice. Questo valore viene utilizzato nell'URL del documento nell'indice. </p> <p>I valori <span class="uicontrol"> Chiave primaria </span> devono essere univoci in tutti i documenti rappresentati dalla configurazione del connettore indice. Eventuali duplicati rilevati verranno ignorati. Se i documenti di origine non contengono un singolo valore univoco da utilizzare come <span class="uicontrol"> Chiave primaria </span>, ma due o più campi considerati insieme <i>possono</i> formare un unico identificatore, è possibile definire la Chiave <span class="uicontrol"> primaria </span> combinando più valori <span class="uicontrol"> di Colonna </span> con una barra verticale ("|") che delimita i valori. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> Rimuovere il codice HTML? </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo origine dati: Feed</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per la ricerca per indicizzazione e l’indicizzazione. In alternativa, è possibile disattivare la configurazione per impedire la ricerca per indicizzazione e l'indicizzazione. </p> <p> <b>Nota</b>: Le configurazioni del connettore indice disattivate vengono ignorate se sono presenti in un elenco entrypoint. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo IP o l'indirizzo URL del sistema host in cui viene trovato il file di origine dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML principale che contiene più "righe" di informazioni. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file incrementale </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML incrementale che contiene più "righe" di informazioni. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni Incremental Index. Se non viene specificato alcun file, viene utilizzato il file elencato in Percorso file. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file verticale </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML che contiene più "righe" di informazioni sparse da utilizzare durante un aggiornamento verticale. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni di aggiornamento verticale. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elimina percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del file di testo semplice semplice semplice e semplice, contenente un singolo valore di identificatore del documento per riga. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> <p>Questo file, se specificato, viene scaricato ed elaborato durante le operazioni Incremental Index. I valori trovati in questo file vengono utilizzati per creare richieste di eliminazione per rimuovere documenti indicizzati in precedenza. I valori in questo file devono corrispondere ai valori trovati nei file Percorso file completo o Incrementale, nella colonna identificata come Chiave <span class="uicontrol"> primaria </span>. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Potete scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTP. </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTPS. </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>Per accedere al server FTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>Per accedere al server SFTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> File </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Identifica l'elemento XML che è possibile utilizzare per identificare singole righe XML nel file di origine dati specificato. </p> <p>Ad esempio, nel seguente frammento Feed di un documento Adobe XML, il valore dell'elemento è <span class="codeph"> record </span>: </p> <p> <code> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
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
      <td colname="col1"> <p>Numero minimo di documenti da indicizzare </p> </td> 
      <td colname="col2"> <p>Se è impostato su un valore positivo, questo specifica il numero minimo di record previsti nel file scaricato. Se vengono ricevuti meno record, l'operazione di indice viene interrotta. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. </p> <p> <b>Nota</b>: Questa funzione è utilizzata solo durante le operazioni con l'indice completo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Consente di specificare le mappature XML da elemento a metadati utilizzando le espressioni XPath. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tag </span> <p>Specifica una rappresentazione XPath dei dati XML analizzati. Utilizzando il documento Adobe XML di esempio riportato sopra, sotto l'opzione Tag elemento, è possibile mapparlo utilizzando la sintassi seguente: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
      /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>La sintassi di cui sopra è la seguente: </p> <p> 
      <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
      <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>L' <span class="codeph"> attributo displayurl </span> dell'elemento del <span class="codeph"> record viene mappato sul campo di metadati </span> page-url <span class="codeph"> </span>. </p> </li> 
      <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi <span class="codeph"> </span> elemento meta contenuto all'interno di un elemento <span class="codeph"> metadati, contenuto all'interno di un elemento </span> record, il cui attributo name è <span class="codeph"> title </span> <span class="codeph"> </span><span class="codeph"> </span>, viene mappato sul titolo del campo di metadati, in modo da poter essere mappato sull'attributo del campo di metadati . </p> </li> 
      <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>L'attributo <span class="codeph"> di contenuto </span> di qualsiasi <span class="codeph"> </span> elemento meta contenuto all'interno di un elemento <span class="codeph"> metadati, contenuto all'interno dell'elemento </span> record, il cui attributo nome è <span class="codeph"> descrizione </span> <span class="codeph"> </span><span class="codeph"> </span>, viene mappato sul campo di metadati . </p> </li> 
      <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi <span class="codeph"> </span> elemento meta contenuto all'interno di un <span class="codeph"> elemento di </span> metadati, contenuto all'interno dell' <span class="codeph"> elemento del </span> record, il cui attributo name è <span class="codeph"> description </span><span class="codeph"> </span>, viene mappato sul corpo del campo di metadati . </p> </li> 
      </ul> </p> <p>XPath è una notazione relativamente complicata. Ulteriori informazioni sono disponibili nel seguente percorso: </p> <p>Consultate <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag <span class="codeph"> &lt;meta&gt; </span> generato. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che <span class="uicontrol"> Field diventi </span> un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l'account corrente. </p> <p>Se necessario, il valore <span class="uicontrol"> Campo </span> può essere un campo di metadati non definito. Talvolta, un campo di metadati non definito è utile per creare contenuto utilizzato da <span class="wintitle"> Filtraggio script </span>. </p> <p>Vedere <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni Sul Filtro Degli Script </a>. </p> <p>Quando il connettore indice elabora documenti XML con più hit su qualsiasi campo mappa, i più valori vengono concatenati in un singolo valore nel documento memorizzato nella cache risultante. Per impostazione predefinita, questi valori vengono combinati mediante un delimitatore di virgola. Tuttavia, supponiamo che il valore <span class="wintitle"> Campo corrispondente </span> sia un campo di metadati definito. Inoltre, il campo dispone dell'attributo <span class="wintitle"> Consenti elenchi </span> impostato. In questo caso, il valore Delimitatori elenco del campo, che è il primo delimitatore definito, viene utilizzato nella concatenazione. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Chiave primaria? </span> <p>Una sola definizione di mappa è identificata come chiave primaria. Questo campo diventa il riferimento univoco presentato quando il documento viene aggiunto all'indice. Questo valore viene utilizzato nell'URL del documento nell'indice. </p> <p>I valori <span class="uicontrol"> Chiave primaria </span> devono essere univoci in tutti i documenti rappresentati dalla configurazione del connettore indice. Eventuali duplicati rilevati verranno ignorati. Se i documenti di origine non contengono un singolo valore univoco da usare come Chiave <span class="uicontrol"> principale </span>, ma due o più campi considerati insieme <i>possono</i> formare un unico identificatore, potete definire la Chiave <span class="uicontrol"> primaria </span> combinando più <span class="uicontrol"> </span> definizioni di Tag con una barra verticale ("|") che delimita i valori. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC81F"> <span class="uicontrol"> Rimuovere il codice HTML? </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_5E829D1D0DBD4BB7AAB5DB983053D248"> <span class="uicontrol"> Utilizzate Elimina? </span> <p>Utilizzato solo durante le operazioni dell'indice incrementale. I record corrispondenti a questo pattern XPath identificano gli elementi da eliminare. Il valore <span class="uicontrol"> Chiave primaria </span> per ciascun record viene utilizzato per creare richieste di eliminazione, come con Elimina percorso file. </p> <p> <b>Nota</b>: Questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo origine dati: XML</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per la ricerca per indicizzazione e l’indicizzazione. In alternativa, è possibile disattivare la configurazione per impedire la ricerca per indicizzazione e l'indicizzazione. </p> <p> <b>Nota</b>: Le configurazioni del connettore indice disattivate vengono ignorate se sono presenti in un elenco entrypoint. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo URL del sistema host in cui viene trovato il file di origine dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML principale contenente i collegamenti ( 
      <userinput>
        &lt;a&gt; 
      </userinput>) in singoli documenti XML. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Potete scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_EA4EB7953D68483FAD75753B2EE70E74"> 
      <li id="li_537F24C6B2AB435CB7C14117663D7B3F"> HTTP <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTP. </p> </li> 
      <li id="li_8C13C93C52364FFA8B9B18830CDB223C"> HTTPS <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTPS. </p> </li> 
      <li id="li_2F967B5675254C949B31EAB19910751C"> FTP <p>Per accedere al server FTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_C24BE4C1DE79488AA64C7133D78CD3A6"> SFTP <p>Per accedere al server SFTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_7581C21CFC104986A361F62BD7A370C1"> File </li> 
      </ul> </p> <p> <b>Nota</b>: L'impostazione Protocollo viene utilizzata solo se sono specificate informazioni nei campi Indirizzo host e/o Percorso file. I singoli documenti XML vengono scaricati mediante HTTP o HTTPS, in base alle specifiche URL. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Identifica l'elemento XML che definisce una "riga" nel file di origine dati specificato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Consente di specificare le mappature tra colonne e metadati utilizzando i numeri di colonna. </p> <p> 
      <ul id="ul_06F50CBA0AA64C7CB1AFAE076E629A64"> 
      <li id="li_0FA2502869BA40DC93D790B79E15A9D2"> <span class="uicontrol"> Tag </span> <p>Specifica una rappresentazione XPath dei dati XML analizzati. Utilizzando il documento Adobe XML di esempio sopra, sotto l'opzione Tag elemento, potete eseguire la mappatura utilizzando la sintassi seguente: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>La sintassi di cui sopra è la seguente: </p> <p> 
      <ul id="ul_F8C536E6E54546D9AA5B22B879C0AF39"> 
      <li id="li_78A35DFFF1B4496CAC6EDC7B1E991F29"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>L' <span class="codeph"> attributo displayurl </span> dell'elemento del <span class="codeph"> record viene mappato sul campo di metadati </span> page-url <span class="codeph"> </span>. </p> </li> 
      <li id="li_FA7DF3D1942248B98660F3D0C82F4563"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi <span class="codeph"> </span> elemento meta contenuto all'interno di un elemento <span class="codeph"> metadati, contenuto all'interno di un elemento </span> record, il cui attributo name è <span class="codeph"> title </span> <span class="codeph"> </span><span class="codeph"> </span>, viene mappato sul titolo del campo di metadati, in modo da poter essere mappato sull'attributo del campo di metadati . </p> </li> 
      <li id="li_D8000A116FF84DE59ED19C656DDD3BC1"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>L'attributo <span class="codeph"> di contenuto </span> di qualsiasi <span class="codeph"> </span> elemento meta contenuto all'interno di un elemento <span class="codeph"> metadati, contenuto all'interno dell'elemento </span> record, il cui attributo nome è <span class="codeph"> descrizione </span> <span class="codeph"> </span><span class="codeph"> </span>, viene mappato sul campo di metadati . </p> </li> 
      <li id="li_7FA6A53DFD3D42A98B7BA17CC29DDB81"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi <span class="codeph"> </span> elemento meta contenuto all'interno di un <span class="codeph"> elemento di </span> metadati, contenuto all'interno dell' <span class="codeph"> elemento del </span> record, il cui attributo name è <span class="codeph"> description </span><span class="codeph"> </span>, viene mappato sul corpo del campo di metadati . </p> </li> 
      </ul> </p> <p>XPath è una notazione relativamente complicata. Ulteriori informazioni sono disponibili nel seguente percorso: </p> <p>Consultate <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_84999D07E0AE4265BC7928BBB49957B9"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag &lt;meta&gt; generato. </p> </li> 
      <li id="li_E125788D0F5242958BD790E26A675C20"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che <span class="uicontrol"> Field diventi </span> un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l'account corrente. </p> <p>Se necessario, il valore <span class="uicontrol"> Campo </span> può essere un campo di metadati non definito. Talvolta, un campo di metadati non definito è utile per creare contenuto utilizzato da <span class="wintitle"> Filtraggio script </span>. </p> <p>Vedere <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni Sul Filtro Degli Script </a>. </p> <p>Quando il connettore indice elabora documenti XML con più hit su qualsiasi campo mappa, i più valori vengono concatenati in un singolo valore nel documento memorizzato nella cache risultante. Per impostazione predefinita, questi valori vengono combinati mediante un delimitatore di virgola. Tuttavia, supponiamo che il valore <span class="wintitle"> Campo corrispondente </span> sia un campo di metadati definito. Inoltre, il campo dispone dell'attributo <span class="wintitle"> Consenti elenchi </span> impostato. In questo caso, il valore Delimitatori elenco del campo, che è il primo delimitatore definito, viene utilizzato nella concatenazione. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824609F"> <span class="uicontrol"> Chiave primaria? </span> <p>Una sola definizione di mappa è identificata come chiave primaria. Questo campo diventa il riferimento univoco presentato quando il documento viene aggiunto all'indice. Questo valore viene utilizzato nell'URL del documento nell'indice. </p> <p>I valori <span class="uicontrol"> Chiave primaria </span> devono essere univoci in tutti i documenti rappresentati dalla configurazione del connettore indice. Eventuali duplicati rilevati verranno ignorati. Se i documenti di origine non contengono un singolo valore univoco da usare come Chiave <span class="uicontrol"> principale </span>, ma due o più campi considerati insieme <i>possono</i> formare un unico identificatore, potete definire la Chiave <span class="uicontrol"> primaria </span> combinando più <span class="uicontrol"> </span> definizioni di Tag con una barra verticale ("|") che delimita i valori. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824610G"> <span class="uicontrol"> Rimuovere il codice HTML? </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_6302D18971AD439FBECE27742649C56B"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Fai clic **[!UICONTROL Setup Maps]** per scaricare un esempio dell’origine dati. I dati vengono esaminati per verificare l&#39;idoneità all&#39;indicizzazione. Questa funzione è disponibile solo per i tipi di testo e feed.
1. (Facoltativo) Fate clic **[!UICONTROL Preview]** per verificare il funzionamento effettivo della configurazione. Questa funzione è disponibile solo per i tipi di testo e feed.
1. Fate clic **[!UICONTROL Add]** per aggiungere la configurazione alla [!DNL Index Connector Definitions] pagina e all’elenco a [!DNL Index Connector Configurations] discesa sulla [!DNL URL Entrypoints] pagina.

   Consultate [I punti di ingresso](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)URL.
1. Sulla [!DNL Index Connector Definitions] pagina, fate clic su **[!UICONTROL rebuild your staged site index]**.
1. (Facoltativo) Nella [!DNL Index Connector Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica della definizione del connettore indice {#task_DCFC9C6A9964421DB5AB6C25DEE98DE9}

È possibile modificare un connettore indice esistente definito.

>[!NOTE]
>
>Non tutte le opzioni possono essere modificate, ad esempio Nome connettore indice o Tipo, dall&#39;elenco a [!DNL Type] discesa.

**Per modificare una definizione del connettore indice**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella [!DNL Index Connector] pagina, sotto l&#39;intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Edit]** per specificare il nome di definizione del connettore indice di cui si desidera modificare le impostazioni.
1. Nella [!DNL Index Connector Edit] pagina, impostate le opzioni desiderate.

   Vedere la tabella delle opzioni in [Aggiunta di una definizione](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886)del connettore indice.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella [!DNL Index Connector Definitions] pagina, fare clic su **[!UICONTROL rebuild your staged site index]**.
1. (Facoltativo) Nella [!DNL Index Connector Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Visualizzazione delle impostazioni di una definizione del connettore indice {#task_D0B71A7426E54247BDB3468EC576D871}

È possibile esaminare le impostazioni di configurazione di una definizione di connettore indice esistente.

Dopo che alla [!DNL Index Connector Definitions] pagina è stata aggiunta la definizione del connettore indice, non è possibile modificarne l&#39;impostazione Tipo. Al contrario, è necessario eliminare la definizione e aggiungerne una nuova.

**Per visualizzare le impostazioni di una definizione del connettore indice**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella [!DNL Index Connector] pagina, sotto l&#39;intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Edit]** per specificare il nome di definizione del connettore indice di cui si desidera esaminare o modificare le impostazioni.

## Copia della definizione di un connettore indice {#task_3AD55DF07FC44A748D0EFDAB7B35699B}

È possibile copiare una definizione del connettore indice esistente da usare come base per la creazione di un nuovo connettore indice.

Quando si copia una definizione del connettore indice, per impostazione predefinita la definizione copiata viene disabilitata. Per abilitare o &quot;attivare&quot; la definizione, è necessario modificarla dalla [!DNL Index Connector Edit] pagina e selezionare **[!UICONTROL Enable]**.

Vedere [Modifica della definizione](../c-about-settings-menu/c-about-crawling-menu.md#task_DCFC9C6A9964421DB5AB6C25DEE98DE9)di un connettore indice.

**Per copiare una definizione del connettore indice**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella [!DNL Index Connector] pagina, sotto l&#39;intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Copy]** per specificare il nome di definizione del connettore indice di cui si desidera duplicare le impostazioni.
1. Nella [!DNL Index Connector Copy] pagina, immettete il nuovo nome della definizione.
1. Clic **[!UICONTROL Copy]**.
1. (Facoltativo) Nella [!DNL Index Connector Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Ridenominazione della definizione del connettore indice {#task_5132118FC21B47D99881E0ED425225D7}

È possibile modificare il nome di una definizione del connettore indice esistente.

Dopo aver rinominato la definizione, selezionare **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Accertarsi che il nuovo nome della definizione sia riportato nell’elenco a discesa della [!DNL URL Entrypoints] pagina.

Consultate [Aggiunta di più punti di ingresso URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

**Per rinominare una definizione del connettore indice**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella [!DNL Index Connector] pagina, sotto l’intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Rename]** per il nome della definizione del connettore indice che si desidera modificare.
1. Nella [!DNL Index Connector Rename] pagina, immettere il nuovo nome della definizione nel [!DNL Name] campo.
1. Clic **[!UICONTROL Rename]**.
1. Fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Se nell&#39;elenco è presente il nome del connettore indice precedente, rimuoverlo e aggiungere la voce rinominata di recente.

   Consultate [Aggiunta di più punti di ingresso URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45). 1. (Facoltativo) Nella [!DNL Index Connector Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di una definizione del connettore indice {#task_6B0BD5D0C09F4597A401B0F3AC7C7EA7}

È possibile eliminare una definizione del connettore indice esistente non più necessaria o utilizzata.

**Per eliminare una definizione del connettore indice**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Nella [!DNL Index Connector Definitions] pagina, sotto l’intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Delete]** sul nome della definizione del connettore indice da rimuovere.
1. Sulla [!DNL Index Connector Delete] pagina, fate clic su **[!UICONTROL Delete]**.
