---
description: Potete utilizzare le regole di post-ricerca per esaminare i risultati di una ricerca e determinare in che modo la ricerca influisce sul contenuto visualizzato.
seo-description: Potete utilizzare le regole di post-ricerca per esaminare i risultati di una ricerca e determinare in che modo la ricerca influisce sul contenuto visualizzato.
seo-title: Informazioni sulle regole post-ricerca
solution: Target
title: Informazioni sulle regole post-ricerca
topic: Rules,Site search and merchandising
uuid: 312d1e4a-f5b6-4629-8645-17e6f6c09fc4
translation-type: tm+mt
source-git-commit: d07cdc2c88f93eed4cecb0ee8818f7fdea06ee9d
workflow-type: tm+mt
source-wordcount: '2121'
ht-degree: 0%

---


# Informazioni sulle regole post-ricerca{#about-post-search-rules}

Potete utilizzare le regole di post-ricerca per esaminare i risultati di una ricerca e determinare in che modo la ricerca influisce sul contenuto visualizzato.

## Utilizzo delle regole post-ricerca {#concept_AF6ADFCC0ADF4A788003964939917FDE}

Se una ricerca non ha risultati, una regola di post-ricerca può eseguire una ricerca per un elemento simile. Oppure, può visualizzare una pagina Web che raccomanda altri elementi ai clienti che cercano l’elemento che non è stato trovato.

Ogni regola post-ricerca è composta da due elementi principali: le azioni della regola e le relative condizioni facoltative. È possibile specificare un numero illimitato di regole e condizioni. L&#39;ordine di queste regole è importante perché il set di regole viene ripetuto a ciclo continuo, regola per regola. Quando le condizioni di una regola corrispondono, vengono eseguite tutte le azioni associate.

Potete definire il set di risultati della ricerca per un massimo di tre cicli di ricerca. In seguito, viene utilizzato tutto ciò che è attualmente disponibile. Questo limite previene cicli infiniti e garantisce che il cliente riceva una risposta efficiente. Più volte si ripristina una ricerca più tempo è necessario per restituire i risultati della ricerca. Se nessuna delle regole di corrispondenza modifica una delle ricerche per il modello di presentazione attualmente utilizzato o cambia il modello, il set di risultati di ricerca viene considerato completato e le uscite di post-ricerca.

L&#39;elaborazione post-ricerca si basa sui moduli di elaborazione precedenti, ovvero Pulizia query ed elaborazione pre-ricerca. Di conseguenza, tutte le variabili personalizzate impostate in tali moduli sono disponibili per l&#39;uso nelle regole di elaborazione post-ricerca. Analogamente, l’elaborazione di pre-ricerca ha creato un’istanza di tutti i modelli in cui ogni ricerca denominata associata al modello di presentazione ha una propria copia locale dei parametri CGI. A sua volta, potete personalizzare ogni ricerca singolarmente.

Vedere [Informazioni sulle regole di pulizia delle query](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C).

Vedere [Informazioni sulle regole di pre-ricerca](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

## Informazioni sulle condizioni della regola post-ricerca {#section_C43EB77CC0AC43B8B9D38569264BF1B5}

Le condizioni sono facoltative. Se si specifica che le azioni vengono specificate per ogni query, le azioni vengono sempre eseguite. Potete basare le condizioni su qualsiasi parametro di query CGI, cookie, risultato della ricerca o variabile personalizzata impostata da una regola precedente. In alternativa, potete basarlo su una condizione di sistema, ad esempio quale sia il modello attualmente selezionato o se si tratta dell&#39;ultima ricerca. Quando create una condizione sui risultati di una ricerca o di un parametro CGI, specificate il modello e il nome della ricerca.

## Informazioni sulle azioni della regola post-ricerca {#section_0E15FE683A894ECAAA386267EEC7F7C5}

Vengono esercitate tutte le azioni di una regola post-ricerca con condizioni corrispondenti. Le azioni sono in genere costituite da un&#39;operazione, dai dati su cui eseguire l&#39;operazione e dal valore da utilizzare. L&#39;azione più semplice consiste nel cambiare il modello di presentazione da utilizzare in base alle condizioni della regola di post-ricerca. Potete utilizzare azioni più avanzate per modificare i parametri di una ricerca che determina la ripetizione della ricerca. Quando eseguite un&#39;operazione sul parametro di ricerca di un modello, specificate un modello di presentazione ed effettuate una ricerca.

## Regole generali {#section_AEE923988CC748FF9DEF2233FBF333B5}

Quando si eseguono operazioni sul parametro di ricerca di un modello, esistono due valori speciali, *target e *primario rispettivamente per il modello Presentazione e la ricerca con nome. Utilizzate questi valori per creare regole basate sulla ricerca primaria del modello di destinazione corrente. Questi costrutti consentono di creare regole generiche in cui non è necessario preoccuparsi della denominazione del modello di destinazione o della ricerca primaria corrente. Se questa passata è la prima attraverso l&#39;elaborazione post-ricerca, il modello di destinazione è qualsiasi cosa che l&#39;elaborazione pre-ricerca lo imposta.

## Reindirizza {#section_E5669A2F13C240F2968E31C75591CD6A}

Gli hit diretti e i reindirizzamenti all&#39;interno di Query Cleaning (Pulizia query) consentono di reindirizzare a un URL in base ai termini di ricerca in entrata. I reindirizzamenti all&#39;interno delle regole di post-ricerca estendono questa idea, con la differenza che consente di controllare quanti risultati sono stati restituiti dalla ricerca prima di decidere se si desidera eseguire un reindirizzamento. Con le regole post-ricerca, potete reindirizzare a un URL, dove potete sostituire variabili personalizzate o parametri di query. In alternativa, è possibile reindirizzare a un campo all&#39;interno del primo risultato. Quando si effettua il reindirizzamento al campo di un risultato, si definisce il campo nel modello Trasporto e deve contenere un URL valido ed esplicito, altrimenti il reindirizzamento viene ignorato.

Quando si utilizza il meccanismo di reindirizzamento all&#39;interno delle regole di post-ricerca, è possibile rilevare quando una ricerca restituisce un singolo risultato. Anziché restituire tale risultato, potete effettuare il reindirizzamento alla pagina Web associata al risultato.

Per un esempio di utilizzo dei reindirizzamenti con le regole di post-ricerca, consultate l&#39;esempio di reindirizzamento riportato di seguito.

## Ultima regola {#section_FC1E0050C9324278B171038E98F6C335}

Quando vengono soddisfatte le condizioni per una regola con l&#39;opzione **[!UICONTROL Last Rule]** impostata, il modulo di elaborazione post ricerca non esegue alcuna regola aggiuntiva dopo l&#39;azione della regola corrispondente. Questa situazione è utile quando sono state impostate azioni che determinano la corrispondenza di una regola successiva ma si desidera che l’elaborazione venga interrotta. E affinché quella regola successiva possa potenzialmente corrispondere dopo il successivo ciclo di ricerca.

## Esempi {#section_DDB98383690941F9B44AD00FBA55BB56}

Nell&#39;esempio seguente, si supponga di disporre di due modelli di presentazione. Un modello viene utilizzato per visualizzare molti risultati di ricerca e l&#39;altro modello viene utilizzato per visualizzare un singolo risultato e una ricerca aggiuntiva per gli accessori relativi alla ricerca principale. Desiderate rilevare i casi in cui disponete di un singolo risultato e passare all’altro modello di presentazione. Per eseguire questa attività, potete utilizzare le seguenti regole:

```
On condition: 
  targeted template is default 
  targeted template primary results equal 1 
  not last search 
Perform the following actions: 
  Set targeted template to product_spotlight
```

MegaElectronic è un grande negozio di elettronica. Dopo aver analizzato i dati di ricerca, MegaElectronic nota che molti dei loro clienti eseguono una ricerca di prodotto utilizzando il numero di parte di un prodotto. In tali casi, MegaElectronic vuole reindirizzare alla pagina Web associata al prodotto, se il cliente lo ha cercato direttamente e solo un singolo prodotto è stato trovato.

Per ottenere questo risultato, è possibile utilizzare una singola regola con tre condizioni. La prima condizione verifica che la ricerca restituita abbia un solo risultato. La seconda condizione assicura che il termine della query corrisponda al formato del numero parte di MegaElectronic per i risultati che desiderano causare il reindirizzamento. La terza condizione assicura che il cliente non abbia utilizzato facet per espandere un risultato, dato che il numero parte potrebbe essere un numero parte e restituire più di un risultato. L&#39;azione viene reindirizzata a un campo all&#39;interno del risultato.

```
On condition: 
  targeted template's primary results equal 1 
  query q matches regular expression ^\D\D\D-\d+ 
  no facet selected ^\D\D\D-\d+ 
Perform the following actions: 
  redirect to result field "loc" in template *targeted for search *primary
```

## Best practice {#section_1BF7DE1BD5664B3BAEC26AA829FDB0BA}

* Qualsiasi insieme di regole che attiva un nuovo ciclo di ricerca deve sempre avere una clausola condizionale per verificare che non sia l&#39;ultima passata attraverso il modulo. Se avete già eseguito il numero massimo di ricerche, non potete ripristinare le ricerche.
* Se siete sull&#39;ultimo passaggio del modulo e i risultati sono ancora insufficienti, potete passare a un modello &quot;nessun risultato&quot;.
* È consigliabile basare la modifica di un modello di presentazione sul risultato di una ricerca che potrebbe presentare altri parametri. Se desiderate selezionare un modello basato solo sulla query in entrata, una regola di pre-ricerca risulta più efficiente.
* Il data mining della query viene eseguito nel modulo Query Cleaning. È possibile fare riferimento alle variabili personalizzate nell&#39;elaborazione post-ricerca.
* Quando effettuate un reindirizzamento, verificate sempre che il cliente non abbia selezionato alcun facet. Il motivo è che è scomodo quando un cliente si avventura in un facet e viene improvvisamente rimosso dai risultati della ricerca. Il cliente potrebbe desiderare di deselezionare la facet quando vede che il singolo risultato non è desiderato che stessero cercando.

## Aggiunta di una nuova regola di post-ricerca {#task_52F6F9AAD65B45B5ACA1FF245DFFADD9}

Potete utilizzare [!DNL Post-Search Rules] per selezionare il modello di presentazione utilizzato per visualizzare i risultati della ricerca in base alla query in entrata.

**Per aggiungere una nuova regola di post-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Post-Search Rules] fare clic su **[!UICONTROL Add New Rule]**.
1. Nel campo [!DNL Name] digitare il nome della nuova regola di pulizia della query.
1. Nella pagina [!DNL Add Post-Search Rule], utilizzare gli elenchi a discesa e i campi di testo per creare la query.

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
      <td colname="col2"> <p>Un cookie HTTP. I nomi e i valori dei cookie devono essere codificati in Uniform Resource Identifier. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Variabile personalizzata </p> </td> 
      <td colname="col2"> <p>Variabile definita dall'utente. Potete aggiungere, eliminare o impostare un numero illimitato di variabili personalizzate. </p> <p>È possibile fare riferimento a qualsiasi variabile personalizzata definita nei moduli Pulizia query e Regole pre-ricerca, all'interno delle regole post-ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Variabile di sistema </p> </td> 
      <td colname="col2"> <p>Variabili di sola lettura impostate dal sistema interno che è possibile controllare. Sono supportate le seguenti variabili di sistema: </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> hostname  </span> <p>Nome dell'host del server. </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri  </span> <p>Identificatore risorsa uniforme richiesto senza la stringa di query. </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>L'intera stringa di query. </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> ambiente </span> <p>"Stage" o "live" a seconda che la query in entrata sia stata inviata all'ambiente in cui è stato eseguito lo stage o meno. </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>Uniform Resource Locator di provenienza del cliente. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Variabile di sistema </p> </td> 
      <td colname="col2"> <p>Variabili di sola lettura che è possibile utilizzare nelle condizioni per determinare lo stato corrente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet di ricerca del modello </p> </td> 
      <td colname="col2"> <p>Facet locale per una ricerca con nome associata a un modello di presentazione. Un facet è essenzialmente parametri CGI speciali utilizzati per indicare quale valore all’interno di un facet è stato selezionato da un cliente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro di ricerca del modello </p> </td> 
      <td colname="col2"> <p>Un parametro CGI locale per una ricerca con nome associata a un modello di presentazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro back-end del modello </p> </td> 
      <td colname="col2"> <p>I parametri di query in entrata vengono infine convertiti in parametri di back-end utilizzati per eseguire la ricerca. </p> <p>Vedere <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Parametri CGI di ricerca back-end </a>. </p> <p>I parametri di back-end non vengono visualizzati sugli elementi di navigazione. Di conseguenza, potete nascondere ai clienti eventuali parametri aggiuntivi da applicare a una ricerca. </p> <p>Il parametro è locale per una ricerca specifica all’interno di un modello di presentazione. Le azioni sui parametri di backend sono ritardate; in altre parole, vengono applicate subito prima dell’invio della ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Modello di destinazione </p> </td> 
      <td colname="col2"> <p>Un'istanza speciale di una variabile personalizzata definita dal sistema che non può essere eliminata. Questa variabile contiene il modello di presentazione con targeting corrente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Classifica </p> </td> 
      <td colname="col2"> <p>Consente di specificare la regola di classificazione da utilizzare nella ricerca. Questa opzione viene visualizzata solo se sono stati definiti campi di classificazione e regole di classificazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ultima regola </p> </td> 
      <td colname="col2"> <p>Se questa opzione è selezionata, il modulo di elaborazione post-ricerca non esegue alcuna regola aggiuntiva dopo l'azione della regola corrispondente. Questa azione è utile quando sono state impostate azioni che fanno corrispondere una regola successiva ma non si desidera che venga eseguita la regola successiva. </p> </td> 
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

## Modifica di una regola di post-ricerca {#task_ECB00334C0A74C87AF857DB3EB372119}

È possibile modificare le regole di post-ricerca esistenti aggiunte alla pagina [!DNL Post-Search Rules].

**Per modificare una regola di post-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Post-Search Rules], nella colonna **[!UICONTROL Actions]** della tabella fare clic su **[!UICONTROL Edit]** per la regola associata da modificare.
1. Nella pagina [!DNL Edit Post-Search Rule], utilizzare gli elenchi a discesa e i campi di testo per creare la query.

   Vedere la tabella delle opzioni in [Aggiunta di una nuova regola di post-ricerca](../c-about-rules-menu/c-about-post-search-rules.md#task_52F6F9AAD65B45B5ACA1FF245DFFADD9).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una regola di post-ricerca {#task_0F4653AB20D54B769A4FA8D1491AB4CF}

È possibile eliminare le regole di post-ricerca non più necessarie o utilizzate.

Quando si elimina una regola, l&#39;ordine di esecuzione delle regole rimanenti viene modificato automaticamente per tenere conto dell&#39;eliminazione.

**Per eliminare una regola di post-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Post-Search Rules], nella colonna **[!UICONTROL Actions]** della tabella fare clic su **[!UICONTROL Delete]** per la regola associata da eliminare.
1. Nella finestra di dialogo [!DNL Confirmation], fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica dell&#39;ordine in cui vengono eseguite le regole di post-ricerca {#task_40542FCD32234BBF881A81BF5477F78F}

Potete riordinare le regole di post-ricerca per modificare l&#39;ordine in cui vengono eseguite sui modelli di presentazione.

Le regole di post-ricerca vengono eseguite nell&#39;ordine in cui sono state definite. Più alto è il numero dell&#39;ordine di una regola, più tardi verrà eseguito nel processo, trumping regole precedenti. Riordinare le regole immettendo un nuovo numero nella colonna Ordine della tabella nella pagina [!DNL Post-Search Rules]. Potete anche utilizzare le regole di trascinamento per modificarne l&#39;ordine di esecuzione.

**Per modificare l&#39;ordine di esecuzione delle regole di post-ricerca**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Post-Search Rules], effettuare una delle seguenti operazioni:

   * Fate clic sull&#39;intestazione della colonna **[!UICONTROL Order]** per ordinare le regole in ordine crescente o decrescente.
   * Nella colonna [!DNL Order], digitare il numero di ordine che si desidera eseguire nel campo di testo a sinistra del nome di una regola di pre-ricerca.
   * Trascinare una riga di tabella nella posizione in cui si desidera eseguire la regola. Tutti i numeri di ordine vengono aggiornati in base al nuovo ordine in cui vengono eseguite le regole.

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL History]** per annullare le modifiche apportate.

      Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
