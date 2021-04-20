---
description: È possibile utilizzare Indice completo per indicizzare tutte le pagine del sito web in esecuzione o in esecuzione. L’indicizzazione consente ai clienti di trovare più facilmente ciò che cercano o ciò di cui hanno bisogno quando eseguono una ricerca.
solution: Target
subtopic: Full Index
title: Informazioni sull'indice completo
topic: Index,Site search and merchandising
uuid: dce1eafd-5aea-4945-8305-8f9e7dc392df
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 1%

---


# Informazioni sull&#39;indice completo{#about-full-index}

È possibile utilizzare Indice completo per indicizzare tutte le pagine del sito web in esecuzione o in esecuzione. L’indicizzazione consente ai clienti di trovare più facilmente ciò che cercano o ciò di cui hanno bisogno quando eseguono una ricerca.

## Utilizzo dell&#39;indice completo {#concept_C69BD21863FD4856B49326F35DB570D3}

Quando si genera un indice completo, vengono visualizzate le informazioni sullo stato, ad esempio il tempo di avvio, il tempo trascorso e gli errori durante il processo di indicizzazione. Vengono visualizzate anche informazioni sullo stato dell&#39;ultimo indice.

Se è stata modificata un&#39;impostazione di un conto che richiede una rigenerazione dell&#39;indice, lo stato potrebbe essere &quot;Rigenerazione&quot;. Durante la rigenerazione, le impostazioni dell&#39;account vengono applicate per creare un indice del sito aggiornato.

Puoi interrompere o riavviare il processo di indicizzazione in qualsiasi momento.

Mentre il nuovo indice è generato per un sito web live, i clienti possono continuare a cercare il tuo sito utilizzando il tuo ultimo indice. Vengono visualizzate anche informazioni sullo stato dell&#39;ultimo indice.

## Impostazione della pianificazione completa dell&#39;indice per un sito web live {#task_6760F3256D004A228B38968DF15421F0}

Puoi specificare l’ora e i giorni in cui eseguire la ricerca per indicizzazione del sito web e aggiornare l’indice.

L&#39;ora selezionata è locale in base al fuso orario configurato in Impostazioni account.

Consulta [Configurazione delle impostazioni account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

I server web sono spesso programmati per la manutenzione nel bel mezzo della notte. Se il server è inattivo durante un&#39;ora di indicizzazione pianificata, il processo di indicizzazione non riuscirà. Assicurati di selezionare un’ora del giorno in cui il server web è disponibile.

La pianificazione dell&#39;indice si applica solo al tuo indice live; non è possibile pianificare gli indici di staging.

**Impostazione della pianificazione completa dell&#39;indice per un sito web live**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Schedule]**.
1. Nell’elenco a discesa **[!UICONTROL Time]** , seleziona l’ora in cui vuoi avviare l’indicizzazione completa.
1. Seleziona uno o più giorni da eseguire per l’indicizzazione completa.
1. Clic **[!UICONTROL Save Changes]**.

## Esecuzione di un indice completo di un sito web live o in staging {#task_F7FE04D8A1654A7787FCCA31B45EB42D}

È possibile utilizzare Indice completo per indicizzare tutte le pagine del sito web in esecuzione o in esecuzione. L’indicizzazione consente ai clienti di trovare più facilmente ciò che cercano o ciò di cui hanno bisogno quando eseguono una ricerca.

**Per eseguire un indice completo di un sito web live o in staging**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Index]**.

1. Imposta le opzioni di indicizzazione desiderate.

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
    <td colname="col2"> <p>Rimuove tutti i documenti dalla cache degli indici. </p> <p>Quando questa opzione è selezionata, ogni pagina del sito web viene scaricata dal server. Se questa impostazione è selezionata e disabilitata, l’account viene impostato per cancellare la cache ogni volta che viene eseguito un indice completo. Oppure, alcune impostazioni account precedentemente modificate ora richiedono un indice completo. </p> <p>Quando questa opzione è deselezionata, tutte le pagine indicizzate rimangono nell’indice fino a quando il server web non indica che la pagina non esiste più. Questa situazione è vera anche se i collegamenti a tale pagina vengono rimossi. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Rigenera in sospeso </p> </td> 
    <td colname="col2"> <p>Seleziona Se hai apportato modifiche alle impostazioni del tuo account che hanno modificato sostanzialmente il contenuto dell'indice. Le modifiche sostanziali includono l’apportare modifiche a uno dei seguenti elementi: 
    <ul id="ul_4EB8FF692FEB47BBB9A64D61299380D1"> 
    <li id="li_7CF8D286512F4210BEA3DB9F0EFA097A">Sinonimi </li> 
    <li id="li_8178ABC342BB4365B3927E20433756E3">Raccolte </li> 
    <li id="li_57C8BD06BFA64AFAA2C9EF2CC59520EF">Metadati </li> 
    <li id="li_C4B6A7DA023B4A43991D03EC592170C9">Parole escluse </li> 
    <li id="li_9E0AD4B6DDC24A5A8FB5C2C1CCD5348A">Lingua dell'account </li> 
    <li id="li_338F107547DF48AAA0EF90F4AD8664A5">Classifica </li> 
    <li id="li_7F49B86D94974E79AAD381A64A1400F2">Attivazione della ricerca con distinzione tra maiuscole e minuscole </li> 
    <li id="li_E8FE6EE240A840AC826ADF4294AAC6F6">Attivazione del supporto diacritico </li> 
    <li id="li_51763D482DCB4ED0972966F492B8C0F2">Attivazione dell’indicizzazione dei numeri </li> 
    </ul> </p> <p>Prima che venga effettuata un'altra ricerca per indicizzazione, viene eseguita una trasmissione rapida attraverso tutti i dati dell'indice per renderlo conforme alle nuove impostazioni dell'account. </p> <p>Questa opzione è disponibile solo se si sta utilizzando un indice completo di un sito web di staging. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Conteggio tutte le pagine </p> </td> 
    <td colname="col2"> <p>Consente di continuare la ricerca per indicizzazione delle pagine del sito web anche dopo il raggiungimento del limite di pagina dell’account. </p> <p>Ulteriori pagine non vengono aggiunte all’indice, ma puoi verificare il numero totale di documenti presenti sul sito web. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Full Index Now]**.
1. (Facoltativo) Se si sono verificati errori di indicizzazione, fai clic su **[!UICONTROL View Errors]** per visualizzare il registro associato.

## Visualizzazione dell&#39;intero registro dell&#39;indice di un sito web live o in staging {#task_02E5E944C56B4EB19CC1FF321F3221B8}

Al termine di un indice completo attivo o di un indice completo in staging, puoi visualizzare il registro associato per risolvere eventuali errori.

Non puoi esportare i registri né salvarli. Il registro rimane disponibile per la visualizzazione fino a quando non si verifica il nuovo indice.

**Per visualizzare l&#39;intero registro dell&#39;indice di un sito web live o in staging**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di log, in alto o in basso, effettua una delle seguenti operazioni:

   * Utilizza le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi all’interno del registro.

   * Utilizza le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare la visualizzazione.

