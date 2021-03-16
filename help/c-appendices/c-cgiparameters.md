---
description: Scopri come utilizzare vari parametri CGI.
solution: Target
title: Parametri CGI
topic: Appendici, Ricerca nel sito e merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1943'
ht-degree: 1%

---


# Parametri CGI{#cgi-parameters}

## Parametri CGI {#concept_F395999090FE4926B38BC73D5E612800}

## Cerca parametri CGI {#reference_DA27A8B0728246DA94994885E1353890}

Il codice del modulo di ricerca viene fornito per copiare e incollare nell’HTML del sito ( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**).

Vedere [Copia del codice HTML del modulo di ricerca in...](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

È inoltre possibile impostare i parametri elencati nel modulo di ricerca stesso o da uno script. Oltre ai parametri elencati di seguito è possibile utilizzare i parametri di ricerca di back-end per controllare la ricerca.

Consulta [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

Le richieste di ricerca sono costituite da un URL di base. L’URL di base indica l’account ricercato dal cliente e un set di parametri CGI (coppie chiave-valore) che indicano come restituire i risultati di ricerca desiderati per l’account associato.

L’URL di base è associato a un account specifico e a un ambiente in staging o live. Puoi richiedere più alias per l&#39;URL di base dal tuo account manager. Ad esempio, una società chiamata Megacorp può avere due URL di base associati al suo account: `https://search.megacorp.com` e `https://stage.megacorp.com`. L’URL precedente cerca il loro indice live e l’URL successivo cerca il loro indice di staging.

Sono supportati tre formati di parametri CGI. Per impostazione predefinita, il tuo account è configurato per separare i parametri CGI con un punto e virgola come nell’esempio seguente:

`https://search.megacorp.com?q=shoes;page=2`

Se lo desideri, puoi chiedere al tuo account manager di configurare il tuo account in modo che utilizzi il e commerciale per separare i parametri CGI come nell&#39;esempio seguente:

`https://search.megacorp.com?q=shoes&page=2`

È inoltre supportato un terzo formato, denominato formato SEO, in cui viene utilizzata una barra `/` al posto del separatore e un segno di uguale come nell’esempio seguente:

`https://search.megacorp.com/q/shoes/page/2`

Ogni volta che il formato SEO viene utilizzato per inviare una richiesta, tutti i collegamenti di output vengono restituiti nello stesso formato.

| Parametro di ricerca guidato | Esempio | Descrizione |
|--- |--- |--- |
| q | `q=string` | Specifica la stringa di query per la ricerca. Questo parametro viene mappato sul parametro di ricerca di back-end `sp_q` .  Consulta [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| q# | `q#=string` | L’impostazione della faccia (ricerca all’interno di un dato campo) viene eseguita tramite i parametri q e x numerati.  Il parametro q definisce il termine che stai cercando nel facet come indicato dal parametro x corrispondente.<br>Ad esempio, se hai due facet denominati dimensione e colore, puoi avere qualcosa come q1=small;x1=size;q2=red;x2=color.  Questo parametro viene mappato sui parametri di ricerca di back-end `sp_q_exact_#` .  <br>Consulta  [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| x# | `q#=string` | L’impostazione della faccia (ricerca all’interno di un dato campo) viene eseguita tramite i parametri q e x numerati.  Il parametro q definisce il termine che stai cercando nel facet come indicato dal parametro x corrispondente. <br>Ad esempio, se hai due facet denominati dimensione e colore, puoi avere qualcosa come q1=small;x1=size;q2=red;x2=color.  Questo parametro viene mappato sui parametri di ricerca di back-end `sp_x_#` .  <br>Consulta  [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| raccolta | `collection=string` | Specifica la raccolta da utilizzare per la ricerca.  Questo parametro viene mappato sul parametro di ricerca di back-end `sp_k` .  Consulta [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| count | `count=number` | Specifica il conteggio totale dei risultati visualizzati.  Il valore predefinito è definito in [!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ]. .  Questo parametro viene mappato sul parametro di ricerca di back-end `sp_c` .  Consulta [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| page | `page=number` | Specifica la pagina dei risultati restituiti. |
| rango | `rank=field` | Specifica il campo di classificazione da utilizzare per la classificazione statica.  Il campo deve essere un campo di tipo Rank con rilevanza superiore a 0.  Questo parametro viene mappato sul parametro di backend `sp_sr` .  Consulta [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| sort | `sort=number` | Specifica l&#39;ordinamento.<br>&quot;0&quot; è l’impostazione predefinita e ordinata in base al punteggio di pertinenza; &quot;1&quot; ordinamenti per data; &quot;-1&quot; non effettua l&#39;ordinamento.  Gli utenti possono specificare un nome di campo per il valore del parametro `sp_s` .  Ad esempio, `sp_s=title` ordina i risultati in base ai valori contenuti nel campo titolo. Quando un nome di campo viene utilizzato per il valore di un parametro ` sp_s `, i risultati vengono ordinati in base a tale campo e quindi suddivisi per rilevanza.  Per abilitare questa funzione, fai clic su [!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]. Nella pagina Definizioni fare clic su [!UICONTROL Add New Field ] o fare clic su [!UICONTROL Edit ] per un nome di campo specifico. Nell’elenco a discesa [!UICONTROL Sorting ] , seleziona [!UICONTROL Ascending ] o [!UICONTROL Descending ]. Questo parametro viene mappato sul parametro di ricerca di back-end `sp_s` . <br>Consulta  [Parametri CGI di ricerca back-end].(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |

## Parametri CGI di ricerca back-end {#reference_582E85C3886740C98FE88CA9DF7918E8}

In genere i clienti interagiscono con un livello di presentazione denominato Ricerca guidata. Tuttavia, è teoricamente possibile saltare il livello di ricerca guidata e interagire con la ricerca di base di back-end direttamente utilizzando i parametri CGI descritti in questa pagina.

Puoi selezionare i parametri CGI di ricerca back-end nella tabella seguente:
<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Supporto di singole query </p> </th> 
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
   <td colname="col3"> <p> <code>sp_a= string </code> </p> </td> 
   <td colname="col4"> <p>Specifica la stringa del numero di account. Questo parametro è obbligatorio e deve essere una stringa di numero di account valida. Puoi trovare la stringa del numero di account in <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Opzioni account </span> &gt; <span class="uicontrol"> Impostazioni account </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_advanced= 0 or 1 </code> </p> </td> 
   <td colname="col4"> <p>Se <code>sp_advanced=1 </code> viene inviato con una query, per il modulo di ricerca viene utilizzato tutto il codice compreso tra il tag <code>&lt;search-if-advanced&gt; </code> e il tag <code>&lt;/search-if-advanced&gt; </code> nel modello di ricerca. Tutto il codice compreso tra il tag <code>&lt;search-if-not-advanced&gt; </code> e il tag <code>&lt;/search-if-not-advanced&gt; </code> viene ignorato. Se viene inviato <code>sp_advanced=0 </code> (o qualsiasi altro valore), il blocco del modello &lt;search-if-advanced&gt; viene ignorato e viene utilizzato il blocco del modello &lt;search-if-not-advanced&gt; . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_c= number </code> </p> </td> 
   <td colname="col4"> <p>Specifica il conteggio totale dei risultati da visualizzare. Il valore predefinito è 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>Raccoglie informazioni contestuali per il campo specificato. Le informazioni raccolte vengono inviate nei risultati della ricerca tramite il tag modello <code>&lt;search-context&gt; </code> . Il valore predefinito è <code>body </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_d= type </code> </p> </td> 
   <td colname="col4"> <p>Specifica il tipo di intervallo di date da eseguire. I valori possibili per il tipo sono any, il che significa che non esegue ricerche nell’intervallo di date, custom, che indica che il valore di <code>sp_date_range </code> deve essere utilizzato per determinare le date da cercare, e specifici, che indica che i valori in <code>sp_start_day </code>, <code>sp_start_month </code>, <code>sp_start_year </code>, <code>sp_end_day </code>, <code>sp_end_month </code> e <code>sp_end_year </code> vengono utilizzati per determinare l’intervallo di date da cercare. <code>sp_d </code> è richiesto solo se il modulo di ricerca contiene l’opzione per eseguire ricerche in base a un intervallo personalizzato (tramite  <code>sp_date_range </code>) o in base a un intervallo di date di inizio e fine specifico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <code>sp_d_#= type </code> </p> </td> 
   <td colname="col4"> <p>Specifica il tipo di intervallo di date da eseguire per la query <code>sp_q_# </code> corrispondente. Il "#" viene sostituito da un numero compreso tra 1 e 16 (ad esempio, <code>sp_d_8 </code>, si applica alla query numerata <code>sp_q_8 </code>). </p> <p>È possibile impostare <code>type </code> su qualsiasi, il che significa che non esegue ricerche per intervalli di date, personalizzato, che indica che il valore di <code>sp_date_range_# </code> viene utilizzato per determinare le date da cercare, e specifico, che indica che i valori in <code>sp_q_min_day_# </code>, <code>sp_q_min_month_# </code>, <code>sp_q_min_year_# </code>, <code>sp_q_max_day_# </code>, <code>sp_q_max_month_# </code> e <code>sp_q_max_year_# </code> devono essere utilizzati per determinare l’intervallo di date. L’utilizzo di <code>sp_d_# </code> è richiesto solo se il modulo di ricerca contiene l’opzione per la ricerca in base a un intervallo personalizzato (tramite <code>sp_date_range_# </code>) o in base a un intervallo di date di inizio e fine specifico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>sp_date_range </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifica un intervallo di date predefinito da applicare alla ricerca. Valori maggiori o uguali a zero specificano il numero di giorni da cercare prima della data odierna — ad esempio, un valore di "0" specifica "oggi", un valore di "1" specifica "oggi e ieri", un valore di "30" specifica "entro gli ultimi 30 giorni" e così via. </p> <p>I valori inferiori a zero specificano un intervallo personalizzato come segue: </p> <p>-1 = "None", come se non si specificasse alcun intervallo di date. </p> <p>-2 = "Questa settimana", che cerca da domenica a sabato della settimana corrente. </p> <p>-3 = "Ultima settimana", che cerca da domenica a sabato della settimana precedente alla settimana corrente. </p> <p>-4 = "Questo mese", che cerca le date entro il mese corrente. </p> <p>-5 = "Ultimo mese", che esegue una ricerca nelle date entro il mese precedente il mese corrente. </p> <p>-6 = "Quest'anno", che cerca le date entro l'anno corrente. </p> <p>-7 = "Ultimo anno", che cerca le date entro l'anno precedente l'anno corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_date_range_# </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range_#= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifica un intervallo di date predefinito da applicare alla query <code>sp_q_# </code> corrispondente. Il "#" viene sostituito da un numero compreso tra 1 e 16 (ad esempio, <code>sp_date_range_8 </code>, si applica alla query numerata <code>sp_q_8 </code>). </p> <p>Valori maggiori o uguali a zero specificano il numero di giorni in cui eseguire la ricerca prima della data odierna. Ad esempio, un valore pari a 0 specifica oggi; un valore pari a 1 indica oggi e ieri; un valore di 30 specifica negli ultimi 30 giorni e così via. </p> <p>I valori inferiori a zero specificano un intervallo personalizzato come segue: </p> <p>-1 = "None", come se non si specificasse alcun intervallo di date. </p> <p>-2 = "Questa settimana", che cerca da domenica a sabato della settimana corrente. </p> <p>-3 = "Ultima settimana", che cerca da domenica a sabato della settimana precedente alla settimana corrente. </p> <p>-4 = "Questo mese", che cerca le date entro il mese corrente. </p> <p>-5 = "Ultimo mese", che esegue una ricerca nelle date entro il mese precedente il mese corrente. </p> <p>-6 = "Quest'anno", che cerca le date entro l'anno corrente. </p> <p>-7 = "Ultimo anno", che cerca le date entro l'anno precedente l'anno corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifica un singolo campo su cui duplicare i risultati della ricerca. Tutti i risultati duplicati in quel campo vengono rimossi dai risultati della ricerca. Ad esempio, se per <code>sp_dedupe_field=title </code> nei risultati di ricerca viene visualizzato solo il risultato superiore per un determinato titolo (nessun risultato avrà lo stesso contenuto del campo titolo). Per i campi di tipo con più valori (ad elenco consentiti), per il confronto viene utilizzato l’intero contenuto del campo. È possibile specificare un solo campo. Un "qualificatore tabella" non è consentito nel nome del campo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_e= number </code> </p> </td> 
   <td colname="col4"> <p>Specifica che l'espansione automatica dei caratteri jolly deve essere eseguita per qualsiasi parola della stringa query con più di caratteri numerici. In altre parole, <code>sp_e=5 </code> specifica che le parole con 5 o più caratteri, come "query" o "number", devono essere espanse con il carattere jolly '*', rendendo la ricerca equivalente a una ricerca per "query*" o "number*". Le parole con un numero inferiore di caratteri non vengono espanse, pertanto la ricerca di "parola" non avrebbe un’espansione automatica dei caratteri jolly. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <code>sp_e_#= number </code> </p> </td> 
   <td colname="col4"> <p>Specifica che l'espansione automatica dei caratteri jolly ha luogo per qualsiasi parola della stringa di query <code>sp_q_# </code> corrispondente con più di caratteri numerici. In altre parole, <code>sp_e_2=5 </code> specifica che le parole con cinque o più caratteri nella stringa di query <code>sp_q_2 </code>, come "query" o "number", devono essere espanse con il carattere jolly ' <code>* </code>', rendendo la ricerca equivalente a una ricerca per "query*" o "number*". Le parole con un numero inferiore di caratteri non vengono espanse, pertanto la ricerca di "parola" in <code>sp_q_2 </code> non avrebbe un’espansione automatica dei caratteri jolly. </p> </td> 
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
   <td colname="col3"> <p> <code>sp_f= string </code> </p> </td> 
   <td colname="col4"> <p>Specifica il set di caratteri delle stringhe del parametro di query (ad esempio <code>sp_q </code>). Questa stringa deve sempre corrispondere al set di caratteri della pagina contenente il modulo di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>Definisce una tabella di dati logica costituita dai campi specificati. Ad esempio, una tabella denominata "elementi" costituita dai campi "colore", "dimensione" e "prezzo" verrebbe definita come segue: </p> <p> <code>sp_field_table=items:color,size,price </code> </p> <p>Le tabelle logiche sono più utili in combinazione con i campi che hanno selezionato "Elenchi consentiti" (in <span class="uicontrol"> Impostazioni </span> &gt; <span class="uicontrol"> Metadati </span> &gt; <span class="uicontrol"> Definizioni </span>). Tutti i parametri CGI e i tag modello che utilizzano un nome di campo come valore possono facoltativamente specificare un nome di tabella seguito da un "". prima del nome del campo (ad esempio, <code>sp_x_1=tablename.fieldname </code>). </p> <p>Ad esempio, per eseguire una ricerca per i documenti che contengono uno o più elementi "rossi" di dimensioni "grandi" (dove gli elementi sono rappresentati come righe parallele di metadati), è possibile utilizzare quanto segue: </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p></td><td colname="col4"><p></p><p></p><p><code>sp_i=1 </code><code>sp_i=2 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_k= string </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_l= string </code></p></td><td colname="col4"><p><code>sp_q </code><code>string </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_literal= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_literal=1 </code></p><p><code>sp_literal=0 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_m= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_n= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_not_found_page= url </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p= any/all/phrase </code></p></td><td colname="col4"><p><code>any </code><code>all </code><code>phrase </code></p><p><code>phrase </code><code>all </code><code>sp_p </code></p><p></p><p></p><p><code>sp_p </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p_#= any/all/phrase </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>any </code><code>all </code><code>phrase </code></p><p><code>all </code><code>phrase </code><code>sp_p_# </code><code>any </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>exact </code><code>equivalent </code><code>compatible </code><code>sp_p </code><code>exact </code><code>sp_p </code><code>all </code><code>phrase </code><code>equivalent </code><code>sp_pt </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt_#= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>exact </code><code>equivalent </code><code>exact </code><code>compatible </code><code>sp_p_# </code><code>exact </code><code>sp_p_# </code><code>equivalent </code><code>sp_pt_# </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q= string </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_#= text </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_q_1 </code><code>sp_q_16 </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_day= integer value </code></p><p><code>sp_q_month= integer value </code></p><p><code>sp_q_year= integer value </code></p><p><code>sp_q_day_#= integer value </code></p><p><code>sp_q_month_#= integer value </code></p><p><code>sp_q_year_#= integer value </code></p></td><td colname="col4"><p><code>sp_q_day </code><code>sp_q_month </code><code>sp_q_year </code><code>sp_q </code></p><p><code># </code><code>sp_q_day_6 </code><code>sp_q_6 </code></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p><p><code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p></td><td colname="col4"><p><code>sp_q_location </code><code>sp_q_location_# </code><code># </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_max_relevant_distance= <i>value</i> </code></p><p><code> sp_q_max_relevant_distance_#= <i>value</i> </code></p></td><td colname="col4"><p><code>sp_q_max_relevant_distance </code><code>sp_q_max_relevant_distance_# </code><code># </code></p><p><code>sp_q_max_relevant_distance </code></p><p><code>sp_q_max_relevant_distance_# </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p><p></p></td><td colname="col03"><p></p><p></p></td><td colname="col3"><p><code> sp_q_min_day=<i>integer value</i> </code></p><p><code> sp_q_min_month=<i>integer value</i> </code></p><p><code> sp_q_min_year=<i>integer value</i> </code></p><p><code> sp_q_max_day=<i>integer value</i> </code></p><p><code> sp_q_max_month=<i>integer value</i> </code></p><p><code> sp_q_max_year=<i>integer value</i> </code></p><p><code> sp_q_min_day_#=<i>integer value</i> </code></p><p><code> sp_q_min_month_#=<i>integer value</i> </code></p><p><code> sp_q_min_year_#=<i>integer value</i> </code></p><p><code> sp_q_max_day_#=<i>integer value</i> </code></p><p><code> sp_q_max_month_#=<i>integer value</i> </code></p><p><code> sp_q_max_year_#=<i>integer value</i> </code></p></td><td colname="col4"><p><code>sp_q_min_day </code><code>sp_q_min_month </code><code>sp_q_min_year </code><code>sp_q_max_day </code><code>sp_q_max_month </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_day_6 </code><code>sp_q_6 </code></p><p></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_min= value </code></p><p><code>sp_q_max= value </code></p><p><code>sp_q_min_#= value </code></p><p><code>sp_q_max_#= value </code></p><p><code>sp_q_exact_#=value </code></p></td><td colname="col4"><p><code>sp_q_min </code><code>sp_q_max </code><code>sp_q_exact </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_8 </code><code>sp_q_8 </code></p><p><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code></p><p><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_nocp= 1 or 0 </code></p><p><code>sp_q_nocp_#= 1 or 0 </code></p></td><td colname="col4"><p><code>0 </code></p><p><code>1 </code></p><p><code>sp_q_nocp </code><code>sp_q </code><code># </code><code>sp_q_nocp_8 </code><code>sp_q_8 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_required= 1 or 0 or -1 </code></p><p><code>sp_q_required_#= 1 or 0 or -1 </code></p></td><td colname="col4"><p></p><p><code>sp_q_required </code><code>sp_q </code></p><p><code># </code><code>sp_q_required_8 </code><code>sp_q_8 </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_referrer= url </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>ro </code></p><p></p><p><code>sp_ro=body:10 </code></p><p></p><p><code>sp_ro=body:9|title:9 </code></p><p><p><code>sp_ro=title:10 </code><code>title </code><code>sp_ro </code><code>sp_ro </code></p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_s= number </code></p></td><td colname="col4"><p></p><p><code>sp_s </code><code>sp_s=title </code><code>sp_s </code></p><p></p><p><code>sp_s </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code></p><p><code>sp_field_table </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sr= field </code></p></td><td colname="col4"><p><code>sp_sr </code></p><p><code>sp_sr </code><code>&lt;input type="hidden" name="sp_sr" value=""&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sfvl_field= string </code></p></td><td colname="col4"><p><code>search-field-value-list</code></p><p><code>sp_sfvl_field </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>search-field-value-list </code></p><p><code>dynamic-facet-field-count </code><code>dynamic-facet-field-count </code></p><p><code>sp_sfvl_df_count </code><code>dynamic-facet-field-count </code><code>sp_sfvl_df_count </code><code>sp_sfvl_df_count </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p><p><code>sp_sfvl_df_count </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_count </code></p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_staged= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_staged=1 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_start_day= number </code></p><p><code>sp_start_month= number </code></p><p><code>sp_start_year= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_suggest_q= number </code></p></td><td colname="col4"><p><code>sp_suggest_q </code><code>sp_q[_#] </code></p><p><code>sp_suggest_q </code><code>sp_q </code></p><p><code>sp_suggest_q=1 </code><code>sp_q_1 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_t= string </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_trace= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_stage=1 </code></p><p></p><p><p></p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_w= <i>sound-alike-enable</i> </code></p><p><code> sp_w_control=<i>sound-alike-control</i> </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p><p></p><code>sp_w_control </code></p><p><code>sp_w_control=0 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control=1 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control </code><code>sp_w </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x= field </code></p></td><td colname="col4"><p><code>sp_q </code><code>sp_x </code></p><p></p><p><code>sp_x </code></p><p></p><p><code>sp_x=any </code><code>sp_x </code></p><p><code>sp_x </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x_#= field-name </code></p></td><td colname="col4"><p><code>sp_q_# </code><code> # </code><code>sp_x_8 </code></p><p><code>sp_x_# </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code></p><p><code>sp_x </code><code>sp_x_# </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code></p></td></tr></tbody></table>

## Esempio tipico di utilizzo dei parametri CGI di ricerca back-end {#section_260012BBC2514CC9A8E02E53DE8B41EE}

Le seguenti query di collegamento avviano una ricerca utilizzando &quot;Musica&quot; come query di ricerca e utilizzano tutti i parametri predefiniti. Per garantire la leggibilità, l’URL è suddiviso in due righe. Nel tuo HTML, questo collegamento dovrebbe essere tutti su una riga.

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

In genere, quando si avvia una ricerca è consigliabile utilizzare i parametri predefiniti. In questo modo, viene visualizzata la prima pagina, ordinata in base alla pertinenza, e consente al cliente di scegliere altre pagine e altre opzioni. Se il modulo di ricerca sul sito include opzioni per le raccolte, passa il nome della raccolta come parametro.

## Un esempio dettagliato sull&#39;utilizzo dei parametri CGI di ricerca back-end {#section_5FA3C620D5124FB2AB28857F8D8473F6}

Le seguenti query del modulo visualizzano i risultati `25` a partire dal risultato `10`. I riepiloghi non vengono visualizzati, l’ordinamento è in base alla data e viene utilizzata la raccolta denominata `support`. Vengono restituiti solo i documenti datati negli ultimi 30 giorni.

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

