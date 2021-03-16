---
description: Puoi utilizzare le Regole aziendali per merchandising della ricerca.
solution: Target
title: Informazioni sulle regole aziendali
topic: Regole,Ricerca nel sito e merchandising
uuid: f2186f54-7a39-4f46-bb29-5115d5a17f07
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '3120'
ht-degree: 0%

---


# Informazioni sulle regole aziendali{#about-business-rules}

Puoi utilizzare le Regole aziendali per merchandising della ricerca.

## Utilizzo delle regole aziendali {#concept_2A93D76216754D3D8412CDEA00BD26BD}

Ad esempio, puoi configurare quando vengono visualizzati i banner, quali risultati vengono visualizzati e in quale ordine. Puoi anche configurare la posizione di un elemento nel facet e il modello utilizzato per una determinata ricerca. Le regole vengono eseguite nell&#39;ordine in cui sono state definite; più alto è il numero dell&#39;ordine di una regola, più tardi verrà eseguito nel processo, trumping delle regole precedenti. Puoi trascinare le regole per modificarne l’ordine oppure riordinarle immettendo un nuovo numero nella casella di testo dell’ordine delle regole.

Ogni regola business è composta da attivatori e azioni.

Il trigger definisce quando la regola viene eseguita. Ad esempio, quando il termine della query è &quot;mens&quot; o quando i risultati sono principalmente cappelli. Il trigger è costituito da più condizioni che devono essere tutte o una qualsiasi di esse deve essere true per rendere il trigger complessivo true. È possibile specificare la precedenza modificando l&#39;operatore trigger.

L’azione definisce cosa accade quando la condizione di attivazione viene soddisfatta. Ad esempio, impostare il banner per visualizzare o spostare un dato risultato in posizione 1. La tabella delle regole mostra informazioni di riepilogo sulla regola. Puoi fare clic sul nome di una regola per aprirla e visualizzare ulteriori informazioni.

La tabella delle regole mostra un elenco di tutte le regole aziendali. Per impostazione predefinita, la tabella mostra le ultime dieci regole aggiunte, in ordine decrescente. Puoi fare clic sulle intestazioni di colonna nella tabella per ordinare le regole in ordine crescente o decrescente.

Le regole aziendali possono avere uno dei tre stati seguenti: Approvato, sospeso o WIP (Work In Progress)

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stato della regola commerciale </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Approvato </p> </td> 
   <td colname="col2"> <p>Le regole di business approvate vengono eseguite nell’ambiente live e nell’ambiente di staging. È possibile approvare una regola business nel Generatore di regole avanzate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sospeso </p> </td> 
   <td colname="col2"> <p>Le regole aziendali sospese non vengono mai eseguite nell’ambiente di staging o in quello live. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>WIP </p> </td> 
   <td colname="col2"> <p>WIP (Work In Progress) sono regole aziendali non approvate né sospese. In altre parole, potreste ancora lavorare su di loro o vorreste testarli prima di approvarli. Le regole aziendali in uno stato di WIP vengono eseguite solo nell'ambiente di staging. </p> </td> 
  </tr> 
 </tbody> 
</table>

Approvi le regole di business e le invii live in modo che vengano eseguite nell’ambiente live. Attualmente, puoi solo inviare in diretta le regole *all* . Tuttavia, puoi modificare lo stato di una regola per avere il controllo su quali regole vengono eseguite e non vengono eseguite nell&#39;ambiente live.

Per impostazione predefinita, le regole vengono eseguite ogni volta che vengono soddisfatti i trigger associati. È tuttavia possibile pianificare facoltativamente l&#39;esecuzione di una regola per un intervallo di date e ore specifico.

Inoltre, per impostazione predefinita, le regole vengono eseguite ogni volta che i relativi trigger associati vengono soddisfatti per tutti gli archivi. Se desideri che la regola si applichi solo a determinati archivi, puoi utilizzare il pannello Negozi per selezionare uno o più archivi a cui viene applicata la regola.

## Aggiunta di una nuova regola business {#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7}

Puoi utilizzare [!DNL Visual Rule Builder] o [!DNL Advanced Rule Builder] per aggiungere regole di business che adattano l’esperienza di ricerca del cliente.

**Per aggiungere una nuova regola business**

I passaggi seguenti presuppongono l&#39;utilizzo di Visual Rule Builder.

1. Esegui una delle operazioni seguenti:

   * Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]** dal menu del prodotto. Nella pagina [!DNL Business Rules], fai clic su **[!UICONTROL Add New Rule]**.

   * Scegliere **[!UICONTROL Simulator]** dal menu del prodotto. Nella pagina **[!UICONTROL Simulator for Today]** , fai clic su **[!UICONTROL Add New Rule]** a destra del menu a discesa **[!UICONTROL Options]** .

      Se l&#39;opzione **[!UICONTROL Add New Rule]** non è visibile sulla pagina, scegliere **[!UICONTROL Options]** dal menu a discesa **[!UICONTROL Simulate Staged]**.

      ![](assets/Simulator.png)

1. Nel campo di testo **[!UICONTROL Name]**, digitare il nuovo nome della regola business.

   Non fare ancora clic su **[!UICONTROL Save Rule]** .
1. (Facoltativo) Se gestisci un gran numero di regole business, puoi assegnare alle regole business etichette specifiche. Nel campo **[!UICONTROL Tags]** immetti una o più etichette di tag, Usa una virgola, una tabulazione o un Invio come delimitatore.

   Nella pagina [!DNL Business Rules] , utilizza la funzione **[!UICONTROL Filter by tag]** per filtrare le regole che corrispondono a una determinata etichetta. 1. Nella pagina [!DNL Business Rule Builder] , imposta i trigger e le azioni che desideri utilizzare.

   **Opzioni di attivazione**

   I trigger sono le condizioni che devono essere soddisfatte affinché una regola business possa essere eseguita. Quando una regola business ha più attivatori, puoi configurare il modo in cui i trigger rispondono utilizzando uno dei tre metodi seguenti:

   * Una risposta in cui tutti gli attivatori devono essere veri (l&#39;impostazione predefinita) come nell&#39;esempio seguente:

      `if a AND b AND c then ...`

   * Una risposta in cui uno qualsiasi dei trigger deve essere vero come nell’esempio seguente:

      `if a OR b OR c then ...`

   * Risposta in cui è specificata una combinazione personalizzata di trigger. In altre parole, puoi combinare singoli attivatori o &quot;condizioni&quot; con gli operatori `AND` e `OR`.

      È inoltre possibile modificare la precedenza della valutazione aggiungendo combinazioni di parentesi sinistra e destra come nell&#39;esempio seguente:

      `if (a OR b) AND c then ...`

      >[!NOTE]
      >
      >Se combini operatori `AND` con operatori `OR` in un set di regole di business personalizzate, assicurati di specificare le parentesi in modo appropriato per garantire che i trigger siano valutati nell&#39;ordine corretto.

      Per impostazione predefinita, questa funzione di personalizzazione di una combinazione di attivatori non è attivata. Contatta il supporto tecnico per attivare questa funzione.
   <table> 
      <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione Triggers </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Corrispondenza parole chiave </p> </td> 
      <td colname="col2"> <p>Trigger è true quando il termine di ricerca corrisponde alla parola chiave che distingue tra maiuscole e minuscole specificata. Il trigger è true sia per la parola chiave che per tutti i relativi sinonimi, come definito nel dizionario Linguistica. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Corrispondenza query </p> </td> 
      <td colname="col2"> <p> Trigger è true quando tutti i parametri di ricerca corrispondono. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Gruppo di risultati dominante </p> </td> 
      <td colname="col2"> <p> Trigger è true quando il gruppo di risultati definiti dalla ricerca specificata domina il set di risultati. </p> <p>Per impostazione predefinita, la dominanza è impostata sul 50%. Questa impostazione è una preferenza di merchandising che è possibile impostare. </p> <p> 
        <!--See <xref href="t_Configuring_Merchandising_preferences.xml#task_7AC7B9F5D9F44E10AB5BC0B8CB31C37A" type="task" format="dita" scope="local">Configuring Merchandising preferences</xref>. --> </p> <p>Affinché il trigger sia true, l'intero gruppo deve essere presente all'interno del set di risultati. Il gruppo di risultati è dinamico. Possono cambiare dopo le operazioni di indice, a seconda dei risultati che corrispondono ai criteri di ricerca originali. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Gruppo di risultati presente </p> </td> 
      <td colname="col2"> <p> Trigger è true quando il gruppo di risultati definiti dalla ricerca specificata è presente nel set di risultati. L’intero gruppo deve essere presente all’interno del set di risultati per soddisfare il trigger (i risultati possono essere presenti su qualsiasi pagina). Il gruppo di risultati è dinamico e può cambiare dopo le operazioni dell'indice a seconda dei risultati che corrispondono ai criteri di ricerca originali. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Risultati presenti </p> </td> 
      <td colname="col2"> <p> Trigger è true quando il singolo risultato si trova all'interno del set di risultati. Il risultato può trovarsi in qualsiasi punto del set di risultati, non deve necessariamente trovarsi nella pagina che l’utente sta visualizzando attualmente. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **Opzioni azione**

   Quando gli attivatori di una regola business vengono soddisfatti, vengono eseguite le azioni associate alla regola. Mentre il Generatore di regole di visualizzazione consente di creare le azioni seguenti, puoi utilizzare il Generatore di regole avanzate per creare ulteriori tipi di azioni.

   Le azioni Rimuovi elemento facet, Mostra elemento facet, Mostra facet, Rimuovi facet, Spinge elemento facet nella tabella seguente richiedono un facet. L’interfaccia per la scelta di un facet dipende dalla configurazione dell’account. Ad esempio, un account normale utilizza un elenco a discesa per scegliere i facet. Tuttavia, se il tuo account ha dei facet con inclinazione, viene visualizzata una casella di testo autocompleta in cui puoi immettere il nome di qualsiasi facet. Il completamento automatico suggerisce i facet in un elenco a discesa quando si digita il nome del facet. I suggerimenti includono facet attualmente definiti. Se il tuo account ha una mappa slot, suggerisce anche sfaccettature inclinate.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione Azioni </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Gruppo push </p> </td> 
      <td colname="col2"> <p> Invia a una posizione specifica il gruppo di risultati di ricerca definito dai criteri di ricerca specificati. </p> <p>Inviando un gruppo di risultati di ricerca, il gruppo non viene aggiunto in modo implicito. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi gruppo </p> </td> 
      <td colname="col2"> <p> Aggiungi il gruppo di risultati di ricerca definito dai criteri di ricerca specificati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi gruppo </p> </td> 
      <td colname="col2"> <p> Rimuovi il gruppo di risultati di ricerca definito dai criteri di ricerca specificati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Singolo push </p> </td> 
      <td colname="col2"> <p> Invia il singolo risultato di ricerca alla posizione selezionata. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi singolo </p> </td> 
      <td colname="col2"> <p> Aggiunge un singolo risultato di ricerca alla posizione selezionata. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi singola </p> </td> 
      <td colname="col2"> <p> Rimuove un singolo risultato di ricerca dal set di risultati di ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi tutti i risultati </p> </td> 
      <td colname="col2"> <p>Rimuove tutti i risultati dal set di risultati della ricerca. </p> <p> 
        <!-- Bug #3331637 The option is meant to be used in conjunction with other rule actions in order to create "canned landing pages" where we want to create a page's content solely by rule actions, and need to completely discard the "natural" results of the search. Given that the other options don't have any kind of "here's how/why you might use this", I don't see much point in breaking that precedent here.--> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Seleziona un banner diverso </p> </td> 
      <td colname="col2"> <p> Modifica il banner nell’area banner selezionata. </p> <p>Questa opzione è disponibile quando si fa clic con il pulsante destro del mouse su un banner nell’area di visualizzazione della pagina Web. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi comandi banner </p> </td> 
      <td colname="col2"> <p>Si applica solo ai modelli Dynamic Media Classic di Adobe. </p> <p>Consente di modificare i parametri predefiniti utilizzati nel modello banner. </p> <p>Vedi la tabella delle opzioni in <a scope="local" href="../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3" type="reference" format="dita"> Aggiunta di un banner con Adobe Dynamic Media Classic </a>. </p> <p>Consulta anche <a href="../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9" type="task" format="dita" scope="local"> Modifica di un banner tramite Adobe Dynamic Media Classic </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi banner </p> </td> 
      <td colname="col2"> <p> Rimuove il banner dall’area del banner selezionata; nessun banner viene visualizzato a meno che un'altra regola che imposta un banner non sostituisca questa regola. </p> <p>Questa opzione è disponibile quando si fa clic con il pulsante destro del mouse su un banner nell’area di visualizzazione della pagina Web. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elemento facet push </p> </td> 
      <td colname="col2"> <p> Invia un elemento all’interno di un facet alla posizione selezionata. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi area </p> </td> 
      <td colname="col2"> <p> Rimuove una zona dalla pagina dei risultati della ricerca. </p> <p>Vedi anche l'azione Rimuovi facet di seguito. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zona di rivelazione </p> </td> 
      <td colname="col2"> <p> Mostra una zona nella pagina dei risultati della ricerca. </p> <p>Vedi anche l'azione Mostra facet di seguito. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi elemento facet </p> </td> 
      <td colname="col2"> <p> Rimuove un elemento facet da un facet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Reveal Facet Item (Mostra elemento facet) </p> </td> 
      <td colname="col2"> <p> Rivela un elemento facet specifico. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet di rivelazione </p> </td> 
      <td colname="col2"> <p> Rivela un facet specifico. Questa azione è preferita rispetto all’azione Zona di visualizzazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi facet </p> </td> 
      <td colname="col2"> <p> Rimuove un facet specifico. Questa azione è da preferirsi all'azione Rimuovi zona. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   A seconda del pannello del generatore di regole attivo (dispiegato), puoi anche fare quanto segue per impostare attivatori e azioni.

   * Quando si apre il pannello **[!UICONTROL Triggers]** - Nell&#39;area del modello di presentazione della pagina Generatore di regole business, fare clic con il pulsante destro del mouse su un risultato di ricerca o un facet di ricerca, quindi fare clic su **[!UICONTROL Add "result present" trigger]**.

      Nel pannello Triggers fai clic sulla &quot;X&quot; a sinistra di un trigger per rimuoverlo dall’elenco dei trigger.

   * Quando si apre il pannello **[!UICONTROL Actions]** - Nell&#39;area del modello di presentazione della pagina Generatore di regole business, fare clic con il pulsante destro del mouse su un risultato della ricerca. Fare clic su **[!UICONTROL Add Result]**, **[!UICONTROL Remove Result]**, **[!UICONTROL Push to bottom]** o **[!UICONTROL Push to #`<n>`]** (dove `<n>` è un numero).


1. (Facoltativo) In qualsiasi pannello di Generatore regole business ( [!DNL Triggers], [!DNL Actions] o [!DNL Schedule]), effettua una delle seguenti operazioni:

   * Nell&#39;area del modello di presentazione dell&#39;area della pagina Generatore di regole business fare clic con il pulsante destro del mouse su un banner, quindi scegliere **[!UICONTROL Select different banner]**. Nella pagina **[!UICONTROL Pick Banner]** , fai clic su **[!UICONTROL Pick this banner]** sotto la miniatura del banner per aggiungerlo al modello di presentazione. Sono disponibili solo i banner che corrispondono alle dimensioni e all’area del banner originale nel modello di presentazione.

      L’azione Aggiungi banner viene aggiunta al pannello [!DNL Actions] .

   * Nell&#39;area del modello di presentazione della pagina [!DNL Business Rule Builder], fare clic con il pulsante destro del mouse su un banner modello Dynamic Media Classic di Adobe di cui si desidera modificare i parametri, quindi fare clic su **[!UICONTROL Add banner commands]**. Nella finestra di dialogo [!DNL Change Parameters], impostare le opzioni relative ai parametri desiderate.

      Vedi la tabella delle opzioni in [Aggiunta di un banner con Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

      Clic **[!UICONTROL Save]**.

      Le modifiche ai parametri vengono aggiunte al pannello [!DNL Actions] .

      Consulta anche [Modifica di un banner con Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9).

   * Nell&#39;area del modello di presentazione della pagina Generatore di regole business fare clic con il pulsante destro del mouse sul banner che si desidera eliminare dalla pagina, quindi fare clic su **[!UICONTROL Remove banner]**. L’azione Rimuovi banner viene aggiunta al pannello Azioni.

1. (Facoltativo) Nel pannello **[!UICONTROL Schedule]** , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Run Indefinitely]** per far eseguire la regola ogni volta che i relativi attivatori associati vengono soddisfatti. Questa è l’opzione predefinita.
   * Fare clic su **[!UICONTROL Fixed Schedule]**, quindi specificare la data e l&#39;ora di inizio e la data e l&#39;ora di fine dell&#39;esecuzione della regola ogni volta che viene soddisfatto il trigger associato.

1. Clic **[!UICONTROL Save Rule]**.
1. (Facoltativo) Nella pagina [!DNL Business Rules] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di una regola business {#task_375CFA75D1D94D9E92A35DE1228E5087}

È possibile utilizzare Visual Rule Builder o Advanced Rule Builder per modificare le regole business aggiunte.

**Per modificare una nuova regola business**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Business Rules] , effettua una delle seguenti operazioni:

   * Nella colonna [!DNL Name] fare clic sul nome di una regola business che si desidera modificare.

      La regola business viene aperta nell’interfaccia predefinita specificata in **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL My Preferences]**.

   * Nell&#39;elenco a discesa, accanto al nome di una regola business che si desidera modificare, fare clic su **[!UICONTROL Edit in advanced mode]** o **[!UICONTROL Edit in visual mode]**.

1. Nel campo di testo [!DNL Name], digitare il nuovo nome della regola business.

   Non fare ancora clic su **[!UICONTROL Save Rule]** . 1. Nella pagina [!DNL Business Rule Builder] , imposta i trigger e le azioni che desideri utilizzare.

   Vedi la tabella delle opzioni in [Aggiunta di una nuova regola business](../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7).
1. (Facoltativo) In qualsiasi pannello **[!UICONTROL Business Rule Builder]** ( [!DNL Triggers], [!DNL Actions] o [!DNL Schedule], effettua una delle seguenti operazioni:

   * Nell&#39;area del modello di presentazione della pagina [!DNL Business Rule Builder] fare clic con il pulsante destro del mouse su un banner, quindi scegliere **[!UICONTROL Select different banner]**. Per aggiungerlo al modello di presentazione, fai clic su **[!UICONTROL Pick this banner]** sotto la miniatura del banner. [!DNL Pick Banner page] Sono disponibili solo i banner che corrispondono alle dimensioni e all’area del banner originale nel modello di presentazione.

      L’azione Aggiungi banner viene aggiunta al pannello [!DNL Actions] .

   * Nell&#39;area del modello di presentazione della pagina [!DNL Business Rule Builder], fare clic con il pulsante destro del mouse su un banner modello Dynamic Media Classic di Adobe di cui si desidera modificare i parametri, quindi fare clic su **[!UICONTROL Add banner commands]**. Nella finestra di dialogo [!DNL Change Parameters], impostare le opzioni relative ai parametri desiderate.

      Vedi la tabella delle opzioni in [Aggiunta di un banner con Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

      Clic **[!UICONTROL Save]**.

      Le modifiche ai parametri vengono aggiunte al pannello [!DNL Actions] .

      Consulta anche [Modifica di un banner con Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9).

   * Nell&#39;area del modello di presentazione della pagina [!DNL Business Rule Builder] fare clic con il pulsante destro del mouse sul banner che si desidera eliminare dalla pagina, quindi fare clic su **[!UICONTROL Remove banner]**. L’azione Rimuovi banner viene aggiunta al pannello [!DNL Actions] .

1. (Facoltativo) Nel pannello [!DNL Schedule] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Run Indefinitely]** per far eseguire la regola ogni volta che i relativi attivatori associati vengono soddisfatti. Questa è l’opzione predefinita.
   * Fare clic su **[!UICONTROL Fixed Schedule]**, quindi specificare la data e l&#39;ora di inizio e la data e l&#39;ora di fine dell&#39;esecuzione della regola ogni volta che viene soddisfatto il trigger associato.

1. Clic **[!UICONTROL Save Rule]**.

   La pagina [!DNL Business Rule Builder] viene chiusa e si viene restituiti alla pagina **[!UICONTROL Business Rule]** . Le regole vengono visualizzate nella tabella. Fai clic sull’intestazione di colonna **[!UICONTROL Modified]** per ordinare le regole in base alla data di modifica. 1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Copia di una regola business {#task_89F1879C71A54EE9B7454439302C03EC}

È possibile copiare una regola business esistente da utilizzare come base per una nuova regola business che si desidera creare.

**Per copiare una regola business**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella pagina **[!UICONTROL Business Rules]** dell’elenco a discesa accanto al nome di una regola business che si desidera copiare, fare clic su **[!UICONTROL Copy rule]**.
1. Modifica la regola business copiata come di consueto.

   Consulta [Modifica di una regola business](../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087).

## Approvazione delle regole business {#task_BD569D18BF664272B8692294C162E2C1}

È possibile attivare regole business con stato WIP (Work In Progress) o sospeso.

**Per approvare le regole aziendali**

1. Scegliere **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Business Rules], utilizzando l&#39;intestazione della colonna di stato nella colonna [!DNL Status] della tabella delle regole di business, ordina le regole che hanno uno stato **[!UICONTROL WIP]** o **[!UICONTROL suspended]**.

   Utilizza l’intestazione della colonna della casella di controllo sul lato sinistro della tabella per controllare tutte le regole attualmente visualizzate sulla pagina oppure controlla solo quelle che hanno uno stato **[!UICONTROL WIP]** o **[!UICONTROL suspended]**. 1. Nella barra dei menu vicino alla parte superiore della pagina, fai clic su **[!UICONTROL Approve]**.
1. Nella finestra di dialogo **[!UICONTROL Confirm Action]** fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Sospensione delle regole aziendali {#task_364E1FFB905141C08E306C8F1794A20E}

È possibile sospendere le regole business con stato WIP (Work In Progress) o approvato.

Quando hai sospeso una regola, nell’interfaccia utente indica che la hai temporaneamente resa inattiva e stai rinviando il lavoro su di essa per un altro momento. Tuttavia, puoi comunque modificare una regola sospesa.

**Sospensione delle regole aziendali**

1. Scegliere **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Business Rules], utilizzando lo stato nella colonna Stato della tabella delle regole business, nella colonna a sinistra della tabella controllare le regole che hanno uno stato **[!UICONTROL WIP]** o **[!UICONTROL approved]**.
1. Nella barra dei menu vicino alla parte superiore della pagina, fai clic su **[!UICONTROL Suspend]**.
1. Nella finestra di dialogo **[!UICONTROL Confirm Action]** fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Riprendere le regole aziendali {#task_E67D678C765B436EA2A3D6ADD7A49ABA}

È possibile riprendere le regole business per riattivare una regola sospesa. Dopo aver ripreso la regola business, il relativo stato viene impostato su WIP (Work In Progress).

**Per riprendere le regole aziendali**

1. Scegliere **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Business Rules], utilizzando lo stato nella colonna Stato della tabella delle regole business, nella colonna a sinistra della tabella controllare le regole che hanno uno stato **[!UICONTROL suspended]**.
1. Nella barra dei menu vicino alla parte superiore della pagina, fai clic su **[!UICONTROL Resume]**.
1. Nella finestra di dialogo [!DNL Confirm Action] fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica dell&#39;ordine di esecuzione delle regole business {#task_FE3B1C17307F49B49050C2EC5A063991}

È possibile riordinare le regole business per modificare l&#39;ordine in cui vengono eseguite sui modelli di presentazione.

Le regole aziendali vengono eseguite nell&#39;ordine in cui sono state definite; più alto è il numero dell&#39;ordine di una regola, più tardi verrà eseguito nel processo, trumping delle regole precedenti. Per riordinare le regole, immetti un nuovo numero nella colonna Ordine della tabella nella pagina [!DNL Business Rules]. Puoi inoltre utilizzare le regole di trascinamento per modificarne l’ordine di esecuzione.

**Per modificare l&#39;ordine di esecuzione delle regole business**

1. Scegliere **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella tabella della pagina [!DNL Business Rules] eseguire una delle operazioni seguenti:

   * Fai clic sull’intestazione di colonna **[!UICONTROL Order]** per ordinare le regole in ordine crescente o decrescente.
   * Nella colonna **[!UICONTROL Order]**, digitare il numero di ordine che si desidera eseguire nel campo di testo a sinistra del nome di una regola business.
   * Trascinare una riga di tabella nella posizione in cui si desidera eseguire la regola. Tutti i numeri dell&#39;ordine vengono aggiornati per riflettere il nuovo ordine in cui vengono eseguite le regole.

1. Clic **[!UICONTROL Save Changes]**.

   Le regole aziendali verranno ora eseguite nell&#39;ordine specificato. L&#39;eccezione si verifica se è specificata una regola business di reindirizzamento. Se e quando la regola business di reindirizzamento viene attivata o colpita, l&#39;elaborazione della regola business si interrompe per consentire il reindirizzamento.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione delle regole business {#task_AE37B42412044541BCC6D46CF8793DFF}

È possibile eliminare le regole business il cui stato è WIP, sospeso o approvato, utilizzando il menu a discesa Azioni in blocco.

**Per eliminare le regole business**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella pagina [!DNL Business Rules] , effettua una delle seguenti operazioni:

   * Utilizza l’intestazione della colonna della casella di controllo per controllare tutte le regole attualmente visualizzate sulla pagina.
   * Selezionare solo le regole business che si desidera eliminare, in base allo stato della colonna Stato della tabella.

1. Nell’elenco a discesa [!DNL Bulk Actions] , fai clic su **[!UICONTROL Delete]**.
1. Nella finestra di dialogo [!DNL Confirm Action] fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
