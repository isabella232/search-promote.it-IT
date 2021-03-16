---
description: È possibile configurare diverse aree di Completamento automatico per controllare la generazione del modulo di ricerca con completamento automatico abilitato e il file autocomplete_data.js, incluso come parte del modulo di ricerca con completamento automatico abilitato.
solution: Target
subtopic: Auto-Complete
title: Informazioni sul completamento automatico
topic: Progettazione, ricerca nel sito e merchandising
uuid: 3dfdd14d-2044-4f01-a5bc-fcb2eb0d5068
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1499'
ht-degree: 1%

---


# Informazioni sul completamento automatico{#about-auto-complete}

È possibile configurare diverse aree di Completamento automatico per controllare la generazione del modulo di ricerca con completamento automatico abilitato e il file autocomplete_data.js, incluso come parte del modulo di ricerca con completamento automatico abilitato.

## Informazioni sul completamento automatico {#concept_093A9CD754864BA79B456FE4BEB64578}

Il file [!DNL autocomplete_data.js] viene rigenerato e pubblicato nella rete di contenuti di ricerca ogni volta che si verificano modifiche salvate dalla pagina Configurazione completamento automatico .

## Configurazione del completamento automatico {#task_F491F2BFC4D24A61BBDC48B9059C11BB}

È possibile configurare e impostare le opzioni che controllano la generazione del modulo di ricerca abilitato per la compilazione automatica e il file.

<!-- 

t_configuring_auto-complete.xml

 -->

Dopo aver configurato il completamento automatico, è possibile visualizzare l&#39;origine HTML risultante per la revisione. L’origine HTML è l’elemento copiato e incollato nelle pagine del sito web.

Vedere [Anteprima del modulo di ricerca così come apparirebbe sul proprio...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

Vedere [Configurazione dell&#39;elenco di parole con completamento automatico](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4).

Consulta [Configurazione del CSS con completamento automatico](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**Per configurare il completamento automatico**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Setup]**.
1. Nella pagina [!DNL Auto-Complete Setup] , imposta le opzioni desiderate.

   Vedere anche [Anteprima del modulo di ricerca così come apparirebbe sul proprio...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Suggerimenti massimi </p> </td> 
      <td colname="col2"> <p>Specifica il numero massimo di elementi da visualizzare nell'elenco dei suggerimenti per il completamento automatico. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Caratteri di input minimi </p> </td> 
      <td colname="col2"> <p>Specifica il numero di caratteri che un cliente deve digitare nel modulo di ricerca con completamento automatico prima di visualizzare i suggerimenti. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero massimo di voci della cache </p> </td> 
      <td colname="col2"> <p>Specifica il numero massimo di suggerimenti di completamento automatico richiesti in precedenza da memorizzare in cache nel browser del cliente. In genere, è consigliabile lasciare questa impostazione al valore predefinito di 1000. </p> <p>È tuttavia sconsigliato disattivare completamente la memorizzazione in cache del browser impostando questa opzione su 0. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome del modulo </p> </td> 
      <td colname="col2"> <p>Specifica l'attributo "name" del tag "form" del modulo di ricerca abilitato automatico. Ad esempio, </p> <p> <span class="filepath"> &lt;form name="SiteSearch" method="get" action="https://sp1004337c.guided.t1.atomz.com" target="_blank"&gt; </span> </p> <p>dove <span class="filepath"> SiteSearch </span> è l'attributo name del tag modulo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>ID tag Div </p> </td> 
      <td colname="col2"> <p>Specifica l'attributo ID del tag "div" del modulo di ricerca abilitato automatico. Ad esempio, </p> <p> <span class="filepath"> &lt;div id="autocomplete"&gt; </span> </p> <p>dove <span class="filepath"> autocomplete </span> è l’attributo del tag div. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>ID tag di input </p> </td> 
      <td colname="col2"> <p>Specifica l'attributo ID del tag "input" del modulo di ricerca abilitato automatico. Ad esempio, </p> <p> <span class="filepath"> &lt;input type="text" id="q" name="q" /&gt; </span> </p> <p>dove <span class="filepath"> q </span> è l'attributo id del tag di input. </p> </td> 
      </tr> 
      <tr>
      <td colname="col1"> <p>Visualizza ombreggiatura </p> </td>
      <td colname="col2"> <p>Aggiunge un’ombreggiatura cosmetica all’elenco dei suggerimenti per il completamento automatico. </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>Corrispondenza solo all'inizio della frase </p> </td>
      <td colname="col2"> <p>Suggerisci solo i risultati che corrispondono all’inizio del testo di input . </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>Supporta set di caratteri UTF-8 </p> </td>
      <td colname="col2"> <p>Gestire correttamente i caratteri non ASCII in termini. </p> </td>
      </tr>
    </tbody> 
   </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configurazione dell&#39;elenco di parole con completamento automatico {#task_1F8E0F346263443383F8CFD2C7AB35D4}

Configura l’elenco di parole e frasi che il completamento automatico visualizza a un cliente come suggerimenti.

<!-- 

t_configuring_auto-complete_word_list.xml

 -->

Consulta [Configurazione del completamento automatico](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Consulta [Configurazione del CSS con completamento automatico](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**Per configurare l&#39;elenco di parole con completamento automatico**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Word List]**.
1. Nella pagina [!DNL Auto-Complete Word List] , imposta le opzioni desiderate.

   Vedere [Anteprima del modulo di ricerca così come apparirebbe sul proprio...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Periodo di ricerche popolari </p> </td> 
      <td colname="col2"> <p> Controlla il periodo di tempo per l'inclusione di parole e frasi dalle ricerche recenti di un cliente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Numero massimo di ricerche </p> </td> 
      <td colname="col2"> <p>Controlla il numero massimo di parole e frasi ricercate da includere nell'elenco di parole complete automaticamente. Sono incluse le parole e le frasi principali, che sono anche le più popolari. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome campo </p> </td> 
      <td colname="col2"> <p>Ogni nome campo definisce il nome di un campo per il quale includere valori indicizzati. Utilizza + e - per aggiungere o rimuovere i nomi di campo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Conteggio valori massimo </p> </td> 
      <td colname="col2"> <p>Definisce il numero massimo di valori di campo consentiti per il nome di campo selezionato. Sono inclusi i valori principali, anch'essi quelli più citati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi queste parole e frasi </p> </td> 
      <td colname="col2"> <p> L’elenco di parole con completamento automatico viene compilato con le parole e le frasi elencate in quest’area. </p> <p> Fare clic su <span class="uicontrol"> Modifica </span> per visualizzare l'elenco o per aggiungere parole ed frasi all'elenco. Al termine, fai clic su <span class="uicontrol"> Salva modifiche </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovi queste parole e frasi </p> </td> 
      <td colname="col2"> <p> Le voci in quest'area non vengono visualizzate nell'elenco di parole completo automatico. </p> <p> Fare clic su <span class="uicontrol"> Modifica </span> per visualizzare l'elenco o per aggiungere parole ed frasi all'elenco. Al termine, fai clic su <span class="uicontrol"> Salva modifiche </span>. </p> <p> Le espressioni regolari sono consentite in questo elenco. Per specificare un’espressione regolare in questo elenco, inizia la riga con <code>regexp</code> seguito da un singolo spazio, seguito dall’espressione regolare. Le righe dell’elenco di parole che corrispondono all’espressione regolare vengono rimosse. </p> <p> <b>Importante</b>: Utilizzare espressioni regolari solo se in precedenza sono state utilizzate in altre applicazioni. </p> <p>Consulta <a href="c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignora maiuscole </p> </td> 
      <td colname="col2"> <p>Le voci duplicate nell'elenco di parole completo automatico che differiscono solo per lettere maiuscole/minuscole alfabetiche vengono rimosse; tutte le voci dell’elenco di parole sono forzate a utilizzare lettere minuscole. </p> <p>Se desideri che i suggerimenti di completamento automatico vengano visualizzati come "prima lettera con maiuscole" o "tutte le maiuscole", aggiungi la 
        <code>
          text-transform : capitalize; 
        </code> o 
        <code>
          text-transform : uppercase; 
        </code> Proprietà di testo CSS per il contenuto CSS con completamento automatico, in "/* stili per l’elemento risultato */". </p> <p>Consulta <a href="c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96" type="task" format="dita" scope="local"> Configurazione del CSS con completamento automatico </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiornamento sul reindice </p> </td> 
      <td colname="col2"> <p>L'elenco di parole completo viene rigenerato automaticamente dopo ogni reindicizzazione dell'account riuscita. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.
   * Fai clic su **[!UICONTROL Preview Word List]** per salvare le modifiche apportate, quindi apri la pagina [!DNL Auto-Complete Word List Preview] in cui puoi rivedere l’elenco dei suggerimenti per il completamento automatico. Utilizza le opzioni di navigazione nella parte superiore della pagina per rivedere e perfezionare l’elenco visualizzato. Al termine, fai clic su **[!UICONTROL Close]** per tornare alla pagina [!DNL Auto-Complete Word List].

      Vedere [Uso dell&#39;opzione Cronologia](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configurazione del CSS con completamento automatico {#task_EECE35DEB6C94F4A8A5B42B4DED76D96}

Utilizzare il CSS con completamento automatico per configurare il foglio di stile CSS con completamento automatico da utilizzare.

<!-- 

t_configuring_auto-complete_css.xml

 -->

Il CSS con completamento automatico controlla il contenuto di [!DNL autocomplete_styles.css], incluso come parte del modulo di ricerca abilitato automatico. Il CSS specificato qui controlla la presentazione visiva dell’elenco dei suggerimenti con completamento automatico. Per un esempio delle idee di presentazione visiva possibili, consulta:

[https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html](https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html).

[Configurazione dell’elenco di parole con completamento automatico](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4).

[Configurazione del completamento automatico](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Una volta completata la configurazione del CSS con completamento automatico, puoi visualizzare in anteprima il modulo di ricerca per verificare se il CSS specificato è accettabile in termini di aspetto e layout.

Vedere [Anteprima del modulo di ricerca così come apparirebbe sul proprio...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

**Importante**: Per applicare il CSS personalizzato con completamento automatico, devi rimuovere i tag di commento dalla seconda riga visualizzata nel codice HTML. Quindi si sposta la stessa riga all’interno della sezione iniziale della pagina che contiene il modulo di ricerca.

Vedere [Copia del codice HTML del modulo di ricerca in...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

**Per configurare il CSS con completamento automatico**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete CSS]**.
1. Nel campo di testo [!DNL Auto-Complete CSS], incollare o digitare le informazioni del foglio di stile CSS che si desidera associare all&#39;elenco dei suggerimenti completi automaticamente.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Visualizzazione dell&#39;anteprima del modulo di ricerca così come apparirebbe sul sito web {#task_437B35EFA5424603A08AF8E79E6B4714}

In base alla configurazione del CSS con completamento automatico e completamento automatico, è possibile visualizzare in anteprima l’aspetto del modulo di ricerca se si desidera aggiungere il codice HTML al sito web.

<!-- 

t_previewing_the_search_form_as_it_would_appear_on_your_website.xml

 -->

Consulta [Configurazione del completamento automatico](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Consulta [Configurazione del CSS con completamento automatico](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

Vedere [Copia del codice HTML del modulo di ricerca in...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Vedere [Uso delle raccolte nei moduli di ricerca](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Vedere [Uso dei frame con forms](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Consultare [Esempio di modulo di ricerca avanzato](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).

Vedere [Codice HTML del modulo di ricerca avanzato](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9).

Vedere [Codice modello di modulo di ricerca avanzato](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579).

**Per visualizzare in anteprima il modulo di ricerca così come apparirebbe sul sito web**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Search Form]**.
1. (Facoltativo) Fai clic su **[!UICONTROL HTML code]** per visualizzare l’HTML che copia e incolla nelle pagine del sito web.

## Copiare il codice HTML del modulo di ricerca nelle pagine del sito web {#task_A3A01EA800F24C0AA33902387E0362C7}

In base alla configurazione del CSS con completamento automatico e completamento automatico, è possibile visualizzare in anteprima l’aspetto del modulo di ricerca se si desidera aggiungere il codice HTML al sito web.

<!-- 

t_copying_the_html_code_of_the_search_form_into_the_pages_of_your_website.xml

 -->

Consulta [Configurazione del completamento automatico](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Consulta [Configurazione del CSS con completamento automatico](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

Vedere [Copia del codice HTML del modulo di ricerca in...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Vedere [Uso delle raccolte nei moduli di ricerca](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Vedere [Uso dei frame con forms](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Consultare [Esempio di modulo di ricerca avanzato](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).

Vedere [Codice HTML del modulo di ricerca avanzato](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9).

Vedere [Codice modello di modulo di ricerca avanzato](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579).

**Per copiare il codice HTML del modulo di ricerca nelle pagine del sito web**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**.

   >[!NOTE]
   >
   >Non modificare il valore `form name=` nell’origine del modulo.

1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Se hai configurato il CSS con completamento automatico e desideri che gli stili siano applicati al modulo di ricerca, rimuovi i tag commento dalla seconda riga visualizzata nel codice HTML. Quindi, sposta la stessa riga all’interno della sezione iniziale della pagina che contiene il modulo di ricerca.
   * Per ottenere le massime prestazioni, sposta i tag elencati nella parte inferiore del codice HTML e posizionali nella parte inferiore della sezione corpo di ogni pagina contenente il modulo di ricerca.

1. Copia il codice e incollalo nelle pagine web del sito web in cui desideri visualizzare il modulo di ricerca.
