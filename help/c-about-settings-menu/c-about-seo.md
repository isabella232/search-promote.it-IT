---
description: Potete utilizzare i tag meta SEO (Search Engine Optimization) per personalizzare alcuni elementi delle pagine e migliorare quindi il posizionamento dei motori di ricerca.
seo-description: Potete utilizzare i tag meta SEO (Search Engine Optimization) per personalizzare alcuni elementi delle pagine e migliorare quindi il posizionamento dei motori di ricerca.
seo-title: Informazioni sul SEO
solution: Target
subtopic: SEO
title: Informazioni sul SEO
topic: Settings,Site search and merchandising
uuid: 5c5d64f5-fe79-4489-85c6-399d1437f2c4
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# Informazioni sul SEO{#about-seo}

Potete utilizzare i tag meta SEO (Search Engine Optimization) per personalizzare alcuni elementi delle pagine e migliorare quindi il posizionamento dei motori di ricerca.

## Utilizzo del SEO {#concept_C58BFCE720824A2B9B5F5E613CFD4C0B}

È possibile definire ciascun elemento come un testo iniziale seguito da un elenco di parole. L&#39;elenco di parole può includere quanto segue:

* Frasi di ricerca più comuni nel sito per un periodo di tempo selezionato (ad esempio, &quot;ultimo mese&quot;), fatte salve le esclusioni personalizzate.
* Set di valori di uno o più campi dalla ricerca di provenienza della pagina.
* Parole e frasi statiche definite in un elenco

Gli elementi di pagina più comuni utilizzati per SEO sono il titolo della pagina e i tag meta &quot;keywords&quot; e &quot;description&quot;. Potete definire le impostazioni per questi tre elementi di pagina. È inoltre possibile definire le seguenti tre impostazioni per ciascuno dei tre tipi di pagine: Pagine dei risultati di ricerca, pagine di ricerca e pagine di dettagli elemento.

Quando salvate o visualizzate in anteprima le impostazioni SEO, vengono generati piccoli segmenti di modelli di ricerca (trasporto) che potete includere negli altri modelli di ricerca con il tag del `<search-include>` modello. Ad esempio, è possibile includere il campo Titolo pagine Risultati ricerca in un altro modello con i seguenti elementi:

```
<search-include file="seo/seo_search_title.tpl" />
```

I nove valori possibili per l’ `file` attributo del `<search-include>` tag per i campi SEO sono i seguenti:

* `seo/seo_search_title.tpl`
* `seo/seo_search_description.tpl`
* `seo/seo_search_keywords.tpl`
* `seo/seo_browse_title.tpl`
* `seo/seo_browse_description.tpl`
* `seo/seo_browse_keywords.tpl`
* `seo/seo_item_title.tpl`
* `seo/seo_item_description.tpl`
* `seo/seo_item_keywords.tpl`

Per utilizzare i campi SEO in un modello di presentazione, è necessario completare diversi passaggi.

Innanzitutto, utilizzate `<search-include>` come descritto sopra per includere i campi desiderati in un modello di ricerca XML, all&#39;interno di un `<general>` elemento.

Quindi, racchiudete ciascun `<search-include>` tag con `<general-field>` tag e `</general-field>` , assegnando i nomi dei campi nell&#39; `name` attributo come nell&#39;esempio seguente:

```
<general> 
    <general-field name="seo_search_title"><search-include file="seo/seo_search_title.tpl" /></general-field> 
    <general-field name="seo_search_description"><search-include file="seo/seo_search_description.tpl" /></general-field> 
    <general-field name="seo_search_keywords"><search-include file="seo/seo_search_keywords.tpl" /></general-field> 
</general>
```

Quindi, nel modello di presentazione, potete utilizzare `<guided-general-field>` i tag per inserire i campi denominati ovunque vi troviate, come nell&#39;esempio seguente:

```
<title><guided-general-field gsname="default" field="seo_search_title"></title> 
<meta name="description" content="<guided-general-field gsname="default" field="seo_search_description">"/> 
<meta name="keywords" content="<guided-general-field gsname="default" field="seo_search_keywords">"/>
```

Osservate l&#39;uso dell&#39; `gsname` attributo per specificare, in questo caso, la ricerca &quot;predefinita&quot;.

Nel complesso, potete definire nove diversi campi SEO da utilizzare nelle pagine Web. Sono inclusi i seguenti elementi:

* Pagine dei risultati di ricerca - titolo, descrizione e parole chiave
* Pagine di ricerca - titolo, descrizione e parole chiave
* Pagine Dettagli elemento - titolo, descrizione e parole chiave

Tutti e nove i campi sono definiti con impostazioni simili. Infatti, i nomi dei nove campi, come il campo &quot;titolo&quot; in &quot;Pagine dei risultati della ricerca&quot;, sono solo suggerimenti su come utilizzarli. Potete utilizzare qualsiasi campo in qualsiasi contesto nei modelli di presentazione e nei modelli di ricerca.

Vedere anche [Informazioni sui modelli](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

Consultate anche Tag [per modelli di](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)presentazione.

Consultate anche [Cercare i tag](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)dei modelli.

Consultate anche [Configurazione di un elenco](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4)di parole di risultati della ricerca.

## Configurazione dell’elenco di parole dei risultati di ricerca {#task_A459A3734EC04042BA52C81184251DD4}

È possibile configurare l’elenco delle parole e frasi dei risultati della ricerca incluse nei titoli, nelle descrizioni e nelle parole chiave della pagina.

**Per configurare l&#39;elenco di parole dei risultati di ricerca**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**.
1. Nella [!DNL SEO Browse Pages Word List] pagina, nei rispettivi [!DNL Title], [!DNL Description]e [!DNL Keywords] gruppi, impostate le opzioni desiderate.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Titolo| Descrizione| Parole chiave Inizia con </p> </td> 
      <td colname="col2"> <p>Testo che si desidera visualizzare davanti all'elenco di parole. </p> <p>Ad esempio, potrebbe essere necessario che l'elenco Parole chiave inizi con la parola "Marchi". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi ricerche più frequenti durante </p> </td> 
      <td colname="col2"> <p>Periodo di tempo per il quale vengono incluse le ricerche. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero massimo ricerche </p> </td> 
      <td colname="col2"> <p>Il numero massimo di ricerche incluse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi valori campo </p> </td> 
      <td colname="col2"> <p>I valori dei campi inclusi nell'elenco di parole dei risultati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi parole e frasi </p> </td> 
      <td colname="col2"> <p>Elenca le parole che si desidera aggiungere al titolo della pagina dei risultati di ricerca, al titolo della pagina di ricerca o al titolo della pagina di dettaglio dell'elemento. </p> <p>Fare clic su <b>Modifica</b> per aggiungere delle parole all'elenco. </p> <p>È possibile aggiungere una parola o una frase per riga. Al termine, fate clic su <b>Salva modifiche</b>, quindi chiudete la pagina per tornare alla pagina SEO principale. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi queste parole e frasi (ad eccezione dei valori dei campi inclusi) </p> </td> 
      <td colname="col2"> <p>Elenca le parole che si desidera rimuovere dal titolo della pagina dei risultati di ricerca, dal titolo della pagina di ricerca o dal titolo della pagina di dettaglio dell'elemento. </p> <p>Fare clic su <b>Modifica</b> per aggiungere parole all'elenco di rimozione. </p> <p>È possibile aggiungere una parola o una frase per riga. Al termine, fate clic su <b>Salva modifiche</b>, quindi chiudete la pagina per tornare alla pagina SEO principale. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Fate clic su **Anteprima output** campione per visualizzare in anteprima i valori risultanti per i campi SEO impostati.

   Consultate [Anteprima dei tag meta SEO configurati](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL SEO Search Results Word List] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Configurazione dell&#39;elenco di parole delle pagine di ricerca {#task_D7A1D765A92A4D6C94E672B3A86ECB5A}

È possibile configurare l&#39;elenco delle parole e delle frasi delle pagine di ricerca incluse nei titoli, nelle descrizioni e nelle parole chiave della pagina.

**Per configurare l&#39;elenco di parole delle pagine di ricerca**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Browse Pages]**.
1. Nella [!DNL SEO Browse Pages Word List] pagina, nei rispettivi [!DNL Title], [!DNL Description]e [!DNL Keywords] gruppi, impostate le opzioni desiderate.

   Vedere la tabella delle opzioni in [Configurazione di un elenco](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4)di parole di risultati di ricerca.
1. (Facoltativo) Fate clic su **Anteprima output** campione per visualizzare in anteprima i valori risultanti per i campi SEO impostati.

   Consultate [Anteprima dei tag meta SEO configurati](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL SEO Browse Pages Word List] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Configurazione di un elenco di parole con dettagli elemento {#task_761538C519B34164BE189F13C39B2495}

È possibile configurare l’elenco di parole e frasi di dettaglio degli elementi incluse nei titoli, nelle descrizioni e nelle parole chiave della pagina.

**Per configurare un elenco di parole con dettagli elemento**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Item Detail Pages]**.
1. Nella [!DNL SEO Item Detail Word List] pagina, nei rispettivi [!DNL Title], [!DNL Description]e [!DNL Keywords] gruppi, impostate le opzioni desiderate.

   Vedere la tabella delle opzioni in [Configurazione di un elenco](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4)di parole di risultati di ricerca.
1. (Facoltativo) Fate clic su **Anteprima output** campione per visualizzare in anteprima i valori risultanti per i campi SEO impostati.

   Consultate [Anteprima dei tag meta SEO configurati](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL SEO Item Detail Word List] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Anteprima dei tag meta SEO configurati {#task_3F97949E193C4F92A104AD117FE49621}

È possibile visualizzare in anteprima i valori risultanti per i campi SEO impostati per visualizzare il contenuto inserito nel punto in cui vengono utilizzati.

I campi SEO possono contenere valori di campo inclusi, pertanto i risultati della ricerca possono dipendere dalla query di ricerca specificata.

**Per visualizzare in anteprima i tag meta SEO configurati**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**.
1. Nella pagina SEO, fate clic su **Anteprima output** di esempio.
1. Nella [!DNL SEO Preview] pagina, nel [!DNL Enter sample query] campo, digitare il termine di query su cui si desidera eseguire la ricerca.
1. Fate clic su **Cerca**.

   I campi Titolo, Descrizione e Parole chiave risultanti mostrano il contenuto inserito in una pagina in base alla query di ricerca appena immessa.
1. Fate clic su **Chiudi** per tornare alla pagina SEO principale.
