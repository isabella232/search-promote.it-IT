---
description: Puoi utilizzare i dizionari per gestire una raccolta di dizionari e i relativi sinonimi e ipponimi associati.
solution: Target
title: Informazioni sui dizionari
topic: Linguistics,Site search and merchandising
uuid: d4463896-30fe-4385-a283-c930c8264a02
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '2462'
ht-degree: 1%

---


# Informazioni sui dizionari{#about-dictionaries}

Puoi utilizzare i dizionari per gestire una raccolta di dizionari e i relativi sinonimi e ipponimi associati.

## Utilizzo dei dizionari {#concept_B8028B71EC8144669614C64578EDB034}

I sinonimi sono parole che hanno lo stesso significato o lo stesso significato come pantaloni, jeans, pantaloni e pantaloni, e pantaloni, o comprare, acquistare, acquistare, acquistare, acquistare e ordinare.

Gli ipponimi sono sinonimi unidirezionali e forniscono una soluzione quando i sinonimi sono inappropriati. Ad esempio, il termine di ricerca principale di un sito di abbigliamento al dettaglio è &quot;pantaloni&quot;. Tuttavia, i jeans non vengono visualizzati nei risultati della ricerca. In tal caso, è possibile utilizzare un ipponimo per associare i jeans con i pantaloni, ma per consentire a una ricerca di jeans di restituire solo i jeans. Utilizzare gli ipponimi anche per fornire un abbinamento per prodotti discontinui o termini competitivi. Questa strategia assicura un impatto minimo su altri risultati di ricerca. Ad esempio, se il prodotto &quot;S2000&quot; è discontinuo e il &quot;S3000&quot; è il suo successore, utilizza un ipponimo invece di un sinonimo per garantire che i risultati della ricerca per &quot;S3000&quot; non includano i risultati randagi &quot;S2000&quot;.

I sinonimi e gli ipponimi consentono ai clienti di trovare risultati di ricerca rilevanti quando immettono termini di corrispondenza non esatti che non esistono sulle pagine web. Ad esempio, se la parola &quot;pantaloni&quot; viene utilizzata in tutto il sito web, è possibile creare un sinonimo che associa &quot;pantaloni&quot; e &quot;pantaloni&quot;. A sua volta, quando i clienti cercano &quot;pantaloni&quot;, vengono restituiti risultati di ricerca relativi ai pantaloni.

I sinonimi e gli ipponimi sono raggruppati come Dizionari di dominio. Si tratta di dizionari speciali creati per un tema o uno scopo specifico.

Nella pagina Menu dizionario sono elencati tutti i dizionari di dominio attualmente definiti dal tuo account. In questa pagina principale è possibile rinominare, modificare, eliminare o abilitare e disabilitare i dizionari di dominio.

## Informazioni sul sinonimo e la notazione dell&#39;ippogramma {#section_B459CCB850974F4FB16A14E489BBBEC0}

L&#39;immagine seguente è un esempio di un gruppo di termini con relazioni sia sinonimo sia ipponico.

![](assets/synonym1.png)

Sei relazioni principali sinonimo sono esplicitamente definite. Ogni termine è separato da segni uguali (=).

* &quot;Auto&quot; è un sinonimo di automobile.
* &quot;Sedan&quot; è un sinonimo di salone.
* &quot;Station wagon&quot; è un sinonimo di proprietà.
* &quot;ASP&quot; è un sinonimo di Active Server Pages e Application Service Provider.
* &quot;Purchase&quot;, &quot;buy&quot; e &quot;procure&quot; sono sinonimi gli uni degli altri.
* &quot;US&quot;, &quot;USA&quot; e &quot;Stati Uniti d&#39;America&quot; sono sinonimi gli uni degli altri.

Le righe che contengono una singola parola sono sinonimi semplici. Le righe con alberi espandibili formano relazioni ipponiche. Nell&#39;esempio, il secondo albero definisce la berlina, il salone, il vagone della stazione e la tenuta come ipponimi di auto e automobile. Viceversa, auto e automobili sono ipernimi del resto dei termini nell&#39;albero.

Il terzo albero definisce auto e moto come ipponimi di veicolo.

È possibile includere più di un acronimo e/o espansione di più parole in ciascun sinonimo, come visto nel sinonimo &quot;US&quot; di cui sopra. Quando una parola o un acronimo ha diversi significati, crea un sinonimo per ogni significato, come nell&#39;esempio &quot;ASP&quot; di cui sopra. Aggiungendo più sinonimi si assicura che una ricerca per &quot;Application Service Provider&quot;, ad esempio, non restituisca i risultati di ricerca per &quot;Active Server Pages&quot;.

Gli ipponimi non si espandono con altri ipponimi. Gli ipponimi si espandono, al massimo, a un livello con i loro sinonimi. Ad esempio, una ricerca per &quot;veicolo&quot; restituisce i risultati per &quot;auto&quot; e &quot;automobile&quot;, ma non restituisce i risultati per &quot;berlina&quot; e &quot;carro della stazione&quot;.

## Informazioni sulla ricerca di termini tra dizionari {#section_28E7F80CE68D4481BBF4F51EED237C67}

È possibile cercare ipmi e sinonimi in tutti i dizionari aggiunti. Questa funzione è utile se desideri modificare o eliminare un termine specifico che può esistere in più dizionari. Ogni dizionario con i risultati corrispondenti viene visualizzato con i relativi set di parole corrispondenti. Se la query restituisce più di 1000 set, o alberi, vengono presentati solo i primi 1000.

Consultare [Ricerca in tutti i dizionari](../c-about-linguistics-menu/c-about-dictionaries.md#task_8D2BACC6F9B4487FA82367CBEDEE306F).

Vedere [Modifica di un dizionario](../c-about-linguistics-menu/c-about-dictionaries.md#task_7B349B2D385048D7A06E754FAB75316A).

## Informazioni sulla configurazione di un dizionario come dizionario radice {#section_B859E2E957674F558AC6F8D05A0ED190}

Lo stemming, che è la capacità di cercare nella radice di una parola che può avere più terminazioni, può funzionare in una delle tre modalità seguenti: Dizionari di dominio, Forms di Word alternativo predefinito e Nessuno.

Consulta [Informazioni su parole e lingua](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79).

Le informazioni seguenti presuppongono che l’account sia **[!UICONTROL Alternative Word Forms]** impostato su **[!UICONTROL Domain Dictionaries]**, in modo da poter configurare dizionari di dominio specifici come origine degli steli.

Puoi trasformare qualsiasi dizionario di dominio in un &quot;dizionario che sorge&quot;. I suoi sinonimi e ipponimi continuano ad espandersi come previsto, ma con effetti collaterali aggiuntivi. Con qualsiasi termine in comune trovato in un altro dizionario, o anche se stesso, unisce il suo gruppo di parole con quei sinonimi o ipponimi. Potete immaginarlo come un altro livello di espansione delle parole.

Senza stemming, sinonimi e ipponimi devono essere verbosi e completi, elencando ogni parola pertinente come membro.

Di seguito è riportato un esempio di sinonimi e di assenza di stemming:

* Sinonimi: jog = running
* Una query per &quot;jog&quot; restituisce documenti con le parole &quot;running&quot; e &quot;jog&quot;.
* Una query per &quot;eseguire&quot; restituisce gli stessi documenti di &quot;jog&quot;.
* Nel risultato della query mancano pagine web senza &quot;jog&quot; e &quot;running&quot;, ma con altri moduli di parole come &quot;run&quot; ed &quot;run&quot;.

In questo esempio, una parola di query non si espande a meno che non sia membro di un sinonimo o di un hyponym specifico.

Di seguito è riportato un esempio di sinonimi e stemmi:

* Sinonimi: jog = running
* Voce sinonimo di un dizionario radice: running = run = run
* Una query per &quot;jog&quot; o &quot;running&quot; restituisce tutte le pagine web con le parole &quot;run&quot;, &quot;running&quot;, &quot;run&quot; e &quot;jog&quot;.
* Una query per &quot;run&quot; e &quot;run&quot; restituisce gli stessi risultati o risultati simili.

In questo esempio, un sinonimo di un dizionario mobile ha la capacità di unire il proprio gruppo di parole equivalenti con qualsiasi altro sinonimo o ipponimo in qualsiasi altro dizionario che abbia almeno un termine in comune.

La designazione di troppi dizionari con troppe parole può avere ramificazioni delle prestazioni. È consigliabile designare i dizionari di dominio come dizionari di origine moderata. La suddivisione può anche creare espansioni di parole impreviste durante il tempo di ricerca e complicare il processo di debug e di tracciamento delle espansioni di parole.

Consultare [Configurazione di un dizionario come dizionario di origine](../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074).

## Aggiunta di un nuovo dizionario {#task_F31AC6723E894C4F91D12AB2A4CEE9FB}

È possibile aggiungere un nuovo dizionario di sinonimi e ipponimi per aiutare i clienti a trovare risultati di ricerca rilevanti. Questa funzione è particolarmente utile quando i clienti immettono termini di corrispondenza non esatti che potrebbero non esistere nelle pagine web.

Vedere anche [Aggiunta di una nuova regola business](../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7).

**Per aggiungere un nuovo dizionario**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto.
1. Nella pagina **[!UICONTROL Dictionary Menu]**, fai clic su **[!UICONTROL Add New Dictionary]**.
1. Nella pagina **[!UICONTROL Dictionary]** , immetti il nome del nuovo dizionario nel campo **[!UICONTROL Name]** .
1. Clic **[!UICONTROL Add Synonyms]**.
1. Nella finestra di dialogo **[!UICONTROL Add Terms]** eseguire una delle operazioni seguenti:

   * Per aggiungere i sinonimi, immettere due o più termini nel campo di testo principale, separando ogni parola o frase con un segno uguale (=). Ad esempio, pantaloni = pantaloni = pantaloni = pantaloni.
   * Per aggiungere gli ipponimi, immettere un termine ipernimo nel campo di testo principale. Fare clic su **[!UICONTROL Add Hyponym]**, quindi immettere un ipponimo relativo all&#39;ipernimo immesso. Per esempio, &quot;sedan&quot;, &quot;saloon&quot;, &quot;station wagon&quot; e &quot;estate&quot; potrebbero essere ipponimi di &quot;auto&quot; e &quot;automobile&quot; (entrambi ipernimi) come mostrato di seguito.

      ![](assets/synonym2.png)

      Le voci dell&#39;ipponimo possono anche formare sinonimi come &quot;sedan&quot; e &quot;saloon&quot;.

1. Clic **[!UICONTROL Save]**.
1. Esegui una delle operazioni seguenti:

   * Ripeti i passaggi 4-6 per aggiungere altri sinonimi e ipponimi.
   * Procedi al passaggio successivo.

1. Per visualizzare in anteprima i risultati delle modifiche, fai clic su **[!UICONTROL regenerate your staged site index]** per ricreare l’indice del sito web in staging.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto, quindi effettuare una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Abilitazione o disabilitazione di un dizionario {#task_EC282EA0846942F6913918EA8218220B}

Le relazioni di ogni parola vengono generate al momento dell&#39;indicizzazione del sito web. Prima dell’operazione di indicizzazione successiva, puoi attivare o disattivare qualsiasi dizionario aggiunto.

**Per abilitare o disabilitare un dizionario**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto.
1. Nella pagina **[!UICONTROL Dictionary Menu]**, sotto la colonna **[!UICONTROL Enabled]** della tabella, effettuare una delle seguenti operazioni:

   * Selezionare la casella di un dizionario che si desidera attivare e che è stato indicizzato.
   * Deseleziona la casella di un dizionario che desideri disattivare e che non è indicizzato.

1. Clic **[!UICONTROL Save Changes]**.
1. Per visualizzare in anteprima i risultati delle modifiche, fai clic su **[!UICONTROL regenerate your staged site index]** per ricreare l’indice del sito web in staging.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto, quindi effettuare una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di un dizionario {#task_7B349B2D385048D7A06E754FAB75316A}

È possibile modificare o eliminare i gruppi sinonimi e hyponym che costituiscono un dizionario specifico.

<!-- 

t_editing_a_dictionary.xml

 -->

È inoltre possibile utilizzare **[!UICONTROL Find]** per individuare sinonimi e ippoimi specifici da modificare o eliminare in tutti i dizionari.

**Per modificare un dizionario**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto.
1. Esegui una delle operazioni seguenti:

   * Nella tabella della pagina [!DNL Dictionary Menu] fare clic sul nome di un singolo dizionario con collegamento ipertestuale di cui si desidera modificare o eliminare i termini.
   * Nella pagina [!DNL Dictionary Menu], digitare un termine che si desidera individuare nel campo di testo **[!UICONTROL Find]** in tutti i dizionari, quindi fare clic su **[!UICONTROL Find]**.

      Nella pagina [!DNL Find in Dictionaries], utilizza gli elenchi a discesa associati per impostare le opzioni di perfezionamento desiderate.

      <table> 
      <thead> 
        <tr> 
        <th colname="col1" class="entry"> <p>Opzione </p> </th> 
        <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
        </tr> 
      </thead>
      <tbody> 
        <tr> 
        <td colname="col1"> <p>Trova </p> </td> 
        <td colname="col2"> <p>Consente di immettere il termine che si desidera cercare in tutti i dizionari. </p> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p>Elenco a discesa Corrispondenza </p> </td> 
        <td colname="col2"> <p>Consente di scegliere tra i seguenti quattro tipi di corrispondenza: 
        <ul id="ul_D656F159677946938050115F610EEF4B"> 
        <li id="li_2D6B302E021A4CE7A47F028812633EDC"> <span class="uicontrol"> Corrispondenza esatta  </span> <p>La query deve avere una corrispondenza esatta con un hyponym o sinonimo. </p> </li> 
        <li id="li_30AD5976E43041E98190F4757E821092"> <span class="uicontrol"> Contiene testo  </span> <p>La query richiede solo una corrispondenza della sottostringa; una corrispondenza all'interno di un ipponimo o sinonimo. </p> </li> 
        <li id="li_9BF911EFB54345BB82679BDE51DDF8AF"> <span class="uicontrol"> Inizia con  </span> <p>La query viene confrontata solo con l’inizio di ciascun ippogramma e sinonimo. </p> </li> 
        <li id="li_CB791C7F5B5A4496B329ED505E7D97BC"> <span class="uicontrol"> Corrispondenza  </span> <p>La query viene confrontata con ogni parola proveniente da un sinonimo o da un ipponimo, ma la parola deve corrispondere esattamente. </p> </li> 
        </ul> </p> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p>Elenco a discesa Dizionario abilitato/disabilitato </p> </td> 
        <td colname="col2"> <p>Consente di scegliere tra le seguenti opzioni: 
        <ul id="ul_EBBD3F3A2D854952A35CBDDBECB40958"> 
        <li id="li_7F5654C284BE485EAC9B000A663C6C60"> <span class="uicontrol"> Dizionari abilitati e disabilitati  </span> <p>Cerca il termine specificato nei dizionari abilitati e disabilitati. </p> </li> 
        <li id="li_4A83EECF38044287A923EC0AAF639079"> <span class="uicontrol"> Solo dizionari abilitati  </span> <p>La ricerca dei soli dizionari abilitati è utile per il debug dell'indice corrente. </p> </li> 
        </ul> </p> <p>Consulta <a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_EC282EA0846942F6913918EA8218220B" type="task" format="dita" scope="local"> Abilitazione o disabilitazione di un dizionario </a>. </p> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p>Elenco a discesa Staged/Live </p> </td> 
        <td colname="col2"> <p>Consente di scegliere tra le seguenti opzioni: 
        <ul id="ul_BD0733A30E6B470E942B21F499A4373B"> 
        <li id="li_F9A8C39C22EA4FBF86536F5924ED973C"> <span class="uicontrol"> Dizionari in tempo/in tempo reale  </span> <p>Cerca il termine specificato nei dizionari in tempo reale e in fase di esecuzione. Tuttavia, cerca solo la versione in staging del dizionario se esiste. Se la versione di staging non esiste, cerca la versione live del dizionario. </p> </li> 
        <li id="li_DB0944DB18564269AA10676BDFDB0460"> <span class="uicontrol"> Dizionari live  </span> <p>Cerca il termine specificato solo nei dizionari live. </p> </li> 
        </ul> </p> </td> 
        </tr> 
      </tbody> 
      </table>

1. Nella tabella, effettuare una delle seguenti operazioni:

   * Fare clic su ![](assets/icon_edit.gif) associato al termine che si desidera aggiornare. Nella finestra di dialogo **[!UICONTROL Edit Terms]** modificare i termini desiderati. Al termine, fai clic su **[!UICONTROL Save]**.

   * Fare clic su ![](assets/icon_delete.gif) associato al termine che si desidera rimuovere. Nella finestra di dialogo **[!UICONTROL Delete Terms]** fare clic su **[!UICONTROL Delete]**. Assicurati di eliminare il termine corretto; non è disponibile alcuna finestra di dialogo di conferma dell’eliminazione.

1. Per visualizzare in anteprima i risultati delle modifiche, fai clic su **[!UICONTROL regenerate your staged site index]** per ricreare l’indice del sito web in staging.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto, quindi effettuare una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ridenominazione di un dizionario {#task_7F1F372B337B4853BFA2A60AD267B092}

Puoi modificare il nome di un dizionario aggiunto.

<!-- 

t_renaming_a_dictionary.xml

 -->

Se si imposta l&#39;opzione **[!UICONTROL Alternate Word Forms]** su **[!UICONTROL Domain Dictionaries]** in **[!UICONTROL Words & Language]**, viene utilizzata l&#39;opzione **[!UICONTROL Configure]** invece di **[!UICONTROL Rename]**.

Consulta [Informazioni su parole e lingua](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79).

**Per rinominare un dizionario**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto.
1. Nella pagina **[!UICONTROL Dictionary Menu]**, sotto la colonna **[!UICONTROL Actions]** della tabella, effettuare una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL Rename]** per il dizionario associato di cui si desidera modificare il nome.

      Nella finestra di dialogo **[!UICONTROL Rename Dictionary]**. nel campo **[!UICONTROL Name]** , immetti il nuovo nome del dizionario.

      Clic **[!UICONTROL Rename File]**.

   * Fare clic su **[!UICONTROL Configure]** per il dizionario associato di cui si desidera modificare il nome.

      Nella finestra di dialogo **[!UICONTROL Configure Dictionary]**. nel campo **[!UICONTROL Name]** , immetti il nuovo nome del dizionario.

      Clic **[!UICONTROL Save Configuration]**.

1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configurazione di un dizionario come dizionario radice {#task_541E8453A12F4A8E89CF6F595469F074}

È possibile impostare un dizionario su modalità di stemming avanzata per sfruttare le parole che si trovano nelle ricerche.

<!-- 

t_configuring_a_dictionary_as_a_stemming_dictionary.xml

 -->

Tale modalità restituisce pagine web che corrispondono a varianti di ciò che i clienti stanno cercando.

Vedere [Informazioni sui dizionari](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034).

Consulta [Informazioni su parole e lingua](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79).

**Per configurare un dizionario come dizionario di origine**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]** dal menu del prodotto.
1. Nella pagina [!DNL Words & Languages], seleziona **[!UICONTROL Domain Dictionaries]** dall’elenco a discesa **[!UICONTROL Alternate Words Forms]**.

   Qualsiasi dizionario di dominio impostato come dizionario di origine (vedere il passaggio 7 seguente) viene utilizzato come origine di moduli di parole alternative.

1. Clic **[!UICONTROL Save Changes]**.
1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto.
1. Nella pagina [!DNL Dictionaries Menu], nella colonna **[!UICONTROL Actions]** della tabella, fare clic su **[!UICONTROL Configure]** per un dizionario associato che si desidera impostare come dizionario di origine.
1. Nella finestra di dialogo **[!UICONTROL Configure Dictionary]**, selezionare **[!UICONTROL Advanced Stemming Mode]** dall’elenco a discesa **[!UICONTROL Yes]**.
1. Clic **[!UICONTROL Save Configuration]**.
1. Fai clic su **[!UICONTROL regenerate your staged site index]** per ricostruire l&#39;indice del sito web in staging.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto, quindi effettuare una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ricerca in tutti i dizionari {#task_8D2BACC6F9B4487FA82367CBEDEE306F}

È possibile cercare ipmi e sinonimi in tutti i dizionari aggiunti alla ricerca/merchandising del sito.

<!-- 

t_searching_across_dictionaries.xml

 -->

Questa funzione è utile se desideri modificare o eliminare un termine specifico che può esistere in più dizionari. Ogni dizionario con i risultati corrispondenti viene visualizzato con i relativi set di parole corrispondenti. Se la query restituisce più di 1000 set, o alberi, vengono presentati solo i primi 1000.

Vedere [Modifica di un dizionario](../c-about-linguistics-menu/c-about-dictionaries.md#task_7B349B2D385048D7A06E754FAB75316A).

**Ricerca tra dizionari**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto.
1. Nella pagina [!DNL Dictionary Menu], digitare un termine che si desidera individuare nel campo di testo **[!UICONTROL Find]** in tutti i dizionari, quindi fare clic su **[!UICONTROL Find]**.
1. Nella pagina [!DNL Find in Dictionaries], utilizza gli elenchi a discesa associati per impostare le opzioni di perfezionamento desiderate.

   Vedere [Modifica di un dizionario](../c-about-linguistics-menu/c-about-dictionaries.md#task_7B349B2D385048D7A06E754FAB75316A).
1. (Facoltativo) Utilizza il menu a discesa **[!UICONTROL Show]** per specificare il numero massimo di risultati da visualizzare per pagina.

## Eliminazione di un dizionario {#task_DBAAEE624BC14D2590444B0B7869ECCA}

È possibile eliminare i dizionari non più necessari o utilizzati.

<!-- 

t_deleting_a_dictionary.xml

 -->

Se elimini un dizionario attivo, questo viene messo in scena per l&#39;eliminazione. Se elimini un dizionario che è in fase di staging, questo viene eliminato immediatamente.

Assicurati di eliminare un dizionario di cui hai più bisogno; non è disponibile alcuna funzione di cronologia per ripristinare l’eliminazione.

**Per eliminare un dizionario**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]** dal menu del prodotto.
1. Nella pagina [!DNL Dictionary Menu], nella colonna **[!UICONTROL Actions]** della tabella fare clic su **[!UICONTROL Delete]** per il dizionario associato che si desidera rimuovere.
1. Nella finestra di dialogo **[!UICONTROL Delete Dictionary]**. fai clic su **[!UICONTROL Yes]** per confermare l’eliminazione.
1. (Facoltativo) Se hai eliminato un dizionario live, effettua una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

