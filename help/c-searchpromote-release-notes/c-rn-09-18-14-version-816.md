---
description: nulle
seo-description: nulle
seo-title: Search&amp;Promote 8.16.0 - Note sulla versione (18/9/2014)
solution: Target
title: Search&amp;Promote 8.16.0 - Note sulla versione (18/9/2014)
topic: Release Notes,Site search and merchandising
uuid: 0a59858b-213b-40d6-aea1-d085c4d6d2fa
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 41%

---


# Note sulla versione di Search&amp;Promote 8.16.0 (18/9/2014){#search-promote-release-notes}

## Search&amp;Promote 8.16.0 - Note sulla versione (18/9/2014) {#topic_5BECD3F66C684987828F6AE65E62DA29}

## Nuova funzionalità {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Memorizzazione nella cache dei risultati di ricerca in Guided Search 3 (GS3) - Per impostare questa funzionalità personalizzata per l&#39;utente in modo da poterlo utilizzare nel proprio account, contattare il responsabile dell&#39;account tecnico  Adobe.
* Aggiornamenti verticali per i campi modificati di frequente - È ora possibile aggiornare rapidamente tutti i valori per un set di campi di metadati senza dover reindicizzare completamente il contenuto.

   Vedere l&#39;opzione Campo aggiornamento verticale nella tabella in [Aggiunta di un nuovo campo tag meta](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5) e [Informazioni sull&#39;aggiornamento verticale](../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899).

   Questa funzione può essere utilizzata solo sugli account [!DNL Adobe Search&Promote] che utilizzano il connettore indice. Per richiedere l&#39;impostazione di questa funzionalità personalizzata per il proprio account, contattare l&#39;Account Manager tecnico Adobe.

## Problemi risolti e miglioramenti {#section_22D1AFC99F394D569898828A0D3C419D}

* Correzione dell&#39;analisi del connettore indice dei feed XML che contenevano una stringa `?>`.
* Correzione dei feed SFTP del connettore indice in caso di imposizione del conteggio minimo dei documenti.
* L&#39;esportazione dei report in Microsoft Excel ora supporta la codifica UTF8.
* Guided Search: la compilazione dei facet risultava lenta.
* Caricatore degli attributi: nei dati aggregati erano presenti chiavi duplicate.
* Correzione dell&#39;ordine di esecuzione errato della Regola aziendale in caso di invio live di una singola regola.
* I collegamenti Annulla errati delle facet venivano generati da Guided Search.
* Aggiunta di una nuova operazione del controllo remoto (`sp_lines=N`) che consente di controllare l&#39;avanzamento e lo stato di una ricerca per indicizzazione in esecuzione.

   Vedere [Informazioni sul telecomando per l&#39;indicizzazione](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

* Invio necessario di informazioni di autenticazione per il recupero di informazioni eliminate durante l&#39;incremento del connettore indice.
* Il report [!DNL Change Log] (Modifica registro) ora identifica l&#39;utente che ha avviato un&#39;operazione di indicizzazione manuale.

   Vedere [Visualizzazione del registro delle modifiche](../c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

* Quando si esporta un [!DNL Terms Report], non si possono più limitare a 500 o meno elementi nel rapporto.

   Vedere [Visualizzazione del rapporto Termini o dei termini di ricerca Null...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* L&#39;impostazione Connettore indice **[!UICONTROL Strip HTML]** veniva sempre visualizzata come selezionata.
* Con la funzione **[!UICONTROL Common Phrases]** sono stati rilevati risultati di ricerca non coerenti.
* La visualizzazione dei nomi degli attributi risultava troncata nei riepiloghi degli elenchi delle regole.
* Vivere una singola regola aziendale significava imporre live tutte le regole aziendali.

