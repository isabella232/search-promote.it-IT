---
description: È possibile utilizzare Parole e lingua per determinare la corrispondenza dei termini di ricerca con il contenuto delle pagine web.
solution: Target
title: Parole e lingua
topic-legacy: Linguistics,Site search and merchandising
uuid: 793d7a40-4609-44b8-a170-536eb1434537
exl-id: bfc84879-1fd1-4c86-beab-353469014c64
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 0%

---

# Informazioni su parole e lingua{#about-words-language}

È possibile utilizzare [!DNL Words & Language] per determinare la corrispondenza dei termini di ricerca con il contenuto delle pagine web.

## Utilizzo di parole e lingua {#concept_CEB4B9576F3C4E2EB87B352EEC738D79}

Prima che gli effetti delle impostazioni [!DNL Words & Language] siano disponibili per i visitatori del sito, comprese eventuali modifiche apportate a tali impostazioni, è necessario rigenerare l&#39;indice del sito. La rigenerazione, a differenza dell’indicizzazione, non comporta la ricerca per indicizzazione delle pagine web e richiede solo pochi secondi.

## Configurazione della corrispondenza dei termini di ricerca con i contenuti web {#task_351A9144A51F4B41923BDBACDEF3B616}

È possibile utilizzare parole e lingua per determinare in che modo la ricerca/merchandising del sito corrisponde i termini di ricerca al contenuto delle pagine web.

<!-- 

t_configuring_how_search_terms_matched_to_your_web_content.xml

 -->

**Per configurare la corrispondenza dei termini di ricerca con i contenuti web**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]** dal menu del prodotto.
1. Nella pagina [!DNL Words & Languages] , imposta le opzioni desiderate.

   <!-- 
   
   r_words_and_languages_options.xml
   
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
      <td colname="col1"> <p>Sensibilità ai casi </p> </td> 
      <td colname="col2"> <p>Non selezionato per impostazione predefinita. </p> <p>Determina se le lettere maiuscole vengono distinte dalle lettere minuscole. Ad esempio, se questa opzione è selezionata, l’opzione "Completato" è distinta da quella "Completato" e i risultati della ricerca possono variare tra le due. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sensibilità diacritica </p> </td> 
      <td colname="col2"> <p>Selezionato per impostazione predefinita. </p> <p> Determina se le parole che contengono caratteri diacritici devono essere distinte dalle parole che non lo fanno. Ad esempio, se selezionato, "pagina" è distinto da "página". Deseleziona questa opzione se disponi di un sito web che utilizza lingue diverse dall’inglese. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numeri </p> </td> 
      <td colname="col2"> <p>Selezionato per impostazione predefinita. </p> <p>Determina se le parole contenenti cifre sono indicizzate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignora apostrofi </p> </td> 
      <td colname="col2"> <p>Non selezionato per impostazione predefinita. </p> <p>Gli apostrofi vengono rimossi dalle query. Ad esempio, una ricerca per "Albero" restituirebbe gli stessi risultati di una ricerca per "Alberi". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignora trattini </p> </td> 
      <td colname="col2"> <p>Non selezionato per impostazione predefinita. </p> <p>I trattini vengono rimossi dalle query. Ad esempio, una ricerca per "blue-bell" restituirebbe gli stessi risultati di una ricerca per "bluebell". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Corrispondenza alfanumerica parziale </p> </td> 
      <td colname="col2"> <p>Non selezionato per impostazione predefinita. </p> <p>Quando è selezionata, questa opzione consente di suddividere i token nelle transizioni alfabetiche-numeriche per consentire corrispondenze a testo libero su token parte o prodotto. </p> <p>Ad esempio, supponi di avere un identificatore di prodotto <span class="codeph"> 910XT </span> nel contenuto del corpo di una o più pagine di un sito web. Quando questa opzione è <i>non</i> selezionata, <span class="keyword"> l'Adobe </span> trova le corrispondenze per questo identificatore del prodotto durante la ricerca di <span class="codeph"> 910XT </span>. Inoltre, con <span class="uicontrol"> Search Concat-Div-Enable </span> attivato, <span class="keyword"> Adobe Search&amp;Promote </span> troverà anche <span class="codeph"> 910 XT </span>. Tuttavia, non troverebbe esclusivamente istanze di <span class="codeph"> 910 </span> o <span class="codeph"> XT </span>. </p> <p>Quando selezioni <span class="uicontrol"> Corrispondenza alfanumerica parziale </span>, l’indicizzatore suddivide questi token alfanumerici misti in più token. Ad esempio, un identificatore di prodotto come <span class="codeph"> XYZ123 </span> è indicizzato in tre token: <span class="codeph"> XYZ123 </span>, <span class="codeph"> XYZ </span> e <span class="codeph"> 123 </span>. Tali funzionalità consentono la corrispondenza di testo in tempo libero su una qualsiasi di queste varianti. </p> <p>In un altro esempio, supponiamo di avere l'identificatore del prodotto <span class="codeph"> AB910XT </span>. Se si seleziona <span class="uicontrol"> Corrispondenza alfanumerica parziale </span> <i>e</i> <span class="uicontrol"> Cerca Concat-Div-Abilita </span> attivata, <span class="keyword"> Search&amp;Promote Adobe </span> lo indicizza come <span class="codeph"> AB910XT </span>, <span class="codeph"> AB </span>, <span class="codeph"> 910 </span> e <span class="codeph"> XT </span>. Quindi, quando un utente cerca <span class="codeph"> 910XT </span>, ad esempio, la ricerca si espande per trovare anche le istanze di <span class="codeph"> 910XT </span>, <span class="codeph"> 910 </span> o <span class="codeph"> XT </span>. </p> <p> <p>Nota:  <span class="uicontrol"> Search Concat-Div-Enable </span> non è abilitato per impostazione predefinita. Contatta il supporto tecnico per attivare la funzione. </p> </p> <p> <p>Nota:  <span class="uicontrol"> La corrispondenza alfanumerica parziale </span> viene applicata globalmente a tutti i campi indicizzati. Tuttavia, influisce solo sulla corrispondenza in formato libero; non influisce sulla corrispondenza esatta o sulla corrispondenza dell’intervallo. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Corrispondenza simile al suono </p> </td> 
      <td colname="col2"> <p>Selezionato per impostazione predefinita. </p> <p>Parole che somigliano al suono sono abbinate come "salute" e "salute". Questa funzione consente al cliente di effettuare ricerche facilmente nonostante l’invio errato di una parola. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Forms di Word alternativo </p> </td> 
      <td colname="col2"> <p>Il valore predefinito è <b>Forms alternativo predefinito di Word</b>. </p> <p>È possibile selezionare una delle seguenti opzioni nell'elenco a discesa Forms di Word alternativo: 
      <ul id="ul_CAC73FB4D1384312BB5DD327D3D66948"> 
      <li id="li_F4E76CD27EA34AC5BC81E648BC6CBA4C"><b>None (Nessuno)</b> <p>Durante l’indicizzazione non vengono applicate forme di stemming o di word alternative. </p> </li> 
      <li id="li_3186FD1F3BC94A5CB66FFF8EA6726D81"><b>Forms di Word alternativo predefinito</b> <p>Lo stampaggio viene eseguito automaticamente durante l'indicizzazione. </p> </li> 
      <li id="li_5815DE0795E0423C9C84C62B96A3F841"><b>Dizionario di dominio</b> <p>Qualsiasi dizionario di dominio impostato come dizionario di origine viene utilizzato come origine di moduli di parole alternative. </p> <p>Vedere <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> Informazioni sui dizionari </a>. </p> <p>Consultare <a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074" type="task" format="dita" scope="local"> Configurazione di un dizionario come dizionario di origine </a>. </p> </li> 
      </ul> </p> <p>Se lo stemming delle frasi è abilitato in <span class="keyword"> Search&amp;Promote di Adobe </span>, tenere presente che i moduli di parole alternative si verificano anche all'interno di frasi. </p> <p>Consulta <a href="../c-searchpromote-release-notes/c-rn-06-19-14-version-815.md#concept_E8CEBC65A28A4E61BDE69B4B4DA55E73" format="dita" scope="local"> Note sulla versione di Search&amp;Promote 8.15.0 (19/6/2014) </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lingua </p> </td> 
      <td colname="col2"> <p>Il valore predefinito è <b>Inglese (Stati Uniti)</b>. </p> <p>La lingua selezionata assicura che i valori numerici e di data vengano analizzati in base alle convenzioni utilizzate nella parte selezionata del mondo. </p> <p>Quando <span class="uicontrol"> Forms di Word alternativo </span> è impostato su <span class="uicontrol"> Forms di Word alternativo predefinito </span> o su <span class="uicontrol"> Dizionario di dominio </span>, i moduli di parole e le terminazioni di parole vengono modificati in base alle regole linguistiche per la lingua selezionata. </p> <p>Per impostazione predefinita, l’impostazione Lingua non viene utilizzata per determinare la lingua delle pagine lette dal sito web. La lingua di una pagina di lettura è determinata dalle relative intestazioni HTTP o dai metatag all’interno della pagina stessa. Il tuo sito web potrebbe contenere pagine in molte lingue diverse. Ogni pagina viene letta e indicizzata correttamente, indipendentemente dalla lingua selezionata. </p> <p>Se utilizzi una codifica per set di caratteri Unicode, ad esempio UTF-8, per alcune pagine del sito web, assicurati che la lingua per ciascuna di queste pagine sia specificata correttamente. Se le intestazioni o i metatag HTTP appropriati non esistono per i documenti Unicode, è possibile utilizzare <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Iniezioni </span> per specificare la lingua appropriata. </p> <p>Controllare <span class="uicontrol"> Applica ai documenti senza una lingua specifica? </span> utilizzare l’impostazione Lingua per le pagine lette dal sito web che non hanno un’impostazione esplicita. Utilizzare questa impostazione quando solo <i>alcuni</i> dei documenti non dispongono di impostazioni di lingua. Utilizza <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Iniezioni </span> se <i>none</i> dei tuoi documenti dispone di impostazioni di lingua o se il set di documenti interessati è un elenco ben noto e gestibile di piccole dimensioni. </p> <p>Consulta <a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5" type="concept" format="dita" scope="local"> Informazioni sulle iniezioni </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Utilizzare Decompounder? </p> </td> 
      <td colname="col2"> <p> <p>Nota:  Questa funzione è utilizzata solo per danese e tedesco. Inoltre, questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivare la funzione. Dopo l'abilitazione, utilizza <b>decomposizione?</b> l’opzione viene visualizzata nell’interfaccia utente solo se si seleziona  <span class="uicontrol"> Danese  </span> o  <span class="uicontrol"> Tedesco  </span> dall’elenco a  <span class="uicontrol"> discesa  </span> Lingua descritto in precedenza in questa tabella. </p> </p> <p>Quando si seleziona <span class="uicontrol"> Use Decompounder? </span>, il servizio scompone le parole composte danesi o tedesche, che permettono l'indicizzazione delle parole che compongono insieme alle parole composte originali. </p> <p>Per vedere come funziona questa funzione, immetti le parole nel campo di testo, quindi fai clic su <span class="uicontrol"> Test </span>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Settings]**.
1. Per visualizzare in anteprima i risultati delle modifiche, fai clic su **[!UICONTROL regenerate your staged site index]** per ricreare l’indice del sito web in staging.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
