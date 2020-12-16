---
description: nulle
seo-description: nulle
seo-title: Search&amp;Promote 8.14.0 - Note sulla versione (22/05/2014)
solution: Target
title: Search&amp;Promote 8.14.0 - Note sulla versione (22/05/2014)
topic: Release Notes,Site search and merchandising
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 3%

---


# Search&amp;Promote 8.14.0 - Note sulla versione (22/05/2014){#search-promote-release-notes}

**Problemi risolti**

* Se [!DNL sqlite_open] ha esito negativo, il vecchio file di database sqlite viene spostato e ne viene creato uno nuovo da zero.
* I risultati della ricerca di base non erano coerenti quando veniva ripetuta la stessa ricerca.
* Miglioramento delle prestazioni dell&#39;elaborazione dei modelli quando sono presenti molti campi in uscita per risultato della ricerca.
* Aggiunte note a **[!UICONTROL Business Rule History]**.
* Le prestazioni degli attivatori basati sui risultati e delle azioni della fase di rigenerazione dell&#39;indice di anteprima, durante le operazioni di indicizzazione, sono state costantemente ridotte nel tempo.
* L&#39;opzione **[!UICONTROL Reset SPIN cache]** è stata modificata da booleano no/esecuzione successiva a tre stati: no/always/next-run.

