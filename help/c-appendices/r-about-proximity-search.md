---
description: La ricerca per prossimità consente di associare una posizione univoca a qualsiasi pagina del sito Web, quindi di cercare e ordinare i risultati per prossimità (distanza) da una determinata posizione.
seo-description: La ricerca per prossimità consente di associare una posizione univoca a qualsiasi pagina del sito Web, quindi di cercare e ordinare i risultati per prossimità (distanza) da una determinata posizione.
seo-title: Informazioni sulla ricerca di prossimità
solution: Target
title: Informazioni sulla ricerca di prossimità
topic: Appendices,Site search and merchandising
uuid: 24fc9265-3400-46a7-b6e0-4de5b049a39a
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Informazioni sulla ricerca di prossimità{#about-proximity-search}

La ricerca per prossimità consente di associare una posizione univoca a qualsiasi pagina del sito Web, quindi di cercare e ordinare i risultati per prossimità (distanza) da una determinata posizione.

Ad esempio, supponete di aver popolato pagine nel sito Web con metadati del codice postale statunitense quali:

```
<meta name="zipcode" content="84057">
```

Quindi configurate il vostro account per indicizzare i metadati del codice ZIP. In **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** > **[!UICONTROL Add New Field]**, sulla [!DNL Add Field] pagina si impostano le seguenti opzioni:

* Nome campo: `zip`
* Nome/i tag meta: `zipcode`
* Tipo di dati: **[!UICONTROL Location]**
* Ordinamento: **[!UICONTROL Ascending]**
* Unità predefinite: **[!UICONTROL Miles]**

Dopo aver indicizzato il sito, effettuate la ricerca seguente:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_s=zip_proximity
```

Il set di risultati contiene tutti i documenti ubicati entro 100 miglia dal codice ZIP 84057, ordinati in ordine crescente di distanza dal codice ZIP.

È inoltre possibile utilizzare i codici dell&#39;area telefonica per le ubicazioni negli Stati Uniti. In alternativa, potete utilizzare coppie latitudine/longitudine per specificare le posizioni nei metadati del sito e nei criteri di ricerca. Il tipo di posizione viene determinato automaticamente dal modulo dei dati forniti.

I valori di posizione a tre cifre (&quot;DDD&quot;, dove ogni &quot;D&quot; rappresenta una cifra decimale da 0 a 9) sono trattati come un codice dell&#39;area telefonica statunitense.

I valori di posizione di cinque o cinque cifre (DDDDD o DDDDD-DDDD) sono trattati come codice postale statunitense.

I valori di posizione nella forma esatta di &quot;±DD.DDDDD±DDD.DDDD&quot; sono trattati come una coppia latitudine/longitudine. Il primo valore numerico con segno specifica la latitudine e il secondo valore numerico con segno rappresenta la longitudine.

**Importante**: Se specificate un valore di latitudine positivo, un valore di longitudine positivo o entrambi, il carattere &quot;+&quot; nell’URL deve essere codificato come `%2b`. In caso contrario, il simbolo &quot;+&quot; viene interpretato come uno spazio e il valore non viene riconosciuto come una posizione valida. Ad esempio, se il valore di latitudine era +49.2394 e il valore di longitudine era -123.1892, La parte della posizione dell&#39;URL, con &quot;+&quot; codificato, avrà l&#39;aspetto seguente:

```
...&sp_q_location_1=%2b49.2394-123.1892...
```

* I valori di latitudine positivi rappresentano i gradi a nord dell’equatore.
* I valori di latitudine negativi rappresentano i gradi a sud dell’equatore.
* I valori di longitudine positivi rappresentano i gradi a est del Primo Meridiano.
* I valori di longitudine negativi rappresentano i gradi ad ovest del primo Meridian.

Ad esempio, il valore &quot;+48.8577+002.2950&quot; rappresenta 48.8577 gradi a nord dell&#39;equatore, 2.295 gradi a est del Primo Meridiano, la posizione esatta della Torre Eiffel a Parigi, Francia. I segni numerici e ogni cifra sono obbligatori, anche gli zero iniziali e finali. Ad esempio, i tre valori &quot;48.8577+2.2950&quot;, &quot;+48.8577+2.2950&quot; e &quot;+48.8577+02.295&quot; non sono posizioni. Nel primo valore manca il segno iniziale sulla latitudine. Nel secondo valore mancano i due zeri iniziali sulla longitudine. Nel terzo valore manca lo zero finale sulla longitudine. Accertatevi di esaminare attentamente il registro di indice per eventuali problemi relativi alla posizione.

Quando si esegue una ricerca per prossimità, per quella ricerca è creato un &quot;campo di output di prossimità&quot; speciale. Il campo viene compilato con la distanza relativa tra la posizione specificata nei criteri di ricerca e la posizione associata a ciascun risultato di ricerca. Questo campo speciale è denominato per il campo di tipo posizione utilizzato nei criteri di ricerca con l’aggiunta di &quot;_proximity&quot; alla fine.

Nella ricerca di esempio sopra, i risultati sono ordinati in ordine crescente in &quot;zip_proximity&quot;. Ovvero, la distanza tra il codice ZIP specificato (84057) e la posizione del campo &quot;zip&quot; di ogni risultato. È inoltre possibile utilizzare questo speciale &quot;campo di output di prossimità&quot; per visualizzare la distanza relativa per ogni risultato di ricerca, in chilometri o miglia, utilizzando il tag modello di `<Search-Display-Field>` ricerca.

Consultate [Cercare i tag](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)dei modelli.

È inoltre possibile eseguire ricerche senza l&#39;opzione sp_s. In tal caso, i risultati sono ordinati per punteggio (sp_s=0, che è il valore predefinito). La valutazione è influenzata dalla distanza relativa di ciascun risultato dalla posizione di ricerca di prossimità specificata dal parametro sp_q_location[_#] . È stato aggiunto un nuovo parametro cgi sp_q_max_relevant_distanza[#] , per controllare facoltativamente il calcolo della pertinenza applicato alle ricerche di prossimità.

Di seguito è riportato un esempio di ricerca per rilevanza per prossimità:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_q_2=shirt&sp_x_2=title&sp_q_max_relevant_distance_2=50
```

Il set di risultati contiene tutti i documenti che si trovano entro 100 miglia dal codice ZIP 84057 e contengono la parola &quot;camicia&quot; nel campo del titolo, ordinati per punteggio influenzato dal punteggio di rilevanza relativa alla prossimità. Un punteggio di rilevanza perfetto per il componente di prossimità rappresenterebbe una distanza di 0. Un punteggio minimo di rilevanza per il componente di prossimità rappresenterebbe una distanza di poco più di 50 miglia.

Per ulteriori informazioni sulla ricerca di prossimità, consulta `sp_location`, `sp_location_#`, `sp_q_min`, `sp_q_min_#`, `sp_q_max`, e `sp_q_max_#``sp_s` nell’argomento di riferimento Cerca parametri CGI.

Consultate [Cercare i parametri](../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890)CGI.

Consultate [Aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)tag meta.
