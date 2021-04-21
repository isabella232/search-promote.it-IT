---
description: Gli hit diretti consentono di reindirizzare un cliente a un URL specifico quando il cliente cerca un termine corrispondente. Questo tipo di funzionalità consente di migliorare la navigazione nella ricerca del sito web.
solution: Target
title: Informazioni sugli hit diretti
topic-legacy: Rules,Site search and merchandising
uuid: 374d63c8-2b82-4165-b543-05b587757baa
exl-id: 251dfa47-f55a-469c-8fca-e187877b7759
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---

# Informazioni sugli hit diretti{#about-direct-hits}

Gli hit diretti consentono di reindirizzare un cliente a un URL specifico quando il cliente cerca un termine corrispondente. Questo tipo di funzionalità consente di migliorare la navigazione nella ricerca del sito web.

## Utilizzo di hit diretti {#concept_C5EE074A19FD4D5B8DD21DB575E35565}

Gli hit diretti sono costituiti da due elementi principali: l’URL del sito web e uno o più termini di ricerca delimitati da virgole. Gli hit diretti sono specificati come segue:

```
    website_URL: term
    website_URL: term, term, term
```

Ad esempio, supponiamo di avere un sito web aziendale con una pagina che specifichi tutti i termini e le condizioni. Quando un cliente cerca i termini e le condizioni, invece di mostrare i risultati, può reindirizzare il cliente alla pagina dei termini e delle condizioni.

```
    https://www.mycompany.com/policies.asp?article=terms: terms and conditions, terms, conditions, security
    https://www.mycompany.com/press/news.asp: press releases, press
```

Se il termine di query non corrisponde ad alcun hit diretto, i risultati di ricerca vengono restituiti nel modo consueto.

## Configurazione degli hit diretti {#task_64DFB8C554874C699FCC0C2F26C3669F}

È possibile specificare termini di ricerca che reindirizzano un browser Web a un URI anziché restituire i risultati di ricerca.

<!-- 

t_configuring_direct_hits.xml

 -->

Sono consentite righe vuote e di commento che iniziano con un carattere &#39;#&#39; (hash).

**Per configurare gli hit diretti**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]** dal menu del prodotto.
1. Nel campo [!DNL Direct Hits] , immetti l’URL del sito web e uno o più termini di ricerca delimitati da virgole.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Test dei risultati diretti {#task_1E2EA833BF90423AA0DD8C5BBFE77445}

Prima di attivare le regole di hit diretti, puoi testare gli hit diretti inserendo un termine.

<!-- 

t_testing_direct_hits.xml

 -->

Se verifichi un termine che non è coperto da una regola di hit diretti, viene visualizzato un messaggio per informarti. In questo caso, se la regola dell’hit diretto era attiva sul sito web, i risultati della ricerca venivano restituiti come di consueto. Se verifichi un termine coperto da una regola di hit diretta, viene visualizzato un messaggio per informarti che si è verificato un reindirizzamento all’URL specificato.

**Per testare gli hit diretti**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]** dal menu del prodotto.
1. Nel campo [!DNL Test Direct Hits] , inserisci un termine di ricerca, quindi fai clic su **[!UICONTROL Test]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
