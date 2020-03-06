---
description: Gli hit diretti consentono di reindirizzare un cliente a un URL specificato quando il cliente cerca un termine corrispondente. Questo tipo di funzionalità consente di migliorare la navigazione nella ricerca del sito Web.
seo-description: Gli hit diretti consentono di reindirizzare un cliente a un URL specificato quando il cliente cerca un termine corrispondente. Questo tipo di funzionalità consente di migliorare la navigazione nella ricerca del sito Web.
seo-title: Informazioni sugli hit diretti
solution: Target
title: Informazioni sugli hit diretti
topic: Rules,Site search and merchandising
uuid: 374d63c8-2b82-4165-b543-05b587757baa
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Informazioni sugli hit diretti{#about-direct-hits}

Gli hit diretti consentono di reindirizzare un cliente a un URL specificato quando il cliente cerca un termine corrispondente. Questo tipo di funzionalità consente di migliorare la navigazione nella ricerca del sito Web.

## Utilizzo di hit diretti {#concept_C5EE074A19FD4D5B8DD21DB575E35565}

Gli hit diretti sono costituiti da due elementi principali: l’URL del sito Web e uno o più termini di ricerca delimitati da virgole. Gli hit diretti sono specificati come segue:

```
    website_URL: term
    website_URL: term, term, term
```

Ad esempio, supponiamo di avere un sito Web aziendale con una pagina che specifica tutti i termini e le condizioni dell&#39;utente. Quando un cliente cerca i termini e le condizioni, invece di mostrare i risultati, può reindirizzare il cliente alla pagina dei termini e delle condizioni.

```
    https://www.mycompany.com/policies.asp?article=terms: terms and conditions, terms, conditions, security
    https://www.mycompany.com/press/news.asp: press releases, press
```

Se il termine della query non corrisponde ad alcun hit diretto, i risultati della ricerca vengono restituiti nel modo usuale.

## Configurazione degli hit diretti {#task_64DFB8C554874C699FCC0C2F26C3669F}

Potete specificare termini di ricerca che reindirizzano un browser Web a un URI anziché restituire i risultati della ricerca.

<!-- 

t_configuring_direct_hits.xml

 -->

Sono consentite righe vuote e righe di commento che iniziano con il carattere &quot;#&quot; (hash).

**Per configurare gli hit diretti**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]** dal menu del prodotto.
1. Nel [!DNL Direct Hits] campo, inserite l’URL del sito Web e uno o più termini di ricerca delimitati da virgole.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Test degli hit diretti {#task_1E2EA833BF90423AA0DD8C5BBFE77445}

Prima di attivare live le regole di hit diretti, potete sottoporre a test gli hit diretti immettendo un termine.

<!-- 

t_testing_direct_hits.xml

 -->

Se si verifica un termine che non è coperto da una regola di hit diretto, viene visualizzato un messaggio per informarlo. In questo caso, se la regola di hit diretto era live sul sito Web, i risultati della ricerca venivano restituiti come al solito. Se sottoponete a test un termine coperto da una regola di hit diretto, viene visualizzato un messaggio che informa che si è verificato un reindirizzamento all&#39;URL specificato.

**Per testare gli hit diretti**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]** dal menu del prodotto.
1. Nel [!DNL Test Direct Hits] campo, immettere un termine di ricerca e quindi fare clic su **[!UICONTROL Test]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

