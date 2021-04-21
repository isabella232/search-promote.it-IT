---
description: Visualizzazioni dati mostra i risultati della ricerca con i campi meta. Ogni colonna è un campo meta e ogni riga è il risultato di una query di ricerca. Personalizza visualizzazioni dati scegliendo e ridisponendo le colonne. Le visualizzazioni dati possono anche avere titoli e descrizioni personalizzati.
solution: Target
title: Informazioni sulle visualizzazioni dati
topic-legacy: Reports,Site search and merchandising
uuid: 18930551-960d-40c2-b5b7-0807a2e11134
exl-id: 9ef5eaef-85d6-41e9-af44-b4775755e5bf
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 1%

---

# Informazioni sulle visualizzazioni dati{#about-data-views}

Visualizzazioni dati mostra i risultati della ricerca con i campi meta. Ogni colonna è un campo meta e ogni riga è il risultato di una query di ricerca. Personalizza visualizzazioni dati scegliendo e ridisponendo le colonne. Le visualizzazioni dati possono anche avere titoli e descrizioni personalizzati.

## Utilizzo delle visualizzazioni dati {#concept_DCA897D074464BC1861AA47B40CC86C3}

Ogni account ha la comodità di creare più visualizzazioni dati. Utilizza la pagina Visualizzazioni dati per creare e modificare queste visualizzazioni dati.

Dopo aver aggiunto una visualizzazione dati, è necessario modificarla per configurarla e personalizzarla.

Vedere [Modifica di una visualizzazione dati](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

È possibile copiare una visualizzazione dati esistente da utilizzare come base per la creazione di una nuova visualizzazione dati.

Vedere [Copia di una visualizzazione dati](../c-about-reports-menu/c-about-data-views.md#task_78D4C2799BC84677843ED4CA1CD205AF).

## Aggiunta di una visualizzazione dati {#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D}

È possibile aggiungere una visualizzazione dati alla pagina [!DNL Data Views] per visualizzare i valori di ciascun campo meta con una query di ricerca.

Dopo aver aggiunto una visualizzazione dati, è necessario modificarla per configurarla e personalizzarla.

Vedere [Modifica di una visualizzazione dati](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

**Aggiunta di una visualizzazione dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Nella pagina [!DNL Data Views], fai clic su **[!UICONTROL Add New Data View]**.
1. Nella finestra di dialogo [!DNL Add New Data View], immettere il nome della visualizzazione dati da creare nel campo [!DNL Title].
1. Clic **[!UICONTROL Add]**.

## Modifica di una visualizzazione dati {#task_258A367896C24DD498C755925EA8F516}

Quando si aggiunge una visualizzazione dati alla pagina [!DNL Data Views], è possibile utilizzare Modifica per modificare il nome e la descrizione della visualizzazione dati o per spostare, visualizzare o nascondere la visualizzazione di ciascun campo metadati.

È inoltre possibile bloccare o sbloccare una visualizzazione dati selezionata.

Vedere [Aggiunta di una visualizzazione dati](../c-about-reports-menu/c-about-data-views.md#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D).

**Per modificare una visualizzazione dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Nella pagina [!DNL Data Views] della colonna [!DNL Actions] della tabella fare clic su **[!UICONTROL Edit]** nella riga con la visualizzazione dati che si desidera modificare.
1. Nella pagina [!DNL Data Views Editor] , imposta le opzioni desiderate.

   L’Editor visualizzazione dati dispone di tutti i controlli per nascondere, visualizzare e spostare le colonne dei campi nella pagina Visualizzazione dati.

   Quando visualizzi una visualizzazione dati, la tabella risultante mostra anche i seguenti campi di colonna aggiuntivi non modificabili: Classifica, pertinenza e punteggio (nel complesso). Questi tre campi speciali rappresentano i punteggi di rilevanza, i punteggi di classifica e i punteggi complessivi per ciascun risultato.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Titolo </p> </td> 
      <td colname="col2"> <p>Nome della visualizzazione dati. Il nome viene visualizzato in alto a destra quando si visualizza la visualizzazione dati. </p> <p>Vedere <a href="../c-about-reports-menu/c-about-data-views.md#task_FD0D2CE53DF84CBD9220AD7CA920011F" type="task" format="dita" scope="local"> Visualizzazione di una visualizzazione dati</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Descrizione </p> </td> 
      <td colname="col2"> <p>(Facoltativo) Contiene una descrizione della visualizzazione dati. La descrizione viene visualizzata tra il nome del titolo della visualizzazione dati e il campo di testo <span class="wintitle"> Nuova ricerca</span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametri di ricerca </p> </td> 
      <td colname="col2"> <p>Consente di specificare i parametri di ricerca predefiniti. Quando la visualizzazione dati viene visualizzata per la prima volta, questi parametri CGI vengono aggiunti automaticamente. </p> <p>Non modificare o eliminare <span class="codeph"> sp_cs</span> o <span class="codeph"> sp_f</span>. Questi parametri sono essenziali per la visualizzazione dati indipendentemente dal set di caratteri preferito dell’account. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Parametri CGI di ricerca back-end</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Stato blocco </p> </td> 
      <td colname="col2"> <p>Consente di bloccare o sbloccare la visualizzazione dati. </p> <p>È possibile visualizzare una visualizzazione dati bloccata solo con una password e un nome utente. L'utente deve essere un membro corrente dell'account. </p> <p>È possibile accedere a una visualizzazione dati sbloccata senza password o account utente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ordine </p> </td> 
      <td colname="col2"> <p> Consente di modificare l'ordine delle colonne modificando il numero nella casella di testo <span class="wintitle"> Ordine</span>. Puoi anche trascinare una riga per modificare l’ordine delle colonne. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi </p> </td> 
      <td colname="col2"> <p> Consente di attivare o disattivare la visualizzazione della colonna. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visualizza URL come immagine </p> </td> 
      <td colname="col2"> <p>Visualizza miniature e immagini in questa colonna se il risultato della ricerca per questa colonna restituisce un URL. </p> <p>L'URL viene rimosso dal nome o dal protocollo dello schema prima di diventare un valore dell'attributo <span class="codeph"> src</span> di un tag immagine. </p> <p>Se il risultato della ricerca di ritorno non assomiglia a un URL di un'immagine, viene visualizzato un . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lunghezza campo </p> </td> 
      <td colname="col2"> <p>Imposta il numero di caratteri visualizzati come risultato nella visualizzazione dati. </p> <p>Il valore predefinito è 100 caratteri. </p> <p>Alcuni campi, come il punteggio di classificazione e il campo data, non dispongono di lunghezze di campo regolabili. </p> </td> 
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

## Copia di una visualizzazione dati {#task_78D4C2799BC84677843ED4CA1CD205AF}

Puoi copiare una visualizzazione dati esistente nella pagina [!DNL Data Views] da utilizzare come base per la creazione di una nuova visualizzazione dati.

Dopo aver copiato una visualizzazione dati, puoi personalizzarla ulteriormente modificando la visualizzazione.

Vedere [Modifica di una visualizzazione dati](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

**Per copiare una visualizzazione dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Nella pagina [!DNL Data Views] della colonna [!DNL Actions] della tabella fare clic su **[!UICONTROL Copy]** nella riga con la visualizzazione dati da copiare.
1. Nella pagina [!DNL Copy Data View] del campo di testo [!DNL New Title] immettere il nuovo nome che si desidera assegnare alla visualizzazione dati.
1. Clic **[!UICONTROL Copy]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una visualizzazione dati {#task_61C32F8F00A549A5A3E7EDDA6F537098}

È possibile eliminare una visualizzazione dati sulla pagina [!DNL Data Views] che non è più necessaria o utilizzata.

**Eliminazione di una visualizzazione dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Nella pagina [!DNL Data Views] della colonna [!DNL Actions] della tabella fare clic su **[!UICONTROL Delete]** nella riga con la visualizzazione dati da rimuovere.
1. Nella pagina [!DNL Delete Data View], fai clic su **Elimina**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Visualizzazione di una visualizzazione dati {#task_FD0D2CE53DF84CBD9220AD7CA920011F}

Puoi utilizzare [!DNL View] nella pagina [!DNL Data Views] per visualizzare una visualizzazione dati selezionata.

La visualizzazione dati selezionata viene aperta in una finestra separata del browser.

**Visualizzazione di una visualizzazione dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Effettua una delle seguenti operazioni:

   * Nella colonna [!DNL Title] della tabella della pagina [!DNL Data Views] fare clic sul nome di una visualizzazione dati che si desidera aprire.

   * Nella pagina [!DNL Data Views] della colonna [!DNL Actions] della tabella fare clic su **[!UICONTROL View]** nella riga con la visualizzazione dati che si desidera aprire.
