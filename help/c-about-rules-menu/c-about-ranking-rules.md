---
description: Puoi utilizzare le Regole di classificazione per controllare il posizionamento o la classificazione relativi dei risultati di ricerca di un cliente in base al contenuto di meta tag e alle metriche Adobe Analytics correlate.
solution: Target
subtopic: Ranking Rules
title: Informazioni sulle regole di classificazione
topic: Rules,Site search and merchandising
uuid: 21962f9a-1d9c-442f-a6c4-5f452436c640
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '4621'
ht-degree: 0%

---


# Informazioni sulle regole di classificazione{#about-ranking-rules}

Puoi utilizzare le Regole di classificazione per controllare il posizionamento o la classificazione relativi dei risultati di ricerca di un cliente in base al contenuto di meta tag e alle metriche Adobe Analytics correlate.

## Utilizzo delle regole di classificazione {#concept_F555C076759B4E81B925441CFE707397}

È possibile definire regole di classificazione che influiscono sul posizionamento relativo dei documenti all’interno dei risultati della ricerca, in base al contenuto di ciascun documento. Puoi basare le regole di classificazione sul contenuto dei metadati, sulle metriche di Adobe Analytics (se il tuo account è configurato per funzionare con Adobe Analytics) o sulle metriche di Adobe Analytics HBX (se il tuo account è configurato per funzionare con Adobe Analytics HBX).

È possibile impostare pagine web che contengono meta tag con le caratteristiche desiderate, ad esempio un determinato nome o prezzo del marchio, o pagine web che desiderano che gli indicatori prestazioni chiave di Adobe Analytics, come i visualizzatori unici, ricevano una classificazione più alta rispetto alle pagine web che non lo fanno. Le caratteristiche &quot;desiderabili&quot; sono facilmente aggiornate aggiungendo o modificando regole di classificazione e reindicizzando il tuo sito web.

Se sono definiti più meta tag di tipo &quot;rank&quot;, è possibile creare raccolte separate di regole da utilizzare nel calcolo dei vari campi di classificazione. Puoi aggiungere un gruppo di regole di classificazione, che puoi quindi assegnare a uno dei campi Classifica definiti. I gruppi di regole contengono normalmente una o più definizioni di regole, ma possono anche fare riferimento ad altri gruppi di regole, in modo da poter creare uno o più gruppi di regole di uso comune condivisi durante il calcolo dei diversi ranghi.

Consulta [Aggiunta di un gruppo di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

Un valore di classificazione positivo promuove i risultati della ricerca verso l’alto; un valore di classificazione negativo deduce i risultati della ricerca verso la parte inferiore dei risultati della ricerca. L’intervallo normale per i valori di classificazione è 1,0, ovvero la promozione massima all’interno dei risultati di ricerca, mentre -1,0 è la degradazione massima. Anche se è possibile personalizzare questo intervallo modificando il campo Classifica nelle definizioni dei metadati, questo tipo di personalizzazione non è in genere necessario.

Vedere [Informazioni sulle definizioni](../c-about-settings-menu/c-about-metadata-menu.md#concept_AE48035C210145169BE067D396975620).

Se hai definito più di un campo di classificazione in Impostazioni > Metadati > Definizioni, puoi creare set aggiuntivi di regole di classificazione, una per ciascun campo di classificazione. È possibile definire set aggiuntivi di regole di classificazione senza essere direttamente associati a un campo di classificazione. Questa flessibilità ti consente di creare set di regole comuni che possono essere condivisi nel calcolo di uno o più valori di classificazione.

**Importante**: Prima di poter utilizzare le Regole di classificazione, è necessario completare diversi passaggi di configurazione dell’account.

Consulta [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)

## Configurazione della classificazione {#task_4CEBC13925B047FC95BDC217B48089C5}

Prima di poter utilizzare le regole di classificazione, è necessario completare diversi passaggi di configurazione dell’account.

**Per configurare la classificazione**

1. Scegli una delle seguenti opzioni:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Attività </p> </th> 
      <th colname="col2" class="entry"> <p>Configurazione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Creazione di regole di classificazione basate sui tag meta </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_28ABB980143948DFA79AC4360AAB7556"> 
      <li id="li_544075CFA0964C6F8FAF7941AAA9ECCC"> Nel menu del prodotto, fai clic su <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Definizioni </span>. </li> 
      <li id="li_F237F13B89E8425080C15D3BD697652C"> Nella pagina Definizioni fare clic su <span class="uicontrol"> Aggiungi nuovo campo </span>. </li> 
      <li id="li_2A839874D71D45FEA661B3D3B8BE2A86"> Nella pagina Aggiungi campo digitare il campo di testo <span class="uicontrol"> Nome campo </span> 
      <code>
        rank 
      </code>; nel campo di testo <span class="uicontrol"> Meta Tag Name </span> , digita 
      <code>
        rank 
      </code>; nell’elenco a discesa <span class="uicontrol"> Tipo di dati </span> , seleziona <span class="uicontrol"> Classifica </span>. Lascia invariate tutte le altre opzioni di campo. <p>Vedi il parametro di query <span class="codeph"> sp_sr </span> in <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Parametri CGI di ricerca back-end </a>. </p> </li> 
      <li id="li_8E91AF4BE51A4A41ABBF9680DDE0B7CE">Fai clic su <span class="uicontrol">Aggiungi </span>. </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Creazione di regole di classificazione basate sulle metriche di Adobe Analytics </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_BE57CBC303D941778B10D855ADC93C68"> 
      <li id="li_8DF5D8F924B24ECBBD2D93C76C69D00C"> Assicurati di aver configurato l’autenticazione Adobe Analytics dall’interno di ricerca/merchandising del sito. <p>Consulta <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42" type="task" format="dita" scope="local"> Configurazione dell’autenticazione delle metriche Adobe Analytics </a>. </p> </li> 
      <li id="li_CF7DD073FC5A432DADBD282AA8BB9920"> Seleziona e aggiungi una suite di rapporti disponibile. <p>Consulta <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0" type="task" format="dita" scope="local"> Aggiunta di una suite di rapporti Adobe Analytics </a>. </p> </li> 
      <li id="li_9A63448577D04E028DF211D8715F943A"> Configura l’elenco delle metriche di Adobe Analytics che desideri rendere disponibili per la creazione di nuove regole di classificazione. <p>Consulta <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Modifica delle metriche Adobe Analytics di una suite di rapporti </a>. </p> </li> 
      <li id="li_1ACA3611D9B44AC394604CD89209C966"> Carica le metriche Adobe Analytics iniziali per le pagine del sito web. <p>Consulta <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181" type="task" format="dita" scope="local"> Caricamento di dati Adobe Analytics </a>. </p> </li> 
      </ol> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Aggiungi una o più regole di classificazione.

   Consulta [Aggiunta di una regola di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

1. Fai clic su **[!UICONTROL regenerate your staged site index]** per eseguire un reindice completo del sito web (da **[!UICONTROL Index]** > **[!UICONTROL Full Index]**).

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. Controlla i valori nella colonna Classifica in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** per verificare che le regole di classificazione siano state applicate correttamente.

## Informazioni sulla classificazione dei documenti per età {#topic_770815CF1B2A491F83FF765871B6F1B8}

È possibile classificare un documento HTML in base alla sua età con una funzione di decadimento esponenziale. Il tasso di decadimento è specificato con una costante mezza vita scelta, la quantità di tempo che deve passare prima che il valore scenda a metà del suo valore iniziale.

La classificazione dell’età si basa sulle due equazioni seguenti:

`K = -ln(2) / H`

`RANK = e^(K * T)`

Le variabili `H` e `T` sono input di questa funzione: `H` è il periodo di emivita desiderato e `T` è l&#39;età del documento, espressa in secondi. `K` è la mezza vita calcolata ed  `RANK` è il decadimento esponenziale del valore di età specificato. Il valore risultante è compreso tra 0 e 1. Un documento più recente ha un valore di classificazione più vicino a 1 rispetto a un documento precedente. In teoria, i documenti non dovrebbero mai raggiungere il valore 0, ma gli errori di arrotondamento possono causare un risultato pari a 0.

## Requisiti per l&#39;uso della classificazione dell&#39;età {#section_D716507D589442C6B7848892BD28F966}

* Il tuo account deve già essere configurato correttamente per la classificazione. Se non è configurato, consulta [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).
* Il documento HTML deve avere un campo meta tag HTML che rappresenta la data di nascita, l’inizio come timestamp o un altro valore di data significativo.
* La funzione speciale incorporata `search_get_age_rank()`, specificata nelle pagine Aggiungi o Modifica regola di classificazione, viene utilizzata per calcolare la classificazione di età di un documento. Le sezioni successive descrivono in dettaglio l&#39;uso generale della funzione di classificazione dell&#39;età. Viene inoltre presentato un esempio che illustra la funzione di classificazione dell’età.

## Utilizzo di search_get_age_rank () nella pagina Aggiungi regola di classificazione o nella pagina Modifica regola di classificazione {#section_34BC5276F2AB4419AD92872A397CA0AF}

Specificare `search_get_age_rank()` come segue:

`search_get_age_rank(Birthdate#Half_Life#Default_Rank)`

* Data di nascita: la data di nascita o la data di inizio del file deve essere una stringa formattata per la data in base ai formati di data del campo. Questa stringa formattata per la data deve essere un riferimento di campo, come in `{field_name}`.
* Half_Life - La mezza durata è la quantità di tempo che deve trascorrere prima che il valore scenda a metà del valore iniziale. Questo valore è espresso nel numero di giorni ed è un numero intero o un numero a virgola mobile.
* Default_Rank - Il rango predefinito viene utilizzato come rete di sicurezza nel caso in cui la data di nascita non sia valida o la data sia futura. Non è possibile utilizzare questo valore predefinito se anche il relativo campo di metadati associato presenta un valore predefinito valido. Il valore qui è un numero a virgola mobile o un numero intero. Consulta di seguito per suggerimenti in caso di problemi con cui viene utilizzato il valore predefinito.

Consulta [Aggiunta di una regola di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

Consulta [Modifica di una regola di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275).

**Esempio**

Nell&#39;esempio seguente:

`search_get_age_rank({birthdate}#28#0.20)`

la data contenuta nel campo `birthdate` del documento viene passata come timestamp. La mezza vita è di 28 giorni. Il valore di classificazione predefinito è 0,20 se la data non è valida.

Vedi la tabella delle opzioni in [Aggiunta di una regola di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

Nella sezione Valori/blocchi della pagina Aggiungi regola di classificazione o della pagina Modifica regola di classificazione è possibile utilizzare solo `search_get_age_rank` con regole personalizzate. Pertanto, assicurati di scegliere **Personalizzato** dall&#39;elenco a discesa Valori/Classificazioni. Quando la regola utilizza la funzione di classificazione dell&#39;età, non sono consentiti spazi nella parte dei valori della regola. Assicurati che non ci siano spazi negli argomenti della funzione o tra essi. E non ci sono spazi tra operatori matematici o condizionali.

Di seguito è riportato un esempio di regola dei valori/dei ranking, una regola associata a un campo di testo:

`regexp .* search_get_age_rank({other_field}#365#0.20)`

Questo esempio presuppone che `other_field` contenga un valore di data. Se questo campo non è di per sé un campo di tipo data, questo valore viene interpretato utilizzando i formati data associati al campo Data predefinito. In caso contrario, vengono utilizzati i formati data di questo campo. Questa voce di valori/ranks viene utilizzata ogni volta che il campo del documento, che l&#39;origine dati della regola identifica, non è vuoto e il valore restituito dalla funzione (da 0 a 1) è la classificazione assegnata.

Per una regola associata a un campo Numerico, in particolare un campo Data:

`9999999999 search_get_age_rank({other_field}#365#0.20)`

Durante l’elaborazione di ciascun documento, il valore in `other_field` viene convertito nel modulo Unix &quot;epoch&quot;, utilizzando le definizioni del formato data del campo. Questo valore viene utilizzato nella chiamata `search_get_age_rank()` . Poiché ogni valore &quot;epoch&quot; è inferiore a 99999999999 (almeno per ora), la regola fornisce semplicemente il valore restituito dalla funzione (da 0 a 1) come rango.

In entrambi gli esempi precedenti, è tipico che l&#39;origine dati della regola sia lo stesso campo utilizzato nella funzione `search_get_age_rank()` - `other_field` in questo caso.

## Un esempio di integrazione della classificazione dell&#39;età nelle regole di classificazione {#section_A86D909687CC45E19D4EA7A4A9283F28}

Di seguito è riportato un esempio di come integrare la classificazione delle età nelle regole di classificazione. L’esempio mostra anche i risultati non elaborati della funzione di classificazione dell’età e i risultati delle regole di classificazione. L&#39;esempio presuppone quanto segue:

* Le pagine web sottoposte a ricerca per indicizzazione hanno il meta tag HTML denominato &quot;compleato&quot;. Il contenuto di questo tag è una marca temporale relativa al documento.
* Le definizioni dei metadati dispongono di un campo metatag definito per il tag di data di nascita. Questo campo è impostato su &quot;date&quot;.

**Regole di classificazione**

Consulta [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

Ora aggiungi una nuova regola di classificazione. La regola è definita per utilizzare il campo &quot;data di nascita&quot; sul documento. Viene aggiunta una nuova regola di classificazione con le seguenti proprietà impostate:

* Tipo di origine dati: Tag Meta
* Nome origine dati: compleanno
* Peso/Condizioni: 10 - Importanza massima
* Valori/spazi: 9999999999 search_get_age_rank({data di nascita}#14#0.10)
* Classificazione predefinita: -1

La regola fa diverse cose. Il peso della regola è impostato su 10. Il valore di classificazione è semplicemente il risultato della funzione di classificazione dell&#39;età, un valore da 0 a 1. Non è possibile utilizzare spazi con `search_get_age_rank()`. Inoltre, notare che il campo &quot;compleanni&quot; è racchiuso tra parentesi. Infine, quando salvi questa regola, le virgole nella definizione Valori/Ranks vengono sostituite con caratteri `#`; questo comportamento è normale.

**Visualizzazione dei risultati**

Utilizza la funzione Visualizzazione dati per vedere rapidamente i risultati della funzione di classificazione età. Aggiungi i campi metadati appropriati. Nell’esempio, `age_val` e `myrank` sono i due campi Metadati che devono essere aggiunti alla visualizzazione dati. Il campo `myrank` mostra in che modo la classificazione dell’età influisce sui valori di classificazione. Il campo `age_val` mostra l&#39;output non elaborato della funzione di decadimento esponenziale per quel documento.

## Valori predefiniti {#section_CB109EF78F914E92955D512ACFC3310E}

Di seguito sono riportati tre valori predefiniti coinvolti nella funzione `search_get_age_rank()`:

* Il valore predefinito che è possibile immettere nella funzione `search_get_age_rank()` stessa.
* Il valore di classificazione predefinito dalla regola di classificazione.
* Il valore predefinito dalla definizione di metadati.

A seconda di dove si verifica l’errore, è possibile ottenere valori predefiniti diversi.

Ad esempio, se la funzione Classifica e Filtro è implementata correttamente, il valore predefinito della definizione dei metadati non deve mai verificarsi. Questo valore predefinito è l’ultimo valore di risorsa se non esiste alcun contenuto valido o noto per quel campo Metadati. Il valore predefinito dalle regole di classificazione può essere visualizzato quando `search_get_age_rank()` fa riferimento al proprio tag associato e il tag è mancante nel documento. In questo caso, questa regola va direttamente al valore predefinito della regola. Se la funzione di classificazione dell&#39;età fa riferimento al tag di un&#39;altra regola di classificazione, è possibile che il valore predefinito passato in quella funzione di classificazione dell&#39;età venga utilizzato se il tag di riferimento è mancante o non valido.

## Aggiunta di una regola di classificazione {#task_A132789FD4E5423DAD090DCDA7311E8A}

È possibile aggiungere [!DNL Ranking Rules] per influenzare il posizionamento relativo delle pagine web all’interno dei risultati di ricerca, in base al contenuto di ogni pagina web.

Consulta [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**Per aggiungere una regola di classificazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Facoltativo) Se hai creato un gruppo di regole e aggiunto regole al gruppo, nella pagina [!DNL Define Ranking Rules], nell&#39;elenco a discesa **[!UICONTROL Select Rule Group]** , seleziona un gruppo di regole contenente le regole che desideri modificare.

   Consulta [Aggiunta di un gruppo di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).
1. Nella pagina [!DNL Define Ranking Rules] , fai clic su **[!UICONTROL Add Rule]** per aggiungere una nuova regola di classificazione o per aggiungere un riferimento a un set di regole.
1. Nella pagina [!DNL Add Ranking Rule] , imposta le opzioni desiderate. I campi contrassegnati con un asterisco (*) sono obbligatori.

   Il tipo di origine dati selezionato influisce sulle scelte disponibili nell&#39;elenco a discesa [!DNL Data Source Name] . Ad esempio, se hai selezionato **[!UICONTROL Meta Tag]** come Tipo di origine dati, il Nome origine dati fa riferimento al nome di un tag meta sulle pagine del sito web. Se hai selezionato **[!UICONTROL Adobe Analytics Metric (Number)]**, il Nome origine dati fa riferimento a uno dei nomi delle metriche Adobe Analytics selezionati in una suite di rapporti, come trovato nella pagina **[!UICONTROL Edit Adobe Analytics Metrics]** in ricerca/merchandising del sito.

   Consulta [Modifica delle metriche Adobe Analytics di una suite di rapporti](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Tipo di origine dati </p> </td> 
      <td colname="col2"> <p>Determina le caratteristiche dell’origine dati utilizzata come input per questa regola di classificazione. </p> <p>I tipi di origine dati selezionabili sono i seguenti: 
      <ul id="ul_B0A97BF0E314495985F44A642C86918D"> 
      <li id="li_4D8BDE32853540809AE78FF5FF5677A1"> <span class="uicontrol"> Tag Meta  </span> <p> Basa questa regola su dati numerici o di testo memorizzati all’interno di un tag meta denominato sulle pagine del sito web. </p> </li> 
      <li id="li_4976C31D67254C7F81D554EC49DDBB40"> <span class="uicontrol"> Metrica Adobe Analytics (numero)  </span> <p>Basa questa regola su una metrica Adobe Analytics numerica associata alle pagine del sito. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome origine dati </p> </td> 
      <td colname="col2"> <p>Se hai scelto <span class="uicontrol"> Meta Tag </span> come tipo di origine dati, questo è il nome di un tag meta che si trova nelle pagine del tuo sito web. I nomi nel menu a discesa provengono dall'elenco dei valori di metadati definiti configurati in Impostazioni &gt; Metadati &gt; Definizioni. </p> <p>Consulta <a scope="local" href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita"> Aggiunta di un nuovo campo meta tag </a>. </p> <p>Se hai scelto Adobe Analytics Metric (Number) come tipo di origine dati, questo è il nome di una metrica Adobe Analytics. I nomi nel menu a discesa provengono dall’elenco definito per le metriche disponibili di Adobe Analytics configurate in Impostazioni &gt; Adobe Analytics &gt; Metriche &gt; Modifica. </p> <p>Consulta <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Modifica delle metriche Adobe Analytics di una suite di rapporti </a>. </p> <p>Se il nome della metrica Adobe Analytics selezionato non è già definito in <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Definizioni </span>, vengono visualizzati un campo di testo e un pulsante Aggiungi. Immetti il nome del campo metadati (il nome del campo metadati non può superare i 20 caratteri), quindi fai clic su <span class="uicontrol"> Aggiungi </span>. </p> <p>Quando si incontrano pagine con più chiavi Adobe Analytics, come con una pagina di prodotto che visualizza più prodotti, Combinazione composita specifica come gestire i diversi valori di metrica Adobe Analytics associati a tale pagina. Selezionare una delle seguenti opzioni: </p> <p> 
      <ul id="ul_D6E51748BB3949048A37C1895F2C0A58"> 
      <li id="li_04F00F382A264C96A519B0D975E25E94"> <span class="uicontrol"> Somma  </span> <p>Restituisce la somma dei valori delle metriche. </p> </li> 
      <li id="li_FA44219B663F4CC197BD3A094EB84396"> <span class="uicontrol"> Media  </span> <p>Restituisce la media dei valori (la somma divisa per il numero di valori). </p> </li> 
      <li id="li_F0EAAE1EA1754FFEB30F611E5550097B"> <span class="uicontrol"> Massimo  </span> <p>Restituisce il più grande tra i valori. </p> </li> 
      <li id="li_38E3E3F3D9AF4C57803B84B60223FB9D"> <span class="uicontrol"> Primo  </span> <p>Restituisce il valore corrispondente alla prima chiave. </p> </li> 
      <li id="li_4AEE470CE6BB4D899E975915EC226624"> <span class="uicontrol">Last (Ultimo)</span> <p>Restituisce il valore corrispondente all’ultima chiave. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Peso/Condizioni </p> </td> 
      <td colname="col2"> <p>Contiene un numero di peso di una singola regola semplice o un elenco abbinato di numeri di peso di regole e condizioni di test. </p> <p>Un numero di peso della regola è un valore compreso tra 1 e 10 che indica l’importanza di questa regola di classificazione rispetto alle altre regole di classificazione per determinare il rango complessivo di un documento. Un maggiore peso della regola indica maggiore importanza. Un valore pari a zero (0) ignora la regola. </p> <p>Scegli <span class="uicontrol"> Personalizzato </span> dall'elenco a discesa per personalizzare il peso della regola per varie pagine definendo un elenco di coppie di condizioni di ponderazione della regola/test. Le condizioni di test sono frammenti di Perl utilizzati per testare i valori delle origini dati o variabili globali definite nello script di filtro personalizzato (ad esempio, prezzo, marchio, stagione o visualizzazioni di pagina, come nell’esempio seguente). Se una condizione di test restituisce "true", viene applicato il valore di peso della regola associata. Se una condizione di test restituisce "false", viene valutata la condizione successiva nell’elenco. <code> 0&nbsp;({price}&nbsp;&gt;&nbsp;50.00)&nbsp;&amp;&amp;&nbsp;({brand}=~/Kuhl/)5&nbsp;{season}&nbsp;=~&nbsp;/Fall/10&nbsp;{pageviews}&nbsp;&gt;&nbsp;1000005 </code>Nell’esempio di peso/condizione creato personalizzato sopra, il peso della regola 0 viene applicato se la prima condizione di test restituisce "true". Cioè, il prezzo contiene un valore superiore a 50 e il marchio contiene "Kuhl"). Se la prima condizione di test restituisce "false", viene valutata la condizione successiva. Se nessuna delle condizioni precedenti è soddisfatta, viene assegnato il peso della regola 5. </p> <p>È sempre necessario fornire un peso della regola senza alcuna condizione alla fine dell’elenco. In caso contrario, la regola ottiene un peso pari a 0 nel caso in cui nessuno dei test di condizione restituisca "true". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Valori/Classificazioni </p> </td> 
      <td colname="col2"> <p>È costituito da una delle funzioni di classificazione integrate o da un possibile contenuto Origine dati insieme ai ranghi desiderati. </p> <p>Se hai scelto <span class="uicontrol"> Metrica Adobe Analytics (Numero) </span> come tipo di origine dati, ti viene presentato un elenco a discesa con le seguenti opzioni: 
      <ul id="ul_104906B6AA8547BAB6979AA37C4FAB90"> 
      <li id="li_7656A2855A054DB8B64E90FE501517AA"> <span class="uicontrol"> Classificazione automatica per ordine (predefinito)  </span> <p>Calcola una classificazione basata sulla posizione relativa del documento, in base alla metrica Adobe Analytics. Ad esempio, più il documento è in posizione superiore, più il documento è in posizione più alta. </p> </li> 
      <li id="li_1A7D60EA6965434AA6D39B215C158306"> <span class="uicontrol"> Classificazione automatica per valore  </span> <p>Calcola una classificazione in base al valore relativo del documento, in base alla metrica Adobe Analytics. Ad esempio, più il valore del documento è vicino al valore del documento di primo livello, più alto è il suo rango. </p> </li> 
      <li id="li_457DE44D6ADA40619DC77220BF12318E"> <span class="uicontrol"> Personalizzato </span> <p>Specifica le impostazioni personalizzate. Ad esempio, un’origine dati con il nome di "marchio" potrebbe contenere il nome del marchio per un particolare prodotto. Puoi specificare l’importanza relativa di ogni marchio inserendola insieme al relativo rango. </p> </li> 
      </ul> </p> <p>I valori di classificazione restituiti dai calcoli di Classificazione automatica sono compresi tra 0,0 (il più basso) e 1,0 (il più alto). Non vengono regolati in base agli intervalli definiti per il campo Classifica in Impostazioni &gt; Metadati &gt; Definizioni. </p> <p>Nell’esempio seguente, se l’origine dati del brand per un particolare risultato di ricerca corrisponde esattamente a "DKNY", la classificazione applicata per quel risultato è 0,5. In caso contrario, se il marchio è "Levis", la classificazione applicata è 0,1. Il contenuto Origine dati deve corrispondere al valore impostato. In altre parole, se il contenuto Origine dati è "Levis Corp.", non corrisponderà al valore "Levis". Il caso viene ignorato, quindi "DKNY" corrisponde a "dkny" e "Dkny". <code> DKNY&nbsp;0.5 Levis&nbsp;0.1 Lee&nbsp;0.2 </code> </p> <p>Come opzione più avanzata, puoi specificare i valori come espressioni regolari. Ad esempio, supponiamo che alcune pagine del sito contengano un valore di marchio "Levis" e che altre pagine del sito contengano un valore di marchio "Levis jeans". È possibile utilizzare un'espressione regolare specificata con la parola chiave 
      <code>
        regexp 
      </code>. </p> <p>Consulta <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> <p>Nell’esempio seguente, a un documento dei risultati di ricerca contenente il contenuto del marchio "Levis jeans" viene assegnato un rango di 0,1. Come per il confronto standard, le espressioni regolari vengono ignorate in base al caso. <code> DKNY&nbsp;0.5 regexp&nbsp;Levis.*&nbsp;0.1 Lee&nbsp;0.2 </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Classificazione predefinita </p> </td> 
      <td colname="col2"> <p> Specifica la classificazione da applicare ai documenti dei risultati di ricerca che non corrispondono a nessuno dei valori specificati. Nell’esempio precedente, a un documento dei risultati di ricerca con un’origine dati "brand" contenente "the gap" viene assegnato il valore di classificazione predefinito, perché "the gap" non corrisponde a nessuno dei valori definiti. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Note </p> </td> 
      <td colname="col2"> <p>Aggiungi informazioni relative alla definizione della regola di classificazione o al gruppo di regole creato. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   L&#39;intervallo di valori di classificazione validi è normalmente da -1.0 a 1.0 come nell&#39;esempio seguente:

   * `-1.0` è &quot;Classificazione minima (mostra più in basso nei risultati della ricerca)&quot;.
   * `0.0` è &quot;Classificazione neutra (non modificare l’ordine dei risultati della ricerca)&quot;.
   * `1.0` è &quot;Classificazione massima (visualizza più in alto nei risultati della ricerca.&quot;

   I ranghi definiti devono rientrare nello stesso intervallo per ogni regola. Gli intervalli di classificazione devono inoltre corrispondere agli intervalli definiti per il campo Classifica in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   Consulta [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

   Vedere anche [Modifica di una regola di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275).
1. Clic **[!UICONTROL Add]**.
1. Per visualizzare in anteprima i risultati dell’aggiunta della regola, fai clic su **[!UICONTROL regenerate your staged site index]** per ricostruire l’indice del sito web in staging.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di una regola di classificazione {#task_5EBF55A43D6545FEA46BAE5E586FA275}

Puoi modificare una regola di classificazione esistente già aggiunta.

Consulta [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**Per modificare una regola di classificazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Facoltativo) Se hai creato un gruppo di regole e aggiunto delle regole al gruppo, nella pagina **[!UICONTROL Define Ranking Rules]**, nell&#39;elenco a discesa **[!UICONTROL Select Rule Group]** , seleziona un gruppo di regole contenente le regole che desideri modificare.

   Consulta [Aggiunta di un gruppo di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).
1. Nella tabella, sotto l’intestazione di colonna **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Edit]** per il nome dell’origine dati che si desidera modificare.
1. Nella pagina [!DNL Edit Ranking Rule] , imposta le opzioni desiderate. I campi contrassegnati con un asterisco (*) sono obbligatori.

   Vedi la tabella delle opzioni in [Aggiunta di una regola di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).
1. Clic **[!UICONTROL Save Changes]**.
1. Ricostruisci l’indice del sito web di staging per visualizzare in anteprima i risultati della modifica della regola.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di una regola di classificazione {#task_742A3BCC2A6E4164BE84CC7408807EBB}

È possibile eliminare regole di classificazione che non è più necessario utilizzare.

Consulta [Configurazione della classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

Consulta [Aggiunta di un gruppo di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**Per eliminare una regola di classificazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Facoltativo) Se hai creato un gruppo di regole e aggiunto delle regole al gruppo, nella pagina [!DNL Define Ranking Rules], nell&#39;elenco a discesa **[!UICONTROL Select Rule Group]** , seleziona un gruppo di regole contenente le regole che desideri eliminare.
1. Nella tabella, sotto l’intestazione di colonna **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Delete]** per il nome dell’origine dati che si desidera modificare.
1. Nella pagina [!DNL Delete Ranking Rule], fai clic su **[!UICONTROL Delete]**.

   Viene nuovamente visualizzata la pagina [!DNL Define Ranking Rules].
1. Ricostruisci l’indice del sito web di staging per visualizzare in anteprima i risultati dell’eliminazione della regola.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Aggiunta di un gruppo di regole di classificazione {#task_B65081B3CC9E4330A7FEE77B7BCD36C8}

Se hai definito più di un meta tag di tipo &quot;rank&quot;, puoi creare raccolte separate di regole da utilizzare nel calcolo dei vari campi di classificazione. Puoi aggiungere un gruppo di regole di classificazione, che puoi quindi assegnare a uno dei campi Classifica definiti.

I gruppi di regole in genere contengono una o più regole aggiunte. Tuttavia, i gruppi di regole possono anche fare riferimento ad altri gruppi di regole. Ad esempio, puoi creare uno o più gruppi di regole e quindi aggiungere a ciascuno di essi le regole di uso comune. Tali regole vengono quindi condivise durante il calcolo dei diversi ranghi.

Consulta [Modifica di un gruppo di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_D3EC0437E47144BC9E754FEF99C725E5).

Vedere [Eliminazione di un gruppo di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_BE5BE01F377843BEA9846E094A07F2EA).

Consulta [Revisione dei gruppi di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_5694459D050C4254A25186038CD66B6E).

**Per aggiungere un gruppo di regole di classificazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella pagina [!DNL Define Ranking Rules], a destra dell’elenco a discesa **[!UICONTROL Select Rule Group]** , fai clic su **[!UICONTROL Add]**.
1. Nella pagina [!DNL Add Ranking Rule Group], digita un nome univoco per il nuovo gruppo di regole nel campo **[!UICONTROL Rule Group Name]** .
1. Nell’elenco a discesa **[!UICONTROL Rank Field Name]** , seleziona il nome di un campo di metadati di classificazione da associare al nuovo gruppo di regole. Selezionare **[!UICONTROL None]** se non si desidera assegnare un rango.

   L’elenco dei nomi dei campi di classificazione proviene dalle definizioni dei metadati aggiunte in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   Vedi la tabella delle opzioni in [Aggiunta di un nuovo campo tag meta](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Clic **[!UICONTROL Add]**.
1. Ricostruisci l’indice del sito web di staging per visualizzare in anteprima i risultati dell’aggiunta della regola.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Modifica di un gruppo di regole di classificazione {#task_D3EC0437E47144BC9E754FEF99C725E5}

Puoi modificare le impostazioni di un gruppo di regole di classificazione esistente.

Consulta [Aggiunta di un gruppo di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**Per modificare un gruppo di regole di classificazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella pagina [!DNL Define Ranking Rules], a destra dell’elenco a discesa **[!UICONTROL Select Rule Group]** , fai clic su **[!UICONTROL Edit]**.
1. Nella pagina [!DNL Edit Ranking Rule Group], digita un nome univoco per il gruppo di regole nel campo **[!UICONTROL Rule Group Name]** .
1. Nell’elenco a discesa **[!UICONTROL Rank Field Name]** , seleziona il nome di un campo di metadati di classificazione da associare al gruppo di regole. Selezionare **[!UICONTROL None]** se non si desidera assegnare un rango.

   L’elenco dei nomi dei campi di classificazione proviene dalle definizioni dei metadati aggiunte in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   Vedi la tabella delle opzioni in [Aggiunta di un nuovo campo tag meta](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Clic **[!UICONTROL Save Changes]**.
1. Ricostruisci l’indice del sito web di staging per visualizzare in anteprima i risultati dell’aggiunta della regola.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di un gruppo di regole di classificazione {#task_BE5BE01F377843BEA9846E094A07F2EA}

È possibile eliminare un gruppo di regole di classificazione che non è più necessario o utilizzato. Quando elimini un gruppo, vengono eliminate anche tutte le Regole aggiunte al gruppo. Non è possibile eliminare il gruppo predefinito &quot;Regole di classificazione&quot;.

Il contenuto di qualsiasi gruppo di regole contenuto nel gruppo di eliminazione non viene eliminato; vengono rimossi solo i riferimenti a tali gruppi.

Assicurati di reindicizzare il sito web in modo che la modifica si rifletta correttamente nei risultati della ricerca.

Consulta [Aggiunta di un gruppo di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**Per eliminare un gruppo di regole di classificazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella pagina [!DNL Define Ranking Rules], nell’elenco a discesa **[!UICONTROL Select Rule Group]** , seleziona il gruppo da eliminare.
1. A destra dell’elenco a discesa **[!UICONTROL Select Rule Group]** , fai clic su **[!UICONTROL Delete]**.
1. Nella pagina [!DNL Delete Ranking Rule Group], fai clic su **[!UICONTROL Delete]**.
1. Ricostruisci l’indice del sito web di staging per visualizzare in anteprima i risultati dell’aggiunta della regola.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Verifica dei gruppi di regole di classificazione {#task_5694459D050C4254A25186038CD66B6E}

Puoi utilizzare Panoramica dei gruppi di regole di classificazione per visualizzare ogni gruppo Nome campo di classificazione e origine dati e ponderazione associate.

Consulta [Aggiunta di un gruppo di regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**Per esaminare i gruppi di regole di classificazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella pagina [!DNL Define Ranking Rules], a destra dell’elenco a discesa **[!UICONTROL Select Rule Group]** , fai clic su **[!UICONTROL Overview]**.
1. Nella pagina [!DNL Ranking Rule Groups Overview] , fai clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL Define Ranking Rules].
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Verifica delle regole di classificazione {#task_56F64EE7ED5B42E481F0990A9DD98ADB}

Puoi fornire un test URL adatto alle definizioni delle regole di classificazione configurate. Vengono visualizzate le metriche utilizzate nei calcoli, insieme al valore Rank calcolato.

Consulta [Informazioni sulle regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

**Verifica delle regole di classificazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Nella pagina [!DNL Define Ranking Rules] , digita l’URL di una pagina web presente sul sito web nell’area **[!UICONTROL Test URL]** .
1. Clic **[!UICONTROL Test]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Regolazione del peso associato alle regole di classificazione {#task_3CB6FC92A66F4D99874A42D55825DB64}

Puoi modificare i contributi relativi delle singole Regole di classificazione e il contributo di Classifica ai risultati finali della ricerca.

Quando la classificazione non è definita, i risultati della ricerca sono 100% sul lato **[!UICONTROL Natural Relevance]** della barra degli strumenti Regole e rilevanza nella pagina **[!UICONTROL Adjust Ranking Weights]**. Questo equilibrio significa semplicemente che i risultati della ricerca sono ordinati solo in base ai termini di ricerca.

Quando si definisce il ranking, al campo metadati Classifica associato viene assegnato un valore di pertinenza compreso tra 1 e 10. Il valore 1 indica che la Classifica calcolata costituisce il 10% dell’ordinamento dei risultati della ricerca e la Rilevanza Naturale il restante 90%.

Se in un gruppo di regole sono definite più regole, il valore Peso di ciascuna regola determina quanto il risultato di tale regola contribuisce al punteggio totale calcolato. Ad esempio, supponi di avere una rilevanza naturale dell’80%, il che significa che la rilevanza del campo Rank associato è 2. Hai inoltre definito due regole: uno con un peso di 3 e il secondo con un peso di 7. In tal caso, il contributo della prima regola al risultato finale è del 6% ((3 / (3+7)) * 20%). Il contributo della seconda regola al risultato finale è del 14% ((7 / (3+7)) * 20%).

**Per regolare il peso associato alle regole di classificazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Adjust Weights]**.
1. Nella pagina [!DNL Adjust Ranking Weights], nell’elenco a discesa **[!UICONTROL Select Rule Group]** , seleziona un gruppo di cui desideri regolare i pesi di classificazione.
1. Trascinate i cursori per modificare i valori di contributo corrispondenti.

   Il grafico a torta riflette graficamente le modifiche apportate.
1. Clic **[!UICONTROL Save Changes]**.
1. Ricostruisci l’indice del sito web di staging per visualizzare in anteprima i risultati dell’aggiunta della regola.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
