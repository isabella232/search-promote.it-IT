---
description: Potete utilizzare Indice completo per indicizzare tutte le pagine del sito Web in stato di esecuzione o in stato di esecuzione. L’indicizzazione consente ai clienti di trovare più facilmente ciò che cercano o ciò di cui hanno bisogno quando effettuano una ricerca.
seo-description: Potete utilizzare Indice completo per indicizzare tutte le pagine del sito Web in stato di esecuzione o in stato di esecuzione. L’indicizzazione consente ai clienti di trovare più facilmente ciò che cercano o ciò di cui hanno bisogno quando effettuano una ricerca.
seo-title: Informazioni sull'indice completo
solution: Target
subtopic: Full Index
title: Informazioni sull'indice completo
topic: Index,Site search and merchandising
uuid: dce1eafd-5aea-4945-8305-8f9e7dc392df
translation-type: tm+mt
source-git-commit: 7af85dd37f06fe506e5f57e28a25385ca7ab3db5
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%

---


# Informazioni sull&#39;indice completo{#about-full-index}

Potete utilizzare Indice completo per indicizzare tutte le pagine del sito Web in stato di esecuzione o in stato di esecuzione. L’indicizzazione consente ai clienti di trovare più facilmente ciò che cercano o ciò di cui hanno bisogno quando effettuano una ricerca.

## Utilizzo dell&#39;indice completo {#concept_C69BD21863FD4856B49326F35DB570D3}

Quando si genera un indice completo, vengono visualizzate informazioni sullo stato, ad esempio ora di inizio, tempo trascorso ed errori durante il processo di indicizzazione. Vengono visualizzate anche informazioni sullo stato dell&#39;ultimo indice.

Se è stata modificata un&#39;impostazione account che richiede una rigenerazione dell&#39;indice, lo stato potrebbe essere &quot;Rigenerazione&quot;. Durante la rigenerazione, le impostazioni dell&#39;account vengono applicate per creare un indice del sito aggiornato.

È possibile interrompere o riavviare il processo di indicizzazione in qualsiasi momento.

Mentre il nuovo indice è creato per un sito Web live, i clienti possono continuare a cercare sul sito utilizzando l&#39;ultimo indice. Vengono visualizzate anche informazioni sullo stato dell&#39;ultimo indice.

## Impostazione della pianificazione completa dell&#39;indice per un sito Web live {#task_6760F3256D004A228B38968DF15421F0}

Potete specificare l’ora e i giorni in cui eseguire la ricerca per indicizzazione nel sito Web e aggiornare l’indice.

L&#39;ora selezionata è locale in base al fuso orario configurato in Impostazioni account.

Consultate [Configurazione delle impostazioni dell&#39;account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

I server Web sono spesso programmati per la manutenzione nel bel mezzo della notte. Se il server è inattivo durante un periodo di tempo di indicizzazione pianificato, il processo di indicizzazione non riuscirà. Accertatevi di selezionare un&#39;ora del giorno in cui il server Web sarà disponibile.

La pianificazione dell&#39;indice si applica solo all&#39;indice live; non è possibile pianificare indici in fase.

**Impostazione della pianificazione completa dell&#39;indice per un sito Web live**

1. Scegliere **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Schedule]** dal menu del prodotto.
1. Nell&#39;elenco a discesa **[!UICONTROL Time]**, selezionare l&#39;ora di inizio dell&#39;indicizzazione completa.
1. Selezionare uno o più giorni in cui si desidera eseguire l&#39;indicizzazione completa.
1. Clic **[!UICONTROL Save Changes]**.

## Esecuzione di un indice completo di un sito Web live o in fase {#task_F7FE04D8A1654A7787FCCA31B45EB42D}

Potete utilizzare Indice completo per indicizzare tutte le pagine del sito Web in stato di esecuzione o in stato di esecuzione. L’indicizzazione consente ai clienti di trovare più facilmente ciò che cercano o ciò di cui hanno bisogno quando effettuano una ricerca.

**Per eseguire un indice completo di un sito Web attivo o in fase di esecuzione**

1. Nel menu del prodotto, effettuate una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Index]**.

1. Impostare le opzioni di indicizzazione desiderate.

   <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>Opzione </p> </th> 
    <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Cancella cache indice </p> </td> 
    <td colname="col2"> <p>Rimuove tutti i documenti dalla cache di indice. </p> <p>Quando è selezionata questa opzione, ogni pagina del sito Web viene scaricata dal server. Se questa impostazione è selezionata e disattivata, il vostro account è impostato per cancellare la cache ogni volta che viene eseguito un indice completo. Oppure, alcune impostazioni account precedentemente modificate ora richiedono un indice completo. </p> <p>Se questa opzione è deselezionata, tutte le pagine indicizzate rimangono nell’indice fino a quando il server Web non indica che la pagina non esiste più. Questa situazione è vera anche se i collegamenti a tale pagina vengono rimossi. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Rigenera in sospeso </p> </td> 
    <td colname="col2"> <p>Selezionate Se avete apportato modifiche alle impostazioni dell’account che hanno modificato in modo sostanziale il contenuto dell’indice. Le modifiche sostanziali includono l’effettuazione di modifiche a uno dei seguenti elementi: 
    <ul id="ul_4EB8FF692FEB47BBB9A64D61299380D1"> 
    <li id="li_7CF8D286512F4210BEA3DB9F0EFA097A">Sinonimi </li> 
    <li id="li_8178ABC342BB4365B3927E20433756E3">Raccolte </li> 
    <li id="li_57C8BD06BFA64AFAA2C9EF2CC59520EF">Metadati </li> 
    <li id="li_C4B6A7DA023B4A43991D03EC592170C9">Escluse le parole </li> 
    <li id="li_9E0AD4B6DDC24A5A8FB5C2C1CCD5348A">Lingua account </li> 
    <li id="li_338F107547DF48AAA0EF90F4AD8664A5">Classificazione </li> 
    <li id="li_7F49B86D94974E79AAD381A64A1400F2">Attivazione della ricerca con distinzione tra maiuscole e minuscole </li> 
    <li id="li_E8FE6EE240A840AC826ADF4294AAC6F6">Attivazione del supporto diacritico </li> 
    <li id="li_51763D482DCB4ED0972966F492B8C0F2">Attivazione dell'indicizzazione dei numeri </li> 
    </ul> </p> <p>Prima che venga eseguita un'altra ricerca per indicizzazione, viene eseguito un passaggio rapido attraverso tutti i dati di indice per renderlo conforme alle nuove impostazioni dell'account. </p> <p>Questa opzione è disponibile solo se si sta effettuando un indice completo di un sito Web in uno stadio. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Conteggio tutte le pagine </p> </td> 
    <td colname="col2"> <p>Consente di continuare la ricerca per indicizzazione delle pagine del sito Web anche dopo aver raggiunto il limite di pagine dell'account. </p> <p>Ulteriori pagine non vengono aggiunte all’indice, ma è possibile determinare il numero totale di documenti presenti sul sito Web. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Full Index Now]**.
1. (Facoltativo) In caso di errori di indicizzazione, fare clic su **[!UICONTROL View Errors]** per visualizzare il registro associato.

## Visualizzazione dell&#39;intero registro indice di un sito Web live o in fase {#task_02E5E944C56B4EB19CC1FF321F3221B8}

Quando un indice completo attivo o un indice completo in fase è completo, potete visualizzare il registro associato per risolvere eventuali errori che si sono verificati.

Non è possibile esportare i file di registro né salvarli. Il registro rimane disponibile per la visualizzazione fino a quando non si verifica il nuovo indice.

**Per visualizzare il registro dell&#39;indice completo di un sito Web live o in fase di esecuzione**

1. Nel menu del prodotto, effettuate una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di registro, in alto o in basso, effettuate una delle seguenti operazioni:

   * Utilizzare le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi all&#39;interno del registro.

   * Utilizzate le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare il contenuto visualizzato.

