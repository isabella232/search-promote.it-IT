---
description: È possibile utilizzare i meta tag SEO (Search Engine Optimization) per personalizzare alcuni elementi delle pagine e migliorare in tal modo il posizionamento del motore di ricerca.
solution: Target
subtopic: SEO
title: Informazioni sul SEO
topic: Impostazioni, Ricerca nel sito e merchandising
uuid: 5c5d64f5-fe79-4489-85c6-399d1437f2c4
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 1%

---


# Informazioni su SEO{#about-seo}

È possibile utilizzare i meta tag SEO (Search Engine Optimization) per personalizzare alcuni elementi delle pagine e migliorare in tal modo il posizionamento del motore di ricerca.

## Utilizzo di SEO {#concept_C58BFCE720824A2B9B5F5E613CFD4C0B}

È possibile definire ogni elemento come un testo iniziale seguito da un elenco di parole. L’elenco delle parole può includere quanto segue:

* Espressioni di ricerca popolari sul sito per un periodo di tempo selezionato (ad esempio, &quot;ultimo mese&quot;), fatte salve le esclusioni personalizzate.
* Set di valori di uno o più campi dalla ricerca di origine della pagina.
* Parole e frasi statiche definite in un elenco

Gli elementi di pagina più comuni utilizzati per SEO sono il titolo della pagina e i tag meta &quot;keywords&quot; e &quot;description&quot;. È possibile definire le impostazioni per questi tre elementi di pagina. È inoltre possibile definire queste tre impostazioni per ciascuno dei tre tipi di pagine: Cerca nelle pagine dei risultati, nelle pagine di navigazione e nelle pagine dei dettagli degli elementi.

Quando salvi o visualizzi in anteprima le impostazioni SEO (Search Engine Optimization), vengono generati piccoli segmenti di modelli di ricerca (Transport) che puoi includere negli altri modelli di ricerca con il tag modello `<search-include>` . Ad esempio, puoi includere il campo Titolo pagine risultati di ricerca in un altro modello con quanto segue:

```
<search-include file="seo/seo_search_title.tpl" />
```

I nove valori possibili per l’attributo `file` del tag `<search-include>` per i campi SEO sono i seguenti:

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

Innanzitutto, utilizza `<search-include>` come descritto sopra per includere i campi desiderati in un modello di ricerca XML, all’interno di un elemento `<general>`.

Quindi, racchiudi ogni tag `<search-include>` con tag `<general-field>` e `</general-field>`, assegnando i nomi dei campi nell&#39;attributo `name` come nell&#39;esempio seguente:

```
<general> 
    <general-field name="seo_search_title"><search-include file="seo/seo_search_title.tpl" /></general-field> 
    <general-field name="seo_search_description"><search-include file="seo/seo_search_description.tpl" /></general-field> 
    <general-field name="seo_search_keywords"><search-include file="seo/seo_search_keywords.tpl" /></general-field> 
</general>
```

Quindi, nel modello di presentazione, è possibile utilizzare i tag `<guided-general-field>` per inserire i campi denominati ovunque sia necessario, come nell&#39;esempio seguente:

```
<title><guided-general-field gsname="default" field="seo_search_title"></title> 
<meta name="description" content="<guided-general-field gsname="default" field="seo_search_description">"/> 
<meta name="keywords" content="<guided-general-field gsname="default" field="seo_search_keywords">"/>
```

Osserva l’utilizzo dell’attributo `gsname` per specificare, in questo caso, la ricerca &quot;predefinita&quot;.

Nel complesso, puoi definire nove diversi campi SEO (Search Engine Optimization) utilizzabili nelle pagine web. Includono quanto segue:

* Pagine dei risultati di ricerca: titolo, descrizione e parole chiave
* Sfoglia pagine: titolo, descrizione e parole chiave
* Pagine dettagli elemento: titolo, descrizione e parole chiave

Tutti e nove i campi sono definiti con impostazioni simili. Infatti, i nomi dei nove campi, come il campo &quot;titolo&quot; in &quot;Pagine dei risultati della ricerca&quot;, sono solo suggerimenti su come utilizzarli. È possibile utilizzare uno qualsiasi dei campi in qualsiasi contesto nei modelli di presentazione e di ricerca.

Vedere anche [Informazioni sui modelli](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

Vedere anche [Tag del modello di presentazione](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

Vedere anche [Ricerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Vedere anche [Configurazione di un elenco di parole dei risultati di ricerca](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4).

## Configurazione di un elenco di parole dei risultati di ricerca {#task_A459A3734EC04042BA52C81184251DD4}

È possibile configurare l’elenco delle parole e frasi dei risultati di ricerca incluse nei titoli, nelle descrizioni e nelle parole chiave della pagina.

**Per configurare un elenco di parole dei risultati di ricerca**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**.
1. Nella pagina [!DNL SEO Browse Pages Word List], impostare le opzioni desiderate nei gruppi [!DNL Title], [!DNL Description] e [!DNL Keywords] rispettivi.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Titolo | Descrizione | Parole chiave inizia con </p> </td> 
      <td colname="col2"> <p>Testo da visualizzare davanti all’elenco di parole. </p> <p>Ad esempio, potresti desiderare che l’elenco Parole chiave inizi con la parola "Marchi". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi ricerche popolari durante </p> </td> 
      <td colname="col2"> <p>Periodo di tempo per il quale vengono incluse le ricerche. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero massimo di ricerche </p> </td> 
      <td colname="col2"> <p>Numero massimo di ricerche incluse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi valori campo </p> </td> 
      <td colname="col2"> <p>I valori dei campi inclusi nell'elenco di parole dei risultati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi queste parole e frasi </p> </td> 
      <td colname="col2"> <p>Elencare le parole che si desidera aggiungere al titolo della pagina dei risultati di ricerca, al titolo della pagina di ricerca o al titolo della pagina di dettaglio dell'elemento. </p> <p>Fare clic su <b>Modifica</b> per aggiungere parole all'elenco. </p> <p>È possibile aggiungere una parola o una frase per riga. Al termine, fai clic su <b>Salva modifiche</b>, quindi chiudi la pagina per tornare alla pagina SEO principale. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi queste parole e frasi (ad eccezione dei valori dei campi inclusi) </p> </td> 
      <td colname="col2"> <p>Elencare le parole che si desidera rimuovere dal titolo della pagina dei risultati di ricerca, dal titolo della pagina di ricerca o dal titolo della pagina di dettaglio dell'elemento. </p> <p>Fare clic su <b>Modifica</b> per aggiungere parole all'elenco di rimozione. </p> <p>È possibile aggiungere una parola o una frase per riga. Al termine, fai clic su <b>Salva modifiche</b>, quindi chiudi la pagina per tornare alla pagina SEO principale. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Fai clic su **Anteprima output campione** per visualizzare in anteprima i valori risultanti per i campi SEO impostati.

   Consulta [Anteprima dei meta tag SEO configurati](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL SEO Search Results Word List] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configurazione dell&#39;elenco di parole delle pagine di ricerca {#task_D7A1D765A92A4D6C94E672B3A86ECB5A}

È possibile configurare l’elenco delle parole e frasi delle pagine di ricerca incluse nei titoli, nelle descrizioni e nelle parole chiave della pagina.

**Per configurare un elenco di parole per le pagine di ricerca**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Browse Pages]**.
1. Nella pagina [!DNL SEO Browse Pages Word List], impostare le opzioni desiderate nei gruppi [!DNL Title], [!DNL Description] e [!DNL Keywords] rispettivi.

   Vedi la tabella delle opzioni in [Configurazione di un elenco di parole dei risultati di ricerca](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4).
1. (Facoltativo) Fai clic su **Anteprima output campione** per visualizzare in anteprima i valori risultanti per i campi SEO impostati.

   Consulta [Anteprima dei meta tag SEO configurati](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL SEO Browse Pages Word List] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configurazione di un elenco di parole con dettagli elemento {#task_761538C519B34164BE189F13C39B2495}

È possibile configurare l’elenco delle parole e frasi di dettaglio degli elementi incluse nei titoli, nelle descrizioni e nelle parole chiave della pagina.

**Per configurare un elenco di parole con dettagli elemento**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Item Detail Pages]**.
1. Nella pagina [!DNL SEO Item Detail Word List], impostare le opzioni desiderate nei gruppi [!DNL Title], [!DNL Description] e [!DNL Keywords] rispettivi.

   Vedi la tabella delle opzioni in [Configurazione di un elenco di parole dei risultati di ricerca](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4).
1. (Facoltativo) Fai clic su **Anteprima output campione** per visualizzare in anteprima i valori risultanti per i campi SEO impostati.

   Consulta [Anteprima dei meta tag SEO configurati](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL SEO Item Detail Word List] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anteprima dei metatag SEO configurati {#task_3F97949E193C4F92A104AD117FE49621}

Puoi visualizzare in anteprima i valori risultanti per i campi SEO impostati per vedere cosa viene inserito nel punto in cui li utilizzi.

I campi SEO possono contenere valori di campo inclusi, pertanto i risultati della ricerca possono dipendere dalla query di ricerca specificata.

**Per visualizzare in anteprima i metadati SEO configurati**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**.
1. Nella pagina SEO, fai clic su **Anteprima output campione**.
1. Nella pagina [!DNL SEO Preview] del campo [!DNL Enter sample query] digitare il termine di query su cui si desidera eseguire la ricerca.
1. Fare clic su **Cerca**.

   I campi Titolo, Descrizione e Parole chiave risultanti mostrano il contenuto inserito in una pagina in base alla query di ricerca appena immessa.
1. Fai clic su **Chiudi** per tornare alla pagina SEO principale.
