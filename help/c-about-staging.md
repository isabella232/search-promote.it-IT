---
description: La gestione temporanea consente di verificare e visualizzare in anteprima le modifiche apportate alle impostazioni e alle configurazioni senza interferire con l'indice live.
seo-description: La gestione temporanea consente di verificare e visualizzare in anteprima le modifiche apportate alle impostazioni e alle configurazioni senza interferire con l'indice live.
seo-title: Informazioni sullo stato
solution: Target
title: Informazioni sullo stato
topic: Staging,Site search and merchandising
uuid: 2e5889a6-2e9c-4ac7-9d6e-d35e7cafda5b
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Informazioni sullo stato{#about-staging}

La gestione temporanea consente di verificare e visualizzare in anteprima le modifiche apportate alle impostazioni e alle configurazioni senza interferire con l&#39;indice live.

## Informazioni sullo stato {#concept_08B8F3CA1F4241108F14BA7FC7806CA7}

La gestione temporanea consente di verificare e visualizzare in anteprima le modifiche apportate alle impostazioni e alle configurazioni senza interferire con l&#39;indice live.

Vedere anche ID [elemento: context_A5783D07C72042EC886F300FFF62C50](c-about-simulator.md#context_A5783D07C72042EC8886F300FFF62C50).

Qualsiasi pagina con le opzioni di gestione temporanea **[!UICONTROL Push All Live]** o **[!UICONTROL View Live Settings]** indica che tutte le impostazioni della pagina possono essere memorizzate in una sequenza. Le eccezioni sono le pagine Web in Index. Le pagine in questa area sono esplicitamente per l&#39;indice in fase o per l&#39;indice live per consentire di controllare direttamente i due indici in modo indipendente.

Puoi mettere in scena praticamente qualsiasi cosa, incluso il tuo indice. Alcune eccezioni includono impostazioni specifiche per l’account che influiscono sia sull’ambiente live che sullo stadio contemporaneamente e sulla pianificazione delle operazioni di indicizzazione. Per impostazione predefinita, quando si salvano modifiche a un&#39;impostazione che può essere messa in scena, questa viene automaticamente messa in sequenza.

Se le **[!UICONTROL Push All Live]** opzioni **[!UICONTROL View Lives Settings]** o non sono abilitate (attenuate) significa che le impostazioni della pagina sono le stesse delle impostazioni attive.

Per un elemento che viene messo in stato, tenete presente che la versione live delle impostazioni è di sola lettura; può essere manipolato solo spingendo le impostazioni in tempo reale.

## Informazioni sulla cronologia nelle pagine con più stati {#section_5BE780AFF26A450A9EFF4000DE53531B}

La maggior parte delle impostazioni per uno stage dispone di un’ [!DNL History] opzione in alto a destra nella pagina. Facendo clic su **[!UICONTROL History]**, è possibile ripristinare le modifiche apportate di recente alla particolare pagina dello stage aperta.

È inoltre possibile visualizzare il registro delle modifiche per una visualizzazione alternativa della cronologia. Ogni volta che viene applicata una modifica, viene creata una versione di backup del file di dati sottostante. Il registro delle modifiche mostra ciascuna revisione, indicando il numero di versione, l’indirizzo e-mail dell’utente che ha apportato le modifiche e la data in cui è stato effettuato il backup. La voce con un valore di versione in grassetto rappresenta la versione corrente.

Consultate [Visualizzazione del registro](c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057)delle modifiche.

## Pagina Gestione impostazioni stage-Live {#section_E72B8CAF516345A5B6B6783CF6E512EE}

Oltre a offrire le opzioni **[!UICONTROL Push All Live]** e **[!UICONTROL View Live Settings]** direttamente da una determinata pagina, è anche possibile utilizzare la **[!UICONTROL Manage Stage-Live Settings]** pagina per eseguire la stessa operazione. La **[!UICONTROL Manage Stage-Live Settings]** pagina, disponibile dal menu principale del prodotto, è una posizione centrale che mostra tutte le impostazioni dell&#39;account attualmente in fase di esecuzione. Potete trasmettere live tutte le impostazioni, inviare live solo le impostazioni selezionate o eliminare le impostazioni. Come procedura ottimale, tuttavia, è sempre consigliabile inviare in diretta tutti gli elementi sullo stage per evitare eventuali problemi di interdipendenza.

Le impostazioni della pagina sono raggruppate in categorie. È possibile espandere ciascuna categoria per visualizzare le impostazioni della pagina che sono in stato di avanzamento. Al momento, le dipendenze non vengono tracciate all&#39;interno del manager dell&#39;area di visualizzazione. Pertanto, si consiglia di spingere tutti gli elementi live in una volta sola, ad eccezione dell&#39;indice.

È possibile inviare live un indice in fase. Verificate innanzitutto che l&#39;indice in fase non sia obsoleto o danneggiato. Se fai un errore e trasmetti l&#39;indice in tempo reale, puoi ripristinare un indice live precedente. Il push live di un indice in fase di esecuzione in genere richiede meno di 30 secondi.

## Verifica di un&#39;impostazione o un indice in fase {#section_6800E52D20854A779946EAB600801F12}

Sulle pagine che supportano un controllo di test, potete eseguire il test in base alle impostazioni dello stage o del live. Quando visualizzate le impostazioni della fase, per il test viene utilizzata l’impostazione della fase. Allo stesso modo, quando visualizzate l&#39;impostazione dal vivo, il test utilizza le impostazioni dal vivo. Nella sezione dei modelli, tutti i test vengono eseguiti rispetto alla versione in fase dell&#39;indice. Per eseguire la ricerca in un indice in fase, impostate il parametro `sp_staged` CGI su 1. A sua volta, questo indica che si desidera utilizzare l&#39;indice in fase. Se non esiste un indice in fase, viene effettuata una ricerca nell’indice live e vengono applicate le impostazioni della fase di ricerca appropriate.

Consultate anche Parametri CGI di ricerca [back-end](c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

## Visualizzazione delle impostazioni dal vivo {#task_401A0EBDB5DB4D4CA933CBA7BECDC10F}

È possibile esaminare la versione live delle impostazioni da qualsiasi pagina sullo stage.

<!-- 

t_viewing_live_settings.xml

 -->

Se l’ **[!UICONTROL View Live Settings]** opzione non è abilitata (attenuata), significa che le impostazioni dell’area di visualizzazione della pagina e delle impostazioni attive sono già sincronizzate.

**Per visualizzare le impostazioni dal vivo**

1. In qualsiasi pagina con impostazioni per uno stage, fate clic **[!UICONTROL View Live Settings]** per visualizzare la versione attiva delle impostazioni.
1. Facoltativamente, effettuate una delle seguenti operazioni:

   * Fare clic **[!UICONTROL View]** per visualizzare le opzioni correnti selezionate per l&#39;impostazione della fase.
   * Fate clic **[!UICONTROL View Stage Settings]** per tornare all’impostazione dello stage in cui potete modificare o eliminare l’impostazione.

## Invio live delle impostazioni dell’area di visualizzazione {#task_44306783B4C0408AAA58B471DAF2D9A4}

Potete trasmettere le impostazioni in diretta da qualsiasi visualizzazione di pagina in fase o dalla **[!UICONTROL Manage Stage-Live Settings]** pagina centrale.

<!-- 

t_pushing_live_settings_live.xml

 -->

Quando l’ **[!UICONTROL Push Live]** opzione è abilitata (non attenuata) su una pagina, significa che è presente un’impostazione in cui è impostata la visualizzazione in sequenza. Oppure, significa che un’impostazione ha delle modifiche e, al momento del salvataggio, l’impostazione viene messa in scena. Quando fate clic su questa opzione, tutte le modifiche non salvate vengono salvate nell’area intermedia. In assenza di modifiche in sospeso, le impostazioni della pagina vengono immediatamente inviate in diretta.

**Per inviare live le impostazioni per uno stadio**

1. Esegui una delle operazioni seguenti:

   * In qualsiasi pagina in cui sia selezionata l&#39;opzione &quot;In primo piano&quot; come vista, fare clic su **[!UICONTROL Push Live]**.
   * Scegliere **[!UICONTROL Staging]**. Nella **[!UICONTROL Manage Stage-Live Settings]** pagina, effettuate una delle seguenti operazioni:

   * Utilizzate la struttura delle impostazioni per controllare solo le impostazioni che desiderate trasmettere in push dal vivo, quindi fate clic **[!UICONTROL Push Selected Live]**.
   * Clic **[!UICONTROL Push All Live]**.

## Eliminazione delle impostazioni di stage live da una posizione centrale {#task_B72BEA9269704B1399600A9CA273369B}

Se dovete eliminare molte impostazioni, potete utilizzare la **[!UICONTROL Manage Stage-Live Settings]** pagina per eliminare le impostazioni da una posizione centrale.

<!-- 

t_deleting_staged_settings_from_a_central_location.xml

 -->

**Avviso**: Quando si fa clic **[!UICONTROL Delete Selected]**, tutte le impostazioni selezionate vengono immediatamente eliminate; non è disponibile alcuna finestra di dialogo di conferma per verificare che si desideri eliminare le impostazioni selezionate. Inoltre, alla pagina non è associata alcuna funzione Cronologia. Pertanto, non è possibile annullare l’eliminazione.

**Per eliminare le impostazioni della fase dal vivo da una posizione centrale**

1. Scegliere **[!UICONTROL Staging]**.
1. Nella **[!UICONTROL Manage Stage-Live Settings]** pagina, utilizzate la struttura delle impostazioni per controllare solo le impostazioni da eliminare.
1. Clic **[!UICONTROL Delete Selected]**.
