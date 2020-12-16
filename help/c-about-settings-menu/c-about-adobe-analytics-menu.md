---
description: Utilizzate il menu  Adobe Analytics per impostare 'autenticazione delle metriche Adobe Analytics, gestire  metriche Adobe Analytics di una suite di rapporti o utilizzare SAINT per migliorare  rapporti Adobe Analytics mediante l'accettazione di dati tabulari provenienti da origini esterne.
seo-description: Utilizzate il menu  Adobe Analytics per impostare 'autenticazione delle metriche Adobe Analytics, gestire  metriche Adobe Analytics di una suite di rapporti o utilizzare SAINT per migliorare  rapporti Adobe Analytics mediante l'accettazione di dati tabulari provenienti da origini esterne.
seo-title: 'Informazioni sul menu Adobe Analytics '
solution: Target
subtopic: Adobe Analytics
title: 'Informazioni sul menu Adobe Analytics '
topic: Settings,Site search and merchandising
uuid: 5536edf1-d3a4-47af-a307-6e46f385f738
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '3448'
ht-degree: 0%

---


# Informazioni sul menu Adobe Analytics {#about-the-adobe-analytics-menu}

Utilizzate il menu  Adobe Analytics per impostare &#39;autenticazione delle metriche Adobe Analytics, gestire  metriche Adobe Analytics di una suite di rapporti o utilizzare SAINT per migliorare  rapporti Adobe Analytics mediante l&#39;accettazione di dati tabulari provenienti da origini esterne.

## Impostazione &#39;autenticazione delle metriche Adobe Analytics {#task_8AA93F6273B747F9B4DE9E8DFBCBDC42}

Per includere  metriche Adobe Analytics nelle classificazioni di ricerca/merchandising del sito, è innanzitutto necessario ottenere un  accesso ai servizi Web Adobe Analytics. Dopo aver ottenuto le informazioni di accesso, potete utilizzarle per configurare &#39;autenticazione Adobe Analytics nella ricerca del sito/merchandising.

**Per impostare &#39;autenticazione delle metriche Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Authentication]** dal menu del prodotto.
1. Nella pagina [!DNL Setup Adobe Analytics Metrics Authentication], specificate le informazioni richieste in ciascun campo.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Campo di testo </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> nome società Adobe Analytics </p> </td> 
      <td colname="col2"> <p>La stessa impostazione Nome società utilizzata per accedere al tuo account Adobe Analytics . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome utente Servizi Web </p> </td> 
      <td colname="col2"> <p>Nome utente servizi Web associato al tuo account Adobe Analytics . </p> <p>Potete ottenere queste informazioni in  Adobe Analytics. Nella barra dei menu  Adobe Analytics, fare clic su <span class="uicontrol"> <b>Admin</b> </span> &gt; <span class="uicontrol"> <b> Admin Console</b> </span> &gt; <span class="uicontrol"> &lt;a8/&gt; <b>Company</b> </span> &gt; <span class="uicontrol"> <b>Servizi Web</b> </span>. Le informazioni si trovano nella tabella Informazioni di accesso API. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Segreto condiviso servizi Web </p> </td> 
      <td colname="col2"> <p>Segreto condiviso di Web Services associato al tuo account Adobe Analytics . </p> <p>Potete ottenere queste informazioni in  Adobe Analytics. Nella barra dei menu  Adobe Analytics, fare clic su <span class="uicontrol"> <b>Admin</b> </span> &gt; <span class="uicontrol"> <b> Admin Console</b> </span> &gt; <span class="uicontrol"> &lt;a8/&gt; <b>Company</b> </span> &gt; <span class="uicontrol"> <b>Servizi Web</b> </span>. Le informazioni si trovano nella tabella Informazioni di accesso API. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni  suite di rapporti Adobe Analytics {#concept_1A51AEC5D40E459B813E7891D64B1BAE}

Per utilizzare  dati delle suite di rapporti Adobe Analytics nella ricerca del sito/merchandising, è innanzitutto necessario creare copie dei dati Adobe Analytics  nel vostro account di ricerca del sito/merchandising.

Puoi creare nuove definizioni  suite di rapporti Adobe Analytics, oppure puoi visualizzare o modificare le suite  rapporti Adobe Analytics esistenti e le metriche associate.

La prima volta che accedete  Adobe Analytics dalla ricerca del sito/merchandising, viene scaricato e memorizzato nella cache un elenco delle suite di rapporti disponibili per la vostra azienda. Se sono state aggiunte di recente nuove suite di rapporti o ne sono state rimosse altre esistenti, puoi aggiornare l’elenco delle suite di rapporti per scaricare nuovamente l’elenco delle suite di rapporti.

## Aggiunta di  suite di rapporti Adobe Analytics {#task_6DE17305EA7146DA8C30FF8FDF68A3C0}

Potete selezionare  Suite di rapporti Adobe Analytics su cui basare le regole di classificazione di ricerca e merchandising del sito.

L&#39;elenco da cui potete selezionare deve corrispondere alle suite di rapporti disponibili dall&#39;account Adobe Analytics . La Suite di rapporti selezionata determina le metriche disponibili per l&#39;utilizzo nelle regole di classificazione di ricerca e merchandising del sito.

Vedere [Informazioni sulle regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

Dopo aver aggiunto una suite di rapporti Adobe Analytics , puoi modificarne le metriche.

Consultate [Modifica delle metriche Adobe Analytics  di una suite di rapporti](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

**Per aggiungere una suite di rapporti Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]** dal menu del prodotto.
1. Nella pagina  suite di rapporti di Adobe Analytics, fate clic su **[!UICONTROL Add Report Suite]**.
1. Nell&#39;elenco a discesa della riga di tabella appena aggiunta, selezionate la suite di rapporti desiderata.
1. Modificare le metriche Adobe Analytics  di una suite di rapporti.

## Modifica delle metriche Adobe Analytics  di una suite di rapporti {#task_360904CCBBB140238ADA036C3CC07664}

Per includere  metriche Adobe Analytics nelle regole di classificazione nella ricerca e nel merchandising del sito, selezionate una o più metriche associate alla suite di rapporti selezionata. Quindi si configurano le opzioni utilizzate per recuperare i dati delle metriche tramite il  Adobe Analytics Web Service.

Consultate [Aggiunta di una suite di rapporti Adobe Analytics ](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0).

Vedere [Configurazione di opzioni avanzate  Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_C0FF2D69F59D44D8943A7831ED7FEC19).

**Per modificare le metriche Adobe Analytics  di una suite di rapporti**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]** dal menu del prodotto.
1. Nella pagina [!DNL Adobe Analytics Report Suites], nella colonna **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Edit]** per la suite di rapporti di cui si desidera configurare le metriche.
1. Nella pagina [!DNL Edit Adobe Analytics Metrics], imposta le metriche richieste. Le metriche che non hanno un asterisco (*) accanto al nome della metrica sono facoltative.

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
      <td colname="col2"> <p>Fornisce un nome "alias" per il nome  suite di rapporti Adobe Analytics. Questo nome alternativo è utile se la stessa Suite di rapporti viene utilizzata in più definizioni. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Seleziona tipo di rapporto </p> </td> 
      <td colname="col2"> <p>Specifica il valore del tipo di rapporto da utilizzare con la suite di rapporti selezionata. Il valore identifica la chiave per ogni riga di risultati restituita. </p> <p>Il tipo di rapporto è anche noto come elemento Adobe Analytics . </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome campo rimando </p> </td> 
      <td colname="col2"> <p>Specifica un campo di metadati i cui valori vengono utilizzati come "chiavi" di ricerca nei dati della suite di rapporti. </p> <p>Se non è selezionato alcun valore ("— None —"), i dati di questa Suite di rapporti non sono disponibili per l'utilizzo nei calcoli di classificazione ( <span class="uicontrol"> <b>Rules</b> </span> &gt; <span class="uicontrol"> <b>Regole di classificazione</b> </span> &gt; <span class="uicontrol"> <b>Modifica regole</b> 11/&gt;).</span> </p> <p>Quando si seleziona un valore, i valori di questo campo vengono utilizzati per fare riferimento incrociato ai documenti di ricerca e merchandising del sito con i dati Adobe Analytics  suite di rapporti, utilizzando il valore selezionato Tipo di rapporto impostato in precedenza. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rapporto termini di ricerca </p> </td> 
      <td colname="col2"> <p>Consente di creare regole business e simulare i termini di ricerca dalla pagina <b>Stage  Adobe Analytics Data Preview</b>. </p> <p>Vedere <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0" type="task" format="dita" scope="local">Anteprima  dati Adobe Analytics</a>. </p> <p>Su ogni riga viene visualizzato un menu a discesa contenente due opzioni: <b>Simula termini di ricerca</b> e <b>Crea nuova regola business</b>. </p> <p>Entrambe le opzioni utilizzano i dati del tipo di rapporto come termini di ricerca. Pertanto, questa funzione ha senso solo se il tipo di rapporto rappresenta i termini di ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Metrics (Metriche) </p> </td> 
      <td colname="col2"> <p>Identifica i valori delle metriche da scaricare e utilizzare nelle regole di classificazione di ricerca e merchandising del sito. </p> <p>Le metriche configurate qui vengono visualizzate come scelte nelle <span class="uicontrol"> <b>Regole</b> </span> &gt; <span class="uicontrol"> <b>Regole di classificazione</b> </span> &gt; <span class="uicontrol"> <b>Modifica regole</b> </span> &lt;a11/&gt; pagine centrali dei membri, quando il tipo di dati della regola è impostato su <span class="uicontrol">  Adobe Analytics Metric (Number) </span>. Le opzioni disponibili mostrano una combinazione dei nomi delle suite di rapporti o delle visualizzazioni delle suite di rapporti, se specificate, e dei singoli nomi delle metriche. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore della metrica minima </p> </td> 
      <td colname="col2"> <p>Consente di immettere un valore diverso da zero per specificare un valore minimo per la metrica. </p> <p>Se vuoto o zero, vengono scaricati tutti i valori della metrica; in caso contrario, il download di questa metrica si interrompe quando viene passato il valore della metrica minima. </p> <p> le metriche Adobe Analytics vengono recuperate in ordine decrescente. </p> <p>Fare clic su <span class="uicontrol"> <b>+</b> </span> per aggiungere definizioni metriche aggiuntive; fate clic su <span class="uicontrol"> <b>-</b> </span> per rimuovere le definizioni delle metriche non più necessarie o desiderate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> periodo di aggregazione delle metriche Adobe Analytics (giorni) </p> </td> 
      <td colname="col2"> <p> Controlla il numero di giorni di  metriche Adobe Analytics da recuperare, contando dalla data di ieri. Nessun tentativo di recupero dati dal giorno corrente. </p> <p>Il valore predefinito è 7. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Frequenza di aggiornamento del download di Adobe Analytics (giorni) </p> </td> 
      <td colname="col2"> <p> Imposta l'intervallo minimo tra i download  dati Adobe Analytics utilizzati nei calcoli di classifica. </p> <p>I download attivati dall'indice che si verificano entro l'intervallo di frequenza di aggiornamento del download vengono ignorati. Tuttavia, i download manuali ignorano questo valore. </p> <p>Se si imposta questo valore sul valore predefinito 1,  i dati Adobe Analytics non vengono scaricati più di una volta entro un periodo di 24 ore. Tutti gli indici di ricerca che si verificano entro l’intervallo di frequenza di aggiornamento del download utilizzano l’ultimo set di dati scaricato. </p> <p>Questa metrica è obbligatoria. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Vedere anche [Informazioni sulle regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).
1. Clic **[!UICONTROL Save Changes]**.

   Viene nuovamente visualizzata la pagina [!DNL Adobe Analytics Report Suites] in fase.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di  suite di rapporti Adobe Analytics {#task_0ACA172214D14654ABDB139F417B9F7D}

Puoi utilizzare Elimina per rimuovere una suite di rapporti dalla pagina [!DNL Adobe Analytics Report Suites]. L&#39;eliminazione di una suite di rapporti rimuove solo la copia dei dati dai server di ricerca/merchandising del sito; non influisce sui dati  sistemi Adobe Analytics.

**Per eliminare una  suite di rapporti Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]** dal menu del prodotto.
1. Nella pagina [!DNL Adobe Analytics Report Suites], nella colonna **[!UICONTROL Actions]** fare clic su **[!UICONTROL Delete]** per la suite di rapporti da rimuovere.
1. Nella pagina [!DNL Adobe Analytics Delete Report Suite] fare clic su **[!UICONTROL Delete]**.

## Anteprima  dati Adobe Analytics {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

Potete utilizzare Anteprima per visualizzare le metriche Adobe Analytics caricate più di recente .

La colonna Riga della tabella mostra il numero per ogni riga di dati delle metriche, indicando l&#39;ordine originale in cui sono state caricate le metriche Adobe Analytics .

La colonna Prodotto mostra l&#39;elemento Adobe Analytics  associato a ogni riga di dati delle metriche. I valori di questa colonna vengono utilizzati per associare le pagine di ricerca e merchandising del sito ai valori delle metriche corrispondenti, come configurato nelle definizioni delle classificazioni.

Vedere [Informazioni sulle regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

Vedere [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

Le colonne rimanenti mostrano i valori delle metriche associati a ciascuna voce.

Se la tabella è vuota, significa che non sono ancora stati caricati  dati Adobe Analytics. È possibile chiudere la pagina [!DNL Adobe Analytics Data Preview], quindi caricare  dati Adobe Analytics.

Vedere [Caricamento  dati Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).
Se la tabella è stata designata come rapporto di termini di ricerca, in ogni riga viene visualizzato un piccolo triangolo. È possibile fare clic sull&#39;elenco a discesa e selezionare **Simula termine di ricerca** o **Crea nuova regola business**. L&#39;azione selezionata viene applicata al termine di ricerca della riga, i dati che risiedono nella seconda colonna

**Per visualizzare in anteprima  dati Adobe Analytics**

1. Nel menu del prodotto, effettuate una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**. Nella pagina [!DNL Adobe Analytics Report Suites], nella colonna [!DNL Actions], fare clic su **[!UICONTROL Preview]** per la suite di rapporti di cui si desidera visualizzare i dati scaricati.

   * Clic **[!UICONTROL Reports]** > **[!UICONTROL Adobe Analytics Terms Reports]**. Nella pagina [!DNL Adobe Analytics Terms Report], nella colonna [!DNL Actions], fare clic su **[!UICONTROL Preview]** per la suite di rapporti di cui si desidera visualizzare i dati scaricati.

1. Nella pagina [!DNL Adobe Analytics Data Preview], utilizzate le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare i dati.

   Fai clic sull’intestazione di una colonna nella tabella per ordinare i dati in ordine crescente o decrescente.
1. Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL Download to Desktop]** per scaricare e salvare la tabella come file `.xlt`.

   * Chiudi la pagina al termine dell’anteprima dei dati Adobe Analytics  e torna alla pagina visualizzata in precedenza.

## Visualizzazione del registro dal caricamento di dati Adobe Analytics più recente  {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

È possibile utilizzare Visualizza registro per esaminare  file di registro dati Adobe Analytics del processo di download più recente. Potete inoltre utilizzare la visualizzazione del registro per monitorare un download in esecuzione.

Vedere [Caricamento  dati Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**Per visualizzare il registro dal caricamento dei dati Adobe Analytics  più recente**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]** dal menu del prodotto.
1. Nella pagina [!DNL Adobe Analytics Report Suites] fare clic su **[!UICONTROL View Log]**. Pagina di registro,
1. Nella pagina [!DNL Adobe Analytics Data Log], utilizzate le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare le informazioni di registro.
1. Al termine, chiudete la pagina per tornare alla pagina [!DNL Adobe Analytics Report Suites].

## Caricamento  dati Adobe Analytics {#task_2F3C55189B0A4049AB2113F2291CC181}

Puoi scaricare i dati  suite di rapporti Adobe Analytics configurati nella ricerca del sito/merchandising.

La pagina Caricamento dati mostra lo stato dell’ultima operazione di caricamento dati Adobe Analytics  con le seguenti informazioni:

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

**Per caricare  dati Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]** dal menu del prodotto.
1. Nella pagina [!DNL Stage Adobe Analytics Report Suites] fare clic su **[!UICONTROL Load Adobe Analytics Data]**.
1. Nella pagina **[!UICONTROL Adobe Analytics Data Load]**, effettuare una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL Start Load]** per avviare l&#39;operazione di caricamento.

      Durante un&#39;operazione di caricamento dei dati, la riga **Progress** fornisce informazioni sull&#39;avanzamento.

   * Fare clic su **[!UICONTROL Stop Load]** per arrestare l&#39;operazione di caricamento.

1. Fare clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL Stage Adobe Analytics Reports Suite].

## Aggiornamento dell&#39;elenco Suite di rapporti {#task_EA6215D438CA4185B106657D9712ED34}

La prima volta che accedete  Adobe Analytics dall’interfaccia utente di ricerca del sito/merchandising, viene scaricato e memorizzato nella cache un elenco delle suite di rapporti Adobe Analytics  della società disponibili. Se sono state aggiunte di recente nuove suite di rapporti o ne sono state eliminate di esistenti, potete utilizzare Aggiorna elenco suite di rapporti per aggiornare l&#39;elenco attualmente visualizzato nella ricerca del sito/merchandising.

Consultate [Aggiunta di una suite di rapporti Adobe Analytics ](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0).

Vedere [Eliminazione di una suite di rapporti Adobe Analytics ](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_0ACA172214D14654ABDB139F417B9F7D).

**Per aggiornare l&#39;elenco Suite di rapporti**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]** dal menu del prodotto.
1. Nella pagina [!DNL Adobe Analytics Report Suites] fare clic su **[!UICONTROL Refresh Report Suite List]**.

## Configurazione delle opzioni avanzate  Adobe Analytics {#task_C0FF2D69F59D44D8943A7831ED7FEC19}

È possibile utilizzare [!DNL Advanced Adobe Analytics Options] per controllare le impostazioni volte a migliorare il comportamento del processo di download  suite di rapporti Adobe Analytics.

Consultate [Modifica delle metriche Adobe Analytics  di una suite di rapporti](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

**Per configurare le opzioni avanzate  Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Advanced Options]** dal menu del prodotto.
1. Nella pagina [!DNL Advanced Adobe Analytics Options], impostate le seguenti opzioni:

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
      <td colname="col2"> <p>Un'impostazione di ottimizzazione che impedisce il download di troppi dati Adobe Analytics . </p> <p>Se si imposta questa opzione su un valore diverso da zero, il recupero dati  Adobe Analytics viene interrotto quando il numero totale di righe recuperate per ogni metrica supera il valore specificato. </p> <p>Il valore predefinito è 0; nessun valore massimo applicato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Metrica Dimensione recupero ripetuto (righe) </p> </td> 
      <td colname="col2"> <p> Controlla il numero  valori delle metriche Adobe Analytics da recuperare alla volta. Le righe dei dati delle metriche vengono recuperate ripetutamente fino al recupero di tutti i dati o fino al raggiungimento del limite massimo di righe. </p> <p>Normalmente non è necessario modificare questa impostazione. Tuttavia, potrebbe essere utile ottimizzare la fase di download delle metriche di un reindice completo del sito. </p> <p>Il valore predefinito è 5000. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sui feed di classificazione SAINT {#concept_C55609DA24914BBC92CD90ED0259199D}

Puoi utilizzare  SAINT Adobe Analytics per migliorare i tuoi report di analisi tramite l&#39;accettazione di dati tabulari da origini esterne. Ad esempio, potete utilizzare la ricerca nel sito/merchandising per recuperare i dati dai propri indici ed esportare tali dati in  Adobe Analytics.

Per utilizzare con successo la funzione SAINT Adobe Analytics  nella ricerca del sito/merchandising, è necessario essere consapevoli dei seguenti requisiti:

* È necessario disporre di una  società Adobe Analytics e di una suite di rapporti.

   Vedere [Informazioni sul menu Adobe Analytics ](../c-about-settings-menu/c-about-adobe-analytics-menu.md#concept_5FD2D13C9D0D40988E6E51480D690411).
* L&#39;account utente  Adobe Analytics deve disporre dei privilegi per modificare la Suite di rapporti.

   Vedere [Configurazione &#39;autenticazione delle metriche Adobe Analytics](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42).
* L&#39;utente Adobe Analytics  deve appartenere al gruppo API Web in modo che possa utilizzare l&#39;API Web  Adobe Analytics.
* L&#39;indice di ricerca deve avere dati che  Adobe Analytics può utilizzare, ad esempio dati nel formato corretto.

Prima di creare un feed, esaminate le seguenti domande e informazioni in modo da poter completare correttamente la procedura guidata Feed SAINT:

* Con quale suite di rapporti lavorerai?
* Per quale set di classificazioni, ad esempio prodotto, e-var e così via, fornisci i dati?
* Quali classificazioni esistono nei rapporti? La risposta a questa domanda è determinata dal tipo di dati prontamente disponibili dalla ricerca sul sito/merchandising e dal tipo di rapporti che  Adobe Analytics segnala come desiderati.
* Il SAINT accetta i dati provenienti dalla ricerca del sito/merchandising come tipo di testo. Il formato di tali dati influisce sulla presentazione dei report Adobe Analytics .

## Creazione di un feed SAINT Adobe Analytics  {#task_914B5AB821E84627953D8EF9339A7DD0}

Potete utilizzare  SAINT Adobe Analytics per migliorare  rapporti Adobe Analytics accettando dati tabulari provenienti da fonti esterne.

Ad esempio, potete utilizzare la ricerca nel sito/merchandising per recuperare dati dai propri indici ed esportare tali dati in  Adobe Analytics.

**Per creare un feed SAINT Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]** dal menu del prodotto.
1. Nella pagina [!DNL SAINT Classification Feeds] fare clic su **[!UICONTROL Create SAINT Feed]**.
1. Nella finestra di dialogo [!DNL Create Feed], nel campo di testo **Feed Name**, immettere il nuovo nome del feed, quindi fare clic su **[!UICONTROL Next]**.

   A questo punto, il feed viene salvato e aggiunto alla pagina [!DNL SAINT Classification Feed]. Se lo scegliete, potete uscire e modificare il feed in un secondo momento per completare la procedura guidata.
1. Nella pagina [!DNL Authentication], specificate il nome  società Adobe Analytics, il nome utente e il segreto Web nei rispettivi campi di testo, quindi fate clic su **[!UICONTROL Next]**.

   Accertatevi che sia autorizzato a utilizzare l&#39;API Web con  Adobe Analytics.
1. Nella pagina **[!UICONTROL Report Suite]**, scegli una suite di rapporti e il relativo set di dati di classificazione, quindi fai clic su **[!UICONTROL Next]**.
1. Nella pagina [!DNL Field Maps] mappare  classificazioni Adobe Analytics con campi di metadati di ricerca nel sito/merchandising, quindi fare clic su **[!UICONTROL Next]**.

   Per regolare  classificazioni Adobe Analytics, fare clic su **[!UICONTROL Edit]**  Classificazioni Adobe Analytics per accedere  Adobe Analytics. Dopo aver apportato le modifiche, fare clic su **[!UICONTROL Refresh Classifications]** per aggiornare le scelte di classificazione.
1. Nella pagina [!DNL Search Criteria], i dati provenienti dalla ricerca del sito/merchandising possono essere filtrati prima che vengano inviati a  SAINT Adobe Analytics. Create qui le regole del filtro utilizzando l&#39;interfaccia del generatore di regole, quindi fate clic su **[!UICONTROL Next]**.
1. Nella pagina [!DNL Configure FTP], seleziona il server FTP. Specificate la frequenza con cui desiderate caricare i dati, quindi fate clic su **[!UICONTROL Next]**.

   Come procedura ottimale, ogni feed dispone di un proprio account FTP per evitare la perdita accidentale di dati. Puoi creare un nuovo account Adobe Analytics FTP  qui.
1. Nella pagina [!DNL Verification], fare clic su **[!UICONTROL Show Data View]** per controllare la rappresentazione della visualizzazione dati dell&#39;output. Se esistono dei file di feed effettivi, questi sono elencati qui e sono disponibili per il download.
1. Clic **[!UICONTROL Close]**.

## Modifica di un feed SAINT Adobe Analytics  {#task_5BF34D02D0D14359B1CF4B3C1B0ACC84}

Potete modificare tutti gli aspetti di un feed SAINT esistente creato.

**Per modificare un feed SAINT Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]** dal menu del prodotto.
1. Nella pagina [!DNL Saint Classification Feeds], nella colonna **[!UICONTROL Name]**, nell&#39;elenco a discesa accanto a un feed, fare clic su **[!UICONTROL Edit feed]**.
1. Nella finestra di dialogo Feed SAINT, nel campo di testo **Nome feed**, immettete il nuovo nome per il feed, quindi fate clic su **[!UICONTROL Next]**.

   A questo punto, il feed viene salvato e aggiunto alla pagina [!DNL SAINT Classification Feed]. Se lo scegliete, potete uscire e modificare il feed in un secondo momento per completare la procedura guidata.
1. Nella pagina [!DNL Authentication], specificate il nome  società Adobe Analytics, il nome utente e il segreto Web nei rispettivi campi di testo, quindi fate clic su **[!UICONTROL Next]**.

   Accertatevi che sia autorizzato a utilizzare l&#39;API Web con  Adobe Analytics.
1. Nella pagina **[!UICONTROL Report Suite]**, scegli una suite di rapporti e il relativo set di dati di classificazione, quindi fai clic su **[!UICONTROL Next]**.
1. Nella pagina [!DNL Field Maps] mappare  classificazioni Adobe Analytics con campi di metadati di ricerca nel sito/merchandising, quindi fare clic su **[!UICONTROL Next]**.

   Per regolare  classificazioni Adobe Analytics, fare clic su **[!UICONTROL Edit]**  Classificazioni Adobe Analytics per accedere  Adobe Analytics. Dopo aver apportato le modifiche, fare clic su **[!UICONTROL Refresh Classifications]** per aggiornare le scelte di classificazione.
1. Nella pagina [!DNL Search Criteria], i dati provenienti dalla ricerca del sito/merchandising possono essere filtrati prima che vengano inviati a  SAINT Adobe Analytics. Create qui le regole del filtro utilizzando l&#39;interfaccia del generatore di regole, quindi fate clic su **[!UICONTROL Next]**.
1. Nella pagina [!DNL Configure FTP], seleziona il server FTP. Specificate la frequenza con cui desiderate caricare i dati, quindi fate clic su **[!UICONTROL Next]**.

   Come procedura ottimale, ogni feed dispone di un proprio account FTP per evitare la perdita accidentale di dati. Puoi creare un nuovo account Adobe Analytics FTP  qui.
1. Nella pagina [!DNL Verification], fare clic su **[!UICONTROL Show Data View]** per controllare la rappresentazione della visualizzazione dati dell&#39;output. Se esistono dei file di feed effettivi, questi sono elencati qui e sono disponibili per il download.
1. Clic **[!UICONTROL Close]**.

## Eliminazione di un feed SAINT Adobe Analytics  {#task_5319B1F4CA1A406393CFD7AE97258CEB}

È possibile eliminare un feed SAINT Adobe Analytics  esistente che non è più necessario né utilizzato.

**Per eliminare un feed SAINT Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]** dal menu del prodotto.
1. Nella pagina [!DNL Saint Classification Feeds], nella colonna **[!UICONTROL Name]**, nell&#39;elenco a discesa accanto al feed che si desidera rimuovere, fare clic su **[!UICONTROL Delete feed]**.
1. Nella finestra di dialogo Elimina, fate clic su **Sì** per verificare l&#39;eliminazione del feed.

## Visualizzazione di un file di feed SAINT Adobe Analytics  {#task_F0C8BADD25E14E5DB30BF31D1F879FDB}

È possibile aprire la pagina [!DNL Verification] di un feed SAINT esistente per controllare la rappresentazione della visualizzazione dati dell&#39;output.

Se esistono dei file di feed effettivi, questi vengono elencati qui e possono essere scaricati come file di testo.

**Per visualizzare un file di feed SAINT Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]** dal menu del prodotto.
1. Nella pagina [!DNL Saint Classification Feeds], nella colonna **[!UICONTROL Name]**, nell&#39;elenco a discesa accanto a un feed, fare clic su **[!UICONTROL View Feed Files]**.
1. (Facoltativo) Fate clic su **[!UICONTROL Download File]** per salvare il file di feed come file di testo.
1. Fare clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL SAINT Classification Feeds].

## Verifica di un feed SAINT Adobe Analytics  {#task_9864D69BE3824FC29C10B36EE4855D25}

Potete testare un feed di SAINT Adobe Analytics  esistente senza caricamento di file.

Consultate [Generazione e caricamento di un feed SAINT Adobe Analytics ](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_47AED946AA964334A877FDC8D4F6F00A).

Vedere [Visualizzazione di un file di feed SAINT Adobe Analytics ](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB).

**Per testare un file di feed SAINT Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]** dal menu del prodotto.
1. Nella pagina [!DNL Saint Classification Feeds], nella colonna **[!UICONTROL Name]**, nell&#39;elenco a discesa accanto a un feed, fare clic su **[!UICONTROL Test Feed (No file upload)]**.
1. Al termine dell&#39;elaborazione del feed, fate clic su **[!UICONTROL View Feed Files]** dall&#39;elenco a discesa del nome del feed.
1. Nella pagina [!DNL Verification], fate clic su **[!UICONTROL Download File]** per scaricare il file del feed.
1. Fare clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL SAINT Classification Feeds].

## Generazione e caricamento di un feed SAINT Adobe Analytics  {#task_47AED946AA964334A877FDC8D4F6F00A}

Potete generare e caricare i file di feed per un feed Adobe Analytics  esistente creato.

Vedere [Verifica di un feed SAINT Adobe Analytics ](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_9864D69BE3824FC29C10B36EE4855D25).

Vedere [Visualizzazione di un file di feed SAINT Adobe Analytics ](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB).

**Per generare e caricare un file di feed SAINT Adobe Analytics**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]** dal menu del prodotto.
1. Nella pagina [!DNL Saint Classification Feeds], nella colonna **[!UICONTROL Name]**, nell&#39;elenco a discesa accanto a un feed, fare clic su **[!UICONTROL Generate and Upload Feed]**.
1. Al termine dell&#39;elaborazione del feed, fate clic su **[!UICONTROL View Feed Files]** dall&#39;elenco a discesa del nome del feed.
1. Nella pagina [!DNL Verification], fate clic su **[!UICONTROL Download File]** per scaricare il file del feed.
1. Fare clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL SAINT Classification Feeds].
