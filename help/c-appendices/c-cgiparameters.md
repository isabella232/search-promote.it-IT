---
description: nulle
seo-description: nulle
seo-title: Parametri CGI
solution: Target
title: Parametri CGI
topic: Appendices,Site search and merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
translation-type: tm+mt
source-git-commit: 7b883870bb16284d8070a21547cdb62cc79d7632
workflow-type: tm+mt
source-wordcount: '5490'
ht-degree: 1%

---


# Parametri CGI{#cgi-parameters}

## Parametri CGI {#concept_F395999090FE4926B38BC73D5E612800}

## Cerca parametri CGI {#reference_DA27A8B0728246DA94994885E1353890}

Il codice del modulo di ricerca viene fornito per consentire la copia e l’incolla nell’HTML del sito ( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**).

Vedere [Copia del codice HTML del modulo di ricerca in corso...](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

È inoltre possibile impostare i parametri elencati nel modulo di ricerca stesso o da uno script. Oltre ai parametri elencati di seguito, potete anche usare i parametri di ricerca di back-end per controllare la ricerca.

Consultate [Parametri](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)CGI di ricerca di back-end.

Le richieste di ricerca sono costituite da un URL di base. L&#39;URL di base indica l&#39;account che il cliente sta cercando e un set di parametri CGI (coppie chiave-valore) che indicano come restituire i risultati di ricerca desiderati per l&#39;account associato.

L&#39;URL di base è associato a un account specifico e a un ambiente in fase di esecuzione o in tempo reale. Potete richiedere più alias per l&#39;URL di base al vostro account manager. Ad esempio, una società di nome Megacorp potrebbe avere due URL di base associati al suo account: `https://search.megacorp.com` e `https://stage.megacorp.com`. L’URL precedente esegue la ricerca nel relativo indice live e l’ultimo URL cerca il relativo indice in fase di esecuzione.

Sono supportati tre formati di parametri CGI. Per impostazione predefinita, il vostro account è configurato per separare i parametri CGI con un punto e virgola, come nell’esempio seguente:

`https://search.megacorp.com?q=shoes;page=2`

Se preferite, potete fare in modo che il vostro account manager configuri il vostro account in modo che utilizzi le e commerciale per separare i parametri CGI, come nell&#39;esempio seguente:

`https://search.megacorp.com?q=shoes&page=2`

È inoltre supportato un terzo formato, denominato formato SEO, in cui `/` viene utilizzata una barra al posto del separatore e un segno di uguale come nell’esempio seguente:

`https://search.megacorp.com/q/shoes/page/2`

Ogni volta che il formato SEO viene utilizzato per inviare una richiesta, tutti i collegamenti di output vengono restituiti nello stesso formato.

| Parametro di ricerca guidato | Esempio | Descrizione |
|--- |--- |--- |
| q | `q=string` | Specifica la stringa di query per la ricerca. Questo parametro viene mappato sul parametro di ricerca `sp_q` di back-end.  Consultate [Parametri](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)CGI di ricerca di back-end. |
| q# | `q#=string` | La ricerca all&#39;interno di un dato campo viene eseguita mediante i parametri q e x numerati.  Il parametro q definisce il termine ricercato nel facet come indicato dal parametro x numerato corrispondente.<br>Ad esempio, se avete due facet denominati dimensione e colore, potete avere qualcosa come q1=piccolo;x1=dimensione;q2=rosso;x2=colore.  Questo parametro viene mappato sui parametri di ricerca `sp_q_exact_#` di back-end.  <br>Consultate [Parametri](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)CGI di ricerca di back-end. |
| x# | `q#=string` | La ricerca all&#39;interno di un dato campo viene eseguita mediante i parametri q e x numerati.  Il parametro q definisce il termine ricercato nel facet come indicato dal parametro x numerato corrispondente. <br>Ad esempio, se avete due facet denominati dimensione e colore, potete avere qualcosa come q1=piccolo;x1=dimensione;q2=rosso;x2=colore.  Questo parametro viene mappato sui parametri di ricerca `sp_x_#` di back-end.  <br>Consultate [Parametri](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)CGI di ricerca di back-end. |
| raccolta | `collection=string` | Specifica la raccolta da utilizzare per la ricerca.  Questo parametro viene mappato sul parametro di ricerca `sp_k` di back-end.  Consultate [Parametri](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)CGI di ricerca di back-end. |
| count | `count=number` | Specifica il conteggio totale dei risultati visualizzati.  Il valore predefinito è definito in [!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ]. .  Questo parametro viene mappato sul parametro di ricerca `sp_c` di back-end.  Consultate [Parametri](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)CGI di ricerca di back-end. |
| page | `page=number` | Specifica la pagina dei risultati restituiti. |
| rank | `rank=field` | Specifica il campo di classificazione da utilizzare per la classificazione statica.  Il campo deve essere un campo di tipo Classifica con rilevanza maggiore di 0.  Questo parametro viene mappato sul parametro di `sp_sr` backend.  Consultate [Parametri](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)CGI di ricerca di back-end. |
| sort | `sort=number` | Specifica l&#39;ordinamento.<br>&quot;0&quot; è l&#39;impostazione predefinita e ordina per punteggio di rilevanza; &quot;1&quot;, per data; &quot;-1&quot; non esegue l&#39;ordinamento.  Gli utenti possono specificare un nome di campo per il valore del `sp_s` parametro.  Ad esempio, `sp_s=title` ordina i risultati in base ai valori contenuti nel campo del titolo. Quando un nome di campo viene utilizzato per il valore di un ` sp_s ` parametro, i risultati vengono ordinati in base a tale campo e quindi suddivisi in base alla rilevanza.  To enable this feature, click [!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]. Nella pagina Definizioni, fare clic [!UICONTROL Add New Field ] o fare clic [!UICONTROL Edit ] per specificare il nome di un campo. Nell&#39;elenco a [!UICONTROL Sorting ] discesa, selezionare [!UICONTROL Ascending ] o [!UICONTROL Descending ]. Questo parametro viene mappato sul parametro di ricerca `sp_s` di back-end. <br>Consultate [Parametri]CGI di ricerca di back-end.(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |

## Parametri CGI per la ricerca di back-end {#reference_582E85C3886740C98FE88CA9DF7918E8}

In genere i clienti interagiscono con un livello di presentazione denominato Ricerca guidata. Tuttavia, è teoricamente possibile saltare il livello Guided Search e interagire con la ricerca di base del back-end direttamente utilizzando i parametri CGI descritti in questa pagina.

È possibile selezionare i parametri CGI di ricerca back-end dalla tabella seguente:
<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Supporto per query singole </p> </th> 
   <th colname="col03" class="entry"> <p>Supporto di più query </p> </th> 
   <th colname="col3" class="entry"> <p>Esempi </p> </th> 
   <th colname="col4" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>sp_a </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_a= stringa </span> </p> </td> 
   <td colname="col4"> <p>Specifica la stringa del numero di account. Questo parametro è obbligatorio e deve essere una stringa numero di account valida. Potete trovare la stringa del numero di account in <span class="uicontrol"> Settings (Impostazioni) </span> &gt; <span class="uicontrol"> Account Options (Opzioni account) </span> &gt; <span class="uicontrol"> Account Settings (Impostazioni account) </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_advanced= 0 o 1 </span> </p> </td> 
   <td colname="col4"> <p>Se <span class="codeph"> sp_advanced=1 </span> viene inviato con una query, per il modulo di ricerca viene utilizzato tutto il codice compreso tra il tag <span class="codeph"> &lt;search-if-advanced&gt; </span> e il tag <span class="codeph"> &lt;/search-if-advanced&gt; </span> nel modello di ricerca. Tutto il codice compreso tra il tag <span class="codeph"> &lt;search-if-not-advanced&gt; </span> e il tag <span class="codeph"> &lt;/search-if-not-advanced&gt; </span> viene ignorato. Se <span class="codeph"> sp_advanced=0 </span> (o qualsiasi altro valore) viene inviato, il blocco di modelli &lt;search-if-advanced&gt; viene ignorato e viene utilizzato il blocco di modelli &lt;search-if-not-advanced&gt;. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_c= numero </span> </p> </td> 
   <td colname="col4"> <p>Specifica il conteggio totale dei risultati da visualizzare. Il valore predefinito è 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>Raccoglie informazioni contestuali per il campo specificato. Le informazioni raccolte vengono inserite nei risultati della ricerca tramite il tag modello <span class="codeph"> &lt;search-context&gt; </span> . The default value is <span class="codeph"> body </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d= type </span> </p> </td> 
   <td colname="col4"> <p>Specifica il tipo di intervallo di date da eseguire. I valori possibili per type sono any, ovvero non eseguono ricerche per intervalli di date, custom, che indica che il valore di <span class="codeph"> sp_date_range </span> deve essere utilizzato per determinare le date da cercare, e specific, che indica che sono utilizzati i valori in <span class="codeph"> sp_start_day </span>, <span class="codeph"> sp_start_month </span>, <span class="codeph"> sp_start_year </span>, <span class="codeph"> sp_end_day </span><span class="codeph"> </span><span class="codeph"> </span> , sp_sp_end_month, _end_month, per determinare l'intervallo di date in cui effettuare la ricerca. <span class="codeph"> sp_d </span> è richiesto solo se il modulo di ricerca contiene l'opzione per effettuare ricerche in base a un intervallo personalizzato (tramite <span class="codeph"> sp_date_range </span>) o a un intervallo di date iniziale e finale specifico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d_#= type </span> </p> </td> 
   <td colname="col4"> <p>Specifica il tipo di ricerca dell'intervallo di date da eseguire per la query <span class="codeph"> sp_q_# </span> corrispondente. Il numero "#" viene sostituito con un numero compreso tra 1 e 16 (ad esempio, <span class="codeph"> sp_d_8 </span>, applicabile alla query numerata <span class="codeph"> sp_q_8 </span>). </p> <p>È possibile impostare <span class="codeph"> type </span> su qualsiasi, il che significa che non esegue ricerche per intervalli di date, custom, che indica che il valore di <span class="codeph"> sp_date_range_# </span> è utilizzato per determinare le date da cercare, e specifiche, che indica che i valori in <span class="codeph"> sp_q_min_day_# </span>, <span class="codeph"> sp_q_min_month_# </span>, <span class="codeph"> sp_q_min_year_# </span><span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span> ,  Per determinare l'intervallo di date, è necessario utilizzare sp_q_max_month_#, _max_month_# e _sp_max_year_#. L'uso di <span class="codeph"> sp_d_# </span> è richiesto solo se il modulo di ricerca contiene l'opzione per effettuare ricerche in base a un intervallo personalizzato (per mezzo di <span class="codeph"> sp_date_range_# </span>) oppure in base a uno specifico intervallo di date iniziale e finale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>sp_date_range </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifica un intervallo di date predefinito da applicare alla ricerca. Valori maggiori o uguali a zero specificano il numero di giorni in cui eseguire la ricerca prima della data odierna — ad esempio, un valore pari a "0" specifica "oggi", un valore pari a "1" specifica "oggi e ieri", un valore pari a "30" specifica "entro gli ultimi 30 giorni" e così via. </p> <p>I valori inferiori a zero specificano un intervallo personalizzato come segue: </p> <p>-1 = "None" (Nessuno), come se non fosse specificato alcun intervallo di date. </p> <p>-2 = "Questa settimana", che esegue la ricerca da domenica a sabato della settimana corrente. </p> <p>-3 = "Ultima settimana", che esegue la ricerca da domenica a sabato della settimana precedente alla settimana corrente. </p> <p>-4 = "Questo mese", che esegue la ricerca delle date entro il mese corrente. </p> <p>-5 = "Last month", che esegue la ricerca delle date entro il mese precedente quello corrente. </p> <p>-6 = "Quest'anno", che esegue la ricerca delle date entro l'anno corrente. </p> <p>-7 = "Ultimo anno", che esegue la ricerca delle date entro l'anno precedente l'anno in corso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_date_range_# </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range_#= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifica un intervallo di date predefinito da applicare alla query <span class="codeph"> sp_q_# </span> corrispondente. Il numero "#" viene sostituito con un numero compreso tra 1 e 16 (ad esempio, <span class="codeph"> sp_date_range_8 </span>, applicabile alla query numerata <span class="codeph"> sp_q_8 </span>). </p> <p>Valori maggiori o uguali a zero specificano il numero di giorni in cui eseguire la ricerca prima della giornata odierna. Ad esempio, un valore pari a 0 specifica oggi; un valore pari a 1 indica oggi e ieri; un valore pari a 30 specifica gli ultimi 30 giorni e così via. </p> <p>I valori inferiori a zero specificano un intervallo personalizzato come segue: </p> <p>-1 = "None" (Nessuno), come se non fosse specificato alcun intervallo di date. </p> <p>-2 = "Questa settimana", che esegue la ricerca da domenica a sabato della settimana corrente. </p> <p>-3 = "Ultima settimana", che esegue la ricerca da domenica a sabato della settimana precedente alla settimana corrente. </p> <p>-4 = "Questo mese", che esegue la ricerca delle date entro il mese corrente. </p> <p>-5 = "Last month", che esegue la ricerca delle date entro il mese precedente quello corrente. </p> <p>-6 = "Quest'anno", che esegue la ricerca delle date entro l'anno corrente. </p> <p>-7 = "Ultimo anno", che esegue la ricerca delle date entro l'anno precedente l'anno in corso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifica un singolo campo su cui ridurre i risultati della ricerca. Tutti i risultati duplicati in quel campo vengono rimossi dai risultati della ricerca. Ad esempio, se per <span class="codeph"> sp_dedupe_field=title </span>, nei risultati della ricerca viene visualizzato solo il risultato superiore per un determinato titolo (nessun risultato avrà contenuto identico per il campo titolo). Per i campi di tipo multivalore ( elenco consentiti), per il confronto viene utilizzato l’intero contenuto del campo. È possibile specificare un solo campo. Un "qualificatore tabella" non è consentito nel nome del campo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e= numero </span> </p> </td> 
   <td colname="col4"> <p>Specifica che deve essere eseguita l'espansione automatica del carattere jolly per qualsiasi parola proveniente dalla stringa di query con più caratteri numerici. In altre parole, <span class="codeph"> sp_e=5 </span> specifica che le parole con 5 o più caratteri, come "query" o "numero", devono essere espanse con il carattere jolly '*', rendendo la ricerca equivalente a una ricerca per "query*" o "numero*". Le parole con un numero inferiore di caratteri non vengono espanse, pertanto la ricerca di "parola" non comporterebbe l’espansione automatica dei caratteri jolly. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e_#= numero </span> </p> </td> 
   <td colname="col4"> <p>Specifica che viene eseguita l'espansione automatica del carattere jolly per qualsiasi parola proveniente dalla stringa di query <span class="codeph"> sp_q_# </span> corrispondente con più di un numero di caratteri. In altre parole, <span class="codeph"> sp_e_2=5 </span> specifica che le parole con cinque o più caratteri nella stringa di query <span class="codeph"> sp_q_2 </span> , come "query" o "numero", devono essere espanse con il carattere jolly ' <span class="codeph"> * </span>', rendendo la ricerca equivalente a una ricerca per "query*" o "numero*". Le parole con un numero di caratteri inferiore non vengono espanse, pertanto la ricerca di "parola" in <span class="codeph"> sp_q_2 non </span> comporterebbe l'espansione automatica dei caratteri jolly. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>sp_end_day, sp_end_month, sp_end_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_end_day= <i>number</i>,sp_end_month= <i>number</i>, sp_end_year= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Questo triplo di valori specifica l’intervallo di date di fine della ricerca e deve essere fornito come set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>sp_f </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_f= stringa </span> </p> </td> 
   <td colname="col4"> <p>Specifica il set di caratteri delle stringhe del parametro di query (ad esempio <span class="codeph"> sp_q </span>). Questa stringa deve sempre corrispondere al set di caratteri della pagina che contiene il modulo di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>Definisce una tabella di dati logica costituita dai campi specificati. Ad esempio, una tabella denominata "items" composta dai campi "color", "size" e "price" verrebbe definita come segue: </p> <p> <span class="codeph"> sp_field_table=elementi:colore,dimensione,prezzo </span> </p> <p>Le tabelle logiche sono particolarmente utili in combinazione con i campi che presentano l'opzione "Elenchi consentiti " selezionata (in <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Definizioni </span>). Tutti i parametri CGI e i tag modello che utilizzano un nome di campo come valore possono facoltativamente specificare un nome di tabella seguito da un "." prima del nome del campo (ad esempio, <span class="codeph"> sp_x_1=nomeapp.nomefile </span>). </p> <p>Ad esempio, per eseguire una ricerca di documenti che contengono uno o più elementi "rossi" di dimensioni "grandi" (dove gli elementi sono rappresentati come righe parallele di metadati), potete utilizzare quanto segue: </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_i= <span class="varname"> valore </span> </span> </p> </td> 
   <td colname="col4"> <p>Consente di ignorare la ricerca durante la generazione dei rapporti. </p> <p>Utilizzate questa query per mascherare alcune ricerche di back-end, ad esempio ricerche generate da Did You Mean o ricerche generate da un amministratore nel centro membri. Poiché un utente finale non genera questi tipi di ricerche, queste non vengono visualizzate in vari rapporti sui Search&amp;Promote  Adobe. </p> <p>I valori validi sono <span class="codeph"> sp_i=1 </span> e <span class="codeph"> sp_i=2 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>16 </p> </td> 
   <td colname="col2"> <p>sp_k </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_k= stringa </span> </p> </td> 
   <td colname="col4"> <p> Specifica la raccolta da utilizzare per la ricerca. L'impostazione predefinita è nessuna raccolta, il che significa che la ricerca deve includere l'intero sito. </p> <p>Vedere <a href="../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3" type="reference" format="dita" scope="local"> Uso delle raccolte nei moduli di ricerca </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>17 </p> </td> 
   <td colname="col2"> <p>sp_l </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_l= stringa </span> </p> </td> 
   <td colname="col4"> <p>Specifica la lingua delle stringhe dei parametri di query (ad esempio <span class="codeph"> sp_q </span>). La <i><span class="codeph"> stringa </span></i> deve essere un ID di lingua standard contenente un codice di lingua ISO-639, seguito facoltativamente da un codice di paese ISO-3166. Ad esempio, "en" o "en_US" per l'inglese o "ja" o "ja_JP" per il giapponese. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>18 </p> </td> 
   <td colname="col2"> <p>sp_literal </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_literal= 0 o 1 </span> </p> </td> 
   <td colname="col4"> <p> Impostando <span class="codeph"> sp_literal=1 </span> vengono disattivate temporaneamente tutte le funzioni che potrebbero interpretare le parole della query. Con questo parametro, solo le parole letterali della query corrispondono ai documenti, indipendentemente dai sinonimi, dalle forme di parole alternative e dalla corrispondenza simile. </p> <p>Si noti che <span class="codeph"> sp_literal=0 </span> non ha alcun significato e viene ignorato se utilizzato. </p> <p>Vedere <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> Informazioni sui dizionari </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>19 </p> </td> 
   <td colname="col2"> <p>sp_m </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_m= numero </span> </p> </td> 
   <td colname="col4"> <p> Specifica se i riepiloghi vengono visualizzati. 1 è sì, 0 è no. Il valore predefinito è 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>20 </p> </td> 
   <td colname="col2"> <p>sp_n </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_n= numero </span> </p> </td> 
   <td colname="col4"> <p> Specifica il numero del risultato che avvia i risultati della ricerca. Il valore predefinito è 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>21 </p> </td> 
   <td colname="col2"> <p>sp_not_found_page </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_not_found_page= url </span> </p> </td> 
   <td colname="col4"> <p> Specifica se reindirizzare all'URL specificato in assenza di risultati di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>22 </p> </td> 
   <td colname="col2"> <p>sp_p </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p> Specifica il tipo predefinito di ricerca da eseguire. L'uso di <span class="codeph"> qualsiasi </span> mezzo per cercare documenti che contengono qualsiasi parola della stringa di query. L'uso di <span class="codeph"> tutti </span> indica la ricerca di documenti che contengono tutte le parole nella stringa di query. L'uso di <span class="codeph"> una frase </span> indica che la stringa di query viene trattata come se fosse una frase citata e che tutte le virgolette digitate dall'utente vengono ignorate. </p> <p>Per la <span class="codeph"> frase </span> e <span class="codeph"> tutto </span>, la specifica "+" e "-" prima delle parole di ricerca è disabilitata e tali caratteri vengono ignorati. Se <span class="codeph"> sp_p </span> non è presente, o se è impostato su una stringa vuota o qualsiasi altra, sono consentiti i prefissi "+" e "-" standard. </p> <p>Per ulteriori informazioni sull’utilizzo di più ("+") e meno ("-") nelle ricerche, consultate la descrizione dei suggerimenti per la ricerca. </p> <p>Consultate <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> Le Ricerche </a>. </p> <p>Per esempi sull'utilizzo del parametro <span class="codeph"> sp_p, consultate il modulo di ricerca avanzato di esempio </span> . </p> <p>Vedere <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Esempio di modulo di ricerca avanzato </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>23 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_p_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p_#= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p>Specifica il tipo predefinito di ricerca da eseguire con la query <span class="codeph"> sp_q_# </span> corrispondente. Il numero "#" viene sostituito con un numero compreso tra 1 e 16 (ad esempio, <span class="codeph"> sp_p_8 </span> si applica alla query numerata <span class="codeph"> sp_q_8 </span>). L'uso di <span class="codeph"> qualsiasi </span> mezzo restituisce documenti che contengono qualsiasi parola della stringa di query. L'uso di <span class="codeph"> tutti </span> indica documenti restituiti che contengono tutte le parole nella stringa di query. L'uso di <span class="codeph"> una frase </span> significa che la stringa di query viene trattata come una frase completa (e tutte le virgolette digitate dall'utente vengono ignorate). </p> <p>Se si specifica <span class="codeph"> tutti </span> o <span class="codeph"> frasi </span>, i segni più e meno prima delle parole di ricerca vengono ignorati. Se <span class="codeph"> sp_p_# </span> viene omesso o se è impostato su una stringa vuota o <span class="codeph"> una qualsiasi </span>, sono consentiti prefissi standard "+" e "-". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>24 </p> </td> 
   <td colname="col2"> <p>sp_pt </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_pt= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p> Specifica il tipo di corrispondenza di destinazione da applicare. L'utilizzo di <span class="codeph"> esatte </span> significa che il target di rendimento corrisponde solo in documenti che corrispondono esattamente alla stringa di query all'interno del contenuto di destinazione. L'uso di <span class="codeph"> equivalente </span> è come esatto, tranne che l'ordine delle parole non è importante. L'uso di <span class="codeph"> compatibile imposta </span> automaticamente il tipo di corrispondenza di destinazione in base al valore del parametro <span class="codeph"> sp_p </span> . L'uso di <span class="codeph"> esatto </span> è utilizzato se <span class="codeph"> sp_p </span> è <span class="codeph"> tutto </span> o <span class="codeph"> frase </span>, altrimenti <span class="codeph"> equivalente </span> . Il valore predefinito di <span class="codeph"> sp_pt </span> è <span class="codeph"> compatibile </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>25 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_pt_# </p> </td> 
   <td colname="col3"> <p> <code> sp_pt_#= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifica il tipo di corrispondenza di destinazione da applicare con la query <span class="codeph"> sp_q_# </span> corrispondente. Il numero "#" viene sostituito con un numero compreso tra 1 e 16 (ad esempio, <span class="codeph"> sp_p_8 </span> si applica alla query numerata <span class="codeph"> sp_q_8 </span>). L'utilizzo di <span class="codeph"> esatte </span> significa che il target di rendimento corrisponde solo in documenti che corrispondono esattamente alla stringa di query all'interno del contenuto di destinazione. L'uso di <span class="codeph"> equivalente </span> è come <span class="codeph"> esatto </span>, tranne che l'ordine delle parole non è importante. L'uso di <span class="codeph"> compatibile imposta </span> automaticamente il tipo di corrispondenza di destinazione in base al valore del parametro <span class="codeph"> sp_p_# corrispondente </span> : <span class="codeph"> exact </span> viene utilizzato se <span class="codeph"> sp_p_# </span> è tutto o frase, altrimenti <span class="codeph"> viene utilizzato un equivalente </span> . Il valore predefinito di <span class="codeph"> sp_pt_# </span> è <span class="codeph"> compatibile </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>26 </p> </td> 
   <td colname="col2"> <p>sp_q </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q= stringa </span> </p> </td> 
   <td colname="col4"> <p> Specifica la stringa di query per la ricerca. Una stringa vuota impedisce la visualizzazione di risultati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>27 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_q_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_#= testo </span> </p> </td> 
   <td colname="col4"> <p>Questo parametro consente la creazione di più query sui moduli di ricerca. Il parametro <span class="codeph"> sp_q_# </span> contiene la stringa di query da utilizzare nella query numerata specificata. Una richiesta di ricerca può fare riferimento fino a 16 diverse query numerate ( <span class="codeph"> sp_q_1 </span> a <span class="codeph"> sp_q_16 </span>). </p> <p>Ad esempio, l'invio del modulo seguente restituisce tutti i documenti che contengono le parole "grande" e "libri". </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>28 </p> </td> 
   <td colname="col2"> <p>sp_q_day, sp_q_month, sp_q_year </p> </td> 
   <td colname="col03"> <p> sp_q _day_#, sp_q _month_#, sp_q _year_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_day= valore intero </span> </p> <p> <span class="codeph"> sp_q_month= valore intero </span> </p> <p> <span class="codeph"> sp_q_year= valore intero </span> </p> <p> <span class="codeph"> sp_q_day_#= valore intero </span> </p> <p> <span class="codeph"> sp_q_month_#= valore intero </span> </p> <p> <span class="codeph"> sp_q_year_#= valore intero </span> </p> </td> 
   <td colname="col4"> <p>Questi parametri vengono utilizzati per specificare una data esatta per una particolare query. I parametri <span class="codeph"> sp_q_day </span>, <span class="codeph"> sp_q_month </span>e <span class="codeph"> sp_q_year </span> si applicano alla query principale ( <span class="codeph"> sp_q </span>). </p> <p>Il <span class="codeph"> parametro </span># viene sostituito con un numero compreso tra 1 e 16 (ad esempio, <span class="codeph"> sp_q_day_6 </span>, che si applica alla query numerata <span class="codeph"> sp_q_6 </span>). Per impostazione predefinita, la ricerca viene effettuata in tutte le date relative all'ora di Greenwich. </p> <p>La sezione seguente del codice consente all'utente di cercare la parola "arancione" nei documenti datati "gen. 1°, 2000" in un campo definito dall’utente denominato <span class="codeph"> Data pubblicazione </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>29 </p> </td> 
   <td colname="col2"> <p>sp_q_location </p> </td> 
   <td colname="col03"> <p>sp_q_location_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> <p> <code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> </td> 
   <td colname="col4"> <p>Questi parametri associano una posizione alla query principale o numerata. L'utilizzo di <span class="codeph"> sp_q_location </span> influisce sulla query principale, <span class="codeph"> sp_q_location_# </span> (dove <span class="codeph"> # </span> viene sostituito da un numero compreso tra 1 e 16), influenza la query numerata specificata. Questi parametri vengono utilizzati per eseguire ricerche di prossimità a distanza minima e/o massima rispetto ai dati di posizione indicizzati per ogni pagina del sito. Il formato del valore ne determina l'interpretazione. </p> <p>Un valore nel formato DDD (tre cifre) è interpretato come un prefisso telefonico statunitense; un valore nel modulo DDDDD o DDDDD-DDDD viene interpretato come codice postale USA; e un valore nel formato ±DD.DDDD±DDD.DDDD viene interpretato come una coppia latitudine/longitudine. I segni sono obbligatori per ciascun valore. Ad esempio, +38.6317+120.5509 specifica la latitudine 38.6317, longitudine 120.5509. </p> <p>Consultate <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> La ricerca di prossimità </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>30 </p> </td> 
   <td colname="col2"> <p>sp_q_max_relevant_distanza </p> </td> 
   <td colname="col03"> <p>sp_q_max_relevant _distanza _# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_max_relevant_distance= <i>value</i> </code> </p> <p> <code> sp_q_max_relevant_distance_#= <i>value</i> </code> </p> </td> 
   <td colname="col4"> <p>Questi parametri controllano il calcolo della pertinenza applicato alle ricerche di prossimità. L'utilizzo di <span class="codeph"> sp_q_max_relevant_distanza </span> influenza la query principale, <span class="codeph"> sp_q_max_relevant_Distance_# </span> (dove il <span class="codeph"> # </span> viene sostituito da un numero compreso tra 1 e 16), influenza la query numerata specificata. </p> <p>Il valore predefinito di <span class="codeph"> sp_q_max_relevant_Distanza </span> è 100. </p> <p>Un punteggio di rilevanza perfetto per il componente di prossimità rappresenterebbe una distanza di 0. Un punteggio di rilevanza minimo per il componente di prossimità rappresenterebbe una distanza appena sopra il valore specificato per <span class="codeph"> sp_q_max_relevant_distanza_# </span> . </p> <p>Consultate <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> La ricerca di prossimità </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>31 </p> </td> 
   <td colname="col2"> <p>sp_q_min_day, sp_q_min_month, sp_q_min_year </p> <p>sp_q_max_day, sp_q_max_month, sp_q_max_year </p> </td> 
   <td colname="col03"> <p>sp_q_min_day_#, sp_q_min_month_#, sp_q_min_year_# </p> <p> sp_q_max_day_#, sp_q_max_month_#, sp_q_max_year_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_min_day=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year=<i>integer value</i> </code> </p> <p> <code> sp_q_min_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year_#=<i>integer value</i> </code> </p> </td> 
   <td colname="col4"> <p>Questi parametri vengono utilizzati per impostare intervalli di date minimi e massimi per una particolare query. I <span class="codeph"> sp_q_min_day </span>, <span class="codeph"> sp_q_min_month </span>, <span class="codeph"> sp_q_min_year </span>, sp_q_max_day <span class="codeph"> , </span>sp_q_max_month <span class="codeph"> </span><i></i> <span class="codeph"> </span>, e i parametri spsp_q_max_year_ si applicano alla query principale ( sp_q_). </p> <p>Il <span class="codeph"> # </span>nel nome del parametro viene sostituito con un numero compreso tra 1 e 16 (ad esempio, <span class="codeph"> sp_q_min_day_6 </span> si applica alla query numerata <span class="codeph"> sp_q_6 </span>). </p> <p>È legale specificare solo una data minima, solo una data massima o sia una data minima che una data massima. Tuttavia, per un determinato insieme minimo o massimo, è necessario specificare tutti e tre i parametri di data (giorno, mese e anno). Per impostazione predefinita, la ricerca viene effettuata in tutte le date relative all'ora di Greenwich. </p> <p>La sezione seguente del codice consente all'utente di cercare la parola "arancione" nei documenti con una data compresa tra il 1° gennaio 2000 e il 31 dicembre 2000 in un campo definito dall'utente, <span class="codeph"> Data pubblicazione </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>32 </p> </td> 
   <td colname="col2"> <p>sp_q_min, sp_q_max </p> </td> 
   <td colname="col03"> <p>sp_q_min_#, sp_q _max_#, sp_q _exact_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_min= valore </span> </p> <p> <span class="codeph"> sp_q_max= valore </span> </p> <p> <span class="codeph"> sp_q_min_#= valore </span> </p> <p> <span class="codeph"> sp_q_max_#= valore </span> </p> <p> <span class="codeph"> sp_q_exact_#=value </span> </p> </td> 
   <td colname="col4"> <p>Questi parametri specificano un valore minimo (e/o massimo) da applicare alla query principale o numerata. L'utilizzo di <span class="codeph"> sp_q_min </span>, <span class="codeph"> sp_q_max </span>e <span class="codeph"> sp_q_exact </span> influisce sulla query principale ( <span class="codeph"> sp_q </span>). </p> <p>Sostituire <span class="codeph"> # </span>nel nome del parametro con un numero compreso tra 1 e 16 (ad esempio, <span class="codeph"> sp_q_min_8 </span> si applica alla query numerata <span class="codeph"> sp_q_8 </span>). </p> <p>L'utilizzo di <span class="codeph"> sp_q_exact_# </span> è limitato per specificare sia <span class="codeph"> sp_q_min_# </span> che <span class="codeph"> sp_q_max_# </span> con lo stesso valore. Se <span class="codeph"> sp_q_exact_# </span> è specificato, tutti i parametri <span class="codeph"> sp_q_min_# </span> o <span class="codeph"> </span> sp_q_max_# corrispondenti vengono ignorati. </p> <p>I parametri <span class="codeph"> sp_q_min_# </span>, <span class="codeph"> sp_q_max_# </span> e <span class="codeph"> sp_q_exact_# </span> possono facoltativamente specificare più valori separati "|". Ad esempio, per cercare documenti che contengono il valore verde o rosso all'interno del campo "colore": <span class="codeph"> ...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>33 </p> </td> 
   <td colname="col2"> <p>sp_q_nocp </p> </td> 
   <td colname="col03"> <p>sp_q _nocp _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_nocp= 1 o 0 </span> </p> <p> <span class="codeph"> sp_q_nocp_#= 1 o 0 </span> </p> </td> 
   <td colname="col4"> <p>Il valore predefinito del parametro è <span class="codeph"> 0, </span> ovvero vengono eseguite le espansioni Common Phrase. </p> <p>Se si imposta su <span class="codeph"> 1 </span> per la query di ricerca corrispondente, non vengono eseguite le espansioni Common Phrases. </p> <p>L'utilizzo di <span class="codeph"> sp_q_nocp </span> influisce sul parametro della query di ricerca principale <span class="codeph"> sp_q </span>. Per applicare questo parametro a una query di ricerca numerata, sostituite <span class="codeph"> # </span> nel nome del parametro con il numero corrispondente. Ad esempio, <span class="codeph"> sp_q_nocp_8 </span> si applica alla query di ricerca numerata <span class="codeph"> sp_q_8 </span>. </p> <p> 
     <!--See also <xref href="c_about_common_phrases.xml#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">About Common Phrases</xref>--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>34 </p> </td> 
   <td colname="col2"> <p>sp_q_Required </p> </td> 
   <td colname="col03"> <p>sp_q _obbligatorio _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_Required= 1 or 0 or -1 </span> </p> <p> <span class="codeph"> sp_q_Required_#= 1 o 0 o -1 </span> </p> </td> 
   <td colname="col4"> <p>Questo parametro determina se una corrispondenza deve (1), può (0) o non deve (-1) verificarsi nella query corrispondente per poter restituire un documento nella pagina dei risultati. </p> <p>L'utilizzo di <span class="codeph"> sp_q_Required </span> influisce sulla query principale ( <span class="codeph"> sp_q </span>). </p> <p>Per applicare a una query numerata, sostituire il <span class="codeph"> # </span> nel nome del parametro con il numero corrispondente (ad esempio, <span class="codeph"> sp_q_Required_8 </span> si applica alla query numerata <span class="codeph"> sp_q_8 </span>). Il valore predefinito del parametro è 1 (deve corrispondere). </p> <p>Per cercare documenti che contengono la parola "calc" ma NON contengono "mac", "win" o "all" nel campo "platform" definito dall'utente, il modulo di ricerca HTML potrebbe contenere le seguenti righe: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>35 </p> </td> 
   <td colname="col2"> <p>sp_redirect_if_one_result </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifica se reindirizzare all'URL del risultato della ricerca in presenza di un solo risultato di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>36 </p> </td> 
   <td colname="col2"> <p>sp_referrer </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_referrer= url </span> </p> </td> 
   <td colname="col4"> <p>Specifica l’URL del referente per la ricerca. Utile per le regole di riscrittura della ricerca in cui i risultati della ricerca si collegano allo stesso sito del modulo di ricerca. </p> <p>Il valore predefinito è il valore CGI HTTP_REFERRER standard fornito dal browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>37 </p> </td> 
   <td colname="col2"> <p>sp_ro </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_ro= <span class="varname"> campo </span>: <span class="varname"> pertinenza </span> </span> </p> </td> 
   <td colname="col4"> <p>Consente un tempo di ricerca facoltativo, per nome campo e per il controllo della pertinenza. Il nome <span class="codeph"> o </span> nel nome del parametro è "rilevante override". Il parametro accetta uno o più nomi di campo, seguiti da un carattere di due punti, seguito da un valore di rilevanza compreso tra 0 e 10. </p> <p>Ad esempio, per impostare su 10 il valore di rilevanza per il nome del campo "body", nel momento in cui un cliente effettua una ricerca il parametro appare come segue: </p> <p> <span class="codeph"> sp_ro=body:10 </span> </p> <p>Oppure, per specificare più sostituzioni di rilevanza per i campi nella stringa del parametro, potete utilizzare un delimitatore di tubazioni. Ad esempio, per impostare su 9 il valore di rilevanza per i nomi di campo "body" e "title", al momento in cui un cliente effettua una ricerca, il parametro appare come segue: </p> <p> <span class="codeph"> sp_ro=body:9|title:9 </span> </p> <p> <p>Nota:  La specifica di un campo non coinvolto nella ricerca associata non ha alcun effetto. Ad esempio, se si imposta <span class="codeph"> sp_ro=title:10 </span>, ma non si esegue la ricerca nel nome del <span class="codeph"> campo </span> del titolo, il <span class="codeph"> parametro sp_ro </span> non ha alcun effetto. In altre parole, specificando un nome di campo utilizzando il parametro <span class="codeph"> sp_ro </span> non viene eseguita automaticamente la ricerca in quel campo; sostituisce solo l'impostazione di rilevanza associata al campo. </p> </p> <p>Consultate <a href="../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3" type="task" format="dita" scope="local"> Modifica di campi di tag meta predefiniti o definiti dall’utente </a>. </p> <p>Vedere <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" type="concept" format="dita" scope="local"> Informazioni sulle regole di pulizia delle query </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>38 </p> </td> 
   <td colname="col2"> <p>sp_s </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_s= numero </span> </p> </td> 
   <td colname="col4"> <p>Specifica l'ordinamento. Zero (0) è il valore predefinito e consente di ordinare in base al punteggio di rilevanza. Uno (1) significa ordinare per data e -1 significa non ordinare. </p> <p>Potete specificare un nome di campo per il valore del <span class="codeph"> parametro sp_s </span> . Ad esempio, <span class="codeph"> sp_s=title </span> ordina i risultati in base ai valori contenuti nel campo title. Quando un nome di campo viene utilizzato per il valore di un parametro <span class="codeph"> sp_s </span> , i risultati vengono ordinati in base a tale campo e quindi suddivisi per rilevanza. </p> <p>Per attivare questa funzione, impostare l'ordinamento per il campo di riferimento su <span class="uicontrol"> Ascendente </span> o <span class="uicontrol"> Discendente </span> in <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> </span> Definizioni. </p> <p>È inoltre possibile assegnare più campi di ordinamento a una singola query impostando più volte il parametro <span class="codeph"> sp_s </span> nel modulo di ricerca. Le righe di modello seguenti impostano i risultati di ricerca in modo che siano ordinati per nome dell’artista, per nome dell’album e per nome del brano. </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code> </p> <p>È inoltre possibile ordinare in base ai dati di campo associati alla tabella specificando un qualificatore di nome della tabella prima del nome del campo, ad esempio, items.price. Per ulteriori informazioni sulla corrispondenza delle tabelle, vedere il parametro <span class="codeph"> sp_field_table </span> . </p> <p>Se si esegue una ricerca per prossimità, è possibile ordinare i risultati in base alla prossimità specificando un "campo di output di prossimità". </p> <p>Consultate <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> La ricerca di prossimità </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>39 </p> </td> 
   <td colname="col2"> <p>sp_sr </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sr= campo </span> </p> </td> 
   <td colname="col4"> <p>Specifica il campo di classificazione da utilizzare per la classificazione statica. Il campo deve essere un campo di tipo Classifica con rilevanza maggiore di 0. Se per la query non viene fornito alcun <span class="codeph"> parametro </span> sp_sr, viene automaticamente selezionato un campo di tipo Classifica. </p> <p>Per disabilitare la classificazione statica per una particolare query, includete un valore NULL per <span class="codeph"> sp_sr </span> (ad esempio, <span class="codeph"> &lt;input type="hidden" name="sp_sr" value=""&gt; </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>40 </p> </td> 
   <td colname="col2"> <p>sp_sfvl_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_field= stringa </span> </p> </td> 
   <td colname="col4"> <p>Specifica il nome di un campo da utilizzare insieme al tag <span class="codeph"> &lt;search-field-value-list&gt; </span> nel modello di ricerca. </p> <p>Potete specificare più parametri <span class="codeph"> sp_sfvl_field </span> . </p> </td> 
  </tr> 
  <tr>
   <td colname="col1"> <p>41 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_count </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_df_count= <span class="varname"> &lt;valore_intero&gt; </span> </span> </p> </td> 
   <td colname="col4"> <p> Richiede fino a <span class="codeph"> <span class="varname"> &lt;integer_value&gt; </span></span> campi facet dinamici per <span class="codeph"> campi-valore-elenco di valori-campo di ricerca </span> per questa ricerca. </p> <p>Il valore predefinito è 0. Il valore massimo consentito è il numero corrente di campi di facet dinamico, conteggio campi di facet dinamico definito per un dato indice. I valori interi inferiori a 0 vengono considerati come 0. I valori interi specificati sopra <span class="codeph"> il numero di campi-facet-dinamico </span> sono limitati al conteggio di campi-facet- <span class="codeph"> dinamico </span>. I valori non interi vengono ignorati; vengono trattati come valori predefiniti. </p> <p>La ricerca di una sezione viene limitata con un valore <span class="codeph"> sp_sfvl_df_count massimo consentito </span> per il valore del conteggio campi-facet <span class="codeph"> dinamico della sezione </span> . Quando si uniscono i risultati della sezione, il valore massimo effettivo di <span class="codeph"> sp_sfvl_df_count </span> è il <span class="codeph"> sp_sfvl_df_count massimo effettivo </span> tra tutte le sezioni. </p> <p>Consultate <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Configurazione di facet dinamici </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>42 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_exclude </p> </td> 
   <td colname="col03"> <p> </p> </td>
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_exclude= &lt; <span class="varname"> nome_campo </span>&gt;[|&lt; <span class="varname"> nome_campo </span> </span>&gt;|.. </p> </td> 
   <td colname="col4"> <p> Specifica un elenco di campi sfaccettatura dinamici specifici da escludere dalla considerazione per la ricerca. </p> <p>Per impostazione predefinita, vengono considerati tutti i campi dei facet dinamici. </p> <p>Consultate <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Configurazione di facet dinamici </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>43 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_include </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_include= &lt; <span class="varname"> nome_campo </span>&gt;[|&lt; <span class="varname"> nome_campo </span> </span>&gt;|.. </p> </td> 
   <td colname="col4"> <p> Specifica un elenco di campi sfaccettatura dinamici specifici da includere nei risultati della ricerca. </p> <p> <p>Nota:  Il parametro <span class="codeph"> sp_sfvl_df_count </span> determina il numero totale di campi di facet dinamici da restituire, compresi quelli specificati tramite <span class="codeph"> sp_sfvl_df_include </span>. In altre parole, utilizzando <span class="codeph"> sp_sfvl_df_include </span> il conteggio totale dei campi facet dinamici restituiti non può superare <span class="codeph"> sp_sfvl_df_count </span>. </p> </p> <p>Consultate <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Configurazione di facet dinamici </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>44 </p> </td> 
   <td colname="col2"> <p>sp_stage </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_stage= 0 o 1 </span> </p> </td> 
   <td colname="col4"> <p>Se <span class="codeph"> sp_staged=1 </span> viene inviato con una query, la query eseguita è una ricerca in stato. </p> <p>Una ricerca in uno stadio utilizza tutti i componenti attualmente in fase, inclusi indice e modelli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>45 </p> </td> 
   <td colname="col2"> <p>sp_start_day, sp_start_month, sp_start_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_start_day= numero </span> </p> <p> <span class="codeph"> sp_start_month= numero </span> </p> <p> <span class="codeph"> sp_start_year= numero </span> </p> </td> 
   <td colname="col4"> <p>Questo triplo di valori specifica l’intervallo di date iniziale per la ricerca e lo immetti come set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>46 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_suggerire _q </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_suggerire_q= numero </span> </p> </td> 
   <td colname="col4"> <p>Il parametro <span class="codeph"> sp_tip_q </span> determina il parametro <span class="codeph"> sp_q[_#] </span> da utilizzare con il servizio Suggest. </p> <p>Il valore predefinito di <span class="codeph"> sp_Suggerimento_q </span> è 0, il che significa che il motore di ricerca utilizza il valore di <span class="codeph"> sp_q </span> per determinare i suggerimenti. </p> <p>Impostate <span class="codeph"> sp_Sugger_q=1 </span> per utilizzare il valore di <span class="codeph"> sp_q_1 </span> per determinare i suggerimenti e così via. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>47 </p> </td> 
   <td colname="col2"> <p>sp_t </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_t= stringa </span> </p> </td> 
   <td colname="col4"> <p>Specifica il modello di trasporto da utilizzare. </p> <p>Questo parametro è utile se desiderate controllare l’aspetto dei risultati di ricerca di base nel vostro sito Web utilizzando diversi modelli di trasporto di ricerca per ogni area dell’account di ricerca. </p> <p>Il modello di trasporto predefinito è "search". </p> <p>Consultate <a href="../c-appendices/c-templates.md#reference_12AAB3B9F4C74C11956F1DBA95714C2F" type="reference" format="dita" scope="local"> Gestione di più modelli di trasporto per il sito Web </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>48 </p> </td> 
   <td colname="col2"> <p>sp_trace </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_trace= 0 o 1 </span> </p> </td> 
   <td colname="col4"> <p>Se impostato come <span class="codeph"> sp_stage=1 </span>, abilita la funzionalità di traccia della ricerca di base in Simulator. </p> <p>Consultate <a href="../c-about-simulator.md#concept_020AA6751E32421A96A3455508364C7E" format="dita" scope="local"> Informazioni sul simulatore </a>. </p> <p> <p>Nota:  Se questo parametro non viene specificato, la ricerca di base non raccoglie le informazioni di ricalco e i relativi tag modello di ricerca di base non hanno output. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>49 </p> </td> 
   <td colname="col2"> <p>sp_w, sp_w_control </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_w= <i>sound-alike-enable</i> </code> </p> <p> <code> sp_w_control=<i>sound-alike-control</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifica che la corrispondenza audio-simili deve essere abilitata o disabilitata per questa particolare query. </p> <p>sp_w_control per `Exact` viene ignorato. La corrispondenza sosia è disabilitata. </p><p>sp_w_control per `Alike` viene ignorato. Corrispondenza audio simile attivata</p><p>Il valore sp_w_control per qualsiasi altro elemento è 1. La corrispondenza sosia è disabilitata. </p><p>sp_w_control per qualsiasi altro elemento. Corrispondenza audio-simile attivata. </p>Il <span class="codeph"> parametro </span> sp_w_control consente di creare una casella di controllo composta in modo negativo o positivo per il controllo da parte dell'utente finale della corrispondenza simile al suono. </p> <p>Se si utilizza <span class="codeph"> sp_w_control=0 </span> , per impostare il parametro <span class="codeph"> sp_w </span> viene utilizzata una casella di controllo denominata in modo negativo, come nell'esempio seguente: </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code> </p> <p>Se si utilizza <span class="codeph"> sp_w_control=1 </span> , viene utilizzata una casella di controllo composta in modo positivo per impostare il parametro <span class="codeph"> sp_w </span> come illustrato di seguito: </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code> </p> <p>Per ulteriori esempi sull'utilizzo dei parametri <span class="codeph"> sp_w_control </span> e <span class="codeph"> sp_w, vedere il modulo di ricerca avanzata di esempio </span> . </p> <p>Vedere <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Esempio di modulo di ricerca avanzato </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>50 </p> </td> 
   <td colname="col2"> <p>sp_x </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x= campo </span> </p> </td> 
   <td colname="col4"> <p>Specifica i campi da cercare nella stringa di query. qualsiasi significa cercare tutti i campi. title significa cercare solo i campi titolo. desc indica i campi di ricerca solo per la descrizione del documento. key significa cercare solo le parole chiave del documento. body indica il testo corpo di ricerca solo. alt significa solo testo alternativo da ricercare. url significa cercare solo i valori dell’URL. target significa cercare solo parole chiave di destinazione. In uno di questi casi, le specifiche utente dei prefissi di campo "text:", "desc:", "keys:", "body:", "alt:", "url:" e "target:" all'interno del parametro <span class="codeph"> sp_q corrispondente </span> vengono ignorate. Se <span class="codeph"> sp_x </span> non è presente o se è impostato su una stringa vuota o qualsiasi altra, i prefissi di campo utente standard sono consentiti. Per ulteriori informazioni sui prefissi di campo, consultate la descrizione dei suggerimenti per la ricerca. </p> <p>Consultate <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> Le Ricerche </a>. </p> <p>Per gli esempi che utilizzano il parametro <span class="codeph"> sp_x, consultate la descrizione del modulo di ricerca avanzata di esempio </span> . </p> <p>Vedere <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Esempio di modulo di ricerca avanzato </a>. </p> <p>Potete creare query che eseguono la ricerca in tutti i campi impostati per <span class="uicontrol"> Cerca per impostazione predefinita </span> in <span class="uicontrol"> Opzioni </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Definizioni </span> impostando <span class="codeph"> sp_x=any </span>. I campi predefiniti e definiti dall’utente possono essere utilizzati come valore del parametro <span class="codeph"> sp_x </span> . </p> <p>È inoltre possibile assegnare più campi a una singola query impostando più volte il parametro <span class="codeph"> sp_x </span> . Le righe di modello seguenti consentono agli utenti di eseguire una query sui campi "title" e "author" per "Great Books". </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>51 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_x_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x_#= nome campo </span> </p> </td> 
   <td colname="col4"> <p>Questo parametro specifica quale campo cercare nella corrispondente query <span class="codeph"> sp_q_# </span> . Il <span class="codeph"><span class="codeph"> # </span> </span> viene sostituito con un numero compreso tra 1 e 16 (ad esempio, <span class="codeph"> sp_x_8 </span>). Il nome del campo è un qualsiasi campo predefinito o definito dall’utente. </p> <p>Se non viene fornito alcun parametro <span class="codeph"> sp_x_# </span> per una particolare query numerata, tutti i campi definiti come <span class="uicontrol"> Cerca per impostazione predefinita </span> in <span class="uicontrol"> Impostazione </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Definizioni </span> vengono ricercati da tale query. </p> <p>Ad esempio, l'invio del modulo seguente restituisce tutti i documenti che contengono la parola "grande" e contengono anche la parola "Fitzgerald" nel campo "autore": </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code> </p> <p>È possibile associare più nomi di campo a una query particolare o a una query numerata fornendo più di un'istanza dello stesso parametro <span class="codeph"> sp_x </span> o <span class="codeph"> sp_x_# </span> in una singola richiesta di ricerca. </p> <p>Ad esempio, per cercare la parola "fiore" sia nei campi "body" che "keys", è possibile creare un modulo di ricerca con le seguenti informazioni: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempio tipico di utilizzo dei parametri CGI per la ricerca di back-end {#section_260012BBC2514CC9A8E02E53DE8B41EE}

Le seguenti query di collegamento avviano una ricerca utilizzando &quot;Music&quot; come query di ricerca e utilizzano tutti i parametri predefiniti. L’URL è suddiviso su due righe per garantire la leggibilità. Nel codice HTML, il collegamento deve essere su una sola riga.

```
<a href="https://search.atomz.com/search/?sp_q=Music&sp_a=sp99999999"> 
Testing...</a>
```

La stessa funzionalità è definita più in genere con un modulo:

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q" value="Music"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
</form>
```

In genere, quando si avvia una ricerca è consigliabile utilizzare i parametri predefiniti. In questo modo, viene visualizzata la prima pagina, ordinata per rilevanza, e consente al cliente di scegliere altre pagine e altre opzioni. Se il modulo di ricerca sul sito include opzioni per le raccolte, passate il nome della raccolta come parametro.

## Esempio dettagliato di utilizzo dei parametri CGI per la ricerca di back-end {#section_5FA3C620D5124FB2AB28857F8D8473F6}

Le seguenti query del modulo visualizzano `25` i risultati a partire dal risultato `10`. I riepiloghi non vengono visualizzati, l&#39;ordinamento è per data e viene utilizzata la raccolta denominata `support` . Vengono restituiti solo i documenti datati negli ultimi 30 giorni.

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
<input type=hidden name=sp_n value=10> 
<input type=hidden name=sp_c value=25> 
<input type=hidden name=sp_m value=0> 
<input type=hidden name=sp_s value=1> 
<input type=hidden name=sp_k value="support"> 
<input type=hidden name=sp_date_range value=30> 
</form>
```

