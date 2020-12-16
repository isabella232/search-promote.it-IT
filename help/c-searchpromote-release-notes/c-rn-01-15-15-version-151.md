---
description: nulle
seo-description: nulle
seo-title: Search&amp;Promote 15.1.1 - Note sulla versione (15/01/2015)
solution: Target
title: Search&amp;Promote 15.1.1 - Note sulla versione (15/01/2015)
topic: Release Notes,Site search and merchandising
uuid: 070f9c46-426f-4ca1-80c7-8ca53d40a402
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 17%

---


# Search&amp;Promote 15.1.1 - Note sulla versione (15/01/2015){#search-promote-release-notes}

## Nuova funzionalità {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Precedentemente, la linguistica come stemming, sinonimi e così via era sempre applicata alle parole chiave nelle regole della Ricerca guidata. Ora è possibile disattivare questa espansione per utilizzare le parole chiave così come sono.

   Se si desidera applicare condizioni di attivazione a una regola business, nel [!DNL Advanced Rule Builder] successivo **[!UICONTROL If any/all of the following conditions are met]**, nel primo elenco a discesa selezionare **[!UICONTROL keyword]**, quindi selezionare il nuovo operatore **[!UICONTROL equal exact]** nel secondo elenco a discesa.

   Vedere [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Problemi risolti e miglioramenti {#section_22D1AFC99F394D569898828A0D3C419D}

* [!DNL Visual Rule Builder] e  [!DNL Advanced Rule Builder] non tronca più il valore del campo MDI (Merchandising Document ID).
* I problemi di indicizzazione relativi a RBTA sono stati risolti.
* La modifica di una regola aziendale esistente con stato &quot;approvato&quot; ora revoca lo stato &quot;approvato&quot;. È necessario utilizzare [!DNL Advanced Rule Builder] per ricontrollare l&#39;opzione **[!UICONTROL Approved]**, quindi salvare la regola come di consueto. Se non si approva di nuovo una regola modificata, lo stato della regola viene impostato automaticamente su WIP (Work In Progress) nella pagina [!DNL Business Rules].
* È ora disponibile una nuova opzione **[!UICONTROL Advanced Search]** nella pagina [!DNL Business Rules] per migliorare il filtraggio delle regole.
* È stata aggiunta la condizione **[!UICONTROL contains word]** ai trigger delle regole in [!DNL Query Cleaning], [!DNL Pre-Search Rules], [!DNL Post Search Rules] e [!DNL Business Rules] per specificare facilmente le interruzioni di parola.
* Miglioramenti apportati alle note delle regole di business, ad esempio quando visualizzate una regola, ora potete recuperare la cronologia delle note per quella regola. Inoltre, le note ora sono registrate in **[!UICONTROL Reports]** > **[!UICONTROL Change Log]**.
* Le query con valori `sp_i` diversi da zero non vengono più eseguite tramite il redirector [!DNL Adobe Analytics].

   Vedere la riga 15 nella tabella in [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

