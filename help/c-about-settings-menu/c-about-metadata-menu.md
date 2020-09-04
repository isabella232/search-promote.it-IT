---
description: Utilizzate il menu Metadati per personalizzare le definizioni di ricerca e le iniezioni di indice.
seo-description: Utilizzate il menu Metadati per personalizzare le definizioni di ricerca e le iniezioni di indice.
seo-title: Informazioni sul menu Metadati
solution: Target
subtopic: Metadata
title: Informazioni sul menu Metadati
topic: Settings,Site search and merchandising
uuid: f12fc863-a140-45e8-b219-3dbfdef099cd
translation-type: tm+mt
source-git-commit: 552f93f1f630c64bbe3d5c8a87c4f5895ae6868c
workflow-type: tm+mt
source-wordcount: '8039'
ht-degree: 1%

---


# Informazioni sul menu Metadati{#about-the-metadata-menu}

Utilizzate il menu Metadati per personalizzare le definizioni di ricerca e le iniezioni di indice.

## Informazioni sulle definizioni {#concept_AE48035C210145169BE067D396975620}

Potete utilizzare [!DNL Definitions] per personalizzare il contenuto e la rilevanza dei campi HTML e di metadati che vengono presi in considerazione quando un cliente invia una query di ricerca.

È possibile modificare i campi già definiti in precedenza. Oppure potete anche creare nuovi campi definiti dall’utente basati sul contenuto dei tag di metadati. Ogni definizione viene visualizzata su un&#39;unica riga sulla [!DNL Staged Definitions] pagina.

Vedere anche [Informazioni sulle visualizzazioni](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3)dati.

## Aggiunta di un nuovo campo tag meta {#task_6DF188C0FC7F4831A4444CA9AFA615E5}

Potete definire e aggiungere campi di tag per metadati personalizzati.

Prima che gli effetti della nuova definizione del tag meta siano visibili ai clienti, dovete ricreare l&#39;indice del sito.

**Aggiunta di un nuovo campo tag meta**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Sulla [!DNL Definitions] pagina, fate clic su **[!UICONTROL Add New Field]**.
1. Nella [!DNL Add Field] pagina, impostate le opzioni desiderate.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome campo </p> </td> 
      <td colname="col2"> <p>Specifica un nome utilizzato per fare riferimento al campo. </p> <p>Il nome del campo deve rispettare le regole seguenti: </p> <p> 
      <ul id="ul_D39D09CD7E7D41A59ECB6C5A6F4F263D"> 
      <li id="li_11CE852BE3C64CEF90FEC7A6E1079E13"> Il nome deve contenere solo caratteri alfanumerici. </li> 
      <li id="li_7FC340E7C58545C88CE9AF4AF09AD7AD"> I trattini sono consentiti nel nome, ma nessun spazio. </li> 
      <li id="li_996FF38457AB4C6DB22B15850A0830CC"> Potete immettere un nome lungo fino a 20 caratteri. </li> 
      <li id="li_C1019E587995444D9587D5EA495D719E"> Il nome non fa distinzione tra maiuscole e minuscole, ma viene visualizzato e memorizzato esattamente mentre viene digitato. </li> 
      <li id="li_E55404D6CE354EC89CFFEB1048A11F44"> Non è possibile utilizzare i nomi esistenti nei campi predefiniti come mostrato nella tabella della pagina Definizioni <span class="wintitle"> in fase </span> . </li> 
      <li id="li_7CE328AE3B5F45A8A09E2DA7ECB62551"> Non è possibile utilizzare la parola "any" come valore di un nome di campo definito dall'utente. </li> 
      <li id="li_9B8287EED1784E79BFCBBBA956705CD2"> Non è possibile modificare i nomi dei campi predefiniti. </li> 
      </ul> </p> <p> Esempi di nome campo: </p> <p> 
      <ul id="ul_5881669913D04E35A6D4A6D31BEE7DF3"> 
        <li id="li_0AFFB8B516FE40F8A615C2F578F2CEA3"> author </li> 
        <li id="li_7F0ADFBFB21E4B84ACA8A1CEBFE344D1"> DataPubblicazione </li> 
        <li id="li_6D1BEB3D19AC499E9227EC115AEB6296"> qualcosa di selvaggio </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome/i tag meta </p> </td> 
      <td colname="col2"> <p>Determina il contenuto associato al campo definito. </p> <p>L'elenco dei nomi può contenere fino a 255 caratteri. Inoltre, name può contenere qualsiasi carattere consentito nell'attributo name di un tag meta HTML. </p> <p>È possibile specificare più tag meta in un'unica definizione di campo. </p> <p>I valori multipli devono essere separati da virgola e il nome del tag meta più a sinistra trovato in una determinata pagina Web ha la precedenza. </p> <p>Ad esempio, si supponga di aver definito un campo denominato "auth". Al nome del campo sono associati i tag meta "author, dc.author". In questo caso, il contenuto del tag meta "author" viene indicizzato e ricercato su quello di "dc.author" se entrambi i tag meta vengono visualizzati su una pagina Web. </p> <p>I campi definiti dall’utente devono avere nella definizione almeno un nome di tag meta. I campi predefiniti non devono avere un tag meta associato. Tuttavia, se vengono specificati uno o più tag meta, il contenuto dei tag meta sostituisce l'origine dati corrente per ciascun tag. </p> <p>Ad esempio, se il tag meta "dc.title" è associato al campo "title" predefinito, il contenuto del tag meta "dc.title" viene indicizzato su quello del <code>
        &lt;title&gt; 
      </code> tag per qualsiasi documento specifico. </p> <p>Esempi: </p> <p> 
      <ul id="ul_0132E15FC19E4C0CA13CD5A12EA3BBEC"> 
      <li id="li_ECD3B194FECB4C2090CAEC8449320D3F"> dc.date </li> 
      <li id="li_09C76BC7AC7348859D01989697212E31"> description </li> 
      <li id="li_9230C0450F9D424087D1F127048DA311"> proprietarytag </li> 
      </ul> </p> </td> 
    </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo di dati </p> </td> 
      <td colname="col2"> <p>A ogni campo è associato un tipo di dati quale testo, numero, data, versione, classificazione o posizione. Questo tipo di dati determina il modo in cui il contenuto del campo viene indicizzato, ricercato ed eventualmente ordinato. </p> <p>Non è possibile modificare il tipo di dati dopo la creazione della definizione del campo. </p> <p>Per selezionare il tipo di dati pertinente alle informazioni contenute nel campo, utilizzare le informazioni seguenti. </p> <p> 
      <ul id="ul_A3AD5A0CF354410F836311F39151B8A6"> 
      <li id="li_9F412DA7D9EF497BA6E65F9CE10F3046"> <span class="uicontrol"> I campi dei tipi di </span> dati di testo sono trattati come stringhe di caratteri. </li> 
      <li id="li_AD78B75644AE40208F0239311015611F"> <span class="uicontrol"> I campi del tipo di dati Number </span> sono trattati come valori numerici interi o a virgola mobile. </li> 
      <li id="li_0B46975C589148E9A7C32A8D250487B7"> <span class="uicontrol"> I campi </span> del tipo di dati data sono trattati come specificatori di data/ora. È possibile personalizzare i formati data/ora consentiti quando si aggiunge o si modifica il nuovo campo. </li> 
      <li id="li_BB68CB1DBE0543AC9000B3DEDFB28E7E"> <span class="uicontrol"> I campi del tipo di dati della versione </span> sono trattati come dati numerici a forma libera. Ad esempio, 1.2.3 ordina prima di 1.2.2. </li> 
      <li id="li_0BA895B4DADA46528A7A4161EEB1521E"> <span class="uicontrol"> I campi </span> del tipo di dati classifica sono trattati allo stesso modo dei campi del tipo "Number", con la differenza che influenzano anche i calcoli di classificazione/rilevanza nei risultati della ricerca. <p>Vedere <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" type="concept" format="dita" scope="local"> Informazioni sulle regole di classificazione </a>. </p> </li> 
      <li id="li_459405DA437049AD88AA1FAC28F04720"> <span class="uicontrol"> I campi </span> del tipo di dati della posizione sono trattati come una posizione fisica ovunque nel mondo. I formati di posizione consentiti sono i seguenti: <p> 
      <ul id="ul_D2CEBFA1A5504AA996BA2F7641AFB7F3"> 
      <li id="li_5283A2F2D5D84840B3D920C08D43654C"> Codici ZIP di 5 o 9 cifre sotto forma di DDDDD o DDDDD-DDDD, dove ogni "D" è una cifra di 0-9. </li> 
      <li id="li_A5CD4DFC90164BC68183DB7D10603B7C"> Codici di area a tre cifre sotto forma di DDD. </li> 
      <li id="li_9DAEAE64BC7F4902B25043D998C8F56D"> Coppie latitudine/longitudine nel formato ±DD.DDDD±DDD.DDDD, dove il primo numero specifica la latitudine e il secondo indica la longitudine. </li> 
      </ul> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>elenchi consentiti  </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato il tipo di dati <span class="uicontrol"> Testo </span>, o <span class="uicontrol"> Numero </span> . </p> <p>I valori delimitati da indice separato nel contenuto di metadati di questo campo. </p> <p>Ad esempio, il contenuto "Rosso, Giallo, Verde, Blu" viene trattato come quattro valori separati invece di uno quando si seleziona " Elenchi consentiti". Questo trattamento è particolarmente utile con la ricerca intervallo (utilizzando <code>
        sp_q_min 
      </code>, <code>
        sp_q_max 
      </code>, o <code>
        sp_q_exact 
      </code>) e con <code>
        &lt;search-field-value-list&gt; 
      </code>, <code>
        &lt;search-field-values&gt; 
      </code>, e <code>
        &lt;search-display-field-values&gt; 
      </code>. </p> <p>Non disponibile se è selezionato il tipo di dati Versione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Facet dinamico </p> </td> 
      <td colname="col2"> <p> 
        <!--NEW 2/2/2014--> <p>Nota:  Questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivarlo e utilizzarlo. Dopo essere stato attivato, viene visualizzato nell'interfaccia utente. </p> </p> <p>Imposta il facet identificato come dinamico. </p> <p>I facet sono composti sopra i campi dei tag meta. Un campo tag meta è un livello di ricerca di base basso di  Search&amp;Promote Adobe. I facet fanno invece parte di GS (Guided Search), il livello di presentazione di alto livello del Search&amp;Promote  Adobe. I facet dispongono di campi di tag meta, tuttavia, i campi di tag meta non conoscono i facet. </p> <p>Consultate <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> I facet dinamici </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Consenti deduplicazione </p> </td> 
      <td colname="col2"> <p>Selezionare questa opzione per abilitare la deduplicazione per questo campo. Questo campo può essere specificato in fase di ricerca tramite il parametro <code>
          sp_dedupe_field 
        </code> CGI di ricerca. </p> <p>Consultate <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Cercare i parametri CGI </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome tabella </p> </td> 
      <td colname="col2"> <p>Associa in modo permanente il campo specificato al nome della tabella specificato. </p> <p>Ogni volta che un campo di questo tipo viene menzionato in un parametro CGI di ricerca di base o in un tag modello, il nome della tabella viene fornito automaticamente. Questa funzione consente di selezionare i facet dinamici attraverso le corrispondenze tra tabelle, ma può essere utilizzata anche per i campi facet non dinamici, se necessario. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimitatori elenco </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> Elenchi consentiti </span> è selezionato. </p> <p>Specifica quali caratteri separano i singoli valori dell'elenco. È possibile specificare più caratteri, ciascuno dei quali è trattato come un separatore di valori. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ricerca per impostazione predefinita </p> </td> 
      <td colname="col2"> <p>Quando è selezionata questa opzione, la ricerca nel contenuto del campo viene eseguita anche quando il campo non è specificato in modo esplicito in una determinata query di ricerca. Se deselezionate questa opzione, la ricerca nel campo viene eseguita solo se richiesto. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Campo aggiornamento verticale </p> </td> 
      <td colname="col2"> <p> <p>Nota:  Questa funzione non è abilitata per impostazione predefinita. Contattate il supporto tecnico per attivarlo e utilizzarlo. Dopo essere stato attivato, viene visualizzato nell'interfaccia utente. </p> </p> <p>Imposta il campo identificato come campo Aggiornamento verticale. </p> <p>I campi Aggiornamento verticale sono candidati per l’aggiornamento mediante il processo di aggiornamento verticale ( <span class="uicontrol"> Indice </span> &gt; Aggiornamento <span class="uicontrol"> verticale </span>). A causa del modo in cui vengono eseguiti gli aggiornamenti verticali, non è possibile effettuare ricerche di contenuto in questi campi nelle ricerche in testo libero. Selezionando questa opzione, il contenuto del campo non viene aggiunto all'indice "word" durante qualsiasi operazione di indicizzazione. Consente inoltre di aggiornare il campo durante un'operazione di aggiornamento verticale. </p> <p>Per ulteriori informazioni sugli aggiornamenti verticali, consultate <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Informazioni sull'aggiornamento verticale </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rilevanza </p> </td> 
      <td colname="col2"> <p>Potete modificare la rilevanza dei campi predefiniti e definiti dall’utente. </p> <p>La rilevanza è specificata in una scala da 1 a 10. Con un valore pari a 1 si intende che è il meno rilevante e che 10 è il più rilevante. Questi valori vengono presi in considerazione quando il software considera le corrispondenze della query in ciascun campo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ordinamento </p> </td> 
      <td colname="col2"> <p>Specifica quando i risultati vengono ordinati in base al campo denominato, tramite il parametro <code>
          sp_s 
        </code> CGI di ricerca. </p> <p>Consultate <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Cercare i parametri CGI </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lingua </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Classifica </span>, <span class="uicontrol"> Numero </span>, o <span class="uicontrol"> Data </span> è selezionato. </p> <p>Controlla le convenzioni della lingua e delle impostazioni internazionali applicate durante l'indicizzazione dei valori di data, numero e classificazione di questo campo. </p> <p>È possibile scegliere di applicare la lingua dell'account (Linguistica &gt; Parole e lingue). In alternativa, è possibile applicare la lingua associata al documento contenente ciascun numero o valore data, oppure una lingua specifica. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formato/i data/i </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Data </span> è selezionato. </p> <p>Controlla i formati data riconosciuti durante l'indicizzazione dei valori data per questo campo. </p> <p>Per ogni campo data viene fornito un elenco predefinito di stringhe di formato data. È possibile aggiungere o modificare l'elenco in base alle esigenze del proprio sito. </p> <p>Vedere <a href="../c-appendices/r-date-formats.md#reference_4D1FC1F6B9F44857967188496D8D335B" type="reference" format="dita" scope="local"> Formati di data </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formati data test </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Data </span> è selezionato come Tipo di dati. </p> <p>Consente di visualizzare in anteprima i formati data specificati per garantire che siano formattati correttamente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fuso orario </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Data </span> è selezionato come Tipo di dati. </p> <p>Controlla il fuso orario presunto applicato durante l'indicizzazione dei valori di data per il campo che non specifica un fuso orario. </p> <p>Ad esempio, se il fuso orario del tuo account è impostato su "America/Los Angeles" e si seleziona <span class="uicontrol"> Usa fuso orario account </span>, il seguente valore della data meta, che non ha un fuso orario specificato, viene trattato come se fosse Pacifico, tenendo conto del risparmio di luce del giorno: </p> <p>&lt;meta name="dc.date" content="Mon, 05 set 201213:12:00"&gt; </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore classificazione meno importante </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Classifica </span> è selezionato come Tipo di dati. </p> <p>Controlla il valore della classificazione che rappresenta la classificazione minima di qualsiasi documento. </p> <p>Se le classificazioni del documento sono comprese tra 0 per il livello più basso e 10 per il livello più alto, impostare questo valore su 0. </p> <p>Se le classificazioni del documento sono comprese tra 1 per il livello più alto e 10 per il livello più basso, impostare questo valore su 10. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore classifica predefinito </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Classifica </span> è selezionato come Tipo di dati. </p> <p>Controlla il valore della classificazione utilizzato se un documento non contiene tag meta definiti per questo campo di classificazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore classificazione più importante </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Classifica </span> è selezionato come Tipo di dati. </p> <p>Controlla il valore della classificazione che rappresenta il livello massimo di qualsiasi documento. </p> <p>Se le classificazioni del documento sono comprese tra 0 per il livello più basso e 10 per il livello più alto, impostare questo valore su 10. </p> <p>Se le classificazioni del documento sono comprese tra 1 per il livello più alto e 10 per il livello più basso, impostare questo valore su 1. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Unità predefinite </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Posizione </span> è selezionato come Tipo di dati. </p> <p>Controlla il trattamento dei valori di distanza per le ricerche di prossimità. </p> <p>Se impostate le unità predefinite su <span class="uicontrol"> Miglia </span>, tutti i criteri di distanza minima/massima della ricerca di prossimità applicati a questo campo (tramite i parametri CGI <code>
        sp_q_min[_#] 
      </code> o di <code>
        sp_q_max[_#] 
      </code> Ricerca) vengono trattati come miglia, altrimenti come chilometri. </p> <p>Questa opzione controlla anche le unità di distanza predefinite applicate all’output del tag modello di <code>
        &lt;Search-Display-Field&gt; 
      </code> risultati di ricerca quando applicato a un campo di output di ricerca di prossimità. </p> <p>Consultate <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> La ricerca di prossimità </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Creare una descrizione dell'intervallo? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> Numero </span> è selezionato come Tipo di dati. </p> <p>Controlla la creazione automatica delle descrizioni dell'intervallo di campi, da utilizzare con <span class="uicontrol"> Design </span> &gt; <span class="uicontrol"> Navigation </span> &gt; <span class="uicontrol"> Facet </span>. </p> <p>Consultate <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" format="dita" scope="local"> I Facet </a>. </p> <p> <p>Nota:  Se questo campo è stato <span class="uicontrol"> selezionato Campo aggiornamento </span> verticale, il campo di descrizione Intervallo campi generato viene aggiornato durante un aggiornamento verticale. Tuttavia, si consiglia che anche il campo identificato nel campo <span class="uicontrol"> Intervallo </span> abbia <span class="uicontrol"> selezionato Campo aggiornamento verticale </span> . </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Campo intervallo </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> Crea descrizione intervallo </span> è selezionata. </p> <p>Il <span class="uicontrol"> campo di testo </span> da aggiornare con le descrizioni dell'intervallo per il campo corrente. Questo elenco contiene tutti <span class="uicontrol"> i campi di testo </span> che non sono già utilizzati con altri campi per la generazione dell'intervallo di campi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valori intervallo </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo </span> e se è selezionata l'opzione <span class="uicontrol"> Campo intervallo </span> . </p> <p>Elenco delimitato da spazi vuoti di punti dati da utilizzare per la creazione delle descrizioni dell'intervallo di campi. Ad esempio: </p> <code> 10&amp;nbsp;20&amp;nbsp;50&amp;nbsp;100&amp;nbsp;1000 </code> <p>Potete inserire questi valori in qualsiasi ordine. I valori vengono ordinati e i duplicati rimossi prima di essere salvati. È inoltre possibile specificare valori negativi e non interi. </p> <p>Per ciascuno dei valori di questo campo: 
      <ul id="ul_C4B41AF5AADF4B84B9C489CE82FF7075"> 
      <li id="li_90736394A5AE4F5CA6B47687BCB627AA">se il valore è minore di (&lt;) il valore più piccolo in Valori <span class="uicontrol"> intervallo </span>, viene utilizzato il formato <span class="uicontrol"> "Minore di" </span> </li> 
      <li id="li_A5C272B2D26A468CA07EB2046B2EA8A7">se il valore è maggiore o uguale a (&gt;=) del valore più grande in Valori <span class="uicontrol"> intervallo </span>, viene utilizzato il formato <span class="uicontrol"> "Maggiore di" </span> . </li> 
      <li id="li_9DDFB70E1E824CF4819C57450C1A6DD2">in caso contrario, viene trovato un "intervallo" in cui il valore del campo rientra tra due valori <span class="uicontrol"> Range consecutivi </span> (maggiore di (&gt;) il valore minore e minore o uguale a (&lt;=) il valore maggiore), e viene utilizzato il formato <span class="uicontrol"> Intermedio </span> . </li> 
    </ul> </p> <p>Ad esempio, il precedente set di valori definirà un insieme di descrizioni per i valori: 
    <ul id="ul_03ED30D5A19346AB8E6809BDD186A9A9"> 
      <li id="li_F97A6B3763954EFE9B6751F472AF7D20">inferiore a 10 </li> 
      <li id="li_12B6F636A6444B8292E0BFE4F55032DF">maggiore o uguale a 10 e inferiore a 20 </li> 
      <li id="li_545A2EAF5BD046B5AD59B77DB43DCD14">maggiore o uguale a 20 e inferiore a 50 </li> 
      <li id="li_26A8CD2422524D2CBD36794C6908572A">maggiore o uguale a 50 e inferiore a 100 </li> 
      <li id="li_05EBEEE68DC348E0821F1CC16D04D69C">maggiore o uguale a 100 e inferiore a 10000 </li> 
      <li id="li_9513A6B519394780A6A41B80762A0370">greater than or equal to 10000 </li> 
      </ul> </p> <p>Vedete <span class="uicontrol"> Test using Greater? </span> per modificare il modo in cui vengono eseguiti i test. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formato "Minore di" </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo </span> e se è selezionata l'opzione <span class="uicontrol"> Campo intervallo </span> . </p> <p>Questo è il modello utilizzato per specificare la descrizione dell'intervallo per i valori inferiori al valore più piccolo trovato in Valori <span class="uicontrol"> intervallo </span>. Il valore più piccolo sarà rappresentato utilizzando il token segnaposto numerico <span class="uicontrol"> ~N~ </span>. Ad esempio: </p> <code> Less&amp;nbsp;than&amp;nbsp;~N~ </code> <p>o: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;below </code> <p>Normalmente, il valore sarà formattato "così com'è" - cioè per una <span class="uicontrol"> definizione di valori di intervallo </span> di "5 10 20" e un valore fornito di 1, la descrizione dell'intervallo generato sarebbe semplicemente qualcosa come "Minore di 5". Se invece desiderate che sia "4.99 e inferiore", impostate <span class="uicontrol"> Precision </span> su <span class="uicontrol"> 2 </span> e utilizzate il seguente formato: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;below </code> <p>In formato <span class="uicontrol"> "Minore di" </span>, il minuscolo <span class="uicontrol"> ~n~ </span> determina l'arrotondamento <i>verso il basso</i> del valore in base all'impostazione <span class="uicontrol"> Precisione </span> . </p> <p>Nota: per includere un segnaposto numerico nella descrizione dell'intervallo, come accade, specificate con il prefisso barra rovesciata (\) - ad esempio <span class="uicontrol"> \~N~ </span> o <span class="uicontrol"> \~n~ </span>. Per includere un carattere barra rovesciata, specificatelo con un’altra barra rovesciata, ad esempio <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formato intermedio </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo </span> e se è selezionata l'opzione <span class="uicontrol"> Campo intervallo </span> . </p> <p>Questo è il modello utilizzato per specificare la descrizione dell'intervallo per i valori compresi tra i valori più piccoli e quelli più grandi che si trovano nei valori <span class="uicontrol"> dell'intervallo </span>. Per l'intervallo specificato, il valore dell'intervallo inferiore sarà rappresentato utilizzando il token segnaposto numerico <span class="uicontrol"> ~L~ </span>, e il valore dell'intervallo più alto sarà rappresentato utilizzando il token <span class="uicontrol"> ~H~ </span>. Ad esempio: </p> <code> ~L~&amp;nbsp;to&amp;nbsp;~H~ </code> <p>o: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>o: </p> <code> Less&amp;nbsp;than&amp;nbsp;~H~&amp;nbsp;and&amp;nbsp;greater&amp;nbsp;than&amp;nbsp;~L~ </code> <p>Normalmente, i valori saranno formattati "così com'è" - cioè per una <span class="uicontrol"> definizione di valori intervallo </span> di "5 10 20" e un valore fornito di 8, la descrizione dell'intervallo generato sarebbe semplicemente qualcosa come "Tra 5 e 10". Se invece desiderate che sia "Tra 5 e 9,99", con il valore più alto regolato <i>verso il basso</i>, impostate <span class="uicontrol"> Precisione </span> su <span class="uicontrol"> 2 </span> e utilizzate questo formato: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~h~ </code> <p>Allo stesso modo, <span class="uicontrol"> ~L~ </span> può essere sostituito con <span class="uicontrol"> ~l~ </span> per avere il valore più basso regolato <i>verso l'alto</i>, anche in base all'impostazione <span class="uicontrol"> Precisione </span> . Ciò significa che una definizione come: </p> <code> Between&amp;nbsp;~l~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>con un <span class="uicontrol"> valore di precisione </span> pari a <span class="uicontrol"> 2 </span> si crea "Tra 5,01 e 10". </p> <p>La lettera minuscola <span class="uicontrol"> ~l~ </span> determina l'arrotondamento <i>verso l'alto</i> del valore inferiore in base all'impostazione <span class="uicontrol"> Precision </span> , mentre la lettera minuscola <span class="uicontrol"> ~h~ </span> determina l'arrotondamento <i>verso il basso</i>del valore più alto. </p> <p>Nota: per includere un segnaposto numerico nella descrizione dell'intervallo, come accade, specificate con il prefisso barra rovesciata (\) - ad esempio <span class="uicontrol"> \~L~ </span> o <span class="uicontrol"> \~h~ </span>. Per includere un carattere barra rovesciata, specificatelo con un’altra barra rovesciata, ad esempio <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formato "Maggiore di" </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo </span> e se è selezionata l'opzione <span class="uicontrol"> Campo intervallo </span> . </p> <p>Questo è il modello utilizzato per specificare la descrizione dell'intervallo per i valori superiori al valore più grande trovato in Valori <span class="uicontrol"> intervallo </span>. Il valore più grande sarà rappresentato utilizzando il token segnaposto numerico <span class="uicontrol"> ~N~ </span>. Ad esempio: </p> <code> Greater&amp;nbsp;than&amp;nbsp;~N~ </code> <p>o: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;above </code> <p>Normalmente, il valore sarà formattato "così com'è" - cioè per una <span class="uicontrol"> definizione di valori di intervallo </span> di "5 10 20" e un valore fornito di 30, la descrizione dell'intervallo generato sarebbe semplicemente qualcosa come "Maggiore di 20". Se invece desiderate che sia "20.01 e superiore", impostate <span class="uicontrol"> Precision </span> su <span class="uicontrol"> 2 </span> e utilizzate il seguente formato: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;above </code> <p>In formato <span class="uicontrol"> "Maggiore di" </span>, il minuscolo <span class="uicontrol"> ~n~ </span> determina l'arrotondamento <i>verso l'alto</i> del valore in base all'impostazione <span class="uicontrol"> Precisione </span> . </p> <p>Nota: per includere un segnaposto numerico nella descrizione dell'intervallo, come accade, specificate con il prefisso barra rovesciata (\) - ad esempio <span class="uicontrol"> \~N~ </span> o <span class="uicontrol"> \~n~ </span>. Per includere un carattere barra rovesciata, specificatelo con un’altra barra rovesciata, ad esempio <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Precisione </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo </span> e se è selezionata l'opzione <span class="uicontrol"> Campo intervallo </span> . </p> <p>Un valore intero che specifica il numero di cifre a destra di un separatore decimale. Questo controlla anche le operazioni di arrotondamento. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovere gli zeri iniziali? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo, </span> viene selezionata una voce Campo <span class="uicontrol"> intervallo </span> e viene impostato un valore <span class="uicontrol"> Precisione diverso da zero </span> . </p> <p>Dobbiamo visualizzare "0.50" come ".50"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Striscia zeri finali? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo, </span> viene selezionata una voce Campo <span class="uicontrol"> intervallo </span> e viene impostato un valore <span class="uicontrol"> Precisione diverso da zero </span> . </p> <p>Dovremmo visualizzare "10.00" come "10"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mostra migliaia di separatori? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo </span> e se è selezionata l'opzione <span class="uicontrol"> Campo intervallo </span> . </p> <p>Dovremmo visualizzare "10000" come "10000"? Verranno utilizzati valori specifici per le impostazioni internazionali. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Regolare valori zero? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo </span> e se è selezionata l'opzione <span class="uicontrol"> Campo intervallo </span> . </p> <p>Quando vengono visualizzati valori zero arrotondati, questi devono essere arrotondati per eccesso o per difetto in base all'impostazione <span class="uicontrol"> Precisione </span> ? ad es. display "0.01"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test con maggiore di? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo </span> e se è selezionata l'opzione <span class="uicontrol"> Campo intervallo </span> . </p> <p>Ciascun valore viene confrontato con i valori in Valori <span class="uicontrol"> intervallo </span>, elaborati in ordine <i><b>decrescente</b></i> , per impostazione predefinita viene confrontato utilizzando l'operatore Maggiore o Uguale (&gt;=), arrestandosi una volta completato il test. Questo significa che con un set di valori <span class="uicontrol"> Range </span> come "10 20 50 100 1000" il valore 100 sarà compreso tra 100 e 1000, in quanto 100 è effettivamente &gt;= 100. Se si desidera impostare un valore compreso tra 50 e 100, selezionare questa opzione per fare in modo che i confronti utilizzino l'operatore Maggiore di (&gt;). </p> <p>Ad esempio, per ciascuno dei valori di questo campo, quando questa opzione è selezionata: 
      <ul id="ul_969621B1BD914FA5BD73ED21F8841010"> 
      <li id="li_157BEFDA7D0E44C481F4E4BC9046EF24">se il valore è minore o uguale a (&lt;=) il valore più piccolo in Valori <span class="uicontrol"> intervallo </span>, viene utilizzato il formato <span class="uicontrol"> "Minore di" </span> </li> 
      <li id="li_737EE666CA6243A8864E17A311CF3ACC">se il valore è maggiore di (&gt;) il valore più grande in <span class="uicontrol"> Valori intervallo </span>, verrà utilizzato il formato <span class="uicontrol"> "Maggiore di" </span> </li> 
      <li id="li_353A9820F7F74CCCBB3281EC4CB48734">in caso contrario, verrà trovato un intervallo in cui il valore del campo rientra tra due valori <span class="uicontrol"> Range consecutivi </span> (maggiore o uguale a (&gt;=) il valore minore e minore di (&lt;) il valore maggiore), e verrà utilizzato il formato <span class="uicontrol"> Intermedio </span> </li> 
    </ul> </p> <p>e, se non è selezionato: 
    <ul id="ul_945844C33C2E4D95A598C4876E15F211"> 
      <li id="li_653B6E2934574DA3B4BCEF07D0A84527">se il valore è minore di (&lt;) il valore più piccolo in <span class="uicontrol"> Valori intervallo </span>, verrà utilizzato il formato <span class="uicontrol"> "Minore di" </span> </li> 
      <li id="li_AECA6880002F40FAB1820B37237550A7">se il valore è maggiore o uguale a (&gt;=) del valore più grande in Valori <span class="uicontrol"> intervallo </span>, viene utilizzato il formato <span class="uicontrol"> "Maggiore di" </span> </li> 
      <li id="li_ECB2DF7CA592497298E9ADC708220366">in caso contrario, verrà trovato un intervallo in cui il valore del campo rientra tra due valori <span class="uicontrol"> Range consecutivi </span> (maggiore di (&gt;) il valore minore e minore o uguale a (&lt;=) il valore maggiore), e verrà utilizzato il formato <span class="uicontrol"> Intermedio </span> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Disponibile solo se <span class="uicontrol"> è selezionata l'opzione Crea descrizione intervallo </span> e se è selezionata l'opzione <span class="uicontrol"> Campo intervallo </span> . </p> <p>Specificate un valore numerico di esempio e premete il <span class="uicontrol"> pulsante Prova </span> per vedere come viene creato il campo Intervallo. La descrizione dell'intervallo generato verrà visualizzata nella finestra. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Consultate anche [Aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)tag meta.
1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica di campi tag meta predefiniti o definiti dall’utente {#task_0A7657B63596421BB6DB3ED44F827AB3}

È possibile modificare solo alcuni campi nei tag meta predefiniti, oppure tutti i campi nei tag meta definiti dall&#39;utente.

Prima che gli effetti delle modifiche ai tag meta siano visibili ai clienti, dovete ricreare l&#39;indice del sito.

**Per modificare i campi tag meta predefiniti o definiti dall’utente**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Nella [!DNL Definitions] pagina, nella [!DNL Actions] colonna della tabella, fare clic **[!UICONTROL Edit]** nella riga del nome del campo del tag meta che si desidera modificare.
1. Nella [!DNL Pinned Keyword Results Manager] pagina, nella tabella, fare clic **[!UICONTROL Edit]** sulla riga della parola chiave che si desidera modificare.
1. Nella [!DNL Edit Field] pagina, impostate le opzioni desiderate.

   Se avete scelto di apportare modifiche a un campo di tag meta predefinito, tenete presente che non tutti i campi sono modificabili.

   Vedere la tabella delle opzioni in [Aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)tag meta.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di un campo tag meta definito dall’utente {#task_9361EF38B5E743038B6672FA6CF70FD3}

È possibile eliminare un campo di tag meta definito dall&#39;utente che non è più necessario né utilizzato.

Non è possibile eliminare campi tag meta predefiniti. Tuttavia, è possibile modificare alcuni campi.

Consultate [Modifica di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3)di tag meta predefiniti o definiti dall’utente.

Prima che gli effetti del tag meta di eliminazione siano visibili ai clienti, dovete ricreare l&#39;indice del sito.

**Eliminazione di un campo tag meta definito dall&#39;utente**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Nella [!DNL Definitions] pagina, nella [!DNL User-defined fields] sezione della tabella, fare clic **[!UICONTROL Delete]** nella riga del nome del campo del tag meta che si desidera rimuovere.
1. Nella finestra di dialogo Conferma, fate clic su **[!UICONTROL OK]**.
1. (Facoltativo) Per visualizzare in anteprima i risultati, ricreate l’indice del sito in fase di progettazione.

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. (Facoltativo) Nella [!DNL Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni sulle iniezioni {#concept_DA091920671948A0A893A26B3A2FAAE5}

È possibile utilizzare [!DNL Injections] per inserire contenuti nelle pagine Web senza dover modificare le pagine stesse.

Potete aggiungere contenuto a campi indicizzati specifici come &quot;target&quot; o &quot;body&quot; oppure sostituire il contenuto indicizzato con nuovi valori. Ad esempio, se hai inserito nuovo contenuto nel campo del tag meta &quot;target&quot;, queste informazioni vengono trattate come se si trattasse di contenuto della pagina codificato. Potete modificare il contenuto di qualsiasi campo di tag meta predefinito, indipendentemente dal fatto che le pagine del sito abbiano o meno il contenuto corrispondente. Ad esempio, potete modificare il contenuto dei seguenti nomi di campi tag meta predefiniti:

* Alt
* body
* charset
* date
* desc
* keys
* language
* target
* title
* url

## Utilizzo delle iniezioni dei campi di prova {#section_74939EA9E6EA4D2A92E8066B3B11CF92}

Facoltativamente, potete utilizzare **[!UICONTROL Test]** sulla [!DNL Staged Injections] pagina. Potete immettere un nome di campo di prova (ad esempio, &quot;title&quot; o &quot;body&quot;), il valore di campo originale (ad esempio, &quot;Home Page&quot;) e un URL di prova dal sito Web. Il valore risultante viene visualizzato come riferimento. I valori correnti non vengono modificati durante il test.

## Utilizzo delle definizioni di iniezione dei campi {#section_C1BBF19DE8EF4A6F8CC3ED691F3953A9}

Le definizioni di iniezione hanno il seguente modulo:

```
append|replace field [regexp] URL value
```

The `append|replace`, `field`, `URL`. e `value` gli elementi sono obbligatori. È possibile inserire una definizione di iniezione per riga. L&#39;esempio seguente contiene sei diverse definizioni di iniezione.

```
replace title  https://www.yoursite.com/company/contactus.html Adobe: Contact Us 
append body https://www.yoursite.com/products/* On Sale Now! 
append target https://www.yoursite.com/news/bob_white/ Regular Weekly Feature 
append target regexp https://www.yoursite.com/travel/mr_travel/.*\column.html$ Regular Weekly Feature 
replace charset https://www.yoursite.com/japanese/intro.txt shift-jis 
replace language https://www.yoursite.com/japanese/intro.txt ja_JP
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Definizione di iniezione </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> append|replace </span> </p> </td> 
   <td colname="col2"> <p>Scegliete "append" per aggiungere il valore della definizione di iniezione ("Adobe : Contattaci" o "In vendita!" negli esempi di cui sopra) al contenuto dei campi esistenti. Scegliete "replace" per sovrascrivere il contenuto del campo esistente con il valore definito. Se un campo al momento non ha contenuto, il valore definito viene aggiunto automaticamente, indipendentemente dall'opzione (accoda o sostituisce) utilizzata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> field </span> </p> </td> 
   <td colname="col2"> <p>È richiesto un nome di campo. Di seguito sono riportati dieci nomi di campo predefiniti utilizzabili: </p> <p> 
     <ul id="ul_B9336FA53023474EAEE399116E7FC972"> 
      <li id="li_C621203DCD2B4875A54A1DD19F0B5B90"> <span class="codeph"> alt </span> </li> 
      <li id="li_9217E6A037254BEDBB8D006B70D7670D"> <span class="codeph"> body </span> </li> 
      <li id="li_DCDC50F93F224F02897419B745E09399"> <span class="codeph"> charset </span> </li> 
      <li id="li_D95668236B6547B99966668C82B302AB"> <span class="codeph"> date </span> </li> 
      <li id="li_D2071681274345C3B97E9ADA6D223271"> <span class="codeph"> desc </span> </li> 
      <li id="li_26683A9209454A438D811187FB929482"> <span class="codeph"> keys </span> </li> 
      <li id="li_A5E19F81B872402CA62B5AB9497E030D"> <span class="codeph"> language </span> </li> 
      <li id="li_FD0B1CD9E6304B18B9D7F57E61015107"> <span class="codeph"> target </span> </li> 
      <li id="li_400D7E3F3E9B47EFB2FF5C0D278DB573"> <span class="codeph"> title </span> </li> 
      <li id="li_449BCBEE4F64424BB69F780C10F5956C"> <span class="codeph"> url </span> </li> 
     </ul> </p> <p>Ogni nome campo corrisponde agli elementi presenti nelle pagine del sito. Se si specifica il nome del campo <span class="codeph"> desc </span> , ad esempio, è possibile aggiungere il valore della definizione di iniezione al campo che corrisponde alla descrizione Meta tag nelle pagine del sito. </p> <p>Se nelle pagine non è presente alcuna descrizione, il contenuto definito crea automaticamente il tag. Il contenuto specificato in un' <span class="codeph"> iniezione desc </span> viene visualizzato sulla pagina dei risultati esattamente come il contenuto di Meta-descrizione hardcoded. </p> <p>È inoltre possibile creare più definizioni con lo stesso nome campo. Ad esempio, supponiamo che tu abbia le seguenti iniezioni: </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/&nbsp;Welcome&nbsp;to&nbsp;My&nbsp;Site </code> </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/company/*.html&nbsp;My&nbsp;Site:&nbsp;Contact </code> </p> <p>Tutte le pagine del sito nell'esempio precedente ricevono il titolo "Benvenuti nel sito personale". Alle pagine della cartella "/company/" viene aggiunto il nuovo titolo "Sito personale: Contattateci" che sostituisce il precedente. </p> <p>Si noti che le iniezioni vengono applicate nell'ordine in cui appaiono nella casella di testo <span class="wintitle"> Definizioni iniezione campo </span> . Se lo stesso campo ("title" in questo esempio) è definito più di una volta per le pagine che si trovano nella stessa posizione, la definizione successiva ha la precedenza. </p> <p> <span class="codeph"> [regexp] </span> - facoltativo. Se scegliete di utilizzare l’opzione <span class="codeph"> regexp </span> , l’URL definito viene trattato come un’espressione regolare. </p> <p>Consultate <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> <p>Nella seguente definizione: </p> <p> <code> replace&nbsp;target&nbsp; <b>regexp&amp;nbsp;^.*/products/.*\.html$</b>&nbsp;Important&nbsp;information </code> </p> <p> Nel campo "target" vengono inserite "informazioni importanti" su tutte le pagine che corrispondono all'espressione regolare <span class="codeph"> ^.*/products/.*\.html$ </span>. </p> <p>Di conseguenza, si dispone dei seguenti elementi: </p> <p> <code> https://www.mydomain.com/products/page1.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p> <code> https://www.mydomain.com/product/oldstuff.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;not&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p>Nell'esempio seguente: </p> <p> <code> append&amp;nbsp;title&amp;nbsp;regexp&amp;nbsp;^.*\.pdf$&amp;nbsp;Millennium&amp;nbsp;Science </code> </p> <p>L'iniezione aggiunge "Millennium Science" al contenuto "title" di tutte le pagine che terminano con un'estensione ".pdf". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> URL </span> </p> </td> 
   <td colname="col2"> <p>Un URL è obbligatorio e specifica quali documenti vengono inviati. </p> <p>L’URL è uno dei seguenti: </p> <p> 
     <ul id="ul_C5C74F6D5EA943B293742989EB822751"> 
      <li id="li_382392DB778D4E14BFFC96D35A861951"> Un percorso completo, come in https://www.mydomain.com/products.html </li> 
      <li id="li_EA2BD0FB66A44CD0844613316F6174D4"> Un percorso parziale, come in https://www.mydomain.com/products </li> 
      <li id="li_D5E0D6D897C8493ABBFC65517CD4A7DB"> Un URL che utilizza caratteri jolly, come in https://www.mydomain.com/*.html </li> 
     </ul> </p> <p>Il valore URL non deve contenere spazi. Se si utilizza l’opzione <span class="codeph"> regexp </span> , l’URL viene trattato come un’espressione regolare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> value </span> </p> </td> 
   <td colname="col2"> <p>Un valore è obbligatorio ed è utilizzato per sostituire o aggiungere al contenuto del campo esistente. È possibile specificare più valori per lo stesso nome campo. Ad esempio: </p> <p>aggiungi <b>le chiavi</b> https://www.mysite.com/travel/ <b>estate</b>, <b>spiaggia</b>, <b>sabbia</b> </p> <p>aggiungi <b>le chiavi</b> https://www.mysite.com/travel/fare/*.html biglietti <b>economici</b> </p> <p>Nell'esempio precedente, le parole "estate, spiaggia, sabbia" sono aggiunte al campo "chiavi" su tutte le pagine della directory "/travel/". Le parole "biglietti economici" sono aggiunte anche al campo "chiavi" su tutte le pagine della directory "/travel/fare/". </p> </td> 
  </tr> 
 </tbody> 
</table>

Consultate anche [Selezione dei tipi di contenuto per la ricerca per indicizzazione e per indicizzazione](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

## Aggiunta di definizioni di iniezione di campi {#task_E86566FA1FF74CF68115C0ADA05172AE}

È possibile utilizzare [!DNL Injections] per inserire contenuti nelle pagine Web senza dover modificare le pagine stesse.

Facoltativamente, potete utilizzare **[!UICONTROL Test]** sulla [!DNL Injections] pagina. Potete immettere un nome di campo di prova (ad esempio, &quot;title&quot; o &quot;body&quot;), il valore di campo originale (ad esempio, &quot;Home Page&quot;) e un URL di prova dal sito Web. Il valore risultante viene visualizzato come riferimento. I valori correnti non vengono modificati durante il test.

**Aggiunta di definizioni di iniezione di campi**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**.
1. (Facoltativo) Nella [!DNL Injections] pagina, nell’ [!DNL Test Field Injections] area, immettete il campo test, il valore originale del test e l’URL test, quindi fate clic su **[!UICONTROL Test]**.
1. Nel [!DNL Field Injection Definitions] campo, immettere una definizione di iniezione per riga.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Informazioni su Caricatore attributi {#concept_9EF38E98811B42CDA41996432B9AD209}

Consente [!DNL Attribute Loader] di definire ulteriori origini di input per l’aumento dei dati sottoposti a ricerca per indicizzazione da un sito Web.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nell&#39;account dal rappresentante dell&#39;account  Adobe o dal supporto  Adobe.

È possibile utilizzare un&#39;origine di input di feed di dati per accedere al contenuto memorizzato in un modulo diverso da quello che viene generalmente scoperto in un sito Web. A tale scopo, è possibile utilizzare uno dei metodi disponibili per la ricerca per indicizzazione. I dati provenienti da queste origini possono quindi essere inseriti nei dati provenienti dal contenuto sottoposto a ricerca per indicizzazione.

Dopo aver aggiunto una definizione di Caricatore attributi alla [!DNL Staged Attribute Loader Definitions] pagina, è possibile modificare qualsiasi impostazione di configurazione tranne i valori Nome e Tipo

La [!DNL Attribute Loader] pagina mostra le informazioni seguenti:

* Il nome della configurazione del Caricatore attributi definita configurata e aggiunta.
* Uno dei seguenti tipi di origini dati per ciascun connettore aggiunto:

   * **Testo** - File semplici, delimitati da virgole, delimitati da tabulazioni o altri formati delimitati in modo coerente.
   * **Feed** - Feed XML.

* Indica se la configurazione è abilitata o meno per la ricerca per indicizzazione e l&#39;indicizzazione successive.
* Indirizzo dell&#39;origine dati.

Consultate anche [Funzionamento del processo di iniezione degli attributi per Testo e Feed...](../c-about-settings-menu/c-about-metadata-menu.md#section_E059A33D61EE4DB0972A37B8A35E9E16)

Vedere anche [Informazioni sulla configurazione di più caricatori attributi](../c-about-settings-menu/c-about-metadata-menu.md#section_4CC49C74EF294608A184E233F215ADFF)

Vedere anche [Informazioni sull&#39;utilizzo dell&#39;anteprima quando si aggiunge un attributo.](../c-about-settings-menu/c-about-metadata-menu.md#section_E9CAB000A94C4D9189786C1EDB1CDB46)

## Funzionamento del processo di iniezione degli attributi per le configurazioni di testo e feed in Caricatore attributi {#section_E059A33D61EE4DB0972A37B8A35E9E16}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Passaggio </p> </th> 
   <th colname="col2" class="entry"> <p>Processo </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Scarica l'origine dati. </p> </td> 
   <td colname="col3"> <p>Per le configurazioni di testo e feed, si tratta di un semplice download di file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Suddivide l'origine dati scaricata in singoli pseudo-documenti. </p> </td> 
   <td colname="col3"> <p>Per <span class="uicontrol"> Testo </span>, ogni riga di testo delimitata da una nuova riga corrisponde a un singolo documento e viene analizzata utilizzando il delimitatore specificato, ad esempio una virgola o una tabulazione. </p> <p>Per <span class="uicontrol"> Feed </span>, i dati di ciascun documento vengono estratti utilizzando un pattern di espressione regolare nel seguente modulo: </p> <p> <code class="syntax js"> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Utilizzando <span class="uicontrol"> Map </span> nella pagina <span class="wintitle"> Attribute Loader Add </span> , create una copia memorizzata nella cache dei dati e quindi create un elenco di collegamenti per il crawler. I dati vengono memorizzati in una cache locale e compilati con i campi configurati. </p> <p>I dati analizzati vengono scritti nella cache locale. </p> <p>Questa cache viene letta in seguito per creare i documenti HTML semplici necessari al crawler. Ad esempio, </p> <p> <code class="syntax html"> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>L'elemento <span class="codeph"> &lt;title&gt; </span> viene generato solo quando esiste una mappatura nel campo di metadati Titolo. Analogamente, l'elemento <span class="codeph"> &lt;body&gt; </span> viene generato solo quando esiste una mappatura nel campo di metadati Body. </p> <p> <b>Importante</b>: L'assegnazione di valori al tag meta dell'URL predefinito non è supportata. </p> <p>Per tutte le altre mappature, vengono generati <span class="codeph"> &lt;meta&gt; </span> tag per ogni campo con dati trovati nel documento originale. </p> <p>I campi per ciascun documento vengono aggiunti alla cache. Per ogni documento scritto nella cache, viene generato anche un collegamento come negli esempi seguenti: </p> <p> <code class="syntax html"> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>La mappatura della configurazione deve avere un campo identificato come Chiave primaria. Questa mappatura costituisce la chiave utilizzata quando i dati vengono estratti dalla cache. </p> <p>Il crawler riconosce l’ <span class="codeph"> indice URL: </span> il prefisso dello schema, che può quindi accedere ai dati memorizzati nella cache locale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Eseguire la ricerca per indicizzazione del set di documenti memorizzato nella cache. </p> </td> 
   <td colname="col3"> <p>L' <span class="codeph"> indice: </span> i collegamenti vengono aggiunti all’elenco in sospeso del crawler e vengono elaborati nella normale sequenza di ricerca per indicizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Elabora ogni documento. </p> </td> 
   <td colname="col3"> <p>Il valore chiave di ciascun collegamento corrisponde a una voce nella cache, pertanto la ricerca per indicizzazione di ciascun collegamento determina il recupero dei dati del documento dalla cache. Viene quindi "assemblato" in un’immagine HTML elaborata e aggiunta all’indice. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Informazioni sulla configurazione di più caricatori attributi {#section_4CC49C74EF294608A184E233F215ADFF}

È possibile definire più configurazioni di Caricatore attributi per qualsiasi account.

Quando si aggiunge un Caricatore attributi, è possibile utilizzare la funzione **[!UICONTROL Setup Maps]** per scaricare un esempio dell&#39;origine dati. I dati vengono esaminati per verificarne l&#39;idoneità.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Tipo di caricamento attributi </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Testo </p> </td> 
   <td colname="col2"> <p>Determina il valore del delimitatore provando prima le tabulazioni, poi le barre verticali ( <span class="codeph"> | </span>) e infine virgole ( <span class="codeph"> , </span>). Se avete già specificato un valore di delimitazione prima di aver fatto clic su <span class="uicontrol"> Mappe di installazione </span>, tale valore viene utilizzato. </p> <p>Lo schema di adattamento ottimale si traduce nella compilazione dei campi Mappa con gli specchietti ai valori appropriati di Tag e Campo. Inoltre, viene visualizzato un esempio dei dati analizzati. Accertatevi di selezionare <span class="uicontrol"> Intestazioni nella prima riga </span> se si è certi che il file include una riga di intestazione. La funzione di configurazione utilizza queste informazioni per identificare meglio le voci di mappa risultanti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Scarica l'origine dati ed esegue un'analisi XML semplice. </p> <p>Gli identificatori XPath risultanti vengono visualizzati nelle righe Tag della tabella Mappa e valori simili nei campi. Queste righe identificano solo i dati disponibili e non generano le definizioni XPath più complesse. Tuttavia, è comunque utile perché descrive i dati XML e identifica l'elemento Tag. </p> <p> <p>Nota:  La funzione Setup Maps scarica l’intera origine XML per eseguire l’analisi. Se il file è di grandi dimensioni, l'operazione potrebbe non riuscire. </p> </p> <p>In caso di esito positivo, questa funzione identifica tutti gli elementi XPath possibili, molti dei quali non sono desiderabili da utilizzare. Accertatevi di esaminare le definizioni di mappa risultanti e rimuovere quelle non necessarie o desiderate. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>La funzione Mappe di installazione potrebbe non funzionare per set di dati XML di grandi dimensioni perché il parser di file tenta di leggere l’intero file in memoria. Di conseguenza, potrebbe verificarsi una condizione di memoria insufficiente. Tuttavia, quando lo stesso documento viene elaborato al momento dell&#39;indicizzazione, non viene letto in memoria. Al contrario, i documenti di grandi dimensioni vengono elaborati &quot;in movimento&quot; e non vengono prima letti completamente nella memoria.

## Informazioni sull&#39;utilizzo di Preview (Anteprima) quando si aggiunge un Caricatore attributi {#section_E9CAB000A94C4D9189786C1EDB1CDB46}

I dati del Loader di attributi vengono caricati prima di un&#39;operazione Index.

Al momento dell&#39;aggiunta di un Caricatore attributi, è possibile utilizzare la funzione **[!UICONTROL Preview]** per convalidare i dati, come se li si stesse salvando. Esegue un test rispetto alla configurazione, ma senza salvare la configurazione nell&#39;account. Il test accede all&#39;origine dati configurata. Tuttavia, scrive la cache di download in un percorso temporaneo; non entra in conflitto con la cartella cache principale utilizzata dal crawler di indicizzazione.

Preview elabora solo un predefinito di cinque documenti, come controllato da **Acct:IndexConnector-Preview-Max-Documents**. I documenti visualizzati in anteprima vengono visualizzati nel modulo di origine, man mano che vengono presentati al crawler di indicizzazione. La visualizzazione è simile alla funzione &quot;Visualizza origine&quot; di un browser Web. Potete spostarvi tra i documenti del set di anteprima utilizzando i collegamenti di navigazione standard.

L&#39;anteprima non supporta le configurazioni XML perché tali documenti vengono elaborati direttamente e non scaricati nella cache.

## Aggiunta di una definizione di Caricatore attributi {#task_A735E5EF763343A9B675E1A3B09AFDBC}

Ogni configurazione di Caricatore attributi definisce un&#39;origine dati e mappature che collegano gli elementi dati definiti per tale origine ai campi di metadati nell&#39;indice.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nell&#39;account dal rappresentante dell&#39;account  Adobe o dal supporto  Adobe.

Prima che gli effetti della nuova definizione e della definizione abilitata siano visibili ai clienti, ricreate l’indice del sito.

**Aggiunta di una definizione di Caricatore attributi**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Sulla [!DNL Stage Attribute Loader Definitions] pagina, fate clic su **[!UICONTROL Add New Attribute Loader]**.
1. Nella [!DNL Attribute Loader Add] pagina, impostate le opzioni di configurazione desiderate. Le opzioni disponibili dipendono dalla selezione **[!UICONTROL Type]** effettuata.

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
      <td colname="col2"> <p>Il nome univoco della configurazione del Caricatore attributi. È possibile utilizzare caratteri alfanumerici. Sono consentiti anche i caratteri "_" e "-". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> <p>Origine dei dati. Il tipo di origine dati selezionato influisce sulle opzioni risultanti disponibili nella pagina <span class="wintitle"> Attribute Loader Add </span> . Potete scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Testo </span> <p>File di testo semplici, delimitati da virgole, delimitati da tabulazioni o altri formati delimitati in modo coerente. Ogni riga di testo delimitata da una nuova riga corrisponde a un singolo documento e viene analizzata utilizzando il delimitatore specificato. </p> <p>Potete mappare ciascun valore, o colonna, su un campo di metadati, a cui fa riferimento il numero di colonna, a partire da 1 (uno). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Scarica un documento XML principale che contiene più "righe" di informazioni. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo origine dati: Testo</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per l’uso. In alternativa, è possibile disattivare la configurazione per impedire l'utilizzo di questa funzionalità. </p> <p> <b>Nota</b>: Le configurazioni di Caricatore attributi disattivate vengono ignorate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo dell'host del server in cui si trovano i dati. </p> <p>Se necessario, è possibile specificare un percorso URI completo (Uniform Resource Identifier) per il documento di origine dati, come negli esempi seguenti: </p> <p> <code otherprops="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p> oppure  </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>L'URI è suddiviso nelle voci appropriate per i campi Indirizzo host, Percorso file, Protocollo e, facoltativamente, Nome utente e Password </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del semplice file di testo semplice, delimitato da virgole, delimitato da tabulazioni o di altro formato delimitato in modo coerente. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Potete scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTP. </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTPS. </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>Per accedere al server FTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>Per accedere al server SFTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> File </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Timeout </p> </td> 
      <td colname="col2"> <p>Specifica il timeout, in secondi, per le connessioni FTP, SFTP, HTTP o HTTPS. Il valore deve essere compreso tra 30 e 300. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tentativi </p> </td> 
      <td colname="col2"> <p>Specifica il numero massimo di tentativi per connessioni FTP, SFTP, HTTP o HTTPS non riuscite. Il valore deve essere compreso tra 0 e 10. </p> <p>Un valore pari a zero (0) impedisce i tentativi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Codifica </p> </td> 
      <td colname="col2"> <p>Specifica il sistema di codifica dei caratteri utilizzato nel file di origine dati specificato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimitatore </p> </td> 
      <td colname="col2"> <p>Specifica il carattere da utilizzare per delineare ogni campo nel file di origine dati specificato. </p> <p>Il carattere virgola ( <span class="codeph"> , </span>) è un esempio di carattere di delimitazione. La virgola funge da delimitatore di campo per separare i campi dati nel file di origine dati specificato. </p> <p>Selezionare <span class="uicontrol"> Tab? </span> per utilizzare il carattere di delimitazione della tabulazione orizzontale. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Intestazioni nella prima riga </p> </td> 
      <td colname="col2"> <p>Indica che la prima riga del file di origine dati contiene solo informazioni di intestazione, non dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Giorni obsoleti </p> </td> 
      <td colname="col2"> <p>Imposta l'intervallo minimo tra i download dei dati del caricatore attributi. I download attivati dall'indice che si verificano entro l'intervallo di frequenza di aggiornamento del download vengono ignorati. Se si imposta questo valore sul valore predefinito 1, i dati del Caricatore attributi non vengono scaricati più di una volta entro un periodo di 24 ore. Tutti gli indici di ricerca che si verificano entro l’intervallo di frequenza di aggiornamento del download utilizzano l’ultimo set di dati scaricato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Specifica le mappature tra colonne e metadati utilizzando i numeri di colonna. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Colonna </span> <p> Specifica un numero di colonna, con la prima colonna pari a 1 (una). Per aggiungere nuove righe di mappa per ciascuna colonna, in <span class="wintitle"> Azione </span>fare clic su <span class="uicontrol"> + </span>. </p> <p>Non è necessario fare riferimento a ogni colonna nell'origine dati. È invece possibile scegliere di saltare i valori. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag &lt;meta&gt; generato. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che <span class="uicontrol"> Field diventi </span> un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l'account corrente. </p> <p>Se necessario, il valore <span class="uicontrol"> Campo </span> può essere un campo di metadati non definito. Talvolta, un campo di metadati non definito è utile per creare il contenuto utilizzato da uno script di <span class="wintitle"> filtro </span>. </p> <p>Vedere <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni Sul Filtro Degli Script </a>. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Chiave primaria? </span> <p>Solo un campo è identificato come chiave primaria. Questo campo verrà utilizzato come "chiave esterna" per corrispondere ai dati del Caricatore attributi con il documento corrispondente nell'indice. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> Rimuovere il codice HTML? </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo origine dati: Feed</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per l’uso. In alternativa, è possibile disattivare la configurazione per impedire l'utilizzo di questa funzionalità. </p> <p> <b>Nota</b>: Le configurazioni di Caricatore attributi disattivate vengono ignorate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo dell'host del server in cui si trovano i dati. </p> <p>Se necessario, è possibile specificare un percorso URI completo (Uniform Resource Identifier) per il documento di origine dati, come negli esempi seguenti: </p> <p> <code class="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p> oppure  </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>L'URI è suddiviso nelle voci appropriate per i campi Indirizzo host, Percorso file, Protocollo e, facoltativamente, Nome utente e Password. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML principale che contiene più "righe" di informazioni. </p> <p>Il percorso è relativo alla radice dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Potete scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTP. </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>Se necessario, potete immettere le credenziali di autenticazione corrette per accedere al server HTTPS. </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>Per accedere al server FTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>Per accedere al server SFTP è necessario immettere le credenziali di autenticazione corrette. </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> File </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Identifica l'elemento XML che è possibile utilizzare per identificare singole righe XML nel file di origine dati specificato. </p> <p>Ad esempio, nel seguente frammento Feed di un documento XML di un Adobe , il valore del tag elemento è <span class="codeph"> record </span>: </p> <p> <code class="syntax xml"> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; 
        &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
        &lt;/record&gt; 
        ... 
        &lt;record&gt; 
        ... 
        &lt;/record&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/group&gt; 
        &lt;/gsafeed&gt; 
        </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome campo di riferimento incrociato </p> </td> 
      <td colname="col2"> <p>Specifica un campo di metadati i cui valori vengono utilizzati come "chiavi" di ricerca nei dati della configurazione del caricatore di attributi. Se non è selezionato alcun valore (<b>—Nessuno—</b>), i dati di questa configurazione non sono disponibili per l'uso nei calcoli di classificazione (<b>Regole</b> &gt; Regole di <b>classificazione</b> &gt; <b>Modifica regole</b>). Quando si seleziona un valore, i valori di questo campo vengono utilizzati per fare riferimento incrociato ai documenti di ricerca e merchandising del sito con i dati di questa configurazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Giorni obsoleti </p> </td> 
      <td colname="col2"> <p>Imposta l'intervallo minimo tra i download dei dati del caricatore attributi. I download attivati dall'indice che si verificano entro l'intervallo di frequenza di aggiornamento del download vengono ignorati. Se si imposta questo valore sul valore predefinito 1, i dati del Caricatore attributi non vengono scaricati più di una volta entro un periodo di 24 ore. Tutti gli indici di ricerca che si verificano entro l’intervallo di frequenza di aggiornamento del download utilizzano l’ultimo set di dati scaricato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Consente di specificare le mappature XML da elemento a metadati utilizzando le espressioni XPath. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tag </span> <p>Specifica una rappresentazione XPath dei dati XML analizzati. Utilizzando l'esempio  documento XML dell'Adobe precedente, sotto l'opzione Tag elemento, è possibile mappare il file utilizzando la seguente sintassi: </p> <p> <code class="syntax xml"> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>La sintassi di cui sopra è la seguente: </p> <p> 
        <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
        <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code class="syntax xml"> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>L' <span class="codeph"> attributo displayurl </span> dell'elemento del <span class="codeph"> record viene mappato sul campo di metadati </span> page-url <span class="codeph"> </span>. </p> </li> 
        <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code class="syntax xml"> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi <span class="codeph"> </span> elemento meta contenuto all'interno di un elemento <span class="codeph"> metadati, contenuto all'interno di un elemento </span> record, il cui attributo name è <span class="codeph"> title </span> <span class="codeph"> </span><span class="codeph"> </span>, viene mappato sul titolo del campo di metadati, in modo da poter essere mappato sull'attributo del campo di metadati . </p> </li> 
        <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>L'attributo <span class="codeph"> di contenuto </span> di qualsiasi <span class="codeph"> </span> elemento meta contenuto all'interno di un elemento <span class="codeph"> metadati, contenuto all'interno dell'elemento </span> record, il cui attributo nome è <span class="codeph"> descrizione </span> <span class="codeph"> </span><span class="codeph"> </span>, viene mappato sul campo di metadati . </p> </li> 
        <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi <span class="codeph"> </span> elemento meta contenuto all'interno di un <span class="codeph"> elemento di </span> metadati, contenuto all'interno dell' <span class="codeph"> elemento del </span> record, il cui attributo name è <span class="codeph"> description </span><span class="codeph"> </span>, viene mappato sul corpo del campo di metadati . </p> </li> 
        </ul> </p> <p>XPath è una notazione relativamente complicata. Ulteriori informazioni sono disponibili nel seguente percorso: </p> <p>Consultate <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag <span class="codeph"> &lt;meta&gt; </span> generato. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che <span class="uicontrol"> Field diventi </span> un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l'account corrente. </p> <p>Se necessario, il valore <span class="uicontrol"> Campo </span> può essere un campo di metadati non definito. Talvolta, un campo di metadati non definito è utile per creare contenuto utilizzato da <span class="wintitle"> Filtraggio script </span>. </p> <p>Vedere <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni Sul Filtro Degli Script </a>. </p> <p>Quando Attribute Loader elabora documenti XML con più hit su qualsiasi campo mappa, i più valori vengono concatenati in un singolo valore nel documento memorizzato nella cache risultante. Per impostazione predefinita, questi valori vengono combinati mediante un delimitatore di virgola. Tuttavia, supponiamo che il valore <span class="wintitle"> Campo corrispondente </span> sia un campo di metadati definito. Inoltre, tale campo ha l'attributo <span class="wintitle"> Elenchi consentiti </span> impostato. In questo caso, il valore Delimitatori elenco del campo, che è il primo delimitatore definito, viene utilizzato nella concatenazione. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Chiave primaria? </span> <p>Solo un campo è identificato come chiave primaria. Questo campo verrà utilizzato come "chiave esterna" per corrispondere ai dati del Caricatore attributi con il documento corrispondente nell'indice. </p> </li> 
      <li id="li_80D6AF130FCE40AC972FE4B605B86BF6"> <span class="uicontrol"> Rimuovere il codice HTML? </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Fai clic **[!UICONTROL Setup Maps]** per scaricare un esempio dell’origine dati. I dati vengono esaminati per verificarne l&#39;idoneità.
1. Fate clic **[!UICONTROL Add]** per aggiungere la configurazione alla [!DNL Attribute Loader Definitions] pagina.
1. Sulla [!DNL Attribute Loader Definitions] pagina, fate clic su **[!UICONTROL rebuild your staged site index]**.
1. (Facoltativo) Nella [!DNL Attribute Loader Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica della definizione di Caricatore attributi {#task_AA2D1B2BCAFA44A6A0C59A0318274E80}

È possibile modificare un Caricatore attributi esistente definito.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nell&#39;account dal rappresentante dell&#39;account  Adobe o dal supporto  Adobe.

Non tutte le opzioni di caricamento attributi possono essere modificate, ad esempio Nome o Tipo del caricatore attributi, dall&#39;elenco a [!DNL Type] discesa.

**Per modificare la definizione di Caricatore attributi**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella [!DNL Attribute Loader] pagina, sotto l&#39;intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Edit]** per specificare il nome di una definizione di Caricatore attributi di cui si desidera modificare le impostazioni.
1. Nella [!DNL Attribute Loader Edit] pagina, impostate le opzioni desiderate.

   Vedere la tabella delle opzioni in [Aggiunta di una definizione](../c-about-settings-menu/c-about-metadata-menu.md#task_A735E5EF763343A9B675E1A3B09AFDBC)di Caricatore attributi.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella [!DNL Attribute Loader Definitions] pagina, fare clic su **[!UICONTROL rebuild your staged site index]**.
1. (Facoltativo) Nella [!DNL Attribute Loader Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Copia della definizione di Caricatore attributi {#task_9B40D5ECFC81411E9480F62A0FD5F2E0}

È possibile copiare una definizione di Caricatore attributi esistente da utilizzare come base per la creazione di un nuovo Caricatore attributi.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nell&#39;account dal rappresentante dell&#39;account  Adobe o dal supporto  Adobe.

Durante la copia della definizione di Caricatore attributi, la definizione copiata è disabilitata per impostazione predefinita. Per abilitare o &quot;attivare&quot; la definizione, è necessario modificarla dalla [!DNL Attribute Loader Edit] pagina e selezionare **[!UICONTROL Enable]**.

Vedere [Modifica della definizione](../c-about-settings-menu/c-about-metadata-menu.md#task_AA2D1B2BCAFA44A6A0C59A0318274E80)di Caricatore attributi.

**Per copiare una definizione di Caricatore attributi**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella [!DNL Attribute Loader] pagina, sotto l&#39;intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Copy]** per specificare il nome di una definizione di Caricatore attributi di cui si desidera duplicare le impostazioni.
1. Nella [!DNL Attribute Loader Copy] pagina, immettete il nuovo nome della definizione.
1. Clic **[!UICONTROL Copy]**.
1. (Facoltativo) Nella [!DNL Attribute Loader Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Ridenominazione di una definizione di Caricatore attributi {#task_58D5DFD7EBC04111BCB91118E4440DB4}

È possibile modificare il nome di una definizione di Caricatore attributi esistente.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nell&#39;account dal rappresentante dell&#39;account  Adobe o dal supporto  Adobe.

**Per rinominare una definizione di Caricatore attributi**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella [!DNL Attribute Loader] pagina, sotto l&#39;intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Rename]** per il nome della definizione del caricatore attributi che si desidera modificare.
1. Nella [!DNL Attribute Loader Rename] pagina, immettere il nuovo nome della definizione nel [!DNL Name] campo.
1. Clic **[!UICONTROL Rename]**.
1. (Facoltativo) Nella [!DNL Attribute Loader Definitions] pagina, effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Caricamento dei dati del caricatore attributi {#task_2F3C55189B0A4049AB2113F2291CC181}

È possibile scaricare i dati configurati di caricamento attributi in ricerca/merchandising del sito.

La [!DNL Data Load] pagina mostra le seguenti informazioni sullo stato dell&#39;ultima operazione di caricamento dati del caricatore di attributi:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo di stato </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Stato </p> </td> 
   <td colname="col2"> <p>Indica l'esito positivo o negativo dell'ultimo tentativo di caricamento dei dati. Oppure, visualizza lo stato di un'operazione di caricamento dati già in corso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora di inizio </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l'ora di inizio dell'ultima operazione di caricamento dei dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora di interruzione </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l'ora di completamento dell'ultima operazione di caricamento dei dati. Oppure indica che l'operazione di caricamento dei dati corrente è ancora in corso. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per caricare i dati del caricamento attributi**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Sulla [!DNL Attribute Loader Definitions] pagina, fate clic su **[!UICONTROL Load Attribute Loader Data]**.
1. Nella **[!UICONTROL Attribute Loader Data Load]** pagina, effettuate una delle seguenti operazioni:

   * Fare clic **[!UICONTROL Start Load]** per avviare l&#39;operazione di caricamento.

      Durante un&#39;operazione di caricamento dei dati,**la riga Progress** fornisce informazioni sull&#39;avanzamento.

   * Fare clic **[!UICONTROL Stop Load]** per arrestare l&#39;operazione di caricamento.

1. Fate clic **[!UICONTROL Close]** per tornare alla [!DNL Attribute Loader Definitions] pagina.

## Anteprima dei dati di caricamento attributi {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

È possibile utilizzare Anteprima per visualizzare i dati del Caricatore attributi caricato più di recente.

La colonna Riga della tabella mostra il numero per ogni riga di dati, indicando l&#39;ordine originale in cui sono stati caricati i valori di Caricatore attributi.

Le colonne rimanenti mostrano i valori associati a ciascuna voce.

Se la tabella è vuota, significa che non sono ancora stati caricati dati del Caricatore attributi. È possibile chiudere la [!DNL Attribute Loader Data Preview] pagina e quindi caricare i dati del Caricatore attributi.

Vedere [Caricamento dei dati](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)del caricatore di attributi.

**Visualizzazione in anteprima dei dati del caricamento attributi**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella [!DNL Attribute Loader Definitions] pagina, sotto la [!DNL Actions] colonna, fare clic **[!UICONTROL Preview]** per la configurazione di cui si desidera visualizzare i dati scaricati.
1. Nella [!DNL Attribute Loader Data Preview] pagina, utilizzate le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare i dati.

   Fai clic sull’intestazione di una colonna nella tabella per ordinare i dati in ordine crescente o decrescente.
1. Effettuate una delle seguenti operazioni:

   * Fare clic **[!UICONTROL Download to Desktop]** per scaricare e salvare la tabella come file .xlt.
   * Chiudi la pagina al termine della visualizzazione dell&#39;anteprima dei dati del caricatore attributi e torna alla pagina visualizzata in precedenza.

## Visualizzazione delle impostazioni di una definizione di Caricatore attributi {#task_EA99A9694FE948ADA82C1DBA0667851B}

È possibile esaminare le impostazioni di configurazione di una definizione di Caricatore attributi esistente.

Dopo aver aggiunto alla [!DNL Attribute Loader Definitions] pagina la definizione di Caricatore attributi, non è possibile modificarne l&#39;impostazione Tipo. Al contrario, è necessario eliminare la definizione e aggiungerne una nuova.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nell&#39;account dal rappresentante dell&#39;account  Adobe o dal supporto  Adobe.

**Per visualizzare le impostazioni di una definizione di Caricatore attributi**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella [!DNL Attribute Loader] pagina, sotto l&#39;intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Edit]** per specificare il nome di una definizione di Caricatore attributi di cui si desidera esaminare o modificare le impostazioni.

## Visualizzazione del registro dall&#39;ultimo caricamento di dati del Caricatore attributi {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

È possibile utilizzare [!DNL View Log] per esaminare il file di registro dei dati di caricamento attributi del processo di download più recente. Potete inoltre utilizzare la visualizzazione del registro per monitorare un download in esecuzione.

Vedere [Caricamento dei dati](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)del caricatore di attributi.

**Per visualizzare il registro dal caricamento dati Caricatore attributi più recente**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Sulla [!DNL Attribute Loader Definitions] pagina, fate clic su **[!UICONTROL View Log]**. Pagina di registro,
1. Nella [!DNL Attribute Loader Data Log] pagina, utilizzate le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare le informazioni di registro.
1. Al termine, chiudete la pagina per tornare alla [!DNL Attribute Loader Definitions] pagina.

## Eliminazione di una definizione di Caricatore attributi {#task_E8980F66888B476E98C228C1D307EDF8}

È possibile eliminare una definizione Caricatore attributi esistente che non è più necessaria o che non è più utilizzata.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nell&#39;account dal rappresentante dell&#39;account  Adobe o dal supporto  Adobe.

**Per eliminare una definizione di Caricatore attributi**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella [!DNL Attribute Loader Definitions] pagina, sotto l&#39;intestazione della [!DNL Actions] colonna, fare clic **[!UICONTROL Delete]** per il nome della definizione del caricatore attributi che si desidera rimuovere.
1. Sulla [!DNL Attribute Loader Delete] pagina, fate clic su **[!UICONTROL Delete]**.
