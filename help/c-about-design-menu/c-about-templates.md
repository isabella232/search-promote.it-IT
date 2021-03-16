---
description: È possibile utilizzare Modelli per gestire i modelli di presentazione e di trasporto.
solution: Target
title: Informazioni sui modelli
topic: Progettazione, ricerca nel sito e merchandising
uuid: f5805d3e-43bf-4e13-95df-b6bd6b762d11
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '2652'
ht-degree: 1%

---


# Informazioni sui modelli{#about-templates}

È possibile utilizzare **[!UICONTROL Templates]** per gestire i modelli di presentazione e di trasporto.

## Informazioni sui modelli {#concept_06EB481B14864E18A8AE2BCD1D6EF0B5}

<!-- 

c_about_templates.xml

 -->

È possibile aggiungere, modificare, copiare, rinominare o eliminare modelli di presentazione e modelli di trasporto. Quando fai clic su un nome di modello esistente nella tabella Modelli , questo viene aperto in una finestra dell’editor (o visualizzatore) in cui puoi apportare le modifiche.

È possibile ripristinare le modifiche apportate ai modelli utilizzando la funzione Cronologia dall&#39;elenco a discesa del nome del modello nella tabella Modelli.

È possibile ridurre il peso della pagina di un modello di presentazione selezionando la casella di controllo corrispondente del modello **[!UICONTROL Minimize]** nella tabella del modello. Riducendo il peso della pagina del modello, riduci dinamicamente i codici JavaScript e CSS in linea. È inoltre possibile rimuovere gli spazi vuoti ridondanti nell’HTML. Ridurre al minimo il peso della pagina del modello di presentazione può aiutare a fornire i risultati di ricerca più rapidamente.

Per visualizzare un’anteprima dell’aspetto del modello ridotto a icona, fai clic sull’elenco a discesa accanto al nome del file e quindi fai clic su **[!UICONTROL Preview minimized]**. Se si riduce a icona il modello di presentazione principale, ricordare di abilitare la riduzione a icona per i modelli inclusi (con tag `guided-include`) perché questa opzione non è ereditabile.

Anche se si riduce a icona un modello di presentazione, è comunque possibile modificare la versione &quot;non minimizzata&quot; dello stesso modello.

È possibile utilizzare le regole di pre-ricerca, le regole di post-ricerca e le regole aziendali per determinare quando utilizzare uno degli altri modelli di presentazione. È comune avere una regola come &quot;Per ogni ricerca, imposta il modello di destinazione su xxxx&quot;. Con tale regola, quando si modifica il modello &quot;Predefinito&quot; nella tabella Modelli, sembra che non abbia alcun effetto.

Consulta [Informazioni sulle regole di pre-ricerca](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

Consulta [Informazioni sulle regole di post-ricerca](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

Consultare [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Informazioni sui modelli di presentazione {#section_ACDDEA5C499E481C828A517C230D4596}

I modelli di presentazione sono modelli HTML che un cliente vede quando visualizza i risultati della ricerca sul sito web.

Nel livello di presentazione, è possibile avere un singolo modello di presentazione che presenta i risultati di più ricerche da varie sorgenti. È possibile definire tutti i modelli di presentazione desiderati e persino definire modelli di presentazione condivisi da altri modelli utilizzando i comandi `include`. Il modello di presentazione è il luogo in cui tutti i componenti Design, come facet, menu e breadcrumb, si riuniscono. Per visualizzare i vari componenti di progettazione, è necessario utilizzare i tag modello di presentazione.

Vedere [Tag del modello di presentazione](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

Quando si dispone di più modelli di presentazione, è possibile definire le condizioni in cui vengono utilizzati i vari modelli di presentazione. È possibile selezionare il modello di presentazione da utilizzare in base ai parametri e ai cookie CGI in arrivo. In alternativa, è possibile cambiare il modello di presentazione utilizzato in base al risultato di una ricerca precedente.

Quando si utilizzano più modelli di presentazione, assicurarsi di indicare quale modello si desidera visualizzare inizialmente i risultati di ricerca. A tale scopo, utilizza la colonna **[!UICONTROL Default]** della tabella Modelli .

## Informazioni sui modelli di trasporto {#section_35FD3E8AAA4E4695A737DB7E00C3258B}

I modelli di trasporto possono essere modelli XML o JSON che trasmettono i dati dalla ricerca back-end al livello di presentazione Guided Search.

Per impostazione predefinita, l’account è configurato per utilizzare modelli di trasporto XML. Tuttavia, se preferisci utilizzare JSON per passare i tuoi dati alla Ricerca guidata, contatta Adobe Consulting per aiutarti.

Nel livello di presentazione, è possibile avere un singolo modello di presentazione che presenti i risultati di più ricerche. Ogni ricerca può utilizzare lo stesso modello di trasporto o un modello di trasporto personalizzato per passare i dati al livello di presentazione. Poiché il modello di trasporto viene utilizzato solo per trasmettere dati al livello della presentazione, non deve avere alcun HTML utilizzato per visualizzare i risultati della ricerca. Il modello utilizza i tag del modello di trasporto per trasmettere i risultati della ricerca e i risultati per la compilazione dei facet. All’interno di questi tag, i tag modello di ricerca standard vengono utilizzati per visualizzare i valori effettivi.

Consulta [Ricerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

**Tag specifici del modello di trasporto XML**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag modello di trasporto XML </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>Si tratta dei tag XML principali utilizzati dal livello di presentazione per rilevare ciò che deve analizzare dal modello di trasporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo insieme di tag racchiude i tag dei modelli di ricerca che forniscono dati di riepilogo in base al set di risultati. In genere, questi tag contengono tag di ricerca per il numero totale di risultati, il risultato più basso e il risultato più alto. Puoi definire un numero qualsiasi di campi globali aggiuntivi desiderati con il tag <span class="codeph"> general-field </span> . </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;general&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo set di tag è racchiuso intorno ai risultati della ricerca, in modo che la Ricerca guidata sappia dove cercarli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo set di tag viene racchiuso intorno a ogni risultato di ricerca, in modo che la Ricerca guidata riconosca dove inizia e termina il contenuto di un singolo risultato di ricerca. </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo tag consente di scorrere in sequenza ogni elemento di un elenco con più valori per un singolo risultato. Utilizza il tag solo all’interno di un risultato. Lo scopo principale è quello di consentire l’iterazione degli attributi appartenenti a un campo risultato. </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo insieme di tag passa sui risultati che popolano i facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ogni facet deve avere i propri tag facet in cui il parametro name corrisponde al nome del facet. I tag di ricerca vengono utilizzati all’interno dei tag facet per i valori del facet. </p> <p>Consulta <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" type="concept" format="dita" scope="local"> Informazioni sui facet </a>. </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;facets&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/facets&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestions&gt;&lt;/suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo set di tag racchiude i suggerimenti Vi siete detti, in modo che la Ricerca guidata riconosca quali nodi XML contengono suggerimenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestion&gt;&lt;/suggestion&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo insieme di tag avvolgono ogni suggerimento intendeva dire. </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-if-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;value&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/value&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;count&gt;&lt;search-suggestion-result-count&nbsp;/&gt;&lt;/count&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-if-suggestions&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Tag specifici del modello di trasporto JSON**

Il passaggio di JSON rispetto a XML dal motore di ricerca è noto per essere più veloce perché è un payload più piccolo e un parser più veloce. Tuttavia, quando utilizzi JSON, assicurati che l’output sia JSON rigoroso perché il parser non lo perdona.

Se hai poca esperienza con JSON, puoi utilizzare i seguenti collegamenti ed esempi per iniziare:

* Introduzione a JSON. Vedere [https://www.json.org/](https://www.json.org/).
* Verifica il tuo JSON per assicurarti che sia valido. Vedere [https://jsonlint.com/](https://jsonlint.com/).

**Esempio di modello JSON**

```
{ 
 "general": 
 { 
  "total" : "<search-total />", 
  "lower" : "<search-lower />", 
  "upper" : "<search-upper />", 
  "rbt-trigger-list" : "<search-rbta-trigger-id-list>", 
  "fields" :  
  [ 
   { 
    "name" : "seo_search_title", 
    "value" : "<search-include file="seo/seo_search_title.tpl" />" 
   }, 
   { 
    "name" : "seo_search_keywords", 
    "value" : "<search-include file="seo/seo_search_keywords.tpl" />" 
   } 
  ] 
 }, 
 
 <search-if-suggestions> 
 "suggestions": 
  [ 
  <search-suggestions> 
  { 
   "suggestion":"<search-suggestion-text />", 
   "count": "<search-suggestion-result-count>" 
  }<search-if-not-last-suggestion>,</search-if-not-last-suggestion> 
  </search-suggestions> 
 ], 
 </search-if-suggestions> 
 
 "facets" : 
 [ 
  { 
   "name" : "leveli", 
   "values" : [ <search-field-value-list name="leveli" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="leveli" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" :"levelii", 
   "values" : [<search-field-value-list name="levelii" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="levelii" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" : "brand", 
   "values" : [<search-field-value-list name="brand" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="brand" quotes="no" sortby="values" data="results" />] 
  }, 
 ], 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    }, 
    { 
     "name" : "title", 
     "value" : "<search-display-field name="title" encoding="json"/>" 
    }, 
    { 
     "name" : "img_url_thumbnail", 
     "value" : "<search-display-field name="img_url_thumbnail" encoding="json"/>" 
    }, 
    { 
     "name" : "description", 
     "value" : "<search-display-field name="description" encoding="json"/>" 
    }, 
    { 
     "name" : "mdi", 
     "value" : "<SEARCH-RBTA-DISPLAY-MDI-FIELD>" 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**Esempio di sezione di risultati JSON con una tabella di attributi dei risultati**

```
{ 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    } 
   ], 
   "tables" : 
   [ 
    { 
     "name" : "downloads", 
     "fields" : 
     [ 
      { 
       "name" : "download_title", 
       "value" : <search-display-field name="download_title" encoding="json"/> 
      }, 
      { 
       "name" : "download_link", 
       "value" : <search-display-field name="download_link" encoding="json"/> 
      } 
     ] 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**Esempio di sezione Facet JSON per un facet con campi associati**

```
{ 
 facets" : 
 [ 
  { 
   "name" : "t1", 
   "values" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
   "counts" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="results" sortby="values" />], 
   "custom-fields" : 
   [ 
    { 
     "name" : "taxonmyId", 
     "value" : [<search-field-value-list name="tax1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />] 
    } 
   ] 
  } 
 ] 
}
```

**Esempio di sezione Facet JSON per facet con inclinazione**

```
{ 
  "facets" : 
  [  
   { 
    "name" : "fvalue0", 
                  "dynamic" : 1, 
                  "display-names" : [<search-field-value-list name="fname0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "values" : [<search-field-value-list name="fvalue0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "counts" : [<search-field-value-list name="fvalue0" quotes="no" commas="yes" data="results" sortby="values" />] 
   } 
  ] 
} 
```

## Aggiunta di un nuovo file di presentazione o di modello di trasporto {#task_73199757B6E748CAA604902FF913F012}

È possibile utilizzare **[!UICONTROL Add Template]** per aggiungere modelli di presentazione (.tmpl) o modelli di trasporto (.tpl) alla pagina [!DNL Templates].

<!-- 

t_adding_a_new_presentation_or_transport_template_file.xml

 -->

**Per aggiungere un nuovo file di presentazione o di modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella pagina [!DNL Templates], fai clic su **[!UICONTROL Add New Template]**.
1. Nella finestra di dialogo [!DNL Add Template], impostare le opzioni desiderate.

   <!-- 
   
   r_add_template_options.xml
   
   -->

   | Opzione | Descrizione |
   |--- |--- |
   | Nuovo nome file | Specifica il nome del modello da aggiungere. L’estensione file corretta viene aggiunta automaticamente al nome del file, in base al tipo di modello selezionato.  I modelli di presentazione hanno un&#39;estensione file .tmpl; I modelli di trasporto hanno un&#39;estensione file .tpl. |
   | Nuovo tipo di modello | Consente di scegliere una presentazione o un modello di trasporto da aggiungere.  Consulta [Informazioni sui modelli](../c-about-design-menu/c-about-templates.md). |

   Vedere anche [Modifica di una presentazione o di un modello di trasporto](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).
1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Nella pagina [!DNL Templates] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di una presentazione o di un modello di trasporto {#task_800E0E2265C34C028C92FEB5A1243EC3}

È possibile utilizzare l’Editor modelli per visualizzare e modificare il contenuto della presentazione e i file dei modelli di trasporto.

<!-- 

t_editing_a_template.xml

 -->

È possibile modificare e testare la presentazione e i modelli di trasporto, mentre i visitatori del sito Web continuano a utilizzare le versioni live dei modelli. Puoi testare il modello di staging utilizzando la versione intermedia dell’URL del dominio di ricerca. Ad esempio, puoi testare il modello di trasporto in staging eseguendo una query in staging ( `sp_staged=1`) con `sp_t` impostata sul nome del modello di trasporto. Quando sei soddisfatto della modalità di visualizzazione del layout, puoi utilizzare **[!UICONTROL Push Live]** dall’interno dell’editor modelli per inviare il modello in tempo reale. Una volta che il modello è attivo, i visitatori del sito iniziano a usarlo.

Utilizza il riferimento al tag del modello di presentazione per scoprire come collegare il modello di presentazione a componenti di ricerca guidata quali facet, breadcrumb e menu.

Vedere [Tag del modello di presentazione](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

Utilizza il riferimento al tag del modello di trasporto per ulteriori informazioni sui tag da utilizzare nei modelli di trasporto.

Vedere [Tag dei modelli di trasporto](../c-appendices/c-templates.md#reference_227D199F5A7248049BE1D405C0584751)

**[!UICONTROL To edit a presentation or a transport template]**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella pagina [!DNL Templates] fare clic sul nome di una presentazione o di un file modello di trasporto.
1. Nella pagina [!DNL Template Editor] , apporta le modifiche necessarie ai tag e alla codifica.

   Presta attenzione alle modifiche apportate in [!DNL Template Editor]; non è disponibile alcuna funzione Annulla . Se apporti una modifica indesiderata e desideri tornare alla versione precedente del file, puoi fare clic su **[!UICONTROL Cancel]** per tornare alla tabella dei modelli (partendo dal presupposto che non siano state salvate le modifiche fino a quel momento). Se hai già salvato le modifiche, puoi utilizzare **[!UICONTROL History]** nell’editor per ripristinarle.
1. (Facoltativo) Fate clic su **[!UICONTROL Insert Symbol]** per inserire caratteri speciali e simboli privi di tasti corrispondenti nelle tastiere in inglese US.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

1. Al termine, chiudi la pagina Editor modelli. vieni riportato alla pagina Modelli .

## Copia di una presentazione o di un file modello di trasporto {#task_B744AB3384C84DD59C33CD25E18C2C90}

È possibile utilizzare **[!UICONTROL Copy Template]** per risparmiare tempo duplicando un modello di presentazione (.tmpl) o di trasporto (.tpl) esistente e aggiungerlo alla pagina Modelli.

<!-- 

t_copying_a_presentation_or_a_transport_template.xml

 -->

È necessario modificare il nome del modello, il tipo di modello o entrambi. Se non si apportano modifiche, il modello non viene copiato.

È necessario che sia già stato aggiunto un modello per poter copiare un modello.

Vedere [Aggiunta di un nuovo file di presentazione o di modello di trasporto](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

**Per copiare una presentazione o un file modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella pagina [!DNL Templates] dell’elenco a discesa accanto al nome di un modello da copiare, fare clic su **[!UICONTROL Copy]**.
1. Nella finestra di dialogo [!DNL Copy Template], impostare una o più opzioni desiderate.
1. Clic **[!UICONTROL Copy]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ridenominazione di una presentazione o di un file modello di trasporto {#task_CC30050FC2DE4898BF44379D8378EB31}

È possibile utilizzare [!DNL Rename Template] per modificare il nome di un modello di presentazione esistente (.tmpl) o di un modello di trasporto (.tpl).

<!-- 

t_renaming_a_presentation_or_a_transport_template_file.xml

 -->

Se necessario, puoi anche modificare il tipo di modello.

Per rinominare un modello è necessario che sia già stato aggiunto un modello.

Vedere [Aggiunta di un nuovo file di presentazione o di modello di trasporto](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

**Per rinominare una presentazione o un file modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella pagina [!DNL Templates] dell’elenco a discesa accanto al nome di un modello che si desidera rinominare, fare clic su **[!UICONTROL Rename]**.
1. Nella finestra di dialogo [!DNL Rename Template], impostare una o più opzioni desiderate.
1. Clic **[!UICONTROL Rename]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una presentazione o di un file modello di trasporto {#task_67E532C2B83A449687737E3B06C5AA58}

È possibile utilizzare **[!UICONTROL Delete Template]** per rimuovere un modello di presentazione esistente (.tmpl) o un modello di trasporto (.tpl).

<!-- 

t_deleting_a_presentation_or_a_transport_template_file.xml

 -->

È possibile che tu disponga già di una versione corrispondente del modello di staging inviato live. In tal caso, assicurati di inviare in diretta il modello eliminato utilizzando **[!UICONTROL Staging]** in modo che venga eliminato anche dall’ambiente live. In alternativa, puoi utilizzare **[!UICONTROL Push Live]** nella pagina Modelli .

Consulta [Informazioni sullo staging](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7)

Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

È necessario che sia già stato aggiunto un modello per poter eliminare un modello.

Vedere [Aggiunta di un nuovo file di presentazione o di modello di trasporto](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

**Per eliminare una presentazione o un file modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella pagina [!DNL Templates] dell’elenco a discesa accanto al nome di un modello da eliminare, fare clic su **[!UICONTROL Delete]**.
1. Nella finestra di dialogo [!DNL Delete Template], fai clic su **[!UICONTROL Delete.]**
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anteprima del modello di presentazione ridotto a icona {#task_1757B6207CC74221AE4BFFE5674D320B}

È possibile utilizzare **[!UICONTROL Preview minimized]** per visualizzare l&#39;aspetto del peso ridotto della pagina di un modello di presentazione se si sceglie di ridurlo al minimo.

<!-- 

t_previewing_the_presentation_template_minimized.xml

 -->

Se si riduce a icona il modello di presentazione principale, ricordare di abilitare la riduzione a icona per i modelli inclusi (con tag di inclusione guidata), in quanto questa opzione non è ereditabile.

Vedere [Riduzione del peso della pagina di un modello di presentazione sul proprio...](../c-about-design-menu/c-about-templates.md#task_B09BB3CE89714DEAAE8D9A899CF3009E)

È necessario che sia già stato aggiunto un modello per visualizzare in anteprima il modello ridotto a icona.

Vedere [Aggiunta di un nuovo file di presentazione o di modello di trasporto](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

È possibile visualizzare in anteprima il codice XML di un file modello di trasporto.

Vedere [Anteprima dell&#39;XML di un file modello di trasporto](../c-about-design-menu/c-about-templates.md#task_58C6C52078E14AD88D2B2F0B3C439AE8)

**Per visualizzare in anteprima il modello di presentazione ridotto a icona**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella pagina [!DNL Templates], nell’elenco a discesa accanto al nome di un modello di presentazione, fare clic su **[!UICONTROL Preview minimized]**.

   Utilizza la colonna **[!UICONTROL Type]** nella tabella Modelli per ordinare i modelli in base a Presentazione e trasporto.
1. (Facoltativo) Nella pagina [!DNL Preview Minimized Template] , seleziona **[!UICONTROL Wrap lines]** per leggere i tag all’interno della finestra definita.
1. Clic **[!UICONTROL Close]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Riduzione del peso della pagina di un modello di presentazione sul sito Web {#task_B09BB3CE89714DEAAE8D9A899CF3009E}

È possibile ridurre il peso della pagina di un modello di presentazione utilizzando l&#39;opzione **[!UICONTROL Minimize]** nella tabella dei modelli.

<!-- 

t_reducing_the_page_weight_of_a_presentation_template.xml

 -->

Riducendo il peso della pagina del modello, riduci dinamicamente i codici JavaScript e CSS in linea. È inoltre possibile rimuovere gli spazi vuoti ridondanti nell’HTML. Ridurre al minimo il peso della pagina del modello di presentazione può aiutare a fornire i risultati di ricerca più rapidamente.

È inoltre possibile visualizzare in anteprima l&#39;aspetto del modello di presentazione ridotto a icona utilizzando **[!UICONTROL Preview minimized]**.

Vedere [Anteprima del modello di presentazione ridotto a icona](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**[!UICONTROL To reduce the page weight of a presentation template on your website]**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella pagina [!DNL Templates], sotto la colonna [!DNL Minimize], seleziona la casella per uno o più file di modello di presentazione da inviare come minimo sul sito web.

   Utilizza la colonna **[!UICONTROL Type]** nella tabella [!DNL Templates] per ordinare i modelli in base a Presentazione e trasporto.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Impostazione del file del modello di presentazione predefinito da utilizzare sul sito Web {#task_C1E8CE817E4D43E096167A347C54DD53}

Quando si dispone di più modelli di presentazione, è possibile indicare quale modello viene inizialmente utilizzato per visualizzare i risultati di ricerca.

<!-- 

t_setting_the_default_presentation_template_file_to_use.xml

 -->

È possibile utilizzare le regole di pre-ricerca, le regole di post-ricerca e le regole aziendali per determinare quando utilizzare uno degli altri modelli di presentazione.

Consulta [Informazioni sulle regole di pre-ricerca](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

Consulta [Informazioni sulle regole di post-ricerca](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

Consultare [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

È comune avere una regola come &quot;Per ogni ricerca, imposta il modello di presentazione di destinazione su xxxx&quot;. Con tale regola, la modifica del modello &quot;predefinito&quot; nella pagina Modelli non avrà alcun effetto.

**[!UICONTROL To set the default presentation template file to use on your website]**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella pagina [!DNL Templates], nella colonna [!DNL Default] fare clic sul pulsante di scelta del file del modello di presentazione corrispondente che si desidera utilizzare come predefinito.

   Utilizza la colonna **[!UICONTROL Type]** nella tabella [!DNL Templates] per ordinare i modelli in base a Presentazione e trasporto.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anteprima del file XML di un modello di trasporto {#task_58C6C52078E14AD88D2B2F0B3C439AE8}

È possibile utilizzare [!DNL Preview] per esaminare l’XML di un modello di trasporto aggiunto.

<!-- 

t_previewing_the_xml_of_a_transport_template_file.xml

 -->

È necessario che sia già stato aggiunto un modello di trasporto per visualizzare in anteprima l&#39;XML del modello.

Vedere [Aggiunta di un nuovo file di presentazione o di modello di trasporto](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

È possibile visualizzare in anteprima i file dei modelli di presentazione ridotti al minimo per visualizzarne il peso ridotto.

Vedere [Anteprima del modello di presentazione ridotto a icona](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**Visualizzazione in anteprima dell&#39;XML di un file modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella pagina [!DNL Templates], fai clic su **[!UICONTROL Preview]** nell’elenco a discesa accanto al nome di un modello di trasporto.

   Utilizza la colonna **[!UICONTROL Type]** nella tabella [!DNL Templates] per ordinare i modelli in base a Presentazione e trasporto.
1. Chiudi la finestra di visualizzazione e torna a [!DNL site search/merchandising].
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

