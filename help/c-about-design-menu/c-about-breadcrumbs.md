---
description: Le breadcrumb sono un controllo di navigazione che puoi aggiungere al tuo sito web. La breadcrumb fornisce ai clienti un feedback sulla posizione in cui si trovano all’interno di un set di risultati di ricerca. Consente inoltre di tornare rapidamente a un passaggio precedente.
solution: Target
subtopic: Navigation
title: Informazioni sulle breadcrumb
topic: Progettazione, ricerca nel sito e merchandising
uuid: 3e630a72-a631-4f4f-8aa5-adf2882cdf1c
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 1%

---


# Informazioni su Breadcrumb{#about-breadcrumbs}

Le breadcrumb sono un controllo di navigazione che puoi aggiungere al tuo sito web. La breadcrumb fornisce ai clienti un feedback sulla posizione in cui si trovano all’interno di un set di risultati di ricerca. Consente inoltre di tornare rapidamente a un passaggio precedente.

## Utilizzo delle breadcrumb {#concept_FB8A943C594A4A1593B118141DA61F03}

Le breadcrumb tengono traccia del termine ricercato e dei facet successivi selezionati per restringere il set di risultati.

Utilizza le impostazioni Breadcrumb per personalizzare il controllo breadcrumb del livello di presentazione di ricerca. Se il livello di presentazione presenta più di un set di risultati di ricerca, il controllo breadcrumb agisce sulla ricerca primaria sulla pagina.

Puoi modificare una breadcrumb per modificare il comportamento predefinito, la larghezza massima del valore e l’estensione del valore, e per selezionare se includere il termine della query.

## Aggiunta di una nuova breadcrumb {#task_2FFA94F82AE74F10BDDE7367CDCEAE8B}

Puoi aggiungere una barra di navigazione in modo che un cliente possa tracciare la posizione del sito web.

<!-- 

t_adding_a_new_breadcrumb.xml

 -->

>[!NOTE]
>
>Assicurati di fare riferimento alla breadcrumb nel modello di presentazione in modo che sia visibile sul sito web.

**Per aggiungere una nuova breadcrumb**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Nella pagina [!DNL Breadcrumbs], fai clic su **[!UICONTROL Add Breadcrumb]**.
1. Nella pagina [!DNL Add Breadcrumb] , imposta le opzioni desiderate.

   Queste impostazioni influiscono sia sul comportamento che sulla presentazione predefinita di una breadcrumb. È possibile ignorare alcune di queste impostazioni tramite le impostazioni del modello di presentazione.

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
      <td colname="col2"> <p>Nome del breadcrumb. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Comportamento </p> </td> 
      <td colname="col2"> <p>Imposta uno dei tre comportamenti di breadcrumb seguenti: </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
        <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Goto  </span> <p>Goto rimuove tutte le breadcrumb dopo quella su cui si è fatto clic e avvia una nuova ricerca in quel punto. </p> </li> 
        <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> Rimuovi </span> <p>Rimuovi elimina dal percorso la breadcrumb su cui il cliente ha fatto clic e quindi avvia una nuova ricerca. Questo comportamento è utile quando si desidera consentire al cliente di annullare i passaggi nel drilling verso il basso attraverso la ricerca. </p> </li> 
        <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> Elimina  </span> <p>Rilascia rimuove tutte le breadcrumb. </p> </li> 
      </ul> </p> <p> Ad esempio, supponiamo che tu abbia una breadcrumb di 1 &gt; 2 &gt; 3 &gt; 4. Quando un cliente fa clic su "2", ha i seguenti risultati, in base al comportamento scelto: </p> <p> 
      <ul id="ul_96FCD8E4C3704B45B59BC18A7A1AC52A"> 
        <li id="li_B880037088DF426F880788EAA3072180">Vai a - 1 &gt; 2 </li> 
        <li id="li_D0F07A15DCD043EFA4563632ED33A9E2">Rimuovi - 1 &gt; 3 &gt; 4 </li> 
        <li id="li_D848ED44B4E44538AA92010F9F186224"> Caduta - L'intero percorso di navigazione viene rilasciato, riportando il cliente al punto prima di iniziare a eseguire il drill-down. </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Larghezza max. </p> </td> 
      <td colname="col2"> <p>Specifica la lunghezza di ogni valore nella traccia breadcrumb. È possibile specificare l’impostazione come numero di caratteri. </p> <p>Ad esempio, un’impostazione di 6 indica che la traccia breadcrumb può essere lunga fino a 6 caratteri, compresi gli spazi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Estensione valore </p> </td> 
      <td colname="col2"> <p>Specifica i puntini di sospensione da utilizzare quando un breadcrumb viene troncato. </p> <p>Per impostazione predefinita un ".." (puntini di sospensione). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi termine query </p> </td> 
      <td colname="col2"> <p>Controlla la presenza di un termine di query in una breadcrumb. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilita bretelle definite dall'utente </p> </td> 
      <td colname="col2"> <p>Seleziona per consentire l'utilizzo degli elementi definiti dall'utente nei breadcrumb utilizzando i parametri <span class="codeph"> uX=[name]&amp;[name]=[value] </span> nell'URL. Puoi utilizzare le regole di elaborazione per gestire questi parametri nel modo desiderato. </p> <p>Ad esempio, se questa funzione è abilitata e disponi dell'URL, <code> https://search.host.com/?1=category&amp;q1=Clothes&amp;u2= 
          type&amp;type=Men&amp;x3=kind&amp;q3=Sweater </code> nel caso in cui si disponga di facet <span class="codeph"> <span class="varname"> categoria </span> </span> e <span class="codeph"> tipo <span class="varname"> </span> </span>, il breadcrumb sarà simile a <span class="codeph"> Abiti &gt; Uomini &gt; Maglione </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nomi Crumb Definiti Dall'Utente </p> </td> 
      <td colname="col2"> <p>Elenco separato da virgole di tutti i possibili nomi di elementi breadcrumb definiti dall’utente. </p> <p>Questa opzione è disponibile solo se si seleziona <span class="uicontrol"> Abilita briciole definite dall'utente </span>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Nella pagina [!DNL Breadcrumbs] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di una breadcrumb {#task_583481D9A23E4E0F97AEB18E72CBE13F}

Puoi modificare le impostazioni di qualsiasi breadcrumb aggiunto.

<!-- 

t_editing_a_breadcrumb.xml

 -->

>[!NOTE]
>
>Assicurati di fare riferimento alla breadcrumb nel modello di presentazione in modo che sia visibile sul sito web.

**Per modificare una breadcrumb**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Nella pagina [!DNL Breadcrumbs] , fai clic su **[!UICONTROL Edit]** all’estrema destra del nome di una breadcrumb.
1. Nella pagina [!DNL Edit Breadcrumb] , imposta le opzioni desiderate.

   Vedi la tabella delle opzioni in [Aggiunta di una nuova breadcrumb](../c-about-design-menu/c-about-breadcrumbs.md#task_2FFA94F82AE74F10BDDE7367CDCEAE8B).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella pagina **[!UICONTROL Breadcrumb]** , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una breadcrumb {#task_401C6E481A744284906E15A29E04F757}

Puoi eliminare qualsiasi breadcrumb aggiunto.

<!-- 

t_deleting_a_breadcrumb.xml

 -->

**Per eliminare una breadcrumb**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Nella pagina [!DNL Breadcrumbs] , fai clic su **[!UICONTROL Delete]** all’estrema destra del nome di una breadcrumb.
1. Nella finestra di dialogo [!DNL Confirmation] fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

