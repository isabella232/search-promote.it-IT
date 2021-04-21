---
description: Utilizzare il menu Ricerca per impostare parole, raccolte, restrizioni, anteprima e fotogrammi esclusi.
solution: Target
subtopic: Searching
title: Informazioni sul menu Ricerca
topic-legacy: Settings,Site search and merchandising
uuid: 072111fc-a32b-4acb-8337-cb21bcdb5542
exl-id: 4cb70240-051b-4bf3-ae2a-b151acc7cba1
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '11165'
ht-degree: 1%

---

# Informazioni sul menu Ricerca{#about-the-searching-menu}

Utilizzare il menu Ricerca per impostare parole, raccolte, restrizioni, anteprima e fotogrammi esclusi.

## Informazioni sulle ricerche {#concept_207105CF26B1448F8A3D223787C56AB8}

È possibile utilizzare Ricerche per definire e personalizzare le ricerche denominate a cui possono fare riferimento i modelli di presentazione.

<!-- 

c_about_searches.xml

 -->

Nel modello di presentazione è possibile fare riferimento a qualsiasi ricerca denominata definita all&#39;interno del modulo Ricerche. A sua volta, questo ti consente di personalizzare facilmente il tipo di ricerca che viene effettuata per un dato set di modelli.

Per escludere dai risultati della ricerca frasi e parole comuni utilizzate di frequente, consulta [Configurazione di parole escluse](../c-about-linguistics-menu/c-about-excluded-words.md#task_60BF6BB7A66C48479D2BBB32C0F38CDE).

Per definire aree specifiche e ricercabili del sito web, consulta [Aggiunta di raccolte](../c-about-settings-menu/c-about-searching-menu.md#task_07732D0F00104E59AD421297A704B2F6).

Per specificare un frame di destinazione per i collegamenti ai risultati della ricerca, vedere [Uso dei frame con forms](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Per limitare le ricerche in base al referente HTTP, all&#39;indirizzo IP o allo schema di richiesta (HTTP o HTTPS), consulta [Impostazione dei valori in Anteprima](../c-about-settings-menu/c-about-searching-menu.md#task_CE267A0FF621474E80AB43B67B1C28D7).

## Suggerimenti per la ricerca {#section_22F0E2BCF259459FA5F49FBCC0F09A7C}

Per ottenere risultati di ricerca più specifici, puoi utilizzare i seguenti suggerimenti di ricerca.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Suggerimento per la ricerca </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Controllo ortografia </p> </td> 
   <td colname="col2"> <p>Assicurati che i termini di ricerca siano scritti correttamente. Se <span class="uicontrol"> Corrispondenza simile all'audio </span> è abilitato in <span class="uicontrol"> Linguistica </span> &gt; <span class="uicontrol"> Parole e lingue </span>, il motore di ricerca cerca di trovare parole che abbiano un suono simile ai termini di ricerca. Tuttavia, è sempre meglio cercare di scrivere correttamente i termini di ricerca. </p> <p>Consulta <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Informazioni su parole e lingua </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilizzare più parole </p> </td> 
   <td colname="col2"> <p>Esempio: 
     <code>
       our free product 
     </code> </p> <p>Le query con più parole restituiscono risultati più precisi rispetto alle query con più parole. </p> <p>Ad esempio: 
     <code>
       our free product 
     </code> restituisce risultati più rilevanti rispetto a 
     <code>
       product 
     </code>. </p> <p>Ricorda che i risultati rilevanti vengono restituiti anche se non contengono tutti i termini di query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usa parole simili </p> </td> 
   <td colname="col2"> <p>Esempio: 
     <code>
       safe secure privacy security 
     </code> </p> <p>Le parole più simili utilizzabili in una query di ricerca risultano più rilevanti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilizzare maiuscole appropriate </p> </td> 
   <td colname="col2"> <p>Esempio: 
     <code>
       Search Template Reference 
     </code> </p> <p>Capitalizzare i sostantivi propri. Se utilizzi una parola in minuscolo, il motore di ricerca corrisponde a qualsiasi caso della parola. </p> <p>Ad esempio, se digiti 
     <code>
       search 
     </code>, il motore di ricerca restituisce tutti i documenti che contengono le parole "search", "Search" e "SEARCH". Tuttavia, se digiti 
     <code>
       Search 
     </code>, il motore di ricerca restituisce documenti che contengono solo la parola maiuscola. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usa virgolette </p> </td> 
   <td colname="col2"> <p>Esempio: 
     <code>
       "our pledge to you" 
     </code> </p> <p>Usa le virgolette per trovare parole che devono apparire adiacenti, ad esempio "il nostro impegno verso di te". Senza le citazioni circostanti, i risultati della ricerca includono le parole "nostro", "pegno", "a", e "tu", ma non necessariamente in quell'ordine. Le parole possono invece essere visualizzate in qualsiasi punto e in qualsiasi ordine all’interno del documento. </p> <p> se si utilizza il modulo di ricerca avanzata con i pulsanti di scelta per <span class="uicontrol"> qualsiasi </span>, <span class="uicontrol"> tutto </span> e <span class="uicontrol"> frase </span>, è possibile utilizzare le virgolette solo quando è selezionato <span class="uicontrol"> qualsiasi </span>. Le virgolette vengono ignorate se è selezionata l'opzione <span class="uicontrol"> all </span> o <span class="uicontrol"> phrase </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usa + (più) o - (meno) </p> </td> 
   <td colname="col2"> <p>Esempio: 
     <code>
       +"template language" 
     </code> </p> <p>Utilizza + per indicare che nei risultati della ricerca deve essere visualizzato un termine o una frase di ricerca. </p> <p>Utilizza - per indicare che un termine o una frase di ricerca deve essere assente dai risultati di ricerca. </p> <p>È necessario contenere una frase racchiusa tra virgolette. Non lasciare spazi tra il segno più o meno e il termine di ricerca, come nell’esempio precedente. </p> <p> se si utilizza il modulo di ricerca avanzata con i pulsanti di scelta per <span class="uicontrol"> qualsiasi </span>, <span class="uicontrol"> tutto </span> e <span class="uicontrol"> frase </span>, è possibile utilizzare le virgolette solo quando è selezionato <span class="uicontrol"> qualsiasi </span>. I modificatori più e meno vengono ignorati se è selezionata l’opzione <span class="uicontrol"> all </span> o <span class="uicontrol"> phrase </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usa ricerche nei campi </p> </td> 
   <td colname="col2"> <p>Esempi: </p> <p> 
     <ul id="ul_F7CFF7652894402E8D19D6BA49792530"> 
      <li id="li_27492EF933C5437CB2C499746EC8CF39"> 
       <code>
         title:about 
       </code> </li> 
      <li id="li_BD21505122104FD0B16A4DAD777811DA"> 
       <code>
         desc:"Our Team" 
       </code> </li> 
      <li id="li_8264630F8B3D46BF872EFEB1D69DB6BE"> 
       <code>
         keys:login 
       </code> </li> 
      <li id="li_EBB81CBFC6DA45E99A524890DCD56E9F"> 
       <code>
         body:security 
       </code> </li> 
      <li id="li_6A852E35D6984A2C94144AB6C6D2DFA0"> 
       <code>
         alt:"join now" 
       </code> </li> 
      <li id="li_F4C5699360484D12ACD62BBFB84A7904"> 
       <code>
         url:help 
       </code> </li> 
      <li id="li_B2DBBA2239E74D98868D92B3EDEF5B51"> 
       <code>
         target:Adobe 
       </code> </li> 
     </ul> </p> <p>Le ricerche nei campi consentono di creare ricerche specifiche per le parole che vengono visualizzate in una parte specifica di un documento. </p> <p>È possibile eseguire una ricerca di campo nel corpo del testo (corpo:), nel testo del titolo (titolo:), nel testo alt (alt:), nella descrizione della meta (desc:), nelle parole chiave meta (chiavi:), nell’URL (url:) o nelle parole chiave della meta target (target:). Utilizzare lettere minuscole per il nome del campo e immediatamente seguite da due punti. Non ci sono spazi tra i due punti e il termine di ricerca. </p> <p>Le ricerche dei campi sono seguite solo da una parola o una frase. Le frasi devono essere racchiuse tra virgolette. </p> <p>se si utilizza il modulo di ricerca avanzata con una casella di riepilogo per il nome del campo, è possibile immettere nomi di campo solo prima di una parola o una frase se si seleziona <span class="uicontrol"> qualsiasi </span>. Se nella casella di riepilogo sono selezionati altri campi Modulo di ricerca avanzata, i nomi dei campi specifici vengono ignorati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usa caratteri jolly </p> </td> 
   <td colname="col2"> <p>Esempi: </p> <p> 
     <ul id="ul_D8E3867EB15641B0A6E55AD546CCB4DD"> 
      <li id="li_CB8B8FC15EB14B13BB33BB69F5206303"> 
       <code>
         wh* 
       </code> </li> 
      <li id="li_5350A934648C4C81BD6C0875061B426B"> 
       <code>
         "wh* are" 
       </code> </li> 
      <li id="li_7965A2F7186F40039D2F0736299D11B1"> 
       <code>
         415-*-* 
       </code> </li> 
     </ul> </p> <p>Le ricerche con caratteri jolly consentono di espandere il numero di corrispondenze per una particolare richiesta. Il carattere * viene utilizzato come carattere jolly. </p> <p>Ad esempio, la ricerca 
     <code>
       wh* 
     </code> trova le parole "cosa", "perché", "quando", "se" e qualsiasi altra parola che inizia con "wh". Cercando *lei* trova le parole "qui", "se", "insieme", "raduno" e qualsiasi altra parola che contiene "lei" ovunque all'interno della parola. </p> <p>È possibile combinare i caratteri jolly con i modificatori + e -, le virgolette per le frasi e gli specificatori di ricerca dei campi. </p> <p>La ricerca 
     <code>
       +wh* -se*ch 
     </code> trova tutte le pagine con una parola che inizia con "wh" e non contiene una parola che inizia con "se" e termina con "ch". </p> <p>La ricerca 
     <code>
       "wh* are" 
     </code> trova le frasi "dove sono", "cosa sono", "perché sono" e così via. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aggiunta di una nuova definizione di ricerca {#task_98D3A168AB5D4F30A1ADB6E0D48AB648}

Puoi usare il pannello [!DNL GS Add Search] per configurare e aggiungere una nuova definizione di ricerca per i componenti di Ricerca guidata, come facet, breadcrumb, navigazione delle pagine, menu e ricerche recenti, nel livello di presentazione.

<!-- 

t_adding_a_new_definition.xml

 -->

Dopo aver aggiunto la nuova definizione di ricerca, accertati di fare riferimento a essa nel modello di presentazione in modo che venga visualizzata.

Consulta [Informazioni sui modelli](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**Per aggiungere una nuova definizione di ricerca**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**.
1. Nella pagina [!DNL Searches], fai clic su **[!UICONTROL Add New Search]**.
1. Nella pagina **[!UICONTROL GS Add Search]** , imposta le opzioni desiderate.

   <!-- 
   
   r_gs_search_options.xml
   
   -->

   Tieni presente che le regole di elaborazione che selezionano il modello di presentazione possono sostituire alcune di queste opzioni.

   Consulta [Aggiunta di una nuova definizione di ricerca](../c-about-settings-menu/c-about-searching-menu.md#task_98D3A168AB5D4F30A1ADB6E0D48AB648) o [Modifica di una definizione di ricerca](../c-about-settings-menu/c-about-searching-menu.md#task_AF1FFB1AEF874C13AB359C28F74BF461).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome ricerca </p> </td> 
      <td colname="col2"> <p>Identifica il nome della ricerca definita. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Origine </p> </td> 
      <td colname="col2"> <p>Consente di selezionare la ricerca back-end da utilizzare. Puoi scegliere tra <span class="wintitle"> SiteSearch </span> o <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Account </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se si è scelto <span class="uicontrol"> Search&amp;Promote </span> come origine. </p> <p>Consente di selezionare l’account di ricerca/merchandising del sito in cui si desidera eseguire la ricerca. In genere, una ricerca cerca nell’account in uso. Tuttavia, il modello di presentazione può utilizzare una ricerca back-end per qualsiasi altro account. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome server/IP </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se come origine hai scelto <span class="uicontrol"> Merchandising </span> . </p> <p>Specifica il nome completo del server <span class="wintitle"> Merchandising </span> a cui deve accedere la ricerca <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Porta server </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se come origine hai scelto <span class="uicontrol"> Merchandising </span> . </p> <p>Specifica il numero di porta del server <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Piramide </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se come origine hai scelto <span class="uicontrol"> Merchandising </span> . </p> <p>Specifica la piramide all'interno del server <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero di risultati </p> </td> 
      <td colname="col2"> <p>Specifica il numero di risultati di ricerca che si desidera restituire. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero di risultati della prima pagina (se diversi) </p> </td> 
      <td colname="col2"> <p>Specifica il numero di risultati restituiti nella prima pagina. Utilizza questa opzione se devi impostarla in modo diverso rispetto alle altre pagine. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero di colonne </p> </td> 
      <td colname="col2"> <p>Specifica il numero di colonne su cui sono suddivisi i risultati della ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo Di Ricerca </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se si è scelto <span class="uicontrol"> Search&amp;Promote </span> come origine. </p> <p>Consente di selezionare i tre tipi di ricerca seguenti. </p> <p> 
        <ul id="ul_2F6FA9EFD8DB49EEAB866C3D070E2644"> 
          <li id="li_ECFEBEDD86FF4DE2BB768423B3B91B5E"> <span class="uicontrol"> tutto </span> <p>Cerca i documenti che contengono tutte le parole della stringa query. </p> <p>L’uso di "+" e "-" prima che le parole di ricerca siano disabilitate e che tali caratteri vengano ignorati. </p> </li> 
          <li id="li_62EB215BDDE74DF0BF76B3BD5B96776F"> <span class="uicontrol"> qualsiasi </span> <p>È consentito l’uso di prefissi di parole "+" e "-". </p> </li> 
          <li id="li_3D71982C0BBA41AFA353069AF3F2F6D8"> <span class="uicontrol"> frase  </span> <p>La stringa di query viene trattata come una frase tra virgolette e tutte le virgolette digitate dall'utente vengono ignorate. </p> <p>L’uso di "+" e "-" prima che le parole di ricerca siano disabilitate e che tali caratteri vengano ignorati. </p> </li> 
        </ul> </p> <p> Se desideri che ogni parola in una query selezioni potenzialmente un valore facet, la ricerca primaria deve sempre utilizzare <span class="uicontrol"> tutto </span>. </p> <p>Puoi esaminare i suggerimenti per la ricerca relativi all’utilizzo dei modificatori + e - in una query di ricerca. </p> <p>Consulta <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> Informazioni sulle ricerche </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Raccolta </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se si è scelto <span class="uicontrol"> Search&amp;Promote </span> come origine. </p> <p>Identifica la raccolta all'interno dell'indice in cui si desidera eseguire la ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Promuovi ricerca </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se si è scelto <span class="uicontrol"> Search&amp;Promote </span> come origine. </p> <p>Consente di utilizzare una selezione casuale dai risultati della ricerca, in base al <span class="uicontrol"> Numero di risultati </span> specificato. </p> <p>La ricerca promozionale è un concetto legacy. Di conseguenza, ti consigliamo di utilizzare il nuovo sistema di gestione banner all’interno di ricerca/merchandising del sito. </p> <p>Consulta <a href="../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA" type="concept" format="dita" scope="local"> Informazioni sui banner </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Applicare parametri di facet </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai scelto <span class="uicontrol"> Search&amp;Promote </span> come origine e hai selezionato <span class="uicontrol"> Promuovi ricerca </span>. </p> <p>Specifica che una ricerca promozionale utilizza i facet selezionati per limitare le promozioni. La maggior parte degli account di ricerca promozionali non utilizza questa opzione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fornire una promozione predefinita se non esiste una promozione corrispondente </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai scelto <span class="uicontrol"> Search&amp;Promote </span> come origine e hai selezionato <span class="uicontrol"> Promuovi ricerca </span>. </p> <p>Specifica che si verifica un'altra ricerca di una promozione se la ricerca iniziale di una promozione non trova nulla. La seconda ricerca di una promozione elimina la parola chiave . Cerca invece qualsiasi promozione in cui un campo di metadati "is_default" è impostato su "yes". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ricerca in evidenza </p> </td> 
      <td colname="col2"> <p>Elimina un numero selezionato di risultati dalla ricerca principale che desideri evidenziare in una "zona-eroe". </p> <p>In genere, le ricerche con evidenziazione hanno un criterio di ricerca simile a quello principale, ma con un meccanismo di classificazione diverso per evidenziare determinati risultati. Il software rimuove i duplicati dalla ricerca principale. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ricerca di base </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Evidenzia ricerca </span>. </p> <p>Consente di selezionare la ricerca con i risultati da cui si evidenziano i risultati. I duplicati vengono rimossi da questa ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Priorità DeDupe </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Evidenzia ricerca </span>. </p> <p>Consente di eseguire più ricerche con evidenziazione. </p> <p>Quando disponi di più ricerche con evidenziazione devi specificare la priorità della deduplicazione, dove "1" è la priorità più alta. </p> <p>Ad esempio, supponiamo di avere due ricerche con evidenziazione: bestseller e nuovi prodotti. Teoricamente. è possibile che un best-seller sia anche un nuovo prodotto. In questo caso, vuoi rimuovere il duplicato dai nuovi prodotti e dalla ricerca principale. Pertanto, imposta la priorità dei bestseller su 1 e la priorità dei nuovi prodotti su 2. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro </p> </td> 
      <td colname="col2"> <p>Consente di aggiungere parametri CGI alla ricerca. </p> <p>Consulta <a scope="local" href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita"> Parametri CGI di ricerca back-end </a>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Nella pagina [!DNL Searches] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica della definizione di ricerca {#task_AF1FFB1AEF874C13AB359C28F74BF461}

Puoi usare il pannello [!DNL Staged GS Edit Search] per riconfigurare una definizione di ricerca esistente per il livello di presentazione Ricerca guidata.

<!-- 

t_editing_a_search_definition.xml

 -->

Dopo aver modificato la definizione di ricerca, accertati di averle fatto riferimento nel modello di presentazione in modo che venga visualizzato.

Consulta [Informazioni sui modelli](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**Per modificare una definizione di ricerca**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**.
1. Nella tabella, nella pagina [!DNL Searches] fare clic su **[!UICONTROL Edit]** nella riga della definizione che si desidera modificare.
1. Nella pagina **[!UICONTROL GS Edit Search]** , imposta le opzioni desiderate.

   <!-- 
   
   r_gs_search_options.xml
   
   -->

   Tieni presente che le regole di elaborazione che selezionano il modello di presentazione possono sostituire alcune di queste opzioni.

   Consulta [Aggiunta di una nuova definizione di ricerca](../c-about-settings-menu/c-about-searching-menu.md#task_98D3A168AB5D4F30A1ADB6E0D48AB648) o [Modifica di una definizione di ricerca](../c-about-settings-menu/c-about-searching-menu.md#task_AF1FFB1AEF874C13AB359C28F74BF461).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome ricerca </p> </td> 
      <td colname="col2"> <p>Identifica il nome della ricerca definita. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Origine </p> </td> 
      <td colname="col2"> <p>Consente di selezionare la ricerca back-end da utilizzare. Puoi scegliere tra <span class="wintitle"> SiteSearch </span> o <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Account </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se si è scelto <span class="uicontrol"> Search&amp;Promote </span> come origine. </p> <p>Consente di selezionare l’account di ricerca/merchandising del sito in cui si desidera eseguire la ricerca. In genere, una ricerca cerca nell’account in uso. Tuttavia, il modello di presentazione può utilizzare una ricerca back-end per qualsiasi altro account. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome server/IP </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se come origine hai scelto <span class="uicontrol"> Merchandising </span> . </p> <p>Specifica il nome completo del server <span class="wintitle"> Merchandising </span> a cui deve accedere la ricerca <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Porta server </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se come origine hai scelto <span class="uicontrol"> Merchandising </span> . </p> <p>Specifica il numero di porta del server <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Piramide </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se come origine hai scelto <span class="uicontrol"> Merchandising </span> . </p> <p>Specifica la piramide all'interno del server <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero di risultati </p> </td> 
      <td colname="col2"> <p>Specifica il numero di risultati di ricerca che si desidera restituire. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero di risultati della prima pagina (se diversi) </p> </td> 
      <td colname="col2"> <p>Specifica il numero di risultati restituiti nella prima pagina. Utilizza questa opzione se devi impostarla in modo diverso rispetto alle altre pagine. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero di colonne </p> </td> 
      <td colname="col2"> <p>Specifica il numero di colonne su cui sono suddivisi i risultati della ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo Di Ricerca </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se si è scelto <span class="uicontrol"> Search&amp;Promote </span> come origine. </p> <p>Consente di selezionare i tre tipi di ricerca seguenti. </p> <p> 
        <ul id="ul_E1D8B3DE9DB24DE4813D53F6298A03A6"> 
          <li id="li_C3DD7AA7699B477A9EE0731CFC012630"> <span class="uicontrol"> tutto </span> <p>Cerca i documenti che contengono tutte le parole della stringa query. </p> <p>L’uso di "+" e "-" prima che le parole di ricerca siano disabilitate e che tali caratteri vengano ignorati. </p> </li> 
          <li id="li_4C66B9EFEFA042908A4D3730F9F54EB0"> <span class="uicontrol"> qualsiasi </span> <p>È consentito l’uso di prefissi di parole "+" e "-". </p> </li> 
          <li id="li_37E9AD42A61C4E31A0816DFB8E71118D"> <span class="uicontrol"> frase  </span> <p>La stringa di query viene trattata come una frase tra virgolette e tutte le virgolette digitate dall'utente vengono ignorate. </p> <p>L’uso di "+" e "-" prima che le parole di ricerca siano disabilitate e che tali caratteri vengano ignorati. </p> </li> 
        </ul> </p> <p> Se desideri che ogni parola in una query selezioni potenzialmente un valore facet, la ricerca primaria deve sempre utilizzare <span class="uicontrol"> tutto </span>. </p> <p>Puoi esaminare i suggerimenti per la ricerca relativi all’utilizzo dei modificatori + e - in una query di ricerca. </p> <p>Consulta <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> Informazioni sulle ricerche </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Raccolta </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se si è scelto <span class="uicontrol"> Search&amp;Promote </span> come origine. </p> <p>Identifica la raccolta all'interno dell'indice in cui si desidera eseguire la ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Promuovi ricerca </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se si è scelto <span class="uicontrol"> Search&amp;Promote </span> come origine. </p> <p>Consente di utilizzare una selezione casuale dai risultati della ricerca, in base al <span class="uicontrol"> Numero di risultati </span> specificato. </p> <p>La ricerca promozionale è un concetto legacy. Di conseguenza, ti consigliamo di utilizzare il nuovo sistema di gestione banner all’interno di ricerca/merchandising del sito. </p> <p>Consulta <a href="../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA" type="concept" format="dita" scope="local"> Informazioni sui banner </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Applicare parametri di facet </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai scelto <span class="uicontrol"> Search&amp;Promote </span> come origine e hai selezionato <span class="uicontrol"> Promuovi ricerca </span>. </p> <p>Specifica che una ricerca promozionale utilizza i facet selezionati per limitare le promozioni. La maggior parte degli account di ricerca promozionali non utilizza questa opzione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fornire una promozione predefinita se non esiste una promozione corrispondente </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai scelto <span class="uicontrol"> Search&amp;Promote </span> come origine e hai selezionato <span class="uicontrol"> Promuovi ricerca </span>. </p> <p>Specifica che si verifica un'altra ricerca di una promozione se la ricerca iniziale di una promozione non trova nulla. La seconda ricerca di una promozione elimina la parola chiave . Cerca invece qualsiasi promozione in cui un campo di metadati "is_default" è impostato su "yes". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ricerca in evidenza </p> </td> 
      <td colname="col2"> <p>Elimina un numero selezionato di risultati dalla ricerca principale che desideri evidenziare in una "zona-eroe". </p> <p>In genere, le ricerche con evidenziazione hanno un criterio di ricerca simile a quello principale, ma con un meccanismo di classificazione diverso per evidenziare determinati risultati. Il software rimuove i duplicati dalla ricerca principale. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ricerca di base </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Evidenzia ricerca </span>. </p> <p>Consente di selezionare la ricerca con i risultati da cui si evidenziano i risultati. I duplicati vengono rimossi da questa ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Priorità DeDupe </p> </td> 
      <td colname="col2"> <p>Questa opzione è disponibile solo se hai selezionato <span class="uicontrol"> Evidenzia ricerca </span>. </p> <p>Consente di eseguire più ricerche con evidenziazione. </p> <p>Quando disponi di più ricerche con evidenziazione devi specificare la priorità della deduplicazione, dove "1" è la priorità più alta. </p> <p>Ad esempio, supponiamo di avere due ricerche con evidenziazione: bestseller e nuovi prodotti. Teoricamente. è possibile che un best-seller sia anche un nuovo prodotto. In questo caso, vuoi rimuovere il duplicato dai nuovi prodotti e dalla ricerca principale. Pertanto, imposta la priorità dei bestseller su 1 e la priorità dei nuovi prodotti su 2. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametro </p> </td> 
      <td colname="col2"> <p>Consente di aggiungere parametri CGI alla ricerca. </p> <p>Consulta <a scope="local" href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita"> Parametri CGI di ricerca back-end </a>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella pagina [!DNL Searches] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una definizione di ricerca {#task_1D8E991E4C4146B7A7311FAE5DAA3742}

È possibile eliminare una definizione di ricerca guida che non è più necessaria o utilizzata.

<!-- 

t_deleting_a_search_definition.xml

 -->

Consulta [Informazioni sui modelli](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**Per eliminare una definizione di ricerca**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**.
1. Nella tabella, nella pagina [!DNL Searches] fare clic su **[!UICONTROL Delete]** nella riga della definizione che si desidera rimuovere.
1. Nella finestra di dialogo [!DNL Confirmation] fare clic su **[!UICONTROL OK]**.
1. (Facoltativo) Nella pagina [!DNL Searches] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sul gestore di parole chiave dei risultati fissi {#concept_0C5F152C029C485D8872C6795CBCD7C7}

Puoi fissare manualmente i risultati della ricerca in una posizione specifica. Questi risultati bloccati sono associati a una query di ricerca specifica o a parole chiave. È possibile utilizzare [!DNL Pinned Result Keyword Manager] per gestire tutte le parole chiave con risultati fissi.

<!-- 

c_about_pinned_results_keyword_manager.xml

 -->

## Regole di ricerca per parole chiave da seguire {#section_ED67A24BE884468286F34FA5DFF826D7}

La query di ricerca immessa nel pannello ha le seguenti regole:

* Gli spazi iniziali e finali vengono eliminati dalla query.
* Non sono consentiti caratteri di ricerca speciali, ad esempio:

   * Carattere jolly corrispondente a asterischi (*).
   * Nessun must-have o must-not-have utilizza più o meno (+ o -).
   * Nessun identificatore di campo con i due punti (:).
   * Nessuna virgola o virgolette doppie (, o &quot;).

* Nella query sono consentiti più termini o parole separati da spazi.
* Le lettere maiuscole vengono convertite in lettere minuscole.

I termini di ricerca vengono ricordati esattamente così com&#39;è; per ottenere esattamente gli stessi risultati, è necessario utilizzare nuovamente gli stessi termini di ricerca.

I risultati inseriti non supportano la distinzione tra maiuscole e minuscole. Tutte le parole chiave hanno le loro lettere maiuscole convertite in lettere minuscole.

## Riordinamento dei risultati della ricerca {#section_46FBE5279C7740A09D6DC9F54FE104AA}

Quando esegui una ricerca su una parola chiave nel pannello [!DNL Stage Add New Keyword] o nel pannello [!DNL Staged Edit Keyword], i risultati della ricerca riflettono ciò che potrebbe accadere dopo la successiva operazione di indice. È possibile riordinare i risultati della ricerca nella tabella utilizzando uno dei tre metodi diversi.

Il primo metodo è quello di utilizzare la casella di controllo **[!UICONTROL Pinned]**. La casella di controllo viene utilizzata per fissare un risultato in una posizione specifica. Quando selezioni la casella di controllo, vengono bloccati anche tutti i risultati della ricerca sopra la casella di controllo. Questa funzionalità assicura che tutti i risultati sopra la casella di controllo vengano visualizzati in tale ordine specifico. Se si rimuove un risultato di ricerca, questo viene trascinato sotto tutti i risultati attualmente bloccati.

Il secondo metodo consiste nell’utilizzare il trascinamento nella tabella. È possibile spostare un risultato in una nuova posizione con trascinamento della selezione. Dopo aver trascinato un risultato in una nuova posizione, tutti i risultati sopra la nuova posizione vengono bloccati. Questo blocco automatico assicura che il resto dei risultati venga visualizzato sopra il risultato trascinato di recente.

Il terzo metodo consiste nell&#39;impostare l&#39;ordine dei risultati bloccati inserendo una posizione specifica nella colonna &quot;#&quot;. A differenza del trascinamento della selezione, l’ordine dei risultati della ricerca simulata è evidente solo alla successiva apertura del pannello [!DNL Staged Edit Keyword] . L’impostazione del numero d’ordine per una riga attualmente non bloccata garantisce che almeno molti elementi vengano bloccati. L&#39;impostazione del numero di ordine per una riga attualmente bloccata imposta l&#39;ordine dell&#39;elemento all&#39;interno degli elementi attualmente bloccati. Tuttavia, non aumenta il numero di elementi bloccati.

Quando salvi i risultati della ricerca, puoi visualizzare di nuovo i risultati immettendo la stessa query nel campo Parola chiave.

## Informazioni sui risultati di ricerca bloccati {#section_46780B7812F249F3B45503161C4FBDEE}

I risultati della ricerca sono spesso ordinati in base al punteggio di pertinenza. Tuttavia, un risultato di ricerca bloccato ignora il punteggio di pertinenza e tenta di ignorare l’ordine naturale con la sua posizione predeterminata. Assicurando che il risultato rimanga relativamente dove si trova, altri risultati di ricerca noti sopra devono essere fissati.

I risultati della ricerca visualizzati nel pannello simulano quello che appare dopo l&#39;indice successivo. Tuttavia, le modifiche apportate al documento originale o ad alcune modifiche di configurazione nel Centro membri possono produrre risultati con discrepanze. Ad esempio, la modifica del contenuto di un documento è nota solo dopo l’indice.

I risultati bloccati appaiono in un ordine simile o uguale dopo l&#39;indice, perché ignorano la rilevanza. I risultati non fissati ritornano alla loro posizione naturale dopo un indice; l&#39;ordine dei risultati non bloccati non è garantito.

## Aggiunta di una nuova parola chiave {#task_8CED128DADD34D0DAD2C64B64D0D6B06}

È possibile aggiungere nuove parole chiave e i relativi risultati bloccati.

<!-- 

t_adding_a_new_keyword.xml

 -->

Quando aggiungi una nuova parola chiave, puoi riordinare i risultati della ricerca e fissarli in una posizione specifica.

**Per aggiungere una nuova parola chiave**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]**.
1. Nella pagina [!DNL Pinned Keyword Results Manager], fai clic su **[!UICONTROL Add New Keyword]**.
1. Nella pagina [!DNL Add New Keyword], immettere una query di ricerca nel campo **[!UICONTROL Keyword]**, quindi fare clic su **[!UICONTROL Search Keyword]**.

   <!-- 
   
   r_keyword_options.xml
   
   -->

   È possibile utilizzare il pulsante Modifica tabella per regolare la modalità di visualizzazione della tabella dei risultati della ricerca. Ad esempio, puoi utilizzare l’elenco delle colonne per visualizzare o nascondere colonne specifiche. È inoltre possibile ridisporre l’ordine delle colonne mediante trascinamento della selezione.

   La tabella seguente descrive le proprietà della colonna presenti nell’editor tabella.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Colonna </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Ordine </p> </td> 
      <td colname="col2"> <p>Specifica l'ordine numerico dell'aspetto delle colonne. Puoi trascinare le colonne per aggiornare automaticamente l’ordine. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome campo </p> </td> 
      <td colname="col2"> <p>Identifica il nome dell'intestazione di colonna visualizzata nella tabella <span class="wintitle"> Risultati della ricerca simulata </span> del pannello <span class="wintitle"> Aggiungi nuova parola chiave in staging </span> e nel pannello <span class="wintitle"> Modifica parola chiave in staging </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi </p> </td> 
      <td colname="col2"> <p>Se la casella è selezionata, la colonna viene visualizzata nella tabella Risultati bloccati. Se la casella è vuota o deselezionata, la colonna scompare dalla tabella. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visualizza URL come immagine </p> </td> 
      <td colname="col2"> <p>Se il campo meta assegnato a questa colonna contiene URL a immagini o immagini, selezionando questa casella vengono posizionati tag immagine HTML intorno ad essa e viene visualizzata l'immagine. Le immagini mancanti o i collegamenti non validi sono vuoti. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lunghezza campo </p> </td> 
      <td colname="col2"> <p>Consente di immettere la lunghezza massima del testo da visualizzare prima che venga troncato con puntini di sospensione (..). Se la colonna è impostata per visualizzare gli URL come immagini, questo campo non ha alcun effetto. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Riordinare i risultati della ricerca.
   * Fare clic su **[!UICONTROL Edit Table]** per regolare la visualizzazione della tabella [!DNL Simulated Search Results]. Al termine, fai clic su **[!UICONTROL Save Changes]** per tornare al pannello [!DNL Add New Keyword] .

1. Clic **[!UICONTROL Save Search Results]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Pinned Results Keyword Manager] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di una parola chiave {#task_30C550A7350B4394B5B43536368A84B1}

È possibile modificare le parole chiave esistenti e i relativi risultati fissati.

<!-- 

t_editing_a_keyword.xml

 -->

Quando modifichi una parola chiave, puoi riordinare i risultati della ricerca e fissarli in una posizione specifica.

**Per modificare una parola chiave**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]**.
1. Nella tabella della pagina [!DNL Pinned Keyword Results Manager] fare clic su **[!UICONTROL Edit]** nella riga della parola chiave che si desidera modificare.
1. Nella pagina [!DNL Edit Keyword], immettere una query di ricerca nel campo **[!UICONTROL Keyword]**, quindi fare clic su **[!UICONTROL Search Keyword]**.

   Assicurati di seguire le regole per la ricerca di parole chiave.

   <!-- 
   
   r_keyword_options.xml
   
   -->

   È possibile utilizzare il pulsante Modifica tabella per regolare la modalità di visualizzazione della tabella dei risultati della ricerca. Ad esempio, puoi utilizzare l’elenco delle colonne per visualizzare o nascondere colonne specifiche. È inoltre possibile ridisporre l’ordine delle colonne mediante trascinamento della selezione.

   La tabella seguente descrive le proprietà della colonna presenti nell’editor tabella.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Colonna </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Ordine </p> </td> 
      <td colname="col2"> <p>Specifica l'ordine numerico dell'aspetto delle colonne. Puoi trascinare le colonne per aggiornare automaticamente l’ordine. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome campo </p> </td> 
      <td colname="col2"> <p>Identifica il nome dell'intestazione di colonna visualizzata nella tabella <span class="wintitle"> Risultati della ricerca simulata </span> del pannello <span class="wintitle"> Aggiungi nuova parola chiave in staging </span> e nel pannello <span class="wintitle"> Modifica parola chiave in staging </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi </p> </td> 
      <td colname="col2"> <p>Se la casella è selezionata, la colonna viene visualizzata nella tabella Risultati bloccati. Se la casella è vuota o deselezionata, la colonna scompare dalla tabella. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visualizza URL come immagine </p> </td> 
      <td colname="col2"> <p>Se il campo meta assegnato a questa colonna contiene URL a immagini o immagini, selezionando questa casella vengono posizionati tag immagine HTML intorno ad essa e viene visualizzata l'immagine. Le immagini mancanti o i collegamenti non validi sono vuoti. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lunghezza campo </p> </td> 
      <td colname="col2"> <p>Consente di immettere la lunghezza massima del testo da visualizzare prima che venga troncato con puntini di sospensione (..). Se la colonna è impostata per visualizzare gli URL come immagini, questo campo non ha alcun effetto. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Riordinare i risultati della ricerca.
   * Fare clic su **[!UICONTROL Edit Table]** per regolare la visualizzazione della tabella [!DNL Simulated Search Results].

      Consulta [Aggiunta di una nuova parola chiave](../c-about-settings-menu/c-about-searching-menu.md#task_8CED128DADD34D0DAD2C64B64D0D6B06).

      Al termine, fai clic su **[!UICONTROL Save Changes]** per tornare al pannello [!DNL Add New Keyword] .

1. Clic **[!UICONTROL Save Search Results]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Pinned Results Keyword Manager], effettuare una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una parola chiave {#task_F17D6357D6DD416495E6D4117899D81D}

È possibile eliminare le parole chiave non più necessarie o utilizzate.

<!-- 

t_deleting_a_keyword.xml

 -->

Quando aggiungi una nuova parola chiave, puoi riordinare i risultati della ricerca e fissarli in una posizione specifica.

**Per eliminare una parola chiave**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]**.
1. Nella tabella, nella pagina [!DNL Pinned Keyword Results Manager] fare clic su **[!UICONTROL Delete]** nella riga della parola chiave che si desidera rimuovere.
1. Nella pagina [!DNL Delete Keyword], fai clic su **[!UICONTROL Delete]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Pinned Results Keyword Manager], effettuare una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle raccolte {#concept_62E42ACE53D54EEE9273433B86259127}

Puoi utilizzare le raccolte per consentire ai clienti di cercare aree specifiche di un sito web in modo che possano trovare rapidamente ciò che stanno cercando.

<!-- 

c_about_collections.xml

 -->

Consulta [Informazioni sulle ricerche](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

Vedere [Uso delle raccolte nei moduli di ricerca](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Ad esempio, i clienti possono cercare una raccolta di URL relativi alle vendite dei prodotti o ai servizi di supporto. Prima che i clienti possano utilizzare le raccolte specificate, è necessario aggiornare il modulo di ricerca nel menu Modulo di ricerca.

Prima che gli effetti delle impostazioni Raccolte siano visibili ai clienti, ricostruisci l’indice del sito.

Puoi testare le raccolte immettendo uno degli URL del sito web nel campo facoltativo **[!UICONTROL Test Collections]** , quindi facendo clic su **[!UICONTROL Test]**. Viene restituito l&#39;insieme a cui appartiene la pagina specificata.

Ogni raccolta viene specificata su una singola riga con un nome e una maschera URL. Una maschera URL può essere costituita dai seguenti elementi:

* un percorso completo come `https://www.mydomain.com/products.html`
* un percorso parziale come `https://www.mydomain.com/products`
* espressione regolare

   Per rendere una maschera un&#39;espressione regolare, inserisci la parola chiave `regexp` tra il nome della raccolta e la maschera URL.

   Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Ogni riga del campo Raccolte può contenere una sola maschera URL. Tuttavia, puoi specificare più maschere URL per lo stesso nome della raccolta su righe diverse. L&#39;esempio seguente contiene quattro nomi di raccolta diversi e cinque maschere URL:

```
Company Info https://www.yoursite.com/company 
Products https://www.yoursite.com/products 
FAQs regexp ^.*/faqs 
Support https://www.yoursite.com/email_support/ 
Support https://www.yoursite.com/phone_support/
```

In questo esempio, dopo aver aggiornato il modulo di ricerca per includere queste raccolte, i clienti possono selezionare e cercare singolarmente ciascuna raccolta definita. L&#39;insieme `Support` include file che corrispondono alle maschere URL, in modo che i file sia `www.yoursite.com/email_support/` che `www.yoursite.com/phone_support` vengano ricercati quando questa raccolta viene selezionata.

## Aggiunta di raccolte {#task_07732D0F00104E59AD421297A704B2F6}

È possibile aggiungere raccolte per consentire ai clienti di cercare aree specifiche del sito web in modo che possano trovare rapidamente ciò che stanno cercando.

<!-- 

t_adding_collections.xml

 -->

Assicurati di ricostruire l&#39;indice del sito in modo che i risultati delle maschere URL siano visibili ai clienti.

Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Per aggiungere raccolte**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Collections]**.
1. Nel campo [!DNL Collections] , immetti un nome raccolta e un indirizzo di maschera URL, uno per riga.
1. (Facoltativo) Nella pagina [!DNL Collections], nel campo **[!UICONTROL Test Collections]** immetti una maschera URL di prova dal sito web, quindi fai clic su **[!UICONTROL Test]**.

   Viene visualizzata una finestra di output della raccolta di test che mostra l’URL e il nome della raccolta.
1. Al termine dell’aggiunta delle raccolte, fai clic su **[!UICONTROL Save Changes]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Collections] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle restrizioni {#concept_B5B527E04EBF4E9AB5956EEF881DDBF1}

Prima di eseguire una ricerca, l’URL di riferimento e l’indirizzo IP vengono esaminati per determinare se è possibile effettuare una ricerca da tale posizione. Ciò che hai specificato in [!DNL Restrictions] determina se la ricerca è consentita. Se una ricerca non è consentita, viene restituita al richiedente una pagina di errore generica.

<!-- 

c_about_restrictions.xml

 -->

Puoi specificare le impostazioni di restrizione come maschere URL di riferimento o come maschere di indirizzo IP. Entrambi i tipi di restrizioni utilizzati includono maschere per consentire le ricerche ed escludere maschere per negarle.

È consentita una ricerca se trasmette sia l’URL del referente che i criteri di restrizione dell’indirizzo IP. Se una delle due impostazioni non consente la ricerca, la ricerca non riesce, indipendentemente dalle altre restrizioni che la consentono.

Ad esempio, se il campo &quot;referente HTTP&quot; di una richiesta di ricerca corrisponde a una maschera URL di riferimento &quot;exclude&quot;, la ricerca non riesce, anche se l’indirizzo IP richiedente corrisponde a una maschera di indirizzo IP &quot;include&quot;. Se nessuna maschera corrisponde all’URL o all’indirizzo IP del referente, la posizione viene inclusa per impostazione predefinita.

Inserisci ogni maschera di inclusione o di esclusione su una singola riga.

## Aggiunta di restrizioni relative alla maschera URL di riferimento o alla maschera dell&#39;indirizzo IP {#task_E6FF2DD83E8D4B00A0E2809DC13A56C9}

Puoi specificare le impostazioni di restrizione come &quot;Maschere URL referente&quot; o &quot;Maschere indirizzi IP&quot;. Entrambi i tipi di restrizioni utilizzati includono maschere per consentire le ricerche ed escludere maschere per negarle. È consentita una ricerca se trasmette sia l’URL di riferimento che i criteri di restrizione dell’indirizzo IP.

<!-- 

t_adding_url_mask_or_jp_address_restrictions.xml

 -->

**Per aggiungere restrizioni relative alla maschera URL di riferimento o alla maschera degli indirizzi IP**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]**.
1. Nella pagina [!DNL Restrictions] , imposta le opzioni di restrizione desiderate. Inserisci gli indirizzi della maschera URL di riferimento, gli indirizzi IP o, facoltativamente, un indirizzo URL di una pagina web personalizzata che viene visualizzata ai clienti a cui non è consentito eseguire ricerche nel sito.

   <!-- 
   
   r_restriction_options.xml
   
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
      <td colname="col1"> <p>Maschere URL di riferimento </p> </td> 
      <td colname="col2"> <p>Viene letto l’URL del referente dall’intestazione del referente HTTP. La prima maschera che corrisponde all’URL del referente determina se consentire la ricerca, se la maschera è una maschera di inclusione. Oppure, determina se disabilitare la ricerca, se la maschera è una maschera di esclusione. Se nessuna maschera corrisponde all’URL del referente, tale URL viene incluso e la ricerca è consentita. </p> <p> Se il modello di ricerca contiene un nuovo modulo di ricerca o se il modello di ricerca può contenere collegamenti come "Next 10", "Previous 10" o "Hide Summaries", elencare il modello di risultati di ricerca come una maschera "include". Il modo più semplice per farlo è con l'espressione regolare, come nell'esempio seguente: </p> <p> <span class="codeph"> includere regexp ^https?://[^/]*\.atomz\.com/.*[?&amp;]sp_a=sp1000130e.*$ </span> </p> <p>L’esempio seguente contiene cinque diverse maschere URL di riferimento: </p> <p> <code> include&nbsp;https://www.mydomain.com/search/ 
          include&nbsp;https://search.mydomain.com/ 
          include&nbsp;regexp&nbsp;^https://www.mydomain.com/help/.*/search/ 
          include&nbsp;regexp&nbsp;^https?://[^/]*\.atomz\.com/.*[?&amp;]sp_a=sp1000130e.*$ 
          exclude&nbsp;* </code> </p> <p>Se le maschere dell'URL di riferimento sono le seguenti: </p> <p> <code> https://www.mydomain.com/search/searchpage.html&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          https://search.mydomain.com/advanced/&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          https://www.mydomain.com/help/products/search/advanced/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          https://www.mydomain.com/help/products/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          https://www.anotherdomain.com/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          blank&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maschere di indirizzi IP </p> </td> 
      <td colname="col2"> <p>La prima maschera che corrisponde all'indirizzo IP determina se consentire la ricerca, se la maschera è una maschera di inclusione. Oppure, determina se consentire o meno la ricerca se la maschera è una maschera di esclusione. Se nessuna maschera corrisponde all’indirizzo IP richiedente, l’indirizzo IP viene incluso e la ricerca è consentita. </p> <p>L’esempio seguente mostra quattro diverse maschere di indirizzo IP. </p> <p> <code> include&nbsp;64.128.192.* 
          include&nbsp;192.168. 
          include&nbsp;regexp&nbsp;^209\.42\.97\.[1-5]+ 
          exclude&nbsp;* </code> </p> <p>Se le maschere dell’indirizzo IP di riferimento sono le seguenti: </p> <p> <code> 64.128.192.10&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          192.168.10.127&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          209.42.97.14&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          64.128.193.10&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          192.169.10.14&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          209.42.97.68&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Consenti solo ricerche che utilizzano HTTPS </p> </td> 
      <td colname="col2"> <p>Limita le ricerche a HTTPS. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL a cui devono essere inviate le richieste non consentite </p> </td> 
      <td colname="col2"> <p> Gli utenti con restrizioni vengono reindirizzati all’URL immesso qui. Questa opzione consente di creare una pagina di errore personalizzata da visualizzare ai clienti ai quali non è consentito eseguire ricerche nel sito. </p> <p>Se non si specifica un URL, viene restituita una pagina di errore generica quando un utente con restrizioni tenta di eseguire ricerche nel sito. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sull&#39;anteprima {#concept_DF293FD3B02C467F8842C8C21D62F294}

La stringa di query e i parametri impostati in [!DNL Preview] vengono utilizzati ogni volta che un modulo di ricerca viene testato o visualizzato in anteprima nel software.

<!-- 

c_about_preview.xml

 -->

Vedere anche [Informazioni sulle ricerche](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

## Impostazione dei valori in Anteprima {#task_CE267A0FF621474E80AB43B67B1C28D7}

I valori di anteprima impostati vengono utilizzati ogni volta che un modulo di ricerca viene testato o visualizzato in anteprima nel software.

<!-- 

t_setting_values_in_preview.xml

 -->

**Per impostare i valori in Anteprima**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Preview]**.
1. Nella pagina [!DNL Preview] , imposta le opzioni desiderate.

   <!-- 
   
   r_preview_options.xml
   
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
      <td colname="col1"> <p>Query </p> </td> 
      <td colname="col2"> <p>Per impostazione predefinita, la stringa di query è impostata su <span class="codeph"> * </span>, che in genere restituisce risultati. Tuttavia, puoi specificare una query più specifica per il contenuto del sito web. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametri </p> </td> 
      <td colname="col2"> <p>I parametri sono impostati con un nome e un valore. Puoi specificare tutti i parametri aggiuntivi necessari. Ad esempio, puoi specificare criteri di ricerca aggiuntivi con i parametri <span class="codeph"> sp_q_1 </span> e <span class="codeph"> sp_x_1 </span> . Il valore del parametro <span class="codeph"> sp_q_1=windows&amp;sp_x_1=platform </span> crea una ricerca di anteprima che cerca il valore "windows" nel tag meta "platform" delle pagine cercate, oltre alla query principale. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Parametri CGI di ricerca back-end </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Host </p> </td> 
      <td colname="col2"> <p>Se il sito web utilizza l’etichettatura del dominio privato, imposta il nome host corretto per visualizzare in anteprima con precisione i risultati della ricerca. </p> <p>Per informazioni sull’etichettatura del dominio privato, contatta l’Assistenza clienti. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sui feed {#concept_FEBFEE51A3AB49F88CBA0D16E2AD6916}

L&#39;indice di ricerca viene visualizzato come un grande database del sito web. Con informazioni sufficienti dai tag meta corretti, le informazioni vengono raccolte e organizzate, o sindacati, in feed di dati. Puoi inviare questi feed di dati a un altro servizio, ad esempio a un destinatario di terze parti.

<!-- 

c_about_feeds.xml

 -->

Una volta che il tuo sito web è sottoposto a ricerca per indicizzazione e indicizzazione, puoi generare feed automatici e inviarli a motori di ricerca e motori di acquisto biologici di terze parti. Puoi creare i seguenti feed di flusso:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tipo di feed </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Recommendations </p> </td> 
   <td colname="col2"> <p>Recommendations I feed forniscono funzionalità di sindacazione dei dati con Adobe Recommendations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed generico </p> </td> 
   <td colname="col2"> <p>Puoi implementare molti feed con il tipo di feed generico. Viene eseguita una query di ricerca personalizzata sull'indice del sito web. I dati vengono restituiti tramite modelli di ricerca personalizzati che utilizzano lo stesso linguaggio del modello per visualizzare i risultati della ricerca. Questo tipo di flessibilità consente di inviare feed a molti più fornitori, non solo a tipi di feed specifici. </p> <p>Puoi aggiungere il modello di trasporto (ricerca) utilizzando le istruzioni contenute nel seguente argomento della Guida: </p> <p>Vedere <a href="../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012" type="task" format="dita" scope="local"> Aggiunta di un nuovo file di presentazione o di modello di trasporto </a>. </p> <p> Dopo aver aggiunto il modello, modificalo utilizzando i tag del modello di ricerca per definire quali campi di metadati di ricerca includere, insieme al relativo formato. </p> <p>Vedere <a href="../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3" type="task" format="dita" scope="local"> Modifica di una presentazione o di un modello di trasporto </a>. </p> <p>Consulta <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Ricerca tag modello </a>. </p> <p>Ricorda il nome del file modello di trasporto. Puoi utilizzare il nome per eseguire il binding del feed generico al modello quando specifichi i criteri del feed. </p> <p>Se in precedenza hai lavorato con altri feed, ricorda di mappare i campi dei feed ai campi dei metadati di ricerca. I feed generici non dispongono di questo passaggio specifico nella procedura guidata <span class="uicontrol"> Crea feed </span> . Il modello specifica invece i metadati e la formattazione dei metadati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Merchant </p> </td> 
   <td colname="col2"> <p>Google Merchant Center permette alle persone di vendere prodotti attraverso diversi servizi di Google. Dispone di un componente di sindacazione dei dati in cui è possibile inviare periodicamente un elenco di prodotti disponibili in vendita. </p> <p>Come per qualsiasi fornitore di feed di terze parti, Google Merchant Center ha standard specifici che si soddisfano prima che ritengano il feed legittimo. Per ulteriori informazioni, contatta il tuo rappresentante clienti e visita la documentazione di Google Merchant. Di seguito è riportato un rapido riepilogo di ciò che Google Merchant Center considera durante la convalida di un feed: </p> 
    <ul id="ul_3D84D4A6A4BF4C08860F86403F8F9CD6"> 
     <li id="li_5B6516CC7BC7493B8B8E8AFB454E573F">Ogni prodotto ha una pagina di prodotto; un URL dedicato. </li> 
     <li id="li_5A6D5AD5E1B54A94B224D19E888B5443"> Ogni variante di prodotto ha una voce separata nel feed. </li> 
     <li id="li_89748D3241B34A4493576DAC38681988"> Ogni prodotto ha un URL immagine, preferibilmente proveniente dal server. Le varianti di prodotto hanno immagini specifiche che mostrano le varianti effettive. In altre parole, i diversi colori delle scarpe non devono condividere la stessa immagine. </li> 
     <li id="li_A594AD19480F41EAA72181355F28447B"> Ogni prodotto dispone di informazioni specifiche quali disponibilità, condizione, descrizione, categoria e prezzo. </li> 
     <li id="li_0955B3A6ED2746D2B7CB42DC8AB27D3A">In generale, ogni prodotto ha un identificatore univoco come ISBN, UPC, JAN o EAN e così via. </li> 
     <li id="li_2C371653F1C5471FA638F3A3818ABC17">In generale, ogni prodotto è classificato con la tassonomia del prodotto di Google. </li> 
     <li id="li_6EB392A5A0BE490FAED5BC5E83228E32"> I prodotti di abbigliamento presentano campi obbligatori aggiuntivi, quali genere, fascia di età, colore e dimensione. </li> 
     <li id="li_44B91FA9A95F4172A2F03F8206E9081E"> Le imposte e la spedizione sono specificate come impostazione dell'account all'interno di Google Merchant Center o sulla base del prodotto per prodotto, all'interno di questo feed. </li> 
     <li id="li_71A63E9905B840C0A04F6CDAA23C9AB0"> I prodotti fatti su misura e alcuni prodotti di abbigliamento possono essere esentati da alcune delle norme, ma è necessario contattare Google per l'autorizzazione e i dettagli su tali esenzioni. </li> 
    </ul> <p>La convalida dei feed è disciplinata da numerosi dettagli. Per informazioni sulla gestione dei feed, consulta la documentazione di Google Merchant . Google apporta spesso modifiche alle specifiche, quindi controlla spesso la documentazione. </p> <p>Il feed associato a Google Merchant Center è spesso denominato feed di Google Product Search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Sitemaps </p> </td> 
   <td colname="col2"> <p>Google Sitemaps offre un modo per influenzare il modo in cui Google esegue la ricerca per indicizzazione del tuo sito web. Un feed di dati sindacati, una mappa del sito in questo caso, viene periodicamente inviato a Google Sitemaps. La mappa del sito contiene URL raggiungibili da Internet e a ogni URL possono essere associate informazioni specifiche, come la data dell’ultima modifica o la priorità della pagina. Fornire a Google tali informazioni può aumentare la frequenza e le possibilità che una pagina specifica venga sottoposta a ricerca per indicizzazione. In alcuni casi, una mappa del sito viene utilizzata per pubblicizzare un elenco di collegamenti a cui il crawler non può accedere in circostanze normali. </p> <p>Se siete interessati a creare una mappa del sito Google con la nostra funzione di feed, contattate il vostro rappresentante commerciale. Google ha reso il loro servizio Google Sitemap disponibile al pubblico e fornisce la documentazione nella loro pagina Google Webmaster Tools. </p> <p> <b>Requisiti per la creazione di un feed di Google Sitemap</b> </p> <p>Per creare un feed di Google Sitemap, assicurati di avere già configurato un account Google Webmaster Tools con Google Sitemap. Consulta la documentazione Google Webmaster Tools per la configurazione di Google Sitemap. </p> <p>È inoltre necessario determinare come vengono consegnati i file della mappa del sito. In generale, i file di mappa del sito provengono dal dominio e, in particolare, dalla directory principale del sito web. Il modello semplice consiste nell’avere i file consegnati tramite FTP ai server. L’altra soluzione consiste nel reindirizzare la richiesta dei file di mappa del sito alla rete di contenuti per la ricerca/merchandising del sito. Contatta il tuo rappresentante di consulenza per coordinare e configurare la distribuzione dei feed della mappa del sito. </p> </td> 
  </tr> 
 </tbody> 
</table>

Se siete interessati ai feed automatici, contattate i servizi professionali per assistenza. Ogni feed ha requisiti rigorosi in materia di qualità dei dati e di trasmissione dei file.

Il tipo di feed selezionato influisce sulle opzioni visualizzate quando si crea un campo utilizzando la procedura guidata **[!UICONTROL Create Feed]**. Ogni tipo di feed ha formati di dati diversi. Assicurati di seguire il formato corretto dei dati per evitare il rifiuto di un feed da parte di un destinatario del feed o la pubblicazione di dati impropri ai clienti. Oltre al formato dei dati, i fornitori di solito hanno uno o più modi preferiti per ricevere i dati. Consulta la documentazione del fornitore sui propri feed.

Una sfida nella creazione di un feed è la corrispondenza dei dati tra ricerca/merchandising del sito e il feed. Solitamente i dati recuperati dalla ricerca per indicizzazione sono nel formato errato o mancanti. Di seguito è riportato un elenco di domande che possono aiutarti a concentrarti su cosa cercare quando crei un feed.

* Che tipo di relazione di business hai con il destinatario del feed?
* È necessario registrare e creare un account con il destinatario del feed?
* Chi controllerà e si prenderà cura dei problemi che emergono con il feed rispetto al fornitore? In generale, è tua responsabilità gestire l&#39;account del fornitore. Ad esempio, Google Sitemap richiede un account WebMaster e un utente per monitorare lo stato di salute della mappa del sito.
* Qual è il formato dati del feed?
* L’indice corrisponde alla codifica dei caratteri del feed? I formati di dati delimitati da tabulazioni e virgole diventano un problema quando i dati sono dotati di tabulazioni o virgole.
* Cosa devi fare quando hai tabulazioni o virgole nei tuoi dati?
* Ci sono pagine nel tuo indice con dati vuoti?
* Il destinatario del feed può accettare dati vuoti? È possibile risolvere i dati vuoti modificando il modo in cui i dati vengono recuperati dal software.
* Il formato dei dati si allinea a ciò che vuole il destinatario del feed? Ad esempio, alcuni destinatari di feed sono specifici in merito alla modalità di visualizzazione dei prezzi e della valuta.
* Il fornitore dispone di un numero massimo di articoli che può accettare? Puoi risolvere questo potenziale problema limitando i risultati con i criteri di ricerca.
* In che modo il fornitore desidera ricevere il feed? Sono supportati gli invii FTP e l’hosting HTTP.

## Creazione di un feed {#task_63179C1FC359497483CD6CE13FD1C250}

Puoi creare uno o più feed di dati.

<!-- 

t_creating_a_feed.xml

 -->

**Creazione di un feed**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. Nella pagina [!DNL Feeds] , seleziona un tipo di feed dall’elenco a discesa **[!UICONTROL Create Feed]** .
1. A seconda del tipo di feed selezionato, nella finestra di dialogo [!DNL Create Feed] impostare le opzioni come identificate in ciascun pannello della procedura guidata.

   <!-- 
   
   r_feed_options.xml
   
   -->

   A seconda del tipo di feed che si sta creando o modificando, le opzioni disponibili sono leggermente diverse.

   **Adobe Recommendations**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Pannello </p> </th> 
      <th colname="col2" class="entry"> <p>Nome pannello procedura guidata </p> </th> 
      <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>1 </p> </td> 
      <td colname="col2"> <p>Nome feed </p> </td> 
      <td colname="col3"> <p>Specifica il nome del feed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>Mappe campo </p> </td> 
      <td colname="col3"> <p>Consente di mappare campi di feed specifici del fornitore ai campi di metadati di ricerca/merchandising del sito. Questo passaggio di mappatura nella procedura guidata è importante perché consente ai feed di correlare le informazioni tra i campi nell’indice e i campi nei dati del feed. Nella maggior parte dei casi, ad eccezione dei <span class="wintitle"> Feed generici </span>, le correlazioni vengono salvate in un modello di ricerca generato dinamicamente. </p> <p>Ogni riga della tabella <span class="wintitle"> Mappe campo </span> rappresenta una mappatura campo. Nella colonna Aggiungi/Rimuovi della tabella, fare clic su <span class="uicontrol"> + </span> per aggiungere una nuova riga di mappatura dei campi; fare clic su <span class="uicontrol"> - </span> per eliminare dalla tabella la riga di mappatura del campo attualmente selezionata. Per associare un campo di feed a un campo di metadati di ricerca/merchandising del sito, utilizza i rispettivi elenchi a discesa per scegliere i campi desiderati. </p> <p> <b>Mappature dei campi per Adobe Recommendations</b> </p> <p>Il feed di dati Consigli è un file CSV, colonne di dati separati da virgole. L’ordine di aspetto di ciascuna mappatura nella tabella Mappe campo è importante in quanto determinano l’ordine delle colonne nel file di feed CSV. Crea le righe di mappature nel seguente ordine: ogni riga è obbligatoria: </p> <p> 
        <ol id="ol_49C739D04DD340168DC6C1F794544C35"> 
          <li id="li_A95D9C5A353746A3A0D38F200AC2EEA2"> id </li> 
          <li id="li_044763D4C7054CEB948C94590735D74F"> name </li> 
          <li id="li_832F07CA0E3F4E10A4AE30171F3E8541"> categoryId </li> 
          <li id="li_2A33FB42F7E942ED881BA1F478542C4D"> message </li> 
          <li id="li_A76E66B2366845B0B63ED5C200531ADD"> thumbnailURL </li> 
          <li id="li_518CCD5E7E404521AB8199981BA86F76"> value </li> 
          <li id="li_14A0A8FCC2B34B758E1FBB98E3F2DFB2"> pageURL </li> 
          <li id="li_36D22F1603394AF89E0C7ADB18AAAAB7"> inventory </li> 
          <li id="li_ABDB9C762BBC4F27B82FEA4425A8DDC4"> margin </li> 
        </ol> </p> <p> <b>Utilizzo avanzato</b> </p> <p>Dopo aver mappato i primi nove campi Feed richiesti come descritto sopra, puoi creare campi personalizzati. Nell’elenco a discesa <span class="wintitle"> Campi feed </span> , fai clic su <span class="uicontrol"> Personalizzato </span>. Nel campo di testo associato, immetti un nome di tag personalizzato per quel campo. Questa opzione personalizzata è utile se un feed necessita di campi specifici per il fornitore. </p> <p> <p>Nota:  Sebbene le specifiche di feed della raccomandazione stabiliscano che ogni nome di campo deve essere preceduto da "entity", in questo caso non è necessario. </p> </p> <p>Puoi anche creare un campo di metadati personalizzato. Nell’elenco a discesa <span class="wintitle"> Campi metadati </span> , fai clic su <span class="uicontrol"> Personalizzato </span>. Nel campo di testo associato, immetti un valore del campo di metadati personalizzato. Il valore viene inserito nel modello pregenerato e può essere utilizzato anche per inserire tag modello di ricerca personalizzati. </p> <p>Consulta <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Ricerca tag modello </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Criteri di ricerca </p> </td> 
      <td colname="col3"> <p>Quando i file di feed vengono generati, viene utilizzata una query di ricerca per filtrare i dati. In questo pannello vengono definiti i filtri utilizzati per la query di ricerca. </p> 
        <ul id="ul_799ECF61C03A44878C7182F8B88CC3AD"> 
        <li id="li_0763F600A4FB4650ACC28BF337EB50AF"> <span class="uicontrol"> Campo metadati  </span> <p>Definisce il campo di metadati su cui si desidera filtrare. </p> <p> <b>Utilizzo avanzato</b> </p> <p>Poiché il sistema di filtro è una query di ricerca standard, puoi selezionare <span class="uicontrol"> Modulo libero </span> dall’elenco a discesa per immettere i parametri di ricerca CGI e i relativi valori. L’escape URL è obbligatorio. L'argomento di ricerca <span class="codeph"> sp_q </span> viene ignorato. È possibile creare più righe di caselle di testo a forma libera. Tra ogni riga, gli argomenti sono delimitati automaticamente con &amp;. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Ricerca parametri CGI </a>. </p> </li> 
        <li id="li_756B776902AE4A0E95524442D663343E"> <span class="uicontrol"> Criteri </span> <p>Definisce l'operazione filtro. L’operazione filtro selezionata dall’elenco a discesa applica il valore costante immesso nella terza colonna. </p> </li> 
        <li id="li_7ADEDB8747B241D78AC50F1AC75AE695"> <span class="uicontrol"> Valore </span> <p>Valore costante. </p> </li> 
        <li id="li_4039A9BC2F74460B83BFF662B58DAA1B"> <span class="uicontrol"> Azione </span> <p>Aggiunge una nuova riga di mappatura campo o elimina la riga attualmente evidenziata. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>Invio file </p> </td> 
      <td colname="col3"> <p>Consente di configurare la pianificazione per l’invio dei file di feed e di impostare il metodo da utilizzare per caricare i file. </p> 
        <ul id="ul_55E253F83BDA46BAABF2BE38F0918E80"> 
        <li id="li_877A376B5B30422FAC816E31D50EA508"> <span class="uicontrol"> Pianificazione </span> <p>Imposta la frequenza massima di invio di un feed. Selezionando <span class="uicontrol"> Mai </span> si disattiva il feed. Altri valori definiscono il periodo di attesa del feed prima di inviarlo nuovamente. La decisione su quando inviare il feed viene presa in corrispondenza di ciascun indice. In altre parole, alla fine dell’indice, un feed viene controllato per verificare se è scaduto e deve essere aggiornato e inviato dal fornitore. Inoltre, viene utilizzato come metodo per impedire l'invio eccessivo di un account a un fornitore. Alcuni fornitori hanno dei criteri rispetto alle origini dei feed di dati che vengono caricate troppo spesso. Verifica di controllare la politica del fornitore del feed di dati sulla frequenza degli invii. 
          <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> 
          <!--ick <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_760F5068D3ED46C582AE41392A2CA342"> <span class="uicontrol"> Metodo di caricamento  </span> <p>La maggior parte dei feed offre due modi per distribuire i file: FTP e la rete di contenuti in hosting. </p> 
          <ul id="ul_666759EDDD034537AA7C0ED936A2F315"> 
          <li id="li_B4AD5CEEBB7B41C0B8DC291B95DC5F83"> <span class="uicontrol"> FTP </span> <p>I server di ricerca/merchandising del sito utilizzano un FTP passivo. </p> <p>FTP è l'unico modo per inviare un file a un altro server. </p> <p> <span class="uicontrol"> Server FTP  </span> - Specifica il nome del server FTP. Non includere il protocollo o che precede "ftp://". </p> <p> <span class="uicontrol"> Nome utente FTP  </span> - Specifica il nome dell'account FTP. </p> <p> <span class="uicontrol"> Password FTP  </span> - Specifica la password dell'account FTP. </p> <p> <span class="uicontrol"> Nome file FTP  </span> - Specifica il nome del file da trasmettere. Questo nome è un modello se il feed genera più file, in genere incrementando un numero alla fine del nome ma prima dell’estensione. Ad esempio: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> Directory FTP  </span> - Se è necessario un percorso di directory specifico, inseriscilo qui. Non includere il nome del file nel percorso. </p> </li> 
          <li id="li_C082D3993C6C469B9067F207703BE619"> <span class="uicontrol"> Rete di contenuti in hosting  </span> <p>La rete dei contenuti è il mezzo per servire i file dai server web di ricerca/merchandising dei siti. Il destinatario del feed lo richiama dai server web utilizzando una richiesta HTTP. L'unica informazione da configurare è <span class="uicontrol"> Content Network Filename </span>. Il nome del file è il nome di base del file distribuito. Utilizza solo nomi di file con estensione del nome file. A seconda del feed, il nome del file è un modello per più file in cui il feed potrebbe generare più file nel seguente formato: basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml. </p> <p>Dopo aver inserito il nome del file di base e salvato correttamente il feed, l’URL del file di rete del contenuto viene visualizzato nel pannello Verifica della procedura guidata. L’URL diventa attivo dopo che il feed è stato elaborato correttamente. Il fornitore può ottenere i dati del feed da questo URL. Più file utilizzano lo stesso percorso URL. Tuttavia, assicurati di sostituire o modificare il nome del file in base allo schema di enumerazione. </p> </li> 
          </ul> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>5 </p> </td> 
      <td colname="col2"> <p>Verifica </p> </td> 
      <td colname="col3"> <p>Quando si accede al pannello <span class="wintitle"> Verifica </span>, il feed viene salvato in quel punto. Tuttavia, i file di feed effettivi non vengono salvati fino a un momento successivo. </p> <p>Il pannello <span class="wintitle"> Verifica </span> consente di effettuare le seguenti operazioni: </p> 
        <ul id="ul_0C6EFB38E06F401696084863D85CBD0D"> 
        <li id="li_07FC9F04C7F640048546F9DC5D91DA1D"> <span class="uicontrol"> Visualizzazione dati  </span> <p>Consente di fare clic sul collegamento per controllare l’output del feed attraverso una visualizzazione dati visualizzata sotto forma di tabella. La visualizzazione dati può anche aiutarti a risolvere i problemi mostrando quali metadati sono selezionati e come eventuali criteri di ricerca specificati nel pannello <span class="wintitle"> Criteri di ricerca </span> della procedura guidata influiscono sull’output del feed. La visualizzazione dati viene generata in modo dinamico, quindi è sempre disponibile. </p> </li> 
        <li id="li_67046A56D08C48298E5A3E1F9C4A8AF3"> <span class="uicontrol"> File di feed  </span> <p>Dopo che i server di ricerca/merchandising generano i file di feed, puoi utilizzare l’elenco a discesa <span class="uicontrol"> File di feed </span> per visualizzare i file dai server. Viene visualizzata una nuova scheda del browser o una nuova finestra del browser con il contenuto del feed. Questo metodo è utile per risolvere eventuali problemi di formattazione dei feed. Tieni presente che non visualizzi i file dalla destinazione finale o dai fornitori stessi. </p> <p> Se il feed è nuovo, l’elenco a discesa è vuoto fino a quando non si generano file di feed. </p> </li> 
        <li id="li_99D66C7AD87A475CB3D831D514DB78A0"> <span class="uicontrol"> Collegamento alla rete dei contenuti  </span> <p>Se hai scelto <span class="uicontrol"> Hosted Content Network </span> come metodo di caricamento nel pannello <span class="wintitle"> File Submission </span> della procedura guidata, l’URL viene visualizzato qui. Se non hai ancora generato alcun file di feed, l’URL non è valido finché il feed non viene generato correttamente. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

   **Feed generico**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Pannello </p> </th> 
      <th colname="col2" class="entry"> <p>Nome pannello procedura guidata </p> </th> 
      <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Nome feed </p> </td> 
      <td colname="col3"> <p>Specifica il nome del feed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>Criteri di ricerca </p> </td> 
      <td colname="col3"> <p>Quando i file di feed vengono generati, viene utilizzata una query di ricerca per filtrare i dati. In questo pannello vengono definiti i filtri utilizzati per la query di ricerca. </p> 
        <ul id="ul_C750687E69A647D0A4440FF1B6CC7E05"> 
        <li id="li_B5C3B8523D71472E9508A04E23AC0211"> <span class="uicontrol"> Campo metadati  </span> <p>Definisce il campo di metadati su cui si desidera filtrare. </p> <p> <b>Utilizzo avanzato</b> </p> <p>Poiché il sistema di filtro è una query di ricerca standard, puoi selezionare <span class="uicontrol"> Modulo libero </span> dall’elenco a discesa per immettere i parametri di ricerca CGI e i relativi valori. L’escape URL è obbligatorio. L'argomento di ricerca <span class="codeph"> sp_q </span> viene ignorato. È possibile creare più righe di caselle di testo a forma libera. Tra ogni riga, gli argomenti sono delimitati automaticamente con &amp;. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Ricerca parametri CGI </a>. </p> </li> 
        <li id="li_D1E49834BBEA42CC8C49AE7D72037C53"> <span class="uicontrol"> Criteri </span> <p>Definisce l'operazione filtro. L’operazione filtro selezionata dall’elenco a discesa applica il valore costante immesso nella terza colonna. </p> </li> 
        <li id="li_D5F0651B834F4EACAD15A2D154A0737B"> <span class="uicontrol"> Valore </span> <p>Valore costante. </p> </li> 
        <li id="li_FC8F382BD20C4518BC2230D4B4954591"> <span class="uicontrol"> Azione </span> <p>Aggiunge una nuova riga di mappatura campo o elimina la riga attualmente evidenziata. </p> </li> 
        </ul> <p>I feed generici richiedono un parametro CGI speciale specificato. Per eseguire il binding del modello speciale associato a questo feed, è necessario definire il parametro <span class="codeph"> sp_t </span> . Imposta il valore di <span class="codeph"> sp_t </span> sul nome del file del modello di trasporto. Ad esempio, se hai aggiunto un file modello di trasporto denominato <span class="codeph"> super_feed.tpl </span>, crea un parametro di ricerca CGI personalizzato come <span class="codeph"> sp_t=super_feed </span>. La casella di testo per l'immissione di <span class="codeph"> sp_t </span> non viene visualizzata finché non si seleziona <span class="uicontrol"> Modulo libero </span> dall'elenco a discesa <span class="wintitle"> Campo metadati </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Invio file </p> </td> 
      <td colname="col3"> <p>Consente di configurare la pianificazione per l’invio dei file di feed e di impostare il metodo da utilizzare per caricare i file. </p> 
        <ul id="ul_30E830C41F6A4526822AF1FD3083075A"> 
        <li id="li_79EAFDBD2B9F411EA985CAEC1BAF3926"> <span class="uicontrol"> Pianificazione </span> <p>Imposta la frequenza massima di invio di un feed. Selezionando <span class="uicontrol"> Mai </span> si disattiva il feed. Altri valori definiscono il periodo di attesa del feed prima di inviarlo nuovamente. La decisione su quando inviare il feed viene presa in corrispondenza di ciascun indice. In altre parole, alla fine dell’indice, un feed viene controllato per verificare se è scaduto e deve essere aggiornato e inviato dal fornitore. Inoltre, viene utilizzato come metodo per impedire l'invio eccessivo di un account a un fornitore. Alcuni fornitori hanno dei criteri rispetto alle origini dei feed di dati che vengono caricate troppo spesso. Verifica di controllare la politica del fornitore dei feed sulla frequenza degli invii. 
          <!--he time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> 
          <!--<uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_20BF70A19E7E45BA91CD972E2FCE0EA4"> <span class="uicontrol"> Metodo di caricamento  </span> <p>La maggior parte dei feed offre due modi per distribuire i file: FTP e la rete di contenuti in hosting. </p> 
          <ul id="ul_5888C2E9097645CE89938EE09F8CB4F1"> 
          <li id="li_EA9ED19F3BEA4BEAB1A9F2C2FAFF85F7"> <span class="uicontrol"> FTP  </span> <p>I server di ricerca/merchandising del sito utilizzano un FTP passivo. </p> <p>FTP è l'unico modo per inviare un file a un altro server. </p> <p> <span class="uicontrol"> Server FTP  </span> - Specifica il nome del server FTP. Non includere il protocollo o che precede "ftp://". </p> <p> <span class="uicontrol"> Nome utente FTP  </span> - Specifica il nome dell'account FTP. </p> <p> <span class="uicontrol"> Password FTP  </span> - Specifica la password dell'account FTP. </p> <p> <span class="uicontrol"> Nome file FTP  </span> - Specifica il nome del file da trasmettere. Questo nome è un modello se il feed genera più file, in genere incrementando un numero alla fine del nome ma prima dell’estensione. Ad esempio: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> Directory FTP  </span> - Se è necessario un percorso di directory specifico, inseriscilo qui. Non includere il nome del file nel percorso. </p> </li> 
          <li id="li_181268A7EE40456CA1DB768E8C66EEB9"> <span class="uicontrol"> Rete di contenuti in hosting  </span> <p>La rete di contenuti in hosting è il mezzo per distribuire file dai server web di ricerca/merchandising dei siti. Il destinatario del feed lo richiama dai server web utilizzando una richiesta HTTP. L'unica informazione da configurare è <span class="uicontrol"> Content Network Filename </span>. Il nome del file è il nome di base del file distribuito. Utilizza solo nomi di file con estensione del nome file. 
            <!--Depending on the feed, the file name is a template for multiple files where the feed might generate multiple files in the following format: basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml. --> </p> <p>Dopo aver inserito il nome del file di base e salvato correttamente il feed, l’URL del file di rete del contenuto viene visualizzato nel pannello Verifica della procedura guidata. L’URL diventa attivo dopo che il feed è stato elaborato correttamente. Il fornitore può ottenere i dati del feed da questo URL. </p> </li> 
          </ul> </li> 
        <li id="li_4DF56FA607A7479296CDA042A63C5A2C"> <p> <b>Mantieni schede?</b> </p> <p>Gestisci caratteri di tabulazione nel feed. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>Verifica </p> </td> 
      <td colname="col3"> <p>Quando si accede al pannello <span class="wintitle"> Verifica </span>, il feed viene salvato in quel punto. Tuttavia, i file di feed effettivi non vengono salvati fino a un momento successivo. </p> <p>Il pannello <span class="wintitle"> Verifica </span> consente di effettuare le seguenti operazioni: </p> 
        <ul id="ul_7420C415987448A796DD979CF5FA2EB6"> 
        <li id="li_AF02E8609B7B4F20A01AF4E010308E15"> <span class="uicontrol"> Visualizzazione dati  </span> <p>Consente di fare clic sul collegamento per controllare l’output del feed attraverso una visualizzazione dati visualizzata sotto forma di tabella. La visualizzazione dati può anche aiutarti a risolvere i problemi mostrando quali metadati sono selezionati e come eventuali criteri di ricerca specificati nel pannello <span class="wintitle"> Criteri di ricerca </span> della procedura guidata influiscono sull’output del feed. La visualizzazione dati viene generata in modo dinamico, quindi è sempre disponibile. </p> </li> 
        <li id="li_32CEB8885C184354BFA1773BA66DB7A7"> <span class="uicontrol"> File di feed  </span> <p>Dopo che i server di ricerca/merchandising generano i file di feed, puoi utilizzare l’elenco a discesa <span class="uicontrol"> File di feed </span> per visualizzare i file dai server. Viene visualizzata una nuova scheda del browser o una nuova finestra del browser con il contenuto del feed. Questo metodo è utile per risolvere eventuali problemi di formattazione dei feed. Tieni presente che non visualizzi i file dalla destinazione finale o dai fornitori stessi. </p> <p> Se il feed è nuovo, l’elenco a discesa è vuoto fino a quando non si generano file di feed. </p> </li> 
        <li id="li_8D1B876B0EC2455C8654EC573EC53FA9"> <span class="uicontrol"> Collegamento alla rete dei contenuti  </span> <p>Se hai scelto <span class="uicontrol"> Hosted Content Network </span> come metodo di caricamento nel pannello <span class="wintitle"> File Submission </span> della procedura guidata, l’URL viene visualizzato qui. Se non hai ancora generato alcun file di feed, l’URL non è valido finché il feed non viene generato correttamente. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

   **Centro commerciale Google**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Pannello </p> </th> 
      <th colname="col2" class="entry"> <p>Nome pannello procedura guidata </p> </th> 
      <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Nome feed </p> </td> 
      <td colname="col3"> <p>Specifica il nome del feed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>Mappe campo </p> </td> 
      <td colname="col3"> <p>Consente di mappare campi di feed specifici del fornitore ai campi di metadati di ricerca/merchandising del sito. Questo passaggio di mappatura nella procedura guidata è importante perché consente ai feed di correlare le informazioni tra i campi nell’indice e i campi nei dati del feed. Nella maggior parte dei casi, ad eccezione dei <span class="wintitle"> Feed generici </span>, le correlazioni vengono salvate in un modello di ricerca generato dinamicamente. </p> <p>Ogni riga della tabella Mappe campo rappresenta una mappatura campo. Nella colonna <span class="wintitle"> Aggiungi/Rimuovi </span> della tabella, fare clic su <span class="uicontrol"> + </span> per aggiungere una nuova riga di mappatura dei campi; fai clic su <span class="uicontrol"> - </span> per eliminare dalla tabella la riga di mappatura dei campi attualmente selezionata. Per associare un campo di feed a un campo di metadati di ricerca/merchandising del sito, utilizza i rispettivi elenchi a discesa per scegliere i campi desiderati. </p> <p> <b>Utilizzo avanzato</b> </p> <p>Puoi creare campi personalizzati. Nell’elenco a discesa <span class="wintitle"> Campi feed </span> , fai clic su <span class="uicontrol"> Personalizzato </span>. Nel campo di testo associato, immetti un nome di tag personalizzato per quel campo. Questa opzione personalizzata è utile se un feed necessita di campi specifici per il fornitore. </p> <p>Puoi anche creare un campo di metadati personalizzato. Nell’elenco a discesa <span class="wintitle"> Campi metadati </span> , fai clic su <span class="uicontrol"> Personalizzato </span>. Nel campo di testo associato, immetti un valore del campo di metadati personalizzato. Il valore viene inserito nel modello pregenerato e può essere utilizzato anche per inserire tag modello di ricerca personalizzati. </p> <p>Consulta <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Ricerca tag modello </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Criteri di ricerca </p> </td> 
      <td colname="col3"> <p>Quando i file di feed vengono generati, viene utilizzata una query di ricerca per filtrare i dati. In questo pannello vengono definiti i filtri utilizzati per la query di ricerca. </p> 
        <ul id="ul_8179321A58BB4C72B0CDB2B2BEC58FE4"> 
        <li id="li_9F8008A2398A4667B106BC49C94E5E3E"> <span class="uicontrol"> Campo metadati  </span> <p>Definisce il campo di metadati su cui si desidera filtrare. </p> <p> <b>Utilizzo avanzato</b> </p> <p>Poiché il sistema di filtro è una query di ricerca standard, puoi selezionare <span class="uicontrol"> Modulo libero </span> dall’elenco a discesa per immettere i parametri di ricerca CGI e i relativi valori. L’escape URL è obbligatorio. L'argomento di ricerca <span class="codeph"> sp_q </span> viene ignorato. È possibile creare più righe di caselle di testo a forma libera. Tra ogni riga, gli argomenti sono delimitati automaticamente con &amp;. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Ricerca parametri CGI </a>. </p> </li> 
        <li id="li_50C9CE59E9E5418895F8C1A070560063"> <span class="uicontrol"> Criteri </span> <p>Definisce l'operazione filtro. L’operazione filtro selezionata dall’elenco a discesa applica il valore costante immesso nella terza colonna. </p> </li> 
        <li id="li_9F86D0F5010046A4A9F93DBA5FB158B3"> <span class="uicontrol"> Valore </span> <p>Valore costante. </p> </li> 
        <li id="li_1051AFD5AEA447D0AF5FAB305E1D1E64"> <span class="uicontrol"> Azione </span> <p>Aggiunge una nuova riga di mappatura campo o elimina la riga attualmente evidenziata. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>Invio file </p> </td> 
      <td colname="col3"> <p>Consente di configurare la pianificazione per l’invio dei file di feed e di impostare il metodo da utilizzare per caricare i file. </p> 
        <ul id="ul_A6A3C333AADD4438B835BF3E16E2AEFF"> 
        <li id="li_FCC4DAF198E149278B5CFB870CB6218C"> <span class="uicontrol"> Pianificazione </span> <p>Imposta la frequenza massima di invio di un feed. Selezionando <span class="uicontrol"> Mai </span> si disattiva il feed. Altri valori definiscono il periodo di attesa del feed prima di inviarlo nuovamente. La decisione su quando inviare il feed viene presa in corrispondenza di ciascun indice. In altre parole, alla fine dell’indice, un feed viene controllato per verificare se è scaduto e deve essere aggiornato e inviato dal fornitore. Inoltre, viene utilizzato come metodo per impedire l'invio eccessivo di un account a un fornitore. Alcuni fornitori hanno dei criteri rispetto alle origini dei feed di dati che vengono caricate troppo spesso. Verifica di controllare la politica del fornitore dei feed sulla frequenza degli invii. </p> <p> 
          <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> </p> <p> 
          <!--Click <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_2D9ECAFB8E8544D39B486F7BC3DCE589"> <span class="uicontrol"> Metodo di caricamento  </span> <p>La maggior parte dei feed offre due modi per distribuire i file: FTP e la rete di contenuti in hosting. </p> <p>Il metodo di caricamento consigliato per l’invio del feed di dati è <span class="uicontrol"> FTP </span>. Google Merchant Center ospita un server FTP a questo scopo. Consulta la Guida di Google Merchant Center sulla configurazione di un account Google FTP separato per questo feed Google Product Search. </p> 
          <ul id="ul_BC0D8B541068407883CAC948496DBD0A"> 
          <li id="li_DB28CA23C94A4AF09E1A0EB06DF8F40C"> <span class="uicontrol"> FTP  </span> <p>I server di ricerca/merchandising del sito utilizzano un FTP passivo. </p> <p>FTP è l'unico modo per inviare un file a un altro server. </p> <p> <span class="uicontrol"> Server FTP  </span> - Specifica il nome del server FTP. In questo caso è 
            <code>
              uploads.google.com 
            </code>. Non includere il protocollo o che precede "ftp://". </p> <p> <span class="uicontrol"> Nome utente FTP  </span> - Specifica il nome dell'account FTP. </p> <p> <span class="uicontrol"> Password FTP  </span> - Specifica la password dell'account FTP. </p> <p> <span class="uicontrol"> Nome file FTP  </span> - Specifica il nome del file da trasmettere. Questo nome è un modello se il feed genera più file, in genere incrementando un numero alla fine del nome ma prima dell’estensione. Ad esempio: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> Directory FTP  </span> - Se è necessario un percorso di directory specifico, inseriscilo qui. Non includere il nome del file nel percorso. </p> </li> 
          <li id="li_5990927146434DAF89273F4636D21437"> <span class="uicontrol"> Rete di contenuti in hosting  </span> <p>La rete dei contenuti è il mezzo per servire i file dai server web di ricerca/merchandising dei siti. Il destinatario del feed lo richiama dai server web utilizzando una richiesta HTTP. </p> <p> 
            <!--After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. Multiple files use the same URL path. However, be sure that you replace or change the filename according to the enumeration scheme. --> </p> </li> 
          </ul> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>5 </p> </td> 
      <td colname="col2"> <p>Verifica </p> </td> 
      <td colname="col3"> <p>Quando si accede al pannello <span class="wintitle"> Verifica </span>, il feed viene salvato in quel punto. Tuttavia, i file di feed effettivi non vengono salvati fino a un momento successivo. </p> <p>Il pannello <span class="wintitle"> Verifica </span> consente di effettuare le seguenti operazioni: </p> 
        <ul id="ul_4A94355A8DF840A3BAF6BD5E9F11C27F"> 
        <li id="li_825697CB36B34C4AB5959B15EDDB55F1"> <span class="uicontrol"> Visualizzazione dati  </span> <p>Consente di fare clic sul collegamento per controllare l’output del feed attraverso una visualizzazione dati visualizzata sotto forma di tabella. La visualizzazione dati può anche aiutarti a risolvere i problemi mostrando quali metadati sono selezionati e come eventuali criteri di ricerca specificati nel pannello <span class="wintitle"> Criteri di ricerca </span> della procedura guidata influiscono sull’output del feed. La visualizzazione dati viene generata in modo dinamico, quindi è sempre disponibile. </p> </li> 
        <li id="li_91B8B5F5F9DE4A13863CD62F74AA6206"> <span class="uicontrol"> File di feed  </span> <p>Dopo che i server di ricerca/merchandising generano i file di feed, puoi utilizzare l’elenco a discesa <span class="uicontrol"> File di feed </span> per visualizzare i file dai server. Viene visualizzata una nuova scheda del browser o una nuova finestra del browser con il contenuto del feed. Questo metodo è utile per risolvere eventuali problemi di formattazione dei feed. Tieni presente che non visualizzi i file dalla destinazione finale o dai fornitori stessi. </p> <p> Se il feed è nuovo, l’elenco a discesa è vuoto fino a quando non si generano file di feed. </p> </li> 
        <li id="li_4A5EC089628E43029A38F8919888FF0A"> <span class="uicontrol"> Collegamento alla rete dei contenuti  </span> <p>Se hai scelto <span class="uicontrol"> Hosted Content Network </span> come metodo di caricamento nel pannello <span class="wintitle"> File Submission </span> della procedura guidata, l’URL viene visualizzato qui. Se non hai ancora generato alcun file di feed, l’URL non è valido finché il feed non viene generato correttamente. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

   **Google Sitemaps**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Pannello </p> </th> 
      <th colname="col2" class="entry"> <p>Nome pannello procedura guidata </p> </th> 
      <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Nome feed </p> </td> 
      <td colname="col3"> <p>Specifica il nome del feed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>Mappe campo </p> </td> 
      <td colname="col3"> <p>Consente di mappare campi di feed specifici del fornitore ai campi di metadati di ricerca/merchandising del sito. Questo passaggio di mappatura nella procedura guidata è importante perché consente ai feed di correlare le informazioni tra i campi nell’indice e i campi nei dati del feed. Nella maggior parte dei casi, ad eccezione dei <span class="wintitle"> Feed generici </span>, le correlazioni vengono salvate in un modello di ricerca generato dinamicamente. </p> <p>Ogni riga della tabella Mappe campo rappresenta una mappatura campo. Nella colonna Aggiungi/Rimuovi della tabella, fare clic su <span class="uicontrol"> + </span> per aggiungere una nuova riga di mappatura dei campi; fare clic su <span class="uicontrol"> - </span> per eliminare dalla tabella la riga di mappatura del campo attualmente selezionata. Per associare un campo Feed a un campo metadati, utilizza i rispettivi elenchi a discesa per scegliere i campi desiderati. </p> <p> <b>Utilizzo avanzato</b> </p> <p>Puoi creare campi personalizzati. Nell’elenco a discesa <span class="wintitle"> Campi feed </span> , fai clic su <span class="uicontrol"> Personalizzato </span>. Nel campo di testo associato, immetti un nome di tag personalizzato per quel campo. Questa opzione personalizzata è utile se un feed necessita di campi specifici per il fornitore. </p> <p>Puoi anche creare un campo di metadati personalizzato. Nell’elenco a discesa <span class="wintitle"> Campi metadati </span> , fai clic su <span class="uicontrol"> Personalizzato </span>. Nel campo di testo associato, immetti un valore del campo di metadati personalizzato. Il valore viene inserito nel modello pregenerato e può essere utilizzato anche per inserire tag modello di ricerca personalizzati. </p> <p>Consulta <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Ricerca tag modello </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Criteri di ricerca </p> </td> 
      <td colname="col3"> <p>Quando i file di feed vengono generati, viene utilizzata una query di ricerca per filtrare i dati. In questo pannello vengono definiti i filtri utilizzati per la query di ricerca. </p> 
        <ul id="ul_994585E89A044BD3A89A99D30F277432"> 
        <li id="li_61FA9246B9824E3C8124958C8EBFF0DA"> <span class="uicontrol"> Campo metadati  </span> <p>Definisce il campo di metadati su cui si desidera filtrare. </p> <p> <b>Utilizzo avanzato</b> </p> <p>Poiché il sistema di filtro è una query di ricerca standard, puoi selezionare <span class="uicontrol"> Modulo libero </span> dall’elenco a discesa per immettere i parametri di ricerca CGI e i relativi valori. L’escape URL è obbligatorio. L'argomento di ricerca <span class="codeph"> sp_q </span> viene ignorato. È possibile creare più righe di caselle di testo a forma libera. Tra ogni riga, gli argomenti sono delimitati automaticamente con &amp;. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Ricerca parametri CGI </a>. </p> </li> 
        <li id="li_A5D00883738845C8B8F612A7521F160F"> <span class="uicontrol"> Criteri </span> <p>Definisce l'operazione filtro. L’operazione filtro selezionata dall’elenco a discesa applica il valore costante immesso nella terza colonna. </p> </li> 
        <li id="li_5A312C2984454C2CB518CA453AD9F6D2"> <span class="uicontrol"> Valore </span> <p>Valore costante. </p> </li> 
        <li id="li_666AAE1BC7A2432E91953B08EC7394DC"> <span class="uicontrol"> Azione </span> <p>Aggiunge una nuova riga di mappatura campo o elimina la riga attualmente evidenziata. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>Invio file </p> </td> 
      <td colname="col3"> <p>Consente di configurare la pianificazione per l’invio dei file di feed e di impostare il metodo da utilizzare per caricare i file. </p> 
        <ul id="ul_49B3255BE669424B925BBAEE4C9B385F"> 
        <li id="li_939828C774D440EBB0769F6D5B0BBA23"> <span class="uicontrol"> Pianificazione </span> <p>Imposta la frequenza massima di invio di un feed. Selezionando <span class="uicontrol"> Mai </span> si disattiva il feed. Altri valori definiscono il periodo di attesa del feed prima di inviarlo nuovamente. La decisione su quando inviare il feed viene presa in corrispondenza di ciascun indice. In altre parole, alla fine dell’indice, un feed viene controllato per verificare se è scaduto e deve essere aggiornato e inviato dal fornitore. Inoltre, viene utilizzato come metodo per impedire l'invio eccessivo di un account a un fornitore. Alcuni fornitori hanno dei criteri rispetto alle origini dei feed di dati che vengono caricate troppo spesso. Verifica di controllare la politica del fornitore dei feed sulla frequenza degli invii. </p> <p> 
          <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> </p> <p> 
          <!--Click <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_07B5BCF7936241A7915C4898B231184B"> <span class="uicontrol"> Metodo di caricamento  </span> <p>La maggior parte dei feed offre due modi per distribuire i file: FTP e la rete di contenuti in hosting. </p> 
          <ul id="ul_74FA98A82754469BA5FADCC63FC364F7"> 
          <li id="li_02940B712D6444A8B65C0A51834187E6"> <span class="uicontrol"> FTP  </span> <p>I server di ricerca/merchandising del sito utilizzano un FTP passivo. </p> <p>FTP è l'unico modo per inviare un file a un altro server. </p> <p> <span class="uicontrol"> Server FTP  </span> - Specifica il nome del server FTP. Non includere il protocollo o che precede "ftp://". </p> <p> <span class="uicontrol"> Nome utente FTP  </span> - Specifica il nome dell'account FTP. </p> <p> <span class="uicontrol"> Password FTP  </span> - Specifica la password dell'account FTP. </p> <p> <span class="uicontrol"> Nome file FTP  </span> - Specifica il nome del file da trasmettere. Questo nome è un modello se il feed genera più file, in genere incrementando un numero alla fine del nome ma prima dell’estensione. Ad esempio: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> Directory FTP  </span> - Se è necessario un percorso di directory specifico, inseriscilo qui. Non includere il nome del file nel percorso. </p> </li> 
          <li id="li_EAE504436CD84452BA04BE51855A2BEF"> <span class="uicontrol"> Rete di contenuti in hosting  </span> <p>La rete dei contenuti è il modo per distribuire i file dai server web di ricerca/merchandising dei siti. Il destinatario del feed lo richiama dai server web utilizzando una richiesta HTTP. </p> <p> 
            <!--After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. Multiple files use the same URL path. However, be sure that you replace or change the filename according to the enumeration scheme. --> </p> </li> 
          </ul> </li> 
        </ul> <p>Nota che uno dei metodi di caricamento richiede di specificare l’URL utilizzato da Google per recuperare la mappa del sito, nel campo <span class="wintitle"> URL della mappa del sito principale </span> . Anche qui viene determinato il nome del file della mappa del sito. Se la mappa del sito è grande, potrebbero esistere più file e la convenzione di denominazione prevede di allegare un numero di indice alla fine del file, a partire dal numero 1. Il primo file o file di indice non ha indice, come in <span class="codeph"> sitemap.xml </span>, <span class="codeph"> sitemap1.xml </span>, <span class="codeph"> sitemap2.xml </span> ... <span class="codeph"> sitemap12.xml </span>. </p> <p>Se hai scelto <span class="uicontrol"> Hosted Content Network </span> come metodo di caricamento, l’URL dei file ha gli stessi nomi di file, ma l’URL ha il percorso e il nome host del servizio di hosting. Pertanto, reindirizzerai le richieste per la mappa del sito alla rete di contenuti ospitati. Dovresti anche essere in grado di estrarre i file dalla stessa posizione. </p> <p>Una volta creati e inviati i file di feed alla destinazione intermedia, Google viene eseguito il ping e informa che il feed della mappa del sito è pronto. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>5 </p> </td> 
      <td colname="col2"> <p>Verifica </p> </td> 
      <td colname="col3"> <p>Quando si accede al pannello <span class="wintitle"> Verifica </span>, il feed viene salvato in quel punto. Tuttavia, i file di feed effettivi non vengono salvati fino a un momento successivo. </p> <p>Il pannello <span class="wintitle"> Verifica </span> consente di effettuare le seguenti operazioni: </p> 
        <ul id="ul_A1D889A84972419599FC83F39EA2676A"> 
        <li id="li_C8ED077B6DD1461E85A4914C1CFDBE88"> <span class="uicontrol"> Visualizzazione dati  </span> <p>Consente di fare clic sul collegamento per controllare l’output del feed attraverso una visualizzazione dati visualizzata sotto forma di tabella. La visualizzazione dati può anche aiutarti a risolvere i problemi mostrando quali metadati sono selezionati e come eventuali criteri di ricerca specificati nel pannello <span class="wintitle"> Criteri di ricerca </span> della procedura guidata influiscono sull’output del feed. La visualizzazione dati viene generata in modo dinamico, quindi è sempre disponibile. </p> </li> 
        <li id="li_DACEE40703AF40EFBCD90D43825CE9C1"> <span class="uicontrol"> File di feed  </span> <p>Una volta generati i file di feed, puoi utilizzare l’elenco a discesa <span class="uicontrol"> File di feed </span> per visualizzare i file dai server. Viene visualizzata una nuova scheda del browser o una nuova finestra del browser con il contenuto del feed. Questo metodo è utile per risolvere eventuali problemi di formattazione dei feed. Tieni presente che non visualizzi i file dalla destinazione finale o dai fornitori stessi. </p> <p> Se il feed è nuovo, l’elenco a discesa è vuoto fino a quando non si generano file di feed. </p> </li> 
        <li id="li_1C530354B4F34EC79D92CEFEB5B39ED7"> <span class="uicontrol"> Collegamento alla rete dei contenuti  </span> <p>Se hai scelto <span class="uicontrol"> Hosted Content Network </span> come metodo di caricamento nel pannello <span class="wintitle"> File Submission </span> della procedura guidata, l’URL viene visualizzato qui. Se non hai ancora generato alcun file di feed, l’URL non è valido finché il feed non viene generato correttamente. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. Al termine dei passaggi della procedura guidata, fai clic su **[!UICONTROL Close]**.

## Modifica di un feed {#task_B855D28CD99B4FA58E2D4D4FD6DC9CEB}

Puoi modificare la configurazione di un feed esistente.

<!-- 

t_editing_a_feed.xml

 -->

>[!NOTE]
>
>Quando modificate un feed, non potete modificare il tipo di feed. Se devi modificare il tipo di feed, elimina il feed esistente e aggiungi un nuovo feed con il tipo desiderato.

Consulta [Eliminazione di un feed](../c-about-settings-menu/c-about-searching-menu.md#task_7E39A140E69D43C6B61FB42E81051269).

**Per modificare un feed**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. Esegui una delle operazioni seguenti:

* Nella pagina [!DNL Feeds], sotto la colonna [!DNL Name] della tabella, fai clic sull’elenco a discesa accanto al nome di un feed, quindi fai clic su **[!UICONTROL Edit feed]**.

* Nella pagina [!DNL Feeds], nella colonna [!DNL Name] fare clic sul nome di un feed che si desidera modificare.

1. Nella procedura guidata del feed, imposta le opzioni desiderate per ogni pannello della procedura guidata.

   Vedi le tabelle delle opzioni in **Aggiunta di un feed**.
1. Al termine della procedura guidata, nel pannello [!DNL Verification] fai clic su **[!UICONTROL Close]**.

## Eliminazione di un feed {#task_7E39A140E69D43C6B61FB42E81051269}

È possibile eliminare un feed non più necessario o utilizzato.

<!-- 

t_deleting_a_feed.xml

 -->

**Per eliminare un feed**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. Nella schermata [!DNL Feeds Menu], nella colonna [!DNL Actions] fare clic su **[!UICONTROL Delete]** per il nome del feed che si desidera rimuovere.
1. Nella finestra di dialogo [!DNL Delete feed], fai clic su **[!UICONTROL Yes]** per confermare l’eliminazione.

## Visualizzazione dei file di feed {#task_1E413C7650DE466EA68925F72E086884}

Puoi passare all’ultimo pannello della procedura guidata Feed per accedere rapidamente alla visualizzazione dei dati del feed o per scaricare dal server eventuali file di feed correnti. Questa funzionalità è utile per verificare ed esaminare l’output del feed.

<!-- 

t_viewing_feed_files.xml

 -->

**Per visualizzare i file di feed**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. Nella pagina [!DNL Feeds], sotto la colonna [!DNL Name] della tabella, fai clic sull’elenco a discesa accanto al nome di un feed, quindi fai clic su **[!UICONTROL View Feed Files]**.
1. Nel pannello [!DNL Verification] della procedura guidata del feed, fai clic su **[!UICONTROL Show Data View]**.
1. Clic **[!UICONTROL Close]**.

## Verifica di un feed senza caricamento di file {#task_F1F390F72E0A4886B6CD4CD86EDB4C8C}

Puoi testare un feed senza caricare i file nella destinazione finale.

<!-- 

t_testing_a_feed_with_no_file_upload.xml

 -->

**Per testare un feed senza caricamento di file**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. Nella pagina [!DNL Feeds], sotto la colonna [!DNL Name] della tabella, fai clic sull’elenco a discesa accanto al nome di un feed, quindi fai clic su **[!UICONTROL Test Feed (No file upload)]**.
1. Nella pagina [!DNL Feeds] , la colonna [!DNL Feed Status] viene aggiornata durante e dopo il test.

## Generazione e caricamento di un feed {#task_C9A57827C7674035B62A22D310DDAA0C}

Puoi generare e inviare manualmente i file di feed alla destinazione finale, indipendentemente dalla pianificazione impostata nel pannello [!DNL File Submission] della procedura guidata Feed.

<!-- 

t_generating_and_uploading_a_feed.xml

 -->

Consulta anche [Creazione di un feed](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250).

**Per generare e caricare un feed**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. Nella pagina [!DNL Feeds], sotto la colonna [!DNL Name] della tabella, fai clic sull’elenco a discesa accanto al nome di un feed, quindi fai clic su **[!UICONTROL Generate and Upload Feed]**.
1. Nella pagina [!DNL Feeds] , la colonna [!DNL Feed Status] viene aggiornata durante e dopo la generazione e il caricamento del feed di dati.
