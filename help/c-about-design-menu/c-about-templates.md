---
description: Potete utilizzare Modelli per gestire i modelli di presentazione e di trasporto.
seo-description: Potete utilizzare Modelli per gestire i modelli di presentazione e di trasporto.
seo-title: Informazioni sui modelli
solution: Target
title: Informazioni sui modelli
topic: Design,Site search and merchandising
uuid: f5805d3e-43bf-4e13-95df-b6bd6b762d11
translation-type: tm+mt
source-git-commit: 60cedaac1846e384a37699a42bf7fda33828e1c0

---


# Informazioni sui modelli{#about-templates}

Potete utilizzare **[!UICONTROL Templates]** per gestire i modelli di presentazione e di trasporto.

## Informazioni sui modelli {#concept_06EB481B14864E18A8AE2BCD1D6EF0B5}

<!-- 

c_about_templates.xml

 -->

Potete aggiungere, modificare, copiare, rinominare o eliminare modelli di presentazione e modelli di trasporto. Quando fate clic sul nome di un modello esistente nella tabella Modelli, questo viene aperto in una finestra editor (o visualizzatore) in cui potete apportare le modifiche.

Per ripristinare eventuali modifiche apportate ai modelli, utilizzate la funzione Cronologia dall&#39;elenco a discesa del nome del modello nella tabella Modelli.

Potete ridurre lo spessore della pagina di un modello di presentazione selezionando la **[!UICONTROL Minimize]** casella di controllo corrispondente del modello nella tabella del modello. Riducendo lo spessore della pagina del modello, potete ridurre al minimo dinamicamente i linguaggi JavaScript e CSS in linea. È inoltre possibile rimuovere gli spazi vuoti ridondanti nell’HTML. Riducendo il peso della pagina del modello di presentazione è possibile ottenere risultati di ricerca più rapidamente.

Per visualizzare l’anteprima dell’aspetto del modello ridotto a icona, fate clic sull’elenco a discesa accanto al nome del file, quindi fate clic **[!UICONTROL Preview minimized]**. Se riducete a icona il modello di presentazione principale, ricordate di abilitare la riduzione a icona per i modelli inclusi (con `guided-include` tag) perché questa opzione non è ereditabile.

Anche se riducete a icona un modello di presentazione, potete comunque modificare la versione &quot;non ridotta a icona&quot; dello stesso modello.

Potete utilizzare le regole di pre-ricerca, le regole post-ricerca e le regole aziendali per determinare quando utilizzare uno degli altri modelli di presentazione. È comune avere una regola come &quot;Per ogni ricerca, imposta il modello di destinazione su xxxx&quot;. Con tale regola, quando si modifica il modello &quot;Predefinito&quot; nella tabella Modelli, non si verifica alcun effetto.

Vedere [Informazioni sulle regole](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F)di pre-ricerca.

Consultate [Le Regole](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE)Post-Ricerca.

Vedere [Informazioni sulle regole](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)aziendali.

## I modelli di presentazione {#section_ACDDEA5C499E481C828A517C230D4596}

I modelli di presentazione sono modelli HTML che un cliente vede quando visualizza i risultati della ricerca sul sito Web.

Nel livello della presentazione, potete avere un singolo modello di presentazione che presenti i risultati di più ricerche da varie fonti. Potete definire quanti modelli di presentazione desiderate e persino definire modelli di presentazione condivisi da altri modelli utilizzando `include` i comandi. Il modello di presentazione è il punto in cui tutti i componenti Progettazione, come facet, menu e breadcrumb, si riuniscono. Per visualizzare i vari componenti di progettazione, è necessario utilizzare i tag dei modelli di presentazione.

Consultate Tag del modello [di presentazione](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

Se disponete di più modelli di presentazione, potete definire a quali condizioni vengono utilizzati i vari modelli di presentazione. Potete selezionare il modello di presentazione da utilizzare in base ai parametri e ai cookie CGI in arrivo. In alternativa, potete cambiare il modello di presentazione in uso in base al risultato di una ricerca precedente.

Quando utilizzate più modelli di presentazione, accertatevi di indicare quale modello visualizzare inizialmente i risultati di ricerca. A questo scopo, utilizzate la **[!UICONTROL Default]** colonna della tabella Modelli.

## I modelli di trasporto {#section_35FD3E8AAA4E4695A737DB7E00C3258B}

I modelli di trasporto possono essere modelli XML o JSON che trasferiscono i dati dalla ricerca back-end al livello di presentazione Guided Search.

Per impostazione predefinita, il vostro account è configurato per utilizzare modelli di trasporto XML. Tuttavia, se preferisci utilizzare JSON per passare i tuoi dati a Guided Search, contatta Adobe Consulting, che può aiutarti.

Nel livello della presentazione, potete avere un singolo modello di presentazione che presenti i risultati di più ricerche. Ogni ricerca può utilizzare lo stesso modello di trasporto o un modello di trasporto personalizzato per trasmettere i dati al livello della presentazione. Poiché il modello di trasporto viene utilizzato solo per trasmettere i dati al livello della presentazione, non deve avere codice HTML utilizzato per visualizzare i risultati della ricerca. Il modello utilizza i tag dei modelli di trasporto per trasmettere i risultati della ricerca e i risultati per la compilazione dei facet. All&#39;interno di questi tag, i tag modello di ricerca standard vengono utilizzati per visualizzare i valori effettivi.

Consultate [Cercare i tag](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)dei modelli.

**Tag per modelli di trasporto XML**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tag modello di trasporto XML </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;Guidata-xml&gt;&lt;/led-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>Si tratta dei tag XML principali utilizzati dal livello della presentazione per rilevare ciò che deve analizzare dal modello di trasporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;General&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo set di tag racchiude i tag dei modelli di ricerca che forniscono dati di riepilogo basati sul set di risultati. In genere, questi tag contengono tag di ricerca per il numero totale di risultati, il risultato più basso e il risultato più alto. È possibile definire un numero qualsiasi di campi globali aggiuntivi desiderati con il tag campo <span class="codeph"> generale </span> . </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;general&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;risultati&gt;&lt;/risultati&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo set di tag viene racchiuso intorno ai risultati della ricerca, in modo che la Ricerca guidata sappia dove cercarli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;risultato&gt;&lt;/risultato&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo set di tag viene racchiuso intorno a ciascun risultato di ricerca, in modo che la Ricerca guidata riconosca dove inizia e termina il contenuto di un singolo risultato di ricerca. </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablespace"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo tag consente di scorrere ogni elemento in un elenco con più valori per un singolo risultato. Utilizzate il tag solo all'interno di un risultato. Lo scopo principale è quello di consentire l'iterazione sugli attributi appartenenti a un campo risultato. </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
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
   <td colname="col1"> <p> <span class="codeph"> &lt;facet&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo insieme di tag passa sui risultati che popolano i facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ogni facet deve avere i propri tag facet in cui il parametro name corrisponde al nome del facet. I tag di ricerca vengono utilizzati nei tag facet per i valori dei facet. </p> <p>Consultate <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" type="concept" format="dita" scope="local"> I Facet </a>. </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;facets&gt; 
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
   <td colname="col1"> <p> <span class="codeph"> &lt;suggerimenti&gt;&lt;/suggerimenti&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo set di tag contiene suggerimenti per la Ricerca guidata che consentono di riconoscere i nodi XML contenenti suggerimenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestione&gt;&lt;/sug&gt; </span> </p> </td> 
   <td colname="col2"> <p>Questo set di tag racchiude ogni suggerimento. </p> <p> <b>Esempio</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-if-suggestions&gt; 
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

**Tag JSON per modelli di trasporto**

Il passaggio di JSON rispetto a XML dal motore di ricerca è noto per essere più veloce perché è un payload più piccolo e un parser più veloce. Tuttavia, quando utilizzi JSON per assicurarsi che l&#39;output sia JSON rigoroso perché il parser non lo perdona.

Se non hai familiarità con JSON, puoi usare i seguenti collegamenti ed esempi per iniziare:

* Introduzione a JSON. Consultate [https://www.json.org/](https://www.json.org/).
* Verifica il JSON per verificarne la validità. Consultate [https://jsonlint.com/](https://jsonlint.com/).

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

Potete utilizzare **[!UICONTROL Add Template]** per aggiungere modelli di presentazione (.tmpl) o modelli di trasporto (.tpl) alla [!DNL Templates] pagina.

<!-- 

t_adding_a_new_presentation_or_transport_template_file.xml

 -->

**Per aggiungere un nuovo file di presentazione o di modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Sulla [!DNL Templates] pagina, fate clic su **[!UICONTROL Add New Template]**.
1. Nella finestra di [!DNL Add Template] dialogo, impostare le opzioni desiderate.

   <!-- 
   
   r_add_template_options.xml
   
   -->

   | Opzione | Descrizione |
   |--- |--- |
   | Nuovo nome file | Specifica il nome del modello da aggiungere. L&#39;estensione file corretta viene aggiunta automaticamente al nome del file, in base al tipo di modello selezionato.  I modelli di presentazione hanno un&#39;estensione .tmpl; I modelli di trasporto hanno un&#39;estensione .tpl. |
   | Nuovo tipo di modello | Consente di scegliere una presentazione o un modello di trasporto da aggiungere.  Consultate [I Modelli](../c-about-design-menu/c-about-templates.md). |

   Consultate anche [Modifica di una presentazione o di un modello](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)di trasporto.
1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Nella [!DNL Templates] pagina, effettuare una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica di una presentazione o di un modello di trasporto {#task_800E0E2265C34C028C92FEB5A1243EC3}

Potete utilizzare l&#39;Editor modelli per visualizzare e modificare il contenuto della presentazione e i file modello di trasporto.

<!-- 

t_editing_a_template.xml

 -->

Potete modificare e sottoporre a test i modelli di presentazione e di trasporto per fasi, mentre i visitatori del sito Web continuano a utilizzare le versioni in diretta dei modelli. Per testare il modello in fase, usate la versione in scala dell’URL del dominio di ricerca. Ad esempio, è possibile testare il modello di trasporto su più livelli eseguendo una query su più livelli ( `sp_staged=1`) con `sp_t` il nome impostato sul modello di trasporto. Una volta ottenuto il layout soddisfacente, potete utilizzare **[!UICONTROL Push Live]** dall&#39;editor modelli per rendere attivo il modello. Dopo che il modello è live, i visitatori del sito iniziano a usarlo.

Utilizzate il riferimento del tag del modello di presentazione per apprendere come collegare il modello di presentazione ai componenti di ricerca guidata quali facet, breadcrumb e menu.

Consultate Tag del modello [di presentazione](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

Per ulteriori informazioni sui tag da utilizzare nei modelli di trasporto, utilizzate il riferimento del tag del modello di trasporto.

Consultate Tag dei modelli di [trasporto](../c-appendices/c-templates.md#reference_227D199F5A7248049BE1D405C0584751)

**[!UICONTROL To edit a presentation or a transport template]**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella [!DNL Templates] pagina, fate clic sul nome di una presentazione o di un modello di trasporto.
1. Nella [!DNL Template Editor] pagina, apportare le modifiche desiderate ai tag e alla codifica.

   Prestate attenzione alle modifiche apportate in [!DNL Template Editor]; non è disponibile la funzione Annulla. Se si apporta una modifica indesiderata e si desidera tornare alla versione precedente del file, è possibile fare clic **[!UICONTROL Cancel]** per tornare alla tabella dei modelli (supponendo che non siano state salvate le modifiche fino a quel momento). Se le modifiche sono già state salvate, potete ripristinarle utilizzando **[!UICONTROL History]** l’editor.
1. (Facoltativo) Fate clic **[!UICONTROL Insert Symbol]** per inserire caratteri speciali e simboli senza tasti corrispondenti sulle tastiere inglese USA.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

1. Al termine, chiudete la pagina Editor modelli; viene nuovamente visualizzata la pagina Modelli.

## Copia di una presentazione o di un file modello di trasporto {#task_B744AB3384C84DD59C33CD25E18C2C90}

Potete utilizzare **[!UICONTROL Copy Template]** per risparmiare tempo duplicando un modello di presentazione esistente (.tmpl) o un modello di trasporto (.tpl) e aggiungerlo alla pagina Modelli.

<!-- 

t_copying_a_presentation_or_a_transport_template.xml

 -->

È necessario modificare il nome del modello, il tipo di modello o entrambi. Se non apportate modifiche, il modello non viene copiato.

Per poter copiare un modello è necessario che sia già stato aggiunto un modello.

Consultate [Aggiunta di una nuova presentazione o di un file](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)modello di trasporto.

**Per copiare una presentazione o un file modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella [!DNL Templates] pagina, nell’elenco a discesa accanto al nome del modello da copiare, fate clic su **[!UICONTROL Copy]**.
1. Nella finestra di [!DNL Copy Template] dialogo, impostare una o più delle opzioni desiderate.
1. Clic **[!UICONTROL Copy]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Ridenominazione di una presentazione o di un file modello di trasporto {#task_CC30050FC2DE4898BF44379D8378EB31}

Potete utilizzare [!DNL Rename Template] per cambiare il nome di un modello di presentazione esistente (.tmpl) o di un modello di trasporto (.tpl).

<!-- 

t_renaming_a_presentation_or_a_transport_template_file.xml

 -->

Se necessario, potete anche modificare il tipo di modello.

Per rinominare un modello è necessario che sia già stato aggiunto un modello.

Consultate [Aggiunta di una nuova presentazione o di un file](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)modello di trasporto.

**Per rinominare una presentazione o un file modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella [!DNL Templates] pagina, nell’elenco a discesa accanto al nome di un modello da rinominare, fate clic su **[!UICONTROL Rename]**.
1. Nella finestra di [!DNL Rename Template] dialogo, impostare una o più delle opzioni desiderate.
1. Clic **[!UICONTROL Rename]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di una presentazione o di un file modello di trasporto {#task_67E532C2B83A449687737E3B06C5AA58}

Potete utilizzare **[!UICONTROL Delete Template]** per rimuovere un modello di presentazione esistente (.tmpl) o un modello di trasporto (.tpl).

<!-- 

t_deleting_a_presentation_or_a_transport_template_file.xml

 -->

È possibile che disponiate già di una versione corrispondente del modello in stato di avanzamento. In tal caso, accertatevi di inviare live il modello eliminato in **[!UICONTROL Staging]** modo che venga eliminato anche dall&#39;ambiente live. In alternativa, potete utilizzare **[!UICONTROL Push Live]** nella pagina Modelli.

Consultate [L&#39;utilizzo dello stage](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7)

Consultate [Attivazione live delle impostazioni dell’area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

Per poter eliminare un modello è necessario che sia già stato aggiunto un modello.

Consultate [Aggiunta di una nuova presentazione o di un file modello di trasporto](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

**Per eliminare una presentazione o un file modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella [!DNL Templates] pagina, nell’elenco a discesa accanto al nome di un modello da eliminare, fate clic su **[!UICONTROL Delete]**.
1. Nella finestra di [!DNL Delete Template] dialogo, fate clic su **[!UICONTROL Delete.]**
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Anteprima del modello di presentazione ridotta a icona {#task_1757B6207CC74221AE4BFFE5674D320B}

Potete utilizzare **[!UICONTROL Preview minimized]** per visualizzare l’aspetto di un modello di presentazione con lo spessore ridotto della pagina, se scegliete di ridurlo a icona.

<!-- 

t_previewing_the_presentation_template_minimized.xml

 -->

Se riducete a icona il modello di presentazione principale, ricordate di abilitare la riduzione a icona per i modelli inclusi (con tag di inclusione guidata) perché questa opzione non è ereditabile.

Consultate [Riduzione dello spessore di pagina di un modello di presentazione...](../c-about-design-menu/c-about-templates.md#task_B09BB3CE89714DEAAE8D9A899CF3009E)

Per visualizzare l’anteprima del modello ridotto a icona, è necessario che sia già stato aggiunto un modello.

Consultate [Aggiunta di una nuova presentazione o di un file modello di trasporto](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

Potete visualizzare l&#39;anteprima del codice XML di un file modello di trasporto.

Vedere [Anteprima del codice XML di un file modello di trasporto](../c-about-design-menu/c-about-templates.md#task_58C6C52078E14AD88D2B2F0B3C439AE8)

**Per visualizzare in anteprima il modello di presentazione ridotto a icona**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella [!DNL Templates] pagina, nell’elenco a discesa accanto al nome di un modello di presentazione, fate clic su **[!UICONTROL Preview minimized]**.

   Utilizzate la **[!UICONTROL Type]** colonna nella tabella Modelli per ordinare i modelli per presentazione e trasporto.
1. (Facoltativo) Nella [!DNL Preview Minimized Template] pagina, verificare **[!UICONTROL Wrap lines]** di leggere i tag all’interno della finestra definita.
1. Clic **[!UICONTROL Close]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Riduzione dello spessore della pagina di un modello di presentazione sul sito Web {#task_B09BB3CE89714DEAAE8D9A899CF3009E}

Potete ridurre lo spessore della pagina di un modello di presentazione utilizzando l&#39; **[!UICONTROL Minimize]** opzione presente nella tabella del modello.

<!-- 

t_reducing_the_page_weight_of_a_presentation_template.xml

 -->

Riducendo lo spessore della pagina del modello, potete ridurre al minimo dinamicamente i linguaggi JavaScript e CSS in linea. È inoltre possibile rimuovere gli spazi vuoti ridondanti nell’HTML. Riducendo il peso della pagina del modello di presentazione è possibile ottenere risultati di ricerca più rapidamente.

Potete anche visualizzare l’anteprima dell’aspetto del modello di presentazione ridotto a icona utilizzando **[!UICONTROL Preview minimized]**.

Consultate [Anteprima del modello di presentazione ridotto a icona](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**[!UICONTROL To reduce the page weight of a presentation template on your website]**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella [!DNL Templates] pagina, sotto la [!DNL Minimize] colonna, selezionate la casella per uno o più file modello di presentazione da inviare come minimo sul sito Web.

   Utilizzate la **[!UICONTROL Type]** colonna nella [!DNL Templates] tabella per ordinare i modelli in base a Presentazione e Trasporto.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Impostazione del file modello di presentazione predefinito da utilizzare sul sito Web {#task_C1E8CE817E4D43E096167A347C54DD53}

Se disponete di più modelli di presentazione, potete indicare quale modello viene utilizzato inizialmente per visualizzare i risultati di ricerca.

<!-- 

t_setting_the_default_presentation_template_file_to_use.xml

 -->

Potete utilizzare le regole di pre-ricerca, le regole post-ricerca e le regole aziendali per determinare quando utilizzare uno degli altri modelli di presentazione.

Vedere [Informazioni sulle regole](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F)di pre-ricerca.

Consultate [Le Regole](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE)Post-Ricerca.

Vedere [Informazioni sulle regole](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)aziendali.

È comune avere una regola come &quot;Per ogni ricerca, imposta il modello di presentazione di destinazione su xxxx&quot;. Una volta inserita tale regola, la modifica del modello &quot;predefinito&quot; nella pagina Modelli non avrà alcun effetto.

**[!UICONTROL To set the default presentation template file to use on your website]**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella [!DNL Templates] pagina, sotto la [!DNL Default] colonna, fate clic sul pulsante di scelta del file del modello di presentazione corrispondente da utilizzare come predefinito.

   Utilizzate la **[!UICONTROL Type]** colonna nella [!DNL Templates] tabella per ordinare i modelli in base a Presentazione e Trasporto.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Anteprima dell’XML di un file modello di trasporto {#task_58C6C52078E14AD88D2B2F0B3C439AE8}

È possibile utilizzare [!DNL Preview] per esaminare il codice XML di un modello di trasporto aggiunto.

<!-- 

t_previewing_the_xml_of_a_transport_template_file.xml

 -->

Per visualizzare l&#39;anteprima del codice XML del modello, è necessario che sia già stato aggiunto un modello di trasporto.

Consultate [Aggiunta di una nuova presentazione o di un file](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)modello di trasporto.

Potete visualizzare in anteprima i file dei modelli di presentazione ridotti per visualizzarne lo spessore ridotto.

Consultate [Anteprima del modello di presentazione ridotto a icona](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**Per visualizzare in anteprima il codice XML di un file modello di trasporto**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Templates]** dal menu del prodotto.
1. Nella [!DNL Templates] pagina, fai clic su **[!UICONTROL Preview]** nell’elenco a discesa accanto al nome di un modello di trasporto.

   Utilizzate la **[!UICONTROL Type]** colonna nella [!DNL Templates] tabella per ordinare i modelli in base a Presentazione e Trasporto.
1. Chiudete la finestra di visualizzazione e tornate a [!DNL site search/merchandising].
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

