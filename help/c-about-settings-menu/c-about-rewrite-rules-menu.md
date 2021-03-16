---
description: Utilizza il menu Riscrittura regole per impostare la ricerca per indicizzazione e le regole dell’URL di ricerca e del titolo.
solution: Target
subtopic: Rewrite Rules
title: Menu Regole di riscrittura
topic: Impostazioni, Ricerca nel sito e merchandising
uuid: 77ee84dd-fdba-4d34-ae8e-2fe786599800
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '10202'
ht-degree: 0%

---


# Menu Riscrittura regole {#about-the-rewrite-rules-menu}

Utilizza il menu Riscrittura regole per impostare la ricerca per indicizzazione e le regole dell’URL di ricerca e del titolo.

## Informazioni sulle regole URL dell’archivio elenchi di ricerca per indicizzazione {#concept_B71CF4C8030A4A74A22C3BFE4DE3B865}

Le regole URL di ricerca per indicizzazione specificano come vengono riscritti gli URL che incontra all’interno del contenuto web. Puoi specificare un numero illimitato di regole e condizioni e manipolare qualsiasi parte degli URL incontrati.

<!-- 

c_about_crawl_list_store_url_rules.xml

 -->

Le regole di ricerca per indicizzazione sono più utili per riscrivere le parti dinamiche di un URL, ad esempio un identificatore di sessione univoco per ogni cliente che visita il tuo sito web. È inoltre possibile utilizzare le regole di riscrittura per nascondere parti di un URL, ad esempio parametri di query, dal robot di ricerca. Per impostazione predefinita, non viene specificata alcuna regola e non viene eseguita alcuna riscrittura URL.

Man mano che un sito web viene sottoposto a ricerca per indicizzazione, gli URL di contenuto incorporato vengono memorizzati in un elenco temporaneo di pagine web aggiuntive da esaminare. Prima di aggiungere un URL a questo elenco, vengono applicate le regole di riscrittura store. In genere, le regole di riscrittura store vengono utilizzate per rimuovere un ID sessione da un URL o per applicare un ID sessione specifico per la ricerca per indicizzazione. Quando il robot di ricerca recupera un URL dall’elenco, le regole di riscrittura Recupera vengono utilizzate per manipolare nuovamente parti di tale URL. In genere, le regole di recupero vengono utilizzate per inserire nuovamente dati sensibili al tempo nell’URL. È questo URL finale che viene utilizzato per recuperare effettivamente la pagina dal tuo sito web.

Consulta [Informazioni sulle regole di recupero URL dell&#39;elenco di ricerca per indicizzazione](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA).

In genere, si utilizzano esclusivamente le regole URL store. Le regole URL di recupero sono necessarie solo se gli URL contengono dati dinamici, come un ID sessione, e se i dati dinamici cambiano nel tempo per rimanere validi. In questo caso, utilizza le regole URL del negozio per ottenere lo stato più recente dei dati dagli URL incontrati. Quindi si utilizza Recupera regole URL per aggiungere quei dati a ogni URL quando il robot di ricerca cerca di recuperare la pagina.

Ogni regola è specificata con una direttiva di riscrittura (RewriteRule) e una o più condizioni di riscrittura facoltative (RewriteCond). L&#39;ordine delle regole è importante. Il set di regole viene ripetuto per regola. Quando una regola corrisponde, esegue il ciclo tra le condizioni di riscrittura corrispondenti. Una regola URL di ricerca per indicizzazione viene specificata nel modo seguente:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

Quando viene rilevato un URL incorporato, il robot di ricerca cerca di associare l’URL al pattern di ciascuna regola di ricerca per indicizzazione. Se il pattern corrisponde, il motore di riscrittura cerca le direttive RewriteCond corrispondenti. Se non sono presenti condizioni, l’URL viene sostituito da un nuovo valore costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se le condizioni esistono, vengono elaborate nell’ordine in cui sono elencate. Il motore di riscrittura cerca di corrispondere a un pattern di condizione (CondPattern) rispetto a una stringa di test (TestString). Se le due corrispondenze, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l’URL viene sostituito con la sostituzione specificata nella regola. Se la condizione non viene soddisfatta, l&#39;insieme completo di condizioni e la regola corrispondente falliscono.

## Informazioni sulle direttive RewriteRule {#section_162122340BB34F12BB9A36DC9349092B}

Una direttiva RewriteRule ha la seguente forma:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` può essere un&#39;espressione regolare POSIX applicata all&#39;URL corrente. L’&quot;URL corrente&quot; può essere diverso dall’URL originale richiesto, perché le regole precedenti potrebbero aver già trovato corrispondenza e modificato l’URL.

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Non è possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per preimpostare il pattern. Il carattere &quot;not&quot; consente di negare un pattern, ovvero di essere true solo se l’URL corrente NON corrisponde a questo pattern. Il carattere &quot;not&quot; può essere utilizzato quando è meglio corrispondere a un pattern negativo o come regola predefinita finale.

>[!NOTE]
>
>Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato quando la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento di sfondo nel pattern, a cui possono fare riferimento i parametri Sostituzione e Modello di consenso.

**** SostituzioneL’URL viene sostituito dalla stringa di sostituzione che contiene quanto segue:

Testo normale: Testo passato attraverso invariato.

I riferimenti di sfondo consentono di accedere alle parti raggruppate (tra parentesi) della serie o della serie di cond. Di seguito sono riportati i due tipi di riferimenti retrovisori:

* **RewriteRule** BackreferencesQuesti corrispondono a riferimenti precedenti nel pattern RewriteRule corrispondente e si presentano come $N (0  &lt;> Ad esempio, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* **RewriteCond** BackreferencesQuesti corrispondono a backreferences nell’ultimo pattern di cond RewriteCond corrispondente e prendono il modulo %N (0  &lt;>

Variabili: Si tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE è una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili di ambiente, consulta il flag `*[E]*` .

Funzioni: Si tratta delle funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è il seguente:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.
* l&#39;URL di escape codifica tutti i caratteri in *key*.
* I caratteri &quot;a&quot;.z, A..Z&#39;, &#39;0&#39;.9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati; gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel loro equivalente con codifica URL %xx.
* unescape trasforma &#39;+&#39; di nuovo in spazio e tutti i caratteri codificati con URL %xx in caratteri singoli.

>[!NOTE]
>
>Esiste una stringa di sostituzione speciale: `'-'` significa &quot;NO substitution&quot;. La stringa `'-'` viene spesso utilizzata con il flag C (chain), che consente di associare un URL a diversi pattern prima che si verifichi una sostituzione.

**Flag**

(facoltativo) Racchiudere i flag tra parentesi `[]`. I flag multipli sono separati da virgole.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Ultima regola. </p> <p>Interrompe il processo di riscrittura e non applica alcuna regola di riscrittura aggiuntiva. Usa questo flag per impedire ulteriori elaborazioni dell’URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Prossimo turno. </p> <p> Ripete il processo di riscrittura (iniziando di nuovo con la prima regola di riscrittura) utilizzando l’URL dell’ultima regola di riscrittura (non l’URL originale). Fai attenzione a non creare un deadloop! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Concatenato con la regola successiva. </p> <p>Sposta la regola corrente alla regola successiva (che può anche essere incatenata alla regola seguente e così via). Se una regola corrisponde, il processo di sostituzione continua come di consueto. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p> Rende il pattern privo di distinzione tra maiuscole e minuscole (ovvero, non esiste alcuna differenza tra "A-Z" e "a-z") quando il pattern viene confrontato con l’URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole di num successive nel set di regole. Usa questo flag per creare costrutti pseudo-then-else. L'ultima regola della clausola then diventa un salto=N dove N è il numero di regole nella clausola else. </p> <p> <p>Nota:  Questo flag non è lo stesso del flag 'chain|C'!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Imposta la variabile ambientale. </p> <p>Crea una variabile ambientale "VAR" impostata sul valore VAL, in cui VAL può contenere riferimenti retroversi di espressioni regolari, $N e %N, che vengono espansi. Puoi utilizzare questo flag più volte per impostare più variabili. Le variabili possono essere successivamente rimandate in un pattern RewriteCond seguente tramite %{VAR}. </p> <p>Usa questo flag per rimuovere e ricordare le informazioni dagli URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le regole di riscrittura dell&#39;archivio e le regole di riscrittura di recupero condividono i valori delle variabili. A causa di questo comportamento, è possibile impostare una variabile su un valore sessionid sensibile al tempo quando viene rilevato e memorizzato un URL incorporato. Quando l’URL successivo viene recuperato dall’elenco di archiviazione temporanea, è possibile aggiungere ad esso il valore sessionid più recente prima del recupero della pagina.

**Esempio di RewriteRule con una funzione**

Supponiamo di avere un server sensibile a maiuscole e minuscole che gestisce le stringhe `"www.mydomain.com"` e `"www.MyDomain.com"` in modo diverso. Affinché il server funzioni correttamente, assicurati che il dominio sia sempre `"www.mydomain.com"` anche se alcuni documenti contengono collegamenti che fanno riferimento a `"www.MyDomain.com."` A questo scopo, puoi utilizzare la seguente regola:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

Questa regola di riscrittura utilizza la funzione `tolower` per riscrivere la porzione di dominio di un URL in modo che sia sempre minuscola come nei seguenti casi:

1. Il pattern `(^https://([^/]*)(.*)$)` contiene un riferimento di sfondo `([^/]*)` che corrisponde a tutti i caratteri compresi tra `https://` e il primo `/` nell’URL. Il pattern contiene anche un secondo riferimento di sfondo `(.*)` che corrisponde a tutti i caratteri rimanenti nell’URL.

1. La sostituzione `(https://${tolower:$1}$2)` indica al motore di ricerca di riscrivere l&#39;URL utilizzando la funzione `tolower` sul primo riferimento di sfondo `(https:// ${tolower:$1}$2)` lasciando il resto dell&#39;URL inalterato `(https://${tolower:$1} $2)`.

Pertanto, un URL del modulo `https://www.MyDomain.com/INTRO/index.Html` viene riscritto come `https://www.mydomain.com/INTRO/index.Html`.

## Informazioni sulle direttive RewriteCond {#section_CD5A19B2D3204F73B645411931FC34A1}

La direttiva RewriteCond definisce una condizione di regola. Quando un RewriteCond precede un RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e se si applicano le condizioni aggiuntive. Le condizioni di riscrittura si presentano come segue:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` è una stringa che può contenere i seguenti costrutti:

Testo normale: Testo passato attraverso invariato.

I riferimenti di sfondo consentono di accedere alle parti raggruppate (tra parentesi) della serie o della serie di cond. Di seguito sono riportati i due tipi di riferimenti retrovisori:

* **RewriteRule** BackreferencesQuesti corrispondono a riferimenti precedenti nel pattern RewriteRule corrispondente e si presentano come $N (0  &lt;> Ad esempio, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`.

* **RewriteCond** BackreferencesQuesti corrispondono a backreferences nell’ultimo pattern di cond RewriteCond corrispondente e prendono il modulo %N (0&lt;>

Variabili: Si tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili, consulta il flag RewriteRule *`[E]`* .

Funzioni: Si tratta delle funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è il seguente:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.
* L’URL di escape codifica tutti i caratteri nella chiave . I caratteri &quot;a&quot;.z, A..Z&#39;, &#39;0&#39;.9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi vengono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel loro equivalente con codifica URL `%xx`.
* unescape trasforma &#39;+&#39; di nuovo in spazio e tutti i caratteri di codifica URL `%xx` in caratteri singoli.

**** CondPatterns è un&#39;espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un carattere `!` (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, puoi utilizzare una delle seguenti varianti speciali:

>[!NOTE]
>
>È inoltre possibile preimpostare tutti i test con un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lessicamente meno. </p> <p> Tratta CondPattern come una stringa semplice e lo confronta lessicalmente con TestString. True se TestString è lessicalmente minore di CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Più grande lessicalmente. </p> <p> Tratta CondPattern come una stringa semplice e lo confronta lessicalmente con TestString. True se TestString è lessicalmente maggiore di CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexicamente uguale. </p> <p> Tratta CondPattern come una stringa semplice e lo confronta lessicalmente con TestString. True se TestString è lessicalmente uguale a CondPattern, ovvero se le due stringhe sono esattamente uguali (carattere per carattere). Se CondPattern è solo "" (due virgolette), questo confronta TestString con la stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag**
 (facoltativo) Racchiudono i flag tra parentesi  `[]`. I flag multipli sono separati da virgole.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Nessun caso. </p> <p>Questo flag fa sì che il test non faccia distinzione tra maiuscole e minuscole, ovvero non c'è differenza tra "A-Z" e "a-z" sia nel TestString espanso che nel CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>O la condizione successiva. </p> <p>Utilizza questo flag per combinare le condizioni della regola con un operatore OR locale anziché con l'operatore AND implicito. Senza questo flag, dovresti scrivere il cond/rule più volte. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

Alcune pagine web assegnano una variabile CGI &quot;sessionid&quot; la prima volta che un visitatore arriva a un sito. Questa variabile viene utilizzata per identificare il visitatore e, mentre il visitatore naviga nel sito, viene trasmessa la variabile . Poiché il robot di ricerca assomiglia a un visitatore del sito, gli viene assegnato un numero &quot;sessionid&quot;. Il robot di ricerca mantiene questo singolo valore &quot;sessionid&quot;, anche se una seconda pagina del sito cerca di assegnare un nuovo valore. Per questo motivo, sono necessarie due regole di riscrittura.

La prima regola viene utilizzata per identificare e memorizzare la variabile sessionid:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule utilizza un flag E `([E=sessionid:$1])` per assegnare il valore corrente del parametro sessionid CGI alla variabile `sessionid`. Il `$1` fa riferimento al primo riferimento di sfondo, contenuto tra il primo set di parentesi nel Pattern di RewriteRule `([^&#]+)`.

L&#39;espressione regolare `^&#]+` corrisponde alla porzione di un URL tra la parola `sessionid` e il carattere successivo `**&**or**#**`. Poiché questa RewriteRule viene utilizzata solo per creare il valore iniziale per la variabile sessionid, non viene riscritta. Il campo Sostituzione della regola è impostato su `-` per indicare che non è richiesta alcuna riscrittura.

RewriteCond esamina la variabile `sessionid` ( `%{sessionid}`). Se non ha nemmeno un singolo carattere (!.+), quindi la RewriteRule corrisponde.

Utilizzando questa regola, l’URL viene letto come `https://www.domain.com/home/?sessionid=1234&function=start` e assegna il valore `1234` alla variabile `sessionid`.

La seconda regola viene utilizzata per riscrivere tutti gli URL che corrispondono al seguente pattern di RewriteRule:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

Il pattern RewriteRule contiene due riferimenti di sfondo: `(.+)` e `(.*)`. Il primo backreference corrisponde a tutti i caratteri precedenti a `sessionid`. Il secondo backreference corrisponde a tutti i caratteri dopo il termine `&` o `#`.

Il pattern di sostituzione riscrive l’URL utilizzando il primo riferimento di sfondo, seguito dalla stringa &quot;sessionid=&quot;, seguita dal valore della variabile ID di sessione definita dalla prima regola `%{sessionid}`, seguita dal secondo riferimento di sfondo. `($1sessionid=%{sessionid} $2)`

Tieni presente che questa regola di riscrittura non contiene un RewriteCond. Di conseguenza, causa una riscrittura per tutti gli URL che corrispondono alla regola di riscrittura *Pattern*. Pertanto, se il valore della variabile sessionid ( `%{sessionid}`) è `1234`, un URL del modulo `https://www.domain.com/products/?sessionid=5678&function=buy` viene riscritto come `https://www.domain.com/products/?sessionid=1234&function=buy`

## Conferma {#section_B17088EF38244496BC1DDD4ECF75EB5B}

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta di una regola per l’URL dell’archivio degli elenchi di ricerca per indicizzazione {#task_22DD40DF95584B12BE8E6ECFBF579BCD}

Puoi aggiungere regole per l’archivio degli elenchi di ricerca per indicizzazione degli URL per specificare in che modo vengono riscritti gli URL che si incontrano all’interno del contenuto web. Puoi specificare un numero illimitato di regole e condizioni e manipolare qualsiasi parte degli URL incontrati.

<!-- 

t_adding_a_crawl_list_store_url_rule.xml

 -->

**Per aggiungere regole URL dell’archivio elenchi di ricerca per indicizzazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Store URL Rules]**.
1. Nel campo [!DNL Crawl List Store URL Rules] , immetti le regole desiderate.

   Sono consentite righe vuote e di commento che iniziano con un carattere &#39;#&#39; (hash).
1. (Facoltativo) Nella pagina [!DNL Crawl List Store URL Rules], nel campo [!DNL Test Crawl List Store URL Rules], immetti un URL di test di cui desideri verificare le regole di ricerca per indicizzazione, quindi fai clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Crawl List Store URL Rules] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle regole URL di recupero degli elenchi di ricerca per indicizzazione {#concept_EC8E2E48B99A458D8567B526C9827CBA}

Regole URL per ricerca per indicizzazione specifica come vengono riscritti gli URL incontrati all’interno del contenuto web. Puoi specificare un numero illimitato di regole e condizioni e manipolare qualsiasi parte degli URL incontrati.

<!-- 

c_about_crawl_list_retrieve_url_rules.xml

 -->

Prima che gli effetti delle regole siano visibili ai clienti, assicurati di ricostruire l&#39;indice del sito.

Le regole di ricerca per indicizzazione sono più utili per riscrivere le parti dinamiche di un URL, ad esempio un identificatore di sessione univoco per ogni cliente che visita il tuo sito web. È inoltre possibile utilizzare le regole di riscrittura per nascondere parti di un URL, ad esempio parametri di query, dal robot di ricerca. Per impostazione predefinita, non viene specificata alcuna regola e non viene eseguita alcuna riscrittura URL.

Man mano che un sito web viene sottoposto a ricerca per indicizzazione, gli URL di contenuto incorporato vengono memorizzati in un elenco temporaneo di pagine web aggiuntive da esaminare. Quando il robot di ricerca recupera un URL dall’elenco, le regole di sovrascrittura di recupero vengono utilizzate per manipolare parti di tale URL. In genere, le regole di recupero vengono utilizzate per inserire dati sensibili al tempo in un URL. È questo URL finale che viene utilizzato per recuperare effettivamente la pagina dal tuo sito web.

Le regole di riscrittura di recupero sono necessarie solo se gli URL contengono dati dinamici, come un ID sessione, e se tali dati dinamici cambiano nel tempo per rimanere validi. In questo caso, utilizza le regole di riscrittura store per ottenere lo stato più recente dei dati dagli URL incontrati. Quindi, utilizza le regole di riscrittura di recupero per aggiungere quei dati a ogni URL quando i robot di ricerca recuperano la pagina.

Ogni regola è specificata con una direttiva di riscrittura (RewriteRule) e una o più condizioni di riscrittura facoltative (RewriteCond). L&#39;ordine delle regole è importante. Il set di regole viene ripetuto per regola. Quando una regola corrisponde, esegue il ciclo tra le condizioni di riscrittura corrispondenti. Una regola URL di ricerca per indicizzazione viene specificata nel modo seguente:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

Quando viene rilevato un URL incorporato, il robot di ricerca cerca di associare l’URL al pattern di ciascuna regola di ricerca per indicizzazione. Se il pattern corrisponde, il motore di riscrittura cerca le direttive RewriteCond corrispondenti. Se non sono presenti condizioni, l’URL viene sostituito da un nuovo valore costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se le condizioni esistono, vengono elaborate nell’ordine in cui sono elencate. Il motore di riscrittura cerca di corrispondere a un pattern di condizione (CondPattern) rispetto a una stringa di test (TestString). Se le due corrispondenze, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l’URL viene sostituito con la sostituzione specificata nella regola. Se la condizione non viene soddisfatta, l&#39;insieme completo di condizioni e la regola corrispondente falliscono.

## Informazioni sulle direttive RewriteRule {#section_32B24B29627946398AFBC5F869A610CB}

Una direttiva RewriteRule ha la seguente forma:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` può essere un&#39;espressione regolare POSIX applicata all&#39;URL corrente. L’&quot;URL corrente&quot; può essere diverso dall’URL originale richiesto, perché le regole precedenti potrebbero aver già trovato corrispondenza e modificato l’URL.

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Non è possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per preimpostare il pattern. Il carattere &quot;not&quot; consente di negare un pattern, ovvero di essere true solo se l’URL corrente NON corrisponde a questo pattern. Il carattere &quot;not&quot; può essere utilizzato quando è meglio corrispondere a un pattern negativo o come regola predefinita finale.

>[!NOTE]
>
>Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato quando la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento di sfondo nel pattern, a cui possono fare riferimento i parametri Sostituzione e Modello di consenso.

**** SostituzioneL’URL viene sostituito dalla stringa di sostituzione che contiene quanto segue:

Testo normale: Testo passato attraverso invariato.

I riferimenti di sfondo consentono di accedere alle parti raggruppate (tra parentesi) della serie o della serie di cond. Di seguito sono riportati i due tipi di riferimenti retrovisori:

* **RewriteRule** BackreferencesQuesti corrispondono a riferimenti precedenti nel pattern RewriteRule corrispondente e si presentano come $N (0  &lt;> Ad esempio, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* ** Backreferences RewriteCond** Questi corrispondono a backreferences nell’ultimo pattern di cond RewriteCond corrispondente e prendono la forma %N (0 &lt;= N &lt;= N &lt;= 9).

Variabili: Si tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE è una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili di ambiente, consulta il flag *[E]* .

Funzioni: Si tratta delle funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è il seguente:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.
* l&#39;URL di escape codifica tutti i caratteri in *key*.
* I caratteri &quot;a&quot;.z, A..Z&#39;, &#39;0&#39;.9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati; gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel loro equivalente con codifica URL %xx.
* unescape trasforma &#39;+&#39; di nuovo in spazio e tutti i caratteri codificati con URL %xx in caratteri singoli.

>[!NOTE]
>
>Esiste una stringa di sostituzione speciale: &quot;-&quot; significa &quot;NO substitution&quot;. La stringa &quot;-&quot; viene spesso utilizzata con il flag C (chain), che consente di associare un URL a diversi pattern prima che si verifichi una sostituzione.

**Flag**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Ultima regola. </p> <p>Interrompe il processo di riscrittura e non applica alcuna regola di riscrittura aggiuntiva. Usa questo flag per impedire ulteriori elaborazioni dell’URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Prossimo turno. </p> <p> Ripete il processo di riscrittura (iniziando di nuovo con la prima regola di riscrittura) utilizzando l’URL dell’ultima regola di riscrittura (non l’URL originale). Fai attenzione a non creare un ciclo critico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Concatenato con la regola successiva. </p> <p>Sposta la regola corrente alla regola successiva (che può anche essere incatenata alla regola seguente e così via). Se una regola corrisponde, il processo di sostituzione continua come di consueto. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p> Rende il pattern privo di distinzione tra maiuscole e minuscole (ovvero, non esiste alcuna differenza tra "A-Z" e "a-z") quando il pattern viene confrontato con l’URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole di num successive nel set di regole. Usa questo flag per creare costrutti pseudo-then-else. L'ultima regola della clausola then diventa un salto=N dove N è il numero di regole nella clausola else. </p> <p> <p>Nota:  Questo flag non è lo stesso del flag 'chain|C'!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Imposta la variabile ambientale. </p> <p>Crea una variabile ambientale "VAR" impostata sul valore VAL, in cui VAL può contenere riferimenti retroversi di espressioni regolari, $N e %N, che vengono espansi. Puoi utilizzare questo flag più volte per impostare più variabili. Le variabili possono essere successivamente rimandate in un pattern RewriteCond seguente tramite %{VAR}. </p> <p>Usa questo flag per rimuovere e ricordare le informazioni dagli URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le regole di riscrittura dell&#39;archivio e le regole di riscrittura di recupero condividono i valori delle variabili. A causa di questo comportamento, è possibile impostare una variabile su un valore sessionid sensibile al tempo quando viene rilevato e memorizzato un URL incorporato. Quando l’URL successivo viene recuperato dall’elenco di archiviazione temporanea, è possibile aggiungere ad esso il valore sessionid più recente prima del recupero della pagina.

**Esempio di RewriteRule con una funzione**

Supponiamo di avere un server sensibile a maiuscole e minuscole che gestisce le stringhe &quot;www.mydomain.com&quot; e &quot;www.MyDomain.com&quot; in modo diverso. Affinché il server funzioni correttamente, assicurati che il dominio sia sempre &quot;www.mydomain.com&quot; anche se alcuni documenti contengono collegamenti che fanno riferimento a &quot;www.MyDomain.com&quot;. A questo scopo, puoi utilizzare la seguente regola:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

Questa regola di riscrittura utilizza la funzione `tolower` per riscrivere la porzione di dominio di un URL in modo che sia sempre minuscola come nei seguenti casi:

1. Il pattern `(^https://([^/]*)(.*)$)` contiene un riferimento di sfondo ** `([^/]*)`** che corrisponde a tutti i caratteri compresi tra `https://` e il primo `/` nell’URL. Il pattern contiene anche un secondo riferimento di sfondo `(.*)` che corrisponde a tutti i caratteri rimanenti nell’URL.
1. La sostituzione `(https://${tolower:$1}$2)` indica al motore di ricerca di riscrivere l&#39;URL utilizzando la funzione `tolower` sul primo riferimento di sfondo `(https:// ${tolower:$1}$2)` lasciando il resto dell&#39;URL inalterato `(https://${tolower:$1} $2)`.

Pertanto, un URL del modulo `https://www.MyDomain.com/INTRO/index.Html` viene riscritto come `https://www.mydomain.com/INTRO/index.Html`.

## Informazioni sulle direttive RewriteCond {#section_ADD642A24B68452CB98294A0BD687EC3}

La direttiva RewriteCond definisce una condizione di regola. Quando un RewriteCond precede un RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e se si applicano le condizioni aggiuntive. Le condizioni di riscrittura si presentano come segue:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` è una stringa che può contenere i seguenti costrutti:

Testo normale: Testo passato attraverso invariato.

I riferimenti di sfondo consentono di accedere alle parti raggruppate (tra parentesi) della serie o della serie di cond. Di seguito sono riportati i due tipi di riferimenti retrovisori:

* **RewriteRule** BackreferencesQuesti corrispondono a riferimenti precedenti nel pattern RewriteRule corrispondente e si presentano come $N (0  &lt;> Ad esempio, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`.

* **RewriteCond** BackreferencesQuesti corrispondono a backreferences nell’ultimo pattern di cond RewriteCond corrispondente e prendono il modulo %N (0&lt;>

Variabili: Si tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili, consulta il flag RewriteRule *`[E]`* .

Funzioni: Si tratta delle funzioni del modulo ${NAME_OF_FUNCTION:key} in cui NAME_OF_FUNCTION è il seguente:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.
* L’URL di escape codifica tutti i caratteri nella chiave . I caratteri &quot;a&quot;.z, A..Z&#39;, &#39;0&#39;.9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel loro equivalente con codifica URL %xx.
* unescape trasforma &#39;+&#39; di nuovo in spazio e tutti i caratteri di codifica URL %xx in caratteri singoli.

**** CondPatterns è un&#39;espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un &#39;!&#39; carattere (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, puoi utilizzare una delle seguenti varianti speciali:

>[!NOTE]
>
>È inoltre possibile preimpostare tutti i test con un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lessicamente meno. </p> <p> Tratta CondPattern come una stringa semplice e lo confronta lessicalmente con TestString. True se TestString è lessicalmente minore di CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Più grande lessicalmente. </p> <p> Tratta CondPattern come una stringa semplice e lo confronta lessicalmente con TestString. True se TestString è lessicalmente maggiore di CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexicamente uguale. </p> <p> Tratta CondPattern come una stringa semplice e lo confronta lessicalmente con TestString. True se TestString è lessicalmente uguale a CondPattern, ovvero se le due stringhe sono esattamente uguali (carattere per carattere). Se CondPattern è solo "" (due virgolette), questo confronta TestString con la stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag**
 (facoltativo) Racchiudono i flag tra parentesi  `[]`. I flag multipli sono separati da virgole.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Nessun caso. </p> <p>Questo flag fa sì che il test non faccia distinzione tra maiuscole e minuscole, ovvero non c'è differenza tra "A-Z" e "a-z" sia nel TestString espanso che nel CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>O la condizione successiva. </p> <p>Utilizza questo flag per combinare le condizioni della regola con un operatore OR locale anziché con l'operatore AND implicito. Senza questo flag, dovresti scrivere il cond/rule più volte. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

Alcune pagine web assegnano una variabile CGI &quot;sessionid&quot; la prima volta che un visitatore arriva a un sito. Questa variabile viene utilizzata per identificare il visitatore e, mentre il visitatore naviga nel sito, viene trasmessa la variabile . Poiché il robot di ricerca assomiglia a un visitatore del sito, gli viene assegnato un numero &quot;sessionid&quot;. Il robot di ricerca mantiene questo singolo valore &quot;sessionid&quot;, anche se una seconda pagina del sito cerca di assegnare un nuovo valore. Per questo motivo, sono necessarie due regole di riscrittura.

La prima regola viene utilizzata per identificare e memorizzare la variabile sessionid:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule utilizza un flag E `([E=sessionid:$1])` per assegnare il valore corrente del parametro sessionid CGI alla variabile `sessionid`. Il `$1` fa riferimento al primo riferimento di sfondo, contenuto tra il primo set di parentesi nel Pattern di RewriteRule `([^&#]+)`.

L’espressione regolare `^&#]+` corrisponde alla porzione di un URL compresa tra la parola `sessionid` e il carattere successivo**&amp;**o**#**. Poiché questa RewriteRule viene utilizzata solo per creare il valore iniziale per la variabile sessionid, non viene riscritta. Il campo Sostituzione della regola è impostato su `-` per indicare che non è richiesta alcuna riscrittura.

RewriteCond esamina la variabile `sessionid` ( `%{sessionid}`). Se non ha nemmeno un singolo carattere (!.+), quindi la RewriteRule corrisponde.

Utilizzando questa regola, l’URL viene letto come `https://www.domain.com/home/?sessionid=1234&function=start` e assegna il valore `1234` alla variabile `sessionid`.

La seconda regola viene utilizzata per riscrivere tutti gli URL che corrispondono al seguente pattern di RewriteRule:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

Il pattern RewriteRule contiene due riferimenti di sfondo: `(.+)` e `(.*)`. Il primo backreference corrisponde a tutti i caratteri precedenti a `sessionid`. Il secondo backreference corrisponde a tutti i caratteri dopo il termine `&` o `#`.

Il pattern di sostituzione riscrive l’URL utilizzando il primo riferimento di sfondo, seguito dalla stringa &quot;sessionid=&quot;, seguita dal valore della variabile ID di sessione definita dalla prima regola `%{sessionid}`, seguita dal secondo riferimento di sfondo. `($1sessionid=%{sessionid} $2)`

Tieni presente che questa regola di riscrittura non contiene un RewriteCond. Di conseguenza, causa una riscrittura per tutti gli URL che corrispondono alla regola di riscrittura *Pattern*. Pertanto, se il valore della variabile sessionid ( `%{sessionid}`) è `1234`, un URL del modulo `https://www.domain.com/products/?sessionid=5678&function=buy` viene riscritto come `https://www.domain.com/products/?sessionid=1234&function=buy`

## Conferma {#section_EC3A1DAEB5A54C93A265CB119DF91E9F}

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta di regole URL per il recupero degli elenchi di ricerca per indicizzazione {#task_94A28ED7DC404BFF9767DBB5ADEE6B7A}

È possibile aggiungere regole per recuperare gli URL dall’elenco di ricerca per indicizzazione per specificare in che modo gli URL incontrati all’interno del contenuto web vengono riscritti. Le regole di riscrittura di recupero sono necessarie solo se gli URL contengono dati dinamici, ad esempio un ID sessione, e se tali dati dinamici cambiano nel tempo per rimanere validi.

<!-- 

t_adding_crawl_list_retrieve_url_rules.xml

 -->

**Per aggiungere regole URL di recupero degli elenchi di ricerca per indicizzazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**.
1. Nel campo [!DNL Crawl List Retrieve URL Rules] , immetti le regole desiderate.

   Sono consentite righe vuote e di commento che iniziano con un carattere &#39;#&#39; (hash).
1. (Facoltativo) Nella pagina [!DNL Crawl List Retrieve URL Rules], nel campo [!DNL Test Crawl List Retrieve URL Rules], immetti un URL di test di cui desideri verificare le regole di ricerca per indicizzazione, quindi fai clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Crawl List Retrieve URL Rules] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle regole del titolo della ricerca per indicizzazione {#concept_BD3A576987DA4D93A998B0B9CDDC3C79}

Regole titolo ricerca per indicizzazione specificare il modo in cui i titoli rilevati all’interno del contenuto Web vengono riscritti prima che vengano memorizzati nell’indice di ricerca.

<!-- 

c_about_crawl_title_rules.xml

 -->

Ad esempio, puoi utilizzare una regola di riscrittura per rimuovere una parte del titolo, ad esempio un nome organizzazione. Durante la ricerca per indicizzazione di un sito web, i titoli rilevati vengono memorizzati in un buffer temporaneo. Tuttavia, prima che un titolo venga aggiunto al buffer, le regole del titolo vengono applicate a esso. Per impostazione predefinita, la ricerca/merchandising del sito non ha regole del titolo per ricerca per indicizzazione e non apporta modifiche al titolo.

Prima che gli effetti delle regole siano visibili ai clienti, ricostruisci l&#39;indice del sito.

È possibile ripristinare rapidamente tutte le modifiche apportate alle Regole titolo per ricerca per indicizzazione utilizzando la funzione Cronologia.

Le regole possono essere costituite da due elementi principali: RewriteRule e l&#39;opzione RewriteCond opzionale. È possibile specificare un numero illimitato di regole e condizioni. L&#39;ordine di queste regole è importante perché il set di regole viene ripetuto per regola. Quando una regola corrisponde, esegue il ciclo tra eventuali condizioni di riscrittura (facoltative) corrispondenti. Le regole dell’URL di ricerca per indicizzazione sono specificate nel modo seguente:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

Quando viene rilevato un titolo, il robot di ricerca cerca cerca di associare il titolo al Pattern di ogni regola di ricerca per indicizzazione. Se il pattern corrisponde, il motore di riscrittura cerca le direttive RewriteCond corrispondenti. Se non sono presenti condizioni, l’URL viene sostituito da un nuovo valore costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se le condizioni esistono, vengono elaborate nell’ordine in cui sono elencate. Il motore di riscrittura cerca di corrispondere a un pattern di condizione (CondPattern) rispetto a una stringa di test (TestString). Se le due corrispondenze, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l’URL viene sostituito con la sostituzione specificata nella regola. Se la condizione non viene soddisfatta, l&#39;insieme completo di condizioni e la regola corrispondente falliscono.

Immetti le Regole URL di ricerca per indicizzazione nella casella di testo, quindi fai clic su Salva modifiche. Sono consentite righe vuote e di commento che iniziano con un carattere &#39;#&#39; (hash). Per testare le regole di ricerca, è possibile inserire un URL di test nella casella di testo &quot;Verifica regole di riscrittura&quot;, quindi fare clic su Prova.

## Direttiva RewriteRule {#section_669445C505754E838E14029D6583D9B6}

Ogni direttiva RewriteRule definisce una regola di riscrittura. Le regole vengono applicate nell’ordine in cui sono elencate. Una regola di riscrittura assume la forma seguente:

```
RewriteRule Pattern Substitution [Flags]
```

**** Pattern può essere un’espressione regolare POSIX applicata al titolo corrente. Il &quot;titolo corrente&quot; è diverso dal titolo originale, in quanto le regole precedenti lo hanno già abbinato e modificato.

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

È possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per preimpostare il pattern. Il carattere &quot;not&quot; consente di negare un pattern, ovvero di essere true solo se il titolo corrente NON corrisponde al pattern. Il carattere &quot;not&quot; può essere utilizzato quando è meglio corrispondere a un pattern negativo o come regola predefinita finale. Nota: Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato quando la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento di sfondo, a cui possono fare riferimento i parametri Sostituzione e Modello di consenso.

**** SostituzioneIl titolo viene sostituito dalla stringa di sostituzione. La stringa può contenere quanto segue:

Testo normale : testo trasmesso senza modifiche.

I riferimenti di sfondo consentono di accedere alle parti raggruppate (tra parentesi) della serie o della serie di cond. Di seguito sono riportati due tipi di riferimenti di sfondo:

* Backreferences RewriteRule

   Questi corrispondono ai riferimenti precedenti nel pattern RewriteRule corrispondente e si presentano come $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* Backreferences RewriteCond

   Questi corrispondono ai riferimenti precedenti nell&#39;ultimo pattern di cond RewriteCond corrispondente e prendono il formato %N (0 &lt;= N &lt;= 9).

Variabili Si tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili di ambiente, consulta il flag `[E]` .

Funzioni Queste sono funzioni del modulo ${NAME_OF_FUNCTION: key} dove NAME_OF_FUNCTION è:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.

>[!NOTE]
>
>Esiste una stringa di sostituzione speciale: &quot;-&quot; significa &quot;NO substitution&quot;. La stringa &quot;-&quot; è spesso utile con il flag C (chain), che consente di associare un titolo a diversi pattern prima che si verifichi una sostituzione.

**Flag**  (facoltativo)

I flag sono racchiusi tra parentesi `[]`e più flag sono separati da virgole:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Ultima regola. </p> <p> Interrompe il processo di riscrittura e non applica alcuna regola di riscrittura aggiuntiva. Usa questo flag per evitare ulteriori elaborazioni del titolo corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Prossimo turno. </p> <p> Ripete il processo di riscrittura (iniziando di nuovo con la prima regola di riscrittura) utilizzando il titolo dell’ultima regola di riscrittura, non il titolo originale. Fai attenzione a non creare un ciclo morto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Concatenato con la regola successiva. </p> <p>Sposta la regola corrente alla regola successiva (che può anche essere incatenata alla regola seguente e così via). Se una regola corrisponde, il processo di sostituzione continua come di consueto. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p>Rende il pattern privo di distinzione tra maiuscole e minuscole (ovvero, non esiste alcuna differenza tra "A-Z" e "a-z") quando il pattern viene confrontato con il titolo corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole di num successive nel set di regole. Utilizza questo per creare costrutti pseudo-then-else. L'ultima regola della clausola then diventa un salto=N dove N è il numero di regole nella clausola else. (Nota: Questo non è lo stesso del flag 'chain|C'!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Imposta la variabile di ambiente. </p> <p> Crea una variabile ambientale "VAR" impostata sul valore VAL, in cui VAL può contenere riferimenti retroversi di espressioni regolari, $N e %N, che viene espanso. Puoi utilizzare questo flag più volte per impostare più variabili. In seguito è possibile fare riferimento alle variabili in un pattern RewriteCond seguente tramite %{VAR}. Usa questo flag per eliminare e ricordare le informazioni dai titoli. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Direttiva RewriteCond (facoltativo) {#section_D664B71DE3884E0790531804C49A3222}

La direttiva RewriteCond definisce una condizione di regola. Quando un RewriteCond precede un RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e se si applicano le condizioni aggiuntive.

Le direttive sulla condizione di riscrittura hanno la seguente forma:

```
RewriteCond TestString CondPattern [Flags] 
```

**** TestStringè una stringa che può contenere i seguenti costrutti:

Testo normale : testo trasmesso senza modifiche.

I riferimenti di sfondo consentono di accedere alle parti raggruppate (tra parentesi) della serie o della serie di cond. Esistono due tipi di riferimenti retrospettivi:

* RewriteRule Backreferences Questi corrispondono a backreferences nel pattern RewriteRule corrispondente e prendono il formato $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond Backreferences Questi backreferences corrispondono all’ultimo pattern di cond RewriteCond corrispondente e prendono la forma %N (0 &lt;= N &lt;= N &lt;= 9).

Variabili Si tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili di ambiente, consulta il flag `[E]` .

Funzioni Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} dove NAME_OF_FUNCTION è:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.
* L’URL di escape codifica tutti i caratteri nella chiave .
* I caratteri &quot;a&quot;.z, A..Z&#39;, &#39;0&#39;.9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel loro equivalente con codifica URL %xx.
* unescape trasforma &#39;+&#39; di nuovo in spazio e tutti i caratteri codificati con URL %xx in caratteri singoli.

**** CondPatterns è un&#39;espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un &#39;!&#39; carattere (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, puoi utilizzare una delle seguenti varianti speciali.

>[!NOTE]
>
>È possibile assegnare un prefisso a tutti i test con un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente minore. </p> <p>Tratta il <i>CondPattern</i> come stringa normale e lo confronta lessicalmente con <i>TestString</i>. True se <i>TestString</i> è lessicalmente minore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente maggiore. </p> <p>Tratta il <i>CondPattern</i> come stringa normale e lo confronta lessicalmente con <i>TestString</i>. True se <i>TestString</i> è lessicalmente maggiore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p> È lessicamente uguale. </p> <p>Tratta il <i>CondPattern</i> come stringa normale e lo confronta lessicalmente con <i>TestString</i>. True se <i>TestString</i> è lessicalmente uguale a <i>CondPattern</i>, ovvero, le due stringhe sono esattamente uguali (carattere per carattere). Se <i>CondPattern</i> è solo "" (due virgolette), questo confronta <i>TestString</i> alla stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag**  (facoltativo)

I flag sono racchiusi tra parentesi `[]`e più flag sono separati da virgole:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p> Rende il test non sensibile. In altre parole, non c'è differenza tra "A-Z" e "a-z" sia nella <i>TestString</i> espansa sia nel <i>CondPattern.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p> O la condizione successiva. </p> <p>Utilizza questo flag per combinare le condizioni della regola con un operatore OR locale anziché con l'operatore AND implicito. Senza questo flag, dovresti scrivere il cond/rule più volte. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

Supponiamo di avere un sito Web aziendale con un formato titolo standard: &quot;La mia azienda&quot; seguita da un trattino e quindi da una descrizione specifica della pagina ( ad esempio &quot;La mia azienda - Benvenuto&quot; o &quot;La mia azienda - Notizie&quot;). Vuoi togliere &quot;La mia azienda -&quot; dal titolo e convertire l&#39;intero titolo in lettere maiuscole quando indicizza il sito.

La regola di riscrittura seguente utilizza il contagocce della funzione per riscrivere solo la parte descrittiva di un titolo in maiuscolo:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>}
```

Il Pattern della regola `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` contiene un riferimento di sfondo `(.*)` che corrisponde al contenuto del titolo che segue &quot;La mia azienda-&quot;. Tenere presente che l&#39;area circostante una parte di un pattern con parentesi ( ) crea un riferimento di sfondo a cui può fare riferimento la Sostituzione. In questo esempio, la sostituzione (${toupper:**$1**}) riscrive il riferimento di backreference (**$1**) utilizzando la funzione di contagocce.

Così, un titolo del modulo &quot;La mia azienda - Benvenuto&quot; è riscritto come &quot;BENVENUTO&quot;.

**Riconoscimento**

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta di regole per il titolo della ricerca per indicizzazione {#task_272BB4C603BA4C9ABDBEEB398798B101}

È possibile aggiungere regole per il titolo della ricerca per indicizzazione per specificare come i titoli rilevati all’interno del contenuto web vengono riscritti prima che vengano memorizzati nell’indice di ricerca.

<!-- 

t_adding_crawl_title_rules.xml

 -->

**Per aggiungere regole del titolo di ricerca per indicizzazione**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl Title Rules]**.
1. Nel campo [!DNL Crawl Title Rules] , immetti le regole desiderate.

   Sono consentite righe vuote e di commento che iniziano con un carattere &#39;#&#39; (hash).
1. (Facoltativo) Nella pagina [!DNL Crawl Title Rules], nel campo [!DNL Test Crawl Title Rules], immetti un URL di test di cui desideri verificare le regole di ricerca, quindi fai clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Crawl Title Rules] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle regole URL di ricerca {#concept_017EC95E68844B6C8CC9F874F0EC8D3C}

Regole URL di ricerca specifica come devono essere visualizzati gli URL nei risultati di ricerca del sito web. Le regole operano sugli URL completi. È possibile manipolare qualsiasi parte dell’URL, inclusi gli argomenti di query in cui le informazioni ID sessione vengono spesso mantenute.

<!-- 

c_about_search_url_rules.xml

 -->

In genere, le regole dell’URL di ricerca vengono utilizzate per inserire un ID sessione in un URL. Tuttavia, puoi anche utilizzare le regole dell’URL di ricerca per modificare il nome di dominio visualizzato con i risultati. Per impostazione predefinita, non viene specificata alcuna regola e non viene eseguita alcuna modifica all’URL.

Le regole dell’URL di ricerca possono essere costituite da due elementi principali: RewriteRule e l&#39;opzione RewriteCond opzionale. Quando un URL viene incluso come parte di un risultato di ricerca, le regole vengono utilizzate per manipolarlo. Puoi specificare un numero illimitato di regole e condizioni dell’URL di ricerca. L&#39;ordine di queste regole è importante perché il set di regole viene ripetuto per ogni regola. Quando una regola corrisponde, il software esegue il ciclo tra eventuali condizioni di riscrittura (facoltative) corrispondenti. Le regole dell’URL di ricerca per indicizzazione sono specificate nel modo seguente:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

Quando si elabora un URL, la ricerca/merchandising del sito cerca di farlo corrispondere al pattern di ogni regola di ricerca. Se la corrispondenza non riesce, il motore di riscrittura smette immediatamente di elaborare la regola e continua con la regola successiva nel set. Se il pattern corrisponde, il motore di riscrittura cerca le istruzioni RewriteCond corrispondenti. Se non esistono condizioni, l’URL viene sostituito da un nuovo valore. Questo valore viene costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se le condizioni esistono, l’ordine in cui sono elencate è il modo in cui vengono elaborate. Il motore di riscrittura cerca di corrispondere a un pattern di condizione (CondPattern) rispetto a una stringa di test (TestString). Se le due corrispondenze, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l’URL viene sostituito con la sostituzione specificata nella regola. Se la condizione non viene soddisfatta, l&#39;insieme completo di condizioni e la regola corrispondente falliscono.

## Informazioni sulla direttiva RewriteRule {#section_A3473B5B90B74DA1970213113A90591E}

Una regola di riscrittura assume la forma seguente:

```
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

**** Pattern può essere un’espressione regolare POSIX che viene applicata all’URL corrente. L’&quot;URL corrente&quot; può essere diverso dall’URL originale, perché le regole precedenti potrebbero averlo già corrispondente e modificato.

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

È possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per preimpostare il pattern. Il carattere &quot;not&quot; consente di negare un pattern. In altre parole, è vero solo se l’URL corrente NON corrisponde al pattern. È possibile utilizzare il carattere &quot;not&quot; quando è meglio corrispondere a un pattern negativo o come regola predefinita finale. Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato quando la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento di sfondo, a cui possono fare riferimento i parametri Sostituzione e Modello di consenso.

**** SostituzioneL’URL viene completamente sostituito dalla stringa di sostituzione, che può contenere quanto segue:

Testo normale : testo trasmesso inalterato.

Backreferences Consente di accedere alle parti raggruppate (tra parentesi) della serie o della serie di condPattern. Esistono due tipi di riferimenti retrospettivi:

RewriteRule Backreferences Questi corrispondono a backreferences nel pattern RewriteRule corrispondente e prendono il formato $N (0 &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

RewriteCond Backreferences - Questi corrispondono a backreferences nell’ultimo pattern di cond RewriteCond corrispondente e prendono la forma %N (0 &lt;= N &lt;= N &lt;= 9).

Funzioni: Si tratta delle funzioni del modulo ${NAME_OF_FUNCTION:key} in cui è presente NAME_OF_FUNCTION:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.
* l&#39;URL di escape codifica tutti i caratteri in *key*.
* I caratteri &quot;a&quot;.z, A..Z&#39;, &#39;0&#39;.9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati; gli spazi sono tradotti in &quot;+&quot;; tutti gli altri caratteri vengono trasformati nel loro equivalente con codifica URL %xx.
* unescape trasforma &#39;+&#39; di nuovo in spazio e tutti i caratteri codificati con URL %xx in caratteri singoli.

>[!NOTE]
>
>Esiste una stringa di sostituzione speciale: &quot;-&quot; significa &quot;NO substitution&quot;. La stringa &quot;-&quot; è spesso utile insieme al flag C (chain). Ti consente di associare un URL a diversi pattern prima che si verifichi una sostituzione.

**Flag**  (facoltativo)

I flag sono racchiusi tra parentesi `[]`e più flag sono separati da virgole:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Ultima regola. </p> <p> Interrompi il processo di riscrittura e non applicare ulteriori regole di riscrittura. Usa questo flag per impedire ulteriori elaborazioni dell’URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p> Prossimo turno. </p> <p>Esegui nuovamente il processo di riscrittura (iniziando di nuovo con la prima regola di riscrittura) utilizzando l’URL dell’ultima regola di riscrittura (non l’URL originale). Fai attenzione a non creare un loop morto! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p> Concatenato con la regola successiva. </p> <p>Questo flag catena la regola corrente alla regola successiva, che può anche essere incatenata alla regola seguente, e così via. Se una regola corrisponde, il processo di sostituzione continua come di consueto. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Nessun caso. </p> <p>Questo flag rende il pattern senza distinzione tra maiuscole e minuscole. In altre parole, non c'è differenza tra "A-Z" e "a-z" quando il pattern viene confrontato con l'URL corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole di num successive nel set di regole. Utilizza questo per creare costrutti pseudo-then-else. L'ultima regola della clausola then diventa un salto=N dove N è il numero di regole nella clausola else. (Nota: Questo non è lo stesso del flag 'chain|C'!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Imposta la variabile ambientale. </p> <p> Questo flag crea una variabile ambientale "VAR" impostata sul valore VAL. Il valore VAL può contenere riferimenti di sfondo di espressioni regolari, $N e %N, espansi. Puoi utilizzare questo flag più volte per impostare più variabili. Le variabili possono essere successivamente rimandate in un pattern RewriteCond seguente tramite %{VAR}. Usa questo flag per rimuovere e ricordare le informazioni dagli URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

Le regole di riscrittura store e le regole di riscrittura Retrieve condividono i valori delle variabili. Per questo motivo, puoi impostare una variabile su un valore sessionid sensibile al tempo quando viene rilevato e memorizzato un URL incorporato. Quando l’URL successivo viene recuperato dall’elenco di archiviazione temporanea, è possibile aggiungere ad esso il valore sessionid più recente prima del recupero della pagina.

**Esempio**

Supponiamo di avere un server sensibile a maiuscole e minuscole. Gestisce le stringhe &quot;www.mydomain.com&quot; e &quot;www.MyDomain.com&quot; in modo diverso. Affinché il server funzioni correttamente, è necessario assicurarsi che il dominio sia sempre &quot;www.mydomain.com&quot; anche se alcuni documenti contengono collegamenti che fanno riferimento a &quot;www.MyDomain.com&quot;. A questo scopo, puoi utilizzare la seguente regola:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2 
```

Questa regola di riscrittura utilizza la funzione &quot;tolower&quot; per riscrivere la porzione di dominio di un URL per assicurarti che sia sempre minuscola:

1. Il pattern `(^https://([^/]*)(.*)$)` contiene un riferimento di sfondo **`([^/]*)`** che corrisponde a tutti i caratteri compresi tra &quot;https://&quot; e il primo &quot;/&quot; nell’URL. Il pattern contiene anche un secondo riferimento di sfondo **(.*)** che corrisponde a tutti i caratteri rimanenti nell&#39;URL.

1. La sostituzione `(https://${tolower:$1}$2)` indica al motore di ricerca di riscrivere l&#39;URL utilizzando la funzione **tolower** sul primo riferimento di sfondo `(https://**${tolower:$1**}$2)` lasciando intatto il resto dell&#39;URL `(https://${tolower:$1}*$2*)`.

Pertanto, un URL del modulo `https://www.MyDomain.com/INTRO/index.Html` viene riscritto come `https://www.mydomain.com/INTRO/index.Html`

**Direttiva**  RewriteCond (facoltativo)

La direttiva RewriteCond definisce una condizione di regola. Quando un RewriteCond precede un RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e se si applicano le condizioni aggiuntive.

Le direttive sulla condizione di riscrittura hanno la seguente forma:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i>
```

** TestStringè una stringa che può contenere i costrutti seguenti:

Testo normale: Testo passato attraverso invariato.

I riferimenti di sfondo consentono di accedere alle parti raggruppate (tra parentesi) della serie o della serie di cond. Esistono due tipi di riferimenti retrospettivi:

* ** RewriteRule Backreferences** Questi corrispondono a backreferences nel pattern RewriteRule corrispondente e prendono il modulo $N (0 &lt;= N &lt;= N &lt;= 9). Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond** BackreferencesQuesti corrispondono a backreferences nell’ultimo pattern di cond RewriteCond corrispondente e prendono il modulo %N (0  &lt;>

Variabili Si tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili, consulta il flag RewriteRule *`[E]`* .

>[!NOTE]
>
>Le regole di riscrittura generalmente utilizzano le variabili. Tutti i parametri CGI dall’URL corrente vengono automaticamente trasformati in variabili. Ad esempio, l’URL di ricerca `"https://search.atomz.com/search/?sp_a=sp00000000&sp_q="Product"&session=1234&id=5678"` fornirà automaticamente quattro variabili, alle quali è possibile fare riferimento nelle regole di riscrittura. In questo esempio, una variabile è chiamata &quot;session&quot; e il suo valore è &quot;1234&quot;, mentre un&#39;altra variabile è chiamata &quot;id&quot; e il suo valore è &quot;5678&quot;. (Le altre due variabili sono `sp_a` e `sp_q`.) È necessario passare tutte le variabili necessarie come campi nascosti dal modulo di ricerca sulla pagina Web. In questo esempio, è necessario trasmettere i valori &quot;session&quot; e &quot;id&quot;, che identificano l&#39;utente del sito Web che esegue la ricerca. Per passare un campo nascosto al modulo di ricerca, utilizza un tag come `<input type=hidden name="session" value="1234">`.

Funzioni Queste sono funzioni del modulo ${NAME_OF_FUNCTION:key} dove NAME_OF_FUNCTION è:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.
* l&#39;URL di escape codifica tutti i caratteri in *key*. I caratteri &quot;a&quot;.z, A..Z&#39;, &#39;0&#39;.9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel loro equivalente con codifica URL %xx.
* unescape trasforma &#39;+&#39; di nuovo in spazio e tutti i caratteri di codifica URL %xx in caratteri singoli.

**** CondPatterns è un&#39;espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un &#39;!&#39; carattere (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, puoi utilizzare una delle seguenti varianti speciali.

È possibile usare il prefisso di tutti i test utilizzando un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente minore. </p> <p> Tratta il <i>CondPattern</i> come stringa normale e lo confronta lessicalmente con <i>TestString</i>. True se <i>TestString</i> è lessicalmente minore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente maggiore. </p> <p> Tratta il <i>CondPattern</i> come stringa normale e lo confronta lessicalmente con <i>TestString</i>. True se <i>TestString</i> è lessicalmente maggiore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente uguale. </p> <p> Tratta il <i>CondPattern</i> come stringa normale e lo confronta lessicalmente con <i>TestString</i>. True se <i>TestString</i> è lessicalmente uguale a <i>CondPattern</i>. In altre parole, le due stringhe sono esattamente uguali (carattere per carattere). Se <i>CondPattern</i> è solo "" (due virgolette), questo confronta <i>TestString</i> alla stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag**  (facoltativo)

I flag sono racchiusi tra parentesi `[]`e più flag sono separati da virgole:

&#39;nocase|NC&#39; (nessun caso): In questo modo il test non distingue tra maiuscole e minuscole. In altre parole, non c&#39;è differenza tra &quot;A-Z&quot; e &quot;a-z&quot; sia nella *TestString* espansa sia nella *CondPattern*.

&#39;ornext|OR&#39; (o condizione successiva): Utilizza questa opzione per combinare le condizioni delle regole con un operatore OR locale anziché l&#39;operatore AND implicito. Senza questo flag, dovresti scrivere più volte il cond/rule.

**Esempio**

Alcune pagine web assegnano una variabile CGI &quot;sessionid&quot; la prima volta che un cliente arriva a un sito. Questa variabile viene utilizzata per identificare il cliente e, quando il cliente naviga nel sito, viene trasmessa la variabile . Poiché il robot di ricerca assomiglia a un cliente al tuo sito, gli viene assegnato un numero &quot;sessionid&quot;. Il robot di ricerca mantiene questo singolo valore &quot;sessionid&quot;, anche se una seconda pagina del sito cerca di assegnare un nuovo valore. A questo scopo, è necessaria la seguente regola di riscrittura:

```
RewriteCond  %{sessionid}  .+ 
RewriteRule  ^ 
<b>(.+)</b>sessionid=[^&#]+ 
<i>(.*)</i>$   
<b>$1</b>sessionid=%{sessionid} 
<i>$2</i>
```

Il pattern RewriteRule contiene due riferimenti di sfondo: (.+) e (.*). Il primo backreference corrisponde a tutti i caratteri prima di &quot;sessionid=&quot;. Il secondo backreference corrisponde a tutti i caratteri dopo la terminazione &#39;&amp;&#39; o &#39;#&#39; dell&#39;sessionid.

Il pattern Sostituzione riscrive l’URL utilizzando il primo riferimento a ritroso, seguito dalla stringa &quot;sessionid=&quot;, seguita dal valore della variabile ID sessione, che è stata passata come parametro CGI nell’URL, seguita dal secondo riferimento a ritroso. `($1sessionid=%{sessionid}$2)`.

Il **RewriteCond** esamina la variabile sessionid `(%{sessionid})`. Se contiene almeno un carattere (.+), quindi la RewriteRule corrisponde.

Pertanto, se la query di ricerca è `"https://search.atomz.com/search/?sp_a=sp99999999&sp_q=word&sessionid=5678"`, tutti gli URL dei risultati della ricerca verranno riscritti in modo che il valore &quot;sessionid&quot; sia &quot;5678&quot; invece del valore &quot;sessionid&quot; rilevato dal robot di ricerca durante la ricerca per indicizzazione del sito e il salvataggio dei collegamenti.

**Riconoscimento**

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta di regole URL di ricerca {#task_50C77D1B53804AEEB20896F74265BD6F}

Puoi aggiungere regole per l’URL di ricerca per specificare come vengono visualizzati gli URL nei risultati di ricerca del sito web. Le regole operano sugli URL completi. Puoi manipolare qualsiasi parte dell’URL, inclusi gli argomenti di query in cui le informazioni ID sessione vengono spesso mantenute.

<!-- 

t_adding_search_url_rules.xml

 -->

**Per aggiungere regole URL di ricerca**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search URL Rules]**.
1. Nel campo [!DNL Search URL Rules] , immetti le regole desiderate.

   Sono consentite righe vuote e di commento che iniziano con un carattere &#39;#&#39; (hash).
1. (Facoltativo) Nella pagina [!DNL Search URL Rules], nel campo [!DNL Test Search URL Rules], immetti un URL di test di cui desideri verificare le regole di ricerca per indicizzazione, quindi fai clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Search URL Rules] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informazioni sulle regole del titolo di ricerca {#concept_C72D20F8DFF64EDE809AF4B72797E858}

Regole titolo ricerca specifica come vengono visualizzati i titoli nei risultati della ricerca nel sito Web. È possibile manipolare qualsiasi parte del titolo.

<!-- 

c_about_search_title_rules.xml

 -->

Una regola di riscrittura può essere utilizzata per rimuovere una parte di un titolo, ad esempio un nome organizzazione. Per impostazione predefinita, la funzione di ricerca/merchandising del sito non dispone di regole di titolo e non apporta modifiche al titolo.

Le regole del titolo possono essere costituite da due elementi principali: RewriteRule e RewriteCond facoltativi. È possibile specificare un numero illimitato di regole e condizioni. L&#39;ordine di queste regole è importante, perché il set di regole viene ripetuto per regola. Quando una regola corrisponde, il software esegue il ciclo tra eventuali condizioni di riscrittura (facoltative) corrispondenti. Le regole del titolo di ricerca sono specificate nel modo seguente:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

Quando viene rilevato un titolo, la ricerca/merchandising del sito tenta di farlo corrispondere al pattern di ogni regola di ricerca per indicizzazione. Se il pattern corrisponde, il motore di riscrittura cerca le direttive RewriteCond corrispondenti. Se non sono presenti condizioni, il titolo viene sostituito da un nuovo valore costruito dalla stringa Sostituzione e continua con la regola successiva nel set di regole. Se le condizioni esistono, vengono elaborate nell’ordine in cui sono elencate. Il motore di riscrittura cerca di corrispondere a un pattern di condizione (CondPattern) rispetto a una stringa di test (TestString). Se le due corrispondenze, la condizione successiva viene elaborata finché non sono disponibili ulteriori condizioni. Se tutte le condizioni corrispondono, l’URL viene sostituito con la sostituzione specificata nella regola. Se la condizione non viene soddisfatta, l&#39;insieme completo di condizioni e la regola corrispondente falliscono.

## Direttiva RewriteRule {#section_3BF2B0FF89F74A26AE79D68FA3184B9B}

Ogni direttiva RewriteRule definisce una regola di riscrittura. Le regole vengono applicate nell’ordine in cui sono elencate. Una regola di riscrittura assume la forma seguente:

```
RewriteRule Pattern Substitution [Flags]
```

**** PatternUn’espressione regolare POSIX che viene applicata al titolo corrente. Il &quot;titolo corrente&quot; può essere diverso dal titolo originale, perché le regole precedenti potrebbero averlo già trovato e modificato.

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

È possibile utilizzare il carattere &quot;not&quot; (&#39;!&#39;) per preimpostare il pattern. Il carattere &quot;not&quot; consente di negare un pattern. Cioè, essere vero solo se il titolo corrente NON corrisponde al pattern. Il carattere &quot;not&quot; può essere utilizzato quando è meglio corrispondere a un pattern negativo o come regola predefinita finale. Nota: Non è possibile utilizzare sia il carattere &quot;not&quot; che i caratteri jolly raggruppati in un pattern. Inoltre, non è possibile utilizzare un pattern negato quando la stringa di sostituzione contiene $N.

È possibile utilizzare le parentesi per creare un riferimento di sfondo, a cui possono fare riferimento i parametri Sostituzione e CondPattern.

**** SostituzioneIl titolo viene completamente sostituito dalla stringa di sostituzione, che può contenere quanto segue:

Testo normale : testo trasmesso senza modifiche.

**** BackreferencesFornisci l’accesso alle parti raggruppate (tra parentesi) del pattern o del pattern di consenso. Di seguito sono riportati due tipi di riferimenti di sfondo:

* **RewriteRule** BackreferencesQuesti corrispondono a riferimenti precedenti nel pattern RewriteRule corrispondente e si presentano come $N (0  &lt;> Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* ** Backreferences RewriteCond** Questi corrispondono a backreferences nell’ultimo pattern di cond RewriteCond corrispondente e prendono la forma %N (0 &lt;= N &lt;= N &lt;= 9).

**** VariabiliSi tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili di ambiente, consulta il flag [E] . È inoltre possibile definire le variabili nel modulo di ricerca che ha generato i risultati della ricerca.

**** FunzioniQueste sono funzioni del modulo ${NAME_OF_FUNCTION: key} dove NAME_OF_FUNCTION è:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.

Esiste una stringa di sostituzione speciale: &quot;-&quot; significa &quot;NO substitution&quot;. La stringa &quot;-&quot; è spesso utile insieme al flag C (chain), che consente di associare un titolo a diversi pattern prima che si verifichi una sostituzione.

**Flag**  (facoltativo)

I flag sono racchiusi tra parentesi `[]` e più flag sono separati da virgole:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p> Ultima regola. </p> <p> Interrompi il processo di riscrittura e non applicare ulteriori regole di riscrittura. Usa questo flag per evitare ulteriori elaborazioni del titolo corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Prossimo turno. </p> <p> Esegui nuovamente il processo di riscrittura (iniziando nuovamente con la prima regola di riscrittura) utilizzando il titolo dell’ultima regola di riscrittura (non il titolo originale!). Fai attenzione a non creare un ciclo morto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Concatenato con la regola successiva. </p> <p> Questo flag catena la regola corrente alla regola successiva (che può anche essere incatenata alla regola seguente e così via). Se una regola corrisponde, il processo di sostituzione continua come di consueto. Se la regola non corrisponde, tutte le regole concatenate successive vengono ignorate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Nessun caso. </p> <p> Questo flag rende il pattern senza distinzione tra maiuscole e minuscole. In altre parole, non vi è alcuna differenza tra "A-Z" e "a-z" quando il pattern viene confrontato con il titolo corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p> Ignora la regola o le regole successive. </p> <p> Se la regola corrente corrisponde, questo flag forza il motore di riscrittura a saltare le regole di num successive nel set di regole. Utilizza questo per creare costrutti pseudo-then-else. L'ultima regola della clausola then diventa un salto=N dove N è il numero di regole nella clausola else. (Non è lo stesso del flag 'chain|C'!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Imposta la variabile di ambiente. </p> <p> Questo flag crea una variabile ambientale "VAR" impostata sul valore VAL, in cui VAL può contenere riferimenti di sfondo di espressioni regolari, $N e %N, che verranno espansi. Puoi utilizzare questo flag più volte per impostare più variabili. In seguito è possibile fare riferimento alle variabili in un pattern RewriteCond seguente tramite %{VAR}. Usa questo flag per eliminare e ricordare le informazioni dai titoli. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Direttiva RewriteCond (facoltativo) {#section_9D72B2AB454849A7B681BC39C506AAA3}

La direttiva RewriteCond definisce una condizione di regola. Quando un RewriteCond precede un RewriteRule, la regola viene utilizzata solo se il relativo pattern corrisponde al titolo corrente e se si applicano le condizioni aggiuntive.

Le direttive sulla condizione di riscrittura hanno la seguente forma:

```
RewriteCond TestString CondPattern [Flags]
```

**** TestStringè una stringa che può contenere i seguenti costrutti:

Testo normale : testo trasmesso senza modifiche.

I riferimenti di sfondo consentono di accedere alle parti raggruppate (tra parentesi) della serie o della serie di cond. Esistono due tipi di riferimenti retrospettivi:

* **RewriteRule** BackreferencesQuesti corrispondono a riferimenti precedenti nel pattern RewriteRule corrispondente e si presentano come $N (0  &lt;> Ad esempio, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond** BackreferencesQuesti corrispondono a backreferences nell’ultimo pattern di cond RewriteCond corrispondente e prendono il modulo %N (0  &lt;>

**** VariabiliSi tratta di variabili del modulo %{NAME_OF_VARIABLE} in cui NAME_OF_VARIABLE può essere una stringa per il nome di una variabile definita. Per ulteriori informazioni sull’impostazione delle variabili di ambiente, consulta il flag `[E]` . È inoltre possibile definire le variabili nel modulo di ricerca che ha generato i risultati della ricerca.

**** FunctionsQueste sono funzioni del modulo ${NAME_OF_FUNCTION:key} in cui è denominato NAME_OF_FUNCTION:

* tolower imposta tutti i caratteri in caratteri minuscoli in *key*.
* il contagocce rende maiuscoli tutti i caratteri in *key*.
* l&#39;URL di escape codifica tutti i caratteri in *key*.
* I caratteri &quot;a&quot;.z, A..Z&#39;, &#39;0&#39;.9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; e &#39;_&#39; rimangono invariati, gli spazi sono convertiti in &#39;+&#39; e tutti gli altri caratteri vengono trasformati nel loro equivalente con codifica URL %xx.
* unescape trasforma &#39;+&#39; di nuovo in spazio e tutti i caratteri codificati con URL %xx in caratteri singoli.

Esiste una stringa di sostituzione speciale: &quot;-&quot; significa &quot;NO substitution&quot;. La stringa &quot;-&quot; è spesso utile insieme al flag C (chain), che consente di associare un URL a diversi pattern prima che si verifichi una sostituzione.

**** CondPatternUn’espressione regolare estesa standard con alcune aggiunte. La stringa del pattern può essere preceduta da un &#39;!&#39; carattere (punto esclamativo) per specificare un pattern non corrispondente. Invece delle stringhe di espressione regolare reale, puoi utilizzare una delle seguenti varianti speciali.

Tutte queste prove possono essere precedute da un punto esclamativo (&#39;!&#39;) per negare il loro significato.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa CondPattern </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente minore. </p> <p> Tratta il <i>CondPattern</i> come stringa normale e lo confronta lessicalmente con <i>TestString</i>. True se <i>TestString</i> è lessicalmente minore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p> È lessicamente maggiore. </p> <p> Tratta il <i>CondPattern</i> come stringa normale e lo confronta lessicalmente con <i>TestString</i>. True se <i>TestString</i> è lessicalmente maggiore di <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>È lessicamente uguale. </p> <p> Tratta il <i>CondPattern</i> come stringa normale e lo confronta lessicalmente con <i>TestString</i>. True se <i>TestString</i> è lessicalmente uguale a <i>CondPattern</i>. In altre parole, le due stringhe sono esattamente uguali (carattere per carattere). Se <i>CondPattern</i> è solo "" (due virgolette), questo confronta <i>TestString</i> alla stringa vuota. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flag**  (facoltativo)

I flag sono racchiusi tra parentesi`[]` e più flag sono separati da virgole:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' (nessun caso) </p> </td> 
   <td colname="col2"> <p>Rende il test non sensibile. In altre parole, non c'è differenza tra "A-Z" e "a-z" sia nella <i>TestString</i> espansa sia nella <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' (o condizione successiva) </p> </td> 
   <td colname="col2"> <p> Utilizza questa opzione per combinare le condizioni delle regole con un operatore OR locale anziché l'operatore AND implicito. Senza questo flag, dovresti scrivere più volte il cond/rule. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempio {#section_E7454FFE169E459AABD9D033651939CB}

Supponiamo di avere un sito Web aziendale con un formato titolo standard: &quot;La mia azienda&quot; seguita da un trattino e quindi da una descrizione specifica della pagina ( ad esempio &quot;La mia azienda - Benvenuto&quot; o &quot;La mia azienda - Notizie&quot;). Vuoi togliere &quot;La mia azienda -&quot; dal titolo e convertire l&#39;intero titolo in lettere maiuscole quando indicizza il sito.

La regola di riscrittura seguente utilizza il contagocce della funzione per riscrivere solo la parte descrittiva di un titolo in maiuscolo:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>} 
```

Il Pattern della regola `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` contiene un riferimento di sfondo **`(.*)`** che corrisponde al contenuto del titolo che segue &quot;La mia azienda-&quot;. Tenere presente che l&#39;area circostante una parte di un pattern con parentesi ( ) crea un riferimento di sfondo a cui può fare riferimento la Sostituzione. In questo esempio, la sostituzione (${toupper:**$1**}) riscrive il riferimento di backreference (**$1**) utilizzando la funzione di contagocce.

Così, un titolo del modulo &quot;La mia azienda - Benvenuto&quot; è riscritto come &quot;BENVENUTO&quot;.

**Riconoscimento**

Il software del motore di riscrittura è stato originariamente sviluppato da Apache Group per l&#39;utilizzo nel progetto del server Apache HTTP (https://www.apache.org/).

## Aggiunta di regole del titolo di ricerca {#task_155CECB74BE3444384EDBBD04F41515E}

È possibile aggiungere regole per i titoli di ricerca per specificare la modalità di visualizzazione dei titoli nei risultati della ricerca nel sito web. È possibile manipolare qualsiasi parte del titolo.

<!-- 

t_adding_search_title_rules.xml

 -->

**Per aggiungere regole del titolo di ricerca**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search Title Rules]**.
1. Nel campo [!DNL Search Title Rules] , immetti le regole desiderate.

   Sono consentite righe vuote e di commento che iniziano con un carattere &#39;#&#39; (hash).
1. (Facoltativo) Nella pagina [!DNL Search Title Rules], immetti un titolo di test nel campo [!DNL Test Search Title Rules] , quindi fai clic su **Test**.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Ricostruisci l&#39;indice del sito di staging per visualizzare in anteprima i risultati.

   Consulta [Configurazione di un indice incrementale di un sito web organizzato](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Facoltativo) Nella pagina [!DNL Search Title Rules] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

