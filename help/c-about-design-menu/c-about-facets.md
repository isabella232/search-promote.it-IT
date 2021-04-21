---
description: È possibile utilizzare i facet per personalizzare il livello di presentazione e fornire agli utenti una ricerca guidata che consenta loro di approfondire i risultati della ricerca.
solution: Target
subtopic: Navigation
title: Informazioni sui facet
topic-legacy: Design,Site search and merchandising
uuid: 28bc4d4d-a84c-4a77-befb-b0fb3bbdb966
exl-id: 10cdc599-79fe-44e1-8f90-f08b819f6dda
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '3827'
ht-degree: 0%

---

# Informazioni su facet{#about-facets}

È possibile utilizzare i facet per personalizzare il livello di presentazione e fornire agli utenti una ricerca guidata che consenta loro di approfondire i risultati della ricerca.

## Utilizzo dei facet {#concept_FA912B3B41EE493DB2F492D188457FF5}

Ad esempio, supponiamo che un visitatore di un sito web che vende strumenti esegua una ricerca di chiavi. L&#39;azienda può utilizzare due facet: uno per specificare tutti i marchi di chiavi trovati e il secondo per specificare tutte le dimensioni di chiave inglese. Il cliente può fare clic su qualsiasi marchio o dimensione all&#39;interno del facet appropriato per limitare i risultati e trovare rapidamente la chiave inglese corretta di cui ha bisogno.

Puoi basare un facet su qualsiasi definizione di metadati esistente. Se un facet è definito come tipo di data nei metadati, viene visualizzato come un facet di intervallo di date.

La tabella nella pagina [!DNL Staged Facets] mostra una panoramica generale delle impostazioni che compongono ciascun facet aggiunto. Puoi aggiungere nuovi facet e modificare o eliminare quelli esistenti. Per ripristinare le modifiche apportate ai facet, utilizza **[!UICONTROL History]** nell’angolo in alto a destra della pagina.

Per impostazione predefinita, le impostazioni dei facet vengono gestite in modo da poter testare eventuali modifiche prima di inviarle in diretta.

Consulta [Informazioni sullo staging](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7).

Puoi utilizzare **[!UICONTROL View Live Settings]** per confrontare le impostazioni di staging con l’impostazione in tempo reale corrente. Utilizza **[!UICONTROL View Staged Settings]** per tornare all&#39;area di gestione temporanea. Per un elemento di staging, la versione live delle impostazioni è di sola lettura. Pertanto, lo si manipola tramite il push live delle impostazioni. Dopo aver apportato tutte le modifiche al facet di staging, fai clic su **[!UICONTROL Push Live]** per eseguirne il push in tempo reale.

## Facet intervallo date {#section_FEFFF6B5B6534456913189FEF559BA58}

I facet definiti come tipo Data nei metadati vengono trattati in modo diverso rispetto agli altri facet. Invece di essere trattati come un insieme di valori, vengono trattati come un intervallo di date, con una data di inizio, una data di fine o entrambi.

Un facet di intervallo di date ha un valore della data di inizio, seguito da &quot;BTW&quot; (per &quot;tra&quot;), seguito dalla data di fine. Le date sono nei due formati seguenti:

gg-gg-aaaa

gg/mm/aaaa

Sono richiesti anni a quattro cifre. Deve essere presente almeno una delle date di inizio o di fine, ma entrambe non sono obbligatorie. Ad esempio, per &quot;12/1/2007BTW1/4/2009&quot; si intendono tutte le date comprese tra il 1° dicembre 2007 e il 4 gennaio 2009. Tuttavia, per &quot;1-1-2005BTW&quot; si intendono tutte le date dal 1° gennaio 2005.

È possibile utilizzare il tag del modello di presentazione `<guided-facet-value/>` per ottenere il valore di un facet dell&#39;intervallo di date, come un facet normale. Al momento, è necessario JavaScript per consentire agli utenti di inserire intervalli di date in cui effettuare la ricerca. Ad esempio, puoi inserire l’input da due campi di immissione per le date di inizio e di fine. Quindi puoi convalidare l’input e aggiungere il valore del nuovo facet (generato dai due campi di input) e il nome del facet all’URL esistente.

Vedere [Tag del modello di presentazione](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

Il seguente esempio di codice è un esempio su come presentare un intervallo di date su una pagina. Mostra l’intervallo di date esistente, se selezionato; in caso contrario, presenta un semplice modulo di input. Quando il modulo viene inviato, esegue una semplice convalida. Invia quindi il browser a un nuovo URL che include due nuovi parametri:

* `q#` - Rappresenta l’intervallo di date selezionato assemblato dai due campi di input.
* `x#` - Assegna un nome al facet. In questo esempio, il facet dell’intervallo di date è denominato &quot;modificato&quot;.

Le parti `replace(/%2F/ig, '~2F')` nel codice sono necessarie perché Apache non consente `%2F` nei percorsi URL per motivi di sicurezza e quando si utilizzano URL SEO la query si trova nel percorso URL. Pertanto, `/` viene codificato come `~2F` invece di `%2F`, in quanto normalmente si trova in un URL.

```
<div class="date_range"> 
 <p>Date Range</p> 
 <guided-if-facet-selected gsname="modified"> 
  <guided-facet-values gsname="modified"> 
   <script> 
   var modified_daterange= '<guided-facet-value />'.split(/BTW/) ; 
   if (modified_daterange[0]=='') modified_daterange[0]= '--/--/----' ; 
   if (modified_daterange[1]=='') modified_daterange[1]= '--/--/----' ; 
   document.write('From: ' + modified_daterange[0]) ; 
   document.write('<br>To: ' + modified_daterange[1]) ; 
   </script> 
  </guided-facet-values> 
 
 <guided-else-facet-selected> 
  <form action="#"> 
   From: <input name="dateFrom" size=10> 
   <br>To: <input name="dateTo" size=10> 
   <br><input type="button" value="Go" onclick="goClick(this.form)"> 
  </form> 
  <script> 
  function goClick(f) { 
   if (f.dateFrom.value=='' && f.dateTo.value=='') { 
    alert('You must enter either a From: date or a To: date.') ; 
    return ; 
   } 
   if ( f.dateFrom.value!='' && !f.dateFrom.value.match(/^\d+[\/\-]\d+[\/\-]\d\d\d\d$/) ) { 
    alert('From: date must be in "mm/dd/yyyy" or "mm-dd-yyyy" format.') ; 
    return ; 
   } 
   if ( f.dateTo.value!='' && !f.dateTo.value.match(/^\d+[\/\-]\d+[\/\-]\d\d\d\d$/) ) { 
    alert('To: date must be in "mm/dd/yyyy" or "mm-dd-yyyy" format.') ; 
    return ; 
   } 
   // Note that "/" is encoded as "~2F" instead of "%2F" to avoid Apache 404 error. 
   var new_url= '<guided-current-path />&<guided-query-param-name gsname="q#" offset="0" />=' 
    + encodeURIComponent(f.dateFrom.value).replace(/%2F/ig, '~2F') + 'BTW' 
    + encodeURIComponent(f.dateTo  .value).replace(/%2F/ig, '~2F') 
    + '&<guided-query-param-name gsname="x#" offset="0" />=modified' ; 
   location.href= new_url ; 
  } 
  </script> 
 </guided-if-facet-selected> 
</div>
```

## Informazioni sui facet nidificati {#section_6BC77F38DE9F43D5B6911F8CECB15DFC}

I facet nidificati sono facet che mostrano più livelli di categorie come nei seguenti:

![](assets/nestedfacets.png)

Le categorie Womens e Mens si trovano nel facet superiore o padre. Le sottocategorie, come Accessori e Calzature, si trovano nella parte inferiore o secondaria.

La profondità del facet nidificato supportato corrente è due, ma può trovarsi in qualsiasi punto dell’elenco a discesa.

Di seguito sono riportati i comportamenti di vari tipi di facet nidificati:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Comportamento del tipo di facet nidificato </p> </th> 
   <th colname="col2" class="entry"> <p>Comportamento </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Normale </p> </td> 
   <td colname="col2"> <p>Il comportamento di un facet nidificato normale è che si restringe se altri facet restringono la ricerca. </p> <p>Se il facet nidificato è selezionato, si restringe verso il basso verso la sua selezione. Se è selezionato un facet padre, solo quest'ultimo viene visualizzato con tutti i facet figlio rimanenti. Se è selezionato un facet figlio, il facet mostra solo il facet padre selezionato e il facet figlio selezionato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>In rilievo </p> </td> 
   <td colname="col2"> <p>Il comportamento di un facet nidificato fisso consiste nel cercare di mantenere il facet aperto il più possibile in base allo stato di altri facet o criteri di ricerca. Se il facet figlio è selezionato, conta verso la profondità adesiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Selezione multipla </p> </td> 
   <td colname="col2"> <p>Il comportamento di un facet a selezione multipla consiste nel mantenere aperto il facet. Qualsiasi nuova selezione cerca di cancellare tutte le altre selezioni di facet a meno che il facet non sia un "elemento padre" del facet nidificato della categoria. In questo caso, "parent" si riferisce ai facet di categoria, non alle categorie di primo livello di un facet nidificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Selezione multipla categoria </p> </td> 
   <td colname="col2"> <p>Come il tipo di facet nidificato Multi-Select con le seguenti eccezioni: </p> 
    <ul id="ul_D5AB6AF3169A483E8F3FC6D2A2EA3A28"> 
     <li id="li_9308156EF2FF43CE9DFB933F13786C58">Se questo facet è selezionato per la prima volta, viene deselezionato qualsiasi altro facet precedentemente scelto. </li> 
     <li id="li_DD96D6802A9C479283212A0FD68C6F85">Anche gli altri facet precedentemente scelti vengono deselezionati se il cliente effettua un drill-down direttamente al facet figlio senza fare clic sul facet padre o viene selezionato un facet padre diverso. </li> 
     <li id="li_8BF58F10969B4743986D5D0E0086AD6C">Possono avere genitori nel senso che le sfaccettature di categoria hanno genitori. Non confondere questo comportamento con le relazioni padre-figlio trovate con tutti i facet nidificati. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Vedere anche [Informazioni sulla barra laterale](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB).

## Aggiunta di un nuovo facet {#task_FC07BFFA62CA4B718D6CBF4F2855C89B}

È possibile aggiungere facet per personalizzare il livello di presentazione e fornire ai clienti una Ricerca guidata che consenta loro di approfondire i risultati della ricerca.

<!-- 

t_adding_a_new_facet.xml

 -->

La tabella dei facet nella pagina [!DNL Facets] mostra un estratto delle impostazioni che compongono un singolo facet. Puoi aggiungere nuovi facet e modificare o eliminare quelli esistenti. Qualsiasi modifica apportata ai facet può essere ripristinata utilizzando la funzione Cronologia .

>[!NOTE]
>
>Assicurati di fare riferimento al facet nel modello di presentazione in modo che sia visibile sul sito web.

Vedere anche [Informazioni sulla barra laterale](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB).

**Per aggiungere un nuovo facet**

1. Prima di aggiungere un nuovo facet, accertati di aver già eseguito le operazioni seguenti prima di procedere al passaggio successivo:

   * Alcuni campi meta tag sono già definiti.

      Consulta [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
   * Inserisci i metadati nel tuo indice.
Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

1. Nel menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facets.]**
1. Nella pagina [!DNL Facets], fai clic su **[!UICONTROL Add New Facet]**.
1. Nella pagina [!DNL Add Facet] , imposta le opzioni desiderate.

   Queste impostazioni influiscono sia sul comportamento che sulla presentazione predefinita di un facet. È possibile ignorare alcune di queste impostazioni tramite le impostazioni del modello di presentazione.

   Se un facet è definito come tipo di data nei metadati, viene visualizzato come intervallo di date.

   Vedere [Facet intervallo date](../c-about-design-menu/c-about-facets.md#section_FEFFF6B5B6534456913189FEF559BA58).

   A seconda delle opzioni di facet selezionate, non tutte le opzioni sono disponibili.

   <!-- 
   r_add_facet_options.xml
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome facet </p> </td> 
      <td colname="col2"> <p>Identifica il nome di un dato facet. </p> <p> <p>Nota:  Puoi avere un solo facet basato sui metadati definiti dall’utente esistenti. Se nell’elenco a discesa non sono disponibili facet, è innanzitutto necessario definire alcuni metadati. </p> </p> <p>Consulta <a href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita" scope="local"> Aggiunta di un nuovo campo meta tag </a>. </p> <p>Per creare un facet basato su una tabella di campi, utilizza il nome del facet personalizzato e specifica il nome della tabella di campi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Etichetta visualizzazione </p> </td> 
      <td colname="col2"> <p>Imposta l’etichetta di un facet che può quindi essere utilizzato in una breadcrumb, invece di un nome di campo di metadati (con il tag <span class="codeph"> &lt;guide-breadcrumb-label&gt; </span> ) o un valore autonomo (con il tag <span class="codeph"> &lt;guide-facet-display-name&gt; </span> ). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Comportamento </p> </td> 
      <td colname="col2"> <p>Imposta uno dei tre comportamenti dei facet. </p> <p> 
      <ul id="ul_67C19E1C16224B9990F04A0D05BD3D05"> 
      <li id="li_6B232C11A61840B68CA59E1F593405A0"> <span class="uicontrol"> Normale </span> <p>Quando un cliente fa clic su un facet il cui comportamento è impostato su <span class="uicontrol"> Normale </span>, esegue un drill-down dei risultati di ricerca per tale elemento. Da lì, il cliente può perfezionare e restringere ulteriormente il numero di risultati di ricerca. </p> </li> 
      <li id="li_7D7C43A7F7AB4B84A9B0FEF34627605A"> <span class="uicontrol"> Categoria </span> <p>I facet delle categorie si comportano come elementi di navigazione. Questi facet sono facet di primo livello che i clienti in genere analizzano prima di rivelare i facet con le opzioni degli attributi. I facet delle categorie non si restringono quando sono selezionati altri facet e rimangono aperti. Facendo clic su un valore diverso all’interno di un facet di categoria, si deseleziona tutti gli altri facet della pagina eccetto quelli principali del facet di categoria. </p> </li> 
      <li id="li_01255993D71F40DBA8870AA3FEA7D304"> <span class="uicontrol"> Selezione multipla categoria  </span> <p>i facet sono sfaccettature di categoria che supportano la selezione di più elementi dal facet in cui gli elementi sono "ORed" insieme. </p> </li> 
      </ul> 
      <ul id="ul_683F6D3FC8524E65AF303453ADDB6001"> 
        <li id="li_81F504D1D1294666BBBC5EA43B34B712"> <span class="uicontrol"> In rilievo </span> <p>Quando un cliente fa clic su un facet il cui comportamento è impostato su <span class="uicontrol"> Sticky </span>, il facet con l’opzione selezionata rimane aperto durante il drill-down. Questa opzione è utile quando desideri consentire a un cliente di cambiare una scelta precedente. </p> </li> 
      </ul> 
      <ul id="ul_8E871D63B09445268C600C8ABC20F6A4"> 
        <li id="li_F88AC5528B0C4751BC4CFE7FA9525857"> <span class="uicontrol"> Selezione multipla  </span> <p>Consente la selezione di più elementi da un facet, dove gli elementi all’interno del facet sono "ORed" insieme. Questa opzione è utile per un facet che può mostrare un attributo minore come i colori e vuoi consentire al cliente di creare una query che consenta loro di "mostrare scarpe nella mia dimensione che sono rosse o nere". </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mostra sempre </p> </td> 
      <td colname="col2"> <p>Per un facet normale o fisso, imposta il facet in modo che rimanga visibile al cliente in qualsiasi momento. </p> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Normale </span>, <span class="uicontrol"> Categoria </span> o <span class="uicontrol"> Sticky </span> dall'elenco a discesa <span class="uicontrol"> Comportamento </span> . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Genitori di Facet </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Categoria </span> o <span class="uicontrol"> Categoria Selezione multipla </span> dall'elenco a discesa <span class="uicontrol"> Comportamento </span> . </p> <p>Indica quali sono i genitori del facet della categoria. Gli elementi selezionati nelle categorie facet padre vengono utilizzati per limitare le scelte disponibili all'interno del facet categoria corrente. I facet padre non vengono deselezionati quando un cliente interagisce con il facet categoria. È possibile specificare più elementi padre delimitati da virgole. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Profondità adesiva </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Sticky </span> dall'elenco a discesa <span class="uicontrol"> Comportamento </span> . </p> <p>Imposta il numero di opzioni che devono rimanere aperte durante il drill-down. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Soglia lunghezza </p> </td> 
      <td colname="col2"> <p>Imposta la lunghezza verticale (1-9999) del facet definito in numero di elementi. </p> <p>Se il modello di presentazione è configurato correttamente, è possibile utilizzare questa impostazione per fornire un "Mostra altro..." o determinare quando lanciare il facet in un div scorrevole e così via. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Soglia per lunghezze troncate </p> </td> 
      <td colname="col2"> <p>Tronca il numero di elementi in un facet dopo una determinata soglia. </p> <p>Alcune implementazioni hanno facet con migliaia di elementi. Può essere costoso inviare tutti i dati via cavo. È possibile utilizzare questa impostazione per ridurre il facet a un livello gestibile. Il facet viene troncato dopo l’ordinamento. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Larghezza max. </p> </td> 
      <td colname="col2"> <p>Specifica un limite alla lunghezza della stringa del valore del facet (1-999). </p> <p>Questa opzione è utile quando si desidera inserire un facet in un layout a larghezza fissa e impedire che le stringhe si racchiudano. Per impostazione predefinita, la stringa è impostata su 3 caratteri più corti della soglia, in modo da poter aggiungere un puntino di sospensione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Estensione valore </p> </td> 
      <td colname="col2"> <p>Specifica la stringa da utilizzare per indicare che il valore di un facet è troncato. Per impostazione predefinita, la stringa ".." viene utilizzato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimitatore </p> </td> 
      <td colname="col2"> <p>Specifica il delimitatore da utilizzare per qualsiasi elenco di valori separati delimitati applicato al facet. </p> <p>Il delimitatore utilizzato è lo stesso definito nei metadati su cui si basa il facet. Il delimitatore predefinito è una virgola. Tuttavia, è possibile utilizzare qualsiasi valore conforme a XML. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ordinare </p> </td> 
      <td colname="col2"> <p>Specifica la modalità di ordinamento dei facet nel sito web. I facet possono essere ordinati come segue. Se lo desideri, puoi combinare fino a cinque tipi. </p> 
      <ul id="ul_12987F4DC7B34C63ABC906B59688A174"> 
      <li id="li_3206C96013DF431D90119F594D93D85D"> <span class="uicontrol"> alfa  </span> <p>Ordina i valori in ordine alfabetico (0-9, A-Z), compresi i caratteri di punteggiatura. </p> </li> 
      <li id="li_304E4A518FBE48D18D9E9EA7339A3481"> <span class="uicontrol"> alfa (solo alfanumerico)  </span> <p>Ordina i valori in ordine alfabetico (0-9, A-Z), ignorando i caratteri di punteggiatura. </p> </li> 
      <li id="li_CADB888CC514455F9CA379C8EEE490AA"> <span class="uicontrol"> alfa (senza distinzione maiuscole/minuscole)  </span> <p>Ordina i valori in ordine alfabetico (0-9, A-Z), ignorando le lettere maiuscole in minuscole e viceversa. </p> </li> 
      <li id="li_F61122E79AB5413792DA31F8AB1414BD"> <span class="uicontrol"> alfa (non sensibile a maiuscole e minuscole, solo alfanumerico)  </span> <p>Ordina i valori in ordine alfabetico (0-9, A-Z), ignorando le lettere maiuscole in minuscole e viceversa. </p> </li> 
      <li id="li_F50CC298ABF046D0A39D5AE5B1261823"> <span class="uicontrol"> count  </span> <p>Ordina per numero di risultati che corrispondono a ciascun valore di facet da maggiore a minore. </p> </li> 
      <li id="li_32B6AF39E9534762B39B15181DC5AD01"> <span class="uicontrol"> numerico  </span> <p>Ordina i valori numericamente. Quando si ordinano i numeri, questa opzione è superiore a un ordinamento Alfa perché se si utilizza un ordinamento Alfa, viene visualizzato 10 prima di 2. </p> </li> 
      <li id="li_CF8E76A7B1184E0C8DCC11B53E31A1DC"> <span class="uicontrol"> dividere  </span> <p>Divide l’elenco in due elenchi separati per soglia di conteggio. I valori dei facet al di sopra della soglia vengono spostati nella parte superiore. I valori dei facet con conteggi inferiori alla soglia vengono spostati in basso. È necessaria una soglia di suddivisione quando desideri che i valori di un determinato intervallo siano sempre nella parte superiore. </p> </li> 
      <li id="li_4AB8276577384B1099CBA895898205AD"> <span class="uicontrol"> break  </span> <p>Forza alcuni valori nella parte superiore o inferiore dell’elenco. Ad esempio, è sempre possibile visualizzare il termine "Altro" in fondo all’elenco. Quando utilizzi un ordinamento a barre per identificare i valori espliciti che devono trovarsi nella parte superiore o inferiore dell’ordinamento, sono necessari valori superiori o inferiori o valori inferiori. </p> </li> 
      <li id="li_227E96CFED2044FCA2F10B6913B03CFB"> <span class="uicontrol"> ordinato  </span> <p>I valori dei facet devono sempre essere in ordine fisso (un elenco di valori delimitatori separati definito nell'opzione <span class="uicontrol"> Ordine </span> descritta di seguito). </p> </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Alias del facet </p> </td> 
      <td colname="col2"> <p>Per supportare gli URL di ricerca esistenti che potrebbero essere presenti nel carattere jolly, puoi utilizzare un alias di facet per mappare il nome del parametro legacy su modificato o semplicemente creare un facet con un nome diverso. L’alias viene applicato solo alle richieste in arrivo e non viene utilizzato per creare collegamenti facet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome della barra di sfaccettatura </p> </td> 
      <td colname="col2"> <p>Nome della barra dei facet se si decide di ordinare i facet in ordine alfabetico, per conteggio o con un metodo personalizzato. </p> <p>Consulta <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> Informazioni sulla barra laterale </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ordine </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Ordinato </span> dall'elenco a discesa <span class="uicontrol"> Ordina </span> . </p> <p>Consente di definire un elenco delimitato di valori che specifica l’ordine da utilizzare. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi altri </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Ordinato </span> dall'elenco a discesa <span class="uicontrol"> Ordina </span> . </p> <p>Se i valori non sono presenti nell’elenco ordinato, questi vengono aggiunti alla fine. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mostra fantasmi </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Ordinato </span> dall'elenco a discesa <span class="uicontrol"> Ordina </span> . </p> <p>Se mancano i valori specificati dall'elenco ordinato, questa opzione contrassegna ogni elemento mancante nel facet come "fantasma" in modo che gli elementi vengano visualizzati in modo diverso. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet nidificato </p> </td> 
      <td colname="col2"> <p>Un facet nidificato visualizza le relative categorie e le relative categorie figlio. Può mostrare solo una profondità di due categorie, ma può essere ovunque lungo il drill-down. </p> <p>I dati per questo facet devono seguire una convenzione per descrivere i due livelli di categorie. Ad esempio, un valore di facet può essere "shoes:boots", dove la categoria principale è "shoes" e la categoria figlio è "boots". Il valore ':' viene utilizzato come delimitatore per separarli. </p> <p>Per ulteriori informazioni sulla modifica del delimitatore, consulta Delimitatore nidificato di seguito. </p> <p>Per generare i dati in questo formato, è possibile utilizzare uno script di filtro per combinare due categorie esistenti. È possibile combinare i comportamenti Normale, Categoria e Adesivo con i facet nidificati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome padre nidificato </p> </td> 
      <td colname="col2"> <p>Questo elenco a discesa è disponibile solo se è stato selezionato <span class="uicontrol"> Facet nidificato </span>. </p> <p>Consente di scegliere quale campo rappresenta la categoria principale. Questo campo viene utilizzato durante il tempo di ricerca nelle categorie padre corrispondenti. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome figlio nidificato </p> </td> 
      <td colname="col2"> <p>Questo elenco a discesa è disponibile solo se è stato selezionato <span class="uicontrol"> Facet nidificato </span>. </p> <p>Consente di scegliere quale campo rappresenta la categoria figlio. Questo campo viene utilizzato durante il tempo di ricerca nelle categorie figlio corrispondenti. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimitatore di sfaccettature nidificate </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Facet nidificato </span>. </p> <p>Il carattere immesso viene utilizzato per analizzare le categorie padre e figlio dai relativi dati. </p> <p>Ad esempio, se ':' viene utilizzato come delimitatore e il padre è 'shoes' e il figlio è 'boots', si aspetta che i dati vengano formattati come 'shoes:boots'. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Soglia di divisione </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Dividi </span> dall'elenco a discesa <span class="uicontrol"> Ordina </span> . </p> <p>Quando si utilizza un ordinamento diviso, la soglia di suddivisione definisce il conteggio in cui dividere il facet in due elenchi separati. I valori con conteggi maggiori o uguali alla soglia vengono mantenuti nella parte superiore, mentre i valori al di sotto della soglia vengono spostati nella parte inferiore. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valori principali </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Interrompi </span> dall'elenco a discesa <span class="uicontrol"> Ordina </span> . </p> <p>Quando si utilizza un ordinamento Interruzione, questo elenco delimitato di valori viene sempre posizionato in cima all’elenco. L’uso di espressioni regolari è consentito ma deve essere tra parentesi graffe o parentesi graffe, ad esempio: {^Nuovo .*?},{^Molto Nuovo .*} </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valori inferiori </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Interrompi </span> dall'elenco a discesa <span class="uicontrol"> Ordina </span> . </p> <p>Quando si utilizza un ordinamento Interruzione, questo elenco delimitato di valori viene sempre posizionato in fondo all’elenco. L’uso di espressioni regolari è consentito ma deve essere tra parentesi graffe o parentesi graffe, come nell’esempio seguente: {^Vecchio .*?},{^Molto vecchio .*} </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Nella pagina [!DNL Facets] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Aggiunta di un facet nidificato {#task_A132FA7EB7494A6B88E443F2C3FABBBA}

Puoi aggiungere un facet nidificato per visualizzare più livelli di categorie.

<!-- 

t_adding_a_nested_facet.xml

 -->

Quando create un facet nidificato, tenete presente quanto segue:

* Ogni facet nidificato richiede un campo meta tag definito dall’utente.
* I facet nidificati sono composti da altri due facet, il facet padre e il facet figlio. Possono essere sfaccettature a valore singolo o sfaccettature a più valori. Non è consentita la combinazione di facet a valore singolo e facet a più valori.
* È necessario determinare se questo facet verrà utilizzato nella tabella dei campi di ricerca. La tabella dei campi richiede il facet nidificato e i relativi facet compositi.
* Valuta l’utilizzo di JSON per implementare i facet nidificati; è più facile.

* [Attività 1 - Aggiungere un tag meta](../c-about-design-menu/c-about-facets.md#task_6944558325204E749C725DCFEF17EF3D)
* [Attività 2 - Aggiungi uno script di filtro per generare dati preformattati](../c-about-design-menu/c-about-facets.md#task_2DFED8BCB87B4067A6CE280945D7CAF4)
* [Attività 3 - Aggiungi un nuovo facet](../c-about-design-menu/c-about-facets.md#task_3C11A4159FC44B9494D48594941AF8CF)
* [Attività 4 - Modifica ricerca guidata](../c-about-design-menu/c-about-facets.md#task_E50EFD7BBD0F45729C15759EA4F548D8)
* [Attività 5 - Creare il modello di trasporto](../c-about-design-menu/c-about-facets.md#task_C1FEDEF11D2549DEB1A9C09BFBA64381)
* [Attività 6 - Creare il modello di presentazione](../c-about-design-menu/c-about-facets.md#task_4B2ABB37B9CD4F3F8AF8E6874227A995)
* [Attività 7 - Modificare la breadcrumb](../c-about-design-menu/c-about-facets.md#task_5E22409528EC4DA284821F82FDCE3438)

>[!NOTE]
>
>Questo argomento fa riferimento al facet nidificato come facet n1.

## Task 1 - Aggiungere un tag meta {#task_6944558325204E749C725DCFEF17EF3D}

Aggiungi un nuovo campo meta tag dedicato alla data del facet nidificato. Può essere un campo multivalore o un campo a valore singolo.

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Nella pagina [!DNL Definitions], fai clic su **[!UICONTROL Add New Field]**.
1. Nella pagina [!DNL Add Field] , imposta le opzioni desiderate.

   Consulta [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

   Le altre attività fanno riferimento a questo campo del metatag come **n1**.

## Attività 2 - Aggiungi uno script di filtro per generare dati preformattati {#task_2DFED8BCB87B4067A6CE280945D7CAF4}

1. Aggiungi uno script di filtro per combinare i facet originali nel seguente formato: `<parent_value><nested_delimiter><child_value>`.

   Vedere [Aggiunta di uno script di filtro](../c-about-settings-menu/c-about-filtering-menu.md#task_0AB84FD1133F47F9AA069A79BEA13A22).

   Di seguito sono riportati alcuni esempi di valori per il campo meta tag n1, utilizzando il formato di cui sopra

   `Womens:Handbags`

   `Womens:Dresses`

   `Mens:Accessories`

   `Mens:Footwear`
1. Dopo aver creato o modificato lo script di filtraggio, testarlo. Se sembra corretto, reindicizza il tuo account, se appropriato. Puoi controllare l&#39;indice utilizzando [!DNL Index Overview].

   Gli esempi seguenti presuppongono che alcune librerie di consulenza standard siano incluse nell&#39;inizializzazione dello script di filtro. Ricorda che ogni account è diverso, pertanto il tuo script di filtraggio dovrebbe riflettere i requisiti necessari per il tuo account.

   **Esempio di script di filtro con più valori**

   ```
   my $doc; 
   { 
   # Slurp all the data into $doc 
   local $/; 
   undef $/; 
   $doc = <>; 
   } 
    # Create n1 field 
    if ( $doc =~ m{<meta\s+name="t1"\s+content="([^\"]*)"}is ) 
    { 
     my @t1arr = split(/\|/, $1); 
     if (scalar @t1arr > 0) 
     { 
      if ( $doc =~ m{<meta\s+name="t2"\s+content="([^\"]*)"}is ) 
      { 
       my @t2arr = split(/\|/, $1); 
   
       if ( scalar @t2arr > 0 ) 
       { 
        my $max = ((scalar @t1arr) < (scalar @t2arr)) ? (scalar @t1arr) : (scalar @t2arr); 
        for (my $i = 0; $i < $max; $i++) 
        { 
         $t1arr[$i] .= ":" . $t2arr[$i]; 
        } 
       } 
      } 
      my $output = join( '|', @t1arr ); 
      $doc =~ s{</head>}{<meta name="n1" content="$output" />\b</head>}is; 
     } 
    } 
    # END: n1 field
   ```

   **Esempio di script di filtro a un singolo valore**

   ```
   # This is a complete example. 
   # This script is designed for index connector where each record 
   # in the XML file is converted into a fake HTML page filled with 
   # meta data tags.  
   my $doc; 
   { 
   # Slurp all the data 
   local $/; 
   undef $/; 
   $doc = <>; 
   } 
   # All legitimate index connector data has key in its URL. 
   # Process the page if and only if it is coming from index connector and 
   # it is not the first entry point page.  Entry point pages don't have key 
   # in the URL. 
   if ($main::search_url =~ /\?key=/) { 
    my $meta = {}; 
    # Mine and scrape the meta fields from the page 
    my @lines = split(/\n/,$doc); 
    foreach my $line (@lines) 
    { 
     if ($line =~ m{<meta name="(.*?)" content="(.*?)" />}) 
     { 
      $meta->{lc($1)} = $2; 
     } 
    } 
    # Combined t1,t2 and t2,t3, and t3,t4 together. 
    # Assign them respectively to n1, n2, and n3. 
    my ($t1, $t2, $t3, $t4); 
    my %meta2; 
    $t1 = $meta->{'t1'}; 
    $t2 = $meta->{'t2'}; 
    $t3 = $meta->{'t3'}; 
    $t4 = $meta->{'t4'}; 
    if (defined $t1 && $t1) { 
     $meta2{'n1'} = $t1; 
     if (defined $t2 && $t2) { 
      $meta2{'n1'} .= ":" . $t2; 
      $meta2{'n2'} = $t2; 
      if (defined $t3 && $t3) { 
      $meta2{'n2'} .= ":" . $t3; 
       $meta2{'n3'} = $t3; 
       if (defined $t4 && $t4) { 
        $meta2{'n3'} .= ":" . $t4; 
       } 
      } 
     } 
    } 
    foreach my $stuff ( keys %meta2 ) 
    { 
     my $v = $meta2{$stuff}; 
     $doc =~ s{</head>}{<meta name="$stuff" content="$v" />\n</head>}; 
    } 
   } 
   
   # Do some ranking stuff here 
   ws_insert_static_rank_meta_tag(\$doc, "RANK"); 
   
   # Prints the entire page back out. 
   print $doc;
   ```

## Attività 3 - Aggiungi un nuovo facet {#task_3C11A4159FC44B9494D48594941AF8CF}

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facets]**.
1. Nella pagina [!DNL Facets], fai clic su **[!UICONTROL Add New Facet]**.
1. Nella pagina [!DNL Add Facet] , imposta le seguenti opzioni:

   * Nell’elenco a discesa [!DNL Facet Name] , seleziona il campo meta tag definito nell’attività 1. Se utilizzi tabelle di campi di ricerca, seleziona **[!UICONTROL custom]** nell’elenco a discesa, quindi immetti il nome personalizzato del facet.

   * Seleziona **[!UICONTROL Nested Facet]** per &quot;attivare&quot; i facet nidificati.
   * Negli elenchi a discesa [!DNL Nested Parent Name] e [!DNL Nested Child Name] , scegli i campi meta tag che puoi utilizzare. Se utilizzi tabelle di campi di ricerca, seleziona **[!UICONTROL custom]** e immetti il nome personalizzato del facet.

   * Nel campo [!DNL Nested Facet Delimiter] , specifica il delimitatore da utilizzare, ad esempio un segno &quot;:&quot; (due punti). Non confonderlo con il delimitatore a più valori. Entrambi i delimitatori devono essere diversi tra loro.
   * Se imposti il comportamento del facet **[!UICONTROL Category]**, puoi specificare gli elementi principali del facet (non confondere l’elemento padre con gli elementi padre dei facet nidificati). In generale, non utilizzare mai il nome di un altro facet nidificato come padre di categoria. Utilizza invece i singoli facet che compongono il facet nidificato.
   * Imposta tutte le altre opzioni di facet desiderate.

   Consulta [Aggiunta di un nuovo facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B).
1. Clic **[!UICONTROL Add]**.

## Attività 4 - Modifica ricerca guidata {#task_E50EFD7BBD0F45729C15759EA4F548D8}

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**.
1. Nelle pagine [!DNL Searches] fare clic su **[!UICONTROL Edit]** nel nome del tipo di ricerca che si desidera aggiornare.
1. Il `sp_field_table` richiede il campo n1, t1 e t2.

   Se si utilizzano tabelle di campi, è necessario modificare il parametro `sp_field_table` . In alternativa, puoi eseguire questa operazione altrove utilizzando le regole di pulizia delle query o le regole di pre-ricerca.

   Vedere [Aggiunta di una regola di pulizia delle query](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54).

   Consulta [Aggiunta di una nuova regola di pre-ricerca](../c-about-rules-menu/c-about-pre-search-rules.md#task_182B95918462490D8BDA7F16A81CAC11).
1. Clic **[!UICONTROL Save Changes]**.

## Attività 5 - Creare il modello di trasporto {#task_C1FEDEF11D2549DEB1A9C09BFBA64381}

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nelle pagine [!DNL Templates], fai clic su **[!UICONTROL Add New Template]**.
1. Nella finestra di dialogo [!DNL Add Template], specifica il nome del file modello di trasporto.
1. Nell’elenco a discesa [!DNL New Template Type] , seleziona **[!UICONTROL Transport]**.
1. Clic **[!UICONTROL Add]**.
1. Nella pagina [!DNL Templates] , fai clic sul nome del file del modello di trasporto appena aggiunto.
1. Nella pagina [!DNL Template Editor] del modello di trasporto, includi i dati provenienti dal campo n1. Vedi i seguenti esempi.

   **Esempio XML di restituzione di** dati di facet nidificatiL&#39;esempio XML deve specificare quale carattere viene utilizzato come delimitatore tra i valori di facet. In questo caso, è una tubazione (|).

   ```
   <facet name="n1"> 
     <values delimiter="|"><search-field-value-list name="n1" quotes="no" separator="|" sortby="values" data="values" /></values> 
     <counts><search-field-value-list name="n1" quotes="no" sortby="values" data="results" /></counts> 
   </facet>
   ```

   **Esempio JSON di restituzione di dati di facet nidificati**

   ```
   { 
      "name" : "n1", 
      "values" : [ <search-field-value-list name="n1" quotes="yes" sortby="values" data="values" encoding="json"/>], 
      "counts" : [<search-field-value-list name="n1" quotes="no" sortby="values" data="results" />] 
   },
   ```

## Attività 6 - Creare il modello di presentazione {#task_4B2ABB37B9CD4F3F8AF8E6874227A995}

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nelle pagine [!DNL Templates], fai clic su **[!UICONTROL Add New Template]**.
1. Nella finestra di dialogo [!DNL Add Template], specificare il nome del file del modello di presentazione.
1. Nell’elenco a discesa [!DNL New Template Type] , seleziona **[!UICONTROL Presentation]**.
1. Clic **[!UICONTROL Add]**.
1. Nella pagina [!DNL Templates] fare clic sul nome del file del modello di presentazione appena aggiunto.
1. Nella pagina [!DNL Template Editor] del modello di presentazione, aggiungi il markup HTML che si integra con l&#39;output previsto.

   Per visualizzare i tag secondari è possibile utilizzare i seguenti tag:

* **Se esistono tag figlio** `<guided-if-facet-value-has-children><guided-else-facet-value-selected></guided-if-facet-value-has-children>`

* **Tag Valore figlio** `<guided-facet-value-children></guided-facet-value-children>`

   I tag Valore figlio non si comportano come normali tag di facet-value guidati. I tag wrapper sono che forzano l’iterazione di tutti i tag `<guided-facet-value>` inclusi tra i valori dei facet figlio invece dei valori dei facet padre. Analogamente, altri tag facet guidato, come i tag di annullamento, seguono la stessa cosa. Si consiglia di utilizzarli all’interno dei tag `<guided-if-facet-value-has-children>` .

   Di seguito è riportato un esempio di modello di presentazione con marcatura HTML.

   ```
   <guided-facet gsname="n1"> 
   <guided-if-facet-selected> 
    <guided-facet-values> 
    <guided-if-facet-value-selected> 
     <li><span class="selected"><guided-facet-value /></span><guided-facet-value-undo-link gsname="n1">X</guided-facet-value-undo-link></li> 
     <guided-if-facet-value-has-children> 
      <ul> 
      <guided-facet-value-children> 
      <guided-if-facet-value-selected> 
       <li><span class="selected"><guided-facet-value /></span><guided-facet-value-undo-link gsname="n1">X</guided-facet-value-undo-link></li> 
      <guided-else-facet-value-selected> 
       <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
      </guided-if-facet-value-selected> 
      </guided-facet-value-children> 
      </ul> 
     </guided-if-facet-value-has-children> 
    <guided-else-facet-value-selected> 
     <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
     <guided-if-facet-value-has-children> 
      <ul> 
      <guided-facet-value-children> 
       <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
      </guided-facet-value-children> 
      </ul> 
     </guided-if-facet-value-has-children> 
    </guided-if-facet-value-selected> 
    </guided-facet-values> 
   <guided-else-facet-selected>  
    <guided-facet-values> 
    <guided-if-facet-value-selected> 
     <li><span class="selected"><guided-facet-value /></span><guided-facet-value-undo-link gsname="n1">X</guided-facet-value-undo-link></li> 
     <guided-if-facet-value-has-children> 
      <ul> 
      <guided-facet-value-children> 
       <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
      </guided-facet-value-children> 
      </ul> 
     </guided-if-facet-value-has-children> 
    <guided-else-facet-value-selected> 
     <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
     <guided-if-facet-value-has-children> 
      <ul> 
      <guided-facet-value-children> 
       <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
      </guided-facet-value-children> 
      </ul> 
     </guided-if-facet-value-has-children> 
    </guided-if-facet-value-selected> 
    </guided-facet-values> 
   </guided-if-facet-selected> 
   </guided-facet>
   ```

## Attività 7 - Modificare la breadcrumb {#task_5E22409528EC4DA284821F82FDCE3438}

Se utilizzi le breadcrumb nella ricerca, devi impostare il comportamento su **Vai a**.

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Nelle pagine [!DNL Breadcrumbs] , fai clic su **[!UICONTROL Edit]** nel nome della breadcrumb di cui vuoi aggiornare il comportamento.
1. Nella pagina [!DNL Edit Breadcrumb], seleziona [!DNL Behavior] dall’elenco a discesa **Vai a**.
1. Clic **[!UICONTROL Save Changes]**.

## Modifica di un facet {#task_457EDC49983F4F7781873703AF574DA5}

Puoi modificare le impostazioni di qualsiasi facet aggiunto.

<!-- 

t_editing_a_facet.xml

 -->

>[!NOTE]
>
>Assicurati di fare riferimento al facet nel modello di presentazione in modo che sia visibile sul sito web.

**Per modificare un facet**

1. Nel menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facets.]**
1. Nella pagina [!DNL Facets] , fai clic su **[!UICONTROL Edit]** all’estrema destra del nome di un facet.
1. Nella pagina [!DNL Edit Facet] , imposta le opzioni desiderate.

   Vedi la tabella delle opzioni in [Aggiunta di un nuovo facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella pagina [!DNL Facets] ,

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di un facet {#task_17756FD66BCC49629325B2217F821BDD}

Puoi eliminare qualsiasi facet aggiunto.

<!-- 

t_deleting_a_facet.xml

 -->

**Per eliminare un facet**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facets]**.
1. Nella pagina [!DNL Facets] , fai clic su **[!UICONTROL Delete]** all’estrema destra del nome di un facet.
1. Nella finestra di dialogo [!DNL Confirmation] fare clic su **[!UICONTROL OK]**.
1. Esegui una delle operazioni seguenti:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
