---
description: È possibile utilizzare i menu per personalizzare il livello della presentazione.
solution: Target
subtopic: Navigation
title: Informazioni sui menu
topic: Progettazione, ricerca nel sito e merchandising
uuid: 011050cd-21b6-4150-9503-18fa3f771626
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---


# Informazioni su Menu{#about-menus}

È possibile utilizzare i menu per personalizzare il livello della presentazione.

## Utilizzo dei menu {#concept_68123CE5CF4447B59217B5D721424E32}

Aggiungi i menu da mappare alle impostazioni all’interno della ricerca. Ogni voce all&#39;interno di un menu specifica il valore per l&#39;impostazione del menu. È inoltre possibile personalizzare le etichette del menu.

Nel modello di presentazione è possibile fare riferimento ai menu definiti. Puoi quindi inserirli in qualsiasi componente HTML desiderato, ad esempio un controllo selezionato. Questa combinazione consente agli utenti di personalizzare i risultati della ricerca. Sono supportati tre tipi di menu: ordinamento, conteggio e navigazione.

## Aggiunta di un nuovo menu {#task_EE171532D3AE477FAFE8C2F4077A6D73}

È possibile aggiungere menu mappati alle impostazioni all’interno dei risultati della ricerca.

<!-- 

t_adding_a_new_menu.xml

 -->

>[!NOTE]
>
>Assicurati di fare riferimento al menu nel modello di presentazione in modo che sia visibile sul sito web.

**Aggiunta di un nuovo menu**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**.
1. Nella pagina [!DNL Menus], fai clic su **[!UICONTROL Add New Menu]**.
1. Nella pagina [!DNL Add Menu] , imposta le opzioni desiderate.

   Queste impostazioni influiscono sia sul comportamento che sulla presentazione predefinita di una breadcrumb. È possibile ignorare alcune di queste impostazioni tramite le impostazioni del modello di presentazione.

   Consultare [Informazioni sui menu](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32).

   <!-- 
   r_add_menu_options.xml
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome menu </p> </td> 
      <td colname="col2"> <p>Nome del menu. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo di menu </p> </td> 
      <td colname="col2"> <p>Imposta uno dei tre tipi di menu seguenti: </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
      <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Ordinare  </span> <p>Organizza la ricerca in base a uno qualsiasi dei tipi di metadati definiti. </p> <p>Ad esempio, puoi definire un menu di ordinamento con i seguenti tipi di metadati: tre punti rilevanti; un campo di metadati personalizzato, ad esempio un codice di disponibilità; e il prezzo. I tre elementi possono essere indicati rispettivamente le etichette "Ordina per pertinenza", "Ordina per disponibilità" e "Ordina per prezzo". Quando lo includi nel modello di presentazione, il cliente può utilizzare questo controllo per ordinare i risultati della ricerca. </p> </li> 
      <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> Conteggio  </span> <p>Definisce il numero di risultati di ricerca da visualizzare. Questo tipo di menu è associato al parametro cgi <span class="varname"> sp_c </span>. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> Parametri CGI di ricerca back-end </a>. </p> </li> 
      <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> Navigazione </span> <p>Specifica un set di URL statici associati alle voci di menu. In genere, un menu di navigazione viene utilizzato per creare una barra di navigazione di primo livello nella pagina dei risultati della ricerca. </p> <p>Ad esempio, puoi creare un menu con donne, uomini, ragazzi e ragazze in cui le voci di menu sono simili alle seguenti: 
      <code>
        /?q1=womens;x1=gender 
      </code> 
      <code>
        /?q1=mens;x1=gender 
      </code> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Merchandising </p> 
        <!--DONT' KNOW WHAT THIS DOES--> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se si è scelto il tipo di menu <span class="uicontrol"> Ordina. </span> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero di elementi nel menu </p> </td> 
      <td colname="col2"> <p>Specifica il numero di elementi in un menu. La modifica di questa impostazione aggiunge o elimina campi dal modulo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elemento predefinito </p> </td> 
      <td colname="col2"> <p>Consente di selezionare quale voce di menu viene visualizzata per impostazione predefinita. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore dell'articolo </p> </td> 
      <td colname="col2"> <p>Il valore dell’elemento dipende dal tipo di menu impostato. </p> 
        <ul id="ul_2F14E6AA673640578A2D5161FD9D13EF"> 
        <li id="li_5017EC6E4ACB4B8E99E0AA61CBAAFFAE"> Tipo di menu Ordina <p>Identifica in base all’ordinamento dell’elemento selezionato nel menu. Gli elementi selezionati vengono compilati con campi di metadati ordinabili. </p> <p>Per un singolo elemento è possibile ordinare in base a tre campi di metadati. L'ordinamento viene eseguito nell'ordine specificato. </p> </li> 
        <li id="li_CC6BAFBF969C4367A71B55F08E0758D1"> Tipo di menu Conteggio <p>Consente di specificare il numero di risultati da restituire quando il cliente seleziona questa voce di menu. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Etichetta articolo </p> </td> 
      <td colname="col2"> <p>L’etichetta dell’elemento dipende dal tipo di menu impostato. </p> 
        <ul id="ul_957BF01235F84748B5EB7062D6AEAC41"> 
        <li id="li_03FB2E2C96134A2B8E08154F87F0CD55"> Tipo di menu Ordina <p>Identifica l’etichetta personalizzata che il cliente deve visualizzare quando visualizza questa voce nel menu. </p> </li> 
        <li id="li_C9FE2BC46D9443FB85FEB837C7CA45E1"> Tipo di menu Conteggio <p>Identifica l'etichetta personalizzata che si desidera visualizzare per questa voce di menu. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Nella pagina [!DNL Menus] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di un menu {#task_0770DBFD0C7046169097FB6F771B9114}

Puoi modificare le impostazioni di qualsiasi menu aggiunto.

<!-- 

t_editing_a_menu.xml

 -->

>[!NOTE]
>
>Assicurati di fare riferimento al menu nel modello di presentazione in modo che sia visibile sul sito web.

**Per modificare un menu**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**.
1. Nella pagina [!DNL Menus] , fai clic su **[!UICONTROL Edit]** all’estrema destra del nome di un menu.
1. Nella pagina [!DNL Edit Menu] , imposta le opzioni desiderate.

   Vedi la tabella delle opzioni in [Aggiunta di un nuovo menu](../c-about-design-menu/c-about-menus.md#task_EE171532D3AE477FAFE8C2F4077A6D73).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella pagina [!DNL Menus] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di un menu {#task_645E212311A045CD8D9D906878165F47}

È possibile eliminare qualsiasi menu aggiunto.

<!-- 

t_deleting_a_menu.xml

 -->

**Per eliminare un menu**

1. Nel menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**
1. Nella pagina [!DNL Menus] , fai clic su **[!UICONTROL Delete]** all’estrema destra del nome di un menu.
1. Nella finestra di dialogo [!DNL Confirmation] fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

