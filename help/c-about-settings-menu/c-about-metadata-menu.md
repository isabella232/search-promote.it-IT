---
description: Utilizza il menu Metadati per personalizzare le definizioni di ricerca e le iniezioni di indice.
solution: Target
subtopic: Metadata
title: Informazioni sul menu Metadati
topic: Settings,Site search and merchandising
uuid: f12fc863-a140-45e8-b219-3dbfdef099cd
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '8029'
ht-degree: 1%

---


# Informazioni sul menu Metadati{#about-the-metadata-menu}

Utilizza il menu Metadati per personalizzare le definizioni di ricerca e le iniezioni di indice.

## Informazioni sulle definizioni {#concept_AE48035C210145169BE067D396975620}

È possibile utilizzare [!DNL Definitions] per personalizzare il contenuto e la pertinenza dei campi HTML e metadati che vengono presi in considerazione quando un cliente invia una query di ricerca.

Puoi modificare i campi già predefiniti. In alternativa, puoi creare nuovi campi definiti dall’utente in base al contenuto dei tag dei metadati. Ogni definizione viene visualizzata su una singola riga nella pagina [!DNL Staged Definitions].

Vedere anche [Informazioni sulle visualizzazioni dati](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3).

## Aggiunta di un nuovo campo meta tag {#task_6DF188C0FC7F4831A4444CA9AFA615E5}

Puoi definire e aggiungere campi di tag per metadati personalizzati.

Prima che gli effetti della nuova definizione del tag meta siano visibili ai clienti, è necessario ricostruire l&#39;indice del sito.

**Per aggiungere un nuovo campo meta tag**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Nella pagina [!DNL Definitions], fai clic su **[!UICONTROL Add New Field]**.
1. Nella pagina [!DNL Add Field] , imposta le opzioni desiderate.

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
      <li id="li_7FC340E7C58545C88CE9AF4AF09AD7AD"> Il nome contiene i trattini, ma non spazi. </li> 
      <li id="li_996FF38457AB4C6DB22B15850A0830CC"> È possibile immettere un nome lungo fino a 20 caratteri. </li> 
      <li id="li_C1019E587995444D9587D5EA495D719E"> Il nome non fa distinzione tra maiuscole e minuscole, ma viene visualizzato e memorizzato esattamente come viene digitato. </li> 
      <li id="li_E55404D6CE354EC89CFFEB1048A11F44"> Non è possibile utilizzare i nomi esistenti nei campi predefiniti come mostrato nella tabella nella pagina <span class="wintitle"> Definizioni di staging </span> . </li> 
      <li id="li_7CE328AE3B5F45A8A09E2DA7ECB62551"> Non è possibile utilizzare la parola "any" come valore di un nome di campo definito dall’utente. </li> 
      <li id="li_9B8287EED1784E79BFCBBBA956705CD2"> Non è possibile modificare i nomi dei campi predefiniti. </li> 
      </ul> </p> <p> Esempi di nomi di campo: </p> <p> 
      <ul id="ul_5881669913D04E35A6D4A6D31BEE7DF3"> 
        <li id="li_0AFFB8B516FE40F8A615C2F578F2CEA3"> autore </li> 
        <li id="li_7F0ADFBFB21E4B84ACA8A1CEBFE344D1"> PublishDate </li> 
        <li id="li_6D1BEB3D19AC499E9227EC115AEB6296"> qualcosa di selvaggio </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome/i del tag Meta </p> </td> 
      <td colname="col2"> <p>Determina il contenuto associato al campo definito. </p> <p>L'elenco dei nomi può contenere fino a 255 caratteri. Inoltre, il nome può contenere qualsiasi carattere consentito nell'attributo name di un tag meta HTML. </p> <p>È possibile specificare più meta tag in una singola definizione di campo. </p> <p>I valori multipli devono essere separati da virgole e il nome del tag meta più a sinistra trovato in una determinata pagina web ha la precedenza. </p> <p>Ad esempio, supponi di aver definito un campo denominato "auth". Il nome del campo ha i meta tag associati "author, dc.author". In questo caso, il contenuto del tag meta "autore" viene indicizzato e cercato in quello di "dc.author" se entrambi i meta tag compaiono in una pagina web. </p> <p>I campi definiti dall'utente devono avere almeno un nome di tag meta nella loro definizione. I campi predefiniti non devono avere un tag meta associato. Tuttavia, se sono specificati uno o più meta tag, il contenuto dei meta tag sostituisce l’origine dati corrente per ciascun tag. </p> <p>Ad esempio, se il tag meta "dc.title" è associato al campo "title" predefinito, il contenuto del tag meta "dc.title" viene indicizzato su quello del tag 
      Tag <code>
        &lt;title&gt; 
      </code> per qualsiasi documento specifico. </p> <p>Gli esempi includono: </p> <p> 
      <ul id="ul_0132E15FC19E4C0CA13CD5A12EA3BBEC"> 
      <li id="li_ECD3B194FECB4C2090CAEC8449320D3F"> dc.date </li> 
      <li id="li_09C76BC7AC7348859D01989697212E31"> descrizione </li> 
      <li id="li_9230C0450F9D424087D1F127048DA311"> proprietario </li> 
      </ul> </p> </td> 
    </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo di dati </p> </td> 
      <td colname="col2"> <p>A ogni campo è associato un tipo di dati, ad esempio testo, numero, data, versione, classificazione o posizione. Questo tipo di dati determina il modo in cui il contenuto del campo viene indicizzato, cercato ed eventualmente ordinato. </p> <p>Non è possibile modificare il tipo di dati dopo aver creato la definizione del campo. </p> <p>Utilizza le seguenti informazioni per aiutarti a selezionare il tipo di dati pertinente alle informazioni contenute nel campo. </p> <p> 
      <ul id="ul_A3AD5A0CF354410F836311F39151B8A6"> 
      <li id="li_9F412DA7D9EF497BA6E65F9CE10F3046"> <span class="uicontrol"> I campi del tipo di  </span> dati di testo vengono trattati come stringhe di caratteri. </li> 
      <li id="li_AD78B75644AE40208F0239311015611F"> <span class="uicontrol"> I campi tipo  </span> dati numero sono trattati come valori numerici interi o a virgola mobile. </li> 
      <li id="li_0B46975C589148E9A7C32A8D250487B7"> <span class="uicontrol"> I campi del tipo di  </span> dati data vengono trattati come specificatori di data/ora. È possibile personalizzare i formati di data/ora consentiti quando si aggiunge o si modifica il nuovo campo. </li> 
      <li id="li_BB68CB1DBE0543AC9000B3DEDFB28E7E"> <span class="uicontrol"> I campi del tipo di  </span> dati della versione vengono trattati come dati numerici in formato libero. Ad esempio, 1.2.3 ordina prima di 1.2.2. </li> 
      <li id="li_0BA895B4DADA46528A7A4161EEB1521E"> <span class="uicontrol"> I campi  </span> del tipo di dati classificato vengono trattati allo stesso modo dei campi del tipo "Numero", tranne per il fatto che influenzano anche i calcoli di classificazione/rilevanza nei risultati della ricerca. <p>Consulta <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" type="concept" format="dita" scope="local"> Informazioni sulle regole di classificazione </a>. </p> </li> 
      <li id="li_459405DA437049AD88AA1FAC28F04720"> <span class="uicontrol"> I campi del tipo di  </span> dati della posizione vengono trattati come una posizione fisica in qualsiasi parte del mondo. I formati di posizione consentiti includono: <p> 
      <ul id="ul_D2CEBFA1A5504AA996BA2F7641AFB7F3"> 
      <li id="li_5283A2F2D5D84840B3D920C08D43654C"> Codici ZIP a 5 o 9 cifre sotto forma di DDDD o DDDD-DDD, dove ogni "D" è a 0-9 cifre. </li> 
      <li id="li_A5CD4DFC90164BC68183DB7D10603B7C"> Codici di area a tre cifre sotto forma di DDD. </li> 
      <li id="li_9DAEAE64BC7F4902B25043D998C8F56D"> Coppie di latitudine/longitudine nella forma ±DD.DDDD±DDD.DDD, dove il primo numero specifica la latitudine e il secondo numero specifica la longitudine. </li> 
      </ul> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>elenchi consentiti </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato il tipo di dati <span class="uicontrol"> Testo </span> o <span class="uicontrol"> Numero </span> . </p> <p>Indice separato dei valori delimitati nel contenuto dei metadati di questo campo. </p> <p>Ad esempio, il contenuto "Rosso, Giallo, Verde, Blu" viene trattato come quattro valori separati invece di uno quando si seleziona "Elenchi consentiti". Questo trattamento è più utile con la ricerca di intervallo (utilizzando 
      <code>
        sp_q_min 
      </code> 
      <code>
        sp_q_max 
      </code> oppure 
      <code>
        sp_q_exact 
      </code>) e con il 
      <code>
        &lt;search-field-value-list&gt; 
      </code> 
      <code>
        &lt;search-field-values&gt; 
      </code> e 
      <code>
        &lt;search-display-field-values&gt; 
      </code>. </p> <p>Non disponibile se è selezionato il tipo di dati Versione . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Facet dinamico </p> </td> 
      <td colname="col2"> <p> 
        <!--NEW 2/2/2014--> <p>Nota:  Questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivarlo per il tuo utilizzo. Dopo l'attivazione, viene visualizzato nell'interfaccia utente. </p> </p> <p>Imposta il facet identificato come dinamico. </p> <p>I facet sono costruiti sopra i campi meta tag. Un campo meta tag è un livello di ricerca di base basso di Adobe Search&amp;Promote. I facet, d'altro canto, fanno parte di GS (Guided Search) - lo strato di presentazione di alto livello del Search&amp;Promote Adobe. I facet possiedono campi meta tag, tuttavia, i campi meta tag non sanno nulla dei facet. </p> <p>Consulta <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Informazioni sui facet dinamici </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Consenti deduplicazione </p> </td> 
      <td colname="col2"> <p>Seleziona questa opzione per abilitare la deduplicazione per questo campo. In altre parole, consente di specificare questo campo in fase di ricerca tramite 
        <code>
          sp_dedupe_field 
        </code> Cerca il parametro CGI. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Ricerca parametri CGI </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome tabella </p> </td> 
      <td colname="col2"> <p>Associa in modo permanente il campo specificato al nome della tabella specificato. </p> <p>Ogni volta che un tale campo viene menzionato in un parametro CGI di ricerca di base o in un tag modello, il nome della tabella viene fornito automaticamente. Questa funzione consente di selezionare i facet dinamici attraverso le corrispondenze delle tabelle, ma può essere utilizzata anche per i campi dei facet non dinamici, se necessario. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimitatori elenco </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Elenchi consentiti </span>. </p> <p>Specifica quali caratteri separano i singoli valori dell'elenco. È possibile specificare più caratteri, ciascuno dei quali è trattato come separatore di valore. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ricerca per impostazione predefinita </p> </td> 
      <td colname="col2"> <p>Quando è selezionata questa opzione, la ricerca viene eseguita anche quando il campo non è specificato in modo esplicito in una determinata query di ricerca. Se deselezioni questa opzione, la ricerca nel campo viene eseguita solo quando richiesto. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Campo aggiornamento verticale </p> </td> 
      <td colname="col2"> <p> <p>Nota:  Questa funzione non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivarlo per il tuo utilizzo. Dopo l'attivazione, viene visualizzato nell'interfaccia utente. </p> </p> <p>Imposta il campo identificato come campo Aggiornamento verticale. </p> <p>I campi Aggiornamento verticale sono candidati per essere aggiornati tramite il processo di aggiornamento verticale ( <span class="uicontrol"> Indice </span> &gt; <span class="uicontrol"> Aggiornamento verticale </span>). A causa del modo in cui vengono effettuati gli Aggiornamenti verticali, la ricerca del contenuto di questi campi non può essere eseguita in ricerche in testo libero. Selezionando questa opzione il contenuto di questo campo non viene aggiunto all'indice "word" durante qualsiasi tipo di operazione di indicizzazione. Consente inoltre l'aggiornamento di questo campo durante un'operazione di aggiornamento verticale. </p> <p>Per ulteriori informazioni sugli aggiornamenti verticali, vedere <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Informazioni sull'aggiornamento verticale </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rilevanza </p> </td> 
      <td colname="col2"> <p>Puoi modificare la pertinenza dei campi predefiniti e definiti dall’utente. </p> <p>La pertinenza è specificata in una scala da 1 a 10. Un’impostazione pari a 1 significa che è la meno rilevante e 10 la più pertinente. Questi valori vengono presi in considerazione quando il software considera le corrispondenze della query in ciascun campo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ordinamento </p> </td> 
      <td colname="col2"> <p>Specifica quando i risultati vengono ordinati in base al campo denominato, tramite 
        <code>
          sp_s 
        </code> Cerca il parametro CGI. </p> <p>Consulta <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Ricerca parametri CGI </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lingua </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato il tipo di dati <span class="uicontrol"> Classifica </span>, <span class="uicontrol"> Numero </span> o <span class="uicontrol"> Data </span>. </p> <p>Controlla le convenzioni della lingua e delle impostazioni internazionali applicate durante l'indicizzazione dei valori di data, numero e classificazione per questo campo. </p> <p>Puoi scegliere di applicare la lingua dell’account (Linguistica &gt; Parole e lingue). In alternativa, è possibile applicare la lingua associata al documento contenente ogni numero o valore di data o una lingua specifica. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formato/i </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato il tipo di dati <span class="uicontrol"> Data </span> . </p> <p>Controlla i formati di data riconosciuti durante l'indicizzazione dei valori di data per questo campo. </p> <p>Per ogni campo data viene fornito un elenco predefinito di stringhe di formato data. È possibile aggiungere all’elenco o modificare l’elenco in base alle esigenze del sito. </p> <p>Vedere <a href="../c-appendices/r-date-formats.md#reference_4D1FC1F6B9F44857967188496D8D335B" type="reference" format="dita" scope="local"> Formati di data </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formati di data del test </p> </td> 
      <td colname="col2"> <p>Disponibile solo se come tipo di dati è selezionato il tipo di dati <span class="uicontrol"> Data </span> . </p> <p>Consente di visualizzare in anteprima i formati di data specificati per assicurarti che siano formattati correttamente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fuso orario </p> </td> 
      <td colname="col2"> <p>Disponibile solo se come tipo di dati è selezionato il tipo di dati <span class="uicontrol"> Data </span> . </p> <p>Controlla il fuso orario presunto applicato durante l'indicizzazione dei valori di data per questo campo che non specificano un fuso orario. </p> <p>Ad esempio, se il tuo fuso orario dell'account è impostato su "America/Los Angeles" e selezioni <span class="uicontrol"> Usa fuso orario dell'account </span>, il seguente valore della data del metadati, che non ha un fuso orario specificato, viene trattato come se si trattasse dell'ora del Pacifico, tenendo conto dei risparmi della luce del giorno: </p> <p>&lt;meta name="dc.date" content="Mon, 05 Sep 201213:12:00"&gt; </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore nominale meno importante </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Classifica </span> è selezionato come Tipo di dati. </p> <p>Controlla il valore di classificazione che rappresenta il livello minimo di qualsiasi documento. </p> <p>Se le classificazioni del documento sono comprese tra 0 per il rango più basso e 10 per il rango più alto, impostare questo valore su 0. </p> <p>Se le classificazioni del documento sono comprese tra 1 per il rango più alto e 10 per il rango più basso, impostare questo valore su 10. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore nominale predefinito </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Classifica </span> è selezionato come Tipo di dati. </p> <p>Controlla il valore di classificazione utilizzato se un documento non contiene tag meta definiti per questo campo di classificazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valore di classifica più importante </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Classifica </span> è selezionato come Tipo di dati. </p> <p>Controlla il valore di classificazione che rappresenta il livello massimo di qualsiasi documento. </p> <p>Se le classificazioni del documento sono comprese tra 0 per il rango più basso e 10 per il rango più alto, impostare questo valore su 10. </p> <p>Se le classificazioni del documento sono comprese tra 1 per il rango più alto e 10 per il rango più basso, impostare questo valore su 1. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Unità predefinite </p> </td> 
      <td colname="col2"> <p>Disponibile solo se il tipo di dati <span class="uicontrol"> Posizione </span> è selezionato come Tipo di dati. </p> <p>Controlla il trattamento dei valori di distanza per le ricerche di prossimità. </p> <p>Se le unità predefinite vengono impostate su <span class="uicontrol"> Miglia </span>, qualsiasi criterio di ricerca di prossimità relativo alla distanza minima/massima applicata a questo campo (tramite 
      <code>
        sp_q_min[_#] 
      </code> o 
      <code>
        sp_q_max[_#] 
      </code> Ricerca parametri CGI) è trattato come miglia, altrimenti come chilometri. </p> <p>Questa opzione controlla anche le unità di distanza predefinite applicate all'output del 
      <code>
        &lt;Search-Display-Field&gt; 
      </code> tag modello risultati ricerca applicato a un campo di output ricerca prossimità. </p> <p>Consultare <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Informazioni sulla ricerca di prossimità </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Crea descrizione intervallo? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se come tipo di dati è selezionato <span class="uicontrol"> Numero </span> . </p> <p>Controlla la creazione automatica delle descrizioni dell’intervallo di campi, da utilizzare con <span class="uicontrol"> Progettazione </span> &gt; <span class="uicontrol"> Navigazione </span> &gt; <span class="uicontrol"> Facet </span>. </p> <p>Consulta <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" format="dita" scope="local"> Informazioni sui facet </a>. </p> <p> <p>Nota:  Se questo campo è selezionato <span class="uicontrol"> Campo di aggiornamento verticale </span>, il campo di descrizione dell’intervallo di campi generato viene aggiornato durante un aggiornamento verticale. Tuttavia, si consiglia anche che il campo identificato in <span class="uicontrol"> Campo intervallo </span> abbia selezionato <span class="uicontrol"> Campo aggiornamento verticale </span> . </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Campo intervallo </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> . </p> <p>Il campo <span class="uicontrol"> Testo </span> da aggiornare con le descrizioni dell’intervallo per il campo corrente. Questo elenco contiene tutti i campi <span class="uicontrol"> Testo </span> che non sono già in uso con altri campi per la generazione dell’intervallo di campi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valori intervallo </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> e se è selezionato un elemento <span class="uicontrol"> Campo intervallo </span> . </p> <p>Elenco di punti dati delimitati da spazi vuoti da utilizzare per la creazione delle descrizioni dell’intervallo di campi. Ad esempio: </p> <code> 10&amp;nbsp;20&amp;nbsp;50&amp;nbsp;100&amp;nbsp;1000 </code> <p>Puoi immettere questi valori in qualsiasi ordine. I valori vengono ordinati e i duplicati vengono rimossi prima di essere salvati. È inoltre possibile specificare valori negativi e non interi. </p> <p>Per ciascuno dei valori di questo campo: 
      <ul id="ul_C4B41AF5AADF4B84B9C489CE82FF7075"> 
      <li id="li_90736394A5AE4F5CA6B47687BCB627AA">se il valore è minore di (&lt;) il valore più piccolo in <span class="uicontrol"> Valori intervallo </span>, viene utilizzato il formato <span class="uicontrol"> "Less Than" </span> </li> 
      <li id="li_A5C272B2D26A468CA07EB2046B2EA8A7">se il valore è maggiore o uguale a (&gt;=) il valore più grande in <span class="uicontrol"> Valori intervallo </span>, viene utilizzato il formato <span class="uicontrol"> "Maggiore di" </span>. </li> 
      <li id="li_9DDFB70E1E824CF4819C57450C1A6DD2">in caso contrario, viene trovato un "intervallo" in cui il valore del campo rientra tra due valori di intervallo consecutivi <span class="uicontrol"> </span> (maggiore di (&gt;) il valore minore e minore o uguale a (&lt;=) il valore maggiore) e viene utilizzato il <span class="uicontrol"> formato intermedio </span>. </li> 
    </ul> </p> <p>Ad esempio, il set di valori di esempio riportato sopra definirà un set di descrizioni per i valori: 
    <ul id="ul_03ED30D5A19346AB8E6809BDD186A9A9"> 
      <li id="li_F97A6B3763954EFE9B6751F472AF7D20">inferiore a 10 </li> 
      <li id="li_12B6F636A6444B8292E0BFE4F55032DF">maggiore o uguale a 10 e inferiore a 20 </li> 
      <li id="li_545A2EAF5BD046B5AD59B77DB43DCD14">maggiore o uguale a 20 e inferiore a 50 </li> 
      <li id="li_26A8CD2422524D2CBD36794C6908572A">maggiore o uguale a 50 e inferiore a 100 </li> 
      <li id="li_05EBEEE68DC348E0821F1CC16D04D69C">maggiore o uguale a 100 e inferiore a 10000 </li> 
      <li id="li_9513A6B519394780A6A41B80762A0370">greater than or equal to 10000 </li> 
      </ul> </p> <p>Consulta <span class="uicontrol"> Test using Greater Than? </span> per modificare le modalità di esecuzione dei test. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formato "Minore di" </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> e se è selezionato un elemento <span class="uicontrol"> Campo intervallo </span> . </p> <p>Questo è il modello utilizzato per specificare la descrizione dell'intervallo per i valori inferiori al valore più piccolo trovato in <span class="uicontrol"> Valori intervallo </span>. Il valore più piccolo sarà rappresentato utilizzando il token segnaposto numerico <span class="uicontrol"> ~N~ </span>. Ad esempio: </p> <code> Less&amp;nbsp;than&amp;nbsp;~N~ </code> <p>o: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;below </code> <p>Normalmente, il valore sarà formattato "così com'è" - cioè per una <span class="uicontrol"> Valori di intervallo </span> definizione di "5 10 20" e un valore fornito di 1, la descrizione dell'intervallo generato sarebbe semplicemente qualcosa come "Minore di 5". Se invece desideri che sia "4.99 e inferiore", imposta <span class="uicontrol"> Precisione </span> su <span class="uicontrol"> 2 </span> e utilizza questo formato: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;below </code> <p>In <span class="uicontrol"> "Less Than" Format </span>, le lettere minuscole <span class="uicontrol"> ~n~ </span> causeranno l'arrotondamento del valore <i>down</i> in base all'impostazione <span class="uicontrol"> Precisione </span>. </p> <p>Nota: per includere un segnaposto numerico nella descrizione dell’intervallo, così come è, specifica con un prefisso barra rovesciata (\) - ad esempio <span class="uicontrol"> \~N~ </span> o <span class="uicontrol"> \~n~ </span>. Per includere un carattere barra rovesciata, specificalo con un’altra barra rovesciata, ad esempio <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formato intermedio </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> e se è selezionato un elemento <span class="uicontrol"> Campo intervallo </span> . </p> <p>Questo è il modello utilizzato per specificare la descrizione dell'intervallo per i valori che si trovano tra i valori più piccoli e quelli più grandi che si trovano in <span class="uicontrol"> Valori intervallo </span>. Per l’intervallo specificato, il valore dell’intervallo inferiore sarà rappresentato utilizzando il token segnaposto numerico <span class="uicontrol"> ~L~ </span> e il valore dell’intervallo superiore sarà rappresentato utilizzando il token <span class="uicontrol"> ~H~ </span>. Ad esempio: </p> <code> ~L~&amp;nbsp;to&amp;nbsp;~H~ </code> <p>o: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>o: </p> <code> Less&amp;nbsp;than&amp;nbsp;~H~&amp;nbsp;and&amp;nbsp;greater&amp;nbsp;than&amp;nbsp;~L~ </code> <p>Normalmente, i valori saranno formattati "così com'è" - cioè per una <span class="uicontrol"> Valori di intervallo </span> definizione di "5 10 20" e un valore fornito di 8, la descrizione di intervallo generata sarebbe semplicemente qualcosa come "Tra 5 e 10". Se invece desideri che sia "Tra 5 e 9.99", con il valore più alto regolato <i>verso il basso</i>, imposta <span class="uicontrol"> Precisione </span> su <span class="uicontrol"> 2 </span> e utilizza questo formato: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~h~ </code> <p>Allo stesso modo, <span class="uicontrol"> ~L~ </span> può essere sostituito con <span class="uicontrol"> ~l~ </span> per avere il valore inferiore regolato <i>verso l'alto</i>, anche in base all'impostazione <span class="uicontrol"> Precisione </span>. Ciò significa che una definizione come: </p> <code> Between&amp;nbsp;~l~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>con un valore <span class="uicontrol"> Precision </span> di <span class="uicontrol"> 2 </span> si crea "Between 5.01 and 10". </p> <p>Le lettere minuscole <span class="uicontrol"> ~l~ </span> consentono di arrotondare il valore inferiore <i>su</i> in base all'impostazione <span class="uicontrol"> Precisione </span> e le lettere minuscole <span class="uicontrol"> ~h~ </span> consentono di arrotondare il valore più alto <i>verso il basso</i>. </p> <p>Nota: per includere un segnaposto numerico nella descrizione dell’intervallo, così come è, specifica con un prefisso barra rovesciata (\) - ad esempio <span class="uicontrol"> \~L~ </span> o <span class="uicontrol"> \~h~ </span>. Per includere un carattere barra rovesciata, specificalo con un’altra barra rovesciata, ad esempio <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formato "Maggiore di" </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> e se è selezionato un elemento <span class="uicontrol"> Campo intervallo </span> . </p> <p>Questo è il modello utilizzato per specificare la descrizione dell'intervallo per i valori maggiori del valore più grande trovato in <span class="uicontrol"> Valori intervallo </span>. Il valore più grande sarà rappresentato utilizzando il token segnaposto numerico <span class="uicontrol"> ~N~ </span>. Ad esempio: </p> <code> Greater&amp;nbsp;than&amp;nbsp;~N~ </code> <p>o: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;above </code> <p>Normalmente, il valore sarà formattato "così com'è" - cioè per una <span class="uicontrol"> Valori di intervallo </span> definizione di "5 10 20" e un valore fornito di 30, la descrizione di intervallo generata sarebbe semplicemente qualcosa come "Maggiore di 20". Se invece desideri che sia "20.01 e superiore", imposta <span class="uicontrol"> Precisione </span> su <span class="uicontrol"> 2 </span> e utilizza questo formato: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;above </code> <p>In <span class="uicontrol"> Formato "Maggiore di" </span>, le lettere minuscole <span class="uicontrol"> ~n~ </span> consentono di arrotondare il valore <i>su</i> in base all'impostazione <span class="uicontrol"> Precisione </span>. </p> <p>Nota: per includere un segnaposto numerico nella descrizione dell’intervallo, così come è, specifica con un prefisso barra rovesciata (\) - ad esempio <span class="uicontrol"> \~N~ </span> o <span class="uicontrol"> \~n~ </span>. Per includere un carattere barra rovesciata, specificalo con un’altra barra rovesciata, ad esempio <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Precisione </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> e se è selezionato un elemento <span class="uicontrol"> Campo intervallo </span> . </p> <p>Un valore intero che specifica il numero di cifre a destra di un punto decimale. Questo controlla anche le operazioni di arrotondamento. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovere gli zeri iniziali? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span>, viene selezionato un elemento <span class="uicontrol"> Campo intervallo </span> e viene impostato un valore diverso da zero <span class="uicontrol"> Precisione </span>. </p> <p>È necessario visualizzare "0.50" come ".50"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Eliminare gli zeri finali? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span>, viene selezionato un elemento <span class="uicontrol"> Campo intervallo </span> e viene impostato un valore diverso da zero <span class="uicontrol"> Precisione </span>. </p> <p>Dovremmo visualizzare "10.00" come "10"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mostra migliaia di separatori? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> e se è selezionato un elemento <span class="uicontrol"> Campo intervallo </span> . </p> <p>Dovremmo visualizzare "10000" come "10.000"? Verranno utilizzati valori specifici per le impostazioni internazionali. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Regolare valori zero? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> e se è selezionato un elemento <span class="uicontrol"> Campo intervallo </span> . </p> <p>Quando vengono visualizzati valori zero arrotondati, devono essere arrotondati per eccesso o per difetto in base all'impostazione <span class="uicontrol"> Precisione </span>? ad es. display "0.01"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Prova con Maggiore di? </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> e se è selezionato un elemento <span class="uicontrol"> Campo intervallo </span> . </p> <p>Poiché ogni valore viene confrontato con i valori in <span class="uicontrol"> Valori intervallo </span>, elaborati in ordine <i><b>decrescente</b></i>, viene confrontato, per impostazione predefinita, utilizzando l'operatore Maggiore di o Uguale (&gt;=), arrestandosi una volta che il test ha esito positivo. Ciò significa che con un set di <span class="uicontrol"> Valori di intervallo </span> come "10 20 50 100 1000" il valore 100 scenderà nell’intervallo da 100 a 1000, in quanto 100 è effettivamente &gt;= 100. Se preferisci che rientri nell’intervallo da 50 a 100, seleziona questa opzione, in modo che i confronti utilizzino invece l’operatore Maggiore di (&gt;). </p> <p>Ad esempio, per ciascuno dei valori di questo campo, quando questa opzione è selezionata: 
      <ul id="ul_969621B1BD914FA5BD73ED21F8841010"> 
      <li id="li_157BEFDA7D0E44C481F4E4BC9046EF24">se il valore è minore o uguale a (&lt;=) il valore più piccolo in <span class="uicontrol"> Valori intervallo </span>, verrà utilizzato il formato <span class="uicontrol"> "Less Than" </span> </li> 
      <li id="li_737EE666CA6243A8864E17A311CF3ACC">se il valore è maggiore di (&gt;) rispetto al valore più grande in <span class="uicontrol"> Valori intervallo </span>, verrà utilizzato il formato <span class="uicontrol"> "Maggiore di" </span> </li> 
      <li id="li_353A9820F7F74CCCBB3281EC4CB48734">in caso contrario, verrà trovato un intervallo in cui il valore del campo rientra tra due valori di intervallo consecutivi <span class="uicontrol"> </span> (maggiore o uguale a (&gt;=) il valore minore e minore di (&lt;) il valore maggiore) e verrà utilizzato il formato intermedio <span class="uicontrol"> </span> </li> 
    </ul> </p> <p>e, se deselezionato: 
    <ul id="ul_945844C33C2E4D95A598C4876E15F211"> 
      <li id="li_653B6E2934574DA3B4BCEF07D0A84527">se il valore è minore di (&lt;) il valore più piccolo in <span class="uicontrol"> Valori intervallo </span>, verrà utilizzato il formato <span class="uicontrol"> "Less Than" </span> </li> 
      <li id="li_AECA6880002F40FAB1820B37237550A7">se il valore è maggiore o uguale a (&gt;=) il valore più grande in <span class="uicontrol"> Valori intervallo </span>, verrà utilizzato il formato <span class="uicontrol"> "Maggiore di" </span> </li> 
      <li id="li_ECB2DF7CA592497298E9ADC708220366">in caso contrario, verrà trovato un intervallo in cui il valore del campo rientra tra due valori di intervallo consecutivi <span class="uicontrol"> </span> (maggiore di (&gt;) il valore minore o uguale a (&lt;=) il valore maggiore) e verrà utilizzato il formato intermedio <span class="uicontrol"> </span> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è selezionato <span class="uicontrol"> Crea descrizione intervallo </span> e se è selezionato un elemento <span class="uicontrol"> Campo intervallo </span> . </p> <p>Fornisci un valore numerico di esempio e premi il pulsante <span class="uicontrol"> Test </span> per vedere come viene creato il campo Intervallo. La descrizione dell’intervallo generato verrà visualizzata nella finestra . </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Consulta anche [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Clic **[!UICONTROL Add]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di campi meta tag predefiniti o definiti dall&#39;utente {#task_0A7657B63596421BB6DB3ED44F827AB3}

È possibile modificare solo determinati campi nei tag meta predefiniti oppure tutti i campi nei tag meta definiti dall’utente.

Prima che gli effetti delle modifiche ai tag meta siano visibili ai clienti, devi ricreare l&#39;indice del sito.

**Per modificare campi meta tag predefiniti o definiti dall’utente**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Nella pagina [!DNL Definitions] della colonna [!DNL Actions] della tabella fare clic su **[!UICONTROL Edit]** nella riga del nome del campo del tag meta che si desidera modificare.
1. Nella tabella della pagina [!DNL Pinned Keyword Results Manager] fare clic su **[!UICONTROL Edit]** nella riga della parola chiave che si desidera modificare.
1. Nella pagina [!DNL Edit Field] , imposta le opzioni desiderate.

   Se hai scelto di apportare modifiche a un campo metadati predefinito, tieni presente che non tutti i campi sono modificabili.

   Vedi la tabella delle opzioni in [Aggiunta di un nuovo campo tag meta](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di un campo meta tag definito dall&#39;utente {#task_9361EF38B5E743038B6672FA6CF70FD3}

È possibile eliminare un campo meta tag definito dall’utente che non è più necessario o utilizzato.

Non è possibile eliminare i campi meta tag predefiniti. Tuttavia, è possibile modificare alcuni campi.

Consulta [Modifica di campi meta tag predefiniti o definiti dall&#39;utente](../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3).

Prima che gli effetti del tag meta di eliminazione siano visibili ai clienti, è necessario ricreare l&#39;indice del sito.

**Eliminazione di un campo meta tag definito dall’utente**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Nella sezione [!DNL User-defined fields] della tabella della pagina [!DNL Definitions] fare clic su **[!UICONTROL Delete]** nella riga del nome del campo del tag meta che si desidera rimuovere.
1. Nella finestra di dialogo Conferma, fai clic su **[!UICONTROL OK]**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle iniezioni {#concept_DA091920671948A0A893A26B3A2FAAE5}

È possibile utilizzare [!DNL Injections] per inserire contenuto nelle pagine web senza la necessità di modificare le pagine stesse.

Puoi aggiungere contenuto a campi indicizzati specifici come &quot;target&quot; o &quot;body&quot; oppure sostituire il contenuto indicizzato con nuovi valori. Ad esempio, se hai inserito nuovo contenuto nel campo del tag meta di &quot;target&quot;, queste informazioni vengono trattate come se fossero contenuti codificati a livello di pagina. Puoi modificare il contenuto di qualsiasi campo metadati predefinito, indipendentemente dal fatto che le pagine del sito abbiano o meno il contenuto corrispondente. Ad esempio, puoi modificare il contenuto dei seguenti nomi di campi di tag meta predefiniti:

* Alt
* corpo
* charset
* date
* desc
* chiavi
* language
* target
* title
* url

## Utilizzo delle iniezioni dei campi di test {#section_74939EA9E6EA4D2A92E8066B3B11CF92}

Facoltativamente, puoi utilizzare **[!UICONTROL Test]** nella pagina [!DNL Staged Injections]. Immetti un nome di campo di prova (ad esempio, &quot;title&quot; o &quot;body&quot;), il valore di campo originale (ad esempio, &quot;Home page&quot;) e un URL di test dal tuo sito web. Il valore risultante viene visualizzato come riferimento. I valori correnti non vengono modificati durante la prova.

## Utilizzo delle definizioni di iniezione dei campi {#section_C1BBF19DE8EF4A6F8CC3ED691F3953A9}

Le definizioni di iniezione presentano la seguente forma:

```
append|replace field [regexp] URL value
```

I valori `append|replace`, `field`, `URL`. e le voci `value` sono obbligatorie. Immettere una definizione di iniezione per riga. L&#39;esempio seguente contiene sei diverse definizioni di iniezione.

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
   <th colname="col1" class="entry"> <p>Definizione dell'iniezione </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> append|replace  </span> </p> </td> 
   <td colname="col2"> <p>Scegli "append" per aggiungere il valore della definizione di iniezione ("Adobe: Contattaci" o "In vendita ora!" negli esempi di cui sopra) al contenuto dei campi esistenti. Scegli "sostituisci" per sovrascrivere il contenuto del campo esistente con il valore definito. Se un campo al momento non dispone di contenuto, il valore definito viene aggiunto automaticamente, indipendentemente dall’opzione (accoda o sostituisci) utilizzata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> field  </span> </p> </td> 
   <td colname="col2"> <p>È richiesto un nome di campo. Di seguito sono riportati dieci nomi di campo predefiniti utilizzabili: </p> <p> 
     <ul id="ul_B9336FA53023474EAEE399116E7FC972"> 
      <li id="li_C621203DCD2B4875A54A1DD19F0B5B90"> <span class="codeph"> alt  </span> </li> 
      <li id="li_9217E6A037254BEDBB8D006B70D7670D"> <span class="codeph"> corpo  </span> </li> 
      <li id="li_DCDC50F93F224F02897419B745E09399"> <span class="codeph"> charset </span> </li> 
      <li id="li_D95668236B6547B99966668C82B302AB"> <span class="codeph"> date </span> </li> 
      <li id="li_D2071681274345C3B97E9ADA6D223271"> <span class="codeph"> desc  </span> </li> 
      <li id="li_26683A9209454A438D811187FB929482"> <span class="codeph"> chiavi  </span> </li> 
      <li id="li_A5E19F81B872402CA62B5AB9497E030D"> <span class="codeph"> language  </span> </li> 
      <li id="li_FD0B1CD9E6304B18B9D7F57E61015107"> <span class="codeph"> target  </span> </li> 
      <li id="li_400D7E3F3E9B47EFB2FF5C0D278DB573"> <span class="codeph"> title </span> </li> 
      <li id="li_449BCBEE4F64424BB69F780C10F5956C"> <span class="codeph"> url </span> </li> 
     </ul> </p> <p>Ogni nome campo corrisponde agli elementi delle pagine del sito. Se ad esempio si specifica il nome di campo <span class="codeph"> desc </span>, è possibile aggiungere il valore di definizione di iniezione al campo corrispondente alla descrizione Meta tags nelle pagine del sito. </p> <p>Se nelle pagine non esiste una descrizione Meta tag, il contenuto definito crea il tag per te. Il contenuto specificato in un'iniezione <span class="codeph"> desc </span> viene visualizzato nella pagina dei risultati proprio come farebbe il contenuto di una Meta-descrizione hardcoded. </p> <p>È inoltre possibile creare più definizioni con lo stesso nome campo. Ad esempio, supponiamo che tu abbia le seguenti iniezioni: </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/&nbsp;Welcome&nbsp;to&nbsp;My&nbsp;Site </code> </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/company/*.html&nbsp;My&nbsp;Site:&nbsp;Contact </code> </p> <p>Tutte le pagine del sito nell’esempio precedente ricevono un titolo inserito "Benvenuti nel sito personale". Alle pagine della cartella "/company/" viene aggiunto il nuovo titolo "Sito personale: Contattaci" che sostituisce il precedente. </p> <p>Le iniezioni vengono applicate nell'ordine in cui appaiono nella casella di testo <span class="wintitle"> Definizioni di iniezione campo </span>. Se lo stesso campo ("title" in questo esempio) viene definito più di una volta per le pagine che si trovano nella stessa posizione, la definizione successiva ha la precedenza. </p> <p> <span class="codeph"> [regexp]  </span> - facoltativo. Se scegli di utilizzare l’opzione <span class="codeph"> regexp </span> , l’URL definito viene trattato come un’espressione regolare. </p> <p>Consulta <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> <p>Nella seguente definizione: </p> <p> <code> replace&nbsp;target&nbsp; <b>regexp&amp;nbsp;^.*/products/.*\.html$</b>&nbsp;Important&nbsp;information </code> </p> <p> "Informazioni importanti" viene inserito nel campo "target" in tutte le pagine che corrispondono all'espressione regolare <span class="codeph"> ^.*/products/.*\.html$ </span>. </p> <p>Pertanto, si dispone dei seguenti elementi: </p> <p> <code> https://www.mydomain.com/products/page1.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p> <code> https://www.mydomain.com/product/oldstuff.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;not&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p>Nell'esempio seguente: </p> <p> <code> append&amp;nbsp;title&amp;nbsp;regexp&amp;nbsp;^.*\.pdf$&amp;nbsp;Millennium&amp;nbsp;Science </code> </p> <p>L'iniezione aggiunge "Millennium Science" al contenuto "title" di tutte le pagine che terminano con un'estensione del nome file ".pdf". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> URL </span> </p> </td> 
   <td colname="col2"> <p>Un URL è obbligatorio e specifica quali documenti vengono inseriti. </p> <p>L’URL è uno dei seguenti: </p> <p> 
     <ul id="ul_C5C74F6D5EA943B293742989EB822751"> 
      <li id="li_382392DB778D4E14BFFC96D35A861951"> Un percorso completo, come in https://www.mydomain.com/products.html </li> 
      <li id="li_EA2BD0FB66A44CD0844613316F6174D4"> Un percorso parziale, come in https://www.mydomain.com/products </li> 
      <li id="li_D5E0D6D897C8493ABBFC65517CD4A7DB"> Un URL che utilizza caratteri jolly, come in https://www.mydomain.com/*.html </li> 
     </ul> </p> <p>Il valore URL non deve contenere spazi. Se utilizzi l’opzione <span class="codeph"> regexp </span> , l’URL viene trattato come un’espressione regolare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> value </span> </p> </td> 
   <td colname="col2"> <p>Un valore è obbligatorio e viene utilizzato per sostituire o aggiungere al contenuto del campo esistente. È possibile specificare più valori per lo stesso nome campo. Ad esempio: </p> <p>aggiungi <b>chiavi</b> https://www.mysite.com/travel/ <b>estate</b>, <b>spiaggia</b>, <b>sabbia</b> </p> <p>aggiungi <b>chiavi</b> https://www.mysite.com/travel/fare/*.html <b>biglietti economici</b> </p> <p>Nell'esempio precedente, le parole "estate, spiaggia, sabbia" sono aggiunte al campo "chiavi" su tutte le pagine della directory "/travel/". Le parole "biglietti economici" sono aggiunte anche al campo "chiavi" su tutte le pagine della directory "/travel/fare/". </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulta anche [Selezione dei tipi di contenuto per la ricerca per indicizzazione e l&#39;indicizzazione](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

## Aggiunta di definizioni di iniezione di campi {#task_E86566FA1FF74CF68115C0ADA05172AE}

È possibile utilizzare [!DNL Injections] per inserire contenuto nelle pagine web senza la necessità di modificare le pagine stesse.

Facoltativamente, puoi utilizzare **[!UICONTROL Test]** nella pagina [!DNL Injections]. Immetti un nome di campo di prova (ad esempio, &quot;title&quot; o &quot;body&quot;), il valore di campo originale (ad esempio, &quot;Home page&quot;) e un URL di test dal tuo sito web. Il valore risultante viene visualizzato come riferimento. I valori correnti non vengono modificati durante la prova.

**Aggiunta di definizioni di iniezione campi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**.
1. (Facoltativo) Nella pagina [!DNL Injections], nell’area [!DNL Test Field Injections], immetti il campo di test, il valore originale del test e l’URL di test, quindi fai clic su **[!UICONTROL Test]**.
1. Nel campo [!DNL Field Injection Definitions] immettere una definizione di iniezione per riga.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sul caricatore di attributi {#concept_9EF38E98811B42CDA41996432B9AD209}

Utilizza [!DNL Attribute Loader] per definire sorgenti di input aggiuntive per incrementare i dati sottoposti a ricerca per indicizzazione da un sito web.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nel tuo account dal rappresentante dell&#39;account Adobe o dal supporto Adobe.

È possibile utilizzare un’origine di input per feed di dati per accedere al contenuto memorizzato in un modulo diverso da quello normalmente rilevato su un sito web. A tale scopo, utilizza uno dei metodi disponibili per la ricerca per indicizzazione. I dati provenienti da queste sorgenti possono quindi essere inseriti nei dati provenienti da contenuti sottoposti a ricerca per indicizzazione.

Dopo aver aggiunto una definizione del Caricatore di Attributi alla pagina [!DNL Staged Attribute Loader Definitions], è possibile modificare qualsiasi impostazione di configurazione tranne i valori Nome e Tipo

La pagina [!DNL Attribute Loader] mostra le seguenti informazioni:

* Nome della configurazione del caricatore di attributi definita configurata e aggiunta.
* Uno dei seguenti tipi di origine dati per ciascun connettore aggiunto:

   * **Testo** : file semplici &quot;flat&quot;, delimitati da virgole, delimitati da tabulazioni o altri formati delimitati in modo coerente.
   * **Feed**  - Feed XML.

* Se la configurazione è abilitata o meno per la ricerca per indicizzazione e l’indicizzazione successive.
* Indirizzo dell&#39;origine dati.

Vedi anche [Come funziona il processo di iniezione degli attributi per Testo e Feed...](../c-about-settings-menu/c-about-metadata-menu.md#section_E059A33D61EE4DB0972A37B8A35E9E16)

Vedere anche [Informazioni sulla configurazione di più caricatori di attributi](../c-about-settings-menu/c-about-metadata-menu.md#section_4CC49C74EF294608A184E233F215ADFF)

Vedere anche [Informazioni sull&#39;utilizzo di Preview quando si aggiunge un attributo..](../c-about-settings-menu/c-about-metadata-menu.md#section_E9CAB000A94C4D9189786C1EDB1CDB46)

## Funzionamento del processo di iniezione degli attributi per le configurazioni di testo e feed in Attribute Loader {#section_E059A33D61EE4DB0972A37B8A35E9E16}

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
   <td colname="col2"> <p>Scarica l’origine dati. </p> </td> 
   <td colname="col3"> <p>Per le configurazioni Testo e Feed, si tratta di un semplice download di file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Suddividi l’origine dati scaricata in singoli pseudo-documenti. </p> </td> 
   <td colname="col3"> <p>Per <span class="uicontrol"> Testo </span>, ogni riga di testo delimitata da una nuova riga corrisponde a un singolo documento e viene analizzata utilizzando il delimitatore specificato, ad esempio una virgola o una scheda. </p> <p>Per <span class="uicontrol"> Feed </span>, i dati di ciascun documento vengono estratti utilizzando un pattern di espressione regolare nel seguente modulo: </p> <p> <code class="syntax js"> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Utilizzando <span class="uicontrol"> Mappa </span> nella pagina <span class="wintitle"> Caricamento attributi Aggiungi </span> , crea una copia in cache dei dati e quindi crea un elenco di collegamenti per il crawler. I dati vengono memorizzati in una cache locale e compilati con i campi configurati. </p> <p>I dati analizzati vengono scritti nella cache locale. </p> <p>Questa cache viene letta in seguito per creare i documenti HTML semplici necessari al crawler. Ad esempio, </p> <p> <code class="syntax html"> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>L’elemento <span class="codeph"> &lt;title&gt; </span> viene generato solo quando esiste una mappatura al campo metadati Titolo. Allo stesso modo, l'elemento <span class="codeph"> &lt;body&gt; </span> viene generato solo quando esiste una mappatura al campo dei metadati Body. </p> <p> <b>Importante</b>: L'assegnazione di valori al tag meta URL predefinito non è supportata. </p> <p>Per tutte le altre mappature, i tag <span class="codeph"> &lt;meta&gt; </span> vengono generati per ogni campo contenente i dati presenti nel documento originale. </p> <p>I campi di ciascun documento vengono aggiunti alla cache. Per ogni documento scritto nella cache, viene generato anche un collegamento come negli esempi seguenti: </p> <p> <code class="syntax html"> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>La mappatura della configurazione deve avere un campo identificato come Chiave primaria. Questa mappatura rappresenta la chiave utilizzata quando i dati vengono recuperati dalla cache. </p> <p>Il crawler riconosce l'indice URL <span class="codeph">: Prefisso schema </span>, che può quindi accedere ai dati memorizzati nella cache locale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Eseguire la ricerca per indicizzazione del set di documenti memorizzati nella cache. </p> </td> 
   <td colname="col3"> <p>Indice <span class="codeph">: I collegamenti </span> vengono aggiunti all’elenco in sospeso del crawler e vengono elaborati nella sequenza di ricerca per indicizzazione normale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Elabora ogni documento. </p> </td> 
   <td colname="col3"> <p>Il valore chiave di ogni collegamento corrisponde a una voce nella cache, pertanto la ricerca per indicizzazione di ogni collegamento fa sì che i dati del documento vengano recuperati dalla cache. Viene quindi "assemblato" in un'immagine HTML che viene elaborata e aggiunta all'indice. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Informazioni sulla configurazione di più caricatori di attributi {#section_4CC49C74EF294608A184E233F215ADFF}

Puoi definire più configurazioni del Caricatore di Attributi per qualsiasi account.

Quando si aggiunge un caricatore di attributi, è possibile utilizzare facoltativamente la funzione **[!UICONTROL Setup Maps]** per scaricare un esempio dell&#39;origine dati. I dati sono esaminati per verificarne l&#39;idoneità.

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
   <td colname="col2"> <p>Determina il valore del delimitatore provando prima le tabulazioni e poi le barre verticali ( <span class="codeph"> | </span>) e infine virgole ( <span class="codeph"> , </span>). Se prima di fare clic su <span class="uicontrol"> Mappe di installazione </span> hai già specificato un valore di delimitazione, viene utilizzato tale valore. </p> <p>Lo schema di adattamento ottimale si traduce nella compilazione dei campi Mappa con supposizioni in base ai valori Tag e Campo appropriati. Inoltre, viene visualizzato un campione dei dati analizzati. Assicurati di selezionare <span class="uicontrol"> Intestazioni nella prima riga </span> se sai che il file include una riga di intestazione. La funzione di configurazione utilizza queste informazioni per identificare meglio le voci di mappa risultanti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Scarica l’origine dati ed esegue un’analisi XML semplice. </p> <p>Gli identificatori XPath risultanti vengono visualizzati nelle righe Tag della tabella Mappa e valori simili nei campi. Queste righe identificano solo i dati disponibili e non generano le definizioni XPath più complesse. Tuttavia, è ancora utile perché descrive i dati XML e identifica gli elementi tag. </p> <p> <p>Nota:  La funzione Mappe di installazione scarica l'intera sorgente XML per eseguire la sua analisi. Se il file è di grandi dimensioni, l'operazione potrebbe scadere. </p> </p> <p>In caso di esito positivo, questa funzione identifica tutti gli elementi XPath possibili, molti dei quali non sono desiderabili da utilizzare. Esamina le definizioni di mappa risultanti e rimuovi quelle che non sono necessarie o che desideri. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>La funzione Mappe di installazione potrebbe non funzionare per set di dati XML di grandi dimensioni perché il relativo parser di file tenta di leggere l&#39;intero file in memoria. Di conseguenza, potresti riscontrare una condizione di memoria esaurita. Tuttavia, quando lo stesso documento viene elaborato al momento dell&#39;indicizzazione, non viene letto in memoria. Al contrario, i documenti di grandi dimensioni vengono elaborati &quot;in movimento&quot; e non vengono letti interamente in memoria prima.

## Informazioni sull&#39;utilizzo di Anteprima quando si aggiunge un Caricatore di Attributi {#section_E9CAB000A94C4D9189786C1EDB1CDB46}

I dati del caricatore di attributi vengono caricati prima di un&#39;operazione Index.

Al momento dell&#39;aggiunta di un caricatore di attributi, è possibile utilizzare facoltativamente la funzione **[!UICONTROL Preview]** per convalidare i dati, come se li si stesse salvando. Esegue un test sulla configurazione, ma senza salvare la configurazione nell&#39;account. Il test accede all’origine dati configurata. Tuttavia, scrive la cache di download in una posizione temporanea; non è in conflitto con la cartella cache principale utilizzata dal crawler per l’indicizzazione.

Preview elabora solo un predefinito di cinque documenti come controllato da **Acct:IndexConnector-Preview-Max-Documents**. I documenti visualizzati in anteprima vengono visualizzati nel modulo di origine, in quanto vengono presentati al crawler di indicizzazione. La visualizzazione è simile alla funzione &quot;Visualizza origine&quot; di un browser Web. Puoi navigare nei documenti del set di anteprima utilizzando collegamenti di navigazione standard.

L&#39;anteprima non supporta le configurazioni XML perché tali documenti vengono elaborati direttamente e non scaricati nella cache.

## Aggiunta di una definizione di caricamento attributi {#task_A735E5EF763343A9B675E1A3B09AFDBC}

Ogni configurazione del Caricatore di Attributi definisce un&#39;origine dati e le mappature per collegare gli elementi dati definiti per tale origine ai campi di metadati nell&#39;indice.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nel tuo account dal rappresentante dell&#39;account Adobe o dal supporto Adobe.

Prima che gli effetti della nuova definizione abilitata siano visibili ai clienti, ricostruisci l&#39;indice del sito.

**Aggiunta di una definizione di caricamento attributi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella pagina [!DNL Stage Attribute Loader Definitions], fai clic su **[!UICONTROL Add New Attribute Loader]**.
1. Nella pagina [!DNL Attribute Loader Add] , imposta le opzioni di configurazione desiderate. Le opzioni disponibili dipendono dal **[!UICONTROL Type]** selezionato.

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
      <td colname="col2"> <p>Nome univoco della configurazione del caricatore di attributi. È possibile utilizzare caratteri alfanumerici. Sono consentiti anche i caratteri "_" e "-". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> <p>Origine dei dati. Il tipo di origine dati selezionato influisce sulle opzioni risultanti disponibili nella pagina <span class="wintitle"> Caricamento attributi Aggiungi </span> . Puoi scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Testo </span> <p>File di testo semplici, delimitati da virgole, delimitati da tabulazioni o altri formati delimitati in modo coerente. Ogni riga di testo delimitata da una nuova riga corrisponde a un singolo documento ed è analizzata utilizzando il delimitatore specificato. </p> <p>Puoi mappare ogni valore, o colonna, su un campo di metadati, a cui fa riferimento il numero di colonna, a partire da 1 (uno). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Scarica un documento XML primario contenente più "righe" di informazioni. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo di origine dati: Testo</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per l'uso. Oppure, puoi disattivare la configurazione per impedire l'utilizzo di if. </p> <p> <b>Nota</b>: Le configurazioni del caricatore di attributi disattivate vengono ignorate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo dell'host del server in cui si trovano i dati. </p> <p>Se lo desideri, puoi specificare un percorso URI completo (Uniform Resource Identifier) per il documento dell’origine dati, come negli esempi seguenti: </p> <p> <code otherprops="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p> oppure  </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>L’URI viene suddiviso nelle voci appropriate per i campi Indirizzo host, Percorso file, Protocollo e, facoltativamente, Nome utente e Password </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del file di testo semplice, delimitato da virgole, delimitato da tabulazioni o in un altro file di formato delimitato in modo coerente. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Puoi scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTP. </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTPS. </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server FTP. </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server SFTP. </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> File </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Timeout </p> </td> 
      <td colname="col2"> <p>Specifica il timeout, in secondi, per le connessioni FTP, SFTP, HTTP o HTTPS. Questo valore deve essere compreso tra 30 e 300. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nuovi tentativi </p> </td> 
      <td colname="col2"> <p>Specifica il numero massimo di tentativi per connessioni FTP, SFTP, HTTP o HTTPS non riuscite. Questo valore deve essere compreso tra 0 e 10. </p> <p>Un valore pari a zero (0) impedirà i tentativi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Codifica </p> </td> 
      <td colname="col2"> <p>Specifica il sistema di codifica dei caratteri utilizzato nel file di origine dati specificato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimitatore </p> </td> 
      <td colname="col2"> <p>Specifica il carattere da utilizzare per delineare ogni campo nel file di origine dati specificato. </p> <p>La virgola ( <span class="codeph"> , </span>) è un esempio di delimitatore. La virgola funge da delimitatore di campo che consente di separare i campi dati nel file di origine dati specificato. </p> <p>Selezionare la scheda <span class="uicontrol">? </span> per utilizzare il carattere di tabulazione orizzontale come delimitatore. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Intestazioni nella prima riga </p> </td> 
      <td colname="col2"> <p>Indica che la prima riga del file di origine dati contiene solo informazioni di intestazione, non dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Giorni non aggiornati </p> </td> 
      <td colname="col2"> <p>Imposta l'intervallo minimo tra i download dei dati del caricatore di attributi. I download attivati dall'indice che si verificano nell'intervallo di frequenza di aggiornamento del download vengono ignorati. Se si imposta questo valore sul valore predefinito 1, i dati del caricatore di attributi non vengono scaricati più di una volta entro un periodo di 24 ore. Tutti gli indici di ricerca che si verificano all'interno dell'intervallo di frequenza di aggiornamento del download utilizzano l'ultimo set di dati scaricato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Specifica le mappature da colonna a metadati utilizzando i numeri di colonna. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Colonna </span> <p> Specifica un numero di colonna, con la prima colonna pari a 1 (una). Per aggiungere nuove righe della mappa per ogni colonna, in <span class="wintitle"> Azione </span>, fai clic su <span class="uicontrol"> + </span>. </p> <p>Non è necessario fare riferimento a ciascuna colonna nell’origine dati. È invece possibile scegliere di saltare i valori. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag &lt;meta&gt; generato. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che il campo <span class="uicontrol"> </span> diventi un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l’account corrente. </p> <p>Il valore del campo <span class="uicontrol"> </span> può essere un campo di metadati non definito, se necessario. Un campo di metadati non definito è talvolta utile per creare contenuti utilizzati da uno <span class="wintitle"> script di filtro </span>. </p> <p>Consultare <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni sul filtro degli script </a>. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Chiave principale?  </span> <p>Solo un campo è identificato come chiave primaria. Questo campo verrà utilizzato come "chiave esterna" per far corrispondere i dati del Caricatore di attributi con il documento corrispondente nell'indice. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> Striscia HTML?  </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Tipo di origine dati: Feed</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abilitato </p> </td> 
      <td colname="col2"> <p>Attiva la configurazione per l'uso. Oppure, puoi disattivare la configurazione per impedire l'utilizzo di if. </p> <p> <b>Nota</b>: Le configurazioni del caricatore di attributi disattivate vengono ignorate. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Indirizzo host </p> </td> 
      <td colname="col2"> <p>Specifica l'indirizzo dell'host del server in cui si trovano i dati. </p> <p>Se lo desideri, puoi specificare un percorso URI completo (Uniform Resource Identifier) per il documento dell’origine dati, come negli esempi seguenti: </p> <p> <code class="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p> oppure  </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>L’URI viene suddiviso nelle voci appropriate per i campi Indirizzo host, Percorso file, Protocollo e, facoltativamente, Nome utente e Password. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Percorso file </p> </td> 
      <td colname="col2"> <p>Specifica il percorso del documento XML primario contenente più "righe" di informazioni. </p> <p>Il percorso è relativo alla directory principale dell'indirizzo host. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protocollo </p> </td> 
      <td colname="col2"> <p>Specifica il protocollo utilizzato per accedere al file. Puoi scegliere tra le seguenti opzioni: </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTP. </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>Se necessario, è possibile immettere le credenziali di autenticazione appropriate per accedere al server HTTPS. </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server FTP. </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>Devi immettere le credenziali di autenticazione appropriate per accedere al server SFTP. </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> File </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elemento </p> </td> 
      <td colname="col2"> <p>Identifica l'elemento XML che è possibile utilizzare per identificare singole righe XML nel file di origine dati specificato. </p> <p>Ad esempio, nel seguente frammento Feed di un documento XML di Adobe, il valore del tag elemento è <span class="codeph"> record </span>: </p> <p> <code class="syntax xml"> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
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
      <td colname="col2"> <p>Specifica un campo di metadati i cui valori vengono utilizzati come "chiavi" di ricerca nei dati della configurazione del caricatore di attributi. Se non è selezionato alcun valore (<b>—None—</b>), i dati di questa configurazione non sono disponibili per l'utilizzo nei calcoli di ranking (<b>Regole</b> &gt; <b>Regole di classificazione</b> &gt; <b>Modifica regole</b>). Quando selezioni un valore, i valori di questo campo vengono utilizzati per fare riferimento a documenti di ricerca/merchandising del sito con i dati di questa configurazione. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Giorni non aggiornati </p> </td> 
      <td colname="col2"> <p>Imposta l'intervallo minimo tra i download dei dati del caricatore di attributi. I download attivati dall'indice che si verificano nell'intervallo di frequenza di aggiornamento del download vengono ignorati. Se si imposta questo valore sul valore predefinito 1, i dati del caricatore di attributi non vengono scaricati più di una volta entro un periodo di 24 ore. Tutti gli indici di ricerca che si verificano all'interno dell'intervallo di frequenza di aggiornamento del download utilizzano l'ultimo set di dati scaricato. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mappa </p> </td> 
      <td colname="col2"> <p>Consente di specificare le mappature XML da elemento a metadati utilizzando le espressioni XPath. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tag </span> <p>Specifica una rappresentazione XPath dei dati XML analizzati. Utilizzando l'esempio di documento XML di Adobe sopra, sotto l'opzione Tag elemento, può essere mappato utilizzando la seguente sintassi: </p> <p> <code class="syntax xml"> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>La sintassi di cui sopra si traduce come segue: </p> <p> 
        <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
        <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code class="syntax xml"> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>L'attributo <span class="codeph"> displayurl </span> del record <span class="codeph"> </span> viene mappato sul campo metadati <span class="codeph"> page-url </span>. </p> </li> 
        <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code class="syntax xml"> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi elemento <span class="codeph"> meta </span> contenuto all'interno di un elemento <span class="codeph"> metadati </span> contenuto all'interno di un elemento <span class="codeph"> record </span>, il cui attributo name è <span class="codeph"> titolo </span>, viene mappato sul campo metadati <span class="codeph"> titolo </span> </p> </li> 
        <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi elemento <span class="codeph"> meta </span> contenuto all'interno di un elemento <span class="codeph"> metadati </span> contenuto all'interno del record <span class="codeph"> </span>, il cui attributo name è <span class="codeph"> descrizione </span>, è mappato al campo metadati <span class="codeph"> desc </span> </p> </li> 
        <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>L'attributo <span class="codeph"> content </span> di qualsiasi elemento <span class="codeph"> meta </span> contenuto all'interno di un elemento <span class="codeph"> metadati </span> contenuto nel record <span class="codeph"> </span>, il cui attributo name è <span class="codeph"> descrizione </span>, viene mappato sul campo metadati <span class="codeph"> corpo </span> </p> </li> 
        </ul> </p> <p>XPath è una notazione relativamente complicata. Ulteriori informazioni sono disponibili nel seguente percorso: </p> <p>Vedere <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Campo </span> <p>Definisce il valore dell'attributo name utilizzato per ciascun tag <span class="codeph"> &lt;meta&gt; </span> generato. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadati? </span> <p>Fa sì che il campo <span class="uicontrol"> </span> diventi un elenco a discesa dal quale è possibile selezionare campi di metadati definiti per l’account corrente. </p> <p>Il valore del campo <span class="uicontrol"> </span> può essere un campo di metadati non definito, se necessario. Un campo di metadati non definito è talvolta utile per creare contenuti utilizzati da <span class="wintitle"> Script di filtro </span>. </p> <p>Consultare <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informazioni sul filtro degli script </a>. </p> <p>Quando Attribute Loader elabora documenti XML con più hit su qualsiasi campo di mappa, i più valori vengono concatenati in un singolo valore nel documento memorizzato nella cache risultante. Per impostazione predefinita, questi valori vengono combinati utilizzando un delimitatore virgola. Supponiamo tuttavia che il valore corrispondente del campo <span class="wintitle"> </span> sia un campo metadati definito. Inoltre, per quel campo è impostato l'attributo <span class="wintitle"> Elenchi consentiti </span> . In questo caso, il valore Delimitatori elenco del campo, che è il primo delimitatore definito, viene utilizzato nella concatenazione. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Chiave principale?  </span> <p>Solo un campo è identificato come chiave primaria. Questo campo verrà utilizzato come "chiave esterna" per far corrispondere i dati del Caricatore di attributi con il documento corrispondente nell'indice. </p> </li> 
      <li id="li_80D6AF130FCE40AC972FE4B605B86BF6"> <span class="uicontrol"> Striscia HTML?  </span> <p>Quando questa opzione è selezionata, tutti i tag HTML trovati nei dati di questo campo vengono rimossi. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Azione </span> <p>Consente di aggiungere righe alla mappa o rimuovere righe dalla mappa. L'ordine delle righe non è importante. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Fai clic su **[!UICONTROL Setup Maps]** per scaricare un esempio dell’origine dati. I dati sono esaminati per verificarne l&#39;idoneità.
1. Fai clic su **[!UICONTROL Add]** per aggiungere la configurazione alla pagina [!DNL Attribute Loader Definitions].
1. Nella pagina [!DNL Attribute Loader Definitions], fai clic su **[!UICONTROL rebuild your staged site index]**.
1. (Facoltativo) Nella pagina [!DNL Attribute Loader Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica della definizione del caricatore di attributi {#task_AA2D1B2BCAFA44A6A0C59A0318274E80}

È possibile modificare un Caricatore di Attributi esistente definito.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nel tuo account dal rappresentante dell&#39;account Adobe o dal supporto Adobe.

Non tutte le opzioni del caricatore di attributi sono disponibili per la modifica, ad esempio Nome o Tipo del caricatore di attributi dall&#39;elenco a discesa [!DNL Type].

**Per modificare una definizione del caricatore di attributi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella pagina [!DNL Attribute Loader], sotto l&#39;intestazione della colonna [!DNL Actions], fare clic su **[!UICONTROL Edit]** per il nome di una definizione di Caricatore di Attributi di cui si desidera modificare le impostazioni.
1. Nella pagina [!DNL Attribute Loader Edit] , imposta le opzioni desiderate.

   Vedere la tabella delle opzioni in [Aggiunta di una definizione di Caricatore di Attributi](../c-about-settings-menu/c-about-metadata-menu.md#task_A735E5EF763343A9B675E1A3B09AFDBC).
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella pagina [!DNL Attribute Loader Definitions], fai clic su **[!UICONTROL rebuild your staged site index]**.
1. (Facoltativo) Nella pagina [!DNL Attribute Loader Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Copia della definizione di un caricatore di attributi {#task_9B40D5ECFC81411E9480F62A0FD5F2E0}

È possibile copiare una definizione di Caricatore di Attributi esistente da utilizzare come base per un nuovo Caricatore di Attributi che si desidera creare.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nel tuo account dal rappresentante dell&#39;account Adobe o dal supporto Adobe.

Quando copi una definizione di Caricatore di Attributi, la definizione copiata viene disabilitata per impostazione predefinita. Per abilitare o &quot;attivare&quot; la definizione, è necessario modificarla dalla pagina [!DNL Attribute Loader Edit] e selezionare **[!UICONTROL Enable]**.

Vedere [Modifica della definizione di un caricatore di attributi](../c-about-settings-menu/c-about-metadata-menu.md#task_AA2D1B2BCAFA44A6A0C59A0318274E80).

**Per copiare una definizione del caricatore di attributi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella pagina [!DNL Attribute Loader], sotto l&#39;intestazione di colonna [!DNL Actions], fare clic su **[!UICONTROL Copy]** per il nome di una definizione di Caricatore di Attributi di cui si desidera duplicare le impostazioni.
1. Nella pagina [!DNL Attribute Loader Copy] , immetti il nuovo nome della definizione.
1. Clic **[!UICONTROL Copy]**.
1. (Facoltativo) Nella pagina [!DNL Attribute Loader Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ridenominazione della definizione del caricatore di attributi {#task_58D5DFD7EBC04111BCB91118E4440DB4}

È possibile modificare il nome di una definizione di Caricatore di Attributi esistente.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nel tuo account dal rappresentante dell&#39;account Adobe o dal supporto Adobe.

**Ridenominazione di una definizione del caricatore di attributi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella pagina [!DNL Attribute Loader], sotto l&#39;intestazione della colonna [!DNL Actions], fare clic su **[!UICONTROL Rename]** per il nome della definizione del caricatore di attributi che si desidera modificare.
1. Nella pagina [!DNL Attribute Loader Rename] , immetti il nuovo nome della definizione nel campo [!DNL Name] .
1. Clic **[!UICONTROL Rename]**.
1. (Facoltativo) Nella pagina [!DNL Attribute Loader Definitions] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Caricamento dei dati del caricatore di attributi {#task_2F3C55189B0A4049AB2113F2291CC181}

È possibile scaricare i dati configurati di Attribute Loader nella ricerca/merchandising del sito.

La pagina [!DNL Data Load] mostra le seguenti informazioni sullo stato dell&#39;ultima operazione di caricamento dati del caricatore di attributi:

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
   <td colname="col2"> <p>Indica il successo o l'errore dell'ultimo tentativo di caricamento dei dati. In alternativa, visualizza lo stato di un'operazione di caricamento dati già in corso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora di inizio </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l’ora di inizio dell’ultima operazione di caricamento dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora di interruzione </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l’ora di completamento dell’ultima operazione di caricamento dati. Oppure indica che l'operazione di caricamento dati corrente è ancora in corso. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per caricare i dati del caricamento attributi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella pagina [!DNL Attribute Loader Definitions], fai clic su **[!UICONTROL Load Attribute Loader Data]**.
1. Nella pagina **[!UICONTROL Attribute Loader Data Load]** , effettua una delle seguenti operazioni:

   * Fare clic su **[!UICONTROL Start Load]** per avviare l&#39;operazione di caricamento.

      Durante un&#39;operazione di caricamento dei dati, la riga **Avanzamento** fornisce informazioni sull&#39;avanzamento.

   * Fare clic su **[!UICONTROL Stop Load]** per interrompere l&#39;operazione di caricamento.

1. Fai clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL Attribute Loader Definitions].

## Anteprima dei dati del caricatore di attributi {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

È possibile utilizzare Anteprima per visualizzare i dati del caricatore di attributi caricato più di recente.

La colonna Riga della tabella mostra il numero per ogni riga di dati, indicando l&#39;ordine originale in cui sono stati caricati i valori del caricatore di attributi.

Le colonne rimanenti mostrano i valori associati a ciascuna voce.

Se la tabella è vuota, significa che non sono ancora stati caricati dati del caricatore di attributi. È possibile chiudere la pagina [!DNL Attribute Loader Data Preview] e quindi caricare i dati del caricatore di attributi.

Consultare [Caricamento dei dati del caricatore di attributi](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**Visualizzazione in anteprima dei dati del caricamento attributi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella pagina [!DNL Attribute Loader Definitions], sotto la colonna [!DNL Actions], fai clic su **[!UICONTROL Preview]** per la configurazione di cui desideri visualizzare i dati scaricati.
1. Nella pagina [!DNL Attribute Loader Data Preview] , utilizza le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare i dati.

   Fai clic su un’intestazione di colonna nella tabella per ordinare i dati in ordine crescente o decrescente.
1. Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Download to Desktop]** per scaricare e salvare la tabella come file .xlt.
   * Chiudi la pagina quando finisci di visualizzare l’anteprima dei dati di Attribute Loader e torna alla pagina visualizzata in precedenza.

## Visualizzazione delle impostazioni di una definizione del caricatore di attributi {#task_EA99A9694FE948ADA82C1DBA0667851B}

È possibile esaminare le impostazioni di configurazione di una definizione di Caricatore di Attributi esistente.

Dopo aver aggiunto una definizione di Caricatore attributi alla pagina [!DNL Attribute Loader Definitions], non è possibile modificarne l&#39;impostazione Tipo. È invece necessario eliminare la definizione e aggiungerne una nuova.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nel tuo account dal rappresentante dell&#39;account Adobe o dal supporto Adobe.

**Per visualizzare le impostazioni di una definizione del caricatore di attributi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella pagina [!DNL Attribute Loader], sotto l&#39;intestazione della colonna [!DNL Actions], fare clic su **[!UICONTROL Edit]** per il nome di una definizione di Caricatore di Attributi di cui si desidera esaminare o modificare le impostazioni.

## Visualizzazione del registro dal caricamento dati più recente del caricatore di attributi {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

È possibile utilizzare [!DNL View Log] per esaminare il file di log dei dati del caricatore di attributi del processo di download più recente. È inoltre possibile utilizzare la visualizzazione del registro per monitorare un download in esecuzione.

Consultare [Caricamento dei dati del caricatore di attributi](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**Per visualizzare il registro dal caricamento dati più recente del caricatore di attributi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella pagina [!DNL Attribute Loader Definitions], fai clic su **[!UICONTROL View Log]**. Pagina di log,
1. Nella pagina [!DNL Attribute Loader Data Log] , utilizza le opzioni di navigazione e visualizzazione nella parte superiore e inferiore della pagina per visualizzare le informazioni sul registro.
1. Al termine, chiudi la pagina per tornare alla pagina [!DNL Attribute Loader Definitions] .

## Eliminazione di una definizione di caricamento attributi {#task_E8980F66888B476E98C228C1D307EDF8}

È possibile eliminare una definizione di Caricatore di Attributi esistente che non è più necessaria o utilizzata.

>[!NOTE]
>
>Per utilizzare Attribute Loader, potrebbe essere necessario che sia attivato nel tuo account dal rappresentante dell&#39;account Adobe o dal supporto Adobe.

**Per eliminare una definizione del caricatore di attributi**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Nella pagina [!DNL Attribute Loader Definitions], sotto l&#39;intestazione della colonna [!DNL Actions], fare clic su **[!UICONTROL Delete]** per il nome della definizione del caricatore di attributi che si desidera rimuovere.
1. Nella pagina [!DNL Attribute Loader Delete], fai clic su **[!UICONTROL Delete]**.
