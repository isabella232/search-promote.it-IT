---
description: nulle
seo-description: nulle
seo-title: Search&amp;Promote 8.16.0 - Note sulla versione (18/9/2014)
solution: Target
title: Search&amp;Promote 8.16.0 - Note sulla versione (18/9/2014)
topic: Release Notes,Site search and merchandising
uuid: 0a59858b-213b-40d6-aea1-d085c4d6d2fa
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.16.0 Release Notes (9/18/2014){#search-promote-release-notes}

## Search&amp;Promote 8.16.0 Release Notes (9/18/2014) {#topic_5BECD3F66C684987828F6AE65E62DA29}

## Nuova funzionalità {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Memorizzazione nella cache dei risultati di ricerca in Guided Search 3 (GS3) - Per impostare questa funzionalità personalizzata in modo da poterlo utilizzare nel tuo account, contatta il tuo Adobe Technical Account Manager.
* Aggiornamenti verticali per i campi modificati di frequente - È ora possibile aggiornare rapidamente tutti i valori per un set di campi di metadati senza dover reindicizzare completamente il contenuto.

   Consultate l&#39;opzione Campo aggiornamento verticale nella tabella in [Aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5) tag meta e [Informazioni sull&#39;aggiornamento](../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899)verticale.

   This feature can only be used on [!DNL Adobe Search&Promote] accounts that use Index Connector. Per richiedere l&#39;impostazione di questa funzionalità personalizzata per il proprio account, contattare l&#39;Account Manager tecnico Adobe.

## Fixes and enhancements {#section_22D1AFC99F394D569898828A0D3C419D}

* Corrected the Index Connector parsing of XML feeds that contained `?>` string.
* Correzione dei feed SFTP del connettore indice in caso di imposizione del conteggio minimo dei documenti.
* L&#39;esportazione dei report in Microsoft Excel ora supporta la codifica UTF8.
* Guided Search: la compilazione dei facet risultava lenta.
* Caricatore degli attributi: nei dati aggregati erano presenti chiavi duplicate.
* Correzione dell&#39;ordine di esecuzione errato della Regola aziendale in caso di invio live di una singola regola.
* I collegamenti Annulla errati delle facet venivano generati da Guided Search.
* Aggiunta di una nuova operazione del controllo remoto (`sp_lines=N`) che consente di controllare l&#39;avanzamento e lo stato di una ricerca per indicizzazione in esecuzione.

   Vedere [Informazioni sul controllo remoto per l&#39;indicizzazione](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

* Invio necessario di informazioni di autenticazione per il recupero di informazioni eliminate durante l&#39;incremento del connettore indice.
* Il report [!DNL Change Log] (Modifica registro) ora identifica l&#39;utente che ha avviato un&#39;operazione di indicizzazione manuale.

   Consultate [Visualizzazione del registro](../c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057)delle modifiche.

* When you export a [!DNL Terms Report], you are no longer limited to 500 or less items in the report.

   Consultate [Visualizzazione del rapporto Termini o dei termini di ricerca Null...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* The Index Connector **[!UICONTROL Strip HTML]** setting was always displaying as checked.
* Inconsistent search results were experienced with the **[!UICONTROL Common Phrases]** feature.
* La visualizzazione dei nomi degli attributi risultava troncata nei riepiloghi degli elenchi delle regole.
* L&#39;invio live di una singola regola aziendale comportava l&#39;invio live di tutte le regole aziendali.

