---
description: Utilizza il menu Adobe Analytics per configurare l’autenticazione delle metriche Adobe Analytics, gestire le metriche Adobe Analytics di una suite di rapporti o utilizzare SAINT per migliorare i rapporti Adobe Analytics tramite l’accettazione di dati tabulari provenienti da fonti esterne.
solution: Target
subtopic: Adobe Analytics
title: Informazioni sul menu Adobe Analytics
topic-legacy: Settings,Site search and merchandising
uuid: 5536edf1-d3a4-47af-a307-6e46f385f738
exl-id: e1f7b8f0-45d4-457a-a9d3-a8cb4b785059
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '3407'
ht-degree: 0%

---

# Informazioni sul menu Adobe Analytics{#about-the-adobe-analytics-menu}

Utilizza il menu Adobe Analytics per configurare l’autenticazione delle metriche Adobe Analytics, gestire le metriche Adobe Analytics di una suite di rapporti o utilizzare SAINT per migliorare i rapporti Adobe Analytics tramite l’accettazione di dati tabulari provenienti da fonti esterne.

## Configurazione dell&#39;autenticazione delle metriche Adobe Analytics {#task_8AA93F6273B747F9B4DE9E8DFBCBDC42}

Per incorporare le metriche Adobe Analytics nelle classificazioni di ricerca/merchandising del sito, è innanzitutto necessario ottenere un accesso Adobe Analytics Web Services. Dopo aver ottenuto le informazioni di accesso, puoi utilizzarle per configurare l’autenticazione Adobe Analytics in ricerca/merchandising del sito.

**Configurazione dell’autenticazione delle metriche Adobe Analytics**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Authentication]**.
1. Nella pagina [!DNL Setup Adobe Analytics Metrics Authentication] , specifica le informazioni richieste in ciascun campo.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Campo di testo </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome società Adobe Analytics </p> </td> 
      <td colname="col2"> <p>La stessa impostazione Nome società utilizzata per accedere al tuo account Adobe Analytics. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome utente Servizi Web </p> </td> 
      <td colname="col2"> <p>Nome utente dei servizi Web associato al tuo account Adobe Analytics. </p> <p>Puoi ottenere queste informazioni in Adobe Analytics. Nella barra dei menu di Adobe Analytics, fai clic su <span class="uicontrol"> <b>Amministratore</b> </span> &gt; <span class="uicontrol"> <b>Admin Console</b> </span> &gt; <span class="uicontrol"> <b>Società</b> </span> &gt; <span class="uicontrol"> <b>Servizi Web</b> </span>. Le informazioni si trovano nella tabella Informazioni di accesso API . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Segreto condiviso servizi Web </p> </td> 
      <td colname="col2"> <p>Segreto condiviso di Web Services associato al tuo account Adobe Analytics. </p> <p>Puoi ottenere queste informazioni in Adobe Analytics. Nella barra dei menu di Adobe Analytics, fai clic su <span class="uicontrol"> <b>Amministratore</b> </span> &gt; <span class="uicontrol"> <b>Admin Console</b> </span> &gt; <span class="uicontrol"> <b>Società</b> </span> &gt; <span class="uicontrol"> <b>Servizi Web</b> </span>. Le informazioni si trovano nella tabella Informazioni di accesso API . </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle suite di rapporti di Adobe Analytics {#concept_1A51AEC5D40E459B813E7891D64B1BAE}

Per utilizzare i dati della suite di rapporti di Adobe Analytics nella ricerca/merchandising del sito, devi prima creare copie dei dati di Adobe Analytics nel tuo account di ricerca/merchandising del sito.

Puoi creare nuove definizioni delle suite di rapporti di Adobe Analytics oppure visualizzare o modificare le suite di rapporti di Adobe Analytics esistenti e le metriche associate.

La prima volta che accedi ad Adobe Analytics da site search/merchandising, viene scaricato e memorizzato nella cache un elenco delle suite di rapporti disponibili per la tua azienda. Se sono state aggiunte di recente nuove suite di rapporti o rimosse quelle esistenti, puoi aggiornare l’elenco delle suite di rapporti per scaricare nuovamente l’elenco delle suite di rapporti.

## Aggiunta di una suite di rapporti Adobe Analytics {#task_6DE17305EA7146DA8C30FF8FDF68A3C0}

Puoi selezionare una suite di rapporti Adobe Analytics su cui basare le regole di classificazione di ricerca/merchandising del sito.

L’elenco da cui puoi selezionare deve corrispondere alle suite di rapporti disponibili dall’account Adobe Analytics. La suite di rapporti selezionata determina le metriche disponibili per l’utilizzo all’interno delle regole di classificazione di ricerca/merchandising del sito.

Consulta [Informazioni sulle regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

Dopo aver aggiunto una suite di rapporti di Adobe Analytics, puoi modificarne le metriche.

Consulta [Modifica delle metriche Adobe Analytics di una suite di rapporti](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

**Aggiungere una suite di rapporti Adobe Analytics**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Nella pagina Suite di rapporti di Adobe Analytics, fai clic su **[!UICONTROL Add Report Suite]**.
1. Nell’elenco a discesa della riga di tabella appena aggiunta, seleziona la suite di rapporti desiderata.
1. Modificare le metriche Adobe Analytics di una suite di rapporti.

## Modifica delle metriche di Adobe Analytics di una suite di rapporti {#task_360904CCBBB140238ADA036C3CC07664}

Per incorporare le metriche di Adobe Analytics nelle regole di classificazione nella ricerca/merchandising del sito, seleziona una o più metriche associate alla suite di rapporti selezionata. Quindi configura le opzioni utilizzate per recuperare i dati delle metriche tramite Adobe Analytics Web Service.

Consulta [Aggiunta di una suite di rapporti Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0).

Consulta [Configurazione delle opzioni avanzate di Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_C0FF2D69F59D44D8943A7831ED7FEC19).

**Per modificare le metriche Adobe Analytics di una suite di rapporti**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Nella pagina [!DNL Adobe Analytics Report Suites], nella colonna **[!UICONTROL Actions]**, fai clic su **[!UICONTROL Edit]** per la suite di rapporti di cui desideri configurare le metriche.
1. Nella pagina [!DNL Edit Adobe Analytics Metrics] , imposta le metriche richieste. Le metriche prive di un asterisco (*) accanto al nome della metrica sono facoltative.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Suite di rapporti </p> </td> 
      <td colname="col2"> <p>Visualizza il nome della suite di rapporti attualmente aggiunta. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome della visualizzazione della suite di rapporti </p> </td> 
      <td colname="col2"> <p>Fornisce un nome "alias" per il nome della suite di rapporti di Adobe Analytics. Questo nome alternativo è utile se la stessa suite di rapporti viene utilizzata in più definizioni. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Seleziona tipo di rapporto </p> </td> 
      <td colname="col2"> <p>Specifica il valore del tipo di rapporto da utilizzare con la suite di rapporti selezionata. Il valore identifica la chiave per ogni riga di risultati restituita. </p> <p>Il tipo di rapporto è anche noto come elemento Adobe Analytics. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome campo di riferimento incrociato </p> </td> 
      <td colname="col2"> <p>Specifica un campo di metadati i cui valori vengono utilizzati come "chiavi" di ricerca nei dati della suite di rapporti. </p> <p>Se non è selezionato alcun valore ("— Nessuno —"), i dati di questa suite di rapporti non sono disponibili per l'uso nei calcoli di classificazione ( <span class="uicontrol"> <b>Regole</b> </span> &gt; <span class="uicontrol"> <b>Regole di classificazione</b> </span> &gt; <span class="uicontrol"> <b>Modifica regole</b> &lt;a 11/&gt;).</span> </p> <p>Quando selezioni un valore, i valori di questo campo vengono utilizzati per fare riferimento a documenti di ricerca/merchandising del sito con i dati Adobe Analytics della suite di rapporti, utilizzando il valore del tipo di rapporto selezionato impostato in precedenza. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rapporto termini di ricerca </p> </td> 
      <td colname="col2"> <p>Consente di accedere per creare regole business e simulare i termini di ricerca dalla pagina <b>Stage Adobe Analytics Data Preview</b>. </p> <p>Consulta <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0" type="task" format="dita" scope="local">Anteprima dei dati di Adobe Analytics</a>. </p> <p>Su ogni riga viene visualizzato un menu a discesa contenente due opzioni: <b>Simula termini di ricerca</b> e <b>Crea nuova regola di business</b>. </p> <p>Entrambe le opzioni utilizzano i dati del tipo di rapporto come termini di ricerca. Pertanto, questa funzione ha senso solo se il tipo di rapporto rappresenta i termini di ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Metrics (Metriche) </p> </td> 
      <td colname="col2"> <p>Identifica i valori delle metriche che desideri scaricare e utilizzare nelle regole di classificazione di ricerca/merchandising del sito. </p> <p>Le metriche configurate vengono visualizzate come scelte nelle pagine centrali dei membri <span class="uicontrol"> <b>Regole</b> </span> <span class="uicontrol"> <b>Regole di classificazione</b> </span> &gt; <span class="uicontrol"> <b>Modifica regole</b> </span>  quando il tipo di dati della regola è impostato su <span class="uicontrol"> Metrica Adobe Analytics (numero) </span>. Le scelte mostrano una combinazione dei nomi delle suite di rapporti o delle visualizzazioni delle suite di rapporti, se specificato, e dei singoli nomi delle metriche. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore della metrica minima </p> </td> 
      <td colname="col2"> <p>Consente di immettere un valore diverso da zero per specificare un valore minimo per la metrica. </p> <p>Se vuoto o zero, vengono scaricati tutti i valori della metrica; in caso contrario, il download di questa metrica si interrompe quando viene passato il valore della metrica minima. </p> <p>Le metriche di Adobe Analytics vengono recuperate in ordine decrescente. </p> <p>Fai clic su <span class="uicontrol"> <b>+</b> </span> per aggiungere definizioni metriche aggiuntive; fai clic su <span class="uicontrol"> <b>-</b> </span> per rimuovere le definizioni metriche non più necessarie o desiderate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Periodo di aggregazione della metrica Adobe Analytics (giorni) </p> </td> 
      <td colname="col2"> <p> Controlla il numero di giorni di metriche Adobe Analytics da recuperare, conteggiando dalla data di ieri. Nessun tentativo di recupero dati dal giorno corrente. </p> <p>Il valore predefinito è 7. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Frequenza di aggiornamento del download di Adobe Analytics (giorni) </p> </td> 
      <td colname="col2"> <p> Imposta l’intervallo minimo tra i download dei dati di Adobe Analytics utilizzati nei calcoli di classificazione. </p> <p>I download attivati dall'indice che si verificano nell'intervallo di frequenza di aggiornamento del download vengono ignorati. Tuttavia, i download manuali ignorano questo valore. </p> <p>Se imposti questo valore come impostazione predefinita di 1, i dati di Adobe Analytics non vengono scaricati più di una volta entro un periodo di 24 ore. Tutti gli indici di ricerca che si verificano all'interno dell'intervallo di frequenza di aggiornamento del download utilizzano l'ultimo set di dati scaricato. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Vedere anche [Informazioni sulle regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).
1. Clic **[!UICONTROL Save Changes]**.

   Viene visualizzata nuovamente la pagina Staged [!DNL Adobe Analytics Report Suites] .
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una suite di rapporti Adobe Analytics {#task_0ACA172214D14654ABDB139F417B9F7D}

Puoi utilizzare Elimina per rimuovere una suite di rapporti dalla pagina [!DNL Adobe Analytics Report Suites]. L’eliminazione di una suite di rapporti rimuove solo la copia dei dati dai server di ricerca/merchandising del sito; non influisce sui dati sui sistemi Adobe Analytics.

**Eliminare una suite di rapporti di Adobe Analytics**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Nella pagina [!DNL Adobe Analytics Report Suites], nella colonna **[!UICONTROL Actions]** fare clic su **[!UICONTROL Delete]** per la suite di rapporti che si desidera rimuovere.
1. Nella pagina [!DNL Adobe Analytics Delete Report Suite], fai clic su **[!UICONTROL Delete]**.

## Anteprima dei dati di Adobe Analytics {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

Puoi utilizzare Anteprima per visualizzare le metriche di Adobe Analytics caricate più di recente.

La colonna Riga della tabella mostra il numero per ogni riga di dati di metrica, indicando l’ordine originale in cui sono state caricate le metriche di Adobe Analytics.

La colonna Prodotto mostra l’elemento Adobe Analytics associato a ogni riga di dati metrici. I valori in questa colonna vengono utilizzati per associare le pagine di ricerca/merchandising del sito ai loro valori di metrica corrispondenti, come configurato nelle definizioni di classificazione.

Consulta [Informazioni sulle regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

Consulta [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

Le colonne rimanenti mostrano i valori di metrica associati a ciascuna voce.

Se la tabella è vuota, significa che non hai ancora caricato alcun dato Adobe Analytics. È possibile chiudere la pagina [!DNL Adobe Analytics Data Preview] e quindi caricare i dati di Adobe Analytics.

Consulta [Caricamento di dati Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).
Se la tabella è stata designata come rapporto dei termini di ricerca, viene visualizzato un piccolo triangolo in ogni riga. Puoi fare clic sull’elenco a discesa e selezionare **Simula termine ricerca** o **Crea nuova regola business**. L’azione selezionata viene applicata al termine di ricerca della riga, i dati che si trovano nella seconda colonna

**Visualizzazione in anteprima dei dati di Adobe Analytics**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**. Nella pagina [!DNL Adobe Analytics Report Suites], sotto la colonna [!DNL Actions], fai clic su **[!UICONTROL Preview]** per la suite di rapporti di cui desideri visualizzare i dati scaricati.

   * Clic **[!UICONTROL Reports]** > **[!UICONTROL Adobe Analytics Terms Reports]**. Nella pagina [!DNL Adobe Analytics Terms Report], sotto la colonna [!DNL Actions], fai clic su **[!UICONTROL Preview]** per la suite di rapporti di cui desideri visualizzare i dati scaricati.

1. Nella pagina [!DNL Adobe Analytics Data Preview] , utilizza le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare i dati.

   Fai clic su un’intestazione di colonna nella tabella per ordinare i dati in ordine crescente o decrescente.
1. Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Download to Desktop]** per scaricare e salvare la tabella come file `.xlt`.

   * Chiudi la pagina al termine della visualizzazione dell’anteprima dei dati di Adobe Analytics e torna alla pagina visualizzata in precedenza.

## Visualizzazione del registro dal caricamento dati Adobe Analytics più recente {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

Puoi utilizzare Visualizza registro per esaminare il file di registro dati di Adobe Analytics del più recente processo di download. È inoltre possibile utilizzare la visualizzazione del registro per monitorare un download in esecuzione.

Consulta [Caricamento di dati Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**Per visualizzare il registro dal caricamento dati più recente di Adobe Analytics**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Nella pagina [!DNL Adobe Analytics Report Suites], fai clic su **[!UICONTROL View Log]**. Pagina di log,
1. Nella pagina [!DNL Adobe Analytics Data Log] , utilizza le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare le informazioni sul registro.
1. Al termine, chiudi la pagina per tornare alla pagina [!DNL Adobe Analytics Report Suites] .

## Caricamento dei dati di Adobe Analytics {#task_2F3C55189B0A4049AB2113F2291CC181}

Puoi scaricare i dati della suite di rapporti Adobe Analytics configurati in ricerca/merchandising del sito.

La pagina Caricamento dati mostra lo stato dell’ultima operazione di caricamento dati di Adobe Analytics con le seguenti informazioni:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo di stato </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Stato </p> </td> 
   <td colname="col2"> <p>Indica il successo o l'errore dell'ultimo tentativo di caricamento dei dati. In alternativa, visualizza lo stato di un'operazione di caricamento dati già in corso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Risultati </p> </td> 
   <td colname="col2"> <p>Visualizza il numero di righe di dati metrici scaricate durante l’ultimo tentativo di caricamento dei dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora di inizio </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l’ora di inizio dell’ultima operazione di caricamento dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora di interruzione </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l’ora di completamento dell’ultima operazione di caricamento dati. Oppure indica che l'operazione di caricamento dati corrente è ancora in corso. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per caricare i dati di Adobe Analytics**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Nella pagina [!DNL Stage Adobe Analytics Report Suites], fai clic su **[!UICONTROL Load Adobe Analytics Data]**.
1. Nella pagina **[!UICONTROL Adobe Analytics Data Load]** , effettua una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL Start Load]** per avviare l&#39;operazione di caricamento.

      Durante un&#39;operazione di caricamento dei dati, la riga **Avanzamento** fornisce informazioni sull&#39;avanzamento.

   * Fare clic su **[!UICONTROL Stop Load]** per interrompere l&#39;operazione di caricamento.

1. Fai clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL Stage Adobe Analytics Reports Suite].

## Aggiornamento dell’elenco delle suite di rapporti {#task_EA6215D438CA4185B106657D9712ED34}

La prima volta che accedi ad Adobe Analytics dall’interfaccia utente di ricerca/merchandising del sito, viene scaricato e memorizzato nella cache un elenco delle suite di rapporti Adobe Analytics disponibili per la tua azienda. Se sono state aggiunte di recente nuove suite di rapporti o se sono state eliminate quelle esistenti, puoi utilizzare Aggiorna elenco suite di rapporti per aggiornare l’elenco attualmente visualizzato in Ricerca/merchandising del sito.

Consulta [Aggiunta di una suite di rapporti Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0).

Consulta [Eliminazione di una suite di rapporti Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_0ACA172214D14654ABDB139F417B9F7D).

**Per aggiornare l’elenco Suite di rapporti**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Nella pagina [!DNL Adobe Analytics Report Suites], fai clic su **[!UICONTROL Refresh Report Suite List]**.

## Configurazione delle opzioni avanzate di Adobe Analytics {#task_C0FF2D69F59D44D8943A7831ED7FEC19}

Puoi utilizzare [!DNL Advanced Adobe Analytics Options] per controllare le impostazioni volte a ottimizzare il comportamento del processo di download delle suite di rapporti di Adobe Analytics.

Consulta [Modifica delle metriche Adobe Analytics di una suite di rapporti](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

**Per configurare le opzioni avanzate di Adobe Analytics**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Advanced Options]**.
1. Nella pagina [!DNL Advanced Adobe Analytics Options] , imposta le seguenti opzioni:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Righe massime, qualsiasi metrica </p> </td> 
      <td colname="col2"> <p>Impostazione di ottimizzazione che impedisce il download di troppi dati Adobe Analytics. </p> <p>Se imposti questa opzione su un valore diverso da zero, il recupero dati di Adobe Analytics viene interrotto quando il numero totale di righe recuperate per ogni metrica supera il valore specificato. </p> <p>Il valore predefinito è 0; nessun valore massimo applicato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Metrica Dimensione recupero ripetuto (righe) </p> </td> 
      <td colname="col2"> <p> Controlla il numero di valori delle metriche Adobe Analytics da recuperare alla volta. Le righe di dati della metrica vengono recuperate ripetutamente fino al recupero di tutti i dati o fino al raggiungimento del limite massimo di righe. </p> <p>Normalmente non è necessario modificare questa impostazione. Tuttavia, potrebbe essere utile ottimizzare la fase di download delle metriche di un reindice completo del sito. </p> <p>Il valore predefinito è 5000. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sui feed di classificazione SAINT {#concept_C55609DA24914BBC92CD90ED0259199D}

Puoi utilizzare Adobe Analytics SAINT per migliorare i rapporti di analisi tramite l’accettazione di dati tabulari provenienti da fonti esterne. Ad esempio, puoi utilizzare la funzione di ricerca/merchandising del sito per recuperare i dati dai propri indici ed esportarli in Adobe Analytics.

Per utilizzare correttamente la funzione Adobe Analytics SAINT nella ricerca/merchandising dei siti, è necessario essere consapevoli dei seguenti requisiti:

* Devi disporre di una società Adobe Analytics e di una suite di rapporti.

   Consulta [Informazioni sul menu Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#concept_5FD2D13C9D0D40988E6E51480D690411).
* L’account utente Adobe Analytics deve disporre dei privilegi necessari per modificare la suite di rapporti.

   Consulta [Configurazione dell&#39;autenticazione delle metriche Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42).
* L’utente Adobe Analytics deve appartenere al gruppo API Web in modo che possa utilizzare l’API Web di Adobe Analytics.
* L&#39;indice di ricerca deve avere dati utilizzabili da Adobe Analytics, ad esempio dati nel formato corretto.

Prima di creare un feed, controlla le domande e le informazioni seguenti per consentire il corretto completamento della procedura guidata di feed di SAINT:

* Con quale suite di rapporti lavorerai?
* Per quale set di classificazioni, ad esempio product, e-var e così via, fornirai i dati?
* Quali classificazioni esistono nei rapporti? La risposta a questa domanda è determinata dal tipo di dati prontamente disponibili nella ricerca/merchandising del sito e dal tipo di rapporti che Adobe Analytics segnala come desiderabili.
* SAINT accetta i dati derivanti dalla ricerca/merchandising del sito come tipo di testo. Il formato di tali dati influisce sulla presentazione dei rapporti di Adobe Analytics.

## Creazione di un feed Adobe Analytics SAINT {#task_914B5AB821E84627953D8EF9339A7DD0}

Puoi utilizzare Adobe Analytics SAINT per migliorare i rapporti di Adobe Analytics accettando dati tabulari da fonti esterne.

Ad esempio, puoi utilizzare la funzione di ricerca/merchandising del sito per recuperare i dati dai propri indici ed esportarli in Adobe Analytics.

**Per creare un feed Adobe Analytics SAINT**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella pagina [!DNL SAINT Classification Feeds], fai clic su **[!UICONTROL Create SAINT Feed]**.
1. Nella finestra di dialogo [!DNL Create Feed], immettere il nuovo nome feed nel campo di testo **Nome feed**, quindi fare clic su **[!UICONTROL Next]**.

   A questo punto, il feed viene salvato e aggiunto alla pagina [!DNL SAINT Classification Feed] . Se lo scegli, puoi uscire e modificare il feed in un secondo momento per completare la procedura guidata.
1. Nella pagina [!DNL Authentication] , specifica il nome dell’azienda Adobe Analytics, il nome utente e il segreto web nei rispettivi campi di testo, quindi fai clic su **[!UICONTROL Next]**.

   Assicurati che sia autorizzato a utilizzare l’API web con Adobe Analytics.
1. Nella pagina **[!UICONTROL Report Suite]** , scegli una suite di rapporti e il relativo set di dati di classificazione, quindi fai clic su **[!UICONTROL Next]**.
1. Nella pagina [!DNL Field Maps] mappare le classificazioni Adobe Analytics con i campi di metadati di ricerca/merchandising del sito, quindi fare clic su **[!UICONTROL Next]**.

   Per regolare le classificazioni di Adobe Analytics, fai clic su **[!UICONTROL Edit]** Classificazioni Adobe Analytics per accedere ad Adobe Analytics. Una volta apportate le modifiche, fai clic su **[!UICONTROL Refresh Classifications]** per aggiornare le scelte delle classificazioni.
1. Nella pagina [!DNL Search Criteria] è possibile filtrare i dati provenienti da ricerca/merchandising del sito prima di inviarli ad Adobe Analytics SAINT. Crea qui le regole di filtro utilizzando l&#39;interfaccia del generatore di regole, quindi fai clic su **[!UICONTROL Next]**.
1. Nella pagina [!DNL Configure FTP] , seleziona il server FTP. Specifica la frequenza con cui caricare i dati, quindi fai clic su **[!UICONTROL Next]**.

   Come best practice, ogni feed dispone di un proprio account FTP per evitare la perdita accidentale di dati. Puoi creare un nuovo account Adobe Analytics FTP qui.
1. Nella pagina [!DNL Verification] , fai clic su **[!UICONTROL Show Data View]** per controllare la rappresentazione della visualizzazione dati dell’output. Se esistono dei file di feed effettivi, questi sono elencati qui e sono disponibili per il download.
1. Clic **[!UICONTROL Close]**.

## Modifica di un feed Adobe Analytics SAINT {#task_5BF34D02D0D14359B1CF4B3C1B0ACC84}

È possibile modificare tutti gli aspetti di un feed SAINT esistente creato.

**Per modificare un feed di Adobe Analytics SAINT**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella pagina [!DNL Saint Classification Feeds], sotto la colonna **[!UICONTROL Name]**, nell’elenco a discesa accanto a un feed, fai clic su **[!UICONTROL Edit feed]**.
1. Nella finestra di dialogo Feed di SAINT, immettere il nuovo nome feed nel campo di testo **Nome feed**, quindi fare clic su **[!UICONTROL Next]**.

   A questo punto, il feed viene salvato e aggiunto alla pagina [!DNL SAINT Classification Feed] . Se lo scegli, puoi uscire e modificare il feed in un secondo momento per completare la procedura guidata.
1. Nella pagina [!DNL Authentication] , specifica il nome dell’azienda Adobe Analytics, il nome utente e il segreto web nei rispettivi campi di testo, quindi fai clic su **[!UICONTROL Next]**.

   Assicurati che sia autorizzato a utilizzare l’API web con Adobe Analytics.
1. Nella pagina **[!UICONTROL Report Suite]** , scegli una suite di rapporti e il relativo set di dati di classificazione, quindi fai clic su **[!UICONTROL Next]**.
1. Nella pagina [!DNL Field Maps] mappare le classificazioni Adobe Analytics con i campi di metadati di ricerca/merchandising del sito, quindi fare clic su **[!UICONTROL Next]**.

   Per regolare le classificazioni di Adobe Analytics, fai clic su **[!UICONTROL Edit]** Classificazioni Adobe Analytics per accedere ad Adobe Analytics. Una volta apportate le modifiche, fai clic su **[!UICONTROL Refresh Classifications]** per aggiornare le scelte delle classificazioni.
1. Nella pagina [!DNL Search Criteria] è possibile filtrare i dati provenienti da ricerca/merchandising del sito prima di inviarli ad Adobe Analytics SAINT. Crea qui le regole di filtro utilizzando l&#39;interfaccia del generatore di regole, quindi fai clic su **[!UICONTROL Next]**.
1. Nella pagina [!DNL Configure FTP] , seleziona il server FTP. Specifica la frequenza con cui caricare i dati, quindi fai clic su **[!UICONTROL Next]**.

   Come best practice, ogni feed dispone di un proprio account FTP per evitare la perdita accidentale di dati. Puoi creare un nuovo account Adobe Analytics FTP qui.
1. Nella pagina [!DNL Verification] , fai clic su **[!UICONTROL Show Data View]** per controllare la rappresentazione della visualizzazione dati dell’output. Se esistono dei file di feed effettivi, questi sono elencati qui e sono disponibili per il download.
1. Clic **[!UICONTROL Close]**.

## Eliminazione di un feed Adobe Analytics SAINT {#task_5319B1F4CA1A406393CFD7AE97258CEB}

È possibile eliminare un feed Adobe Analytics SAINT esistente che non è più necessario o utilizzato.

**Per eliminare un feed di Adobe Analytics SAINT**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella pagina [!DNL Saint Classification Feeds], sotto la colonna **[!UICONTROL Name]**, nell’elenco a discesa accanto a un feed da rimuovere, fai clic su **[!UICONTROL Delete feed]**.
1. Nella finestra di dialogo Elimina, fare clic su **Sì** per verificare l’eliminazione del feed.

## Visualizzazione di un file di feed di Adobe Analytics SAINT {#task_F0C8BADD25E14E5DB30BF31D1F879FDB}

È possibile aprire la pagina [!DNL Verification] di un feed di SAINT esistente per esaminare la rappresentazione della visualizzazione dati dell’output.

Se esistono dei file di feed effettivi, questi sono elencati qui e sono disponibili per il download come file di testo.

**Per visualizzare un file di feed di Adobe Analytics SAINT**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella pagina [!DNL Saint Classification Feeds], sotto la colonna **[!UICONTROL Name]**, nell’elenco a discesa accanto a un feed, fai clic su **[!UICONTROL View Feed Files]**.
1. (Facoltativo) Fai clic su **[!UICONTROL Download File]** per salvare il file di feed come file di testo.
1. Fai clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL SAINT Classification Feeds].

## Verifica di un feed Adobe Analytics SAINT {#task_9864D69BE3824FC29C10B36EE4855D25}

Puoi testare un feed Adobe Analytics SAINT esistente senza caricamento file.

Consulta [Generazione e caricamento di un feed Adobe Analytics SAINT](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_47AED946AA964334A877FDC8D4F6F00A).

Consulta [Visualizzazione di un file di feed di Adobe Analytics SAINT](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB).

**Per testare un file di feed di Adobe Analytics SAINT**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella pagina [!DNL Saint Classification Feeds], sotto la colonna **[!UICONTROL Name]**, nell’elenco a discesa accanto a un feed, fai clic su **[!UICONTROL Test Feed (No file upload)]**.
1. Al termine dell’elaborazione del feed, fai clic su **[!UICONTROL View Feed Files]** dall’elenco a discesa del nome del feed.
1. Nella pagina [!DNL Verification] , fai clic su **[!UICONTROL Download File]** per scaricare il file di feed.
1. Fai clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL SAINT Classification Feeds].

## Generazione e caricamento di un feed Adobe Analytics SAINT {#task_47AED946AA964334A877FDC8D4F6F00A}

Puoi generare e caricare file di feed per un feed Adobe Analytics esistente creato.

Consulta [Verifica di un feed Adobe Analytics SAINT](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_9864D69BE3824FC29C10B36EE4855D25).

Consulta [Visualizzazione di un file di feed di Adobe Analytics SAINT](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB).

**Per generare e caricare un file di feed Adobe Analytics SAINT**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella pagina [!DNL Saint Classification Feeds], sotto la colonna **[!UICONTROL Name]**, nell’elenco a discesa accanto a un feed, fai clic su **[!UICONTROL Generate and Upload Feed]**.
1. Al termine dell’elaborazione del feed, fai clic su **[!UICONTROL View Feed Files]** dall’elenco a discesa del nome del feed.
1. Nella pagina [!DNL Verification] , fai clic su **[!UICONTROL Download File]** per scaricare il file di feed.
1. Fai clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL SAINT Classification Feeds].
