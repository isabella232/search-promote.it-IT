---
description: È possibile utilizzare l'indice di rigenerazione per aggiornare l'indice del sito web senza la necessità di eseguire nuovamente la ricerca per indicizzazione del sito.
solution: Target
subtopic: Regenerate Index
title: Indice di rigenerazione
topic-legacy: Index,Site search and merchandising
uuid: 9d1f1d88-0453-4422-a625-a348febbf224
exl-id: 4155a52c-33f6-4f54-b69b-2a092530f7aa
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 1%

---

# Informazioni su Rigenera indice{#about-regenerate-index}

È possibile utilizzare [!DNL Regenerate Index] per aggiornare l&#39;indice del sito web senza la necessità di eseguire nuovamente la ricerca per indicizzazione del sito.

## Utilizzo dell&#39;indice di rigenerazione {#concept_6CBE6B8D18EF47D293091CBA542245FA}

Puoi utilizzare questa opzione ogni volta che apporti una modifica alle seguenti opzioni di account:

* Parole e lingue
* Parole escluse
* Sinonimi
* Impostazioni metadati, ad esempio quando si elimina un campo metadati, si modificano il nome di un campo, il tipo di dati, i formati di data, l’ordinamento, il valore di classificazione minimo o massimo, il valore di classificazione predefinito, il tipo di elenco o il separatore di elenco.

Le informazioni aggiornate sull&#39;opzione dell&#39;account vengono utilizzate per generare un nuovo indice del sito. La funzione Rigenera consente di apportare modifiche rapide ed efficienti all’indice del sito.

Per impostazione predefinita, qualsiasi contenuto nuovo o modificato del sito web non è incluso nell’indice. Per includere tale contenuto, eseguire un indice completo o incrementale.

Vedere anche [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Vedere anche [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Rigenerazione dell&#39;indice di un sito web live o in staging {#task_B28DE40C0E9A475ABCBCBC4FF993AACD}

È possibile utilizzare [!DNL Regenerate Index] per aggiornare l&#39;indice del sito web senza la necessità di eseguire una nuova ricerca del sito.

**Per rigenerare l’indice di un sito web live o di staging**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Regenerate Index]** > **[!UICONTROL Live Regenerate]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Regenerate Index]** > **[!UICONTROL Staged Regenerate]**.

1. Nella pagina [!DNL Regenerate], fai clic su **[!UICONTROL Regenerate Index Now]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Se si sceglie di eseguire **[!UICONTROL Live Regenerate]**, fare clic su **[!UICONTROL View Last Crawl]** per esaminare le statistiche sulle prestazioni per l&#39;ultima rigenerazione dell&#39;indice live eseguita.

   * Durante la rigenerazione dell&#39;indice, fare clic su **[!UICONTROL Stop Regenerate Now]** per arrestare il processo di rigenerazione dell&#39;indice.
   * Durante la rigenerazione dell&#39;indice, fare clic su **[!UICONTROL Restart Regenerate Now]** per riavviare il processo di rigenerazione dell&#39;indice dall&#39;inizio.
   * Se si sono verificati errori di indicizzazione dopo una rigenerazione temporanea, fare clic su **[!UICONTROL View Errors]** per visualizzare il registro associato.

## Visualizzazione del registro dell&#39;indice rigenerato di un sito web live o di staging {#task_61CE8F9E7BF84BA89A8D482B2106BB15}

Al termine di una rigenerazione dell&#39;indice in tempo reale o di una rigenerazione dell&#39;indice in fase, puoi visualizzare il registro associato per risolvere eventuali errori che si sono verificati.

Non puoi esportare i registri né salvarli. Tuttavia, il registro rimane disponibile per la visualizzazione fino a quando non si verifica il nuovo indice.

**Per visualizzare il registro dell’indice rigenerato di un sito web live o in staging**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Regenerate Index]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Regenerate Index]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di log, in alto o in basso, effettua una delle seguenti operazioni:

   * Utilizza le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi all’interno del registro.

   * Utilizza le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare la visualizzazione.
