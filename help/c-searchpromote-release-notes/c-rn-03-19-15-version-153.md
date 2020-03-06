---
description: nulle
seo-description: nulle
seo-title: Search&amp;Promote 15.3.1 - Note sulla versione (24/03/2015)
solution: Target
title: Search&amp;Promote 15.3.1 - Note sulla versione (24/03/2015)
topic: Release Notes,Site search and merchandising
uuid: f02da5a4-2207-4603-aa05-5cff7be16dd5
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 15.3.1 Release Notes (03/24/2015){#search-promote-release-notes}

## Nuove funzioni e miglioramenti {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Ricerca dei numeri dei modelli di prodotto - Aggiunta una nuova impostazione Linguistica che consente di suddividere i token in base alle transizioni alfabetiche-numeriche. Questa funzionalità consente corrispondenze a testo libero più flessibili su token parte o stile prodotto.

   Consultate **[!UICONTROL Partial Alphanumeric Matching]** in [Configurazione della corrispondenza tra i termini di ricerca e il contenuto Web...](../c-about-linguistics-menu/c-about-words-and-language.md#task_351A9144A51F4B41923BDBACDEF3B616).

* Possibilità di esportare i risultati della visualizzazione dati.

   Vedere [Informazioni sulle visualizzazioni](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3)dati.

* Intervalli generati dinamicamente per le feature di intasamento del valore del facet degli attributi oscillati.

   Adobe Systems attualmente richiede di fornire contenuti che identifichino i valori dell&#39;intervallo per farlo. Ad esempio, per un prezzo di 10, generare una stringa intervallo &quot;Tra $10 e $20&quot;). In alternativa, Adobe Systems richiede l’utilizzo di filtri basati su script. Sono stati aggiunti nuovi attributi a una definizione di campo di metadati, solo per `Type=Number` i campi. Le nuove opzioni associano il campo numerico a un `Type=Text` campo e specificano le informazioni di configurazione che descrivono la modalità di creazione della descrizione dell&#39;intervallo.

   Consultate [Aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)tag meta.

## Problemi risolti {#section_22D1AFC99F394D569898828A0D3C419D}

* La finestra di dialogo di modifica della barra laterale deve includere facet in fase.
* Risultati di ricerca di base vuoti per la modalità di ricerca &quot;incorporata&quot;, per una ricerca contenente caratteri giapponesi.
* La conversione Tika dei file .docx di Word ora popola l&#39; `title` attributo.
* Corretti messaggi errati di tipo &quot;banner duplicato&quot; nel **[!UICONTROL Banner]** manager.
* I banner Dynamic Media Classic ora non supportano il protocollo.
* Talvolta l’attributo **[!UICONTROL Table Name]** campo era nascosto quando si modificavano i campi definiti dall’utente nell’interfaccia utente Metadati, anche quando **[!UICONTROL Dynamic Facets]** era abilitato per l’account.
* **[!UICONTROL Recent Searches]** i caratteri non ASCII non vengono più codificati in più lettere.
* I campi MDI possono essere compilati senza ricorrere a Filtro basato su script.
* Codifica errata nei suggerimenti.
* Il trigger &quot;altri facet selezionati&quot; ora funziona correttamente con regole business complesse.

