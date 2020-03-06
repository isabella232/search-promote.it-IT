---
description: Le breadcrumb sono un controllo di navigazione che potete aggiungere al sito Web. La breadcrumb fornisce ai clienti un feedback sulla posizione in cui si trovano all’interno di un set di risultati di ricerca. Consente inoltre di tornare rapidamente a un passaggio precedente.
seo-description: Le breadcrumb sono un controllo di navigazione che potete aggiungere al sito Web. La breadcrumb fornisce ai clienti un feedback sulla posizione in cui si trovano all’interno di un set di risultati di ricerca. Consente inoltre di tornare rapidamente a un passaggio precedente.
seo-title: Informazioni su Breadcrumb
solution: Target
subtopic: Navigation
title: Informazioni su Breadcrumb
topic: Design,Site search and merchandising
uuid: 3e630a72-a631-4f4f-8aa5-adf2882cdf1c
translation-type: tm+mt
source-git-commit: 7f1b5d94e8002992d62ec1e3dce11f9c5605fde8

---


# Informazioni su Breadcrumb{#about-breadcrumbs}

Le breadcrumb sono un controllo di navigazione che potete aggiungere al sito Web. La breadcrumb fornisce ai clienti un feedback sulla posizione in cui si trovano all’interno di un set di risultati di ricerca. Consente inoltre di tornare rapidamente a un passaggio precedente.

## Utilizzo di Breadcrumb {#concept_FB8A943C594A4A1593B118141DA61F03}

Le breadcrumb tengono traccia del termine ricercato e dei facet successivi selezionati per restringere il set di risultati.

Usate le impostazioni Breadcrumb per personalizzare il controllo breadcrumb del livello di ricerca della presentazione. Se il livello della presentazione contiene più di un set di risultati di ricerca, il controllo breadcrumb agisce sulla ricerca principale nella pagina.

È possibile modificare una breadcrumb per modificare il comportamento predefinito, la larghezza massima e l&#39;estensione del valore, nonché per selezionare se includere o meno il termine della query.

## Adding a new breadcrumb {#task_2FFA94F82AE74F10BDDE7367CDCEAE8B}

Potete aggiungere una barra di navigazione per consentire al cliente di tenere traccia della posizione sul sito Web.

<!-- 

t_adding_a_new_breadcrumb.xml

 -->

>[!NOTE]
>
>Assicuratevi di fare riferimento alla breadcrumb nel modello di presentazione in modo che sia visibile sul sito Web.

**Per aggiungere una nuova breadcrumb**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Sulla [!DNL Breadcrumbs] pagina, fate clic su **[!UICONTROL Add Breadcrumb]**.
1. Nella [!DNL Add Breadcrumb] pagina, impostate le opzioni desiderate.

   Queste impostazioni influiscono sia sul comportamento che sulla presentazione predefinita di una breadcrumb. Potete ignorare alcune di queste impostazioni mediante le impostazioni del modello di presentazione.

   <!-- 
   
   r_breadcrumb_options.xml
    
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
      <td colname="col1"> <p>Nome Breadcrumb </p> </td> 
      <td colname="col2"> <p>Nome del percorso di navigazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Comportamento </p> </td> 
      <td colname="col2"> <p>Imposta uno dei tre seguenti comportamenti di breadcrumb: </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
        <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Goto </span> <p>Vai rimuove tutte le breadcrumb dopo quella su cui si fa clic e inizia una nuova ricerca a quel punto. </p> </li> 
        <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> Rimuovi </span> <p>Rimuovi elimina dal percorso la breadcrumb su cui il cliente ha fatto clic e avvia una nuova ricerca. Questo comportamento è utile quando si desidera consentire al cliente di annullare i passaggi necessari per eseguire la ricerca. </p> </li> 
        <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> Drop </span> <p>Drop rimuove tutte le breadcrumb. </p> </li> 
      </ul> </p> <p> Ad esempio, supponiamo che il percorso di navigazione sia 1 &gt; 2 &gt; 3 &gt; 4. Quando un cliente fa clic su "2", si ottengono i seguenti risultati, in base al comportamento scelto: </p> <p> 
      <ul id="ul_96FCD8E4C3704B45B59BC18A7A1AC52A"> 
        <li id="li_B880037088DF426F880788EAA3072180">Vai a - 1 &gt; 2 </li> 
        <li id="li_D0F07A15DCD043EFA4563632ED33A9E2">Rimuovi - 1 &gt; 3 &gt; 4 </li> 
        <li id="li_D848ED44B4E44538AA92010F9F186224"> Drop - L'intero percorso di navigazione viene rimosso, riportando il cliente al punto prima che inizi a scendere. </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Larghezza valore max </p> </td> 
      <td colname="col2"> <p>Specifica la lunghezza di ciascun valore nella traccia breadcrumb. Potete specificare l'impostazione come numero di caratteri. </p> <p>Ad esempio, con un'impostazione pari a 6 la traccia breadcrumb può essere lunga fino a 6 caratteri, compresi gli spazi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Estensione valore </p> </td> 
      <td colname="col2"> <p>Specifica le ellissi da utilizzare quando un percorso di navigazione viene troncato. </p> <p>Per impostazione predefinita, un ".." (ellissi). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi termine query </p> </td> 
      <td colname="col2"> <p>Controlla la presenza del termine della query in una breadcrumb. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilita Crumbs Definite Dall’Utente </p> </td> 
      <td colname="col2"> <p>Selezionate questa opzione per utilizzare gli elementi definiti dall’utente nelle breadcrumb utilizzando i parametri <span class="codeph"> uX=[nome]&amp;[nome]=[valore] </span> nell’URL. È possibile utilizzare le regole di elaborazione per gestire questi parametri nel modo desiderato. </p> <p>Ad esempio, se questa funzione è attivata e si dispone dell’URL, <code> https://search.host.com/?1=category&amp;q1=Clothes&amp;u2= 
          type&amp;type=Men&amp;x3=kind&amp;q3=Sweater </code> nel caso in cui si disponga di facet <span class="codeph"> categoria <span class="varname"> e </span> tipo </span> di sfaccettatura <span class="codeph"> , il percorso del pangrattolo sarà simile a <span class="varname"> </span> </span><span class="codeph"> </span>Abiti &gt; Uomini &gt; . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nomi Crumb Definiti Dall’Utente </p> </td> 
      <td colname="col2"> <p>Un elenco separato da virgole di tutti i possibili nomi di elementi di breadcrumb definiti dall'utente. </p> <p>Questa opzione è disponibile solo se selezionate <span class="uicontrol"> Abilita crepuscoli definiti dall’utente </span>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Nella [!DNL Breadcrumbs] pagina, effettuare una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica di una breadcrumb {#task_583481D9A23E4E0F97AEB18E72CBE13F}

Potete modificare le impostazioni di qualsiasi breadcrumb aggiunto.

<!-- 

t_editing_a_breadcrumb.xml

 -->

>[!NOTE]
>
>Assicuratevi di fare riferimento alla breadcrumb nel modello di presentazione in modo che sia visibile sul sito Web.

**Per modificare una breadcrumb**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Nella [!DNL Breadcrumbs] pagina, fate clic **[!UICONTROL Edit]** all’estrema destra del nome di una breadcrumb.
1. Nella [!DNL Edit Breadcrumb] pagina, impostate le opzioni desiderate.

   Consultate la tabella delle opzioni in [Aggiunta di una nuova breadcrumb](../c-about-design-menu/c-about-breadcrumbs.md#task_2FFA94F82AE74F10BDDE7367CDCEAE8B).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella **[!UICONTROL Breadcrumb]** pagina, effettuare una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di una breadcrumb {#task_401C6E481A744284906E15A29E04F757}

Potete eliminare qualsiasi breadcrumb aggiunto.

<!-- 

t_deleting_a_breadcrumb.xml

 -->

**Per eliminare una breadcrumb**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Nella [!DNL Breadcrumbs] pagina, fate clic **[!UICONTROL Delete]** all’estrema destra del nome di una breadcrumb.
1. Nella finestra di [!DNL Confirmation] dialogo fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

