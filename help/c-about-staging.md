---
description: La gestione temporanea consente di verificare e visualizzare in anteprima le modifiche alle impostazioni e alle configurazioni senza influire sull'indice live.
solution: Target
title: Informazioni sullo staging
topic: Staging, ricerca del sito e merchandising
uuid: 2e5889a6-2e9c-4ac7-9d6e-d35e7cafda5b
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 0%

---


# Informazioni sullo staging{#about-staging}

La gestione temporanea consente di verificare e visualizzare in anteprima le modifiche alle impostazioni e alle configurazioni senza influire sull&#39;indice live.

## Informazioni sullo staging {#concept_08B8F3CA1F4241108F14BA7FC7806CA7}

La gestione temporanea consente di verificare e visualizzare in anteprima le modifiche alle impostazioni e alle configurazioni senza influire sull&#39;indice live.

Vedi anche [ID elemento :context_A5783D07C72042EC886F300FFF62C50](c-about-simulator.md#context_A5783D07C72042EC8886F300FFF62C50).

Qualsiasi pagina con le opzioni di gestione temporanea **[!UICONTROL Push All Live]** o **[!UICONTROL View Live Settings]** significa che tutte le impostazioni in quella pagina possono essere posizionate. Le eccezioni sono le pagine web in Index. Le pagine di quest&#39;area sono esplicitamente per l&#39;indice di staging o l&#39;indice live per consentire di controllare direttamente i due indici in modo indipendente.

Puoi mettere in scena quasi tutto, incluso il tuo indice. Alcune eccezioni includono impostazioni specifiche per l’account che influiscono simultaneamente sull’ambiente live e in esecuzione e sulla pianificazione delle operazioni di indicizzazione. Per impostazione predefinita, quando si salvano modifiche a un&#39;impostazione che può essere messa in scena, questa viene messa in scena automaticamente.

Quando le opzioni **[!UICONTROL Push All Live]** o **[!UICONTROL View Lives Settings]** non sono abilitate (oscurate), le impostazioni di staging in quella pagina sono le stesse delle impostazioni live.

Per un elemento di staging, tieni presente che la versione live delle impostazioni è di sola lettura; può essere manipolato solo spingendo in diretta le impostazioni di staging.

## Informazioni sulla cronologia delle pagine in staging {#section_5BE780AFF26A450A9EFF4000DE53531B}

La maggior parte delle impostazioni di staging dispone di un’opzione [!DNL History] nell’area in alto a destra della pagina. Quando fai clic su **[!UICONTROL History]**, puoi ripristinare tutte le modifiche apportate di recente alla pagina intermedia in questione che hai aperto.

È inoltre possibile visualizzare il registro delle modifiche per una visualizzazione alternativa della cronologia. Ogni volta che viene applicata una modifica, viene creata una versione di backup del file di dati sottostante. Il Registro delle modifiche mostra ogni revisione, indicando il numero di versione, l&#39;indirizzo e-mail dell&#39;utente che ha eseguito le modifiche e la data in cui è stato effettuato il backup. La voce con un valore di versione in grassetto rappresenta la versione corrente.

Consulta [Visualizzazione del registro delle modifiche](c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

## Pagina Gestione impostazioni stage-Live {#section_E72B8CAF516345A5B6B6783CF6E512EE}

Oltre a offrire le opzioni **[!UICONTROL Push All Live]** e **[!UICONTROL View Live Settings]** direttamente da una determinata pagina, puoi anche utilizzare la pagina **[!UICONTROL Manage Stage-Live Settings]** per eseguire la stessa operazione. La pagina **[!UICONTROL Manage Stage-Live Settings]**, disponibile dal menu principale del prodotto, è una posizione centrale che ti mostra tutte le impostazioni del tuo account attualmente in fase di staging. È possibile inviare tutte le impostazioni in tempo reale, inviare solo le impostazioni selezionate in tempo reale o eliminare le impostazioni. Come best practice, tuttavia, esegui sempre il push in diretta di tutti gli elementi di staging per evitare eventuali problemi di interdipendenza.

Le impostazioni nella pagina sono raggruppate in categorie. È possibile espandere ogni categoria per mostrare quali impostazioni della pagina sono state impostate. Attualmente, le dipendenze non vengono tracciate all’interno del gestore di stage. Pertanto, si consiglia di inviare tutto live in una sola volta, ad eccezione dell&#39;indice.

È possibile inviare un indice in tempo reale. Assicurati innanzitutto di verificare che l&#39;indice di staging non sia vecchio o danneggiato. Se commetti un errore e invii l&#39;indice in tempo reale puoi riportare un vecchio indice live. Il push live di un indice in fase di esecuzione in genere richiede meno di 30 secondi.

## Verifica di un&#39;impostazione o di un indice di staging {#section_6800E52D20854A779946EAB600801F12}

Sulle pagine che supportano un controllo di test, puoi eseguire il test rispetto alle impostazioni di staging o live. Quando visualizzi le impostazioni di staging, questa viene utilizzata per il test. Allo stesso modo, quando visualizzi l’impostazione live, il test utilizza le impostazioni live. Nella sezione templates (Modelli), tutti i test vengono eseguiti rispetto alla versione intermedia dell’indice. Per cercare un indice di staging, imposta il parametro `sp_staged` CGI su 1. A sua volta, indica che desideri utilizzare l’indice di staging. Se non esiste un indice di staging, la ricerca viene eseguita nell’indice live e vengono applicate le impostazioni di tempo di ricerca di staging, in base alle necessità.

Vedi anche [Parametri CGI di ricerca back-end](c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

## Visualizzazione delle impostazioni live {#task_401A0EBDB5DB4D4CA933CBA7BECDC10F}

Puoi rivedere la versione live delle impostazioni da qualsiasi pagina intermedia.

<!-- 

t_viewing_live_settings.xml

 -->

Se l’opzione **[!UICONTROL View Live Settings]** non è abilitata (disattivata), significa che le impostazioni dell’area di visualizzazione per quella pagina e le impostazioni Live sono già sincronizzate.

**Per visualizzare le impostazioni Live**

1. In qualsiasi pagina con impostazioni di staging, fai clic su **[!UICONTROL View Live Settings]** per visualizzare la versione attiva delle impostazioni.
1. Facoltativamente, eseguire una delle operazioni seguenti:

   * Fai clic su **[!UICONTROL View]** per visualizzare le opzioni correnti selezionate per l’impostazione temporanea.
   * Fai clic su **[!UICONTROL View Stage Settings]** per tornare all’impostazione temporanea in cui puoi modificare o eliminare l’impostazione.

## Invio live delle impostazioni dello stadio {#task_44306783B4C0408AAA58B471DAF2D9A4}

Puoi inviare le impostazioni in diretta da qualsiasi visualizzazione di pagina in staging o dalla pagina centrale **[!UICONTROL Manage Stage-Live Settings]** .

<!-- 

t_pushing_live_settings_live.xml

 -->

Quando l’opzione **[!UICONTROL Push Live]** è attivata (in grigio) su una pagina, significa che è presente un’impostazione in fase di staging. Oppure, significa che un&#39;impostazione ha delle modifiche e quando si salva, l&#39;impostazione viene messa in scena. Quando fai clic su questa opzione, le modifiche non salvate vengono salvate nell’area intermedia. In assenza di modifiche in sospeso, le impostazioni della pagina vengono inviate immediatamente dal vivo.

**Per attivare le impostazioni in tempo reale**

1. Esegui una delle operazioni seguenti:

   * In qualsiasi pagina in cui è selezionata l’opzione &quot;Staged&quot; come visualizzazione, fare clic su **[!UICONTROL Push Live]**.
   * Scegliere **[!UICONTROL Staging]** dal menu del prodotto. Nella pagina **[!UICONTROL Manage Stage-Live Settings]** , effettua una delle seguenti operazioni:

   * Utilizza la struttura delle impostazioni per controllare solo le impostazioni che desideri inviare in diretta, quindi fai clic su **[!UICONTROL Push Selected Live]**.
   * Clic **[!UICONTROL Push All Live]**.

## Eliminazione delle impostazioni stage-live da una posizione centrale {#task_B72BEA9269704B1399600A9CA273369B}

Se si dispone di molte impostazioni da eliminare, è possibile utilizzare la pagina **[!UICONTROL Manage Stage-Live Settings]** per eliminare le impostazioni da una posizione centrale.

<!-- 

t_deleting_staged_settings_from_a_central_location.xml

 -->

**Avviso**: Quando fai clic su  **[!UICONTROL Delete Selected]**, tutte le impostazioni selezionate vengono immediatamente eliminate; non è disponibile una finestra di dialogo di conferma per verificare che si desideri eliminare le impostazioni selezionate. Inoltre, non esiste una funzione Cronologia associata alla pagina. Pertanto, non è possibile annullare l’eliminazione.

**Per eliminare le impostazioni di stage live da una posizione centrale**

1. Scegliere **[!UICONTROL Staging]** dal menu del prodotto.
1. Nella pagina **[!UICONTROL Manage Stage-Live Settings]**, utilizza la struttura delle impostazioni per controllare solo le impostazioni da eliminare.
1. Clic **[!UICONTROL Delete Selected]**.
