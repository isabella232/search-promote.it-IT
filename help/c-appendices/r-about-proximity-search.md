---
description: La ricerca per prossimità ti consente di associare una posizione univoca a qualsiasi pagina del sito web, quindi di cercare e ordinare i risultati per prossimità (distanza) da una determinata posizione.
solution: Target
title: Informazioni sulla ricerca in prossimità
topic-legacy: Appendices,Site search and merchandising
uuid: 24fc9265-3400-46a7-b6e0-4de5b049a39a
exl-id: 52e796a6-43ea-414f-8404-84ecd358bd76
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---

# Informazioni sulla ricerca in prossimità{#about-proximity-search}

La ricerca per prossimità ti consente di associare una posizione univoca a qualsiasi pagina del sito web, quindi di cercare e ordinare i risultati per prossimità (distanza) da una determinata posizione.

Ad esempio, supponiamo di aver popolato pagine sul sito web con metadati del codice postale degli Stati Uniti, come ad esempio:

```
<meta name="zipcode" content="84057">
```

Poi configura il tuo account per indicizzare i metadati del tuo codice ZIP. In **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** > **[!UICONTROL Add New Field]**, nella pagina [!DNL Add Field], imposta le seguenti opzioni:

* Nome campo: `zip`
* Nome/i del tag Meta: `zipcode`
* Tipo di dati: **[!UICONTROL Location]**
* Ordinamento: **[!UICONTROL Ascending]**
* Unità predefinite: **[!UICONTROL Miles]**

Dopo aver indicizzato il sito, esegui la seguente ricerca:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_s=zip_proximity
```

Il set di risultati contiene tutti i documenti che si trovano entro 100 miglia di CAP 84057, ordinati in ordine crescente di distanza da questo CAP.

È inoltre possibile utilizzare i codici dell&#39;area telefonica per le località degli Stati Uniti. In alternativa, puoi utilizzare le coppie latitudine/longitudine per specificare le posizioni nei metadati del sito e nei criteri di ricerca. Il tipo di posizione viene determinato automaticamente dal modulo dei dati forniti.

I valori di posizione a tre cifre (&quot;DDD&quot;, in cui ogni &quot;D&quot; rappresenta una cifra decimale da 0 a 9) sono trattati come un prefisso telefonico degli Stati Uniti.

I valori di posizione a cinque o quattro cifre (&quot;DDDD&quot; o &quot;DDDD-DDD&quot;) sono trattati come CAP degli Stati Uniti.

I valori di posizione nella forma esatta di &quot;±DD.DDDD±DDD.DDDD&quot; sono trattati come una coppia di latitudine/longitudine. Il primo valore numerico firmato specifica la latitudine e il secondo valore numerico firmato rappresenta la longitudine.

**Importante**: Se specifichi un valore di latitudine positivo o un valore di longitudine positivo o entrambi, il carattere &quot;+&quot; nell’URL deve essere codificato come  `%2b`. In caso contrario, il simbolo &quot;+&quot; viene interpretato come uno spazio e il valore non viene riconosciuto come posizione valida. Ad esempio, supponi di avere un valore di latitudine di +49.2394 e un valore di longitudine di -123.1892. La porzione di posizione dell’URL, con codifica &quot;+&quot;, sarà simile alla seguente:

```
...&sp_q_location_1=%2b49.2394-123.1892...
```

* I valori di latitudine positiva rappresentano i gradi a nord dell&#39;equatore.
* I valori di latitudine negativi rappresentano i gradi a sud dell&#39;equatore.
* I valori di longitudine positiva rappresentano i gradi a est del Primo Meridiano.
* I valori negativi di longitudine rappresentano i gradi ad ovest del Primo Meridiano.

Ad esempio, il valore &quot;+48.8577+002.2950&quot; rappresenta 48.8577 gradi a nord dell&#39;equatore, 2.295 gradi a est del Primo Meridian, la posizione esatta della Torre Eiffel a Parigi, Francia. Sono richiesti i segni numerici e ogni cifra, anche gli zeri iniziali e finali. Ad esempio, i tre valori &quot;48.8577+2.2950&quot;, &quot;+48.8577+2.2950&quot; e &quot;+48.8577+02.295&quot; non sono posizioni. Nel primo valore manca il segno iniziale sulla latitudine. Nel secondo valore mancano i due zeri iniziali sulla longitudine. Nel terzo valore manca lo zero finale sulla longitudine. Assicurati di esaminare attentamente il log degli indici per eventuali problemi relativi alla posizione.

Quando si cerca per prossimità c&#39;è un &quot;campo di output di prossimità&quot; speciale creato per quella ricerca. Il campo viene compilato con la distanza relativa tra la posizione specificata nei criteri di ricerca e la posizione associata a ciascun risultato di ricerca. Questo campo speciale viene denominato per il campo di tipo posizione utilizzato nei criteri di ricerca con &quot;_proximity&quot; aggiunto alla fine.

Nella ricerca di esempio di cui sopra, i risultati sono ordinati in ordine crescente di &quot;zip_proximity&quot;. Cioè, la distanza tra il codice ZIP specificato (84057) e la posizione del campo &quot;zip&quot; di ogni risultato. È inoltre possibile utilizzare questo speciale &quot;campo di uscita di prossimità&quot; per visualizzare la distanza relativa per ogni risultato della ricerca, in chilometri o miglia, utilizzando il tag modello `<Search-Display-Field>` Cerca .

Consulta [Ricerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Puoi anche eseguire ricerche senza l’opzione sp_s . In questo caso, i risultati sono ordinati per punteggio (sp_s=0, che è il valore predefinito). Il punteggio è influenzato dalla distanza relativa di ciascun risultato dalla posizione di ricerca di prossimità specificata dal parametro sp_q_location[_#]. Viene aggiunto un nuovo parametro cgi sp_q_max_relevant_distanza[#] per controllare facoltativamente il calcolo della pertinenza applicato alle ricerche di prossimità.

Di seguito è riportato un esempio di ricerca rilevante per la vicinanza:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_q_2=shirt&sp_x_2=title&sp_q_max_relevant_distance_2=50
```

Il set di risultati contiene tutti i documenti che si trovano entro 100 miglia dal codice ZIP 84057 e contengono la parola &quot;camicia&quot; nel campo titolo, ordinati in base al punteggio influenzato dal punteggio di rilevanza in prossimità. Un punteggio di pertinenza perfetto per il componente di prossimità rappresenterebbe una distanza di 0. Un punteggio minimo di pertinenza per la componente di prossimità rappresenterebbe una distanza di appena 50 miglia.

Per ulteriori informazioni sulla ricerca per prossimità, leggi `sp_location`, `sp_location_#`, `sp_q_min`, `sp_q_min_#`, `sp_q_max`, `sp_q_max_#` e `sp_s` nell’argomento di riferimento Cerca parametri CGI.

Consulta [Ricerca parametri CGI](../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890).

Consulta [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
