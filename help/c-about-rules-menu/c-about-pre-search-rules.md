---
description: Utilizzate Regole di pre-ricerca per analizzare la query in entrata e determinare quale modello di presentazione utilizzare. Le regole di pre-ricerca vengono eseguite in sequenza per ogni query. Per modificare l'ordine delle regole è possibile utilizzare il trascinamento della selezione. L'ordine effettivo non cambia finché non viene salvato.
seo-description: Utilizzate Regole di pre-ricerca per analizzare la query in entrata e determinare quale modello di presentazione utilizzare. Le regole di pre-ricerca vengono eseguite in sequenza per ogni query. Per modificare l'ordine delle regole è possibile utilizzare il trascinamento della selezione. L'ordine effettivo non cambia finché non viene salvato.
seo-title: Informazioni sulle regole di pre-ricerca
solution: Target
title: Informazioni sulle regole di pre-ricerca
topic: Rules,Site search and merchandising
uuid: e75f9d9e-e8ca-4184-bf79-b1fdadb5c0fe
translation-type: tm+mt
source-git-commit: d07cdc2c88f93eed4cecb0ee8818f7fdea06ee9d
workflow-type: tm+mt
source-wordcount: '1709'
ht-degree: 1%

---


# Informazioni sulle regole di pre-ricerca{#about-pre-search-rules}

Utilizzate Regole di pre-ricerca per analizzare la query in entrata e determinare quale modello di presentazione utilizzare. Le regole di pre-ricerca vengono eseguite in sequenza per ogni query. Per modificare l&#39;ordine delle regole è possibile utilizzare il trascinamento della selezione. L&#39;ordine effettivo non cambia finché non viene salvato.

## Utilizzo delle regole di pre-ricerca {#concept_5BF84BB6FACB4645BA9CB7496A01CD1F}

Le regole di pre-ricerca vengono in genere utilizzate per selezionare quale modello di presentazione visualizza i risultati in base alla query in entrata. Funzionalità più avanzate possono essere utilizzate per modificare la query utilizzata per una ricerca in corso per un modello di presentazione. È possibile aggiungere, eliminare o modificare il valore dei parametri di query in base alle esigenze. Per ogni query in entrata, un modulo di pre-elaborazione esamina le regole di pre-ricerca per determinare se la query viene modificata e quale modello di presentazione viene utilizzato. Ogni regola di pre-ricerca è composta da due elementi principali: le azioni della regola e le condizioni facoltative. È possibile specificare un numero illimitato di regole e condizioni. L&#39;ordine di queste regole è importante, perché il set di regole viene ripetuto a ciclo continuo per regola. Quando le condizioni di una regola vengono soddisfatte, vengono eseguite tutte le azioni associate.

Nel modulo Pre-Search Processing (Elaborazione pre-ricerca) vengono istanziati tutti i modelli definiti e le relative ricerche con nome, a cui viene assegnata una copia locale dei parametri cgi. Di conseguenza, potete personalizzare una ricerca aggiungendo, eliminando o modificando uno dei parametri cgi utilizzati dalla ricerca senza alterare altre ricerche denominate utilizzate dal modello né influenzare gli altri modelli. Di conseguenza, se disponete di un modello di presentazione che visualizza più set di risultati, potete personalizzare ogni ricerca singolarmente. Se si desidera apportare modifiche ai parametri CGI globali prima che vengano copiati in ogni ricerca per ciascun modello, utilizzare il modulo Pulizia query.

## Condizioni pre-ricerca regola {#section_B5568ADEB28546A280720309498B045D}

Le condizioni sono facoltative. Se si sceglie di specificare le azioni per ogni query, le azioni vengono sempre eseguite. È consigliabile che la prima regola venga eseguita per ogni query, in cui viene selezionato il modello di presentazione predefinito. In questo modo potete essere certi che, indipendentemente dalla query in entrata, avete selezionato un modello di presentazione con scenario peggiore da utilizzare. Le condizioni possono essere basate su qualsiasi parametro di query CGI, cookie o variabile personalizzata impostata da una regola precedente o da una variabile di sistema.

## Azioni regola di pre-ricerca {#section_3B8E19D287554C1C969F5B8D81226981}

Tutte le azioni all&#39;interno di una regola di pre-ricerca con condizioni corrispondenti vengono esercitate. Le azioni sono in genere costituite da un&#39;operazione, dai dati su cui eseguire l&#39;operazione e dal valore da utilizzare. L&#39;azione più semplice consiste nel specificare quale modello di presentazione utilizzare quando la query corrisponde alle condizioni della regola di pre-ricerca. Quindi impostate il modello di destinazione sul nome del modello di presentazione. Per modificare la ricerca utilizzata per un determinato modello è possibile utilizzare azioni più complesse, eseguendo un&#39;operazione sul parametro di ricerca di un modello. Quando eseguite un&#39;operazione sul parametro di ricerca di un modello, specificate un modello di presentazione ed effettuate una ricerca.

## Regole generiche {#section_885ECB9DBF0C4D539C14F82BCAA35B4E}

Quando si eseguono operazioni sui parametri di ricerca di un modello, esistono due valori speciali: *mirato e *primario rispettivamente per il modello di presentazione e la ricerca denominata. Con questi valori, puoi creare regole basate sulla ricerca primaria del modello di destinazione corrente. Questi costrutti consentono di creare regole generiche in cui non è necessario preoccuparsi di come vengono chiamati il modello di destinazione o la ricerca primaria corrente. Ovviamente, una regola di pre-ricerca precedente definisce il modello di destinazione corrente. In caso contrario, viene selezionato un modello di presentazione iniziale, che genera risultati indesiderati.

## Esempi {#section_EA153A151987454EA44A4A6862466DF6}

Impostate il modello predefinito su Guidata.tmpl, quando l&#39;utente passa un parametro cgi denominato lang, impostato su una lingua nota, utilizzate il modello di tale lingua.

```
    On condition: 
      Every Query 
    Perform the following actions: 
      Set targeted template to guided 
 
    On condition: 
      Query lang matches regular expression fr 
    Perform the following actions: 
      Set targeted template to guided_french 
 
    On condition: 
      Query lang matches regular expression de 
    Perform the following actions: 
      Set targeted template to guided_german
```

## Best practice {#section_31EBAE5E54174DEE8986CBB636746A98}

* La prima regola seleziona un modello predefinito per ogni query.
* L&#39;estrazione dei dati della query viene eseguita all&#39;interno delle regole di pulizia della query. Potete farvi riferimento nell’elaborazione di pre-ricerca.
* Aggiungete eventuali nuove variabili personalizzate introdotte nelle regole di pre-ricerca a una regola di pre-ricerca eseguita per ogni query prima che qualsiasi altra regola di pre-ricerca vi faccia riferimento.

## Aggiunta di una nuova regola di pre-ricerca {#task_182B95918462490D8BDA7F16A81CAC11}

Potete utilizzare [!DNL Pre-Search Rules] per selezionare il modello di presentazione utilizzato per visualizzare i risultati della ricerca in base alla query in entrata.

**Per aggiungere una nuova regola di pre-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Pre-Search Rules] fare clic su **[!UICONTROL Add New Rule]**.
1. Nel campo [!DNL Name] digitare il nome della nuova regola di pulizia della query.
1. Nella pagina [!DNL Add Pre-Search Rule], utilizzare gli elenchi a discesa e i campi di testo per creare la query.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Cookie </p> </td> 
      <td colname="col2"> <p>Un cookie HTTP. Il nome e i valori dei cookie devono essere Uniform Resource Identifier codificati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Variabile personalizzata </p> </td> 
      <td colname="col2"> <p>Variabile definita dall'utente. Aggiungete, eliminate o impostate una quantità illimitata di variabili definite dall’utente. </p> <p>È possibile fare riferimento a qualsiasi variabile definita nel modulo Query Cleaning (Pulizia query) all'interno delle Regole di pre-ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Variabile di sistema </p> </td> 
      <td colname="col2"> <p>Variabili di sola lettura impostate dal sistema interno che è possibile controllare. Sono supportate le seguenti variabili di sistema: </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> hostname  </span> <p>Nome dell'host del server. </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri  </span> <p>L'URI richiesto senza la stringa di query. </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>L'intera stringa di query. </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> ambiente </span> <p>"Stage" o "live" a seconda che la query in entrata sia stata inviata o meno all'ambiente in cui è stato eseguito lo stage o dal vivo. </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>L’URL dal quale proveniva il cliente. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet </p> </td> 
      <td colname="col2"> <p>Parametri CGI speciali nella raccolta globale associati a un particolare facet. Tutti i parametri CGI vengono copiati in ogni ricerca con nome all’interno di un modello dopo la pulizia delle query. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro query </p> </td> 
      <td colname="col2"> <p>Parametro CGI nella raccolta globale. Questi parametri vengono copiati in ogni ricerca con nome all’interno di un modello dopo la pulizia delle query. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro di ricerca del modello </p> </td> 
      <td colname="col2"> <p>Un parametro CGI locale per una ricerca con nome associata a un modello di presentazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro back-end del modello </p> </td> 
      <td colname="col2"> <p>I parametri di query in entrata vengono infine convertiti in parametri di back-end utilizzati per eseguire la ricerca. </p> <p>Vedere <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Parametri CGI di ricerca back-end </a>. </p> <p>I parametri di back-end non vengono visualizzati sugli elementi di navigazione. Di conseguenza, potete nascondere ai clienti eventuali parametri aggiuntivi da applicare a una ricerca. Il parametro è locale per una ricerca specifica all’interno di un modello di presentazione. Le azioni sui parametri di backend sono ritardate; in altre parole, vengono applicate subito prima dell’invio della ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Modello di destinazione </p> </td> 
      <td colname="col2"> <p>Un'istanza speciale di una variabile personalizzata definita dal sistema che non può essere eliminata. Questa variabile contiene il modello di presentazione con targeting corrente. Potete leggere o impostare questa variabile specificando la variabile personalizzata "target_template". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Classifica </p> </td> 
      <td colname="col2"> <p>Consente di specificare la regola di classificazione da utilizzare nella ricerca. Questa opzione viene visualizzata solo se sono stati definiti campi di classificazione e regole di classificazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Store </p> </td> 
      <td colname="col2"> <p>Il motore di ricerca rileva automaticamente in quale archivio si trova il cliente in base al nome host o al parametro di query <span class="codeph"> gs_store </span>, con quest'ultimo che ha la precedenza. È possibile creare condizioni fuori dal negozio. Solo per la pulizia delle query, potete anche utilizzare un'azione per ignorare lo store corrente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ultima regola </p> </td> 
      <td colname="col2"> <p>Se questa opzione è selezionata, il modulo di elaborazione pre-ricerca non esegue alcuna regola aggiuntiva dopo l'azione della regola corrispondente. Questa azione è utile quando sono state impostate azioni che fanno corrispondere una regola successiva ma non si desidera che venga eseguita la regola successiva. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sospendi </p> </td> 
      <td colname="col2"> <p>Disattiva l'esecuzione della regola ma non elimina la regola. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di una regola di pre-ricerca {#task_25F77050C5DA42B29DFD1C9718FB8C64}

È possibile modificare le regole di pre-ricerca esistenti aggiunte alla pagina [!DNL Pre-Search Rules].

**Per modificare una regola di pre-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Pre-Search Rules], nella colonna **[!UICONTROL Actions]** della tabella fare clic su **[!UICONTROL Edit]** per la regola associata da modificare.
1. Nella pagina [!DNL Edit Pre-Search Rule], utilizzare gli elenchi a discesa e i campi di testo per creare la query.

   Vedere la tabella delle opzioni in [Aggiunta di una nuova regola di pre-ricerca](../c-about-rules-menu/c-about-pre-search-rules.md#task_182B95918462490D8BDA7F16A81CAC11).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una regola di pre-ricerca {#task_128B6A79CA6C451C991AEDAD58F51743}

È possibile eliminare le regole di pre-ricerca che non sono più necessarie o che non sono più utilizzate.

Quando si elimina una regola, l&#39;ordine di esecuzione delle regole rimanenti viene modificato automaticamente per tenere conto dell&#39;eliminazione.

**Per eliminare una regola di pre-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Pre-Search Rules], nella colonna **[!UICONTROL Actions]** della tabella fare clic su **[!UICONTROL Delete]** per la regola associata da eliminare.
1. Nella finestra di dialogo [!DNL Confirmation], fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica dell&#39;ordine di esecuzione delle regole di pre-ricerca {#task_C18817276A3C459089C97448076365D1}

Potete riordinare le regole di pre-ricerca per modificare l&#39;ordine in cui vengono eseguite sui modelli di presentazione.

Le regole di pre-ricerca vengono eseguite nell&#39;ordine in cui sono state definite. Più alto è il numero dell&#39;ordine di una regola, più tardi verrà eseguito nel processo, trumping regole precedenti. Riordinare le regole immettendo un nuovo numero nella colonna Ordine della tabella nella pagina [!DNL Pre-Search Rules]. Potete anche utilizzare le regole di trascinamento per modificarne l&#39;ordine di esecuzione.

**Per modificare l&#39;ordine di esecuzione delle regole di pre-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Pre-Search Rules], effettuare una delle seguenti operazioni:

   * Fate clic sull&#39;intestazione della colonna **[!UICONTROL Order]** per ordinare le regole in ordine crescente o decrescente.
   * Nella colonna **[!UICONTROL Order]**, digitare il numero di ordine che si desidera eseguire nel campo di testo a sinistra del nome di una regola di pre-ricerca.
   * Trascinare una riga di tabella nella posizione in cui si desidera eseguire la regola. Tutti i numeri di ordine vengono aggiornati in base al nuovo ordine in cui vengono eseguite le regole.

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

