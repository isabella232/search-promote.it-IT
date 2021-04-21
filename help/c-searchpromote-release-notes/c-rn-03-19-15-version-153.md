---
description: Search&amp;Promuovi note sulla versione 15.3.1.
solution: Target
title: Search&amp;Promuovi note sulla versione 15.3.1 (24/03/2015)
topic-legacy: Release Notes,Site search and merchandising
uuid: f02da5a4-2207-4603-aa05-5cff7be16dd5
exl-id: 2d254275-f777-45e5-a838-b6a35365a6dd
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 1%

---

# Note sulla versione di Search&amp;Promote 15.3.1 (24/03/2015){#search-promote-release-notes}

## Nuove funzioni e miglioramenti {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Ricerca dei numeri dei modelli di prodotto - Aggiunta di una nuova impostazione Linguistica che consente di suddividere i token in base alle transizioni alfabetiche-numeriche. Questa funzionalità consente corrispondenze di testo libero più flessibili su token di parte o di stile del prodotto.

   Consulta **[!UICONTROL Partial Alphanumeric Matching]** in [Configurazione della corrispondenza dei termini di ricerca con il contenuto web...](../c-about-linguistics-menu/c-about-words-and-language.md#task_351A9144A51F4B41923BDBACDEF3B616).

* Possibilità di esportare i risultati della visualizzazione dati.

   Consulta [Informazioni sulle visualizzazioni dati](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3).

* Intervalli generati in modo dinamico per le funzioni di bucket di valore sfaccettatura di sfaccettature di attributi con intervalli.

   Adobe Systems attualmente richiede di fornire i valori dell’intervallo di identificazione del contenuto per farlo. Ad esempio, per un prezzo di 10, generare una stringa di intervallo &quot;Tra $ 10 e $ 20&quot;). In alternativa, Adobe Systems richiede l’utilizzo di filtri basati su script. Sono stati aggiunti nuovi attributi alla definizione di un campo di metadati solo per i campi `Type=Number`. Le nuove opzioni associano il campo numerico a un campo `Type=Text` e specificano le informazioni di configurazione che descrivono la modalità di creazione della descrizione dell’intervallo.

   Consulta [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Problemi risolti {#section_22D1AFC99F394D569898828A0D3C419D}

* La finestra di dialogo di modifica della barra dei facet deve includere i facet in fase.
* Risultati di ricerca vuoti di base per la modalità di ricerca &quot;incorporata&quot;, per una ricerca contenente caratteri giapponesi.
* La conversione tika dei file .docx di Word ora popola l&#39;attributo `title`.
* Correzione dei messaggi &quot;banner duplicati&quot; errati nel gestore **[!UICONTROL Banner]**.
* [!DNL Dynamic Media Classic] I banner non sono più compatibili con il protocollo.
* L’attributo del campo **[!UICONTROL Table Name]** era talvolta nascosto durante la modifica dei campi definiti dall’utente nell’interfaccia utente dei metadati, anche quando **[!UICONTROL Dynamic Facets]** era abilitato per l’account.
* **[!UICONTROL Recent Searches]** non codifica più caratteri non ASCII.
* I campi MDI possono essere compilati senza ricorrere a Filtro con script.
* Codifica errata nei suggerimenti.
* Il trigger &quot;other facet selected&quot; ora funziona correttamente con regole business complesse.
