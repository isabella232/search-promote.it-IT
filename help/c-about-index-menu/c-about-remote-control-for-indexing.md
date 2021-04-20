---
description: Ogni volta che il tuo sito web cambia, puoi eseguire uno script o un programma che richiede che il robot di ricerca esegua un indice utilizzando il telecomando.
solution: Target
title: Informazioni sul telecomando per l'indicizzazione
topic: Index,Site search and merchandising
uuid: 20e230c6-5c1a-4bf4-bff3-b8236d14ab21
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---


# Informazioni sul telecomando per l&#39;indicizzazione{#about-remote-control-for-indexing}

Ogni volta che il tuo sito web cambia, puoi eseguire uno script o un programma che richiede che il robot di ricerca esegua un indice utilizzando il telecomando.

## Uso del telecomando per l&#39;indicizzazione {#concept_C79B322190E84106A434E5C6D4A4118F}

La richiesta di indicizzazione del telecomando proviene in genere da uno script o da un programma che si trova sul server.

Il robot esegue gli stessi passaggi di indicizzazione come se fosse stato avviato manualmente dal menu [!DNL Index]. Per inviare una richiesta di controllo remoto, è necessario configurare la password e le stringhe di risposta necessarie.

## Come effettuare una richiesta di controllo remoto {#section_42FAB2BAB25A4E24BEA69566C6D1C70F}

Per effettuare una richiesta di controllo remoto, utilizzare i seguenti esempi di formato in base alla posizione del centro dati:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Posizione del centro dati </p> </th> 
   <th colname="col2" class="entry"> <p>Esempio </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Londra </p> </td> 
   <td colname="col2"> <p> <code> https://center.lon5.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>America del Nord </p> </td> 
   <td colname="col2"> <p> <code> https://center.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Singapore </p> </td> 
   <td colname="col2"> <p> <code> https://center.sin2.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

 oppure 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa e valore </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_a= sp9999999  </span> </p> </td> 
   <td colname="col2"> <p> Numero del tuo account. </p> <p>Puoi trovare il tuo numero di account in <span class="uicontrol"> <b>Impostazioni</b> </span> &gt; <span class="uicontrol"> <b>Opzioni account</b> </span> &gt; <span class="uicontrol"> <b>Impostazioni account</b> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_lines= N  </span> </p> </td> 
   <td colname="col2"> <p>Consente di controllare lo stato di una ricerca per indicizzazione in esecuzione. </p> <p> <span class="codeph">  N  </span> è un numero intero positivo o  <span class="codeph"> tutto  </span>. Se si tratta di un valore numerico, le ultime <span class="codeph"> N </span> righe del file di log dell'indice corrispondente sono incluse nella risposta JSON. </p> <p>Se il valore è <span class="codeph"> tutto </span>, viene restituito l’intero file. </p> <p>Se il valore è <span class="codeph"> 0 </span>, non vengono restituite informazioni di registro. Questo valore è il valore predefinito per una query di stato dell'indice in esecuzione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= op  </span> </p> </td> 
   <td colname="col2"> <p>Consente di specificare una delle seguenti operazioni di indicizzazione da eseguire: </p> <p> 
     <ul id="ul_6CA190AC41694BC293FC7C6BABA629FE"> 
      <li id="li_EFC76E31D47E473F9A56B2EBA8A97CA1"> <span class="codeph"> full_index  </span> <p>Il robot di ricerca esegue un indice completo del tuo sito web. </p> </li> 
      <li id="li_A9ACE21718804A21B3DA7B84AB6729D3"> <span class="codeph"> incrementale_index  </span> <p>Il robot di ricerca esegue un indice incrementale utilizzando la configurazione impostata in <span class="uicontrol"> <b>Indice</b> </span> &gt; <span class="uicontrol"> <b>Indice incrementale</b> </span> &gt; <span class="uicontrol"> <b>Configurazione</b></span>. </p> </li> 
      <li id="li_722FE409AE454AD48ACE95C4CDC7A00B"> <span class="codeph"> verticale_index  </span> <p>Il robot di ricerca esegue un aggiornamento verticale utilizzando la configurazione impostata in <span class="uicontrol"> <b>Indice</b> </span> &gt; <span class="uicontrol"> <b>Aggiornamento verticale</b> </span> &gt; <span class="uicontrol"> <b>Configurazione</b></span>. </p> <p>Vedere <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Informazioni sull'aggiornamento verticale</a>. </p> </li> 
      <li id="li_A40B513CE17043A4925CE3D4DE0B48A4"> <span class="codeph"> script_index  </span> <p>Il robot di ricerca esegue un indice incrementale utilizzando il file di testo specificato in <span class="uicontrol"> <b>Indice</b> </span> &gt; <span class="uicontrol"> <b>Indice script</b> </span> &gt; <span class="uicontrol"> <b>Configurazione</b></span>. </p> </li> 
      <li id="li_A0BC7F1373B14393997BAB7690FD3EF7"> <span class="codeph"> full_staged_index  </span> <p>Il robot di ricerca esegue un indice completo in fase del sito web. </p> </li> 
      <li id="li_47753E358457443A95B384A278FACA83"> <span class="codeph"> incrementale_staged_index  </span> <p>Il robot di ricerca esegue un indice di staging incrementale utilizzando la configurazione impostata in <span class="uicontrol"> <b>Indice</b> </span> &gt; <span class="uicontrol"> <b>Indice incrementale</b> </span> &gt; <span class="uicontrol"> <b>Configurazione</b></span>. </p> </li> 
      <li id="li_C8B5F8F1208E438ABEFDF9129A6B14A3"> <span class="codeph"> Vertical_staged_index  </span> <p>Il robot di ricerca esegue un aggiornamento in fase verticale utilizzando la configurazione impostata in <span class="uicontrol"> <b>Indice</b> </span> &gt; <span class="uicontrol"> <b>Aggiornamento verticale</b> </span> &gt; <span class="uicontrol"> <b>Configurazione</b></span>. </p> </li> 
     </ul> </p> <p>Nota:  Per utilizzare Aggiornamenti verticali, potrebbe essere necessario che sia attivato nel tuo account dal rappresentante dell’account di Adobe o dal supporto di Adobe. </p> <p>Consultare <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Informazioni sull'aggiornamento verticale </a>. </p> <p>Puoi aggiungere <span class="codeph"> _save </span> a uno qualsiasi dei valori <span class="codeph"> sp_operation </span> indicati sopra per fare in modo che il robot di ricerca tenti di utilizzare il contenuto salvato. Ad esempio, puoi specificare quanto segue: </p> <p> <code class="syntax html"> sp_operation=full_index_saved </code> </p> <p> oppure  </p> <p> <code class="syntax html"> sp_operation=full_staged_index_saved </code> </p> <p>In alternativa, puoi aggiungere <span class="codeph"> _status </span> a uno qualsiasi dei valori <span class="codeph"> sp_operation </span> per richiedere un rapporto sullo stato dell'operazione corrente o più recente. Ad esempio, puoi specificare quanto segue: </p> <p> <code class="syntax html"> sp_operation=full_index_status </code> </p> <p> oppure  </p> <p> <code class="syntax html"> sp_operation=full_staged_index_status </code> </p> <p>e i risultati vengono restituiti come oggetto JSON. Includi <span class="codeph"> sp_lines=N </span> per includere N righe del file di registro associato. Se N è negativo, sono incluse le ultime N linee. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= pushlive  </span> </p> </td> 
   <td colname="col2"> <p> Consente di inviare in remoto un indice in esecuzione. </p> <p>Qualsiasi tentativo di aggiungere <span class="codeph"> _save </span> all'operazione push in tempo reale viene ignorato. </p> <p>Quando si esegue un'operazione <span class="codeph"> push </span>, viene restituita al server una stringa di testo di risposta OK, Priorità o Errore. Puoi specificare queste stringhe di risposta nella pagina <span class="wintitle"> Controllo remoto </span> . </p> <p>Consultare <a href="../c-about-index-menu/c-about-remote-control-for-indexing.md#task_57C296258404448DA7A5ADC9B7232391" format="dita" scope="local"> Configurazione del telecomando per l'indicizzazione</a>. </p> <p>Se esegui il push live quando non è presente un indice di staging, non si verifica nulla e viene restituita la stringa di risposta OK. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_password= xxxxxx  </span> </p> </td> 
   <td colname="col2"> <p>Password del telecomando. </p> </td> 
  </tr> 
 </tbody> 
</table>

La ricerca restituisce i dati sotto forma di una risposta HTTP corretta. La risposta completa è composta da uno stato HTTP, intestazioni di risposta HTTP, una riga vuota e la stringa di risposta.

Si supponga, ad esempio, di eseguire la seguente richiesta di controllo remoto:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index
```

Di seguito è riportata la risposta dal server:

```
Status: 200 OK 
Content-type: text/plain 
OK
```

In alternativa, si supponga di eseguire la seguente richiesta di stato del telecomando:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status
```

La risposta dal server potrebbe avere l&#39;aspetto seguente:

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:58:58-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "status": 1, 
    "message": "ok" 
}
```

Per ottenere le prime dieci righe dell’elenco di log associate a questa operazione di indice, insieme al relativo stato, viene utilizzata la seguente query:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=10
```

Risposta dal server:

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:59:30-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "offset": 672, 
    "lines": [ 
        "07/25 16:40:07 PST   ======== Starting manual crawl of account sp99999999. ========", 
        "07/25 16:40:08 PST   Loading existing data", 
        "07/25 16:40:08 PST   Downloading entrypoint https://www.atomz.com/", 
        "07/25 16:40:08 PST   Robots.txt exclude mask: https://www.atomz.com/snap", 
        "07/25 16:40:08 PST   Exclude mask: regexp ^https://www.atomz.com/$", 
        "07/25 16:40:08 PST   Include mask: https://www.atomz.com/", 
        "07/25 16:40:08 PST   Downloading https://www.atomz.com/style.css", 
        "07/25 16:40:09 PST   Ignoring https://www.atomz.com/style.css, document type 'text/css'.", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/privacy.html", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/terms.html" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

Osserva il valore `offset` . Questo valore identifica la posizione di offset del file nel file di registro in cui la lettura è stata interrotta. Per leggere le dieci righe *successive* nel file , includi, in questo esempio, `&sp_offset=672` nella richiesta inviata al server.

Utilizzando `sp_offset`, è possibile utilizzare in modo efficace la pagina tramite un file di registro.

Per ottenere le dieci righe *ultime* del registro, insieme allo stato , specifica il conteggio come numero negativo. Ad esempio, specifica `sp_lines=` con un valore di `-10` come segue:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=-10
```

Risposta dal server:

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T11:01:14-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "lines": [ 
        "07/25 16:40:20 PST   End Time: 07/25/2017 16:40:20 PST", 
        "07/25 16:40:20 PST   Elapsed Time: 13 seconds", 
        "07/25 16:40:20 PST   Pages Crawled: 3 pages", 
        "07/25 16:40:20 PST   Pages Indexed: 3 pages", 
        "07/25 16:40:20 PST   Words/Bytes Indexed: 2373 words/ 20618 bytes", 
        "07/25 16:40:20 PST   Errors: 0", 
        "07/25 16:40:20 PST   *** Index Summary ***", 
        "07/25 16:40:20 PST   Total Pages: 3", 
        "07/25 16:40:20 PST   --------------------------------------------------------------------", 
        "07/25 16:40:20 PST   ======== Finish manual crawl of account sp99999999: Done. ========" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

Non viene restituito alcun valore `offset`, poiché l’operazione è terminata alla fine del file e non sono presenti altre righe da leggere.

## Configurazione del telecomando per l&#39;indicizzazione {#task_57C296258404448DA7A5ADC9B7232391}

Ogni volta che il sito web cambia, è possibile utilizzare il controllo remoto per eseguire uno script o un programma dal server, richiedendo che il robot di ricerca esegua un indice.

**Per configurare il controllo remoto per l&#39;indicizzazione**

1. Scegliere **[!UICONTROL Index]** > **[!UICONTROL Remote Control]** dal menu del prodotto.
1. Nella pagina [!DNL Remote Control] , imposta ogni opzione del campo di configurazione per poter inviare automaticamente una richiesta di indicizzazione dal server per indicizzare il sito web.

   <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>Opzione </p> </th> 
    <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Password controllo remoto </p> </td> 
    <td colname="col2"> <p>Specificare la password del telecomando. </p> <p> Le password sono sensibili all'uso di maiuscole e minuscole, con una lunghezza di almeno sei caratteri e devono includere almeno una lettera. Si consiglia inoltre di includere almeno un numero. </p> <p>Non utilizzare la password di accesso alla ricerca/merchandising del sito. </p> <p>La password viene utilizzata in ogni richiesta di controllo remoto. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Stringa di risposta OK </p> </td> 
    <td colname="col2"> <p>Consente di specificare una stringa di testo di risposta OK se l'operazione di indice richiesta inizia correttamente. In questi casi, il robot di ricerca restituisce la stringa di risposta OK al server. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Stringa di risposta prioritaria </p> </td> 
    <td colname="col2"> <p>Se è in corso un'altra operazione di indicizzazione quando viene effettuata la richiesta remota, il robot di ricerca non può eseguire l'indice richiesto. In questi casi, la stringa di testo della risposta Priorità viene restituita al server. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Stringa di risposta di errore </p> </td> 
    <td colname="col2"> <p>Consente di specificare una stringa di testo per la risposta a un errore Se la password non è corretta o se si verifica un altro errore. In questi casi, il robot di ricerca restituisce la stringa di risposta Errore al server. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
