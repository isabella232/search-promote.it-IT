---
description: Utilizzare le regole di pulizia query per analizzare e modificare la query in entrata.
seo-description: Utilizzare le regole di pulizia query per analizzare e modificare la query in entrata.
seo-title: Informazioni sulle regole di pulizia delle query
solution: Target
title: Informazioni sulle regole di pulizia delle query
topic: Rules,Site search and merchandising
uuid: 683af81f-f7c0-45f8-9212-e5e7cb82ccca
translation-type: tm+mt
source-git-commit: d07cdc2c88f93eed4cecb0ee8818f7fdea06ee9d
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 0%

---


# Informazioni sulle regole di pulizia query{#about-query-cleaning-rules}

Utilizzare le regole di pulizia query per analizzare e modificare la query in entrata.

## Utilizzo delle regole di pulizia query {#concept_17F3CDDC3C8A4128AF092A82B777B86C}

Questa funzione viene spesso utilizzata per modificare il comportamento di ricerca/merchandising del sito. Ad esempio, potete impostare una ricerca vuota su una parola chiave popolare invece di una ricerca &quot;*&quot;, promuovendo così un prodotto popolare. Potete anche utilizzare le regole di pulizia delle query per eseguire un hit diretto, dove reindirizzate a un URL. Questo può essere particolarmente utile quando si rileva che qualcuno sta cercando uno SKU di prodotto e si desidera saltare la ricerca e reindirizzare alla pagina di quel prodotto. La pulizia delle query può anche minare la query e impostare variabili personalizzate che possono essere utilizzate nelle fasi di elaborazione successive. Le regole di pulizia delle query vengono eseguite in sequenza per ogni query. Per modificare l&#39;ordine delle regole è possibile utilizzare il trascinamento della selezione. L’ordine effettivo non viene modificato finché non lo salvate.

Le regole di pulizia query in un modulo di pulizia query vengono esaminate per determinare se è necessario modificare uno dei parametri di query o se è necessario impostare delle variabili personalizzate. Ogni regola di pulizia query è costituita da due elementi principali: le azioni della regola e le condizioni facoltative. È possibile specificare un numero illimitato di regole e condizioni. L&#39;ordine di queste regole è importante, in quanto la ricerca del sito/merchandising esegue cicli continui attraverso la regola set di regole per regola. Quando le condizioni di una regola corrispondono, vengono eseguite tutte le azioni associate.

Al termine della pulizia delle query, i parametri CGI risultanti vengono utilizzati in futuro. Tutte le variabili personalizzate impostate sono disponibili per l&#39;utilizzo in fasi successive del flusso di elaborazione. Per impostazione predefinita, il sistema rimuove automaticamente lo spazio vuoto iniziale e finale dal termine della query.

## Informazioni sulle condizioni di pulizia query {#section_BF6F25F94FED4DDEA8600D921EA43A66}

Le condizioni sono facoltative. Se si decide che le azioni vengono specificate per ogni query, vengono sempre eseguite. Le condizioni possono essere basate su qualsiasi parametro di query CGI, cookie esistente o variabile personalizzata impostata da una regola precedente. La prima regola di pulizia query viene considerata &quot;best practice&quot; per ogni query, in cui vengono definite e inizializzate tutte le variabili personalizzate che si intende utilizzare.

## Informazioni sulle azioni di pulizia delle query {#section_78F74A9B48DE484191CDA95F5B4E7154}

Tutte le azioni all&#39;interno di una regola di pulizia query con condizioni corrispondenti vengono esercitate. Le azioni sono in genere costituite da un&#39;operazione, dai dati su cui eseguire l&#39;operazione e dal valore da utilizzare.

Vedere la tabella delle opzioni in [Aggiunta di una regola di pulizia query](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54).

## Informazioni sui reindirizzamenti {#section_597481E6194440C0A7B9E6FC901A81C0}

L&#39;interfaccia Direct Hits consente di definire un set di reindirizzamenti in base al termine della query in arrivo. I reindirizzamenti all&#39;interno di Query Cleaning estendono questa idea. Tuttavia, i reindirizzamenti offrono una granularità più precisa quando si verifica un reindirizzamento specificando le condizioni e consentono di reindirizzare l’utente a un URL dinamico anziché a un URL statico. Quando selezionate l’azione di reindirizzamento, la riga viene aggiornata in modo da avere una casella di testo in cui specificare l’URL a cui desiderate reindirizzare. Nell’URL potete specificare variabili o parametri da sostituire racchiudendoli tra parentesi graffe. Le variabili personalizzate hanno una precedenza superiore rispetto ai parametri CGI nella sostituzione.

## Esempi {#section_DB5047CC38FB4A57B15CAAF9848073E3}

Si supponga di avere un negozio di abbigliamento con un sito web. Se l&#39;utente fa clic su Cerca senza alcun termine di ricerca, si desidera restituire una ricerca in base ai jeans, perché questo è ciò per cui si è conosciuti a livello internazionale. È inoltre necessario analizzare il termine di query per un genere in modo da poter creare una regola di pre-ricerca in un secondo momento, in base alla variabile personalizzata che utilizza un modello di presentazione diverso per ogni genere.

```
On condition: 
  query q equal 
Perform the following actions: 
  Set query parameter q to value jeans 
 
On condition: 
  Query q matches regular expression wom[e|a]n[s]|girl[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value female 
 
On condition: 
  Query q matches regular expression men[s]|boy[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value male
```

MegaElectronic è un grande negozio di elettronica. Dall&#39;analisi dei dati di ricerca, MegaElectronic ha notato che molti dei loro clienti esperti spesso cercano un prodotto utilizzando lo SKU del prodotto, piuttosto che restituire un risultato di ricerca per il singolo prodotto, MegaElectronic vorrebbe reindirizzare alla pagina web associata a tale SKU.

```
On condition: 
  query q matches regular expression ^\D\D\D-\d\d\d\d$ 
Perform the following actions: 
  redirect to https://www.megaelectronic.com/?sku={{q}}
```

## Aggiunta di una regola di pulizia query {#task_47F43988D3D9485F8AE1DFDA7E00BF54}

Potete definire regole per la pulizia o la modifica della query di ricerca in arrivo da un cliente.

È possibile selezionare solo i modelli attualmente esistenti. Se non avete alcun modello, dovete prima definirlo.

Vedere [Informazioni sui modelli](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**Aggiunta di una regola di pulizia query**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]** dal menu del prodotto.
1. Nella pagina [!DNL Query Cleaning Rules] fare clic su **[!UICONTROL Add New Rule]**.
1. Nel campo [!DNL Name] digitare il nome della nuova regola di pulizia della query.
1. Nella pagina [!DNL Add Query Cleaning Rule], utilizzare gli elenchi a discesa e i campi di testo per creare la query.

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
      <td colname="col2"> <p>Un cookie HTTP. Puoi definire le condizioni in base ai cookie associati al tuo dominio. In alternativa, potete impostare un cookie scritto con i risultati della ricerca in uscita. Il nome e i valori dei cookie devono essere Uniform Resource Identifier codificati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Variabile personalizzata </p> </td> 
      <td colname="col2"> <p>Variabile definita dall'utente. Aggiungete, eliminate o impostate una quantità illimitata di variabili definite dall’utente. Potete fare riferimento a qualsiasi variabile definita dall'utente qui in Regole di pre-ricerca e Regole post-ricerca. </p> </td> 
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
          <li id="li_6FEE352DB7A842FCB2EBE1398AD03666"> <span class="uicontrol"> user agent  </span> <p>Stringa "user-agent" del browser del cliente. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro query </p> </td> 
      <td colname="col2"> <p>Parametri CGI passati alla query. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro di backend </p> </td> 
      <td colname="col2"> <p>I parametri di query in entrata vengono infine convertiti in parametri di back-end utilizzati per eseguire la ricerca. </p> <p>Vedere <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Parametri CGI di ricerca back-end </a>. </p> <p>I parametri di back-end non vengono visualizzati sugli elementi di navigazione. Di conseguenza, potete nascondere ai clienti eventuali parametri aggiuntivi da applicare a una ricerca. Le azioni sui parametri di backend sono ritardate; in altre parole, vengono applicate subito prima dell’invio della ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet </p> </td> 
      <td colname="col2"> <p>Parametri CGI speciali associati a un dato facet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Classifica </p> </td> 
      <td colname="col2"> <p>Consente di specificare la regola di classificazione da utilizzare nella ricerca. Questa opzione viene visualizzata solo se sono stati definiti alcuni campi e regole di classificazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Store </p> </td> 
      <td colname="col2"> <p>Il motore di ricerca rileva automaticamente in quale archivio si trova l'utente in base al nome host o al parametro di query <span class="codeph"> gs_store </span>, con quest'ultimo che ha la precedenza. È possibile creare condizioni fuori dal negozio. Solo per la pulizia delle query, potete anche utilizzare un'azione per ignorare lo store corrente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ultima regola </p> </td> 
      <td colname="col2"> <p>Quando vengono soddisfatte le condizioni per una regola con l'ultima regola impostata, il modulo di elaborazione pulizia query non esegue alcuna regola aggiuntiva dopo l'azione della regola corrispondente. Questa funzione è utile quando sono state impostate azioni che causano la corrispondenza di una regola successiva ma non si desidera attivare la regola successiva. Notate che, se l'azione di una regola è di eseguire un reindirizzamento, il reindirizzamento ha luogo immediatamente, quindi sostanzialmente agisce come se fosse stata impostata l'ultima regola. </p> </td> 
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

## Modifica di una regola di pulizia query {#task_FA2FF1A7E2634350AD703485CBC27CB3}

È possibile modificare le regole di pulizia query esistenti aggiunte alla pagina Regole di pulizia query.

**Per modificare una regola di pulizia query**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]** dal menu del prodotto.
1. Nella pagina [!DNL Query Cleaning Rules], nella colonna **[!UICONTROL Actions]** della tabella fare clic su **[!UICONTROL Edit]** per la regola associata da modificare.
1. Nella pagina [!DNL Edit Query Cleaning Rule], utilizzare gli elenchi a discesa e i campi di testo per creare la query.

   Vedere la tabella delle opzioni in [Aggiunta di una regola di pulizia query](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una regola di pulizia query {#task_C52D17226B824590B087CAB6970CBB01}

È possibile eliminare le regole di pulizia query non più necessarie o utilizzate.

Quando si elimina una regola, l&#39;ordine di esecuzione delle regole rimanenti viene modificato automaticamente per tenere conto dell&#39;eliminazione.

**Per eliminare una regola di pulizia query**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]** dal menu del prodotto.
1. Nella pagina [!DNL Query Cleaning Rules], nella colonna **[!UICONTROL Actions]** della tabella fare clic su **[!UICONTROL Delete]** per la regola associata da eliminare.
1. Nella finestra di dialogo [!DNL Confirmation], fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica dell&#39;ordine di esecuzione delle regole di pulizia della query {#task_C24012C45A4445468A7FD998017388CA}

Potete riordinare le regole di pulizia delle query per modificare l&#39;ordine in cui vengono eseguite sui modelli di presentazione.

Le regole di pulizia delle query vengono eseguite nell&#39;ordine in cui sono state definite. Più alto è il numero dell&#39;ordine di una regola, più tardi verrà eseguito nel processo, trumping regole precedenti. Riordinare le regole immettendo un nuovo numero nella colonna Ordine della tabella nella pagina [!DNL Query Cleaning Rules]. Potete anche utilizzare le regole di trascinamento per modificarne l&#39;ordine di esecuzione.

**Per modificare l&#39;ordine di esecuzione delle regole di pulizia della query**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]** dal menu del prodotto.
1. Nella pagina [!DNL Query Cleaning Rules], effettuare una delle seguenti operazioni:

   * Fate clic sull&#39;intestazione della colonna [!DNL Order] per ordinare le regole in ordine crescente o decrescente.
   * Nella colonna [!DNL Order], nel campo di testo a sinistra del nome di una regola di pulizia query, digitare il numero di ordine che si desidera eseguire.
   * Trascinare una riga di tabella nella posizione in cui si desidera eseguire la regola. Tutti i numeri di ordine vengono aggiornati in base al nuovo ordine in cui vengono eseguite le regole.

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

