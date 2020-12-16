---
description: È possibile utilizzare Rollback per eseguire il backup e archiviare gli indici del sito Web generati. È inoltre possibile ripristinare il backup di un indice in qualsiasi momento.
seo-description: È possibile utilizzare Rollback per eseguire il backup e archiviare gli indici del sito Web generati. È inoltre possibile ripristinare il backup di un indice in qualsiasi momento.
seo-title: Informazioni sul rollback per gli indici
solution: Target
subtopic: Rollback
title: Informazioni sul rollback per gli indici
topic: Index,Site search and merchandising
uuid: abed878a-71b3-4122-9822-7410f4427a9a
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 0%

---


# Rollback per indici{#about-rollback-for-indexes}

È possibile utilizzare [!DNL Rollback] per eseguire il backup e archiviare gli indici dei siti Web generati. È inoltre possibile ripristinare il backup di un indice in qualsiasi momento.

## Utilizzo del rollback per gli indici {#concept_0BC4BC975DB045A986C3607CF32705D8}

L&#39;archivio contiene quattro indici: l&#39;indice del sito corrente e tre precedenti indici del sito, che il robot di ricerca archivia automaticamente in base alle impostazioni di configurazione del rollback. Ogni volta che il sito Web viene indicizzato, l&#39;archivio viene aggiornato. Gli indici più recenti sostituiscono gli indici archiviati esistenti, in modo che l&#39;archivio resti sempre aggiornato.

Ogni indice archiviato è elencato nell&#39;archivio con le seguenti informazioni:

* Data e ora in cui l&#39;indice è stato finalizzato.
* Età indice.
* Numero di documenti indicizzati.
* Tipo di operazione di indicizzazione (completo, incrementale e così via).
* Stato dell&#39;indice, ad esempio se l&#39;indice è attualmente attivo e se verrà mantenuto o rimosso dopo l&#39;indice successivo.

Ogni volta che il sito Web viene indicizzato, il nuovo indice viene aggiunto all&#39;archivio e viene rimosso un indice esistente archiviato. Tuttavia, l&#39;indice meno recente non è necessariamente quello rimosso. Quando si aggiunge un nuovo indice all&#39;archivio, viene effettuato un confronto tra le età di ciascun indice archiviato e le pagine specificate nelle impostazioni di configurazione del rollback. L&#39;indice più lontano dalla pianificazione desiderata viene rimosso. Ad esempio, se l’impostazione di configurazione è 24,48,72 e le pagine degli indici salvati sono 5, 23, 47 e 71. L&#39;indice più recente (di cinque ore) viene rimosso quando un nuovo indice viene aggiunto all&#39;archivio perché la sua età è più lontana dalle impostazioni. Per comodità, le note di archivio che l&#39;indice viene rimosso quando il sito viene nuovamente indicizzato.

È possibile spostarsi ad altre aree dell&#39;interfaccia utente mentre è attivato un indice. Un indicatore di stato tiene traccia dell&#39;avanzamento dell&#39;attivazione ed è disponibile quando si visualizza la pagina [!DNL Rollback]. Se viene ripristinato un indice archiviato, gli utenti ricevono una notifica nella parte superiore delle pagine Indice completo, Indice incrementale, Indice con script e Rigenera. Durante il ripristino di un indice non è possibile effettuare alcuna operazione di indicizzazione. Se un&#39;operazione di rollback è in conflitto con un indice del sito pianificato, l&#39;indicizzazione programmata viene differita fino al completamento del rollback. Se un indice è già in corso, viene annullato, a condizione che l&#39;utente confermi che il rollback riceve priorità.

Per mantenere l&#39;integrità dell&#39;archivio, il robot di ricerca non aggiorna l&#39;archivio di rollback se si verificano errori durante una ricerca per indicizzazione. Non è disponibile alcun aggiornamento se un utente annulla un&#39;operazione di indicizzazione. Se un’operazione di indicizzazione supera il tempo massimo consentito, byte, pagine o documenti, il crawler finalizza l’indice e lo aggiunge all’archivio. Inoltre, se durante un&#39;operazione di indicizzazione non viene raggiunto il numero minimo di pagine, il crawler annulla l&#39;indice e l&#39;indice precedente rimane attivo.

## Configurazione della pianificazione dell&#39;archiviazione di rollback degli indici {#task_CD403B9AE2244B13A6B3861B5F9B055C}

È possibile utilizzare [!DNL Configure] per determinare quali file di indice si desidera archiviare nell&#39;archivio di rollback. L&#39;archivio può memorizzare l&#39;indice corrente e tre indici di backup.

Il campo **[!UICONTROL Schedule]** contiene tre valori separati da virgola che rappresentano ore dal presente. Ad esempio, i valori di pianificazione 24,48,72 specificano 24 ore dal presente o dal ieri, 48 ore dal presente o da due giorni fa e 72 ore dal presente o da tre giorni fa.

La ricerca archivia continuamente gli indici del sito più vicini a un giorno, due giorni e tre giorni fa. I tempi e le date effettivi degli indici archiviati possono variare a seconda della pianificazione di indicizzazione del sito Web.

**Per configurare la pianificazione dell&#39;archiviazione di rollback degli indici**

1. Scegliere **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Configure]** dal menu del prodotto.
1. Nella pagina [!DNL Rollback Configuration], nel campo **[!UICONTROL Schedule]** immettere un elenco separato da comandi di tre pagine indice, in ore. Gli indici più vicini a queste pagine vengono salvati.
1. Clic **[!UICONTROL Save Changes]**.

## Attivazione di un indice archiviato {#task_5DCE3D660F6F4197993E92AA59227332}

È possibile utilizzare Rollback per attivare un indice archiviato.

Quando si fa clic su **[!UICONTROL Activate]** per ripristinare un indice, l&#39;indice attualmente attivo viene spostato nell&#39;archivio.

Dopo l&#39;attivazione dell&#39;indice archiviato, si torna alla pagina [!DNL Activate Index]. Vengono visualizzate informazioni sul rollback dell&#39;indice. Inoltre, la colonna [!DNL Activate] nella tabella [!DNL Available Indexes] identifica l&#39;indice di rollback con lo stato &quot;Active Index&quot;.

1. Scegliere **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Rollback]** dal menu del prodotto.
1. Nella pagina [!DNL Activate Index], nella tabella [!DNL Available Indexes] fare clic su **[!UICONTROL Activate]** per il tipo di indice archiviato associato che si desidera rendere attivo.

   Utilizzare le colonne Data, Età, Pagine e Operazione per determinare l&#39;indice da attivare.
1. Nella pagina [!DNL Verify Rollback], controllare le informazioni di indice per verificare di aver selezionato l&#39;indice corretto, quindi fare clic su **[!UICONTROL Activate Now]**.

## Visualizzazione del registro di tutti i rollback dell&#39;indice {#task_D2D9AA7203F0465FB5AE0D49212AC41C}

Visualizzare la data e l&#39;ora di tutte le operazioni relative al rollback.

**Per visualizzare il registro di tutti i rollback dell&#39;indice**

1. Nel menu del prodotto, effettuate una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di registro, in alto o in basso, effettuate una delle seguenti operazioni:

   * Utilizzare le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi all&#39;interno del registro.

   * Utilizzate le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare il contenuto visualizzato.

