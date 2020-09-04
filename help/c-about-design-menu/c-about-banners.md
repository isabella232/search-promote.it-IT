---
description: Potete utilizzare i banner per gestire gli annunci banner sul vostro sito Web.
seo-description: Potete utilizzare i banner per gestire gli annunci banner sul vostro sito Web.
seo-title: I banner
solution: Target
title: I banner
topic: Design,Site search and merchandising
uuid: 653b567d-5cf3-41a0-a260-a6912d0fd20d
translation-type: tm+mt
source-git-commit: 552f93f1f630c64bbe3d5c8a87c4f5895ae6868c
workflow-type: tm+mt
source-wordcount: '4810'
ht-degree: 1%

---


# I banner {#about-banners}

Potete utilizzare i banner per gestire gli annunci banner presenti sul sito Web.

## Utilizzo dei banner {#concept_5BBE01FEC6134393B43CC917C8CC64DA}

<!-- 

c_about_banners.xml

 -->

Esistono due metodi per aggiungere annunci banner al sito Web.

Il primo metodo consiste nell’aggiungere i banner tramite Target, Search&amp;Promote. I banner sono snippet di codice HTML visualizzati al momento della ricerca nel sito Web da parte di un cliente. Il banner può includere testo o immagine in formato GIF, JPEG o PNG, oppure una combinazione di entrambi. Potete scegliere tra dimensioni predefinite o definire dimensioni personalizzate per adattare la pagina. Il codice HTML utilizzato per visualizzare il banner può anche specificare elementi quali lo stile del font da utilizzare e il bordo. Questo metodo di aggiunta di un banner offre funzionalità di base e non richiede software aggiuntivo.

Il secondo metodo consiste nell’utilizzare  Adobe Dynamic Media Classic, un servizio di gestione e pubblicazione di contenuti multimediali dinamici. Un account  Adobe Dynamic Media Classic valido consente di gestire e distribuire i contenuti dei banner direttamente a Target, tramite l&#39;utilizzo di Dynamic Media Classic. Nella ricerca del sito/merchandising, puoi configurare l’accesso al tuo account Dynamic Media Classic. Quindi aprite il browser per contenuti multimediali dinamici Classic e scegliete una risorsa multimediale dinamica da usare come banner.

>[!NOTE]
>
>Prima di poter utilizzare le risorse multimediali dinamiche come banner nella ricerca del sito/merchandising, le risorse vengono caricate e preparate per la pubblicazione in Scene7 Publishing System. Potete caricare le risorse dall’interno della ricerca nel sito/merchandising e prepararle automaticamente per la pubblicazione in Scene7 Publishing System. In alternativa, potete caricare e pubblicare tutte le risorse dall’interno di Scene7 Publishing System.

## Integrazione dei banner con  Adobe Scene7 Publishing System {#section_D4D7ADEA6A6348E68EDA138E184FE579}

Potete utilizzare i tipi di risorse Dynamic Media Classic come banner nella ricerca e merchandising del sito, incluse immagini, banner dinamici e modelli, ad esempio modelli di immagini o Flash.

I modelli vengono creati in modo dinamico e indirizzati a file di immagini con più livelli, come i file con più livelli in applicazioni di modifica delle immagini come  Adobe Photoshop®. A differenza di un file immagine statico, un modello può includere parametri. Tramite i parametri, potete personalizzare le proprietà variabili dell’immagine e il contenuto dell’immagine.

>[!NOTE]
>
>Potete anche creare modelli da layout utilizzando Pubblicazione modelli in Scene7 Publishing System e file da  Adobe Illustrator e  Adobe InDesign.

Consultate Pubblicazione [di](https://help.adobe.com/en_US/scene7/using/WSFBFBAD30-2694-4b18-B7CE-894F9FC5CDDF.html) modelli nella guida utente di Dynamic Media Classic (Scene7).

Un modello può contenere un numero qualsiasi di livelli di immagine e di testo. Potete convertire un file statico contenente livelli, ad esempio un file PSD con livelli, in un modello oppure creare modelli in Dynamic Media Classic. Potete creare livelli di testo nei modelli utilizzando i font caricati in Scene7 Publishing System. Dopo aver aggiunto del testo a un modello, potete formattarlo modificandone giustificazione, font, dimensione font e colore.

Utilizzando la schermata Parametri di Dynamic Media Classic, potete convertire qualsiasi aspetto di un modello in un parametro indirizzabile. Così facendo, potete cambiare l’immagine a livelli da usare o il valore di testo da usare nel modello. I parametri vengono passati con la stringa URL, consentendo di modificare qualsiasi parametro per personalizzare in modo dinamico l’immagine di risposta generata dal server immagini.

Per ulteriori informazioni sull’utilizzo di Dynamic Media Classic, potete creare modelli e parametrizzare le proprietà dei livelli in modo da poterli usare nei banner.

Consultate Funzioni di base dei [modelli](https://help.adobe.com/en_US/scene7/using/WS60B68844-9054-4099-BF69-3DC998A04D3C.html) nella guida utente di Dynamic Media Classic (Scene7).

**Caricamento e pubblicazione delle risorse**

Prima di poter utilizzare le risorse per i banner nella ricerca e nel merchandising del sito, è necessario caricarle e pubblicarle in Dynamic Media Classic. Questo prerequisito include anche tutte le risorse utilizzate da un modello di immagine o un modello di Flash. Usate il vostro account Dynamic Media Classic per caricare e pubblicare risorse digitali. In alternativa, potete usare la ricerca nel sito/merchandising per caricare una risorsa digitale e farla pubblicare automaticamente da Dynamic Media Classic in base alle impostazioni di caricamento. Se tentate di scegliere una risorsa non ancora caricata e pubblicata, riceverete una notifica nell’interfaccia utente e potrete caricarla prima di procedere.

Per ulteriori informazioni sul caricamento e la pubblicazione di risorse digitali, utilizzate Scene7 Publishing System.

Consultate [Caricare e pubblicare risorse](https://help.adobe.com/en_US/scene7/using/WS3673AD39-098B-4f08-8A24-CA51261B7366.html) nella guida utente di Dynamic Media Classic (Scene7).

>[!NOTE]
>
>Per usare la funzionalità di caricamento nel visualizzatore di risorse Dynamic Media Classic, accertatevi che l’account Dynamic Media Classic utilizzato abbia già il ruolo di &quot;Amministratore società SPS&quot;.

Consultate Impostazione [](https://help.adobe.com/en_US/scene7/using/WS662101DF-D697-47a7-A7D8-B52FD8E94438.html) amministrazione nella guida utente di Dynamic Media Classic (Scene7).

**Modifica dei parametri dei modelli Dynamic Media Classic in un banner tramite le regole aziendali**

Se avete aggiunto una risorsa Dynamic Media Classic come banner, potete utilizzarla [!DNL Visual Rule Builder] in [!DNL Business Rules] per aggiungerla a qualsiasi area del banner del sito Web. Ad esempio, potete aggiungere il banner alle pagine dei risultati di ricerca, come qualsiasi altro banner. Potete inoltre ignorare i valori dei parametri predefiniti nei modelli Dynamic Media Classic personalizzandoli in base alle esigenze specifiche. Questo tipo di funzionalità consente di personalizzare i modelli Dynamic Media Classic con diversi messaggi di marketing e collegamenti ipertestuali verso endpoint diversi.

Vedere anche [Aggiunta di una nuova regola](../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7)business.

Vedere anche [Modifica di una regola](../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087)aziendale.

## Aggiunta di un banner {#task_549D02B5F73B4158B105A94E39D937B7}

Potete utilizzare [!DNL Banners] per gestire gli annunci banner e la posizione in cui questi vengono inseriti nel sito Web. Quando aggiungete un banner, fate riferimento esternamente all’immagine tramite snippet di codice HTML visualizzati in fase di ricerca.

<!-- 

t_adding_a_new_banner.xml

 -->

Se disponete di un account  Adobe Dynamic Media Classic valido, potete aggiungere i banner pubblicitari tramite Scene7 Publishing System.

Consultate [Aggiunta di un banner tramite  Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

Consultate [Configurazione dell’accesso al vostro account](../c-about-settings-menu/c-about-account-options-menu.md#task_CEFF88C2033D41D0B2FE86C435EDAC6D) Adobe Dynamic Media Classic.

**Per aggiungere un banner**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Banners]** dal menu del prodotto.
1. Nella [!DNL Banners] pagina, nell’elenco a **[!UICONTROL Add Banner]** discesa, selezionare **[!UICONTROL HTML code]**.
1. Nella finestra di [!DNL Add Banner] dialogo, impostare le opzioni desiderate.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Obbligatorio. Identifica il nome del banner. Il nome viene utilizzato per fare riferimento al banner quando lo si aggiunge in Visual Rule Builder in Business Rules. Il nome non viene visualizzato nel banner stesso. </p> <p>Consultate <a href="../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7" type="task" format="dita" scope="local"> Aggiunta di una nuova regola business.</a> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>HTML banner </p> </td> 
      <td colname="col2"> <p> Consente di incollare il codice HTML associato al banner. </p> <p>Qualsiasi codice HTML è accettabile, incluso il codice CSS circondato da <code>
          &lt;style&gt; 
        </code> tag o il codice JavaScript circondato da <code>
          &lt;script&gt; 
        </code> tag. Ad esempio, il seguente blocco di codice è relativo a un banner di testo del tipo Orizzontale superiore: <code> &lt;div&nbsp;style="width:&nbsp;684px;&nbsp;background-image:&nbsp;url('https://www.brough.com/blackb.gif');&nbsp; 
          padding-top:&nbsp;10px;&nbsp;padding-bottom:&nbsp;10px;&nbsp;color:&nbsp;white;&nbsp;font-family:&nbsp;verdana;&nbsp; 
          text-align:&nbsp;center;&nbsp;font-size:&nbsp;20px;"&gt;&nbsp;Sound&nbsp;Study&nbsp;ships&nbsp;free!&nbsp;&lt;/div&gt; </code>Nell'esempio seguente, il blocco di codice è relativo a un'immagine iniziale completa: <code> &lt;img&amp;nbsp;src='https://geometrixx.com/images/GEOAds/geometrixx-beauty-home-01.jpg'&amp;nbsp;border="0"&amp;nbsp;/&gt; </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> <p>Specifica i seguenti tipi di banner: 
        <ul id="ul_6423AEDB9E664049989EB529D63C4A62"> 
          <li id="li_BF6CD60B3ED748D49CFFB9C5D607661C"> <span class="uicontrol"> [nuovo tipo] </span> <p>Consente di specificare il tipo di banner desiderato, incluse le dimensioni e il nome. </p> </li> 
          <li id="li_1A29AB22AD644E60A12298187B5E898E"> <span class="uicontrol"> Spinta completa </span> <p>Le dimensioni impostate per questo tipo di banner sono 680 pixel di larghezza e 650 pixel di altezza. Facoltativamente potete specificare il nome del tipo o accettare il nome predefinito corrispondente al nome del tipo di banner stesso. </p> </li> 
          <li id="li_2BE06D013CB54DDE851051BFC038BB57"> <span class="uicontrol"> Piano orizzontale </span> <p> Il banner è posizionato nella parte superiore del sito Web. Questo tipo è utile se intendete aggiungere collegamenti ipertestuali a sinistra o a destra del banner. Le dimensioni impostate per questo tipo di banner sono 468 pixel di larghezza e 60 pixel di altezza. Facoltativamente potete specificare il nome del tipo o accettare il nome predefinito corrispondente al nome del tipo di banner stesso. </p> </li> 
          <li id="li_EC35AB92234749F08AA8A9BD26D0EA8D"> <span class="uicontrol"> Piano orizzontale - Larghezza intera </span> <p>Questo tipo è l'impostazione predefinita quando si aggiunge un nuovo banner. Il banner viene posizionato nella parte superiore del sito Web e occupa la larghezza totale della pagina. Le dimensioni impostate per questo tipo di banner sono 670 pixel di larghezza e 150 pixel di altezza. Facoltativamente potete specificare il nome del tipo o accettare il nome predefinito corrispondente al nome del tipo di banner stesso. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tag </p> </td> 
      <td colname="col2"> <p>Aggiunge tag o "parole chiave" da associare al banner. Se utilizzate molti banner, l’aggiunta di tag può facilitare l’ottimizzazione della ricerca sui banner e consentire di individuare rapidamente il banner corretto in base alle vostre esigenze. Potete inoltre eliminare eventuali tag aggiunti. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica di un banner {#task_D4081083BE7B40F5A003D1A2F1435AEA}

Utilizzate questa opzione [!DNL Edit Banner] per modificare elementi quali il nome del banner, l&#39;HTML del banner, il tipo di banner ed eventuali tag associati.

<!-- 

t_editing_a_banner.xml

 -->

Se avete aggiunto un banner utilizzando la ricerca nel sito/merchandising, potete anche modificare il banner utilizzando  Adobe Dynamic Media Classic.

Consultate anche [Modifica di un banner con  Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9).

**Per modificare un banner**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Banners]** dal menu del prodotto.
1. Sulla [!DNL Banners] pagina, fate clic su ![](assets/icon_edit_16.gif).

   sopra la miniatura del banner da modificare.
1. Nella [!DNL Edit Banner] pagina, impostate le opzioni desiderate.

   Consultate la tabella delle opzioni in [Aggiunta di un banner](../c-about-design-menu/c-about-banners.md#task_549D02B5F73B4158B105A94E39D937B7).
1. Al termine, fate clic su **[!UICONTROL Save]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Aggiunta di un banner tramite  Adobe Dynamic Media Classic {#task_AD1E0C00A9E04B1FA819EB93288786B3}

Potete utilizzare [!DNL Banners] per gestire gli annunci banner sul vostro sito Web. Quando aggiungete un banner utilizzando  Adobe Dynamic Media Classic, potete scegliere tra le risorse digitali caricate in Scene7 Publishing System.

<!-- 

t_adding_a_banner_using_adobe_scene7.xml

 -->

Per aggiungere un banner utilizzando  Adobe Dynamic Media Classic, accertatevi di aver configurato l&#39;accesso al vostro account Dynamic Media Classic valido.

Consultate [Configurazione dell’accesso al vostro account](../c-about-settings-menu/c-about-account-options-menu.md#task_CEFF88C2033D41D0B2FE86C435EDAC6D) Adobe Dynamic Media Classic.

**Per aggiungere un banner con  Adobe Dynamic Media Classic**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Design]** > **[!UICONTROL Banners.]**
1. Nella [!DNL Banners] pagina, nell’elenco a **[!UICONTROL Add Banner]** discesa, fate clic su **[!UICONTROL Adobe Scene7]**.
1. Nella finestra di [!DNL Pick an Asset] dialogo, nel riquadro a sinistra, usate le opzioni di navigazione nell’interfaccia utente per individuare la cartella che contiene la risorsa digitale da usare per un banner.

   Ad eccezione delle opzioni di navigazione delle risorse, tutte le altre opzioni dipendono dalla risorsa digitale selezionata per l’aggiunta o la modifica.

   Utilizzate le opzioni di navigazione delle risorse per individuare una risorsa da usare per un nuovo banner nella ricerca del sito/merchandising. Le opzioni di navigazione si applicano a tutti i tipi di risorse digitali selezionate.

   >[!NOTE]
   >
   >Le opzioni di navigazione delle risorse non vengono visualizzate quando modificate il banner nella finestra di [!DNL Change Parameters] dialogo.

   Consultate [Modifica di un banner con  Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9).

   **Opzioni di navigazione delle risorse**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzioni di navigazione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/S7_folders.png"> </p> </td> 
      <td colname="col2"> <p>Consente di selezionare l’account Dynamic Media Classic per la società in questione dall’elenco a discesa e di spostarvi tra le cartelle delle risorse digitali all’interno di tale account. </p> <p>Quando selezionate una cartella, il riquadro a destra della finestra di <span class="wintitle"> dialogo Scegli una risorsa </span> mostra tutte le risorse digitali disponibili all’interno di tale cartella. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_folderhistory.png"> </p> </td> 
      <td colname="col2"> <p>Consente di spostarsi avanti o indietro nella cronologia di navigazione delle cartelle. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_reloadfolder.png"> </p> </td> 
      <td colname="col2"> <p>Aggiorna l’elenco delle risorse digitali visualizzate per una cartella selezionata. </p> <p>È possibile che dobbiate fare clic su questo controllo se spostate, eliminate o rinominate una risorsa selezionata tramite l'elenco a discesa <span class="uicontrol"> Azioni </span> . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_list_or_grid.png"> </p> </td> 
      <td colname="col2"> <p>Consente di visualizzare le risorse digitali in una vista a elenco. Nell’elenco sono visualizzate l’icona o l’immagine in miniatura associata a ciascuna risorsa, il nome del file, il tipo di risorsa digitale, le dimensioni (ove applicabile) e la data dell’ultima modifica. </p> <p>Nella vista Griglia, le risorse digitali presenti nella cartella selezionata vengono visualizzate come icone, miniature o entrambe. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_actionsdropdown.png"> </p> </td> 
      <td colname="col2"> <p>Nella vista a elenco, potete spostare, eliminare o rinominare una risorsa digitale selezionata. </p> <p>Nella vista Griglia, potete spostare o eliminare una o più risorse digitali selezionate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_upload.png"> </p> </td> 
      <td colname="col2"> <p>Apre la finestra di dialogo <span class="wintitle"> Carica </span> , in cui è possibile caricare una risorsa digitale selezionata dal desktop o da un server esterno in modo da poterlo utilizzare come banner. </p> <p>Dopo aver caricato la risorsa, in Scene7 Publishing System viene automaticamente pianificato un processo di pubblicazione. </p> <p>Consultate la tabella delle opzioni in <a href="../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3" type="reference" format="dita" scope="local"> Aggiunta di un banner tramite  Adobe Dynamic Media Classic </a>. </p> <p>Per ulteriori informazioni sul caricamento e la pubblicazione di risorse digitali, utilizzate Scene7 Publishing System. </p> <p>Consultate <a href="https://help.adobe.com/en_US/scene7/using/WS3673AD39-098B-4f08-8A24-CA51261B7366.html" scope="external" format="html"> Caricare e pubblicare le risorse </a> nella guida utente di Scene7 Publishing System. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_searchfield.png"> </p> </td> 
      <td colname="col2"> <p>Consente di cercare una risorsa digitale per parola chiave o per posizione file all’interno della cartella selezionata e delle relative sottocartelle associate. </p> <p>Quando si fa clic sul campo di ricerca, viene automaticamente aggiunto un campo di filtro facoltativo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_addfilter.png"> </p> </td> 
      <td colname="col2"> <p>Aggiunge un altro filtro di risorse per perfezionare ulteriormente l’elenco delle risorse digitali visualizzate per tipo o per data specifica. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_Kindfilter.png"> </p> </td> 
      <td colname="col2"> <p>Potete ridefinire l’elenco delle risorse digitali visualizzate per visualizzarle solo in base a un determinato tipo di Flash, immagine, modello o qualsiasi. </p> <p>Fate clic <img src="assets/s7_deletefilter.png"> per eliminare il filtro dalla ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_datefilter.png"> </p> </td> 
      <td colname="col2"> <p>Potete ridefinire l’elenco delle risorse digitali visualizzate per visualizzare solo quelle create o modificate prima di una determinata data o dopo una determinata data. </p> <p>Fate clic <img src="assets/s7_deletefilter.png" /> per eliminare il filtro dalla ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_assetzoom.png"> </p> </td> 
      <td colname="col2"> <p>Consente di trascinare il cursore verso sinistra o destra per ridurre o ingrandire rispettivamente l’intera visualizzazione del riquadro delle risorse digitali. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **Opzioni delle proprietà**

   Le opzioni Proprietà vengono visualizzate se scegliete un modello di Flash, un modello di immagine o un’immagine. A seconda della risorsa digitale scelta, non tutte le opzioni sono disponibili.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Proprietà, opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Il nome descrittivo del modello o dell'immagine, senza spazi vuoti. Facoltativamente potete includere nel nome la specifica delle dimensioni immagine per consentire agli utenti di identificare ulteriormente la risorsa. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formato </p> </td> 
      <td colname="col2"> <p>Identifica il formato dell’immagine o del modello di immagine. </p> <p>Potete scegliere tra i seguenti formati: </p> 
        <ul id="ul_9A19421BCC424CF585645049DCB87F10"> 
        <li id="li_A4913D783BD547F9AFA1A259C56EC2B3">jpeg </li> 
        <li id="li_66237D7BE8754FB0B0088CE5A02C0214">png </li> 
        <li id="li_4EDDFD7C8AB04677BEC20EFC9AEBBF1F">png-alpha </li> 
        <li id="li_4FCB03C29AE647ACBAF5105016DF7579">gif </li> 
        <li id="li_B884BD7DFF1845FAA9C58EF09B888A77">gif-alpha </li> 
        </ul> <p>Questa opzione non si applica ai modelli di Flash. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Qualità </p> </td> 
      <td colname="col2"> <p>Controlla il livello di compressione delle immagini in formato JPEG o GIF. Questa impostazione influisce sia sulla dimensione del file che sulla qualità dell’immagine. La scala di qualità è di 1-100. </p> <p>Quando trascinate il cursore verso sinistra o verso destra, l’immagine nella finestra di anteprima viene aggiornata per riflettere la modifica della qualità. </p> <p>Questa opzione non si applica ai modelli di Flash. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Larghezza </p> </td> 
      <td colname="col2"> <p>Specifica la larghezza della risorsa digitale, in pixel. Questa dimensione corrisponde alla larghezza in cui la risorsa viene visualizzata dai clienti che visitano il sito Web. </p> <p>Questa opzione non si applica ai modelli di Flash. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Altezza </p> </td> 
      <td colname="col2"> <p>Specifica l’altezza della risorsa digitale, in pixel. Questa dimensione corrisponde all’altezza in cui la risorsa viene visualizzata dai clienti che visitano il sito Web. </p> <p>Questa opzione non si applica ai modelli di Flash. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **Opzioni collegamento banner**

   Le opzioni Collegamento banner vengono visualizzate solo se avete scelto un’immagine o un modello di immagine per il banner.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione Collegamento banner </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Collegamento URL </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo URL a cui si desidera collegare il banner quando un cliente fa clic sull'immagine. </p> <p>Se non desiderate che il banner si collega a nulla, lasciate vuoto il campo URL collegamento. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Target </p> </td> 
      <td colname="col2"> <p>Specifica dove aprire il banner collegato, ad esempio una nuova finestra del browser o una nuova scheda. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **Modifica collegamenti, opzione**

   L’opzione Modifica collegamenti viene visualizzata solo se avete scelto un modello di Flash per il banner.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Modifica collegamenti, opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <img placement="inline" id="image_EBB8159690C74D4692B5DF945B045E0B" src="assets/icon_edit_16.gif" /> </p> </td> 
      <td colname="col2"> <p>Consente di modificare il campo del collegamento URL utilizzato nel modello di Flash. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **Opzioni Sostituisci testo**

   Le opzioni Sostituisci testo vengono visualizzate solo se avete scelto un modello di Flash per il banner con livelli di testo modificabili.

   Eventuali modifiche apportate al testo nel modello di Flash vengono riportate nella finestra Anteprima.

   >[!NOTE]
   >
   >Se aggiungete un comando di ricerca e sostituzione per sostituire &quot;vacca&quot; con &quot;mela&quot;, e quindi create un secondo comando per sostituire &quot;mela&quot; con &quot;arancione&quot;, il secondo comando non ha effetto.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione Sostituisci testo </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_addfilter.png"> </p> </td> 
      <td colname="col2"> <p>Aggiunge un campo di ricerca e sostituzione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_deletefilter.png"> </p> </td> 
      <td colname="col2"> <p>Elimina un campo Cerca e sostituisci e ripristina il testo utilizzato in precedenza. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ricerca </p> </td> 
      <td colname="col2"> <p>Consente di inserire un termine di ricerca per il testo non collegato nei livelli del modello di Flash. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sostituisci </p> </td> 
      <td colname="col2"> <p>Consente di specificare il testo da inserire al posto del testo ricercato. </p> <p>Quando si preme <span class="uicontrol"> Invio </span> in questo campo, la finestra di anteprima viene aggiornata con il testo sostitutivo. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **Opzioni parametri**

   Le opzioni dei parametri vengono visualizzate solo se avete scelto un modello di immagine o un modello di Flash per il banner. Le opzioni effettive dei parametri variano a seconda di come il modello è stato creato e con i parametri in Scene7 Publishing System. Ad esempio, il modello potrebbe includere campi con parametri che consentono di modificare elementi quali testo, stile font, prezzo, codici speciali utilizzati per la spedizione gratuita, la dimensione dell&#39;immagine all&#39;interno del banner o persino cercare un&#39;altra immagine da utilizzare.

   >[!NOTE]
   >
   >Qualsiasi modifica apportata ai parametri può essere ignorata dalle regole aziendali. I parametri fungono da predefiniti solo quando non vengono create regole business che altrimenti modificherebbero i parametri.

   Consultate [Aggiunta di una nuova regola](../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7)business.

   Consultate [Modifica di una regola](../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087)aziendale.

   **Attiva/disattiva le opzioni Visibilità livello**

   L’opzione Attiva/Disattiva visibilità livello si applica solo se avete scelto un modello di Flash per il banner.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Attiva/Disattiva visibilità livello </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <img src="assets/s7_togglelayervisibility.png"> </p> </td> 
      <td colname="col2"> <p>Consente di attivare o disattivare la visibilità dei vari livelli che compongono il file modello di Flash. </p> <p>Ogni volta che attivate o disattivate la visibilità di un livello, la finestra di anteprima viene aggiornata per aggiornare la visualizzazione. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   (Facoltativo) Se la risorsa digitale che desiderate usare per un banner non è disponibile nella cartella selezionata, potrebbe essere necessario caricarla. Fare clic **[!UICONTROL Upload]** e quindi selezionare il file e le opzioni desiderati. Il file viene caricato nella cartella selezionata.

   >[!NOTE]
   >
   >Se desiderate usare la funzionalità di caricamento nel visualizzatore delle risorse Scene7, accertatevi che l’account Scene7 usato abbia già il ruolo di &quot;Amministratore società SPS&quot;.

   Consultate Impostazione [](https://help.adobe.com/en_US/scene7/using/WS662101DF-D697-47a7-A7D8-B52FD8E94438.html) amministrazione nella guida utente di Scene7 Publishing System.

   **Opzioni di base**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Sfoglia </p> </td> 
      <td colname="col2"> <p> Consente di individuare il file da caricare, pubblicare e di selezionarlo come banner. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Sovrascrivi </p> </td> 
      <td colname="col2"> <p>I file caricati sostituiscono quelli esistenti con lo stesso nome file, all’interno della cartella selezionata. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Preferenze e-mail </p> </td> 
      <td colname="col2"> <p> Consente di scegliere la notifica e-mail ricevuta per il caricamento, oppure potete scegliere di non ricevere alcuna notifica relativa al processo di caricamento. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **Opzioni avanzate**

   Quando caricate i file immagine PostScript (EPS) o  Illustrator (AI), potete formattarli in vari modi. Potete rasterizzare i file, convertirli in FXG per Pubblicazione modelli, mantenere lo sfondo trasparente, scegliere una risoluzione e uno spazio colore.

   I file PSD (Photoshop Document Files) vengono utilizzati più spesso in Dynamic Media Classic per creare i modelli. Quando caricate un file PSD, potete creare automaticamente dal file un modello Dynamic Media Classic (selezionate l’ **[!UICONTROL Create Template]** opzione).

   Scene7 Publishing System crea più immagini da un file PSD con livelli, se utilizzate il file per creare un modello; crea un’immagine per ciascun livello.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Nome gruppo di opzioni </p> </th> 
      <th colname="col02" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Opzioni profilo colore </p> </td> 
      <td colname="col02"> <p>Profilo colore </p> </td> 
      <td colname="col2"> <p> Consente di scegliere tra le seguenti opzioni: </p> 
        <ul id="ul_6927BC08CA2647EDB2C85DAD2B82AE31"> 
        <li id="li_CA3F44FF9C0F4CE987DCB0AF9303C2E4"> <span class="uicontrol"> Converti in SRGB </span> <p>Effettua la conversione in SRGB (Standard Rosso Verde Blu). SRGB è lo spazio colore consigliato per la visualizzazione di immagini sulle pagine Web. </p> </li> 
        <li id="li_FCCEE6B14CCD4246ADA152932010ABF1"> <span class="uicontrol"> Mantieni spazio colore originale </span> <p>Conserva lo spazio colore originale. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni di modifica delle immagini </p> </td> 
      <td colname="col02"> <p>Crea maschera dal tracciato di ritaglio </p> </td> 
      <td colname="col2"> <p>Create una maschera per l’immagine in base alle informazioni del tracciato di ritaglio. Questa opzione si applica alle immagini create con applicazioni di modifica delle immagini in cui è stato creato un tracciato di ritaglio. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni PostScript </p> <p> opzioni Illustrator </p> </td> 
      <td colname="col02"> <p>Processing (Completa elaborazione) </p> </td> 
      <td colname="col2"> <p> <span class="uicontrol"> L’ </span> opzione Rasterizza converte la grafica vettoriale nel file in formato bitmap. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Opzioni PostScript </p> <p> opzioni Illustrator </p> </td> 
      <td colname="col02"> <p> Risoluzione </p> </td> 
      <td colname="col2"> <p> Determina l’impostazione della risoluzione. Questa impostazione determina la quantità di pixel visualizzati per pollice nel file. Il valore predefinito è 150. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Opzioni PostScript </p> <p> opzioni Illustrator </p> </td> 
      <td colname="col02"> <p> Spazio colore </p> </td> 
      <td colname="col2"> <p>Consente di scegliere uno spazio colore per il file Illustrator . Lo spazio colore RGB è preferibile per la visualizzazione online. </p> <p>Potete scegliere tra le seguenti opzioni: </p> 
        <ul id="ul_0E83E2762A574480B243F963A7FB2ACD"> 
        <li id="li_B9FEC7D220D04CCABACD30839051DAE4"> <span class="uicontrol"> Rileva automaticamente </span> <p> Conserva lo spazio colore del file PDF. </p> </li> 
        <li id="li_ED0EB3B12BCF41C7AFC435447010B6FF"> <span class="uicontrol"> Forza come RGB </span> <p> Effettua la conversione nello spazio colore RGB. </p> </li> 
        <li id="li_3FB5DD8887C540BC97148A4D63B38F72"> <span class="uicontrol"> Forza come CMYK </span> <p> Effettua la conversione nello spazio colore CMYK. </p> </li> 
        <li id="li_6C018D3A4B254880AD41896E9F4AF3D9"> <span class="uicontrol"> Forza come scala di grigio </span> <p> Effettua la conversione nello spazio colore Scala di grigio. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Opzioni PostScript </p> <p> opzioni Illustrator </p> </td> 
      <td colname="col02"> <p> Mantieni sfondo trasparente </p> </td> 
      <td colname="col2"> <p>Mantiene la trasparenza dello sfondo del file. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni Photoshop </p> </td> 
      <td colname="col02"> <p> Gestisci livelli </p> </td> 
      <td colname="col2"> <p>Estrae i livelli eventualmente presenti nel file PSD in singole risorse. I livelli delle risorse restano associati al file PSD. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Opzioni Photoshop </p> </td> 
      <td colname="col02"> <p>Crea modello </p> </td> 
      <td colname="col2"> <p> Crea un modello dai livelli presenti nel file PSD. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Opzioni Photoshop </p> </td> 
      <td colname="col02"> <p> Estrai testo </p> </td> 
      <td colname="col2"> <p> Estrae il testo in modo che i clienti possano cercare parole chiave all’interno di un banner. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni Photoshop </p> </td> 
      <td colname="col02"> <p> Estendi livelli </p> </td> 
      <td colname="col2"> <p>Estende le dimensioni dei livelli di immagine estratti alle dimensioni del livello di sfondo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni Photoshop </p> </td> 
      <td colname="col02"> <p> Denominazione dei livelli </p> </td> 
      <td colname="col2"> <p>I livelli nel file PSD vengono caricati come immagini separate. Potete scegliere tra le seguenti opzioni per decidere come denominare queste immagini in Scene7 Publishing System: </p> 
        <ul id="ul_C2A25177A07740CA90B32C638304D39F"> 
        <li id="li_477D5BFF7238454BBF0E04B22DE378F7"> <span class="uicontrol"> Usa nome livello dal file PSD </span> <p>Denomina le immagini in base ai nomi dei rispettivi livelli nel file PSD. Ad esempio, un livello denominato <span class="codeph"> Price Tag </span> nel file PSD originale diventa un’immagine denominata <span class="codeph"> Price Tag </span>. Tuttavia, se i nomi dei livelli nel file PSD sono nomi di livello Photoshop predefiniti (Sfondo, Livello 1, Livello 2 e così via), le immagini vengono denominate in base ai numeri dei rispettivi livelli nel file PSD, non in base ai nomi dei livelli predefiniti. </p> </li> 
        <li id="li_EB4173B884FC41328CFBDE27DA6D43AA"> <span class="uicontrol"> Usa nome file PSD e numero di aggiunta </span> <p>Denomina le immagini in base ai numeri dei rispettivi livelli nel file PSD, ignorando i nomi dei livelli originali. Le immagini vengono denominate con il nome del file Photoshop e un numero del livello aggiunto. Ad esempio, il secondo livello di un file denominato <span class="codeph"> Spring Ad.psd </span> è denominato <span class="codeph"> Spring Ad_2 </span> anche se in Photoshop era presente un nome non predefinito. </p> </li> 
        <li id="li_10B2D2DE2FD24BD08DB56D1D95ABA53D"> <span class="uicontrol"> Usa nome file PSD e nome o numero del livello </span> <p>Denomina le immagini dopo il file PSD seguito dal nome o dal numero del livello. Il numero del livello viene utilizzato se i nomi del livello nel file PSD sono nomi di livello Photoshop predefiniti. Ad esempio, un livello denominato <span class="codeph"> Price Tag </span> in un file PSD denominato <span class="codeph"> SpringAd </span> è denominato <span class="codeph"> Spring Ad_Price Tag </span>. Un livello con il nome predefinito <span class="codeph"> Livello 2 </span> è denominato <span class="codeph"> Spring Ad_2 </span>. </p> </li> 
        <li id="li_5E57AC0719D4484B9C9BD14DB42B4455"> <span class="uicontrol"> Creare una cartella basata sul nome del file PSD </span> <p>Crea una cartella per le immagini dei livelli utilizzando il nome file del file PSD. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni Photoshop </p> </td> 
      <td colname="col02"> <p>Ancoraggio </p> </td> 
      <td colname="col2"> <p>Specificate in che modo le immagini vengono ancorate nei modelli generati dalla composizione a livelli generata dal file PSD. </p> <p>Per impostazione predefinita, l’ancoraggio è al centro. Un ancoraggio centrale consente alle immagini sostitutive di riempire al meglio lo stesso spazio, indipendentemente dalle proporzioni dell’immagine sostitutiva. Le immagini con proporzioni diverse che sostituiscono l’immagine, quando fanno riferimento al modello e utilizzano la sostituzione dei parametri, occupano in modo efficace lo stesso spazio. Passate a un’impostazione diversa se l’applicazione richiede che le immagini sostitutive riempiano lo spazio allocato nel modello. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni PDF </p> </td> 
      <td colname="col02"> <p>Processing (Completa elaborazione) </p> </td> 
      <td colname="col2"> <p> <span class="uicontrol"> L’ </span> opzione Rasterizza consente di estrarre le pagine del file PDF e di convertire la grafica vettoriale in immagini bitmap. 
        <!--Choose this option to create an eCatalog. (This option is thedefault.)--> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni PDF </p> </td> 
      <td colname="col02"> <p> Risoluzione </p> </td> 
      <td colname="col2"> <p>Determina l’impostazione della risoluzione. Questa impostazione determina la quantità di pixel visualizzati per pollice nel file PDF. Il valore predefinito è 150. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni PDF </p> </td> 
      <td colname="col02"> <p> Spazio colore </p> </td> 
      <td colname="col2"> <p>Consente di scegliere uno spazio colore per il file PDF. La maggior parte dei file PDF contiene immagini a colori sia RGB che CMYK. Lo spazio colore RGB è preferibile per la visualizzazione online. </p> <p>Potete scegliere tra le seguenti opzioni: </p> 
        <ul id="ul_44A8C39DEB21473F9375E3962F14D3C6"> 
        <li id="li_1046FA0017934C5EB7C0100F8F78507D"> <span class="uicontrol"> Rileva automaticamente </span> <p> Conserva lo spazio colore del file PDF. </p> </li> 
        <li id="li_561CCF705EDD451993D2DA2EB33F05F7"> <span class="uicontrol"> Forza come RGB </span> <p> Effettua la conversione nello spazio colore RGB. </p> </li> 
        <li id="li_D9E8CF61C40140979484EDEF7DAD2C44"> <span class="uicontrol"> Forza come CMYK </span> <p> Effettua la conversione nello spazio colore CMYK. </p> </li> 
        <li id="li_F3606B45C0F84BA594263EA12243F67A"> <span class="uicontrol"> Forza come scala di grigio </span> <p> Effettua la conversione nello spazio colore Scala di grigio. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Opzioni PDF </p> </td> 
      <td colname="col02"> <p>Genera automaticamente eCatalog da PDF con più pagine </p> </td> 
      <td colname="col2"> <p> Crea automaticamente un eCatalog dal file PDF. L’eCatalog viene denominato in base al file PDF caricato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Opzioni PDF </p> </td> 
      <td colname="col02"> <p>Estrai parole chiave </p> </td> 
      <td colname="col2"> <p>Estrae le parole dal file PDF in modo che sia possibile eseguire la ricerca nel file tramite parole chiave. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Nel riquadro a destra, fate clic sul file di immagine, modello o Flash desiderato.

   Viene visualizzata la finestra [!DNL Pick An Asset] a comparsa.
1. (Facoltativo) Nella finestra [!DNL Pick An Asset] a comparsa, nell’elenco a [!DNL Actions] discesa, effettuate una delle seguenti operazioni:

   * Clic **[!UICONTROL Move]**. Nella finestra di [!DNL Select a folder to move to] dialogo, selezionate la cartella in cui desiderate spostare la risorsa digitale. Clic **[!UICONTROL Move]**.

      Potete anche selezionare più risorse digitali da spostare in un’altra cartella.

   * Clic **[!UICONTROL Delete]**. Nella finestra di [!DNL Delete Selected Assets] dialogo fare clic su **[!UICONTROL Delete]**.

      Potete anche selezionare più risorse digitali da eliminare.

   * Clic **[!UICONTROL Rename]**. Nella finestra di [!DNL Enter a new name for] dialogo, nel campo di testo, digitate un nuovo nome per la risorsa digitale. Clic **[!UICONTROL Rename]**.

1. (Facoltativo) A seconda della risorsa digitale selezionata, impostate le opzioni desiderate nel riquadro a sinistra della finestra a [!DNL Pick an Asset] comparsa.
1. Fate clic sulla risorsa per selezionarla da usare come banner.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica di un banner con  Adobe Dynamic Media Classic {#task_C3E782477FBF428ABEA220751781ACA9}

Usate [!DNL Edit Banner] per modificare le proprietà e i parametri di un banner aggiunto con  Adobe Dynamic Media Classic.

<!-- 

t_editing_a_banner_using_adobe_scene7.xml

 -->

Se avete aggiunto un banner aggiungendo del codice HTML, modificate il banner utilizzando invece la funzione di ricerca/merchandising del sito.

Consultate anche [Modifica di un banner](../c-about-design-menu/c-about-banners.md#task_D4081083BE7B40F5A003D1A2F1435AEA).

**Per modificare un banner con  Adobe Dynamic Media Classic**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Banners]** dal menu del prodotto.
1. Nella [!DNL Banners] pagina, fate clic ![](assets/icon_edit_16.gif) sopra la miniatura di un banner con icona S7 nell’angolo inferiore sinistro della finestra del banner.
1. Nella [!DNL Change Parameter] pagina, impostate le opzioni desiderate.
1. Al termine, fate clic su **[!UICONTROL Save]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione dei banner {#task_32F3BADC481E4E8984B2AA04B96052EB}

Potete eliminare i banner organizzati che non sono più necessari o che desiderate utilizzare uno alla volta o come gruppo.

<!-- 

t_deleting_banners.xml

 -->

**Per eliminare i banner**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Banners]** dal menu del prodotto.
1. (Facoltativo) Effettuate una o più delle seguenti operazioni:

   * Nella [!DNL Banners] pagina, selezionate il tipo di banner che desiderate trovare nell’elenco a **[!UICONTROL Find banner of type]** discesa. Se necessario, specificate un nome per il tag nel campo di **[!UICONTROL with tag]** testo o un nome per il tipo di banner nel campo di **[!UICONTROL with name]** testo. Clic **[!UICONTROL Find.]**

   * Dall’elenco a **[!UICONTROL Sort]** discesa, selezionate la modalità di ordine dell’elenco dei banner.
   * Nell&#39;elenco a **[!UICONTROL Show]** discesa, selezionate il numero di banner da caricare nella pagina corrente che state visualizzando.

1. Esegui una delle operazioni seguenti:

   * Nell’angolo in alto a sinistra di qualsiasi casella di banner, fate clic sulla casella di controllo di ciascun banner da eliminare.
   * Nella barra superiore della [!DNL Banners] pagina, selezionate **[!UICONTROL Select all]** per selezionare tutti i banner caricati nella pagina visualizzata.

1. Nell’elenco a **[!UICONTROL Bulk Actions]** discesa, fate clic su **[!UICONTROL Delete]**.
1. Nella finestra di [!DNL Confirmation Action] dialogo fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Anteprima dei banner {#task_6AB1F81A984A4DC2ACACD1FE030545E2}

Potete sfogliare i banner aggiunti alla [!DNL Banners] pagina per visualizzarne le dimensioni intere. Eventuali CSS presenti nel modello che influiscono sul banner non vengono visualizzati.

<!-- 

t_previewing_banners.xml

 -->

**Per visualizzare in anteprima i banner**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Banners]** dal menu del prodotto.
1. (Facoltativo) Effettuate una o più delle seguenti operazioni:

   * Nella [!DNL Banners] pagina, selezionate il tipo di banner che desiderate trovare nell’elenco a **[!UICONTROL Find banner of type]** discesa. Se necessario, specificate un nome per il tag nel campo di **[!UICONTROL with tag]** testo o un nome per il tipo di banner nel campo di **[!UICONTROL with name]** testo. Clic **[!UICONTROL Find.]**

   * Dall’elenco a **[!UICONTROL Sort]** discesa, selezionate la modalità di ordine dell’elenco dei banner.
   * Nell&#39;elenco a **[!UICONTROL Show]** discesa, selezionate il numero di banner da caricare nella pagina corrente che state visualizzando.

1. Sulla [!DNL Banners] pagina, fate clic sulla miniatura di un banner per visualizzarne le dimensioni intere.
1. Esegui una delle operazioni seguenti:

   * Nella finestra di dialogo di anteprima del banner, fate clic sulla freccia sinistra o destra per spostarvi e visualizzare i banner a dimensione intera aggiunti.
   * Fate clic sul pulsante Chiudi per chiudere la finestra di dialogo di anteprima del banner e tornare alla [!DNL Banners] pagina.

## Invio live dei banner {#task_161F4FEC8362474296A566E64BF05B97}

Potete inviare live nel sito Web uno o più banner selezionati.

<!-- 

t_pushing_banners_live.xml

 -->

Oppure, se preferite, potete trasmettere in diretta tutte le modifiche a qualsiasi banner utilizzando l&#39; **[!UICONTROL Push Live]** opzione nella parte inferiore della [!DNL Banners] pagina.

Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

**Per inviare i banner live**

1. Scegliere **[!UICONTROL Design]** > **[!UICONTROL Banners]** dal menu del prodotto.
1. (Facoltativo) Effettuate una o più delle seguenti operazioni:

   * Nella [!DNL Banners] pagina, selezionate il tipo di banner che desiderate trovare nell’elenco a **[!UICONTROL Find banner of type]** discesa. Se necessario, specificate un nome per il tag nel campo di **[!UICONTROL with tag]** testo o un nome per il tipo di banner nel campo di **[!UICONTROL with name]** testo. Clic **[!UICONTROL Find]**.

   * Dall’elenco a **[!UICONTROL Sort]** discesa, selezionate la modalità di ordine dell’elenco dei banner.
   * Nell&#39;elenco a **[!UICONTROL Show]** discesa, selezionate il numero di banner da caricare nella pagina corrente che state visualizzando.

1. Esegui una delle operazioni seguenti:

   * Nell’angolo in alto a sinistra di qualsiasi casella di banner, fate clic sulla casella di controllo di ciascun banner da eliminare.
   * Nella barra superiore della [!DNL Banner] pagina, selezionate **[!UICONTROL Select all]** per selezionare tutti i banner caricati nella pagina visualizzata.

1. Nell’elenco a **[!UICONTROL Bulk Actions]** discesa, fate clic su **[!UICONTROL Push live]**.
1. Nella finestra di [!DNL Confirmation Action] dialogo fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Nella [!DNL Banners] pagina, fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

   Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.
