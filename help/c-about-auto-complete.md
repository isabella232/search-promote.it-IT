---
description: È possibile configurare diverse aree della funzione di completamento automatico per controllare la generazione del modulo di ricerca con completamento automatico abilitato e il file autocomplete_data.js, incluso nel modulo di ricerca con completamento automatico attivato.
seo-description: È possibile configurare diverse aree della funzione di completamento automatico per controllare la generazione del modulo di ricerca con completamento automatico abilitato e il file autocomplete_data.js, incluso nel modulo di ricerca con completamento automatico attivato.
seo-title: Completamento automatico
solution: Target
subtopic: Auto-Complete
title: Completamento automatico
topic: Design,Site search and merchandising
uuid: 3dfdd14d-2044-4f01-a5bc-fcb2eb0d5068
translation-type: tm+mt
source-git-commit: 552f93f1f630c64bbe3d5c8a87c4f5895ae6868c
workflow-type: tm+mt
source-wordcount: '1530'
ht-degree: 1%

---


# Completamento automatico{#about-auto-complete}

È possibile configurare diverse aree della funzione di completamento automatico per controllare la generazione del modulo di ricerca con completamento automatico abilitato e il file autocomplete_data.js, incluso nel modulo di ricerca con completamento automatico attivato.

## Completamento automatico {#concept_093A9CD754864BA79B456FE4BEB64578}

Il file [!DNL autocomplete_data.js] viene rigenerato e pubblicato nella rete di contenuti di ricerca ogni volta che vengono salvate modifiche dalla pagina di impostazione della funzione di completamento automatico.

## Configurazione del completamento automatico {#task_F491F2BFC4D24A61BBDC48B9059C11BB}

È possibile configurare e impostare le opzioni che controllano la generazione del modulo di ricerca abilitato per il completamento automatico e il file.

<!-- 

t_configuring_auto-complete.xml

 -->

Dopo aver configurato il completamento automatico, potete visualizzare l&#39;origine HTML risultante per la revisione. L’origine HTML è il contenuto che potete copiare e incollare nelle pagine del sito Web.

Vedere [Anteprima del modulo di ricerca così come apparirebbe sul modulo...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

Vedere [Configurazione dell&#39;elenco](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4)di parole con completamento automatico.

Consultate [Configurazione della funzione di completamento automatico del CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**Per configurare la funzione di completamento automatico**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Setup]**.
1. Nella [!DNL Auto-Complete Setup] pagina, impostate le opzioni desiderate.

   Vedere anche [Anteprima del modulo di ricerca così come apparirebbe sul modulo...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Numero massimo di suggerimenti </p> </td> 
      <td colname="col2"> <p>Specifica il numero massimo di elementi da visualizzare nell'elenco dei suggerimenti per il completamento automatico. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero minimo di caratteri di input </p> </td> 
      <td colname="col2"> <p>Specifica il numero di caratteri che un cliente deve digitare nel modulo di ricerca completo per consentirne la visualizzazione automatica prima di visualizzare i suggerimenti. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numero massimo di voci della cache </p> </td> 
      <td colname="col2"> <p>Specifica il numero massimo di suggerimenti di completamento automatico precedentemente richiesti da memorizzare nella cache nel browser del cliente. In genere, è consigliabile lasciare questa impostazione al valore predefinito 1000. </p> <p>È possibile disattivare completamente il caching dei browser impostando questa opzione su 0, ma non è consigliabile. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome modulo </p> </td> 
      <td colname="col2"> <p>Specifica l'attributo "name" del tag "form" del modulo di ricerca abilitato per l'auto-completamento. Ad esempio, </p> <p> <span class="filepath"> &lt;form name="SiteSearch" method="get" action="https://sp1004337c.guided.t1.atomz.com" target="_blank"&gt; </span> </p> <p>dove <span class="filepath"> SiteSearch </span> è l'attributo nome del tag modulo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>ID tag div </p> </td> 
      <td colname="col2"> <p>Specifica l'attributo ID del tag "div" del modulo di ricerca abilitato per l'auto-completamento. Ad esempio, </p> <p> <span class="filepath"> &lt;div id="autocomplete"&gt; </span> </p> <p>dove <span class="filepath"> autocomplete </span> è l'attributo del tag div. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>ID tag di input </p> </td> 
      <td colname="col2"> <p>Specifica l'attributo ID del tag "input" del modulo di ricerca abilitato per l'auto-completamento. Ad esempio, </p> <p> <span class="filepath"> &lt;input type="text" id="q" name="q" /&gt; </span> </p> <p>dove <span class="filepath"> q </span> è l'attributo id del tag di input. </p> </td> 
      </tr> 
      <tr>
      <td colname="col1"> <p>Visualizza ombra </p> </td>
      <td colname="col2"> <p>Aggiunge un’ombreggiatura cosmetica all’elenco dei suggerimenti per la compilazione automatica. </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>Corrispondenza solo all'inizio della frase </p> </td>
      <td colname="col2"> <p>Suggerisci solo risultati che corrispondano all’inizio del testo di input. </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>Supporta set di caratteri UTF-8 </p> </td>
      <td colname="col2"> <p>Gestire correttamente i caratteri non ASCII in termini. </p> </td>
      </tr>
    </tbody> 
   </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Configurazione dell&#39;elenco di parole con completamento automatico {#task_1F8E0F346263443383F8CFD2C7AB35D4}

Configurate come suggerimenti l&#39;elenco di parole e frasi che la funzione di completamento automatico visualizza a un cliente.

<!-- 

t_configuring_auto-complete_word_list.xml

 -->

Consultate [Configurazione della funzione di completamento](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)automatico.

Consultate [Configurazione della funzione di completamento automatico del CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**Per configurare l&#39;elenco di parole con completamento automatico**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Word List]**.
1. Nella [!DNL Auto-Complete Word List] pagina, impostate le opzioni desiderate.

   Vedere [Anteprima del modulo di ricerca così come apparirebbe sul modulo...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Periodo ricerche popolari </p> </td> 
      <td colname="col2"> <p> Controlla il periodo di tempo per l'inclusione di parole e frasi dalle ricerche recenti di un cliente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Numero massimo ricerche </p> </td> 
      <td colname="col2"> <p>Controlla il numero massimo di parole e frasi ricercate da includere nell'elenco di parole complete automaticamente. Le parole e le frasi principali, anch'esse più popolari, sono incluse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome campo </p> </td> 
      <td colname="col2"> <p>Ogni nome campo definisce il nome di un campo per il quale includere valori indicizzati. Utilizzare + e - per aggiungere o rimuovere i nomi dei campi. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Conteggio valori massimo </p> </td> 
      <td colname="col2"> <p>Definisce il numero massimo di valori campo consentiti per il nome campo selezionato. Sono inclusi i valori superiori, anch'essi quelli più citati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiungi queste parole e frasi </p> </td> 
      <td colname="col2"> <p> L'elenco di parole completo viene compilato con le parole e le frasi elencate in questa area. </p> <p> Fare clic su <span class="uicontrol"> Modifica </span> per visualizzare l'elenco o per aggiungere parole ed espressioni all'elenco. Al termine, fate clic su <span class="uicontrol"> Salva modifiche </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rimuovere queste parole e frasi </p> </td> 
      <td colname="col2"> <p> Le voci in questa area non vengono visualizzate nell'elenco di parole completo automatico. </p> <p> Fare clic su <span class="uicontrol"> Modifica </span> per visualizzare l'elenco o per aggiungere parole ed espressioni all'elenco. Al termine, fate clic su <span class="uicontrol"> Salva modifiche </span>. </p> <p> In questo elenco sono consentite espressioni regolari. Per specificare un'espressione regolare in questo elenco, iniziare la riga con <code>regexp</code> seguito da un singolo spazio, seguito dall'espressione regolare. Vengono rimosse tutte le righe dell'elenco di parole che corrispondono all'espressione regolare. </p> <p> <b>Importante</b>: È consigliabile utilizzare espressioni regolari solo se in precedenza sono state utilizzate con esse in altre applicazioni. </p> <p>Consultate <a href="c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignora maiuscole </p> </td> 
      <td colname="col2"> <p>Vengono rimosse le voci duplicate nell'elenco di parole complete automaticamente che differiscono solo in lettere maiuscole e minuscole; tutte le voci dell'elenco di parole sono forzate a essere minuscole. </p> <p>Se desiderate che i suggerimenti di completamento automatico vengano visualizzati come "prima lettera con maiuscole" o "tutte le didascalie", aggiungete le proprietà di testo <code>
          text-transform : capitalize; 
        </code> o <code>
          text-transform : uppercase; 
        </code> CSS al contenuto CSS di completamento automatico, in "/* stili per l'elemento risultato */". </p> <p>Consultate <a href="c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96" type="task" format="dita" scope="local"> Configurazione della funzione di completamento automatico del CSS </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aggiorna su reindicizzazione </p> </td> 
      <td colname="col2"> <p>L'elenco di parole completo automatico viene rigenerato automaticamente dopo ogni reindicizzazione dell'account. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.
   * Fate clic **[!UICONTROL Preview Word List]** [!DNL Auto-Complete Word List Preview] per salvare le modifiche apportate, quindi aprite la pagina in cui potete visualizzare l’elenco dei suggerimenti per la compilazione automatica. Utilizzate le opzioni di navigazione accanto alla parte superiore della pagina per esaminare e perfezionare l&#39;elenco visualizzato. Al termine, fate clic **[!UICONTROL Close]** per tornare alla [!DNL Auto-Complete Word List] pagina.

      Consultate [Utilizzo dell’opzione](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Configurazione della funzione di completamento automatico del CSS {#task_EECE35DEB6C94F4A8A5B42B4DED76D96}

Utilizzare la funzione di completamento automatico del CSS per configurare il foglio di stile a cascata automatico da utilizzare.

<!-- 

t_configuring_auto-complete_css.xml

 -->

La funzione di completamento automatico del codice CSS controlla il contenuto di [!DNL autocomplete_styles.css], incluso nel modulo di ricerca abilitato automaticamente. Il CSS specificato qui controlla la presentazione visiva dell&#39;elenco di suggerimenti auto-completi. Per un esempio delle idee di presentazione visiva possibili, consultate le seguenti risorse:

[https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html](https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html).

[Configurazione dell&#39;elenco](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4)di parole con completamento automatico.

[Configurazione della funzione di completamento](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)automatico.

Una volta completata la configurazione della funzione di completamento automatico del CSS, potete visualizzare in anteprima il modulo di ricerca per verificare se il CSS specificato è accettabile in termini di aspetto e layout.

Vedere [Anteprima del modulo di ricerca così come apparirebbe sul modulo...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

**Importante**: Per applicare un CSS personalizzato con completamento automatico, dovete rimuovere i tag dei commenti dalla seconda riga visualizzata nel codice HTML. Quindi si sposta la stessa riga all&#39;interno della sezione head della pagina che contiene il modulo di ricerca.

Vedere [Copia del codice HTML del modulo di ricerca in corso...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

**Per configurare la funzione di completamento automatico del CSS**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete CSS]**.
1. Nel campo [!DNL Auto-Complete CSS] di testo, incollate o digitate le informazioni del foglio di stile CSS da associare all&#39;elenco dei suggerimenti per il completamento automatico.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Visualizzazione in anteprima del modulo di ricerca così come apparirebbe sul sito Web {#task_437B35EFA5424603A08AF8E79E6B4714}

In base alla configurazione del CSS con completamento automatico e completamento automatico, è possibile visualizzare l’anteprima del modulo di ricerca se si desidera aggiungere il codice HTML al sito Web.

<!-- 

t_previewing_the_search_form_as_it_would_appear_on_your_website.xml

 -->

Consultate [Configurazione della funzione di completamento](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)automatico.

Consultate [Configurazione della funzione di completamento automatico del CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

Vedere [Copia del codice HTML del modulo di ricerca in corso...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Vedere [Uso delle raccolte nei moduli](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)di ricerca.

Vedere [Uso delle cornici con i moduli](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Vedere [Esempio di modulo](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)di ricerca avanzato.

Vedere Codice [HTML per moduli di ricerca](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9)avanzati.

Vedere Codice [modello di modulo di ricerca](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579)avanzata.

**Per visualizzare in anteprima il modulo di ricerca così come apparirebbe sul sito Web**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Search Form]**.
1. (Facoltativo) Fate clic **[!UICONTROL HTML code]** per visualizzare l’HTML copiato e incollato nelle pagine del sito Web.

## Copia del codice HTML del modulo di ricerca nelle pagine del sito Web {#task_A3A01EA800F24C0AA33902387E0362C7}

In base alla configurazione del CSS con completamento automatico e completamento automatico, è possibile visualizzare l’anteprima del modulo di ricerca se si desidera aggiungere il codice HTML al sito Web.

<!-- 

t_copying_the_html_code_of_the_search_form_into_the_pages_of_your_website.xml

 -->

Consultate [Configurazione della funzione di completamento](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)automatico.

Consultate [Configurazione della funzione di completamento automatico del CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

Vedere [Copia del codice HTML del modulo di ricerca in corso...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Vedere [Uso delle raccolte nei moduli](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)di ricerca.

Vedere [Uso delle cornici con i moduli](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Vedere [Esempio di modulo](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)di ricerca avanzato.

Vedere Codice [HTML per moduli di ricerca](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9)avanzati.

Vedere Codice [modello di modulo di ricerca](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579)avanzata.

**Per copiare il codice HTML del modulo di ricerca nelle pagine del sito Web**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**.

   >[!NOTE]
   >
   >Non modificare il `form name=` valore nell&#39;origine del modulo.

1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Se avete configurato la funzione di completamento automatico del CSS e desiderate applicare gli stili al modulo di ricerca, rimuovete i tag dei commenti dalla seconda riga visualizzata nel codice HTML. Quindi, spostare la stessa riga all&#39;interno della sezione head della pagina che contiene il modulo di ricerca.
   * Per ottenere il massimo delle prestazioni, spostate i tag elencati nella parte inferiore del codice HTML e posizionateli nella parte inferiore della sezione corpo di ciascuna pagina che contiene il modulo di ricerca.

1. Copiate il codice e incollatelo nelle pagine Web del sito Web in cui desiderate visualizzare il modulo di ricerca.
