---
description: Search&amp;Note sulla versione di Promote 8.14.0.
solution: Target
title: Search&amp;Promote 8.14.0 Note sulla versione (22/05/2014)
topic-legacy: Release Notes,Site search and merchandising
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
exl-id: fcc00d85-128e-4015-aa82-7d31606cb076
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 1%

---

# Note sulla versione di Search&amp;Promote 8.14.0 (22/05/2014){#search-promote-release-notes}

**Problemi risolti**

* Se [!DNL sqlite_open] non riesce, il vecchio file di database sqlite viene rimosso e ne viene creato uno nuovo da zero.
* I risultati della ricerca di base non erano coerenti quando si ripeteva la stessa ricerca.
* Miglioramento delle prestazioni dell’elaborazione dei modelli quando sono presenti molti campi in uscita per risultato della ricerca.
* Sono state aggiunte note a **[!UICONTROL Business Rule History]**.
* Le prestazioni degli attivatori basati sui risultati e delle azioni della fase di rigenerazione dell&#39;indice di anteprima, durante le operazioni di indicizzazione, sono costantemente degradate nel tempo.
* Opzione **[!UICONTROL Reset SPIN cache]** modificata da booleano no/next-run a tri-state: no/always/next-run.
