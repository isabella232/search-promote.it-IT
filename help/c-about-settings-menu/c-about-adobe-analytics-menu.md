---
description: Utilizzate il menu Adobe Analytics per configurare l'autenticazione delle metriche Adobe Analytics, gestire le metriche Adobe Analytics di una suite di rapporti o utilizzare SAINT per migliorare i report Adobe Analytics attraverso l'accettazione di dati tabulari provenienti da fonti esterne.
seo-description: Utilizzate il menu Adobe Analytics per configurare l'autenticazione delle metriche Adobe Analytics, gestire le metriche Adobe Analytics di una suite di rapporti o utilizzare SAINT per migliorare i report Adobe Analytics attraverso l'accettazione di dati tabulari provenienti da fonti esterne.
seo-title: Informazioni sul menu Adobe Analytics
solution: Target
subtopic: Adobe Analytics
title: Informazioni sul menu Adobe Analytics
topic: Settings,Site search and merchandising
uuid: 5536edf1-d3a4-47af-a307-6e46f385f738
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# Informazioni sul menu Adobe Analytics{#about-the-adobe-analytics-menu}

Utilizzate il menu Adobe Analytics per configurare l&#39;autenticazione delle metriche Adobe Analytics, gestire le metriche Adobe Analytics di una suite di rapporti o utilizzare SAINT per migliorare i report Adobe Analytics attraverso l&#39;accettazione di dati tabulari provenienti da fonti esterne.

## Impostazione dell&#39;autenticazione delle metriche di Adobe Analytics {#task_8AA93F6273B747F9B4DE9E8DFBCBDC42}

Per includere le metriche di Adobe Analytics nelle classificazioni di ricerca e merchandising del sito, è innanzitutto necessario ottenere un accesso Adobe Analytics Web Services. Dopo aver ottenuto le informazioni di accesso, potete utilizzarle per configurare l&#39;autenticazione Adobe Analytics in ricerca nel sito/merchandising.

**Per impostare l&#39;autenticazione delle metriche di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Authentication]**.
1. Nella [!DNL Setup Adobe Analytics Metrics Authentication] pagina, specificate le informazioni richieste in ciascun campo.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Campo di testo </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome società di Adobe Analytics </p> </td> 
      <td colname="col2"> <p>La stessa impostazione Nome società utilizzata per accedere al tuo account Adobe Analytics. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome utente Servizi Web </p> </td> 
      <td colname="col2"> <p>Il nome utente dei servizi Web associato al tuo account Adobe Analytics. </p> <p>Queste informazioni sono disponibili in Adobe Analytics. Nella barra dei menu di Adobe Analytics, fai clic su <span class="uicontrol"> Admin <b></b> &gt; </span> Admin Console <span class="uicontrol"> &gt; <b>Company</b> </span> <span class="uicontrol"> <b></b> </span> <span class="uicontrol"> <b></b> </span>&gt; Web Services. Le informazioni si trovano nella tabella Informazioni di accesso API. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Segreto condiviso servizi Web </p> </td> 
      <td colname="col2"> <p>Segreto condiviso di Web Services associato al tuo account Adobe Analytics. </p> <p>Queste informazioni sono disponibili in Adobe Analytics. Nella barra dei menu di Adobe Analytics, fai clic su <span class="uicontrol"> Admin <b></b> &gt; </span> Admin Console <span class="uicontrol"> &gt; <b>Company</b> </span> <span class="uicontrol"> <b></b> </span> <span class="uicontrol"> <b></b> </span>&gt; Web Services. Le informazioni si trovano nella tabella Informazioni di accesso API. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sulle suite di rapporti di Adobe Analytics {#concept_1A51AEC5D40E459B813E7891D64B1BAE}

Per utilizzare i dati della suite di rapporti di Adobe Analytics nella ricerca del sito/merchandising, devi prima creare delle copie dei dati Adobe Analytics nel tuo account di ricerca del sito/merchandising.

Puoi creare nuove definizioni delle suite di rapporti di Adobe Analytics, oppure puoi visualizzare o modificare le suite di rapporti di Adobe Analytics esistenti e le metriche associate.

La prima volta che accedete ad Adobe Analytics dalla funzione di ricerca/merchandising del sito, viene scaricato e memorizzato nella cache un elenco delle suite di rapporti disponibili per la società. Se sono state aggiunte di recente nuove suite di rapporti o ne sono state rimosse altre esistenti, puoi aggiornare l’elenco delle suite di rapporti per scaricare nuovamente l’elenco delle suite di rapporti.

## Aggiunta di una suite di rapporti di Adobe Analytics {#task_6DE17305EA7146DA8C30FF8FDF68A3C0}

Puoi selezionare una suite di rapporti di Adobe Analytics su cui basare le regole di classificazione di ricerca e merchandising del sito.

L&#39;elenco da cui potete selezionare deve corrispondere alle suite di rapporti disponibili dall&#39;account Adobe Analytics. La Suite di rapporti selezionata determina le metriche disponibili per l&#39;utilizzo nelle regole di classificazione di ricerca e merchandising del sito.

Vedere [Informazioni sulle regole](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)di classificazione.

Dopo aver aggiunto una suite di rapporti di Adobe Analytics, puoi modificarne le metriche.

Consultate [Modifica delle metriche di Adobe Analytics di una suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)di rapporti.

**Per aggiungere una suite di rapporti di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Nella pagina Adobe Analytics Report Suites (Suite di rapporti di Adobe Analytics), fate clic su **[!UICONTROL Add Report Suite]**.
1. Nell&#39;elenco a discesa della riga di tabella appena aggiunta, selezionate la suite di rapporti desiderata.
1. Modifica le metriche di Adobe Analytics di una suite di rapporti.

## Modifica delle metriche di Adobe Analytics di una suite di rapporti {#task_360904CCBBB140238ADA036C3CC07664}

Per includere le metriche di Adobe Analytics nelle regole di classificazione nella ricerca nel sito/merchandising, selezionate una o più metriche associate alla suite di rapporti selezionata. Quindi configurate le opzioni utilizzate per recuperare i dati delle metriche tramite il servizio Web di Adobe Analytics.

Consultate [Aggiunta di una suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0)di rapporti di Adobe Analytics.

Consultate [Configurazione delle opzioni](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_C0FF2D69F59D44D8943A7831ED7FEC19)Adobe Analytics avanzate.

**Per modificare le metriche di Adobe Analytics di una suite di rapporti**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Nella [!DNL Adobe Analytics Report Suites] pagina, nella **[!UICONTROL Actions]** colonna, fai clic **[!UICONTROL Edit]** per la suite di rapporti di cui vuoi configurare le metriche.
1. Nella [!DNL Edit Adobe Analytics Metrics] pagina, imposta le metriche richieste. Le metriche che non hanno un asterisco (*) accanto al nome della metrica sono facoltative.

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
      <td colname="col1"> <p>Nome visualizzazione suite di rapporti </p> </td> 
      <td colname="col2"> <p>Fornisce un nome "alias" per il nome della suite di rapporti di Adobe Analytics. Questo nome alternativo è utile se la stessa Suite di rapporti viene utilizzata in più definizioni. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Seleziona tipo di rapporto </p> </td> 
      <td colname="col2"> <p>Specifica il valore del tipo di rapporto da utilizzare con la suite di rapporti selezionata. Il valore identifica la chiave per ogni riga di risultati restituita. </p> <p>Il tipo di rapporto è anche noto come elemento di Adobe Analytics. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome campo rimando </p> </td> 
      <td colname="col2"> <p>Specifica un campo di metadati i cui valori vengono utilizzati come "chiavi" di ricerca nei dati della suite di rapporti. </p> <p>Se non è selezionato alcun valore ("— Nessuno —"), i dati di questa Suite di rapporti non sono disponibili per l'utilizzo nei calcoli di classificazione ( <span class="uicontrol"> Regole <b></b> &gt; </span> Regole <span class="uicontrol"> di <b>classificazione</b> &gt; </span> <span class="uicontrol"> <b></b> </span>Modifica regole). </p> <p>Quando si seleziona un valore, i valori di questo campo vengono utilizzati per fare riferimento incrociato ai documenti di ricerca e merchandising del sito con i dati Adobe Analytics della suite di rapporti, utilizzando il valore del tipo di rapporto selezionato precedentemente impostato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rapporto termini di ricerca </p> </td> 
      <td colname="col2"> <p>Consente di creare regole business e simulare i termini di ricerca dalla pagina <b>Stage Adobe Analytics Data Preview (Anteprima</b> dati Adobe Analytics). </p> <p>Consultate <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0" type="task" format="dita" scope="local">Anteprima dei dati</a>di Adobe Analytics. </p> <p>Su ogni riga viene visualizzato un menu a discesa contenente due opzioni: <b>Simulare il termine</b> di ricerca e <b>creare una nuova regola</b>aziendale. </p> <p>Entrambe le opzioni utilizzano i dati del tipo di rapporto come termini di ricerca. Pertanto, questa funzione ha senso solo se il tipo di rapporto rappresenta i termini di ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Metrics (Metriche) </p> </td> 
      <td colname="col2"> <p>Identifica i valori delle metriche da scaricare e utilizzare nelle regole di classificazione di ricerca e merchandising del sito. </p> <p>Le metriche configurate qui vengono visualizzate come scelte nelle pagine <span class="uicontrol"> Regole <b></b> &gt; </span> Regole <span class="uicontrol"> di <b>classificazione</b> &gt; </span> <span class="uicontrol"> <b></b> </span> <span class="uicontrol"> </span>Modifica regolecentri membri, quando il tipo di dati della regola è impostato su Analytics Metric (Number). Le opzioni disponibili mostrano una combinazione dei nomi delle suite di rapporti o delle visualizzazioni delle suite di rapporti, se specificate, e dei singoli nomi delle metriche. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore della metrica minima </p> </td> 
      <td colname="col2"> <p>Consente di immettere un valore diverso da zero per specificare un valore minimo per la metrica. </p> <p>Se vuoto o zero, vengono scaricati tutti i valori della metrica; in caso contrario, il download di questa metrica si interrompe quando viene passato il valore della metrica minima. </p> <p>Le metriche di Adobe Analytics vengono recuperate in ordine decrescente. </p> <p>Fai clic su <span class="uicontrol"><b>+</b> </span> per aggiungere altre definizioni di metriche; fare clic su <span class="uicontrol"><b>-</b> </span> per rimuovere le definizioni delle metriche non più necessarie o desiderate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Periodo di aggregazione delle metriche di Adobe Analytics (giorni) </p> </td> 
      <td colname="col2"> <p> Controlla il numero di giorni di recupero delle metriche di Adobe Analytics, che vengono contati dalla data di ieri. Nessun tentativo di recupero dati dal giorno corrente. </p> <p>Il valore predefinito è 7. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Frequenza di aggiornamento download di Adobe Analytics (giorni) </p> </td> 
      <td colname="col2"> <p> Imposta l'intervallo minimo tra i download dei dati di Adobe Analytics utilizzati nei calcoli di classifica. </p> <p>I download attivati dall'indice che si verificano entro l'intervallo di frequenza di aggiornamento del download vengono ignorati. Tuttavia, i download manuali ignorano questo valore. </p> <p>Se imposti questo valore sul valore predefinito 1, i dati di Adobe Analytics non vengono scaricati più di una volta entro un periodo di 24 ore. Tutti gli indici di ricerca che si verificano entro l’intervallo di frequenza di aggiornamento del download utilizzano l’ultimo set di dati scaricato. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Vedere anche [Informazioni sulle regole](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)di classificazione.
1. Clic **[!UICONTROL Save Changes]**.

   Viene nuovamente visualizzata la [!DNL Adobe Analytics Report Suites] pagina sullo stage.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di una suite di rapporti di Adobe Analytics {#task_0ACA172214D14654ABDB139F417B9F7D}

Potete utilizzare Elimina per rimuovere una suite di rapporti dalla [!DNL Adobe Analytics Report Suites] pagina. L&#39;eliminazione di una suite di rapporti rimuove solo la copia dei dati dai server di ricerca/merchandising del sito; non influisce sui dati sui sistemi Adobe Analytics.

**Per eliminare una suite di rapporti di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Nella [!DNL Adobe Analytics Report Suites] pagina, nella **[!UICONTROL Actions]** colonna, fate clic **[!UICONTROL Delete]** per la suite di rapporti da rimuovere.
1. Sulla [!DNL Adobe Analytics Delete Report Suite] pagina, fate clic su **[!UICONTROL Delete]**.

## Anteprima dei dati di Adobe Analytics {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

Puoi utilizzare Anteprima per visualizzare le metriche di Adobe Analytics caricate più di recente.

La colonna Riga della tabella mostra il numero per ogni riga di dati delle metriche, indicando l&#39;ordine originale in cui sono state caricate le metriche di Adobe Analytics.

La colonna Prodotto mostra l’elemento Adobe Analytics associato a ciascuna riga di dati delle metriche. I valori di questa colonna vengono utilizzati per associare le pagine di ricerca e merchandising del sito ai valori delle metriche corrispondenti, come configurato nelle definizioni delle classificazioni.

Vedere [Informazioni sulle regole](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)di classificazione.

Consultate [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

Le colonne rimanenti mostrano i valori delle metriche associati a ciascuna voce.

Se la tabella è vuota, significa che non avete ancora caricato alcun dato di Adobe Analytics. Puoi chiudere la [!DNL Adobe Analytics Data Preview] pagina, quindi caricare i dati di Adobe Analytics.

Consultate [Caricamento di dati](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)Adobe Analytics.
Se la tabella è stata designata come rapporto di termini di ricerca, in ogni riga viene visualizzato un piccolo triangolo. Potete fare clic sull&#39;elenco a discesa e selezionare **Simula termine** di ricerca o **Crea nuova regola** aziendale. L&#39;azione selezionata viene applicata al termine di ricerca della riga, i dati che risiedono nella seconda colonna

**Per visualizzare in anteprima i dati di Adobe Analytics**

1. Nel menu del prodotto, effettuate una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**. Nella [!DNL Adobe Analytics Report Suites] pagina, nella [!DNL Actions] colonna, fate clic **[!UICONTROL Preview]** per la suite di rapporti di cui desiderate visualizzare i dati scaricati.

   * Clic **[!UICONTROL Reports]** > **[!UICONTROL Adobe Analytics Terms Reports]**. Nella [!DNL Adobe Analytics Terms Report] pagina, nella [!DNL Actions] colonna, fate clic **[!UICONTROL Preview]** per la suite di rapporti di cui desiderate visualizzare i dati scaricati.

1. Nella [!DNL Adobe Analytics Data Preview] pagina, utilizzate le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare i dati.

   Fai clic sull’intestazione di una colonna nella tabella per ordinare i dati in ordine crescente o decrescente.
1. Effettuate una delle seguenti operazioni:

   * Fare clic **[!UICONTROL Download to Desktop]** per scaricare e salvare la tabella come `.xlt` file.

   * Chiudi la pagina al termine dell’anteprima dei dati di Adobe Analytics e torna alla pagina visualizzata in precedenza.

## Visualizzazione del registro dall’ultimo caricamento di dati di Adobe Analytics {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

Puoi utilizzare Visualizza registro per esaminare il file di registro dati di Adobe Analytics nell’ultimo processo di download. Potete inoltre utilizzare la visualizzazione del registro per monitorare un download in esecuzione.

Consultate [Caricamento di dati](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)Adobe Analytics.

**Per visualizzare il registro dall&#39;ultimo caricamento di dati di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Sulla [!DNL Adobe Analytics Report Suites] pagina, fate clic su **[!UICONTROL View Log]**. Pagina di registro,
1. Nella [!DNL Adobe Analytics Data Log] pagina, utilizzate le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare le informazioni di registro.
1. Al termine, chiudete la pagina per tornare alla [!DNL Adobe Analytics Report Suites] pagina.

## Caricamento di dati Adobe Analytics {#task_2F3C55189B0A4049AB2113F2291CC181}

Puoi scaricare i dati della suite di rapporti Adobe Analytics configurati nella ricerca del sito/merchandising.

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
   <td colname="col2"> <p>Indica l'esito positivo o negativo dell'ultimo tentativo di caricamento dei dati. Oppure, visualizza lo stato di un'operazione di caricamento dati già in corso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Risultati </p> </td> 
   <td colname="col2"> <p>Visualizza il numero di righe di dati delle metriche scaricate durante l'ultimo tentativo di caricamento dei dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora di inizio </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l'ora di inizio dell'ultima operazione di caricamento dei dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora di interruzione </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l'ora di completamento dell'ultima operazione di caricamento dei dati. Oppure indica che l'operazione di caricamento dei dati corrente è ancora in corso. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per caricare i dati di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Sulla [!DNL Stage Adobe Analytics Report Suites] pagina, fate clic su **[!UICONTROL Load Adobe Analytics Data]**.
1. Nella **[!UICONTROL Adobe Analytics Data Load]** pagina, effettuate una delle seguenti operazioni:

   * Fare clic **[!UICONTROL Start Load]** per avviare l&#39;operazione di caricamento.

      Durante un&#39;operazione di caricamento dei dati, la riga **Progress** fornisce informazioni sull&#39;avanzamento.

   * Fare clic **[!UICONTROL Stop Load]** per arrestare l&#39;operazione di caricamento.

1. Fate clic **[!UICONTROL Close]** per tornare alla [!DNL Stage Adobe Analytics Reports Suite] pagina.

## Aggiornamento dell’elenco Suite di rapporti {#task_EA6215D438CA4185B106657D9712ED34}

La prima volta che accedete ad Adobe Analytics dall&#39;interfaccia utente di ricerca del sito/merchandising, viene scaricato e memorizzato nella cache un elenco delle suite di rapporti Adobe Analytics disponibili per la vostra azienda. Se sono state aggiunte di recente nuove suite di rapporti o ne sono state eliminate di esistenti, potete utilizzare Aggiorna elenco suite di rapporti per aggiornare l&#39;elenco attualmente visualizzato nella ricerca del sito/merchandising.

Consultate [Aggiunta di una suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0)di rapporti di Adobe Analytics.

Consultate [Eliminazione di una suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_0ACA172214D14654ABDB139F417B9F7D)di rapporti di Adobe Analytics.

**Per aggiornare l&#39;elenco Suite di rapporti**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. Sulla [!DNL Adobe Analytics Report Suites] pagina, fate clic su **[!UICONTROL Refresh Report Suite List]**.

## Configurazione delle opzioni avanzate di Adobe Analytics {#task_C0FF2D69F59D44D8943A7831ED7FEC19}

Potete utilizzare [!DNL Advanced Adobe Analytics Options] per controllare le impostazioni volte a migliorare il comportamento del processo di download delle suite di rapporti di Adobe Analytics.

Consultate [Modifica delle metriche di Adobe Analytics di una suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)di rapporti.

**Per configurare le opzioni avanzate di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Advanced Options]**.
1. Nella [!DNL Advanced Adobe Analytics Options] pagina, impostate le seguenti opzioni:

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
      <td colname="col2"> <p>Un'impostazione di ottimizzazione che impedisce il download di troppi dati Adobe Analytics. </p> <p>Se imposti questa opzione su un valore diverso da zero, il recupero dei dati di Adobe Analytics viene interrotto quando il numero totale di righe recuperate per ogni metrica supera il valore specificato. </p> <p>Il valore predefinito è 0; nessun valore massimo applicato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Metrica Dimensione recupero ripetuto (righe) </p> </td> 
      <td colname="col2"> <p> Controlla il numero di valori delle metriche di Adobe Analytics da recuperare alla volta. Le righe dei dati delle metriche vengono recuperate ripetutamente fino al recupero di tutti i dati o fino al raggiungimento del limite massimo di righe. </p> <p>Normalmente non è necessario modificare questa impostazione. Tuttavia, potrebbe essere utile ottimizzare la fase di download delle metriche di un reindice completo del sito. </p> <p>Il valore predefinito è 5000. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sui feed di classificazione SAINT {#concept_C55609DA24914BBC92CD90ED0259199D}

Puoi utilizzare Adobe Analytics SAINT per migliorare i tuoi report di analisi tramite l&#39;accettazione di dati tabulari da origini esterne. Ad esempio, potete utilizzare la ricerca nel sito/merchandising per recuperare i dati dai propri indici ed esportarli in Adobe Analytics.

Per utilizzare con successo la funzione SAINT di Adobe Analytics nella ricerca del sito/merchandising, è necessario essere consapevoli dei seguenti requisiti:

* Devi disporre di una società Adobe Analytics e di una suite di rapporti.

   Consultate [Informazioni sul menu](../c-about-settings-menu/c-about-adobe-analytics-menu.md#concept_5FD2D13C9D0D40988E6E51480D690411)di Adobe Analytics.
* L&#39;account utente di Adobe Analytics deve disporre dei privilegi per modificare la Suite di rapporti.

   Consultate [Configurazione dell’autenticazione](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42)delle metriche di Adobe Analytics.
* L&#39;utente Adobe Analytics deve appartenere al gruppo API Web in modo che possa utilizzare l&#39;API Web di Adobe Analytics.
* L&#39;indice di ricerca deve avere dati utilizzabili da Adobe Analytics, ad esempio dati nel formato corretto.

Prima di creare un feed, esaminate le seguenti domande e informazioni in modo da poter completare correttamente la procedura guidata di feed SAINT:

* Con quale suite di rapporti lavorerai?
* Per quale set di classificazioni, ad esempio prodotto, e-var e così via, fornirete i dati?
* Quali classificazioni esistono nei rapporti? La risposta a questa domanda è determinata dal tipo di dati prontamente disponibili dalla ricerca del sito/merchandising, e dal tipo di report desiderati che Adobe Analytics segnala.
* SAINT accetta i dati dalla ricerca del sito/merchandising come tipo di testo. Il formato di tali dati influisce sulla presentazione dei report di Adobe Analytics.

## Creazione di un feed SAINT di Adobe Analytics {#task_914B5AB821E84627953D8EF9339A7DD0}

Puoi utilizzare Adobe Analytics SAINT per migliorare i rapporti di Adobe Analytics accettando dati tabulari da fonti esterne.

Ad esempio, potete utilizzare la ricerca nel sito/merchandising per recuperare dati dai propri indici ed esportare tali dati in Adobe Analytics.

**Per creare un feed SAINT di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Sulla [!DNL SAINT Classification Feeds] pagina, fate clic su **[!UICONTROL Create SAINT Feed]**.
1. Nella finestra di [!DNL Create Feed] dialogo, nel campo di testo Nome **** feed, immettete il nuovo nome per il feed, quindi fate clic su **[!UICONTROL Next]**.

   A questo punto, il feed viene salvato e aggiunto alla [!DNL SAINT Classification Feed] pagina. Se lo scegliete, potete uscire e modificare il feed in un secondo momento per completare la procedura guidata.
1. Nella [!DNL Authentication] pagina, specifica il nome della società Adobe Analytics, il nome utente e il segreto Web nei rispettivi campi di testo, quindi fai clic su **[!UICONTROL Next]**.

   Accertatevi che sia autorizzato a utilizzare l&#39;API Web con Adobe Analytics.
1. Nella **[!UICONTROL Report Suite]** pagina, scegli una suite di rapporti e il relativo set di dati di classificazione, quindi fai clic su **[!UICONTROL Next]**.
1. Nella [!DNL Field Maps] pagina, mappate le classificazioni di Adobe Analytics con i campi metadati di ricerca nel sito/merchandising, quindi fate clic su **[!UICONTROL Next]**.

   Per regolare le classificazioni di Adobe Analytics, fai clic su Classificazioni **[!UICONTROL Edit]** Adobe Analytics per accedere ad Adobe Analytics. Dopo aver apportato le modifiche, fare clic **[!UICONTROL Refresh Classifications]** per aggiornare le scelte di classificazione.
1. Sulla [!DNL Search Criteria] pagina, i dati provenienti dalla ricerca del sito/merchandising possono essere filtrati prima che vengano inviati ad Adobe Analytics SAINT. Create qui le regole del filtro utilizzando l&#39;interfaccia del generatore di regole, quindi fate clic **[!UICONTROL Next]**.
1. Sulla [!DNL Configure FTP] pagina, seleziona il server FTP. Specificate la frequenza con cui desiderate caricare i dati, quindi fate clic **[!UICONTROL Next]**.

   Come procedura ottimale, ogni feed dispone di un proprio account FTP per evitare la perdita accidentale di dati. Puoi creare un nuovo account FTP di Adobe Analytics qui.
1. Nella [!DNL Verification] pagina, fare clic **[!UICONTROL Show Data View]** per controllare la rappresentazione della visualizzazione dati dell&#39;output. Se esistono dei file di feed effettivi, questi sono elencati qui e sono disponibili per il download.
1. Clic **[!UICONTROL Close]**.

## Modifica di un feed SAINT di Adobe Analytics {#task_5BF34D02D0D14359B1CF4B3C1B0ACC84}

Potete modificare tutti gli aspetti di un feed SAINT esistente creato.

**Per modificare un feed SAINT di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella [!DNL Saint Classification Feeds] pagina, sotto la **[!UICONTROL Name]** colonna, nell’elenco a discesa accanto a un feed, fate clic su **[!UICONTROL Edit feed]**.
1. Nella finestra di dialogo Feed SAINT, nel campo di testo Nome **** feed, immettete il nuovo nome per il feed, quindi fate clic su **[!UICONTROL Next]**.

   A questo punto, il feed viene salvato e aggiunto alla [!DNL SAINT Classification Feed] pagina. Se lo scegliete, potete uscire e modificare il feed in un secondo momento per completare la procedura guidata.
1. Nella [!DNL Authentication] pagina, specifica il nome della società Adobe Analytics, il nome utente e il segreto Web nei rispettivi campi di testo, quindi fai clic su **[!UICONTROL Next]**.

   Accertatevi che sia autorizzato a utilizzare l&#39;API Web con Adobe Analytics.
1. Nella **[!UICONTROL Report Suite]** pagina, scegli una suite di rapporti e il relativo set di dati di classificazione, quindi fai clic su **[!UICONTROL Next]**.
1. Nella [!DNL Field Maps] pagina, mappate le classificazioni di Adobe Analytics con i campi metadati di ricerca nel sito/merchandising, quindi fate clic su **[!UICONTROL Next]**.

   Per regolare le classificazioni di Adobe Analytics, fai clic su Classificazioni **[!UICONTROL Edit]** Adobe Analytics per accedere ad Adobe Analytics. Dopo aver apportato le modifiche, fare clic **[!UICONTROL Refresh Classifications]** per aggiornare le scelte di classificazione.
1. Sulla [!DNL Search Criteria] pagina, i dati provenienti dalla ricerca del sito/merchandising possono essere filtrati prima che vengano inviati ad Adobe Analytics SAINT. Create qui le regole del filtro utilizzando l&#39;interfaccia del generatore di regole, quindi fate clic **[!UICONTROL Next]**.
1. Sulla [!DNL Configure FTP] pagina, seleziona il server FTP. Specificate la frequenza con cui desiderate caricare i dati, quindi fate clic **[!UICONTROL Next]**.

   Come procedura ottimale, ogni feed dispone di un proprio account FTP per evitare la perdita accidentale di dati. Puoi creare un nuovo account FTP di Adobe Analytics qui.
1. Nella [!DNL Verification] pagina, fare clic **[!UICONTROL Show Data View]** per controllare la rappresentazione della visualizzazione dati dell&#39;output. Se esistono dei file di feed effettivi, questi sono elencati qui e sono disponibili per il download.
1. Clic **[!UICONTROL Close]**.

## Eliminazione di un feed SAINT di Adobe Analytics {#task_5319B1F4CA1A406393CFD7AE97258CEB}

Puoi eliminare un feed SAINT di Adobe Analytics esistente che non hai più bisogno o che utilizzi.

**Per eliminare un feed SAINT di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella [!DNL Saint Classification Feeds] pagina, nella **[!UICONTROL Name]** colonna, nell’elenco a discesa accanto al feed da rimuovere, fate clic su **[!UICONTROL Delete feed]**.
1. Nella finestra di dialogo Elimina, fate clic su **Sì** per verificare l’eliminazione del feed.

## Visualizzazione di un file di feed SAINT di Adobe Analytics {#task_F0C8BADD25E14E5DB30BF31D1F879FDB}

Potete aprire la [!DNL Verification] pagina di un feed SAINT esistente per controllare la rappresentazione della visualizzazione dati dell&#39;output.

Se esistono dei file di feed effettivi, questi vengono elencati qui e possono essere scaricati come file di testo.

**Per visualizzare un file di feed SAINT di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella [!DNL Saint Classification Feeds] pagina, sotto la **[!UICONTROL Name]** colonna, nell’elenco a discesa accanto a un feed, fate clic su **[!UICONTROL View Feed Files]**.
1. (Facoltativo) Fate clic **[!UICONTROL Download File]** per salvare il file del feed come file di testo.
1. Fate clic **[!UICONTROL Close]** per tornare alla [!DNL SAINT Classification Feeds] pagina.

## Verifica di un feed SAINT di Adobe Analytics {#task_9864D69BE3824FC29C10B36EE4855D25}

Potete testare un feed SAINT di Adobe Analytics esistente senza caricamento di file.

Consultate [Generazione e caricamento di un feed](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_47AED946AA964334A877FDC8D4F6F00A)SAINT di Adobe Analytics.

Consultate [Visualizzazione di un file](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB)di feed SAINT di Adobe Analytics.

**Per testare un file di feed SAINT di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella [!DNL Saint Classification Feeds] pagina, sotto la **[!UICONTROL Name]** colonna, nell’elenco a discesa accanto a un feed, fate clic su **[!UICONTROL Test Feed (No file upload)]**.
1. Al termine dell&#39;elaborazione del feed, fate clic su **[!UICONTROL View Feed Files]**.
1. Nella [!DNL Verification] pagina, fate clic **[!UICONTROL Download File]** per scaricare il file del feed.
1. Fate clic **[!UICONTROL Close]** per tornare alla [!DNL SAINT Classification Feeds] pagina.

## Generazione e caricamento di un feed SAINT di Adobe Analytics {#task_47AED946AA964334A877FDC8D4F6F00A}

Potete generare e caricare i file di feed per un feed Adobe Analytics esistente creato.

Consultate [Test di un feed](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_9864D69BE3824FC29C10B36EE4855D25)SAINT di Adobe Analytics.

Consultate [Visualizzazione di un file](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB)di feed SAINT di Adobe Analytics.

**Per generare e caricare un file di feed SAINT di Adobe Analytics**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. Nella [!DNL Saint Classification Feeds] pagina, sotto la **[!UICONTROL Name]** colonna, nell’elenco a discesa accanto a un feed, fate clic su **[!UICONTROL Generate and Upload Feed]**.
1. Al termine dell&#39;elaborazione del feed, fate clic su **[!UICONTROL View Feed Files]**.
1. Nella [!DNL Verification] pagina, fate clic **[!UICONTROL Download File]** per scaricare il file del feed.
1. Fate clic **[!UICONTROL Close]** per tornare alla [!DNL SAINT Classification Feeds] pagina.
