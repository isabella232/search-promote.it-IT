---
description: Potete utilizzare Regole di classificazione per controllare il posizionamento relativo o la classificazione dei risultati di ricerca di un cliente in base al contenuto di tag meta contenuti e  metriche Adobe Analytics correlate.
seo-description: Potete utilizzare Regole di classificazione per controllare il posizionamento relativo o la classificazione dei risultati di ricerca di un cliente in base al contenuto di tag meta contenuti e  metriche Adobe Analytics correlate.
seo-title: Informazioni sulle regole di classificazione
solution: Target
subtopic: Ranking Rules
title: Informazioni sulle regole di classificazione
topic: Rules,Site search and merchandising
uuid: 21962f9a-1d9c-442f-a6c4-5f452436c640
translation-type: tm+mt
source-git-commit: 552f93f1f630c64bbe3d5c8a87c4f5895ae6868c
workflow-type: tm+mt
source-wordcount: '4647'
ht-degree: 0%

---


# Informazioni sulle regole di classificazione{#about-ranking-rules}

Potete utilizzare Regole di classificazione per controllare il posizionamento relativo o la classificazione dei risultati di ricerca di un cliente in base al contenuto di tag meta contenuti e  metriche Adobe Analytics correlate.

## Utilizzo delle regole di classificazione {#concept_F555C076759B4E81B925441CFE707397}

Le regole di classificazione vengono definite per influenzare il posizionamento relativo dei documenti all&#39;interno dei risultati di ricerca, in base al contenuto di ciascun documento. Potete basare le regole di classificazione sia sul contenuto di tag meta,  metriche Adobe Analytics (se l&#39;account è configurato per lavorare con  Adobe Analytics), o  metriche Adobe Analytics HBX (se l&#39;account è configurato per lavorare con  Adobe Analytics HBX).

È possibile impostare pagine Web che contengono meta tag con caratteristiche desiderate, ad esempio un determinato marchio o prezzo, o pagine Web con indicatori prestazioni chiave di Adobe Analytics desiderabili  indicatori prestazioni chiave di, come visualizzatori univoci, per ottenere una classificazione più elevata rispetto alle pagine Web che non lo sono. Le caratteristiche &quot;desiderabili&quot; sono facilmente aggiornate aggiungendo o modificando regole di classificazione e quindi reindicizzando il sito Web.

Se sono definiti più tag meta di tipo &quot;rank&quot;, è possibile creare raccolte separate di regole da utilizzare nel calcolo dei vari campi di classificazione. È possibile aggiungere un gruppo di regole di classifica, da assegnare poi a uno dei campi Rank definiti. I gruppi di regole contengono in genere una o più definizioni di regole, ma possono anche fare riferimento ad altri gruppi di regole, per cui potete creare uno o più gruppi di regole comunemente utilizzate che vengono condivisi durante il calcolo dei diversi gruppi.

Consultate [Aggiunta di un gruppo](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)di regole di classificazione.

Un valore di classifica positiva promuove i risultati di ricerca verso l’alto; un valore di classificazione negativo declassa i risultati della ricerca verso il basso dei risultati della ricerca. L’intervallo normale per i valori di classificazione è 1,0, ovvero la promozione massima all’interno dei risultati di ricerca, mentre -1,0 è la retrocessione massima. Anche se potete personalizzare questo intervallo modificando il campo Classifica nelle definizioni dei metadati, questo tipo di personalizzazione non è in genere necessario.

Vedere [Informazioni sulle definizioni](../c-about-settings-menu/c-about-metadata-menu.md#concept_AE48035C210145169BE067D396975620).

Se avete definito più di un campo di classificazione in Impostazioni > Metadati > Definizioni, potete creare altri set di regole di classificazione, uno per ciascun campo di classificazione. È possibile definire set aggiuntivi di regole di classificazione senza essere associati direttamente a un campo di classificazione. Questa flessibilità consente di creare set di regole comuni da condividere nel calcolo di uno o più valori di classificazione.

**Importante**: Prima di poter utilizzare le regole di classificazione, è necessario completare diversi passaggi di configurazione dell&#39;account.

Consultate [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)

## Configurazione della classificazione {#task_4CEBC13925B047FC95BDC217B48089C5}

Prima di poter utilizzare le regole di classificazione, è necessario completare diversi passaggi di configurazione dell&#39;account.

**Per configurare la classificazione**

1. Scegliete tra le seguenti opzioni:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Attività </p> </th> 
      <th colname="col2" class="entry"> <p>Configurazione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Creazione di regole di classificazione basate su tag meta </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_28ABB980143948DFA79AC4360AAB7556"> 
      <li id="li_544075CFA0964C6F8FAF7941AAA9ECCC"> Nel menu del prodotto, fate clic su <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Definizioni </span>. </li> 
      <li id="li_F237F13B89E8425080C15D3BD697652C"> Nella pagina Definizioni, fare clic su <span class="uicontrol"> Aggiungi nuovo campo </span>. </li> 
      <li id="li_2A839874D71D45FEA661B3D3B8BE2A86"> Nella pagina Aggiungi campo digitare <span class="uicontrol"> ; nel campo di testo Nome </span> campo <code>
        rank 
      </code>; nel campo di testo Nome <span class="uicontrol"> tag metadati </span> , digitare <code>
        rank 
      </code>; nell'elenco a discesa <span class="uicontrol"> Tipo di dati </span> , selezionare <span class="uicontrol"> Classifica </span>. Lasciate invariate tutte le altre opzioni di campo. <p>Vedere il parametro di query <span class="codeph"> sp_sr </span> in parametri CGI di ricerca <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> back-end </a>. </p> </li> 
      <li id="li_8E91AF4BE51A4A41ABBF9680DDE0B7CE">Fai clic su <span class="uicontrol">Aggiungi </span>. </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Creazione di regole di classificazione basate su  metriche Adobe Analytics </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_BE57CBC303D941778B10D855ADC93C68"> 
      <li id="li_8DF5D8F924B24ECBBD2D93C76C69D00C"> Accertatevi di aver impostato  autenticazione Adobe Analytics dall'interno della ricerca nel sito/merchandising. <p>Consultate <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42" type="task" format="dita" scope="local"> Impostazione 'autenticazione delle metriche Adobe Analytics </a>. </p> </li> 
      <li id="li_CF7DD073FC5A432DADBD282AA8BB9920"> Seleziona e aggiungi una suite di rapporti disponibile. <p>Consultate <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0" type="task" format="dita" scope="local"> Aggiunta di una suite di rapporti Adobe Analytics  </a>. </p> </li> 
      <li id="li_9A63448577D04E028DF211D8715F943A"> Configura l'elenco  metriche Adobe Analytics che desideri rendere disponibili per la creazione di nuove regole di classificazione. <p>Consultate <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Modifica delle metriche Adobe Analytics  di una suite di rapporti </a>. </p> </li> 
      <li id="li_1ACA3611D9B44AC394604CD89209C966"> Caricate le metriche Adobe Analytics  iniziali per le pagine del sito Web. <p>Vedere <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181" type="task" format="dita" scope="local"> Caricamento  dati Adobe Analytics </a>. </p> </li> 
      </ol> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Aggiungere una o più regole di classificazione.

   Consultate [Aggiunta di una regola](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)di classificazione.

1. Fate clic **[!UICONTROL regenerate your staged site index]** per eseguire un reindicizzazione completa del sito Web (da **[!UICONTROL Index]** > **[!UICONTROL Full Index]**).

   Consultate [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Consultate [Configurazione di un indice incrementale di un sito Web](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)in fase.
1. Controllare i valori nella colonna Classifica in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** per verificare che le regole di classificazione siano state applicate correttamente.

## Classificazione dei documenti per età {#topic_770815CF1B2A491F83FF765871B6F1B8}

È possibile classificare un documento HTML in base alla sua età con una funzione di decadimento esponenziale. Il tasso di decadimento è specificato con una costante mezza vita scelta, il tempo che deve passare prima che il valore scenda a metà del valore iniziale.

La classificazione dell&#39;età si basa sulle due equazioni seguenti:

`K = -ln(2) / H`

`RANK = e^(K * T)`

Variabili `H` e `T` ingressi per questa funzione: `H` è il periodo di mezza durata desiderato ed `T` è l&#39;età del documento, espressa in secondi. `K` è il ciclo di vita calcolato e `RANK` il decadimento esponenziale del valore di età specificato. Il valore risultante è compreso tra 0 e 1. Un documento più recente ha un valore di classificazione più vicino a 1 rispetto a un documento meno recente. In teoria, i documenti non dovrebbero mai raggiungere il valore 0, ma gli errori di arrotondamento possono causare il risultato di diventare 0.

## Requisiti per l’uso della classificazione dell’età {#section_D716507D589442C6B7848892BD28F966}

* Il tuo account deve già essere configurato correttamente per la classificazione. Se non è configurata, consulta [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).
* Il documento HTML deve avere un campo meta tag HTML che rappresenta la data di nascita o l&#39;inizio come data di data e ora o un altro valore significativo.
* La funzione speciale integrata, `search_get_age_rank()`specificata nelle pagine Aggiungi o Modifica regola di classificazione, viene utilizzata per calcolare il grado di età di un documento. Le sezioni seguenti descrivono in dettaglio l&#39;uso generale della funzione di classificazione dell&#39;età. Viene inoltre presentato un esempio che illustra la funzione di classificazione dell’età.

## Utilizzo di search_get_age_rank () nella pagina Aggiungi regola di classificazione o nella pagina Modifica regola di classificazione {#section_34BC5276F2AB4419AD92872A397CA0AF}

Specificate `search_get_age_rank()` quanto segue:

`search_get_age_rank(Birthdate#Half_Life#Default_Rank)`

* Data di nascita: la data di nascita o la data di inizio del file deve essere una stringa formattata in base ai formati data del campo. Questa stringa formattata per la data deve essere un riferimento a un campo, come in `{field_name}`.
* Half_Life - La metà del ciclo di vita è la quantità di tempo che deve trascorrere prima che il valore scenda a metà del valore iniziale. Questo valore è espresso in numero di giorni ed è un numero intero o un numero a virgola mobile.
* Default_Rank - Il rango predefinito viene utilizzato come rete di sicurezza nel caso in cui la data di nascita non sia valida o la data sia futura. Non potete utilizzare questo valore predefinito se anche il relativo campo di metadati associato ha un valore predefinito valido. Il valore qui è un numero a virgola mobile o un numero intero. Consultate di seguito per suggerimenti in caso di problemi con cui viene utilizzato il valore predefinito.

Consultate [Aggiunta di una regola](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)di classificazione.

Consultate [Modifica di una regola](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275)di classificazione.

**Esempio**

Nell&#39;esempio seguente,

`search_get_age_rank({birthdate}#28#0.20)`

la data contenuta nel `birthdate` campo del documento viene passata come data e ora. La mezza vita è di 28 giorni. Il valore di classificazione predefinito è 0,20 se la data non è valida.

Vedere la tabella delle opzioni in [Aggiunta di una regola](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)di classificazione.

Nella sezione Valori/Classificazioni della pagina Aggiungi regola di classificazione o Modifica regola di classificazione è possibile utilizzare solo `search_get_age_rank` con regole personalizzate. Accertatevi quindi di scegliere **Personalizzato** dall&#39;elenco a discesa Valori/Classificazioni. Quando la regola utilizza la funzione di graduatoria, nella parte dei valori della regola non sono consentiti spazi. Assicurarsi che non ci siano spazi negli argomenti della funzione o tra questi. E non ci sono spazi tra operatori matematici o condizionali.

Di seguito è riportato un esempio di regola di valori/classifica, una regola associata a un campo di testo:

`regexp .* search_get_age_rank({other_field}#365#0.20)`

Nell&#39;esempio si presuppone che `other_field` contenga un valore data. Se questo campo non è di per sé un campo di tipo data, questo valore viene interpretato utilizzando i formati data associati al campo Data predefinito. In caso contrario, vengono utilizzati i formati data di questo campo. Questa voce di valori/ranks viene utilizzata ogni volta che il campo del documento, che l&#39;origine dati della regola identifica, non è vuota e il valore restituito dalla funzione (da 0 a 1) è la classificazione assegnata.

Per una regola associata a un campo Numerico, in particolare un campo Data:

`9999999999 search_get_age_rank({other_field}#365#0.20)`

Durante l&#39;elaborazione di ciascun documento, il valore in `other_field` viene convertito nel modulo &quot;epoch&quot; di Unix, utilizzando le definizioni del formato data del campo. Questo valore viene utilizzato nella `search_get_age_rank()` chiamata. Poiché ogni valore &quot;epoch&quot; è inferiore a 99999999999 (almeno per ora), la regola fornisce semplicemente il valore restituito dalla funzione (da 0 a 1) come rango.

In entrambi gli esempi precedenti, è tipico che l&#39;Origine dati della regola sia lo stesso campo utilizzato nella `search_get_age_rank()` funzione, in questo caso `other_field` .

## Un esempio di integrazione della classificazione dell&#39;età nelle regole di classificazione {#section_A86D909687CC45E19D4EA7A4A9283F28}

Di seguito è riportato un esempio di come è possibile integrare la classificazione delle età nelle regole di classificazione. L’esempio mostra anche i risultati non elaborati della funzione di classificazione delle fasce di età e i risultati delle regole di classificazione. L&#39;esempio presuppone quanto segue:

* Le pagine Web sottoposte a ricerca per indicizzazione hanno un tag meta HTML denominato &quot;Birthdate&quot;. Il contenuto di questo tag è costituito da una marca temporale relativa al documento.
* Le definizioni di metadati dispongono di un campo metatag definito per il tag data di nascita. Questo campo è impostato su &quot;date&quot;.

**Regole di classificazione**

Consultate [Aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)tag meta.

Ora si aggiunge una nuova regola di classificazione. La regola è definita per utilizzare il campo &quot;data di nascita&quot; del documento. Viene aggiunta una nuova regola di classificazione con le seguenti proprietà impostate:

* Tipo origine dati: Tag Meta
* Nome origine dati: natalità
* Peso/Condizioni: 10 - Massima importanza
* Valori/spazi: 9999999999 search_get_age_rank({data di nascita}#14#0.10)
* Classifica predefinita: -1

La regola fa diverse cose. Il peso della regola è impostato su 10. Il valore di classifica è semplicemente il risultato della funzione age-rank, un valore da 0 a 1. Non è possibile utilizzare gli spazi con `search_get_age_rank()`. Inoltre, il campo &quot;compleanni&quot; è racchiuso tra parentesi. Infine, quando si salva questa regola, le virgole nella definizione Valori/Rank vengono sostituite con `#` caratteri; questo comportamento è normale.

**Visualizzazione dei risultati**

Utilizzate la funzione Visualizzazione dati per visualizzare rapidamente i risultati della funzione di fascia di età. Aggiungete i campi metadati appropriati. Nell’esempio, `age_val` e `myrank` sono i due campi Metadati che devono essere aggiunti alla Visualizzazione dati. Il `myrank` campo mostra in che modo la classificazione dell’età influisce sui valori di classificazione. Il `age_val` campo mostra l&#39;output non elaborato della funzione di decadimento esponenziale per quel documento.

## Valori predefiniti {#section_CB109EF78F914E92955D512ACFC3310E}

Di seguito sono riportati tre valori predefiniti coinvolti nella funzione `search_get_age_rank()`:

* Il valore predefinito che è possibile immettere nella `search_get_age_rank()` funzione stessa.
* Il valore di classifica predefinito dalla regola di classificazione.
* Il valore predefinito dalla definizione dei metadati.

A seconda di dove si verifica l&#39;errore, è possibile che vengano visualizzati valori predefiniti diversi.

Ad esempio, il valore predefinito della definizione di metadati non deve mai essere impostato se l’implementazione di Ranking e Filtraggio è corretta. Questo valore predefinito è l’ultimo valore di riferimento quando non esiste alcun contenuto valido o noto per tale campo di metadati. Il valore predefinito delle regole di classificazione potrebbe essere visualizzato quando `search_get_age_rank()` si fa riferimento al proprio tag associato e il tag risulta mancante nel documento. In questo caso, questa regola va dritta al valore predefinito della regola. Se la funzione di classificazione dell&#39;età fa riferimento al tag di un&#39;altra regola di classificazione, è possibile che venga utilizzato il valore predefinito passato in tale funzione se il tag di riferimento è mancante o non valido.

## Aggiunta di una regola di classificazione {#task_A132789FD4E5423DAD090DCDA7311E8A}

Potete aggiungere [!DNL Ranking Rules] per influenzare il posizionamento relativo delle pagine Web all’interno dei risultati di ricerca, in base al contenuto di ogni pagina Web.

Consultate [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**Aggiunta di una regola di classificazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Facoltativo) Se avete creato un gruppo di regole e aggiunto delle regole al gruppo, nella [!DNL Define Ranking Rules] pagina selezionate nell&#39;elenco a **[!UICONTROL Select Rule Group]** discesa un gruppo di regole che contiene le regole da modificare.

   Consultate [Aggiunta di un gruppo](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)di regole di classificazione.
1. Nella [!DNL Define Ranking Rules] pagina, fate clic **[!UICONTROL Add Rule]** per aggiungere una nuova regola di classificazione o per aggiungere un riferimento a un set di regole.
1. Nella [!DNL Add Ranking Rule] pagina, impostate le opzioni desiderate. I campi contrassegnati con un asterisco (*) sono obbligatori.

   Il tipo di origine dati selezionato influisce sulle scelte disponibili nell&#39;elenco a [!DNL Data Source Name] discesa. Ad esempio, se hai selezionato **[!UICONTROL Meta Tag]** come Tipo origine dati, il Nome origine dati fa riferimento al nome di un tag meta nelle pagine del sito Web. Se hai selezionato **[!UICONTROL Adobe Analytics Metric (Number)]**, Nome origine dati fa riferimento a uno dei nomi delle metriche Adobe Analytics  che hai selezionato in una suite di rapporti, come trovato nella **[!UICONTROL Edit Adobe Analytics Metrics]** pagina in ricerca/merchandising del sito.

   Consultate [Modifica delle metriche Adobe Analytics  di una suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)di rapporti.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Tipo origine dati </p> </td> 
      <td colname="col2"> <p>Determina le caratteristiche dell'origine dati utilizzata come input per questa regola di classificazione. </p> <p>I tipi di origine dati che puoi selezionare includono: 
      <ul id="ul_B0A97BF0E314495985F44A642C86918D"> 
      <li id="li_4D8BDE32853540809AE78FF5FF5677A1"> <span class="uicontrol"> Tag Meta </span> <p> Basa questa regola su dati numerici o di testo memorizzati in un tag meta denominato sulle pagine del sito Web. </p> </li> 
      <li id="li_4976C31D67254C7F81D554EC49DDBB40"> <span class="uicontrol">  Adobe Analytics Metric (numero) </span> <p>Basa questa regola su una metrica Adobe Analytics  numerica associata alle pagine del sito. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome origine dati </p> </td> 
      <td colname="col2"> <p>Se hai scelto <span class="uicontrol"> Meta Tag </span> come Tipo origine dati, questo è il nome di un tag meta che si trova all'interno delle pagine del tuo sito Web. I nomi nel menu a discesa provengono dall’elenco di valori di metadati definiti configurati in Impostazioni &gt; Metadati &gt; Definizioni. </p> <p>Consultate <a scope="local" href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita"> Aggiunta di un nuovo campo tag meta </a>. </p> <p>Se hai scelto  Adobe Analytics Metric (Number) come Tipo origine dati, questo è il nome di una metrica Adobe Analytics . I nomi nel menu a discesa provengono dall'elenco definito  metriche Adobe Analytics configurate in Impostazioni &gt;  Adobe Analytics &gt; Metriche &gt; Modifica. </p> <p>Consultate <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Modifica delle metriche Adobe Analytics  di una suite di rapporti </a>. </p> <p>Se il nome della metrica Adobe Analytics  selezionata non è già definito in <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span>(Impostazioni &gt; Metadati &gt;Definizioni), vengono visualizzati un campo di testo e un pulsante Add (Aggiungi). Immettete il nome del campo metadati (il nome del campo di metadati non può superare i 20 caratteri), quindi fate clic su <span class="uicontrol"> Aggiungi </span>. </p> <p>Quando si incontrano pagine con più chiavi Adobe Analytics , come con una pagina di prodotto che visualizza più prodotti, Combinazione composita specifica come gestire i valori delle metriche Adobe Analytics  multipli associati a tale pagina. Selezionate una delle seguenti opzioni: </p> <p> 
      <ul id="ul_D6E51748BB3949048A37C1895F2C0A58"> 
      <li id="li_04F00F382A264C96A519B0D975E25E94"> <span class="uicontrol"> Sum </span> <p>Restituisce la somma dei valori delle metriche. </p> </li> 
      <li id="li_FA44219B663F4CC197BD3A094EB84396"> <span class="uicontrol"> Media </span> <p>Restituisce la media dei valori (la somma divisa per il numero di valori). </p> </li> 
      <li id="li_F0EAAE1EA1754FFEB30F611E5550097B"> <span class="uicontrol"> Massimo </span> <p>Restituisce il più grande dei valori. </p> </li> 
      <li id="li_38E3E3F3D9AF4C57803B84B60223FB9D"> <span class="uicontrol"> First </span> <p>Restituisce il valore corrispondente al primo tasto. </p> </li> 
      <li id="li_4AEE470CE6BB4D899E975915EC226624"> <span class="uicontrol">Last (Ultimo)</span> <p>Restituisce il valore corrispondente all'ultima chiave. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Pesi/Condizioni </p> </td> 
      <td colname="col2"> <p>Contiene un semplice numero di peso di una singola regola o un elenco associato di numeri di peso delle regole e condizioni di test. </p> <p>Un numero di peso regola è un valore compreso tra 1 e 10 che indica l'importanza di questa regola di classificazione rispetto alle altre regole di classificazione per determinare il livello complessivo di un documento. Uno spessore maggiore indica un'importanza maggiore. Un peso pari a zero (0) ignora la regola. </p> <p>Scegliete <span class="uicontrol"> Personalizzato </span> dall'elenco a discesa per personalizzare lo spessore della regola per le varie pagine definendo un elenco di coppie di condizioni di spessore regola/test. Le condizioni di test sono frammenti di Perl utilizzati per verificare i valori delle origini dati o variabili globali definite nello script di filtro personalizzato (ad esempio, prezzo, marchio, stagione o visualizzazioni di pagina, come nell'esempio seguente). Se una condizione di test restituisce "true", viene applicato il valore di spessore della regola associata. Se una condizione di test restituisce "false", viene valutata la condizione successiva nell'elenco. <code> 0&nbsp;({price}&nbsp;&gt;&nbsp;50.00)&nbsp;&amp;&amp;&nbsp;({brand}=~/Kuhl/)5&nbsp;{season}&nbsp;=~&nbsp;/Fall/10&nbsp;{pageviews}&nbsp;&gt;&nbsp;1000005 </code>Nell'esempio di spessore/condizione creato personalizzato sopra, lo spessore della regola 0 viene applicato se la prima condizione di test restituisce "true". In altre parole, il prezzo contiene un valore superiore a 50 e il marchio contiene "Kuhl"). Se la prima condizione di test restituisce "false", viene valutata la condizione successiva. Se nessuna delle condizioni precedenti è soddisfatta, viene assegnato lo spessore della regola 5. </p> <p>È sempre necessario specificare lo spessore di una regola senza condizioni alla fine dell'elenco. Se non si esegue questa operazione, la regola ottiene un peso pari a 0 nel caso in cui nessuno dei test di condizione restituisce "true". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valori/Rank </p> </td> 
      <td colname="col2"> <p>È costituito da una delle funzioni integrate di classificazione, oppure da contenuti Origini dati eventualmente presenti con i ranghi desiderati. </p> <p>Se hai scelto <span class="uicontrol"> Adobe Analytics Metric (Number) </span> come Tipo origine dati, viene visualizzato un elenco a discesa con le seguenti opzioni: 
      <ul id="ul_104906B6AA8547BAB6979AA37C4FAB90"> 
      <li id="li_7656A2855A054DB8B64E90FE501517AA"> <span class="uicontrol"> Classificazione automatica per ordine (impostazione predefinita) </span> <p>Calcola un livello basato sulla posizione relativa del documento, in base alla relativa metrica Adobe Analytics . Ad esempio, più vicino è la posizione del documento al documento di primo livello, più alto è il suo rango. </p> </li> 
      <li id="li_1A7D60EA6965434AA6D39B215C158306"> <span class="uicontrol"> Classificazione automatica per valore </span> <p>Calcola un livello in base al valore relativo del documento, in base alla relativa metrica Adobe Analytics . Ad esempio, più il valore del documento è vicino a quello del documento di primo livello, più alto sarà il suo rango. </p> </li> 
      <li id="li_457DE44D6ADA40619DC77220BF12318E"> <span class="uicontrol"> Personalizzato </span> <p>Specifica le impostazioni personalizzate. Ad esempio, un'origine dati con il nome "brand" potrebbe contenere il nome del marchio per un particolare prodotto. Potete specificare l'importanza relativa di ciascun marchio inserendo il relativo elenco con il relativo rango. </p> </li> 
      </ul> </p> <p>I valori di classifica restituiti dai calcoli di Auto-Rank sono compresi tra 0,0 (minimo) e 1,0 (massimo). Non vengono regolati in base agli intervalli definiti per il campo Classifica in Impostazioni &gt; Metadati &gt; Definizioni. </p> <p>Nell'esempio seguente, se l'Origine dati del marchio per un particolare risultato di ricerca corrisponde esattamente a "DKNY", la classificazione applicata per quel risultato è 0,5. In caso contrario, se il marchio è "Levis", la classificazione applicata è 0,1. Il contenuto Origine dati deve corrispondere al valore impostato. In altre parole, se il contenuto Origine dati è "Levis Corp.", non corrisponderà al valore "Levis". Il caso viene ignorato, quindi "DKNY" corrisponde a "dkny" e "Dkny". <code> DKNY&nbsp;0.5 Levis&nbsp;0.1 Lee&nbsp;0.2 </code> </p> <p>Come opzione più avanzata, potete specificare i valori come espressioni regolari. Ad esempio, supponiamo che alcune delle pagine del sito contengano un valore di marchio "Levis" e che altre pagine del sito contengano un valore di marchio "Levis jeans". È possibile utilizzare un'espressione regolare specificata con la parola chiave <code>
        regexp 
      </code>. </p> <p>Consultate <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> <p>Nell'esempio seguente, a un documento dei risultati della ricerca contenente il contenuto del marchio "Levis jeans" viene assegnato un rango pari a 0,1. Come per il confronto standard, per le espressioni regolari viene ignorato il carattere maiuscolo/minuscolo. <code> DKNY&nbsp;0.5 regexp&nbsp;Levis.*&nbsp;0.1 Lee&nbsp;0.2 </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Classifica predefinita </p> </td> 
      <td colname="col2"> <p> Specifica il grado da applicare ai documenti dei risultati di ricerca che non corrispondono ad alcun valore specificato. Nell'esempio precedente, a un documento con risultati di ricerca con un'origine dati "brand" contenente "the gap" viene assegnato il valore di classifica predefinito perché "the gap" non corrisponde ad alcun valore definito. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Note </p> </td> 
      <td colname="col2"> <p>Aggiungete informazioni relative alla definizione della regola di classificazione o del gruppo di regole creato. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   L&#39;intervallo di valori di classificazione validi è normalmente compreso tra -1,0 e 1,0, come illustrato di seguito:

   * `-1.0` è &quot;Classifica minima (visualizza più in basso nei risultati della ricerca).&quot;
   * `0.0` è &quot;Classificazione neutra (non modificate l’ordine dei risultati della ricerca).&quot;
   * `1.0` è &quot;Classificazione massima (visualizzazione superiore nei risultati della ricerca.&quot;

   I gradi definiti devono essere compresi nello stesso intervallo per ogni regola. Gli intervalli di classificazione devono anche corrispondere agli intervalli definiti per il campo Classifica in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   Consultate [Aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)tag meta.

   Vedere anche [Modifica di una regola](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275)di classificazione.
1. Clic **[!UICONTROL Add]**.
1. Per visualizzare in anteprima i risultati dell&#39;aggiunta della regola, fate clic su **[!UICONTROL regenerate your staged site index]** per ricreare l&#39;indice del sito Web in fase.

   Consultate [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Consultate [Esecuzione di un indice incrementale di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica di una regola di classificazione {#task_5EBF55A43D6545FEA46BAE5E586FA275}

Puoi modificare una regola di classificazione esistente già aggiunta.

Consultate [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**Per modificare una regola di classificazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Facoltativo) Se avete creato un gruppo di regole e avete aggiunto delle regole al gruppo, nella **[!UICONTROL Define Ranking Rules]** pagina, nell&#39;elenco a **[!UICONTROL Select Rule Group]** discesa selezionate un gruppo di regole che contiene le regole da modificare.

   Consultate [Aggiunta di un gruppo](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)di regole di classificazione.
1. Nella tabella, sotto l’intestazione della **[!UICONTROL Actions]** colonna, fare clic **[!UICONTROL Edit]** per il nome dell’origine dati da modificare.
1. Nella [!DNL Edit Ranking Rule] pagina, impostate le opzioni desiderate. I campi contrassegnati con un asterisco (*) sono obbligatori.

   Vedere la tabella delle opzioni in [Aggiunta di una regola](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)di classificazione.
1. Clic **[!UICONTROL Save Changes]**.
1. Rigenerate l’indice del sito Web in fase di visualizzazione in anteprima dei risultati della modifica della regola.

   Consultate [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Consultate [Esecuzione di un indice incrementale di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di una regola di classificazione {#task_742A3BCC2A6E4164BE84CC7408807EBB}

È possibile eliminare regole di classificazione che non è più necessario utilizzare.

Consultate [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

Consultate [Aggiunta di un gruppo](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)di regole di classificazione.

**Per eliminare una regola di classificazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Facoltativo) Se avete creato un gruppo di regole e avete aggiunto delle regole al gruppo, nella [!DNL Define Ranking Rules] pagina, nell&#39;elenco a **[!UICONTROL Select Rule Group]** discesa selezionate un gruppo di regole che contiene le regole da eliminare.
1. Nella tabella, sotto l’intestazione della **[!UICONTROL Actions]** colonna, fare clic **[!UICONTROL Delete]** per il nome dell’origine dati da modificare.
1. Sulla [!DNL Delete Ranking Rule] pagina, fate clic su **[!UICONTROL Delete]**.

   Viene nuovamente visualizzata la [!DNL Define Ranking Rules] pagina.
1. Generate di nuovo l&#39;indice del sito Web in fase di visualizzazione in anteprima dei risultati dell&#39;eliminazione della regola.

   Consultate [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Consultate [Esecuzione di un indice incrementale di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Aggiunta di un gruppo di regole di classificazione {#task_B65081B3CC9E4330A7FEE77B7BCD36C8}

Se avete definito più tag meta di tipo &quot;rank&quot;, potete creare raccolte separate di regole da utilizzare nel calcolo dei vari campi di classificazione. È possibile aggiungere un gruppo di regole di classifica, da assegnare poi a uno dei campi Rank definiti.

I gruppi di regole in genere contengono una o più regole aggiunte. Tuttavia, i gruppi di regole possono anche fare riferimento ad altri gruppi di regole. Ad esempio, è possibile creare uno o più gruppi di regole e quindi aggiungere a ciascuno di essi regole utilizzate comunemente. Tali regole vengono quindi condivise durante il calcolo dei diversi gradi.

Consultate [Modifica di un gruppo](../c-about-rules-menu/c-about-ranking-rules.md#task_D3EC0437E47144BC9E754FEF99C725E5)di regole di classificazione.

Consultate [Eliminazione di un gruppo](../c-about-rules-menu/c-about-ranking-rules.md#task_BE5BE01F377843BEA9846E094A07F2EA)di regole di classificazione.

Consultate [Revisione dei gruppi](../c-about-rules-menu/c-about-ranking-rules.md#task_5694459D050C4254A25186038CD66B6E)di regole di classifica.

**Aggiunta di un gruppo di regole di classificazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella [!DNL Define Ranking Rules] pagina, a destra dell’elenco a **[!UICONTROL Select Rule Group]** discesa, fare clic su **[!UICONTROL Add]**.
1. Nella [!DNL Add Ranking Rule Group] pagina, nel **[!UICONTROL Rule Group Name]** campo, digitare un nome univoco per il nuovo gruppo di regole.
1. Nell&#39;elenco a **[!UICONTROL Rank Field Name]** discesa, selezionate il nome di un campo di metadati di classifica da associare al nuovo gruppo di regole. Selezionare **[!UICONTROL None]** se non si desidera assegnare un rango.

   L’elenco dei nomi dei campi con classificazione deriva dalle definizioni di metadati aggiunte in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   Consultate la tabella delle opzioni in [Aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)tag meta.
1. Clic **[!UICONTROL Add]**.
1. Generate di nuovo l&#39;indice del sito Web in fase per visualizzare in anteprima i risultati dell&#39;aggiunta della regola.

   Consultate [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Consultate [Esecuzione di un indice incrementale di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Modifica di un gruppo di regole di classificazione {#task_D3EC0437E47144BC9E754FEF99C725E5}

Potete modificare le impostazioni di un gruppo di regole di classificazione esistente.

Consultate [Aggiunta di un gruppo](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)di regole di classificazione.

**Per modificare un gruppo di regole di classificazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella [!DNL Define Ranking Rules] pagina, a destra dell’elenco a **[!UICONTROL Select Rule Group]** discesa, fare clic su **[!UICONTROL Edit]**.
1. Nella [!DNL Edit Ranking Rule Group] pagina, nel **[!UICONTROL Rule Group Name]** campo, digitare un nome univoco per il gruppo di regole.
1. Nell&#39;elenco a **[!UICONTROL Rank Field Name]** discesa, selezionate il nome di un campo di metadati di livello da associare al gruppo di regole. Selezionare **[!UICONTROL None]** se non si desidera assegnare un rango.

   L’elenco dei nomi dei campi con classificazione deriva dalle definizioni di metadati aggiunte in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   Consultate la tabella delle opzioni in [Aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)tag meta.
1. Clic **[!UICONTROL Save Changes]**.
1. Generate di nuovo l&#39;indice del sito Web in fase per visualizzare in anteprima i risultati dell&#39;aggiunta della regola.

   Consultate [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Consultate [Esecuzione di un indice incrementale di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di un gruppo di regole di classificazione {#task_BE5BE01F377843BEA9846E094A07F2EA}

È possibile eliminare un gruppo di regole di classificazione che non è più necessario né utilizzare. Quando eliminate un gruppo, vengono eliminate anche tutte le regole aggiunte al gruppo. Non è possibile eliminare il gruppo predefinito &quot;Regole di classificazione&quot;.

Il contenuto di qualsiasi gruppo di regole contenuto nel gruppo di eliminazione non viene eliminato; vengono rimossi solo i riferimenti a tali gruppi.

Assicuratevi di reindicizzare il sito Web in modo che la modifica venga riflessa correttamente nei risultati della ricerca.

Consultate [Aggiunta di un gruppo](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)di regole di classificazione.

**Per eliminare un gruppo di regole di classificazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella [!DNL Define Ranking Rules] pagina, nell’elenco a **[!UICONTROL Select Rule Group]** discesa, selezionate un gruppo da eliminare.
1. Nella parte destra dell’elenco a **[!UICONTROL Select Rule Group]** discesa, fare clic su **[!UICONTROL Delete]**.
1. Sulla [!DNL Delete Ranking Rule Group] pagina, fate clic su **[!UICONTROL Delete]**.
1. Generate di nuovo l&#39;indice del sito Web in fase per visualizzare in anteprima i risultati dell&#39;aggiunta della regola.

   Consultate [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Consultate [Esecuzione di un indice incrementale di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Revisione dei gruppi di regole di classifica {#task_5694459D050C4254A25186038CD66B6E}

Puoi utilizzare Panoramica sui gruppi di regole di classificazione per visualizzare ogni gruppo Nome campo classificazione, origine dati e ponderazione associata.

Consultate [Aggiunta di un gruppo](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)di regole di classificazione.

**Per esaminare i gruppi di regole di classifica**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella [!DNL Define Ranking Rules] pagina, a destra dell’elenco a **[!UICONTROL Select Rule Group]** discesa, fare clic su **[!UICONTROL Overview]**.
1. Sulla [!DNL Ranking Rule Groups Overview] pagina, fare clic **[!UICONTROL Close]** per tornare alla [!DNL Define Ranking Rules] pagina.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Verifica delle regole di classificazione {#task_56F64EE7ED5B42E481F0990A9DD98ADB}

Potete fornire un URL adatto per verificare le definizioni delle regole di classificazione configurate. Vengono visualizzate le metriche utilizzate nei calcoli, insieme al valore Rank calcolato.

Vedere [Informazioni sulle regole](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)di classificazione.

**Verifica delle regole di classificazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella [!DNL Define Ranking Rules] pagina, nell’ **[!UICONTROL Test URL]** area, digitate l’URL di una pagina Web nel sito Web.
1. Clic **[!UICONTROL Test]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Regolazione dello spessore associato alle regole di classificazione {#task_3CB6FC92A66F4D99874A42D55825DB64}

È possibile modificare i contributi relativi delle singole regole di classificazione e il contributo di Classificazione ai risultati finali della ricerca.

Se la classificazione non è definita, i risultati della ricerca sono 100% sul **[!UICONTROL Natural Relevance]** lato della barra di scorrimento Regole e rilevanza della **[!UICONTROL Adjust Ranking Weights]** pagina. Questo equilibrio significa semplicemente che i risultati della ricerca vengono ordinati solo in base ai termini di ricerca.

Quando si definisce la classificazione, al campo metadati Classifica associato viene assegnato un valore Rilevanza compreso tra 1 e 10. Un valore pari a 1 indica che il Classificato costituisce il 10% dell&#39;ordine dei risultati della ricerca, mentre il Rank calcolato rappresenta il 90%.

Se in un gruppo Regola sono definite più regole, il valore Peso di ciascuna regola determina la quantità di contributo del risultato della regola alla classifica calcolata totale. Ad esempio, si supponga di avere una rilevanza naturale dell&#39;80%, il che significa che la rilevanza del campo Rank associato è 2. Sono state inoltre definite due regole: uno con un peso di 3 e il secondo con un peso di 7. In tal caso, il primo contributo della regola al risultato finale è del 6% ((3 / (3 + 7)) * 20%). Il secondo contributo della regola al risultato finale è del 14% ((7 / (3+7)) * 20%).

**Per regolare lo spessore associato alle regole di classificazione**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Adjust Weights]**.
1. Nella [!DNL Adjust Ranking Weights] pagina, nell’elenco a **[!UICONTROL Select Rule Group]** discesa, selezionate un gruppo di cui desiderate regolare i pesi di classificazione.
1. Trascinate i cursori per modificare i valori di contributo corrispondenti.

   Il grafico a torta riflette graficamente le modifiche apportate.
1. Clic **[!UICONTROL Save Changes]**.
1. Generate di nuovo l&#39;indice del sito Web in fase per visualizzare in anteprima i risultati dell&#39;aggiunta della regola.

   Consultate [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Consultate [Esecuzione di un indice incrementale di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.
