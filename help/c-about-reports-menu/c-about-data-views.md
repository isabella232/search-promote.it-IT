---
description: Visualizzazioni dati mostra i risultati della ricerca con i campi meta. Ogni colonna è un campo meta e ogni riga è il risultato di una query di ricerca. Personalizzare le visualizzazioni dati scegliendo e ridisponendo le colonne. Le visualizzazioni dati possono anche avere titoli e descrizioni personalizzati.
seo-description: Visualizzazioni dati mostra i risultati della ricerca con i campi meta. Ogni colonna è un campo meta e ogni riga è il risultato di una query di ricerca. Personalizzare le visualizzazioni dati scegliendo e ridisponendo le colonne. Le visualizzazioni dati possono anche avere titoli e descrizioni personalizzati.
seo-title: Informazioni sulle visualizzazioni dati
solution: Target
title: Informazioni sulle visualizzazioni dati
topic: Reports,Site search and merchandising
uuid: 18930551-960d-40c2-b5b7-0807a2e11134
translation-type: tm+mt
source-git-commit: 7af85dd37f06fe506e5f57e28a25385ca7ab3db5

---


# Informazioni sulle visualizzazioni dati{#about-data-views}

Visualizzazioni dati mostra i risultati della ricerca con i campi meta. Ogni colonna è un campo meta e ogni riga è il risultato di una query di ricerca. Personalizzare le visualizzazioni dati scegliendo e ridisponendo le colonne. Le visualizzazioni dati possono anche avere titoli e descrizioni personalizzati.

## Uso delle visualizzazioni dati {#concept_DCA897D074464BC1861AA47B40CC86C3}

Ogni account ha la convenienza di creare più viste dati. Utilizzare la pagina Visualizzazioni dati per creare e modificare tali viste dati.

Dopo aver aggiunto una visualizzazione dati, è necessario modificarla per configurare e personalizzare la visualizzazione.

Vedere [Modifica di una visualizzazione](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516)dati.

È possibile copiare una visualizzazione dati esistente da utilizzare come base per la creazione di una nuova visualizzazione dati.

Vedere [Copia di una visualizzazione](../c-about-reports-menu/c-about-data-views.md#task_78D4C2799BC84677843ED4CA1CD205AF)dati.

## Aggiunta di una visualizzazione dati {#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D}

È possibile aggiungere una visualizzazione dati alla [!DNL Data Views] pagina per visualizzare i valori di ciascun campo meta con una query di ricerca.

Dopo aver aggiunto una visualizzazione dati, è necessario modificarla per configurare e personalizzare la visualizzazione.

Vedere [Modifica di una visualizzazione](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516)dati.

**Aggiunta di una visualizzazione dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Sulla [!DNL Data Views] pagina, fate clic su **[!UICONTROL Add New Data View]**.
1. Nella finestra di [!DNL Add New Data View] dialogo, nel [!DNL Title] campo immettere il nome della visualizzazione dati che si desidera creare.
1. Clic **[!UICONTROL Add]**.

## Modifica di una visualizzazione dati {#task_258A367896C24DD498C755925EA8F516}

Quando si aggiunge una visualizzazione dati alla [!DNL Data Views] pagina, è possibile utilizzare Modifica per modificare il nome e la descrizione della visualizzazione dati o per spostare, visualizzare o nascondere la visualizzazione di ciascun campo meta.

È inoltre possibile bloccare o sbloccare una visualizzazione dati selezionata.

Vedere [Aggiunta di una visualizzazione](../c-about-reports-menu/c-about-data-views.md#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D)dati.

**Per modificare una visualizzazione dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Nella [!DNL Data Views] pagina, nella [!DNL Actions] colonna della tabella, fare clic **[!UICONTROL Edit]** nella riga con la visualizzazione dati che si desidera modificare.
1. Nella [!DNL Data Views Editor] pagina, impostate le opzioni desiderate.

   L&#39;Editor visualizzazione dati dispone di tutti i controlli per nascondere, visualizzare e spostare le colonne dei campi nella pagina Visualizzazione dati.

   Quando si visualizza una visualizzazione dati, la tabella risultante mostra anche i seguenti campi di colonna aggiuntivi, che non sono modificabili: Classificazione, rilevanza e punteggio (nel complesso). Questi tre campi speciali rappresentano i punteggi di rilevanza, i punteggi di classifica e i punteggi complessivi per ciascun risultato.

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
      <td colname="col2"> <p>Nome della visualizzazione dati. Il nome viene visualizzato in alto a destra quando si visualizza la visualizzazione dati. </p> <p>Vedere <a href="../c-about-reports-menu/c-about-data-views.md#task_FD0D2CE53DF84CBD9220AD7CA920011F" type="task" format="dita" scope="local"> Visualizzazione di una visualizzazione</a>dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Descrizione </p> </td> 
      <td colname="col2"> <p>(Facoltativo) Contiene una descrizione della visualizzazione dati. La descrizione viene visualizzata tra il nome del titolo della visualizzazione dati e il campo di testo <span class="wintitle"> Nuova ricerca</span> . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametri di ricerca </p> </td> 
      <td colname="col2"> <p>Consente di specificare i parametri di ricerca predefiniti. Quando la visualizzazione dei dati viene visualizzata per la prima volta, questi parametri CGI vengono aggiunti automaticamente. </p> <p>Non modificare né eliminare <span class="codeph"> sp_cs</span> o <span class="codeph"> sp_f</span>. Questi parametri sono essenziali per la visualizzazione dati, indipendentemente dal set di caratteri preferito dall'account. </p> <p>Consultate <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Blocca stato </p> </td> 
      <td colname="col2"> <p>Consente di bloccare o sbloccare la visualizzazione dati. </p> <p>È possibile visualizzare una visualizzazione di dati bloccata solo con una password e un nome utente. L'utente deve essere un membro corrente dell'account. </p> <p>È possibile accedere a una visualizzazione dati sbloccata senza una password o un account utente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ordine </p> </td> 
      <td colname="col2"> <p> Consente di modificare l'ordine delle colonne modificando il numero nella casella di testo <span class="wintitle"> Ordine</span> . È inoltre possibile trascinare una riga per modificare l'ordine delle colonne. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi </p> </td> 
      <td colname="col2"> <p> Consente di attivare o disattivare la visualizzazione della colonna. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visualizza URL come immagine </p> </td> 
      <td colname="col2"> <p>Visualizzare miniature e immagini in questa colonna se il risultato della ricerca per questa colonna restituisce un URL. </p> <p>L'URL viene rimosso dal nome o dal protocollo dello schema prima di diventare un valore dell'attributo <span class="codeph"> src</span> di un tag immagine. </p> <p>Se il risultato della ricerca di ritorno non ha l’aspetto di un URL per un’immagine, viene visualizzato un messaggio. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lunghezza campo </p> </td> 
      <td colname="col2"> <p>Imposta il numero di caratteri visualizzati come risultato nella visualizzazione dati. </p> <p>Il valore predefinito è 100 caratteri. </p> <p>Alcuni campi, come la valutazione della classifica e il campo data, non dispongono di lunghezze di campo regolabili. </p> </td> 
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

## Copia di una visualizzazione dati {#task_78D4C2799BC84677843ED4CA1CD205AF}

È possibile copiare una visualizzazione dati esistente sulla [!DNL Data Views] pagina da utilizzare come base per la creazione di una nuova visualizzazione dati.

Dopo aver copiato una visualizzazione dati, potete personalizzarla ulteriormente modificando la visualizzazione.

Vedere [Modifica di una visualizzazione](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516)dati.

**Per copiare una visualizzazione dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Nella [!DNL Data Views] pagina, nella [!DNL Actions] colonna della tabella, fare clic **[!UICONTROL Copy]** nella riga con la visualizzazione dati che si desidera copiare.
1. Nella [!DNL Copy Data View] pagina, nel campo di [!DNL New Title] testo, immettere il nuovo nome che si desidera assegnare alla visualizzazione dati.
1. Clic **[!UICONTROL Copy]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di una visualizzazione dati {#task_61C32F8F00A549A5A3E7EDDA6F537098}

È possibile eliminare una visualizzazione dati sulla [!DNL Data Views] pagina che non è più necessaria o che non è più utilizzata.

**Per eliminare una visualizzazione dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Nella [!DNL Data Views] pagina, nella [!DNL Actions] colonna della tabella, fare clic **[!UICONTROL Delete]** nella riga con la visualizzazione dati che si desidera rimuovere.
1. Nella [!DNL Delete Data View] pagina, fate clic su **Elimina**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Visualizzazione di una visualizzazione dati {#task_FD0D2CE53DF84CBD9220AD7CA920011F}

È possibile utilizzare [!DNL View] sulla [!DNL Data Views] pagina per visualizzare una visualizzazione dati selezionata.

La visualizzazione dati selezionata viene aperta in una finestra browser separata.

**Visualizzazione di dati**

1. Scegliere **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** dal menu del prodotto.
1. Effettuate una delle seguenti operazioni:

   * Nella [!DNL Data Views] pagina, nella [!DNL Title] colonna della tabella, fare clic sul nome di una visualizzazione dati che si desidera aprire.

   * Nella [!DNL Data Views] pagina, nella [!DNL Actions] colonna della tabella, fare clic **[!UICONTROL View]** nella riga con la visualizzazione dati che si desidera aprire.

