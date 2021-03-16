---
description: Puoi utilizzare Rollback per eseguire il backup e archiviare gli indici del sito web generati. È inoltre possibile ripristinare il backup di un indice in qualsiasi momento.
solution: Target
subtopic: Rollback
title: Informazioni sul rollback per gli indici
topic: Indice, Ricerca nel sito e merchandising
uuid: abed878a-71b3-4122-9822-7410f4427a9a
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 0%

---


# Informazioni sul rollback per gli indici{#about-rollback-for-indexes}

Puoi utilizzare [!DNL Rollback] per eseguire il backup e archiviare gli indici del sito web generati. È inoltre possibile ripristinare il backup di un indice in qualsiasi momento.

## Utilizzo del ripristino per gli indici {#concept_0BC4BC975DB045A986C3607CF32705D8}

L&#39;archivio contiene quattro indici: l&#39;indice del sito corrente e tre indici del sito precedenti, che il robot di ricerca archivia automaticamente in base alle impostazioni di configurazione del rollback. Ogni volta che il sito web viene indicizzato, l’archivio viene aggiornato. Gli indici più recenti sostituiscono gli indici archiviati esistenti in modo che l’archivio rimanga sempre aggiornato.

Ogni indice archiviato è elencato nell&#39;archivio con le seguenti informazioni:

* Data e ora di completamento dell&#39;indice.
* Età indice.
* Numero di documenti indicizzati.
* Tipo di operazione di indicizzazione (completa, incrementale e così via).
* Stato dell&#39;indice, ad esempio se l&#39;indice è attualmente attivo e se verrà mantenuto o rimosso dopo l&#39;indice successivo.

Ogni volta che il sito web viene indicizzato, il nuovo indice viene aggiunto all&#39;archivio e viene rimosso un indice esistente archiviato. Tuttavia, l&#39;indice meno recente non è necessariamente quello rimosso. Quando si aggiunge un nuovo indice all&#39;archivio, viene effettuato un confronto di pagina di ogni indice archiviato alle pagine specificate nelle impostazioni di configurazione del rollback. L&#39;indice più lontano dalla pianificazione desiderata viene rimosso. Ad esempio, supponiamo che l’impostazione di configurazione sia 24,48,72 e che le pagine degli indici salvati siano 5, 23, 47 e 71. L&#39;indice più recente (di cinque ore) viene rimosso quando viene aggiunto un nuovo indice all&#39;archivio perché la sua età è più lontana dalle impostazioni. Per comodità, l&#39;archivio nota quale indice viene rimosso quando il sito viene nuovamente indicizzato.

È possibile spostarsi ad altre aree dell&#39;interfaccia utente quando viene attivato un indice. Un indicatore di stato tiene traccia dell’avanzamento dell’attivazione ed è disponibile quando visualizzi la pagina [!DNL Rollback] . Se viene ripristinato un indice archiviato, gli utenti vengono informati nella parte superiore delle pagine Indice completo, Indice incrementale, Indice con script e Rigenera. Impossibile eseguire alcuna operazione di indicizzazione durante il ripristino di un indice. Se un&#39;operazione di rollback è in conflitto con un indice di sito pianificato, l&#39;indicizzazione pianificata viene differita fino al completamento del rollback. Se un indice è già in corso, viene annullato, purché l&#39;utente confermi che il rollback riceve priorità.

Per mantenere l&#39;integrità dell&#39;archivio, il robot di ricerca non aggiorna l&#39;archivio di rollback se vengono rilevati errori durante una ricerca per indicizzazione. Non vi è alcun aggiornamento se un utente annulla un&#39;operazione di indicizzazione. Se un&#39;operazione di indicizzazione supera il tempo massimo, i byte, le pagine o i documenti, il crawler finalizza l&#39;indice e lo aggiunge all&#39;archivio. Inoltre, se il numero minimo di pagine non viene soddisfatto durante un&#39;operazione di indicizzazione, il crawler annulla l&#39;indice e l&#39;indice precedente rimane attivo.

## Configurazione della pianificazione dell&#39;archiviazione del rollback degli indici {#task_CD403B9AE2244B13A6B3861B5F9B055C}

È possibile utilizzare [!DNL Configure] per determinare quali file di indice memorizzare nell&#39;archivio di rollback. L&#39;archivio può memorizzare l&#39;indice corrente e tre indici di backup.

Il campo **[!UICONTROL Schedule]** contiene tre valori separati da virgola che rappresentano ore dal presente. Ad esempio, i valori di pianificazione 24,48,72 specificano 24 ore dal presente o dal ieri, 48 ore dal presente o due giorni fa, e 72 ore dal presente o tre giorni fa.

La ricerca archivia continuamente gli indici del sito più vicini a un giorno, due giorni e tre giorni di età. Le date e le ore effettive degli indici archiviati possono variare a seconda della pianificazione di indicizzazione del tuo sito web.

**Per configurare la pianificazione dell&#39;archiviazione del rollback degli indici**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Configure]**.
1. Nella pagina [!DNL Rollback Configuration], nel campo **[!UICONTROL Schedule]** immettere un elenco separato da comandi composto da tre pagine di indice, in ore. Gli indici più vicini a queste pagine vengono salvati.
1. Clic **[!UICONTROL Save Changes]**.

## Attivazione di un indice archiviato {#task_5DCE3D660F6F4197993E92AA59227332}

È possibile utilizzare Rollback per attivare un indice archiviato.

Quando si fa clic su **[!UICONTROL Activate]** per ripristinare un indice, l&#39;indice attualmente attivo viene spostato nell&#39;archivio.

Dopo l&#39;attivazione dell&#39;indice archiviato, vieni riportato alla pagina [!DNL Activate Index]. Vengono visualizzate informazioni sul rollback dell&#39;indice. Inoltre, la colonna [!DNL Activate] nella tabella [!DNL Available Indexes] identifica l&#39;indice di rollback riportato con lo stato &quot;Indice attivo&quot;.

1. Dal menu del prodotto, fai clic su **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Rollback]**.
1. Nella tabella [!DNL Available Indexes] della pagina [!DNL Activate Index] fare clic su **[!UICONTROL Activate]** per il tipo di indice archiviato associato che si desidera rendere attivo.

   Utilizza le colonne Data, Età, Pagine e Operazione per determinare quale indice attivare.
1. Nella pagina [!DNL Verify Rollback], controlla le informazioni di indice per verificare di aver selezionato l&#39;indice corretto, quindi fai clic su **[!UICONTROL Activate Now]**.

## Visualizzazione del registro di tutti i rollback dell&#39;indice {#task_D2D9AA7203F0465FB5AE0D49212AC41C}

Visualizzare la data e l&#39;ora di tutte le operazioni relative al rollback.

**Per visualizzare il registro di tutti i rollback dell&#39;indice**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di log, in alto o in basso, effettua una delle seguenti operazioni:

   * Utilizza le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi all’interno del registro.

   * Utilizza le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare la visualizzazione.

