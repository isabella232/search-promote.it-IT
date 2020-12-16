---
description: Utilizzate il menu Opzioni account per aggiornare le impostazioni dell'account, impostare le preferenze di merchandising o rimuovere il vostro account Search&amp;Promote.
seo-description: Utilizzate il menu Opzioni account per aggiornare le impostazioni dell'account, impostare le preferenze di merchandising o rimuovere il vostro account Search&amp;Promote.
seo-title: Informazioni sul menu Opzioni account
solution: Target
subtopic: Account Options
title: Informazioni sul menu Opzioni account
topic: Settings,Site search and merchandising
uuid: 0f830033-de9e-4197-8d76-906c818662eb
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '1684'
ht-degree: 2%

---


# Informazioni sul menu Opzioni account{#about-the-account-options-menu}

Utilizzate il menu Opzioni account per aggiornare le impostazioni dell&#39;account, impostare le preferenze di merchandising o rimuovere il vostro account di Search&amp;Promote.

## Configurazione delle impostazioni dell&#39;account {#task_80A38D0C8E4F453395BD67B81E4B45D9}

Consente di gestire le impostazioni dell&#39;account come il nome e l&#39;indirizzo del sito Web, il fuso orario e altro ancora. Oppure, visualizzate il numero del vostro account.

**Per configurare le impostazioni dell&#39;account**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Account Settings]** dal menu del prodotto.
1. Nella pagina [!DNL Account Settings], impostate le opzioni desiderate.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome sito Web </p> </td> 
      <td colname="col2"> <p>Obbligatorio. </p> <p>Nome breve utilizzato per descrivere il sito Web o l’account. Questa opzione è utile se disponete di più siti Web. </p> <p> <p>Nota:  Per selezionare uno o più nomi da utilizzare, contattate il supporto tecnico. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo sito Web </p> </td> 
      <td colname="col2"> <p>Obbligatorio. </p> <p>L’indirizzo URL del sito Web. L'indirizzo qui specificato è utilizzato come punto di ingresso principale del sito Web. </p> <p>Consultate anche <a href="../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45" type="task" format="dita" scope="local"> Aggiunta di più punti di immissione URL da indicizzare </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fuso orario (per report e pianificazione) </p> </td> 
      <td colname="col2"> <p>Fuso orario utilizzato per i rapporti e le operazioni di pubblicazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Convalida attributi di tag modello al salvataggio </p> </td> 
      <td colname="col2"> <p>Convalida tutti gli attributi in <span class="codeph"> &lt;guidati-*&gt; </span> e <span class="codeph"> &lt;search-*&gt; </span> quando si salva un modello nell'Editor modelli in fase. </p> <p>Consultate <a href="../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3" type="task" format="dita" scope="local"> Modifica di una presentazione o di un modello di trasporto </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Convalida dei riferimenti ai modelli per gli oggetti GS al salvataggio </p> </td> 
      <td colname="col2"> <p> Controlla l'esistenza di oggetti Guided Search, quali menu, facet, breadcrumb, var personalizzate e modelli, a cui si fa riferimento nei tag <span class="codeph"> &lt;guidate-*&gt; </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Applica un controllo rigoroso della sintassi dei modelli </p> </td> 
      <td colname="col2"> <p>Rende il validatore del modello più rigoroso e consente il controllo di elementi quali virgolette non bilanciate e simboli &lt;&gt;. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero account </p> </td> 
      <td colname="col2"> <p>Non è possibile modificare il numero di account. È solo a scopo di visualizzazione. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.

## Configurazione dell&#39;integrazione con  Adobe CQ5 {#task_EA2FC2C24960498DAE01A1AB769D2F14}

Puoi configurare l’integrazione tra ricerca e merchandising del sito e  Adobe CQ5.

**Per configurare l&#39;integrazione con  Adobe CQ5**

1. Ottenete l’ID membro e l’ID account effettuando le seguenti operazioni:

   * Accedi al tuo account di ricerca/merchandising del sito.
   * Nel percorso URL, copiate l’ID membro e l’ID account.

      Ad esempio, se il percorso dell&#39;URL dell&#39;account fosse `https://searchandpromote.mycompany.com/px/home/?sp_id=00123a4b-sp1234a5b6`, l&#39;ID membro sarebbe `00123a4b` e l&#39;ID account sarebbe `sp1234a5b6`.

1. In  Adobe CQ5, utilizzate la scheda Cloud Services per creare la configurazione di ricerca del sito/merchandising.

   Utilizzate l&#39;ID membro e l&#39;ID account copiati per le rispettive impostazioni.

## Configurazione delle preferenze di merchandising {#task_7AC7B9F5D9F44E10AB5BC0B8CB31C37A}

Gestisci preferenze di merchandising, ad esempio il generatore di regole predefinito e il termine di ricerca predefinito.

**Per configurare le preferenze di Merchandising**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Merchandising Preferences]** dal menu del prodotto.
1. Nella pagina [!DNL Merchandising Preferences], impostate le opzioni desiderate.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Soglia dominante gruppo di trigger </p> </td> 
      <td colname="col2"> <p> La percentuale di soglia da applicare agli attivatori basati sui risultati basati su "group domination" che specificano "use account default". </p> <p>Modificando questa impostazione è possibile eseguire immediatamente le ricerche dal vivo, quindi utilizzare con cautela. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Definizione gruppo </p> </td> 
      <td colname="col2"> <p>Numero di risultati in un gruppo per la console merchandising. Il massimo è 50.000. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Campo 'Merchandising Document ID' (MDI) </p> </td> 
      <td colname="col2"> <p> Il campo specificato deve "univocare" i risultati di ricerca che si desidera manipolare mediante attivatori e azioni basate su risultati singoli. </p> <p>In alcuni casi, l’utilizzo del campo URL predefinito funziona ma non è consigliato. Un campo meta definito dall’utente con un ID univoco per ogni pagina (ad esempio, SKU o product_id) sarebbe molto più efficiente rispetto all’utilizzo del campo URL. Specificando 'none' vengono disattivati attivatori e azioni basati su singoli risultati in Gestore regole. La modifica di questa opzione si applica solo alle regole salvate in futuro; le regole esistenti continuano a utilizzare l'identificatore MDI con il quale sono state salvate originariamente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Termine di ricerca predefinito VRB (Visual Rule Builder) </p> </td> 
      <td colname="col2"> <p> Consente di personalizzare il termine di ricerca iniziale utilizzato in Visual Rule Builder. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ricerca predefinita VRB </p> </td> 
      <td colname="col2"> <p>Questa impostazione consente di impostare la ricerca predefinita inizialmente selezionata in Generatore di regole visive. </p> <p> Questa impostazione è pertinente solo per l’implementazione con più ricerche. Il VRB consente di selezionare la ricerca a cui si riferisce l'attivatore o l'azione a cui si applica il gruppo definito. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Timeout del simulatore/VRB </p> </td> 
      <td colname="col2"> <p>VRB e Simulator inviano le ricerche attraverso un server proxy più lento rispetto alla ricerca di produzione. In alcune circostanze, ad esempio in caso di caricamento lento delle risorse, il VRB o il simulatore possono avere un timeout. È possibile aumentare o diminuire il numero di secondi che l'interfaccia utente deve attendere prima che venga interrotta. Raramente è necessario aumentare questa impostazione dal valore predefinito 60. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.

## Configurazione dell&#39;accesso all&#39;account Dynamic Media Classic  Adobe {#task_CEFF88C2033D41D0B2FE86C435EDAC6D}

Collegate l&#39;account di ricerca/merchandising del sito  Adobe Dynamic Media Classic in modo da poter aggiungere facilmente banner pubblicitari al sito Web utilizzando risorse digitali caricate da  Adobe Scene7.

Vedere [Informazioni sui banner](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA).

Consultate [Aggiunta di un banner tramite  Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

**Per configurare l&#39;accesso al tuo account Dynamic Media Classic  Adobe**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Scene7 Configuration]** dal menu del prodotto.
1. Nella pagina [!DNL Scene7 Configuration], impostate le opzioni desiderate.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Area geografica </p> </td> 
      <td colname="col2"> <p>Obbligatorio. Identifica la regione del mondo in cui l'account Dynamic Media Classic accede ai vari server Dynamic Media Classic. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Società predefinita </p> </td> 
      <td colname="col2"> <p>Identifica il nome della società associata al tuo account Dynamic Media Classic. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> E-mail </p> </td> 
      <td colname="col2"> <p>Obbligatorio. Identifica l’indirizzo e-mail utilizzato per l’accesso e le comunicazioni di Dynamic Media Classic. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Password </p> </td> 
      <td colname="col2"> <p>Obbligatorio. La password di accesso di Dynamic Media Classic. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Abilita tutti i controlli di Dynamic Media Classic nella ricerca del sito/merchandising. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Verifica la correttezza del nome dell'area Dynamic Media Classic, dell'indirizzo e-mail e della password. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Fate clic su **[!UICONTROL Test]** per verificare che il nome dell&#39;area Dynamic Media Classic, l&#39;indirizzo e-mail e i dettagli della password siano corretti.
1. Clic **[!UICONTROL Save Changes]**.

## Configurazione  Adobe Analytics Redirector {#task_2C9DE333FD7246E4A460FC0F55204160}

Se utilizzate [!DNL Adobe Analytics] per il monitoraggio dei visitatori del sito, potete utilizzare [!DNL Adobe Analytics Redirector] nella ricerca del sito/merchandising per tenere traccia di tutti i reindirizzamenti HTTP con [!DNL Adobe Analytics].

**Per configurare  Adobe Analytics Redirector**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Adobe Analytics Redirector]** dal menu del prodotto.
1. Nella pagina [!DNL Adobe Analytics Redirector], impostate le opzioni desiderate.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Attiva  funzione Adobe Analytics Redirector </p> </td> 
      <td colname="col2"> <p>Attiva il tracciamento dei reindirizzamenti HTTP con  Adobe Analytics. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Server di monitoraggio </p> </td> 
      <td colname="col2"> <p> Identifica il nome  server di tracciamento Adobe Analytics. </p> <p>Per conoscere il nome del server di tracciamento, </p> <p> 
      <ol id="ol_D17B77E81F8D40D0948415CD60839BE3"> 
      <li id="li_BE58DBA104D44F0DB6C64AD3F12CEA97"> In  Adobe Analytics, fare clic su <span class="uicontrol"> Amministratore </span> &gt; <span class="uicontrol">  Admin Console </span> &gt; <span class="uicontrol"> Code Manager </span>. </li> 
      <li id="li_67A93D17C3A14874928C6DC4FF2D4784"> Nella casella di gruppo Opzioni <span class="wintitle"> </span>, selezionate una suite di rapporti dal rispettivo elenco a discesa. </li> 
      <li id="li_5AAB004AC58441DBB0F813BDE30EFFD4"> Fare clic su <span class="uicontrol"> Genera codice </span>. </li> 
      <li id="li_E80368993F4D4DD69E37509FF4348B36"> Nella pagina <span class="wintitle"> Code Manager </span> fare clic sulla scheda <span class="uicontrol"> Core Javascript File </span>. </li> 
      <li id="li_991BDCDDA41A445F85CEEAAE9A46A304"> In <span class="wintitle"> Sezione configurazione </span>, trovare la riga che segue: <p> <code> s.trackingServer="yourcompany.122.2o7.net" </code> </p> <p>Il nome del server di tracciamento, in questo caso, è <span class="codeph"> "yourcompany.122.2o7.net" </span> </p> </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>ID suite di rapporti </p> </td> 
      <td colname="col2"> <p> Identifica il tuo ID suite di rapporti. </p> <p>Per conoscere il tuo ID suite di rapporti, </p> <p> 
      <ol id="ol_4FD7B2459358486DBDB130426131D16A"> 
      <li id="li_9AF624CEB128453C808892EEE385D5D1"> In  Adobe Analytics, fare clic su <span class="uicontrol"> Amministratore </span> &gt; <span class="uicontrol">  Admin Console </span> &gt; <span class="uicontrol"> Suite di rapporti </span>. </li> 
      <li id="li_AAC47EAA04144A67BDCB5C7B8D8098E9"> Per trovare l'ID, consultare la colonna <span class="wintitle"> ID suite di rapporti </span> nella tabella. </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametri personalizzati </p> </td> 
      <td colname="col2"> <p>Consente di aggiungere parametri personalizzati all'URL di reindirizzamento di Adobe Analytics . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Impostate le maiuscole/minuscole di tutti i valori personalizzati su </p> </td> 
      <td colname="col2"> <p>Consente di standardizzare il casing utilizzato per qualsiasi valore di parametro personalizzato specificato in precedenza.  Adobe Analytics fa distinzione tra maiuscole e minuscole, pertanto è necessario unificare le maiuscole e minuscole per i valori. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Vedere [Configurazione di un indice incrementale di un sito Web in fase](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Adobe Analytics Redirector], effettuare una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configurazione dei file radice {#task_5F175C8743FB49A2A003813CBF7C56BF}

Gestire i file principali nella cartella principale del sito Web.

**Per configurare i file radice**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Root Files]** dal menu del prodotto.
1. Nella pagina [!DNL Root Files], individuate i file principali da caricare.

   <table> 
    <thead> 
    <tr> 
      <th colname="col1" class="entry"> <p>File principale </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
      <td colname="col1"> <p>favicon.ico </p> </td> 
      <td colname="col2"> <p> Icona del sito. In genere viene visualizzata nella barra degli indirizzi del browser del cliente. </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>robots.txt </p> </td> 
      <td colname="col2"> <p>Consente o impedisce ai bot di accedere a determinate parti del sito Web. </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>sitemap.xml </p> </td> 
      <td colname="col2"> <p>Il file XML con un elenco di tutte le pagine disponibili sul sito Web. </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>crossdomain.xml </p> </td> 
      <td colname="col2"> <p>Consente o meno al Flash Player di accedere ai file tra domini diversi. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Vedere [Configurazione di un indice incrementale di un sito Web in fase](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Root Files], effettuare una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Vedere [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Vedere [Invio live delle impostazioni dell&#39;area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Trasferimento della proprietà dell&#39;account a un altro utente dell&#39;account {#task_47E3C66CC6374274830DA10171E0CF17}

In qualità di proprietario dell’account, se intendete annullare l’accesso dovete prima trasferire la proprietà a un altro utente attivo dell’account. È possibile utilizzare [!DNL Transfer Ownership] per eseguire questa attività.

È possibile trasferire la proprietà a qualsiasi utente di account esistente per la ricerca del sito o il merchandising.

Una volta completato il trasferimento di proprietà, il nuovo proprietario dell&#39;account riceve una notifica e-mail e il primo proprietario è esonerato dalle restrizioni e dalle responsabilità di tale posizione.

Può esserci un solo proprietario per account. Se trasferisci la proprietà a un altro utente, non disponi più dei privilegi di proprietà.

Vedere [Annullamento dell&#39;accesso](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

Vedere [Rimozione di un account](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32).

Vedere [Rimozione di se stessi da un account](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F).

**Per trasferire la proprietà del conto a un altro conto**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Transfer Ownership]** dal menu del prodotto.
1. Nella pagina [!DNL Transfer Ownership] fare clic sull&#39;utente di cui si desidera acquisire la proprietà dell&#39;account.
1. Clic **[!UICONTROL Transfer]**.

## Rimozione di un account {#task_975178D5B9444BF8B52D72B897A49C32}

Potete rimuovere un account completamente da un sito di ricerca/merchandising. In questo caso, voi e tutti gli altri utenti del vostro account non avete più accesso a tale account.

Quando rimuovete l&#39;account, non può più essere usato per indicizzare o cercare nel sito live. Inoltre,

Per consentire agli altri utenti di continuare a utilizzare questo account, potete trasferire la proprietà a un altro utente e quindi rimuovervi come utente dell&#39;account.

Vedere [Trasferimento della proprietà dell&#39;account a un altro utente dell&#39;account](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17).

Se disponete di altri account, dopo aver rimosso l’account corrente, viene portato al primo account elencato nell’accesso.

Vedere [Rimozione di se stessi da un account](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F).

Vedere [Annullamento dell&#39;accesso](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

**Per rimuovere un account**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Account]** dal menu del prodotto.
1. (Facoltativo) Nel campo [!DNL Reason for Removal], immettere un motivo per la rimozione dell&#39;account.
1. Clic **[!UICONTROL Remove Account]**.

## Rimozione di se stessi da un account {#task_C56F5AB87B664BAAAC2FD2F15003E73F}

Puoi rimuoverti da un account di ricerca/merchandising del sito.

Quando si rimuove un utente da un account, non è più possibile accedervi e non è possibile modificare le impostazioni dell&#39;account né indicizzare il sito con esso.

Per ripristinare l’accesso all’account, chiedete a un utente corrente di ripristinarvi.

Vedere [Annullamento dell&#39;accesso](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

Vedere [Rimozione di un account](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32).

Vedere [Trasferimento della proprietà dell&#39;account a un altro utente dell&#39;account](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17).

**Per rimuovere te stesso da un account**

1. Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Yourself]** dal menu del prodotto.
1. Clic **[!UICONTROL Remove Yourself]**.
