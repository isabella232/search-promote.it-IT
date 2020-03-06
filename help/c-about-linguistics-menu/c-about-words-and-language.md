---
description: È possibile utilizzare Parole e lingua per determinare la corrispondenza tra i termini di ricerca e il contenuto delle pagine Web.
seo-description: È possibile utilizzare Parole e lingua per determinare la corrispondenza tra i termini di ricerca e il contenuto delle pagine Web.
seo-title: Parole e lingua
solution: Target
title: Parole e lingua
topic: Linguistics,Site search and merchandising
uuid: 793d7a40-4609-44b8-a170-536eb1434537
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Parole e lingua{#about-words-language}

È possibile utilizzare [!DNL Words & Language] per determinare la corrispondenza tra i termini di ricerca e il contenuto delle pagine Web.

## Utilizzo di parole e lingue {#concept_CEB4B9576F3C4E2EB87B352EEC738D79}

Prima che gli effetti delle [!DNL Words & Language] impostazioni siano disponibili per i visitatori del sito, comprese eventuali modifiche apportate a tali impostazioni, dovete rigenerare l’indice del sito. La rigenerazione, a differenza dell&#39;indicizzazione, non comporta la ricerca per indicizzazione delle pagine Web e richiede solo pochi secondi.

## Configurazione della corrispondenza tra i termini di ricerca e il contenuto Web {#task_351A9144A51F4B41923BDBACDEF3B616}

Potete utilizzare Words &amp; Language per determinare in che modo la ricerca nel sito/merchandising corrisponde ai termini di ricerca al contenuto delle pagine Web.

<!-- 

t_configuring_how_search_terms_matched_to_your_web_content.xml

 -->

**Per configurare la corrispondenza tra i termini di ricerca e il contenuto Web**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]** dal menu del prodotto.
1. Nella [!DNL Words & Languages] pagina, impostate le opzioni desiderate.

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
      <td colname="col1"> <p>Sensibilità maiuscole/minuscole </p> </td> 
      <td colname="col2"> <p>Non selezionato per impostazione predefinita. </p> <p>Specifica se le lettere maiuscole devono essere distinte dalle lettere minuscole. Ad esempio, se è selezionata questa opzione, l’opzione "Successo" è distinta da quella "Riuscito" e i risultati della ricerca possono variare tra i due. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sensibilità diacritica </p> </td> 
      <td colname="col2"> <p>Selezionato per impostazione predefinita. </p> <p> Determina se le parole contenenti caratteri diacritici devono essere distinte dalle parole che non lo fanno. Ad esempio, se è selezionata questa opzione, "pagina" si distingue da "página". Deselezionate questa opzione se disponete di un sito Web che utilizza lingue diverse dall’inglese. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numeri </p> </td> 
      <td colname="col2"> <p>Selezionato per impostazione predefinita. </p> <p>Stabilisce se le parole contenenti cifre sono indicizzate. </p> </td> 
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
      <td colname="col2"> <p>Non selezionato per impostazione predefinita. </p> <p>Quando è selezionata, questa opzione consente di suddividere i token in transizioni alfabetiche-numeriche per consentire corrispondenze a testo libero su token parte o prodotto. </p> <p>Ad esempio, supponete di avere un identificatore di prodotto <span class="codeph"> 910XT </span> nel contenuto di una o più pagine di un sito Web. Se questa opzione <i>non</i> è selezionata, <span class="keyword"> Adobe Search&amp;Promote </span> trova le corrispondenze per l’identificatore del prodotto durante la ricerca di <span class="codeph"> 910XT </span>. Inoltre, con <span class="uicontrol"> Search Concat-Div-Enable </span> attivato, <span class="keyword"> Adobe Search&amp;Promote </span> troverà anche <span class="codeph"> 910 XT </span>. Tuttavia, non troverebbero <span class="codeph"> esclusivamente istanze di </span> 910 <span class="codeph"> o </span> XT. </p> <p>Quando si seleziona Corrispondenza alfanumerica <span class="uicontrol"> parziale </span>, l'indicizzatore divide questi token alfanumerici misti in più token. Ad esempio, un identificatore di prodotto come <span class="codeph"> XYZ123 </span> è indicizzato in tre token: <span class="codeph"> XYZ123 </span>, <span class="codeph"> XYZ </span>e <span class="codeph"> 123 </span>. Questa funzionalità consente la corrispondenza del testo in tempo libero su una di queste varianti. </p> <p>In un altro esempio, supponete di avere l'identificatore del prodotto <span class="codeph"> AB910XT </span>. Se selezionate <span class="uicontrol"> Corrispondenza alfanumerica parziale </span> e fate <i>sì che</i> Search Concat-Div-Enable <span class="uicontrol"> sia attivato, </span> Adobe Search Promote <span class="keyword"> lo indicizza come </span> <span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span>AB910XT, AB, 910, 910, e XT. Quindi, quando un utente cerca <span class="codeph"> 910XT </span>, ad esempio, la ricerca si espande per trovare anche le istanze di <span class="codeph"> 910XT </span>, <span class="codeph"> 910 </span>, o <span class="codeph"> XT </span>. </p> <p> <p>Nota:  <span class="uicontrol"> Search Concat-Div-Enable non </span> è attivato per impostazione predefinita. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. </p> </p> <p> <p>Nota:  La corrispondenza alfanumerica <span class="uicontrol"> parziale </span> viene applicata globalmente a tutti i campi indicizzati. Tuttavia, incide solo sulla corrispondenza del testo libero; non influisce sulla corrispondenza esatta o sulla corrispondenza dell'intervallo. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Corrispondenza simile all'audio </p> </td> 
      <td colname="col2"> <p>Selezionato per impostazione predefinita. </p> <p>Parole che suonano allo stesso modo sono associate come "salute" e "salute". Questa funzione consente al cliente di effettuare facilmente ricerche nonostante la parola non sia corretta. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Moduli Word alternativi </p> </td> 
      <td colname="col2"> <p>Il valore predefinito è <b>Moduli</b>Word alternativi predefiniti. </p> <p>È possibile selezionare una delle seguenti opzioni nell'elenco a discesa Moduli Word alternativi: 
      <ul id="ul_CAC73FB4D1384312BB5DD327D3D66948"> 
      <li id="li_F4E76CD27EA34AC5BC81E648BC6CBA4C"><b>None (Nessuno)</b> <p>Durante l'indicizzazione non vengono applicate forme di stemming o di parole alternative. </p> </li> 
      <li id="li_3186FD1F3BC94A5CB66FFF8EA6726D81"><b>Moduli Word alternativi predefiniti</b> <p>La creazione dello schema viene eseguita automaticamente durante l'indicizzazione. </p> </li> 
      <li id="li_5815DE0795E0423C9C84C62B96A3F841"><b>Dizionario di dominio</b> <p>I dizionari di dominio impostati come dizionario di origine vengono utilizzati come fonte di moduli di parole alternative. </p> <p>Vedere <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> Informazioni sui dizionari </a>. </p> <p>Consultate <a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074" type="task" format="dita" scope="local"> Configurazione di un dizionario come dizionario stemming </a>. </p> </li> 
      </ul> </p> <p>Se in <span class="keyword"> </span>Adobe Search&amp;Promote è abilitata la creazione dello stemming delle frasi, tenete presente che anche all'interno delle frasi si verificano moduli di parole alternative. </p> <p>Consultate <a href="../c-searchpromote-release-notes/c-rn-06-19-14-version-815.md#concept_E8CEBC65A28A4E61BDE69B4B4DA55E73" format="dita" scope="local"> Note sulla versione di Search&amp;Promote 8.15.0 (19/6/2014) </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lingua </p> </td> 
      <td colname="col2"> <p>Il valore predefinito è <b>Inglese (Stati Uniti)</b>. </p> <p>La lingua selezionata assicura che i valori data e numerici siano analizzati in base alle convenzioni utilizzate nella parte selezionata del mondo. </p> <p>Se <span class="uicontrol"> Moduli Word alternativi </span> è impostato su Moduli Word alternativi <span class="uicontrol"> predefiniti </span> o su Dizionario di <span class="uicontrol"> </span>dominio, i moduli delle parole e le terminazioni delle parole vengono modificati in base alle regole linguistiche della lingua selezionata. </p> <p>Per impostazione predefinita, l’impostazione Lingua non viene utilizzata per determinare la lingua delle pagine lette dal sito Web. La lingua di una pagina di lettura è determinata dalle intestazioni HTTP corrispondente o dai metatag all’interno della pagina stessa. Il sito Web può contenere pagine in diverse lingue. Ogni pagina viene letta e indicizzata correttamente, indipendentemente dalla lingua selezionata. </p> <p>Se per alcune pagine del sito Web utilizzate la codifica di un set di caratteri Unicode, ad esempio UTF-8, accertatevi che la lingua di ciascuna di queste pagine sia specificata correttamente. Se le intestazioni o i metatag HTTP appropriati non esistono per i documenti Unicode, potete utilizzare <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Injections </span> per specificare la lingua appropriata. </p> <p>Selezionare <span class="uicontrol"> Applica a documenti senza una lingua specificata? </span> per utilizzare l'impostazione Lingua per le pagine lette dal sito Web che non hanno un'impostazione esplicita. Utilizzate questa impostazione quando solo <i>alcuni</i> documenti non dispongono di impostazioni di lingua. Utilizzate <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Iniezioni </span> se <i>nessuno</i> dei vostri documenti dispone di impostazioni di lingua, oppure se il set di documenti interessati è un elenco ben noto e facilmente gestibile. </p> <p>Consulta <a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5" type="concept" format="dita" scope="local"> Informazioni sulle iniezioni </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Utilizzare Decompounder? </p> </td> 
      <td colname="col2"> <p> <p>Nota:  Questa funzione è utilizzata solo per danese e tedesco. Inoltre, questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. Una volta attivato, l' <b>opzione Usa decomposizione?</b> l'opzione viene visualizzata nell'interfaccia utente solo se si seleziona <span class="uicontrol"> Danese </span> o <span class="uicontrol"> Tedesco </span> dall'elenco a discesa <span class="uicontrol"> </span> Lingua descritto in precedenza in questa tabella. </p> </p> <p>Quando si seleziona <span class="uicontrol"> Use Decompounder? </span>, il servizio scompone le parole composte danesi o tedesche, che consentono l'indicizzazione delle parole componenti insieme alle parole composte originali. </p> <p>Per vedere come funziona questa funzione, immettete le parole nel campo di testo e fate clic su <span class="uicontrol"> Prova </span>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Settings]**.
1. Per visualizzare in anteprima i risultati delle modifiche, fate clic **[!UICONTROL regenerate your staged site index]** per ricreare l’indice del sito Web in fase di creazione.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

