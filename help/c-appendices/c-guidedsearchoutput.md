---
description: Potete personalizzare l’output in qualsiasi formato basato su testo, inclusi XML o JSON.
seo-description: Potete personalizzare l’output in qualsiasi formato basato su testo, inclusi XML o JSON.
seo-title: Uscita di ricerca guidata
solution: Target
title: Uscita di ricerca guidata
topic: Appendices,Site search and merchandising
uuid: 234fd563-f249-42b0-88ca-c89b44f8df77
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '6298'
ht-degree: 2%

---


# Uscita di ricerca guidata{#guided-search-output}

Potete personalizzare l’output in qualsiasi formato basato su testo, inclusi XML o JSON.

## Utilizzo dell&#39;output di ricerca guidata {#concept_2A1BA3AD413848A1AC2A3ABC4FFE481F}

Il formato di output è personalizzabile per supportare il facet, l&#39;ordinamento e altre decisioni specifiche per l&#39;implementazione che vengono prese durante il processo di progettazione. Potete adattare il formato stesso per semplificare lo sviluppo del front-end del cliente, se necessario.

L&#39;intero output è contenuto all&#39;interno dei tag `<result>` e la maggior parte dei dati dinamici è racchiusa tra `<![CDATA[ ]]>` tag. Tale organizzazione consente ai risultati di contenere HTML e altre entità non XML.

Se vengono forniti collegamenti verso altre pagine, questi vengono presentati sotto forma di URL relativo. Questo risultato include anche i parametri della stringa di query passati per generare il risultato desiderato.

## Introduzione all&#39;implementazione di una ricerca guidata {#section_95483980930C4325BAB50A40BD47245A}

Quando iniziate l&#39;implementazione di una ricerca guidata, ricordate che [!DNL Adobe Search&Promote] è responsabile per il livello aziendale. Ovvero, la logica che circonda i risultati e i facet vengono mostrati a un cliente in qualsiasi momento.

Quando si implementa il front-end dell&#39;applicazione Web che analizza e visualizza i risultati come HTML, limitare la funzionalità alla sola visualizzazione. In altre parole, qualsiasi logica lato server utilizzata per creare il Livello presentazione non prende decisioni su cosa presentare al cliente, a meno che non sia necessario. Le regole business non funzionano come previsto se lo script front-end modifica i risultati della ricerca.

[!DNL Adobe Search&Promote] mantiene lo stato utente delle opzioni di perfezionamento ricerca selezionate tramite i parametri dell’URL. Tutti i nodi `<link>` contengono i parametri pertinenti delle selezioni del cliente. Questi parametri possono includere breadcrumb, impaginazione, ordinamento e facet. Se applicabile, vengono restituiti `<undolink>` nodi per consentire al cliente di &quot;eseguire il backup&quot; di una selezione. Facet e breadcrumb offrono questi tipi di collegamenti.

## Utilizzo del server di ricerca {#section_8DBEACDECD714E59BDED6315E6041B8D}

Viene utilizzata un&#39;API REST-like con la quale potete interagire per eseguire ricerche e ricevere risultati. I formati più comuni utilizzati per i risultati sono XML o JSON.

L&#39;URI di base è associato a un account specifico e a un ambiente in fase o in diretta. Potete richiedere più alias per l&#39;URI di base al vostro account manager. Ad esempio, a una società fittizia denominata Megacorp sono associati i due URL di base seguenti:

* `https://search.megacorp.com `
* `https://stage.megacorp.com`

Il primo URI esegue le ricerche rispetto al relativo indice live e il secondo rispetto al relativo indice in fase di esecuzione.

Le richieste di ricerca sono costituite dall’URI di base e da un set di parametri CGI o coppie chiave-valore che indicano la ricerca desiderata per l’account associato all’URI di base.

Sono supportati tre formati di parametri CGI. Per impostazione predefinita, il vostro account è configurato per separare i parametri CGI con un punto e virgola ( `;`), come nell&#39;esempio seguente:

* `https://search.megacorp.com?q=shoes ;page=2`

Se preferite, potete fare in modo che il vostro account manager configuri il vostro account in modo che utilizzi le e commerciale ( `&`) per separare i parametri CGI, come nell&#39;esempio seguente:

* `https://search.megacorp.com?q=shoes &page=2`

È inoltre supportato un terzo formato, denominato formato SEO, in cui viene utilizzata una barra ( `/`) al posto del separatore e un segno di uguale per generare collegamenti &quot;puliti&quot;, come nell&#39;esempio seguente:

* `https://search.megacorp.com/q/shoes/page/2`

Ogni volta che il formato SEO viene utilizzato per inviare una richiesta, tutti i collegamenti di output vengono restituiti nello stesso formato.

## Parametri query di ricerca {#section_7ADA5E130E3040C9BE85D0D68EDD3223}

Nella tabella seguente sono descritti i parametri standard di query di ricerca &quot;out-of-the-box&quot; utilizzabili. Le regole di elaborazione e le regole aziendali possono essere create sulla base di parametri di query definiti dall&#39;utente per implementare una logica aziendale personalizzata rilevante per la tua azienda. Potete collaborare con il team di consulenza per ottenere la documentazione su tali parametri.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Parametro query di ricerca </p> </th> 
   <th colname="col2" class="entry"> <p>Esempio </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q= stringa  </span> </p> </td> 
   <td colname="col3"> <p> Specifica la stringa di query per la ricerca. Questo parametro viene mappato sul parametro di ricerca di back-end <span class="codeph"> sp_q </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q#  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q#= stringa  </span> </p> </td> 
   <td colname="col3"> <p>I parametri <span class="codeph"> q </span> e <span class="codeph"> x </span> numerati consentono di eseguire operazioni di facet o ricerche all'interno di un dato campo. </p> <p>Il parametro <span class="codeph"> q </span> definisce il termine che si sta cercando nel facet come il parametro numero corrispondente <span class="codeph"> x </span> denotes. Ad esempio, se avete due facet denominati dimensione e colore, potreste avere qualcosa come il seguente: </p> <p> <span class="codeph"> q1=piccolo;x1=dimensione;q2=rosso;x2=colore  </span> </p> <p>Questo parametro viene mappato sui parametri di ricerca di back-end <span class="codeph"> sp_q_exact_# </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> x# </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> x#= stringa  </span> </p> </td> 
   <td colname="col3"> <p> I parametri <span class="codeph"> q </span> e <span class="codeph"> x </span> numerati consentono di eseguire operazioni di facet o ricerche all'interno di un dato campo. </p> <p>Il parametro <span class="codeph"> q </span> definisce il termine che si sta cercando nel facet come il parametro numero corrispondente <span class="codeph"> x </span> denotes. Ad esempio, se avete due facet denominati dimensione e colore, potreste avere qualcosa come il seguente: </p> <p> <span class="codeph"> q1=piccolo;x1=dimensione;q2=rosso;x2=colore  </span> </p> <p>Questo parametro viene mappato sui parametri di ricerca di back-end <span class="codeph"> sp_x_# </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> raccolta </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> collection= string  </span> </p> </td> 
   <td colname="col3"> <p> Specifica la raccolta da utilizzare per la ricerca. Questo parametro viene mappato sul parametro di ricerca di back-end <span class="codeph"> sp_k </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> count  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> count= number  </span> </p> </td> 
   <td colname="col3"> <p> Specifica il conteggio totale dei risultati visualizzati. Il valore predefinito è definito in <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Ricerca </span> &gt; <span class="uicontrol"> Ricerche </span>. Questo parametro viene mappato sul parametro di ricerca di back-end <span class="codeph"> sp_c </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> page </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> page= number  </span> </p> </td> 
   <td colname="col3"> <p> Specifica la pagina dei risultati restituiti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> rank  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> rank= field  </span> </p> </td> 
   <td colname="col3"> <p> Specifica il campo di classificazione da utilizzare per la classificazione statica. Il campo deve essere un campo di tipo Classifica con rilevanza maggiore di 0. Questo parametro viene mappato sul parametro di backend <span class="codeph"> sp_sr </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> gs_store  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> gs_store= stringa  </span> </p> </td> 
   <td colname="col3"> <p> Specifica lo store da cercare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sort  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> sort= number  </span> </p> </td> 
   <td colname="col3"> <p> Specifica l'ordinamento. "0" è l'impostazione predefinita e ordina per punteggio di rilevanza; "1", per data; "-1" non esegue l'ordinamento. </p> <p>Gli utenti possono specificare un nome di campo per il valore del parametro <span class="codeph"> sp_s </span>. Ad esempio, <span class="codeph"> sp_s=title </span> ordina i risultati in base ai valori contenuti nel campo title. Quando un nome di campo viene utilizzato per il valore di un parametro <span class="codeph"> sp_s </span>, i risultati vengono ordinati in base a tale campo e quindi suddivisi per rilevanza. </p> <p>Per attivare questa funzione, effettuate le seguenti operazioni: </p> 
    <ol id="ol_3894F81EA7BF4827A84DE8662111ABEF"> 
     <li id="li_C040C0B88F174A4885E1A8E721FD032A">Nel menu del prodotto, fate clic su <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Definizioni </span>. </li> 
     <li id="li_2E83C3A46D1B4BF991EABAD9D3E52B7D">Nella pagina <span class="wintitle"> Definizioni intermedie </span>, effettuare una delle seguenti operazioni: 
      <ul id="ul_8018FEE10E0A4C96A74F84A897080580"> 
       <li id="li_E9A7CE43E2734F4D9522A1283CA111FB">Fare clic su <span class="uicontrol"> Aggiungi nuovo campo </span>. </li> 
       <li id="li_9D2434A321924FBD874569CA9AD2EEF7">Fare clic su <span class="uicontrol"> Modifica </span> per specificare il nome di un campo. </li> 
      </ul> </li> 
     <li id="li_90D5E3F4AC0A4A6189934A5589F69903">Nell'elenco a discesa <span class="wintitle"> Ordinamento </span>, fare clic su <span class="uicontrol"> Crescente </span> o <span class="uicontrol"> Decrescente </span>. <p>Questo parametro viene mappato sul parametro di ricerca di back-end <span class="codeph"> sp_s </span>. </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Integrazione con il sistema {#section_91261B19A44A4E579B3FC9FAB9AD3665}

Di seguito sono riportati alcuni suggerimenti per l&#39;integrazione con il sistema.

* Comunicazione con il server di ricerca.

   È possibile comunicare con i server Web [!DNL Adobe Search&Promote] utilizzando le richieste HTTP. I server generano tali richieste o sul lato client che esegue una richiesta Ajax.
* Salvataggio della cronologia di ricerca.

[!DNL Adobe Search&Promote] è stateless in cui viene passato l’intero stato nella richiesta http.
* Analisi dei risultati restituiti.

   Si consiglia di utilizzare un parser XML basato su SAX per analizzare la risposta XML. Se state generando una richiesta Ajax, configurate [!DNL Adobe Search&Promote] per restituire le risposte JSON per tali richieste, in modo da facilitare l&#39;analisi della risposta.

## Ricerca guidata Output JSON {#reference_EB8182A564DE4374BB84158F2AABEF74}

Tabelle che descrivono l’output di risposta JSON standard.

Vedere anche [Guided Search JSON Output](../c-appendices/c-guidedsearchoutput.md#reference_EB8182A564DE4374BB84158F2AABEF74).

Potete esaminare la risposta JSON per i seguenti elementi:

* [Banner](../c-appendices/c-guidedsearchoutput.md#section_88519CAAD25F4BD49D5E517077745B0E)
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_A7DB0F1DA9ED4CBCAE18395122F3E01E)
* [Facet](../c-appendices/c-guidedsearchoutput.md#section_65932C95931743A1BFAF1DF16D7E6D92)
* [Intestazione e query](../c-appendices/c-guidedsearchoutput.md#section_1D57062259CA46E0B4F598FA4EB37065)
* [Paginazione](../c-appendices/c-guidedsearchoutput.md#section_504E7AB570BD49AF9839530DC438EE96)
* [Ricerche recenti](../c-appendices/c-guidedsearchoutput.md#section_525816A0355C48F8970D89B8FC3F1FFF)
* [Risultati](../c-appendices/c-guidedsearchoutput.md#section_41AC56BB0A084BF59379B06C8BEF2157)
* [Modulo di ricerca](../c-appendices/c-guidedsearchoutput.md#section_434DA13EA295474C99FFE9F14801CD0E)
* [Ordina](../c-appendices/c-guidedsearchoutput.md#section_558853CD376F4D71BACF211D53085D55)
* [Suggerimenti](../c-appendices/c-guidedsearchoutput.md#section_6EC104E1DDD94AC799B65E6E61A2FB3C)
* [Zone](../c-appendices/c-guidedsearchoutput.md#section_AE53A498B440465EAF2286F2AE87D548)

## Banner {#section_88519CAAD25F4BD49D5E517077745B0E}

Esempio:

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nei banner </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un singolo nodo di banner. Potete avere più nodi banner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> Area della pagina Web in cui viene visualizzato il banner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;contenuto&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il contenuto HTML per l'area del banner. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_A7DB0F1DA9ED4CBCAE18395122F3E01E}

Nell&#39;esempio seguente, ogni volta che il cliente si restringe ulteriormente attraverso i facet, la selezione viene aggiunta alla breadcrumb. Ogni elemento è rappresentato come `<breadcrumb-item>`.

Esempio:

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag in Breadcrumb </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un collegamento relativo ai risultati della ricerca che mostra la visualizzazione desiderata. Facendo clic su un collegamento di breadcrumb, il cliente viene visualizzato in cui vengono rimossi tutti i miglioramenti successivi. Sono disponibili anche altre opzioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Testo rivolto al cliente per l’elemento breadcrumb. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facet {#section_65932C95931743A1BFAF1DF16D7E6D92}

I facet sono opzioni di perfezionamento che consentono ai clienti di filtrare in base ai risultati. I facet sono comunemente utilizzati per la categorizzazione, le fasce di prezzo, le selezioni di colore e altri miglioramenti degli attributi. I metadati nell&#39;indice sono i fattori che determinano la gestione dei facet.

È comune nascondere o mostrare i facet di categorizzazione quando un cliente passa attraverso la categorizzazione. Il livello più elevato di classificazione (categoria) è noto come livello 1. Quando un cliente fa clic su un&#39;opzione di livello 1, vengono visualizzate le opzioni di perfezionamento di livello 2 (sottocategoria) e le opzioni di livello 1 scompaiono. Quando un cliente fa clic su un&#39;opzione Livello 2, vengono visualizzate le opzioni di perfezionamento Livello 3 (sottocategoria) e le opzioni Livello 2 scompaiono. Come indicato in precedenza, queste opzioni sono nascoste e l&#39;applicazione Web non viene influenzata da esse.

Ogni facet è contenuto all&#39;interno di `<facet-item>` tag. Nell&#39;esempio seguente, viene visualizzato un facet che consente al cliente di perfezionare i risultati della ricerca per &quot;festività&quot;.

Esempio:

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item> 
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag in facet </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Titolo rivolto al cliente per il facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Etichetta rivolta al cliente per l’opzione facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Collegamento relativo ai risultati ridotti dall’opzione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il numero di risultati nel set di risultati raffinato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> Quando viene selezionato un valore facet, il nodo restituisce un "collegamento di annullamento" che consente al cliente di tornare indietro dai risultati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Intestazione e query {#section_1D57062259CA46E0B4F598FA4EB37065}

Esempio:

```xml
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

Utilizzati insieme, questi tag presentano un messaggio come: &quot;Risultati 1-16 di 621 per &#39;nuovo anno&#39;.&quot;

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nell’intestazione e nella query </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> Query parola chiave inviata con la richiesta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Numero elemento del primo risultato in questa pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il numero dell'ultimo risultato su questa pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il numero totale di risultati che corrispondono alla query utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un campo facoltativo che si applica globalmente ai risultati della ricerca. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Impaginazione {#section_504E7AB570BD49AF9839530DC438EE96}

Esempio:

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nell'impaginazione </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> Numero totale di pagine di risultati, in base al numero di risultati diviso per il numero di risultati per pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo alla prima pagina del set di risultati, a meno che il cliente non stia già visualizzando la pagina 1. In tal caso, è vuota. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo all'ultima pagina del set di risultati, a meno che il cliente non visualizzi l'ultima pagina. In tal caso, è vuota. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo alla pagina precedente nel set di risultati, a meno che il cliente non visualizzi la pagina 1; in tal caso, è vuota. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo all'ultima pagina del set di risultati, a meno che il cliente non visualizzi l'ultima pagina. In tal caso, è vuota. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo a un particolare numero di pagina. Vengono visualizzati dieci numeri di pagina contigui. A pagina 1, sarebbero le pagine 1-10. Alla fine del set di risultati (in questo caso, 39), sarebbero le pagine 30-39. Ad esempio, al centro del set di risultati, pagina 15, si trovano le pagine 11-20. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> Applicato come attributo alla pagina attualmente selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ricerche recenti {#section_525816A0355C48F8970D89B8FC3F1FFF}

Ricerche recenti è una funzione basata su cookie che funziona solo se inviate le informazioni sui cookie ai server.

Esempio:

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nelle ricerche recenti </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un singolo nodo di ricerca recente. Potete avere più nodi di ricerca recenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> Termine ricercato in precedenza dal cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Collegamenti alla ricerca precedente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risultati {#section_41AC56BB0A084BF59379B06C8BEF2157}

L&#39;insieme Results (Risultati) è un&#39;area personalizzabile della risposta JSON. Ogni indice è univoco nei meccanismi di denominazione dei campi dei metadati. Esistono campi comuni che vengono restituiti per ogni risultato, ad esempio titolo, descrizione e URL. Tuttavia, tutti i metadati definiti per una pagina nell&#39;indice possono diventare disponibili per l&#39;utilizzo in ciascun nodo di risultati. Categorizzazione, prezzi, colori e miniature sono solo alcune delle opzioni che potete applicare a un risultato per produrre risultati di ricerca più coinvolgenti.

Il formato Risultati viene personalizzato in base ai metadati specifici per l’implementazione. Tutti i dati per risultato visualizzati nei risultati, inclusi gli URL delle miniature, sono contenuti in questo riquadro.

Inoltre, è possibile configurare più aree risultati all&#39;interno della pagina, ad esempio &quot;Risultati contenuti&quot; o sezioni separate di risultati &quot;Prodotti&quot; e &quot;Contenuto&quot;. In questi casi, all’interno dell’HTML vengono fornite più zone risultato, anche se i facet sono associati solo al set di risultati principale.

Esempio:

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nei risultati </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> Numero di serie del risultato all'interno del set di risultati. In questo esempio, se dieci risultati vengono visualizzati per pagina, a pagina 2 dei risultati, il primo elemento avrà un indice pari a 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Titolo rivolto al cliente per questa pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> URL per la pagina. Viene utilizzato per creare un collegamento ipertestuale che consente al cliente di scorrere i risultati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modulo di ricerca {#section_434DA13EA295474C99FFE9F14801CD0E}

Esempio:

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nel modulo di ricerca </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> Facoltativo. Se presente in JSON, un valore pari a 1 indica che l'account è collegato a <span class="keyword"> Test&amp;Target </span> e ha almeno una regola business che si trova in un test A:B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> Facoltativo. Quando si utilizza la funzione di completamento automatico, questo nodo è presente per indicare che CSS e JavaScript sono presenti nella pagina insieme al contenuto presente nel modulo. In genere questi campi non vengono modificati a meno che qualcuno non abbia modificato un'impostazione di completamento automatico. In tali casi, il campo xxx_cache_ver viene incrementato per forzare l'annullamento della validità del contenuto memorizzato nella cache nel browser del cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il CSS associato al completamento automatico. Per migliorare il rendering della pagina, si consiglia di posizionare questo tag in alto nella pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contenuto richiesto all'interno della ricerca per l'utilità di completamento automatico per collegarsi al controllo corretto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> JavaScript personalizzato richiesto per il completamento automatico. Per migliorare il rendering della pagina, si consiglia di posizionare il tag in basso nella pagina. Il codice JavaScript YUI è necessario anche per la compilazione automatica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene tutti i parametri nascosti (nome e valore) da includere nel modulo di ricerca. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ordina {#section_558853CD376F4D71BACF211D53085D55}

L&#39;esempio seguente mostra i dati per un menu di ordinamento a tre opzioni. Il menu consente al cliente di ordinare in base a rilevanza, titolo o valutazione. L&#39;elemento selezionato include un attributo &quot;selected=true&quot;. &quot;. Offri sempre un’opzione di rilevanza per consentire al cliente di tornare ai risultati di ricerca predefiniti visualizzati originariamente.

Esempio:

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nel menu Ordina </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Testo rivolto al cliente per l’opzione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Rappresenta il valore del parametro della stringa di query di ordinamento per questa opzione. Questo tag non è necessario se viene utilizzato il valore <span class="codeph"> &lt;link&gt; </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Per le opzioni non selezionate, il parametro <span class="codeph"> &lt;link&gt; </span> contiene il collegamento relativo che restituisce lo stesso set di risultati, ordinato in base al nuovo parametro di ordinamento. Questo campo è vuoto per l'opzione di ordinamento attualmente selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suggerimenti {#section_6EC104E1DDD94AC799B65E6E61A2FB3C}

I suggerimenti vengono restituiti quando sono presenti solo pochi risultati o nessun risultato. Questo nodo contiene termini che generano query di successo e che possono essere visualizzati su una pagina &quot;Nessun risultato&quot;. Viene inoltre restituito il collegamento in modo che il cliente possa passare alla nuova query.

Esempio:

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag in Suggerimenti </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Collegamento relativo usato per creare un collegamento ipertestuale per cercare i risultati del termine del suggerimento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>Il termine suggerito. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zone {#section_AE53A498B440465EAF2286F2AE87D548}

Esempio:

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nelle aree </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un singolo nodo di zona. È possibile avere più nodi di area. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> Nome della zona. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1 o 0 per indicare se la zona è o non è visualizzata. Il contenuto dell'area effettiva può essere un'area statica sulla pagina Web o nei risultati della ricerca, ad esempio i migliori venditori o i prodotti correlati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Uscita XML di ricerca guidata {#reference_D93E859A277643068B10AE7A61C973EA}

Tabelle che descrivono l&#39;output di risposta XML standard.

Potete esaminare la risposta XML per i seguenti elementi:

* [Banner](../c-appendices/c-guidedsearchoutput.md#section_6A19EC26DD3B494194AAA788151B78B5)
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_E48A71B0EBDB4EDDA7587009AD865488)
* [Facet](../c-appendices/c-guidedsearchoutput.md#section_5CEB1F966C004FFEA3CF675638966E25)
* [Intestazione e query](../c-appendices/c-guidedsearchoutput.md#section_802835E19BCB48239C6770A1B72DFFF8)
* [Paginazione](../c-appendices/c-guidedsearchoutput.md#section_72DB86DDE1284B1EA295CFFBC16A3150)
* [Ricerche recenti](../c-appendices/c-guidedsearchoutput.md#section_BCA2DDD17F264CF6BA11634E1A514E28)
* [Risultati](../c-appendices/c-guidedsearchoutput.md#section_EC496F5CA2634158891455E2F6DF6833)
* [Modulo di ricerca](../c-appendices/c-guidedsearchoutput.md#section_F92D8C3D37174A10A4E26CAFF3F3DF89)
* [Ordina](../c-appendices/c-guidedsearchoutput.md#section_32DC50A103BF491BA3665A5CADCCAADE)
* [Suggerimenti](../c-appendices/c-guidedsearchoutput.md#section_D81BCE46F0AF443695DF9C4BA084B716)
* [Zone](../c-appendices/c-guidedsearchoutput.md#section_15D8AA585F3246799968BA88EE2C9FC2)

## Banner {#section_6A19EC26DD3B494194AAA788151B78B5}

Esempio:

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nei banner </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un singolo nodo di banner. Potete avere più nodi banner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> Area della pagina Web in cui viene visualizzato il banner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;contenuto&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il contenuto HTML per l'area del banner. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_E48A71B0EBDB4EDDA7587009AD865488}

Nell&#39;esempio seguente, ogni volta che il cliente si restringe ulteriormente attraverso i facet, la selezione viene aggiunta alla breadcrumb. Ogni elemento è rappresentato come `<breadcrumb-item>`.

Esempio:

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag in Breadcrumb </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un collegamento relativo ai risultati della ricerca che mostra la visualizzazione desiderata. Facendo clic su un collegamento di breadcrumb, il cliente viene visualizzato in cui vengono rimossi tutti i miglioramenti successivi. Sono disponibili anche altre opzioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Testo rivolto al cliente per l’elemento breadcrumb. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facet {#section_5CEB1F966C004FFEA3CF675638966E25}

I facet sono opzioni di perfezionamento che consentono ai clienti di filtrare in base ai risultati. I facet sono comunemente utilizzati per la categorizzazione, le fasce di prezzo, le selezioni di colore e altri miglioramenti degli attributi. I metadati nell&#39;indice sono i fattori che determinano la gestione dei facet.

È comune nascondere o mostrare i facet di categorizzazione quando un cliente passa attraverso la categorizzazione. Il livello più elevato di classificazione (categoria) è noto come livello 1. Quando un cliente fa clic su un&#39;opzione di livello 1, vengono visualizzate le opzioni di perfezionamento di livello 2 (sottocategoria) e le opzioni di livello 1 scompaiono. Quando un cliente fa clic su un&#39;opzione Livello 2, vengono visualizzate le opzioni di perfezionamento Livello 3 (sottocategoria) e le opzioni Livello 2 scompaiono. Come indicato in precedenza, queste opzioni sono nascoste e l&#39;applicazione Web non viene influenzata da esse.

Ogni facet è contenuto all&#39;interno di `<facet-item>` tag. Nell&#39;esempio seguente, viene visualizzato un facet che consente al cliente di perfezionare i risultati della ricerca per &quot;festività&quot;.

Esempio:

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item>  
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag in facet </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Titolo rivolto al cliente per il facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Etichetta rivolta al cliente per l’opzione facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Collegamento relativo ai risultati ridotti dall’opzione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il numero di risultati nel set di risultati raffinato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> Quando viene selezionato un valore facet, il nodo restituisce un "collegamento di annullamento" che consente al cliente di tornare indietro dai risultati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Intestazione e query {#section_802835E19BCB48239C6770A1B72DFFF8}

Esempio:

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

Utilizzati insieme, questi tag presentano un messaggio come: &quot;Risultati 1-16 di 621 per &#39;nuovo anno&#39;.&quot;

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag in intestazione e query </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> Query parola chiave inviata con la richiesta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Numero elemento del primo risultato in questa pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il numero dell'ultimo risultato su questa pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il numero totale di risultati che corrispondono alla query utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un campo facoltativo che si applica globalmente ai risultati della ricerca. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Impaginazione {#section_72DB86DDE1284B1EA295CFFBC16A3150}

Esempio:

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nell'impaginazione </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> Numero totale di pagine di risultati, in base al numero di risultati diviso per il numero di risultati per pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo alla prima pagina del set di risultati, a meno che il cliente non stia già visualizzando la pagina 1. In tal caso, è vuota. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo all'ultima pagina del set di risultati, a meno che il cliente non visualizzi l'ultima pagina. In tal caso, è vuota. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo alla pagina precedente nel set di risultati, a meno che il cliente non visualizzi la pagina 1; in tal caso, è vuota. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo all'ultima pagina del set di risultati, a meno che il cliente non visualizzi l'ultima pagina. In tal caso, è vuota. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> Contiene un collegamento relativo a un particolare numero di pagina. Vengono visualizzati dieci numeri di pagina contigui. A pagina 1, sarebbero le pagine 1-10. Alla fine del set di risultati (in questo caso, 39), sarebbero le pagine 30-39. Ad esempio, al centro del set di risultati, pagina 15, si trovano le pagine 11-20. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> Applicato come attributo alla pagina attualmente selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ricerche recenti {#section_BCA2DDD17F264CF6BA11634E1A514E28}

Ricerche recenti è una funzione basata su cookie che funziona solo se inviate le informazioni sui cookie ai server.

Esempio:

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nelle ricerche recenti </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un singolo nodo di ricerca recente. Potete avere più nodi di ricerca recenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> Termine ricercato in precedenza dal cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Collegamenti alla ricerca precedente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risultati {#section_EC496F5CA2634158891455E2F6DF6833}

L&#39;insieme Results (Risultati) è un&#39;area personalizzabile della risposta XML. Ogni indice è univoco nei meccanismi di denominazione dei campi dei metadati. Esistono campi comuni che vengono restituiti per ogni risultato, ad esempio titolo, descrizione e URL. Tuttavia, tutti i metadati definiti per una pagina nell&#39;indice possono diventare disponibili per l&#39;utilizzo in ciascun nodo di risultati. Categorizzazione, prezzi, colori e miniature sono solo alcune delle opzioni che potete applicare a un risultato per produrre risultati di ricerca più coinvolgenti.

Il formato Risultati viene personalizzato in base ai metadati specifici per l’implementazione. Tutti i dati per risultato visualizzati nei risultati, inclusi gli URL delle miniature, sono contenuti in questo riquadro.

Inoltre, è possibile configurare più aree risultati all&#39;interno della pagina, ad esempio &quot;Risultati contenuti&quot; o sezioni separate di risultati &quot;Prodotti&quot; e &quot;Contenuto&quot;. In questi casi, all’interno dell’HTML vengono fornite più zone risultato, anche se i facet sono associati solo al set di risultati principale.

Esempio:

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nei risultati </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> Numero di serie del risultato all'interno del set di risultati. In questo esempio, se dieci risultati vengono visualizzati per pagina, a pagina 2 dei risultati, il primo elemento avrà un indice pari a 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Titolo rivolto al cliente per questa pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> URL per la pagina. Viene utilizzato per creare un collegamento ipertestuale che consente al cliente di scorrere i risultati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modulo di ricerca {#section_F92D8C3D37174A10A4E26CAFF3F3DF89}

Esempio:

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nel modulo di ricerca </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> Facoltativo. Quando è presente nel codice XML, un valore pari a 1 indica che l'account è collegato a <span class="keyword"> Test&amp;Target </span> e ha almeno una regola business presente in un test A:B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> Facoltativo. Quando si utilizza la funzione di completamento automatico, questo nodo è presente per indicare che CSS e JavaScript sono presenti nella pagina insieme al contenuto presente nel modulo. In genere questi campi non vengono modificati a meno che qualcuno non abbia modificato un'impostazione di completamento automatico. In tali casi, il campo xxx_cache_ver viene incrementato per forzare l'annullamento della validità del contenuto memorizzato nella cache nel browser del cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> Il CSS associato al completamento automatico. Per migliorare il rendering della pagina, si consiglia di posizionare questo tag in alto nella pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contenuto richiesto all'interno della ricerca per l'utilità di completamento automatico per collegarsi al controllo corretto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> JavaScript personalizzato richiesto per il completamento automatico. Per migliorare il rendering della pagina, si consiglia di posizionare il tag in basso nella pagina. Il codice JavaScript YUI è necessario anche per la compilazione automatica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contiene tutti i parametri nascosti (nome e valore) da includere nel modulo di ricerca. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ordina {#section_32DC50A103BF491BA3665A5CADCCAADE}

L&#39;esempio seguente mostra i dati per un menu di ordinamento a tre opzioni. Il menu consente al cliente di ordinare in base a rilevanza, titolo o valutazione. L&#39;elemento selezionato include un attributo &quot;selected=true&quot;. &quot;. Offri sempre un’opzione di rilevanza per consentire al cliente di tornare ai risultati di ricerca predefiniti visualizzati originariamente.

Esempio:

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nel menu Ordina </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Testo rivolto al cliente per l’opzione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Rappresenta il valore del parametro della stringa di query di ordinamento per questa opzione. Questo tag non è necessario se viene utilizzato il valore <span class="codeph"> &lt;link&gt; </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Per le opzioni non selezionate, il parametro <span class="codeph"> &lt;link&gt; </span> contiene il collegamento relativo che restituisce lo stesso set di risultati, ordinato in base al nuovo parametro di ordinamento. Questo campo è vuoto per l'opzione di ordinamento attualmente selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suggerimenti {#section_D81BCE46F0AF443695DF9C4BA084B716}

I suggerimenti vengono restituiti quando sono presenti solo pochi risultati o nessun risultato. Questo nodo contiene termini che generano query di successo e che possono essere visualizzati su una pagina &quot;Nessun risultato&quot;. Viene inoltre restituito il collegamento in modo che il cliente possa passare alla nuova query.

Esempio:

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag in Suggerimenti </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Collegamento relativo usato per creare un collegamento ipertestuale per cercare i risultati del termine del suggerimento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>Il termine suggerito. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zone {#section_15D8AA585F3246799968BA88EE2C9FC2}

Esempio:

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag nelle aree </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> Un singolo nodo di zona. È possibile avere più nodi di area. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> Nome della zona. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1 o 0 per indicare se la zona è o non è visualizzata. Il contenuto dell'area effettiva può essere un'area statica sulla pagina Web o nei risultati della ricerca, ad esempio i migliori venditori o i prodotti correlati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ricerca guidata Output XML per Adobe Experience Manager {#reference_DBE13C606C3A4BB185DE53F88D0D3048}

Tabelle che descrivono l&#39;output di risposta XML standard per AEM (Adobe Experience Manager).

Vedi anche . [Ricerca guidata Output XML](../c-appendices/c-guidedsearchoutput.md#reference_D93E859A277643068B10AE7A61C973EA)

Potete esaminare la risposta XML per i seguenti elementi:

* [Banner](../c-appendices/c-guidedsearchoutput.md#section_B16EDC5533FA4494AC9983AA7357CBE3)
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_49EA7043FBE44315A79A4E738BE30114)
* [Campi personalizzati](../c-appendices/c-guidedsearchoutput.md#section_38DD31AFE5DD4263A63644AFF484E0F4)
* [Facet](../c-appendices/c-guidedsearchoutput.md#section_BE98990E3DD748A1BD4E0CA322314B79)
* [Intestazione](../c-appendices/c-guidedsearchoutput.md#section_5305B1DC5774439485CA0665DB683F9C)
* [Menu e ordinamento](../c-appendices/c-guidedsearchoutput.md#section_A34CBB645DBF4C70A12A5B7E81211295)
* [Paginazione](../c-appendices/c-guidedsearchoutput.md#section_E52F81C6A6EB4B8F996157B657EC540F)
* [Query](../c-appendices/c-guidedsearchoutput.md#section_3DAA1013F09742869B80F6A361816E6C)
* [Ricerche recenti](../c-appendices/c-guidedsearchoutput.md#section_17F942F6EC07456DABED7A483AC08446)
* [Risultati](../c-appendices/c-guidedsearchoutput.md#section_155A80B8C4F641678DD9C8F257108412)
* [Modulo di ricerca](../c-appendices/c-guidedsearchoutput.md#section_9E4B99D4FEDC49629F6C7E866F3A7493)
* [Suggerimenti](../c-appendices/c-guidedsearchoutput.md#section_2899FACB9AD84F60B3687C1B4EF09E15)
* [Modello](../c-appendices/c-guidedsearchoutput.md#section_1E2BB2F274B04F5491A4CCCC38F507BD)
* [Zone](../c-appendices/c-guidedsearchoutput.md#section_26C4A947E7B1474A8E37D86D9579B93E)

## Banner {#section_B16EDC5533FA4494AC9983AA7357CBE3}

Ricerca nel sito/merchandising può gestire i banner di un cliente, collegando i banner in varie parti di una pagina Web.

Banner di esempio:

Di seguito è riportato un esempio di un banner posizionato nell&#39;area delle pagine denominata &quot;top&quot;.

```xml
   <banners> 
       <banner> 
           <area><![CDATA[top]]></area> 
           <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
       </banner> 
    </banners> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>banner </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p>Contiene i nodi banner 0-n che rappresentano ciascuna area del banner e il contenuto collegato all'area. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>banner </p> </td> 
   <td colname="col2"> <p>banner </p> </td> 
   <td colname="col3"> <p>Un singolo nodo di banner. Potete avere più nodi banner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>area </p> </td> 
   <td colname="col2"> <p>banner </p> </td> 
   <td colname="col3"> <p>Area della pagina Web in cui viene visualizzato il banner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>content </p> </td> 
   <td colname="col2"> <p>banner </p> </td> 
   <td colname="col3"> <p>Contenuto del banner. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_49EA7043FBE44315A79A4E738BE30114}

Sono supportate più breadcrumb. È possibile definire le breadcrumb e il relativo comportamento in **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**. Dovete inoltre assegnare un nome univoco a ogni breadcrumb definito. Il nodo XML di breadcrumb si ripete su tutte le breadcrumb definite. È consigliabile visualizzare solo una breadcrumb nei risultati della ricerca.

Nell&#39;esempio seguente, ogni volta che il cliente si restringe ulteriormente attraverso i facet, la selezione viene aggiunta alla breadcrumb. Ogni elemento è rappresentato come `<breadcrumb-item>`.

Esempio di nodo breadcrumb:

```xml
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;sp_cs=UTF-8;view=xml]]></link> 
   <value><![CDATA[mens]]></value> 
                <label><![CDATA[]]></label> 
      </breadcrumb-item> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;q1=Channel;sp_cs=UTF-8;view=xml;x1=brand]]></link> 
   <value><![CDATA[Channel]]></value> 
                <label><![CDATA[brand]]></label> 
      </breadcrumb-item> 
   </breadcrumb> 
    </breadcrumbs> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>pane grattugiato </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p> Contiene 0-n nodi di breadcrumb che definiscono ogni breadcrumb. La maggior parte dei clienti ha un solo percorso di navigazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pangrattato </p> </td> 
   <td colname="col2"> <p>pane grattugiato </p> </td> 
   <td colname="col3"> <p> Contiene i nodi secondari che definiscono la definizione di un percorso di navigazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>pangrattato </p> </td> 
   <td colname="col3"> <p> Nome del percorso di navigazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>breadcrumb-item </p> </td> 
   <td colname="col2"> <p>Un singolo elemento all’interno della breadcrumb. Ogni elemento indica un passaggio nella traccia mentre l'utente restringe il set di risultati. </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> Un collegamento relativo ai risultati della ricerca che mostra la visualizzazione desiderata. Facendo clic su un collegamento di breadcrumb, il cliente viene visualizzato in cui vengono rimossi tutti i miglioramenti successivi. Sono disponibili anche altre opzioni, ad esempio rilascio e rimozione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> Testo rivolto al cliente per l’elemento breadcrumb. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> Il tag label genera un'etichetta per un valore di breadcrumb che specifica quale facet è stato selezionato per generare l'elemento breadcrumb. Viene utilizzato solo nel contesto di un blocco di breadcrumb guidato. Per il passaggio del termine della query, questo campo è vuoto. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Campi personalizzati {#section_38DD31AFE5DD4263A63644AFF484E0F4}

I campi personalizzati sono un insieme di variabili con un contesto globale. Viene in genere utilizzato per trasmettere le variabili a fini SEO impostate nei metadati della pagina dei risultati di ricerca.

Esempio di nodo di campi personalizzati:

```xml
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>custom-fields </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p> Può contenere nodi figlio 0-n che definiscono campi personalizzati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>custom-field </p> </td> 
   <td colname="col2"> <p>custom-fields </p> </td> 
   <td colname="col3"> <p> Facoltativo. Contiene un valore per un dato campo personalizzato indicato dall'attributo name. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facet {#section_BE98990E3DD748A1BD4E0CA322314B79}

I facet sono opzioni di perfezionamento che consentono ai clienti di filtrare in base ai risultati. I facet sono comunemente utilizzati per la categorizzazione, le fasce di prezzo, le selezioni di colore e altri miglioramenti degli attributi. I facet sono creati sopra i metadati nell’indice.

È comune nascondere o mostrare i facet di categorizzazione quando un cliente passa attraverso la categorizzazione. Il livello più elevato di classificazione (categoria) è noto come livello 1. Quando un cliente fa clic su un&#39;opzione di livello 1, vengono visualizzate le opzioni di perfezionamento di livello 2 (sottocategoria) e le opzioni di livello 1 scompaiono. Quando un cliente fa clic su un&#39;opzione di livello 2, vengono visualizzate le opzioni di rifinitura di livello 3 (sottocategoria) e le opzioni di livello 2 scompaiono. Come indicato sopra, queste opzioni sono nascoste e visualizzate; l’applicazione Web non li influisce.

Ogni facet è contenuto all&#39;interno di `<facet-item>` tag. Nell&#39;esempio seguente, viene visualizzato un facet che consente al cliente di perfezionare i risultati della ricerca per &quot;festività&quot;.

Esempio di blocco facet:

```xml
<facets>          
     <facet> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undo-link> 
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;q2=Mens;sp_staged=1;view=xml;x1=brand;x2=leveli]]></link> 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undolink> 
      </facet-value> 
      </facet> 
     <facet> 
         <facet-title><![CDATA[Sub-Category]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>0</selected> 
      <facet-value>           
              <label><![CDATA[Apparel]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans;q3=Apparel;sp_staged=1;view=xml;x1=leveli;x2=brand;x3=levelii]]></link> 
       <count><![CDATA[3]]></count>                         
      </facet-value>   
      </facet>         
     <facet> 
         <facet-title><![CDATA[Brand]]></facet-title> 
                <behavior><![CDATA[multi-select]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undo-link> 
      <facet-value>        
              <label><![CDATA[Amoura]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Amoura;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[9]]></count>                         
      </facet-value>   
      <facet-value>         
              <label><![CDATA[Armora]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[12]]></count>                        
      </facet-value>   
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Armora Jeans]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora+Jeans;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undolink> 
      </facet-value>   
      <facet-value>           
              <label><![CDATA[Art of Grooming]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Art+of+Grooming;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count>                         
      </facet-value>   
      <facet-value>          
              <label><![CDATA[Bear Co.]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Bear+Co.;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[1]]></count> 
      </facet-value> 
      <facet-value>      
              <label><![CDATA[Citizens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Citizens;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[D&amp;B]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|D%26B;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[17]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[David Yuri]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|David+Yuri;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[2]]></count>    
      </facet-value>   
      </facet> 
    </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>facet </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p>Il nodo facet contenitore con nodi figlio 0-n che rappresenta ciascun facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p> Una singola istanza facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-title </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Titolo rivolto al cliente per il facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>comportamento </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Il comportamento della facet. Ad esempio, normale, fisso o a selezione multipla. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>selezionato </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>1 se il facet ha un valore selezionato, altrimenti 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>undo-link </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p> Presentato solo quando il facet è selezionato. Il collegamento Annulla ripristina l’intero facet. Ad esempio, quando è un facet a selezione multipla, deseleziona tutte le opzioni selezionate per il facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-value </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Contiene tutti i singoli elementi facet appartenenti al facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>selezionato </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Se l'elemento corrente con il facet è selezionato, questo nodo è presente e impostato su "true". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Etichetta rivolta al cliente per l’opzione facet. Per impostazione predefinita, questo valore deve essere già basato sull'escape HTML. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p> Collegamento relativo ai risultati che l'opzione perfeziona ulteriormente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>count </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Il numero di risultati nel set di risultati raffinato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>undo-link </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Quando viene selezionato un valore facet, il nodo restituisce un "collegamento di annullamento" che consente al cliente di tornare indietro selezionando la selezione del singolo facet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Intestazione {#section_5305B1DC5774439485CA0665DB683F9C}

Esempio:

```xml
xml version="1.0" encoding="utf-8" standalone="yes" 
```

## Menu e ordinamento {#section_A34CBB645DBF4C70A12A5B7E81211295}

Sono supportati i menu per ordinare i risultati e modificare il numero di risultati da restituire per pagina. Supporta inoltre un menu di navigazione che è utile per utilizzare &quot;search as navigation&quot;. Un account può definire più menu dello stesso tipo e utilizzare uno qualsiasi dei menu per la presentazione.

Nodo menu di esempio:

L&#39;esempio seguente mostra i dati per un menu di ordinamento e un menu di navigazione a tre opzioni. Il menu di ordinamento consente al cliente di ordinare in base a rilevanza, titolo o valutazione. L&#39;elemento selezionato include un attributo &quot;selected=true&quot;. &quot;. Offri sempre un’opzione di rilevanza per consentire al cliente di tornare ai risultati di ricerca predefiniti visualizzati originariamente.

```xml
<menus> 
        <menu> 
           <name><![CDATA[sort]]></name>         
             <item selected="true"> 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>   
                    <item> 
                        <label><![CDATA[WOMEN'S]]></label> 
          <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[MEN'S]]></label> 
          <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
          <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
          <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
          <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
          <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[GIFTS & HOME]]></label> 
          <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[CHILDREN & TOYS]]></label> 
          <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[ELECTRONICS]]></label> 
          <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link> 
                    </item> 
        </menu> 
    </menus> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>menu </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p>Contiene i nodi figlio 0-n che definiscono ciascun menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>  </p> </td> 
   <td colname="col2"> <p>menu </p> </td> 
   <td colname="col3"> <p>Una singola istanza di un menu (corrisponde a un menu definito in <span class="uicontrol"> Progettazione </span> &gt; <span class="uicontrol"> Navigazione </span> &gt; <span class="uicontrol"> Menu </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>  </p> </td> 
   <td colname="col3"> <p>Nome del menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>elemento </p> </td> 
   <td colname="col2"> <p>  </p> </td> 
   <td colname="col3"> <p>Definisce ciascuna voce del menu. L'attributo opzionale selezionato è impostato su true se la voce di menu specificata è attualmente selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>elemento </p> </td> 
   <td colname="col3"> <p>Testo rivolto al cliente per la voce di menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>elemento </p> </td> 
   <td colname="col3"> <p>Rappresenta il valore della voce di menu (il valore del parametro di query su cui è impostato il menu). Questo tag non è necessario se si utilizza il valore &lt;link&gt;. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>elemento </p> </td> 
   <td colname="col3"> <p>Per le opzioni non selezionate, il parametro &lt;link&gt; contiene il collegamento relativo che restituisce lo stesso set di risultati, ma con l'opzione di menu applicata. Questo campo è vuoto per l'opzione di ordinamento attualmente selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Impaginazione {#section_E52F81C6A6EB4B8F996157B657EC540F}

I set di risultati sono suddivisi su più pagine. In genere i clienti visualizzano 10-20 risultati su una singola pagina. I risultati successivi vengono visualizzati nella pagina successiva. L’XML di impaginazione consente di creare un set di collegamenti di navigazione che consentono ai clienti di sfogliare, pagina per pagina, i set di risultati. Sono disponibili quattro collegamenti di navigazione: first, last, next e previous. Ogni tipo di collegamento consente ai clienti di spostarsi rapidamente tra le pagine in modo che possano rivedere e perfezionare facilmente ciò che cercano.

L&#39;esempio seguente mostra l&#39;impaginazione di una ricerca che si trova sulla prima pagina con l&#39;impaginazione configurata per mostrare i collegamenti a cinque pagine.

Esempio di impaginazione:

```xml
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
        </pages> 
    </pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>impaginazione </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p> Numero totale di pagine di risultati, in base al numero di risultati diviso per il numero di risultati per pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total-pages </p> </td> 
   <td colname="col2"> <p>impaginazione </p> </td> 
   <td colname="col3"> <p>Il numero totale di pagine su cui vengono distribuiti i risultati della ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pagine </p> </td> 
   <td colname="col2"> <p>impaginazione </p> </td> 
   <td colname="col3"> <p>Contiene i nodi di pagina 0-n che definiscono ogni pagina nell’impaginazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>page </p> </td> 
   <td colname="col2"> <p>pagine </p> </td> 
   <td colname="col3"> <p>Esistono quattro nodi di pagina speciali: first, last, previous e next. Queste quattro pagine sono facoltative e appaiono nel set di risultati solo se hanno senso. Ad esempio, se vi trovate a pagina 1, non esiste un collegamento "precedente". Tutte le altre pagine indicano una posizione. Il numero di pagine elencate dipende dal "numero di collegamenti alle pagine" configurato nell’interfaccia utente di impaginazione. L'attributo "selected" indica la pagina in cui il cliente si trova attualmente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Query {#section_3DAA1013F09742869B80F6A361816E6C}

Esempio di nodo di query:

```xml
    <query> 
        <user-query><![CDATA[mens]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[265]]></total-results> 
    </query> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>query </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p> Un nodo globale che fornisce una panoramica della query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>user-query </p> </td> 
   <td colname="col2"> <p>query </p> </td> 
   <td colname="col3"> <p> La parola chiave cercata. Se <span class="uicontrol"> Avete inteso </span> ricercato automaticamente un termine suggerito a causa del termine originale che non genera risultati, questo si riflette nella nuova parola chiave cercata (consultate il nodo dei suggerimenti per ottenere la parola chiave originale). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>minor risultato </p> </td> 
   <td colname="col2"> <p>query </p> </td> 
   <td colname="col3"> <p> Numero elemento del primo risultato in questa pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>risultati superiori </p> </td> 
   <td colname="col2"> <p>query </p> </td> 
   <td colname="col3"> <p> Il numero dell'ultimo risultato su questa pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total-result </p> </td> 
   <td colname="col2"> <p>query </p> </td> 
   <td colname="col3"> <p> Il numero totale di risultati che corrispondono alla query utente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ricerche recenti {#section_17F942F6EC07456DABED7A483AC08446}

Ricerche recenti è una funzione basata su cookie che funziona solo se le informazioni sui cookie vengono inviate ai server di ricerca/merchandising del sito.

Esempio di ricerche recenti:

```xml
    <recent-searches> 
        <clear-link><![?q=womens&gscr=clear]]></clear-link> 
        <recent-search> 
            <link><![?q=mens]]></link> 
            <label><![CDATA[mens]]></label> 
        <recent-search> 
    </recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ricerche recenti </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p>Il nodo è presente solo se la ricerca dispone di ricerche recenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clear-link </p> </td> 
   <td colname="col2"> <p>ricerche recenti </p> </td> 
   <td colname="col3"> <p>Percorso relativo che cancella tutte le ricerche recenti del cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ricerca recente </p> </td> 
   <td colname="col2"> <p>ricerche recenti </p> </td> 
   <td colname="col3"> <p>Definisce nelle ricerche recenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>ricerca recente </p> </td> 
   <td colname="col3"> <p>Percorso per creare un collegamento che esegue una ricerca eseguita di recente dall'utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>ricerca recente </p> </td> 
   <td colname="col3"> <p>Etichetta visualizzata dal cliente per la ricerca recente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risultati {#section_155A80B8C4F641678DD9C8F257108412}

L&#39;insieme Results (Risultati) è un&#39;area personalizzabile della risposta XML. Ogni indice è univoco nei meccanismi di denominazione dei campi dei metadati. Esistono campi comuni che vengono restituiti per ogni risultato, ad esempio titolo, descrizione e URL. Tuttavia, tutti i metadati definiti per una pagina nell&#39;indice possono diventare disponibili per l&#39;utilizzo in ciascun nodo di risultati. Categorizzazione, prezzi, colori e miniature sono solo alcune delle opzioni che potete applicare a un risultato per produrre risultati di ricerca più coinvolgenti.

Il formato dei risultati viene personalizzato in base ai metadati specifici per l&#39;implementazione. Tutti i dati per risultato visualizzati nei risultati, inclusi gli URL delle miniature, sono contenuti in questo riquadro.

Inoltre, è possibile configurare più aree risultati all&#39;interno della pagina, ad esempio &quot;Risultati contenuti&quot; o sezioni separate di risultati &quot;Prodotti&quot; e &quot;Contenuto&quot;. In questi casi, all’interno dell’HTML vengono fornite più zone risultato, anche se i facet sono associati solo al set di risultati principale.

Nodo dei risultati di esempio:

```xml
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
                    <field name="sku"><![CDATA[200190]]></field> 
                    <field name="pagename"><![CDATA[Relaxed Paint Splattered]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>   
         <result> 
                    <field name="index"><![CDATA[2]]></field> 
                    <field name="sku"><![CDATA[200195]]></field> 
                    <field name="pagename"><![CDATA[Tumbled Jeans]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[235]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>    
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
                    <field name="sku"><![CDATA[200196]]></field> 
                    <field name="pagename"><![CDATA[Montana Relaxed]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[220]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>         
        </result-set>   
    </results> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>risultati </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p>Il nodo contenitore per i set di risultati 0-n. Zero set di risultati indica che siete su una speciale pagina di destinazione senza risultati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>set di risultati </p> </td> 
   <td colname="col2"> <p>risultati </p> </td> 
   <td colname="col3"> <p>Una ricerca in entrata può attivare più ricerche. Ogni set di risultati contiene i risultati di una ricerca con nome specifica eseguita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>set di risultati </p> </td> 
   <td colname="col3"> <p>Nome della ricerca a cui appartiene il set di risultati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>risultato </p> </td> 
   <td colname="col2"> <p>set di risultati </p> </td> 
   <td colname="col3"> <p>Contiene tutti i campi associati a un singolo risultato per il set di risultati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>field </p> </td> 
   <td colname="col2"> <p>risultato </p> </td> 
   <td colname="col3"> <p>L'attributo name definisce il nome del campo all'interno dell'indice visualizzato. Il valore è il valore effettivo per quel campo. Alcuni risultati possono presentare campi mancanti che non sono pertinenti per quel singolo risultato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modulo di ricerca {#section_9E4B99D4FEDC49629F6C7E866F3A7493}

Modulo di ricerca è incluso nel set di risultati per consentire ai clienti di creare il modulo di ricerca in modo dinamico. Questo passaggio è facoltativo. La maggior parte dei clienti dispone di un modulo di ricerca fisso. Tuttavia, consente ai clienti di determinare se il modulo di ricerca ha bisogno di una mbox Test&amp;Target, in base alla presenza di almeno una regola business che esegue un test A:B. Allo stesso modo, consente ai clienti di recuperare automaticamente i file CSS e JavaScript con completamento automatico più recenti.

Esempio di modulo di ricerca XML:

```xml
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>search-form </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p>Contiene i dati per la guida del modulo di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>include-tnt-mbox </p> </td> 
   <td colname="col2"> <p> search-form </p> </td> 
   <td colname="col3"> <p>Tecnicamente è necessaria una mbox nel modulo di ricerca solo quando è presente almeno una regola business che esegue un test A:B Test&amp;Target. Questo nodo indica se è necessaria o meno una mbox che consente di ridurre gli hit di numero sui server Test&amp;Target. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>autocomplete </p> </td> 
   <td colname="col2"> <p>search-form </p> </td> 
   <td colname="col3"> <p>Nodo figlio Case correlato al completamento automatico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>abilitato </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>Impostare su 1 quando l'account di ricerca utilizza la funzione di completamento automatico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>css </p> </td> 
   <td colname="col2"> <p> autocomplete </p> </td> 
   <td colname="col3"> <p> CSS per completamento automatico. Posizionare il nodo il più in alto possibile sulla pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> form-content </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>Contenuto inserito nel modulo di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javascript </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>JavaScript per la compilazione automatica. Posizionare il nodo il più in basso possibile sulla pagina. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suggerimenti {#section_2899FACB9AD84F60B3687C1B4EF09E15}

I clienti possono configurare la funzionalità **[!UICONTROL Did You Mean]** in tre modi: fate suggerimenti a causa di nessun risultato, cercate automaticamente in base al primo suggerimento quando non abbiamo risultati, o fate suggerimenti a causa di risultati bassi (dove i suggerimenti hanno un conteggio di risultati più alto). Tutti i suggerimenti danno risultati.

Questo nodo di suggerimenti contiene i termini che generano query di successo. Viene inoltre restituito il collegamento in modo che il cliente possa passare alla nuova query.

Esempio di output per la creazione di suggerimenti a causa di 0 risultati:

```xml
    <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>0</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=arcade;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[arcade]]></word> 
 </suggestion-item>    
    </suggestions>
```

Esempio di output per la ricerca automatica in base a un suggerimento:

```xml
    <suggestions> 
        <auto-searched>1</auto-searched> 
        <orig-query><![CDATA[arcace]]></orig-query> 
        <suggestions-low-results>0</suggestions-low-results>         
    </suggestions> 
```

Esempio di output per la creazione di suggerimenti a causa di risultati ridotti:

```xml
   <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>1</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=coffee;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[coffee]]></word> 
 </suggestion-item>  
    </suggestions> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>suggerimento </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p> Contiene nodi figlio che definiscono eventuali suggerimenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ricerca automatica </p> </td> 
   <td colname="col2"> <p>suggerimenti </p> </td> 
   <td colname="col3"> <p> Se presente, indica se la ricerca nel sito/merchandising ha eseguito automaticamente la ricerca in base a un nuovo termine a causa di nessun risultato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>orig-query </p> </td> 
   <td colname="col2"> <p>suggerimenti </p> </td> 
   <td colname="col3"> <p> Quando la ricerca del sito/merchandising esegue automaticamente la ricerca rispetto al primo suggerimento, la query utente nel nodo di query mostra la parola chiave con cui viene eseguita la ricerca. Questo nodo mostra il termine di query originale. La combinazione di questi due elementi consente ai clienti di creare strutture quali "Ricerca di arcade invece che di arcace". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>suggerimenti-risultati bassi </p> </td> 
   <td colname="col2"> <p>suggerimenti </p> </td> 
   <td colname="col3"> <p>Se presente, indica se la ricerca del sito/merchandising sta dando suggerimenti a causa del termine di ricerca corrente che genera risultati bassi e un suggerimento che genera risultati notevolmente più alti. Le due soglie sono configurabili in <span class="uicontrol"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sug-item </p> </td> 
   <td colname="col2"> <p>suggerimenti </p> </td> 
   <td colname="col3"> <p>Contiene nodi 0-n che rappresentano i vari suggerimenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>sug-item </p> </td> 
   <td colname="col3"> <p>Contiene il percorso per la creazione di un collegamento al termine suggerito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>word </p> </td> 
   <td colname="col2"> <p>sug-item </p> </td> 
   <td colname="col3"> <p> Contiene la parola suggerita. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modello{#section_1E2BB2F274B04F5491A4CCCC38F507BD}

È supportata la possibilità di cambiare un&#39;esperienza di ricerca dei clienti in base ai risultati. Parte di questo include il passaggio tra diversi modelli con un layout diverso dei risultati di ricerca. Ad esempio, potete avere un modello con una vista a griglia di prodotti per i quali disponete di molti prodotti. Oppure, potete avere un modello &quot;faretto&quot; quando visualizzate un singolo risultato con maggiori dettagli. Potete anche avere un modello &quot;nessun risultato&quot; quando una ricerca non restituisce alcun risultato. Il nodo del modello indica quale modello viene utilizzato per visualizzare i risultati della ricerca.

Esempio di modello:

```xml
<template><![CDATA[grid]]></template>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>un modello </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p>Indica il nome del modello utilizzato per visualizzare i risultati della ricerca. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zone {#section_26C4A947E7B1474A8E37D86D9579B93E}

Le aree sono sezioni delle pagine che possono essere attivate o disattivate dalle regole aziendali. Un&#39;area può contenere qualsiasi contenuto, compresi, tra l&#39;altro, facet, ricerche, breadcrumb, contenuto statico. Le aree della pagina Web del cliente devono essere mappate sulle stesse aree di ricerca del sito/merchandising.

Esempio di nodi di zona:

```xml
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Nodo principale </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>zone </p> </td> 
   <td colname="col2"> <p>risultati del cliente </p> </td> 
   <td colname="col3"> <p>Contiene 0-n zone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zone </p> </td> 
   <td colname="col2"> <p>zone </p> </td> 
   <td colname="col3"> <p> Un singolo nodo di zona. È possibile avere più nodi di area. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>zone </p> </td> 
   <td colname="col3"> <p>Nome della zona. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>display </p> </td> 
   <td colname="col2"> <p>1 o 0, che indica se la zona corrispondente al nome della zona è visualizzata o nascosta. </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi {#reference_64B7D8D228AF4B8D90EDF4DE507B0F84}

Esempio di output per una ricerca * in un sito Web fittizio denominato Geometrixx e un modello di presentazione di esempio utilizzato per generare l&#39;output di esempio.

* [Esempio di output](../c-appendices/c-guidedsearchoutput.md#section_515C000A18B847D59097D0A9CCC02636)
* [Esempio di modello di presentazione](../c-appendices/c-guidedsearchoutput.md#section_AD42571DFB88491AA7F0FDF0929EBE97)

## Esempio di output {#section_515C000A18B847D59097D0A9CCC02636}

Esempio di output per una ricerca * in un sito web fittizio denominato Geometrixx.

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[*]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[1337]]></total-results> 
    </query> 
 
    <custom-fields> 
 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name>

             <item selected="true"> 
 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item>

             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=*;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>

                    <label><![CDATA[WOMEN'S]]></label> 
      <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link>

                    <label><![CDATA[MEN'S]]></label> 
      <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
      <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link>

                    <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
      <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
      <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link>

                    <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
      <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link>

                    <label><![CDATA[GIFTS & HOME]]></label> 
      <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link>

                    <label><![CDATA[CHILDREN & TOYS]]></label> 
      <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link>

                    <label><![CDATA[ELECTRONICS]]></label> 
      <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link>

        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
       
  <breadcrumb-item> 
    <link><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></link> 
    <value><![CDATA[*]]></value> 
                        <label><![CDATA[]]></label> 
   </breadcrumb-item> 
          
   </breadcrumb> 
 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched>0</auto-searched> 
         
        <suggestions-low-results>0</suggestions-low-results> 
         
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
      
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

        </pages> 
    </pagination> 
 
    <facets>  
         
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected>0</selected>

      <facet-value> 
           
              <label><![CDATA[Womens]]></label> 
 
       <link><![CDATA[?i=1;q=*;q1=Womens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[219]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Mens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[202]]></count> 
                         
      </facet-value> 
   
      <facet-value>

              <label><![CDATA[Beauty &amp; Fragrance]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Beauty+%26+Fragrance;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[169]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Children &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Children+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[209]]></count> 
                         
      </facet-value>

      <facet-value> 
           
              <label><![CDATA[Electronics &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Electronics+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[200]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Gifts &amp; Home]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Gifts+%26+Home;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[156]]></count>

      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Jewelry &amp; Accessories]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Jewelry+%26+Accessories;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[182]]></count> 
                         
      </facet-value> 
   
      </facet-item> 
  
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
               
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[2]]></field> 
      <field name="brand"><![CDATA[One For All]]></field> 
      <field name="price"><![CDATA[145]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[208]]></field> 
 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[4]]></field> 
      <field name="brand"><![CDATA[Vera Watson]]></field> 
      <field name="price"><![CDATA[850]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Dresses,  
          Day]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[5]]></field> 
 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[6]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[80]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[7]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[85]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[8]]></field> 
      <field name="brand"><![CDATA[Woolberry]]></field> 
 
      <field name="price"><![CDATA[280]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[9]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[10]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[55]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[11]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[45]]></field> 
 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[12]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[47]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
      
        </result-set>   
    </results>

    <banners> 
         
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
            </banner>

    </banners> 
 
    <zones> 
        <zone> 
 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

## Esempio di modello di presentazione {#section_AD42571DFB88491AA7F0FDF0929EBE97}

Di seguito è riportato un modello di presentazione di esempio utilizzato per generare l&#39;output di esempio riportato sopra.

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[<guided-query-param gsname="q" />]]></user-query> 
 <lower-results><![CDATA[<guided-results-lower>]]></lower-results> 
 <upper-results><![CDATA[<guided-results-upper>]]></upper-results> 
 <total-results><![CDATA[<guided-results-total>]]></total-results> 
    </query> 
 
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[<guided-general-field gsname="default" field="seo_search_keywords"/>]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name> 
     <guided-menu gsname="sort"> 
         <guided-if-menu-item-selected> 
             <item selected="true"> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
        <guided-else-menu-item-selected> 
             <item> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[<guided-menu-item-path />]]></link>     
             </item> 
        </guided-if-menu-item-selected> 
    </guided-menu> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name> 
            <guided-menu gsname="ss_head_nav"> 
                <guided-if-menu-item-selected> 
                    <item selected="true"> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                <guided-else-menu-item-selected> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                </guided-if-menu-item-selected> 
            </guided-menu>  
        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
      <guided-breadcrumb gsname="default"> 
  <breadcrumb-item> 
    <link><![CDATA[<guided-breadcrumb-path gsname="goto">]]></link> 
    <value><![CDATA[<guided-breadcrumb-value />]]></value> 
                        <label><![CDATA[<guided-breadcrumb-label>]]></label> 
   </breadcrumb-item> 
         </guided-breadcrumb> 
   </breadcrumb> 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched><guided-if-suggestion-autosearch>1<guided-else-suggestion-autosearch>0</guided-if-suggestion-autosearch></auto-searched> 
        <guided-if-suggestion-autosearch><orig-query><![CDATA[<guided-suggestion-original-query/>]]></orig-query></guided-if-suggestion-autosearch> 
        <suggestions-low-results><guided-if-suggestion-low-results>1<guided-else-suggestion-low-results>0</guided-if-suggestion-low-results></suggestions-low-results> 
        <guided-suggestions> 
     <suggestion-item> 
         <link><![CDATA[<guided-suggestion-path />]]></link> 
  <word><![CDATA[<guided-suggestion />]]></word> 
     </suggestion-item> 
 </guided-suggestions> 
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[<guided-page-total />]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[<guided-page-path gsname="first" />]]></page> 
     <page position="last"><![CDATA[<guided-page-path gsname="last" />]]></page> 
     <guided-if-page-prev><page position="prev"><![CDATA[<guided-page-path gsname="prev" />]]></page></guided-if-page-prev> 
     <guided-if-page-next><page position="next"><![CDATA[<guided-page-path gsname="next" />]]></page></guided-if-page-next> 
     <guided-if-page-viewall><page position="viewall"><![CDATA[<guided-page-path gsname="viewall" />]]></page></guided-if-page-viewall> 
     <guided-if-page-viewpages><page position="viewall"><![CDATA[<guided-page-path gsname="viewpages" />]]></page></guided-if-page-viewpages> 
 
     <guided-pages> 
                <guided-if-page-selected><page position="<guided-page-number />" selected="true"><![CDATA[<guided-page-path />]]></page> 
  <guided-else-page-selected><page position="<guided-page-number />"><![CDATA[<guided-page-path />]]></page> 
  </guided-if-page-selected> 
     </guided-pages> 
        </pages> 
    </pagination> 
 
    <facets>  
        <guided-facet gsname="leveli"> 
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected><guided-if-facet-selected>1<guided-else-facet-selected>0</guided-if-facet-selected></selected> 
                <guided-if-facet-selected><undo-link><![CDATA[<guided-facet-undo-path gsname="leveli">]]></undo-link></guided-if-facet-selected> 
  <guided-facet-values> 
      <facet-value> 
          <guided-if-facet-value-selected><selected><![CDATA[true]]></selected></guided-if-facet-value-selected> 
              <label><![CDATA[<guided-facet-value>]]></label> 
       <link><![CDATA[<guided-facet-value-path />]]></link> 
       <count><![CDATA[<guided-facet-count>]]></count> 
                        <guided-if-facet-value-selected><undolink><![CDATA[<guided-facet-value-undo-path />]]></undolink></guided-if-facet-value-selected> 
      </facet-value> 
  </guided-facet-values> 
      </facet-item> 
 </guided-facet> 
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
            <guided-results gsname="default">   
         <result> 
                    <field name="index"><![CDATA[<guided-result-index />]]></field> 
      <field name="brand"><![CDATA[<guided-result-field gsname="brand" />]]></field> 
      <field name="price"><![CDATA[<guided-result-field gsname="price" />]]></field> 
      <field name="foundIn"><![CDATA[<guided-if-result-field gsname="leveli"><!--tmpl_var name='leveli'-->, </guided-if-result-field> 
            <guided-if-result-field gsname="levelii"><!--tmpl_var name='levelii'-->, </guided-if-result-field> 
          <guided-if-result-field gsname="leveliii"><!--tmpl_var name='leveliii'--></guided-if-result-field>]]></field> 
         </result>   
     </guided-results> 
        </result-set>   
    </results> 
 
    <guided-if-recent-searches> 
    <recent-searches> 
        <clear-link><guided-recent-searches-clear-path/></clear-link> 
        <guided-recent-searches> 
            <recent-search> 
                <link><guided-recent-searches-path></link> 
                <label><guided-recent-searches-value></label> 
            <recent-search> 
        </guided-recent-searches> 
    </recent-searches> 
    </guided-if-recent-searches> 
 
    <banners> 
        <guided-if-banner-set gsname="top"> 
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<guided-banner gsname="top">]]></content> 
            </banner> 
        </guided-if-banner-set> 
        <guided-if-banner-set gsname="bottom"> 
            <banner> 
                <area><![CDATA[bottom]]></area> 
                <content><![CDATA[<guided-banner gsname="bottom">]]></content> 
            </banner> 
        </guided-if-banner-set> 
    </banners> 
 
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display><guided-if-zone gsname="brand-facet">1<guided-else-zone>0</guided-if-zone></display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox><guided-if-tnt-business-rules>1<guided-else-tnt-business-rules>0</guided-if-tnt-business-rules></include-tnt-mbox> 
        <autocomplete> 
            <enabled><guided-if-autocomplete>1<guided-else-autocomplete>0</guided-if-autocomplete></enabled> 
            <css><![CDATA[<guided-ac-css/>]]></css> 
            <form-content><![CDATA[<guided-ac-form-content/>]]></form-content> 
            <javascript><![CDATA[<guided-ac-javascript/>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

