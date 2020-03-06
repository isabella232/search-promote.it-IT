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

---


# Search&amp;Promote 15.1.1 Release Notes (01/15/2015){#search-promote-release-notes}

## Nuova funzionalità {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Precedentemente, la linguistica come stemming, sinonimi e così via era sempre applicata alle parole chiave nelle regole della Ricerca guidata. Ora è possibile disattivare questa espansione per utilizzare le parole chiave così come sono.

   Quando si desidera applicare condizioni di attivazione a una regola business, nel [!DNL Advanced Rule Builder]seguente elenco a discesa **[!UICONTROL If any/all of the following conditions are met]** selezionare **[!UICONTROL keyword]**, quindi selezionare il nuovo operatore **[!UICONTROL equal exact]** nel secondo elenco a discesa.

   Vedere [Informazioni sulle regole](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)aziendali.

## Fixes and enhancements {#section_22D1AFC99F394D569898828A0D3C419D}

* [!DNL Visual Rule Builder] e [!DNL Advanced Rule Builder] non tronca più il valore del campo MDI (Merchandising Document ID).
* I problemi di indicizzazione relativi a RBTA sono stati risolti.
* La modifica di una regola aziendale esistente con stato &quot;approvato&quot; ora revoca lo stato &quot;approvato&quot;. You must use [!DNL Advanced Rule Builder] to recheck the option **[!UICONTROL Approved]**, and then save the rule as usual. If you do not reapprove an edited rule, the rule&#39;s status is automatically set to WIP (Work In Progress) on the [!DNL Business Rules] page.
* A new **[!UICONTROL Advanced Search]** option is now available on the [!DNL Business Rules] page for improved filtering of rules.
* È stata aggiunta **[!UICONTROL contains word]** una condizione per attivare le regole in [!DNL Query Cleaning], [!DNL Pre-Search Rules], [!DNL Post Search Rules]e [!DNL Business Rules], per specificare facilmente le interruzioni di parola.
* Miglioramenti apportati alle note delle regole di business, ad esempio quando visualizzate una regola, ora potete recuperare la cronologia delle note per quella regola. Inoltre, le note ora sono registrate **[!UICONTROL Reports]** > **[!UICONTROL Change Log]**.
* Queries with nonzero `sp_i` values are no longer run through the [!DNL Adobe Analytics] redirector.

   Vedere la riga 15 nella tabella in [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

