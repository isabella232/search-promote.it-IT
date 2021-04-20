---
description: Utilizzare le regole di pre-ricerca per analizzare la query in arrivo e determinare quale modello di presentazione utilizzare. Le regole di pre-ricerca vengono eseguite in sequenza per ogni query. Per modificare l’ordine delle regole, puoi utilizzare il trascinamento della selezione. L'ordine effettivo non cambia finché non viene salvato.
solution: Target
title: Informazioni sulle regole di pre-ricerca
topic: Rules,Site search and merchandising
uuid: e75f9d9e-e8ca-4184-bf79-b1fdadb5c0fe
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1666'
ht-degree: 1%

---


# Informazioni sulle regole di pre-ricerca{#about-pre-search-rules}

Utilizzare le regole di pre-ricerca per analizzare la query in arrivo e determinare quale modello di presentazione utilizzare. Le regole di pre-ricerca vengono eseguite in sequenza per ogni query. Per modificare l’ordine delle regole, puoi utilizzare il trascinamento della selezione. L&#39;ordine effettivo non cambia finché non viene salvato.

## Utilizzo delle regole di pre-ricerca {#concept_5BF84BB6FACB4645BA9CB7496A01CD1F}

Le regole di pre-ricerca vengono generalmente utilizzate per selezionare quale modello di presentazione visualizza i risultati in base alla query in arrivo. Le funzioni più avanzate possono essere utilizzate per modificare la query utilizzata per una ricerca eseguita per un modello di presentazione. Puoi aggiungere, eliminare o modificare il valore dei parametri di query in base alle esigenze. Per ogni query in arrivo, un modulo di pre-elaborazione esamina le regole di pre-ricerca per determinare se la query viene modificata e quale modello di presentazione viene utilizzato. Ogni regola di pre-ricerca è costituita da due elementi principali: le azioni della regola e le condizioni facoltative. È possibile specificare un numero illimitato di regole e condizioni. L&#39;ordine di queste regole è importante, perché il set di regole viene ripetuto per regola. Quando le condizioni di una regola vengono soddisfatte, vengono eseguite tutte le azioni associate.

Nel modulo Elaborazione pre-ricerca vengono create istanze di tutti i modelli definiti e delle relative ricerche con nome associate, dove a ogni ricerca viene assegnata una copia locale dei parametri cgi. Di conseguenza, è possibile personalizzare una ricerca aggiungendo, eliminando o modificando uno dei parametri cgi utilizzati dalla ricerca senza modificare altri parametri denominati utilizzati dal modello o senza influire su nessuno degli altri modelli. Di conseguenza, se si dispone di un modello di presentazione che visualizza più di un set di risultati, è possibile personalizzare ogni ricerca singolarmente. Se desideri eseguire modifiche ai parametri CGI globali prima che vengano copiati in ogni ricerca per ogni modello, utilizza il modulo Query Cleaning (Pulizia query).

## Condizioni regola di pre-ricerca {#section_B5568ADEB28546A280720309498B045D}

Le condizioni sono facoltative. Se scegli di specificare azioni per ogni query, le azioni vengono sempre eseguite. È considerata una best practice per la prima regola da eseguire per ogni query, in cui viene selezionato il modello di presentazione predefinito. In questo modo è possibile assicurarsi di aver selezionato un modello di presentazione dello scenario peggiore da utilizzare, indipendentemente dalla query in entrata. Le condizioni possono essere basate su qualsiasi parametro di query CGI, cookie o variabile personalizzata impostata da una regola precedente o da una variabile di sistema.

## Azioni regola di pre-ricerca {#section_3B8E19D287554C1C969F5B8D81226981}

Vengono esercitate tutte le azioni all’interno di una regola di pre-ricerca con condizioni corrispondenti. Le azioni sono in genere costituite da un’operazione, dai dati su cui eseguire l’operazione e dal valore da utilizzare. L’azione più semplice consiste nel specificare quale modello di presentazione utilizzare quando la query corrisponde alle condizioni della regola di pre-ricerca. Quindi, impostare il modello di destinazione sul nome del modello di presentazione. È possibile utilizzare azioni più complesse per modificare la ricerca utilizzata per un determinato modello eseguendo un’operazione sul parametro di ricerca di un modello. Quando si esegue un&#39;operazione sul parametro di ricerca di un modello, è necessario specificare un modello di presentazione ed eseguire una ricerca.

## Regole generiche {#section_885ECB9DBF0C4D539C14F82BCAA35B4E}

Quando si eseguono operazioni sul parametro di ricerca di un modello, esistono due valori speciali: *target e *primario rispettivamente per il modello di presentazione e la ricerca denominata. Con questi valori, puoi creare regole basate sulla ricerca primaria del modello di destinazione corrente. Questi costrutti consentono di creare regole generiche in cui non è necessario preoccuparsi della chiamata del modello di destinazione o della ricerca primaria corrente. Ovviamente, una regola di pre-ricerca precedente definisce il modello di destinazione corrente. In caso contrario, viene selezionato un modello di presentazione iniziale che produce risultati indesiderati.

## Esempi {#section_EA153A151987454EA44A4A6862466DF6}

Imposta il modello predefinito su guidato.tmpl quando l&#39;utente passa un parametro cgi denominato lang, impostato su una lingua nota, utilizza il modello di tale lingua.

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
* L’estrazione dei dati della query viene eseguita all’interno delle regole di pulizia delle query. Puoi fare riferimento a tali elementi nell’elaborazione di pre-ricerca.
* Aggiungi tutte le nuove variabili personalizzate introdotte nelle regole di pre-ricerca a una regola di pre-ricerca che viene eseguita per ogni query prima che altre regole di pre-ricerca le facciano riferimento.

## Aggiunta di una nuova regola di pre-ricerca {#task_182B95918462490D8BDA7F16A81CAC11}

È possibile utilizzare [!DNL Pre-Search Rules] per selezionare il modello di presentazione utilizzato per visualizzare i risultati della ricerca in base alla query in arrivo.

**Per aggiungere una nuova regola di pre-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Pre-Search Rules], fai clic su **[!UICONTROL Add New Rule]**.
1. Nel campo [!DNL Name] , digita il nome della nuova regola di pulizia delle query.
1. Nella pagina [!DNL Add Pre-Search Rule], utilizza gli elenchi a discesa e i campi di testo per creare la query.

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
      <td colname="col2"> <p>Un cookie HTTP. Il nome e i valori dei cookie devono essere codificati in Uniform Resource Identifier . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Variabile personalizzata </p> </td> 
      <td colname="col2"> <p>Variabile definita dall'utente. Aggiungi, elimina o imposta una quantità illimitata di variabili definite dall’utente. </p> <p>È possibile fare riferimento a qualsiasi variabile definita nel modulo Query Cleaning (Pulizia query) all'interno delle Regole di pre-ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Variabile di sistema </p> </td> 
      <td colname="col2"> <p>Variabili di sola lettura impostate dal sistema interno che è possibile controllare. Sono supportate le seguenti variabili di sistema: </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> hostname  </span> <p>Nome dell'host del server. </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri  </span> <p>L'URI richiesto senza la stringa di query. </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>L'intera stringa di query. </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> ambiente </span> <p>"Stage" o "live" a seconda che la query in arrivo sia stata inviata all’ambiente di staging o live. </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>URL di origine del cliente. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet </p> </td> 
      <td colname="col2"> <p>Parametri CGI speciali nella raccolta globale associati a un particolare facet. Tutti i parametri CGI vengono copiati in ogni ricerca denominata all’interno di un modello dopo Query Cleaning (Pulizia query). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro query </p> </td> 
      <td colname="col2"> <p>Parametro CGI nella raccolta globale. Questi parametri vengono copiati in ogni ricerca denominata all’interno di un modello dopo Query Cleaning (Pulizia query). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro di ricerca del modello </p> </td> 
      <td colname="col2"> <p>Un parametro CGI locale per una ricerca denominata associata a un modello di presentazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro back-end del modello </p> </td> 
      <td colname="col2"> <p>I parametri di query in arrivo vengono infine tradotti in parametri di backend utilizzati per eseguire la ricerca. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Parametri CGI di ricerca back-end </a>. </p> <p>I parametri di backend non vengono visualizzati sugli elementi di navigazione. Di conseguenza, puoi nascondere ai clienti eventuali parametri aggiuntivi da applicare a una ricerca. Il parametro è locale per una ricerca specifica all'interno di un modello di presentazione. Le azioni sui parametri di backend sono in ritardo di associazione; in altre parole, vengono applicate immediatamente prima dell’invio della ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Modello di destinazione </p> </td> 
      <td colname="col2"> <p>Un'istanza speciale di una variabile personalizzata definita dal sistema che non può essere eliminata. Questa variabile contiene il modello di presentazione di destinazione corrente. Puoi leggere o impostare questa variabile specificando la variabile personalizzata "target_template". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Classificazione </p> </td> 
      <td colname="col2"> <p>Consente di specificare la regola di classificazione da utilizzare nella ricerca. Questa opzione viene visualizzata solo quando sono stati definiti campi di classificazione e regole di classificazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Store </p> </td> 
      <td colname="col2"> <p>Il motore di ricerca rileva automaticamente in quale archivio si trova il cliente in base al nome host o al parametro di query <span class="codeph"> gs_store </span>, con quest'ultimo che ha la precedenza. È possibile creare condizioni al di fuori del negozio. Solo per la pulizia delle query, è inoltre possibile utilizzare un'azione per sovrascrivere l'archivio corrente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ultima regola </p> </td> 
      <td colname="col2"> <p>Quando questa opzione è selezionata, il modulo di elaborazione pre-ricerca non esegue alcuna regola aggiuntiva dopo l’azione della regola corrispondente. Questa azione è utile quando hai impostato azioni che fanno sì che una regola successiva corrisponda ma non desideri che venga eseguita la regola successiva. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sospendi </p> </td> 
      <td colname="col2"> <p>Disattiva l’esecuzione della regola ma non elimina la regola. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di una regola di pre-ricerca {#task_25F77050C5DA42B29DFD1C9718FB8C64}

Puoi modificare le regole di pre-ricerca esistenti aggiunte alla pagina [!DNL Pre-Search Rules] .

**Per modificare una regola di pre-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Pre-Search Rules], nella colonna **[!UICONTROL Actions]** della tabella, fare clic su **[!UICONTROL Edit]** per la regola associata che si desidera modificare.
1. Nella pagina [!DNL Edit Pre-Search Rule], utilizza gli elenchi a discesa e i campi di testo per creare la query.

   Vedi la tabella delle opzioni in [Aggiunta di una nuova regola di pre-ricerca](../c-about-rules-menu/c-about-pre-search-rules.md#task_182B95918462490D8BDA7F16A81CAC11).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una regola di pre-ricerca {#task_128B6A79CA6C451C991AEDAD58F51743}

È possibile eliminare le regole di pre-ricerca non più necessarie o utilizzate.

Quando elimini una regola, l&#39;ordine di esecuzione delle regole rimanenti viene regolato automaticamente per tenere conto dell&#39;eliminazione.

**Per eliminare una regola di pre-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Pre-Search Rules], nella colonna **[!UICONTROL Actions]** della tabella, fare clic su **[!UICONTROL Delete]** per la regola associata che si desidera eliminare.
1. Nella finestra di dialogo [!DNL Confirmation] fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica dell&#39;ordine di esecuzione delle regole di pre-ricerca {#task_C18817276A3C459089C97448076365D1}

È possibile riordinare le regole di pre-ricerca per modificare l&#39;ordine in cui vengono eseguite sui modelli di presentazione.

Le regole di pre-ricerca vengono eseguite nell’ordine in cui sono state definite. Più alto è il numero dell&#39;ordine di una regola, più tardi verrà eseguito nel processo, trumping delle regole precedenti. Per riordinare le regole, immetti un nuovo numero nella colonna Ordine della tabella nella pagina [!DNL Pre-Search Rules]. Puoi inoltre utilizzare le regole di trascinamento per modificarne l’ordine di esecuzione.

**Per modificare l’ordine di esecuzione delle regole di pre-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Pre-Search Rules] , effettua una delle seguenti operazioni:

   * Fai clic sull’intestazione di colonna **[!UICONTROL Order]** per ordinare le regole in ordine crescente o decrescente.
   * Nella colonna **[!UICONTROL Order]**, digitare il numero di ordine che si desidera eseguire nel campo di testo a sinistra del nome di una regola di pre-ricerca.
   * Trascinare una riga di tabella nella posizione in cui si desidera eseguire la regola. Tutti i numeri dell&#39;ordine vengono aggiornati per riflettere il nuovo ordine in cui vengono eseguite le regole.

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

