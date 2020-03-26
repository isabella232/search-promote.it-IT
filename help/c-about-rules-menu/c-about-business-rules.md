---
description: Potete utilizzare le Regole aziendali per merchandising della ricerca.
seo-description: Potete utilizzare le Regole aziendali per merchandising della ricerca.
seo-title: Informazioni sulle regole aziendali
solution: Target
title: Informazioni sulle regole aziendali
topic: Rules,Site search and merchandising
uuid: f2186f54-7a39-4f46-bb29-5115d5a17f07
translation-type: tm+mt
source-git-commit: fc1f0b15a15a9d0308494fc23c5b4258442c8aab

---


# Informazioni sulle regole aziendali{#about-business-rules}

Potete utilizzare le Regole aziendali per merchandising della ricerca.

## Utilizzo delle regole aziendali {#concept_2A93D76216754D3D8412CDEA00BD26BD}

Ad esempio, potete configurare quando vengono visualizzati i banner, quali risultati vengono visualizzati e in quale ordine. Potete anche configurare la posizione di un elemento nel facet e il modello da usare per una determinata ricerca. Le regole vengono eseguite nell&#39;ordine in cui sono state definite; più alto è il numero d&#39;ordine di una regola, più tardi verrà eseguito nel processo, trumping regole precedenti. È possibile trascinare le regole per modificarne l&#39;ordine, oppure riordinarle immettendo un nuovo numero nella casella di testo dell&#39;ordine delle regole.

Ogni regola business è composta da attivatori e azioni.

Il trigger definisce quando la regola viene eseguita. Ad esempio, quando il termine della query è &quot;mens&quot; o i risultati sono principalmente cappelli. L&#39;attivatore è costituito da più condizioni che devono essere tutte, o che devono essere vere per rendere l&#39;attivatore complessivo vero. È possibile specificare la precedenza modificando l&#39;operatore di attivazione.

L&#39;azione definisce cosa accade quando viene soddisfatta la condizione di attivazione. Ad esempio, se impostate il banner in modo che visualizzi o sposti un dato risultato in posizione 1, La tabella delle regole mostra informazioni di riepilogo sulla regola. Potete fare clic sul nome di una regola per aprirla e visualizzare ulteriori informazioni.

La tabella delle regole mostra un elenco di tutte le regole aziendali. Per impostazione predefinita, la tabella mostra le ultime dieci regole aggiunte, in ordine decrescente. È possibile fare clic sulle intestazioni delle colonne nella tabella per ordinare le regole in ordine crescente o decrescente.

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
   <td colname="col2"> <p>Le regole aziendali approvate vengono eseguite nell'ambiente live e nell'ambiente di gestione. È possibile approvare una regola business nel Generatore di regole avanzate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sospeso </p> </td> 
   <td colname="col2"> <p>Le regole di business sospese non vengono mai eseguite nell'ambiente in cui sono state create le fasi o in ambiente live. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>WIP </p> </td> 
   <td colname="col2"> <p>WIP (Work In Progress) sono regole aziendali che non sono né approvate né sospese. In altre parole, potreste ancora lavorare su di loro o potreste desiderare testarli prima di approvarli. Le regole aziendali in uno stato di WIP vengono eseguite solo nell'ambiente in cui sono state create le fasi. </p> </td> 
  </tr> 
 </tbody> 
</table>

Approvate le regole di business e le inviate live in modo che vengano eseguite nel vostro ambiente live. Al momento, è possibile trasmettere *tutte* le regole in diretta. Tuttavia, puoi modificare lo stato di una regola per avere il controllo su quali regole vengono eseguite e non vengono eseguite nell&#39;ambiente live.

Per impostazione predefinita, le regole vengono eseguite ogni volta che vengono soddisfatti i trigger associati. È tuttavia possibile pianificare l&#39;esecuzione di una regola per un intervallo di date e ore specifico.

Inoltre, per impostazione predefinita, le regole vengono eseguite ogni volta che i relativi trigger associati vengono soddisfatti per tutti gli store. Se desiderate che la regola venga applicata solo a determinati store, potete utilizzare il pannello Store per selezionare uno o più store a cui è applicata la regola.

## Aggiunta di una nuova regola business {#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7}

Puoi utilizzare [!DNL Visual Rule Builder] o [!DNL Advanced Rule Builder] aggiungere regole di business che adattano l&#39;esperienza di ricerca del cliente.

**Aggiunta di una nuova regola business**

Nella procedura seguente si presuppone che si stia utilizzando Visual Rule Builder.

1. Esegui una delle operazioni seguenti:

   * Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]** dal menu del prodotto. Sulla [!DNL Business Rules] pagina, fate clic su **[!UICONTROL Add New Rule]**.

   * Scegliere **[!UICONTROL Simulator]**. Sulla **[!UICONTROL Simulator for Today]** pagina, fare clic **[!UICONTROL Add New Rule]** a destra del menu a **[!UICONTROL Options]** discesa.

      Se l’ **[!UICONTROL Add New Rule]** opzione non è visibile sulla pagina, scegliere **[!UICONTROL Options]** dal menu a **[!UICONTROL Simulate Staged]** discesa.

      ![](assets/Simulator.png)

1. Nel campo di **[!UICONTROL Name]** testo, digitare il nuovo nome della regola business.

   Non fate **[!UICONTROL Save Rule]** ancora clic.
1. (Facoltativo) Se gestite un numero elevato di regole business, potete assegnare alle regole business dei tag etichette specifiche. Nel **[!UICONTROL Tags]** campo, immettere una o più etichette di tag, utilizzare una virgola, una tabulazione o un Invio come delimitatore.

   Sulla [!DNL Business Rules] pagina, utilizzate la **[!UICONTROL Filter by tag]** funzione per filtrare le regole che corrispondono a una determinata etichetta. 1. Nella [!DNL Business Rule Builder] pagina, impostate gli attivatori e le azioni che desiderate utilizzare.

   **Opzioni di attivazione**

   Triggers sono le condizioni che devono essere soddisfatte per l&#39;esecuzione di una regola business. Quando una regola business ha più attivatori, puoi configurare il modo in cui i trigger rispondono utilizzando uno dei tre metodi seguenti:

   * Una risposta in cui tutti i trigger devono essere veri (impostazione predefinita), come nell&#39;esempio seguente:

      `if a AND b AND c then ...`

   * Una risposta in cui uno degli attivatori deve essere vero, come nell&#39;esempio seguente:

      `if a OR b OR c then ...`

   * Risposta in cui è specificata una combinazione personalizzata di trigger. In altre parole, è possibile combinare singoli trigger o &quot;condizioni&quot; con `AND` operatori e `OR` operatori.

      È inoltre possibile modificare la precedenza della valutazione aggiungendo combinazioni di parentesi sinistra e destra come nell&#39;esempio seguente:

      `if (a OR b) AND c then ...`

      >[!NOTE]
      >
      >Se si combinano `AND` operatori con `OR` operatori in un set di regole aziendali personalizzate, assicurarsi di specificare le parentesi in modo appropriato per garantire che i trigger vengano valutati nell&#39;ordine corretto.

      Per impostazione predefinita, questa particolare funzione di personalizzazione di una combinazione di attivatori non è abilitata. Per attivare questa funzione, contattate il supporto tecnico.
   <table> 
      <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Attiva, opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Parole chiave corrispondenti </p> </td> 
      <td colname="col2"> <p>Trigger è true quando il termine di ricerca corrisponde alla parola chiave con distinzione tra maiuscole e minuscole specificata. L'attivatore è vero sia per la parola chiave che per tutti i sinonimi, come definito nel dizionario Linguistico. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Corrispondenza query </p> </td> 
      <td colname="col2"> <p> Trigger è true quando tutti i parametri di ricerca corrispondono. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Il gruppo di risultati è dominante </p> </td> 
      <td colname="col2"> <p> Trigger è true quando il gruppo di risultati definito dalla ricerca specificata domina il set di risultati. </p> <p>Per impostazione predefinita, la dominanza è impostata su 50%. Questa impostazione è una preferenza merchandising che potete impostare. </p> <p> 
        <!--See <xref href="t_Configuring_Merchandising_preferences.xml#task_7AC7B9F5D9F44E10AB5BC0B8CB31C37A" type="task" format="dita" scope="local">Configuring Merchandising preferences</xref>. --> </p> <p>L'intero gruppo deve essere presente all'interno del set di risultati affinché l'attivatore sia vero. Il gruppo di risultati è dinamico. Possono essere modificati dopo le operazioni di indice, a seconda dei risultati che corrispondono ai criteri di ricerca originali. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Gruppo di risultati presente </p> </td> 
      <td colname="col2"> <p> Trigger è true quando nel set di risultati è presente il gruppo di risultati definito dalla ricerca specificata. Affinché il trigger possa essere soddisfatto, l'intero gruppo deve essere presente all'interno del set di risultati (i risultati possono essere presentati su qualsiasi pagina). Il gruppo di risultati è dinamico e può variare dopo le operazioni di indice a seconda dei risultati che corrispondono ai criteri di ricerca originali. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Risultati presenti </p> </td> 
      <td colname="col2"> <p> Trigger è true quando il singolo risultato si trova all'interno del set di risultati. Il risultato può trovarsi ovunque nel set di risultati, non deve necessariamente trovarsi nella pagina visualizzata dall’utente. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **Opzioni azione**

   Quando vengono soddisfatti i trigger di una regola business, vengono eseguite le azioni associate alla regola. Con il Generatore di regole visive è possibile creare le azioni seguenti, mentre con il Generatore di regole avanzate è possibile creare ulteriori tipi di azioni.

   Le azioni Rimuovi elemento facet, Rivela elemento facet, Mostra facet, Rimuovi facet, Sposta elemento facet nella tabella seguente richiedono un facet. L&#39;interfaccia per la scelta di un facet dipende dalla configurazione dell&#39;account. Ad esempio, un account normale utilizza un elenco a discesa per scegliere i facet. Tuttavia, se l’account ha dei facet con inclinazione, viene visualizzata una casella di testo con completamento automatico in cui è possibile immettere il nome di qualsiasi facet. Il completamento automatico suggerisce i facet in un elenco a discesa quando si digita il nome del facet. I suggerimenti includono facet attualmente definiti. Se il vostro account ha una mappa slot, suggerisce anche facet inclinati.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Azioni, opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Gruppo push </p> </td> 
      <td colname="col2"> <p> Invia a una posizione specifica il gruppo di risultati di ricerca definito dai criteri di ricerca specificati. </p> <p>L'invio di un gruppo di risultati di ricerca non comporta l'aggiunta implicita del gruppo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi gruppo </p> </td> 
      <td colname="col2"> <p> Aggiungete il gruppo di risultati di ricerca come definito dai criteri di ricerca specificati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi gruppo </p> </td> 
      <td colname="col2"> <p> Rimuovere il gruppo di risultati di ricerca definito dai criteri di ricerca specificati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Push Single </p> </td> 
      <td colname="col2"> <p> Invia il singolo risultato di ricerca alla posizione selezionata. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi singolo </p> </td> 
      <td colname="col2"> <p> Aggiunge un singolo risultato di ricerca alla posizione selezionata. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi singola </p> </td> 
      <td colname="col2"> <p> Rimuove un singolo risultato di ricerca dal set di risultati della ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi tutti i risultati </p> </td> 
      <td colname="col2"> <p>Rimuove tutti i risultati dal set di risultati della ricerca. </p> <p> 
        <!-- Bug #3331637 The option is meant to be used in conjunction with other rule actions in order to create "canned landing pages" where we want to create a page's content solely by rule actions, and need to completely discard the "natural" results of the search. Given that the other options don't have any kind of "here's how/why you might use this", I don't see much point in breaking that precedent here.--> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Selezionate un banner diverso </p> </td> 
      <td colname="col2"> <p> Modifica il banner nell’area del banner selezionata. </p> <p>Questa opzione è disponibile quando fate clic con il pulsante destro del mouse su un banner nell’area di visualizzazione della pagina Web. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiunta di comandi per banner </p> </td> 
      <td colname="col2"> <p>Si applica solo ai modelli Adobe Dynamic Media Classic. </p> <p>Consente di modificare i parametri predefiniti utilizzati nel modello per banner. </p> <p>Consultate la tabella delle opzioni in <a scope="local" href="../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3" type="reference" format="dita"> Aggiunta di un banner tramite Adobe Dynamic Media Classic </a>. </p> <p>Consultate anche <a href="../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9" type="task" format="dita" scope="local"> Modifica di un banner con Adobe Dynamic Media Classic </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi banner </p> </td> 
      <td colname="col2"> <p> Rimuove il banner dall'area del banner selezionata; nessun banner viene visualizzato a meno che un'altra regola che imposta un banner non sovrascriva questa regola. </p> <p>Questa opzione è disponibile quando fate clic con il pulsante destro del mouse su un banner nell’area di visualizzazione della pagina Web. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elemento Facet push </p> </td> 
      <td colname="col2"> <p> Sposta un elemento all’interno di un facet nella posizione selezionata. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi zona </p> </td> 
      <td colname="col2"> <p> Rimuove una zona dalla pagina dei risultati della ricerca. </p> <p>Consultate anche l’azione Rimuovi facet di seguito. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zona Di Rivela </p> </td> 
      <td colname="col2"> <p> Mostra una zona nella pagina dei risultati della ricerca. </p> <p>Vedi anche l’azione Mostra facet di seguito. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi elemento facet </p> </td> 
      <td colname="col2"> <p> Rimuove un elemento facet da un facet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Reveal Facet Item (Mostra elemento facet) </p> </td> 
      <td colname="col2"> <p> Mostra un elemento facet specifico. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet di rivelazione </p> </td> 
      <td colname="col2"> <p> Rivela un facet specifico. Questa azione è preferibile rispetto all’azione Zona di visualizzazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi facet </p> </td> 
      <td colname="col2"> <p> Rimuove un facet specifico. Questa azione è preferibile rispetto all’azione Rimuovi zona. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   A seconda del pannello del generatore di regole attivo (non piegato), potete anche effettuare le seguenti operazioni per impostare attivatori e azioni.

   * Quando il **[!UICONTROL Triggers]** pannello è aperto - Nell’area del modello di presentazione della pagina Generatore di regole aziendali, fate clic con il pulsante destro del mouse su qualsiasi risultato di ricerca o facet di ricerca, quindi fate clic su **[!UICONTROL Add "result present" trigger]**.

      Nel pannello Triggers fare clic sulla &quot;X&quot; a sinistra di un trigger per rimuoverlo dall&#39;elenco dei trigger.

   * Quando il **[!UICONTROL Actions]** pannello è aperto - Nell’area del modello di presentazione della pagina Generatore di regole aziendali, fate clic con il pulsante destro del mouse su un risultato di ricerca. Fate clic **[!UICONTROL Add Result]**, **[!UICONTROL Remove Result]**, **[!UICONTROL Push to bottom]** o **[!UICONTROL Push to #`<n>`]** (dove `<n>` è un numero).


1. (Facoltativo) In qualsiasi pannello Generatore di regole business ( [!DNL Triggers], [!DNL Actions]o [!DNL Schedule]), effettuate una delle seguenti operazioni:

   * Nell&#39;area del modello di presentazione dell&#39;area della pagina Generatore regole business, fare clic con il pulsante destro del mouse su un banner, quindi fare clic **[!UICONTROL Select different banner]**. Nella **[!UICONTROL Pick Banner]** pagina, fate clic **[!UICONTROL Pick this banner]** sotto la miniatura del banner per aggiungerlo al modello di presentazione. Potete scegliere solo i banner che corrispondono alle dimensioni e all’area del banner originale nel modello di presentazione.

      L’azione Aggiungi banner viene aggiunta al [!DNL Actions] pannello.

   * Nell’area del modello di presentazione della [!DNL Business Rule Builder] pagina, fate clic con il pulsante destro del mouse su un banner modello Adobe Dynamic Media Classic i cui parametri desiderate modificare, quindi fate clic su **[!UICONTROL Add banner commands]**. Nella finestra di [!DNL Change Parameters] dialogo, impostare le opzioni dei parametri desiderate.

      Consultate la tabella delle opzioni in [Aggiunta di un banner tramite Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

      Clic **[!UICONTROL Save]**.

      Le modifiche ai parametri vengono aggiunte al [!DNL Actions] pannello.

      Consultate anche [Modifica di un banner con Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9).

   * Nell’area del modello di presentazione della pagina Generatore regole di business, fate clic con il pulsante destro del mouse sul banner da eliminare dalla pagina, quindi fate clic su **[!UICONTROL Remove banner]**. L’azione Rimuovi banner viene aggiunta al pannello Azioni.

1. (Facoltativo) Nel **[!UICONTROL Schedule]** pannello, effettuate una delle seguenti operazioni:

   * Fare clic **[!UICONTROL Run Indefinitely]** per eseguire la regola ogni volta che vengono soddisfatti i trigger associati. Questa è l&#39;opzione predefinita.
   * Fare clic **[!UICONTROL Fixed Schedule]**, quindi specificare la data e l&#39;ora di inizio e la data e l&#39;ora di fine per l&#39;esecuzione della regola ogni volta che viene soddisfatto il trigger associato.

1. Clic **[!UICONTROL Save Rule]**.
1. (Facoltativo) Nella [!DNL Business Rules] pagina, effettuare una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica di una regola business {#task_375CFA75D1D94D9E92A35DE1228E5087}

È possibile utilizzare Visual Rule Builder o Advanced Rule Builder per modificare le regole aziendali aggiunte.

**Per modificare una nuova regola business**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella [!DNL Business Rules] pagina, effettuate una delle seguenti operazioni:

   * Nella [!DNL Name] colonna fare clic sul nome di una regola business da modificare.

      La regola business viene aperta nell&#39;interfaccia predefinita specificata in **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL My Preferences]**.

   * Nell&#39;elenco a discesa, accanto al nome di una regola business che si desidera modificare, fare clic **[!UICONTROL Edit in advanced mode]** o **[!UICONTROL Edit in visual mode]**.

1. Nel campo di [!DNL Name] testo, digitare il nuovo nome della regola business.

   Non fate **[!UICONTROL Save Rule]** ancora clic. 1. Nella [!DNL Business Rule Builder] pagina, impostate gli attivatori e le azioni che desiderate utilizzare.

   Vedere la tabella delle opzioni in [Aggiunta di una nuova regola](../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7)business.
1. (Facoltativo) In qualsiasi **[!UICONTROL Business Rule Builder]** pannello ( [!DNL Triggers], [!DNL Actions]o [!DNL Schedule], effettuate una delle seguenti operazioni:

   * Nell’area del modello di presentazione della [!DNL Business Rule Builder] pagina, fate clic con il pulsante destro del mouse su un banner, quindi fate clic **[!UICONTROL Select different banner]**. Fate clic [!DNL Pick Banner page]sotto la miniatura del **[!UICONTROL Pick this banner]** banner per aggiungerlo al modello di presentazione. Potete scegliere solo i banner che corrispondono alle dimensioni e all’area del banner originale nel modello di presentazione.

      L’azione Aggiungi banner viene aggiunta al [!DNL Actions] pannello.

   * Nell’area del modello di presentazione della [!DNL Business Rule Builder] pagina, fate clic con il pulsante destro del mouse su un banner modello Adobe Dynamic Media Classic i cui parametri desiderate modificare, quindi fate clic su **[!UICONTROL Add banner commands]**. Nella finestra di [!DNL Change Parameters] dialogo, impostare le opzioni dei parametri desiderate.

      Consultate la tabella delle opzioni in [Aggiunta di un banner tramite Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

      Clic **[!UICONTROL Save]**.

      Le modifiche ai parametri vengono aggiunte al [!DNL Actions] pannello.

      Consultate anche [Modifica di un banner con Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9).

   * Nell’area del modello di presentazione della [!DNL Business Rule Builder] pagina, fate clic con il pulsante destro del mouse sul banner che desiderate eliminare dalla pagina, quindi fate clic su **[!UICONTROL Remove banner]**. L’azione Rimuovi banner viene aggiunta al [!DNL Actions] pannello.

1. (Facoltativo) Nel [!DNL Schedule] pannello, effettuate una delle seguenti operazioni:

   * Fare clic **[!UICONTROL Run Indefinitely]** per eseguire la regola ogni volta che vengono soddisfatti i trigger associati. Questa è l&#39;opzione predefinita.
   * Fare clic **[!UICONTROL Fixed Schedule]**, quindi specificare la data e l&#39;ora di inizio e la data e l&#39;ora di fine per l&#39;esecuzione della regola ogni volta che viene soddisfatto il trigger associato.

1. Clic **[!UICONTROL Save Rule]**.

   La [!DNL Business Rule Builder] pagina si chiude e si torna alla **[!UICONTROL Business Rule]** pagina. Le regole vengono visualizzate nella tabella. Fate clic sull’intestazione della **[!UICONTROL Modified]** colonna per ordinare le regole per data di modifica. 1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Copia di una regola business {#task_89F1879C71A54EE9B7454439302C03EC}

È possibile copiare una regola aziendale esistente da utilizzare come base per una nuova regola business che si desidera creare.

**Per copiare una regola business**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella **[!UICONTROL Business Rules]** pagina, nell&#39;elenco a discesa accanto al nome di una regola business che si desidera copiare, fare clic su **[!UICONTROL Copy rule]**.
1. Modificate la regola business copiata come di consueto.

   Consultate [Modifica di una regola](../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087)aziendale.

## Approvazione delle regole aziendali {#task_BD569D18BF664272B8692294C162E2C1}

È possibile attivare regole aziendali con stato WIP (Work In Progress) o sospeso.

**Per approvare le regole aziendali**

1. Scegliere **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella [!DNL Business Rules] pagina, utilizzando l&#39;intestazione della colonna di stato nella [!DNL Status] colonna della tabella delle regole business, ordinate le regole che hanno uno stato **[!UICONTROL WIP]** o **[!UICONTROL suspended]**.

   Utilizzare l&#39;intestazione della colonna della casella di controllo a sinistra della tabella per controllare tutte le regole visualizzate sulla pagina o solo quelle con uno stato **[!UICONTROL WIP]** o **[!UICONTROL suspended]**. 1. Nella barra dei menu accanto alla parte superiore della pagina, fate clic su **[!UICONTROL Approve]**.
1. Nella finestra di **[!UICONTROL Confirm Action]** dialogo fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Sospensione delle regole aziendali {#task_364E1FFB905141C08E306C8F1794A20E}

È possibile sospendere le regole aziendali con stato WIP (Work In Progress) o approvate.

Quando si sospende una regola, nell&#39;interfaccia utente viene indicato che la si è temporaneamente resa inattiva e si sta rinviando qualsiasi lavoro su di essa per un altro momento. È tuttavia possibile modificare una regola sospesa.

**Sospensione delle regole aziendali**

1. Scegliere **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Sulla [!DNL Business Rules] pagina, utilizzando lo stato nella colonna Stato della tabella delle regole aziendali, nella colonna a sinistra della tabella, verificare le regole con stato **[!UICONTROL WIP]**, o **[!UICONTROL approved]**.
1. Nella barra dei menu accanto alla parte superiore della pagina, fate clic su **[!UICONTROL Suspend]**.
1. Nella finestra di **[!UICONTROL Confirm Action]** dialogo fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Riprendere le regole aziendali {#task_E67D678C765B436EA2A3D6ADD7A49ABA}

È possibile riprendere le regole aziendali per riattivare una regola sospesa. Dopo aver ripreso la regola business, il suo stato è impostato su WIP (Work In Progress).

**Per riprendere le regole business**

1. Scegliere **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Sulla [!DNL Business Rules] pagina, utilizzando lo stato nella colonna Stato della tabella delle regole business, nella colonna a sinistra della tabella verificare le regole con lo stato **[!UICONTROL suspended]**.
1. Nella barra dei menu accanto alla parte superiore della pagina, fate clic su **[!UICONTROL Resume]**.
1. Nella finestra di [!DNL Confirm Action] dialogo fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica dell&#39;ordine di esecuzione delle regole aziendali {#task_FE3B1C17307F49B49050C2EC5A063991}

Potete riordinare le regole business per modificare l&#39;ordine in cui vengono eseguite sui modelli di presentazione.

Le regole aziendali vengono eseguite nell&#39;ordine in cui sono state definite; più alto è il numero d&#39;ordine di una regola, più tardi verrà eseguito nel processo, trumping regole precedenti. È possibile riordinare le regole immettendo un nuovo numero nella colonna Ordine della tabella nella [!DNL Business Rules] pagina. Potete anche utilizzare le regole di trascinamento per modificarne l&#39;ordine di esecuzione.

**Per modificare l&#39;ordine di esecuzione delle regole aziendali**

1. Scegliere **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella [!DNL Business Rules] pagina, nella tabella, effettuate una delle seguenti operazioni:

   * Fate clic sull&#39;intestazione della **[!UICONTROL Order]** colonna per ordinare le regole in ordine crescente o decrescente.
   * Nella **[!UICONTROL Order]** colonna, nel campo di testo a sinistra del nome di una regola business, digitare il numero di ordine che si desidera che venga eseguita.
   * Trascinare una riga di tabella nella posizione in cui si desidera eseguire la regola. Tutti i numeri di ordine vengono aggiornati in base al nuovo ordine in cui vengono eseguite le regole.

1. Clic **[!UICONTROL Save Changes]**.

   Le regole aziendali verranno ora eseguite nell&#39;ordine specificato. L&#39;eccezione è rappresentata dalla presenza di una regola business di reindirizzamento specificata. Se e quando la regola business di reindirizzamento viene attivata o colpita, l&#39;elaborazione della regola business si arresta per consentire il reindirizzamento.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione delle regole business {#task_AE37B42412044541BCC6D46CF8793DFF}

È possibile eliminare le regole business il cui stato è WIP, sospeso o approvato, utilizzando il menu a discesa Azioni di massa.

**Per eliminare le regole business**

1. Scegliere **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]** dal menu del prodotto.
1. Nella [!DNL Business Rules] pagina, effettuate una delle seguenti operazioni:

   * Utilizzate l&#39;intestazione della colonna della casella di controllo per controllare tutte le regole attualmente visualizzate sulla pagina.
   * Selezionare solo le regole aziendali da eliminare, in base allo stato nella colonna Stato della tabella.

1. Nell’elenco a [!DNL Bulk Actions] discesa, fate clic su **[!UICONTROL Delete]**.
1. Nella finestra di [!DNL Confirm Action] dialogo fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.
