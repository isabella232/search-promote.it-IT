---
description: Leggi le domande frequenti su Search&amp;Promote
solution: Target
title: Domande frequenti
topic: Appendices,Site search and merchandising
uuid: 4ce454a4-e770-4587-91a0-a25491818ac6
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '8648'
ht-degree: 0%

---


# Domande frequenti{#frequently-asked-questions}

## Flash Adobe {#reference_4A25BBDE32214AF5A1A454F38FD51243}

Pagina delle domande frequenti che illustra il supporto dell&#39;indicizzazione e della ricerca di file SWF su un sito web.

Di seguito sono riportate le domande comuni relative ai file SWF:

* [Quando un file SWF viene sottoposto a ricerca per indicizzazione e indicizzato?](#section_01BB5259140D4D5FB04CCB7A1A63DE99)
* [Cosa devo fare per indicizzare un SWF...](#section_0A6A52CC70D4495BBE14D91906318F95)
* [Come vengono riconosciuti i file SWF?](#section_B36C0536AB544F509601DC6A11A8E656)
* [Come vengono indicizzati i file SWF?](#section_36856058A4B54FA5ABF921344F50410C)
* [Un file SWF viene conteggiato come pagina?](#section_0158D6DE70BC40D78E2374787B9F58AB)
* [Come posso impedire l&#39;indicizzazione di singoli file SWF...](#section_E38AD37989EF410B97AF5125057BFD22)
* [Come posso evitare l&#39;indicizzazione dei file SWF su...](#section_DF2606A50E9A44859CFA0D44D7C5F2E4)
* [Come mai non riesco a cercare i file SWF cinesi, giapponesi o coreani sul mio sito web?](#section_EE1A3A705AE74148BD195A0CE513A5C4)

## Quando un file SWF viene sottoposto a ricerca per indicizzazione e indicizzato? {#section_01BB5259140D4D5FB04CCB7A1A63DE99}

Un file SWF viene sottoposto a ricerca per indicizzazione e indicizzato se è contenuto in un tag di incorporamento o di oggetto in una pagina HTML, come nell&#39;esempio seguente:

```
<embed src="Flash-file-URL">  
 
<object>  
<param name=movie value="Flash-file-URL">  
</object> 
```

Un file SWF viene riconosciuto anche se si elenca l’URL del file come punto di ingresso.

Consulta [Aggiunta di più punti di ingresso URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Cosa devo fare per indicizzare un file SWF? {#section_0A6A52CC70D4495BBE14D91906318F95}

Per eseguire la ricerca per indicizzazione dei file SWF, selezionare il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Se in un documento HTML è presente un riferimento al file di Flash da un tag `<embed>` o `<object>` , il testo viene indicizzato e tutti gli URL elencati nel file vengono sottoposti a ricerca per indicizzazione.

Se al file non viene fatto riferimento da un tag `<embed>` o `<object>`, è possibile elencare il file SWF in un tag `<a href=...>` in un documento HTML o come punto di ingresso URL.

Consulta [Aggiunta di più punti di ingresso URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Come vengono riconosciuti i file SWF? {#section_B36C0536AB544F509601DC6A11A8E656}

I file SWF sono identificati dal seguente tipo MIME:

`application/x-shockwave-flash`

I file SWF vengono riconosciuti anche con i tipi `application/octet-stream`&quot; o `text/plain` MIME, purché l’estensione del file sia .swf.

Un server non configurato correttamente può utilizzare un tipo MIME diverso per i file SWF. Assicurati di controllare la configurazione del server in caso di problemi di ricerca per indicizzazione e indicizzazione dei file SWF.

## Come vengono indicizzati i file SWF? {#section_36856058A4B54FA5ABF921344F50410C}

Il testo contenuto in un file SWF è indicizzato come se fosse `<body>` testo nella pagina HTML di inclusione. Se un risultato della ricerca trova il testo contenuto in un file SWF incorporato, il risultato effettivamente si collega alla pagina HTML di inclusione e non al file SWF. In questo modo, il file SWF viene visualizzato nel contesto corretto.

Se un file SWF contiene un URL come azione &quot;Carica filmato&quot;, il testo nel file SWF a cui si fa riferimento viene indicizzato come parte della pagina HTML di inclusione.

Se un file SWF contiene un URL come azione &quot;Ottieni URL&quot;, l’URL viene sottoposto a ricerca per indicizzazione e successivamente, proprio come un riferimento HTML `<a href=...>` viene sottoposto a ricerca per indicizzazione e successivamente.

Se un file SWF è elencato come punto di ingresso URL, il testo del file SWF è indicizzato come una singola pagina. Risultato di ricerca che trova il testo da un file SWF di entrypoint direttamente nel filmato, non in una pagina HTML di inclusione.

Consulta [Aggiunta di più punti di ingresso URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Un file SWF viene conteggiato come pagina? {#section_0158D6DE70BC40D78E2374787B9F58AB}

No. Un file SWF è considerato parte della relativa pagina HTML di inclusione. Anche tutti gli URL &quot;Load Movie&quot; contenuti nei file SWF sono considerati parte della pagina HTML di inclusione. Pertanto, i file SWF a cui si fa riferimento da una pagina HTML non vengono conteggiati come &quot;pagina&quot; per il totale della pagina dell&#39;account.

Se un file SWF è elencato come punto di ingresso URL, allora quel file SWF e tutti gli URL &quot;Carica filmato&quot; elencati in quel file SWF sono conteggiati come una &quot;pagina&quot; per il totale di pagina dell&#39;account.

## Come posso impedire l&#39;indicizzazione di singoli file SWF? {#section_E38AD37989EF410B97AF5125057BFD22}

Per impedire l’indicizzazione di un file SWF, è possibile aggiungere un tag meta di robot ( `<meta name="ROBOTS" content="NOINDEX">`) o un tag `<noindex>` al documento HTML che lo contiene. Cioè, il documento che contiene il tag `<embed>` o `<object>` .

È inoltre possibile utilizzare il tag meta ( `<meta name="ROBOTS" content="NOFOLLOW">`) dei robot per impedire i seguenti URL contenuti nel file SWF. Se il documento HTML di cui fa parte è stato disattivato, le azioni elencate come &quot;Ottieni URL&quot; nel file SWF non sono seguite.

## Come si impedisce l’indicizzazione dei file SWF sul sito web? {#section_DF2606A50E9A44859CFA0D44D7C5F2E4}

Per disattivare l’indicizzazione SWF, deselezionare il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

È inoltre possibile scegliere di utilizzare [!DNL URL Masks] per disabilitare l&#39;indicizzazione dei file SWF.

Consulta [Aggiunta di maschere URL per indicizzare o meno parti di indice di...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Per disabilitare l&#39;indicizzazione SWF, immetti una delle seguenti maschere URL:

* `exclude *.swf` (se non utilizzi espressioni regolari)
* `exclude regexp ^.*\.swf$` (se utilizzi espressioni regolari)

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Come mai non riesco a cercare i file SWF cinesi, giapponesi o coreani sul mio sito web? {#section_EE1A3A705AE74148BD195A0CE513A5C4}

La ricerca/merchandising del sito ottiene UTF-8 dai file SWF creati con Adobe Flash. L&#39;UTF-8 non contiene alcuna indicazione di lingua. Se è stato selezionato il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare la lingua utilizzata dal file SWF.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

I file SWF precedenti non specificano neanche un set di caratteri. Se è stato selezionato il tipo di contenuto SWF **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare il set di caratteri utilizzato nel file SWF.

## Ricerca generale {#reference_E2C675162789452A9B99C6633B12CBEF}

Una pagina delle domande frequenti che illustra come la ricerca/merchandising dei siti aiuta i clienti che visitano il tuo sito web a trovare ciò che stanno cercando.

Di seguito sono riportate le domande comuni relative alla ricerca generale:

* [Devo installare un software per utilizzare il sito?](#section_02AB2AFF71984F9DAA3AF2B7C0847A22)
* [Cosa succede quando il mio sito supera il limite di pagina?](#section_ECA5FA01032D4322BABA4E2C7FE498C1)
* [Come posso cambiare l&#39;indirizzo e-mail dove settimanale...](#section_AE27F63DD13F425B940C8E7D9ED5C614)
* [Quanto sono sicure le informazioni del mio cliente sulla ricerca del sito/merchandising?](#section_5484CB954167412BB7F0480CB0C504B8)
* [E la privacy delle informazioni sui miei clienti?](#section_8FB493F15E51454BA92A0C83E14C0CC7)
* [Posso mostrare i miei banner pubblicitari sulla ricerca...](#section_611EB8B32C16418386CB7DC7FB6954B8)

Di seguito sono riportate le domande comuni sulle funzioni di ricerca:

* [Posso personalizzare i risultati della ricerca per il mio sito?](#section_A64B3A621B794DF78D35ED06D9C43D0B)
* [Posso vedere quali clienti stanno cercando sul mio...](#section_73709E1B0E82478DA7B4D15B6C845F33)
* [Come posso controllare quali tipi di contenuto (PDF, testo, Flash, MP3 e Microsoft Office) vengono indicizzati e cercati?](#section_0AB8CB4B6BFA4286AA082055FEBFBE1C)
* [Sono supportate le pagine web generate dinamicamente tramite contenuti basati su ASP, JSP, PHP, CFM o Perl?](#section_E279F004F1C542A2B9773B832E7B013F)
* [Come posso utilizzare i sinonimi per migliorare i risultati della ricerca...](#section_E6E36E12514F4D7BAB01F8D1AB61D57B)
* [Ho il controllo sull&#39;ordine dei risultati della ricerca...](#section_C6361048502745779D9749A842C4C370)
* [Posso cambiare la lingua della pagina dei risultati della ricerca?](#section_6EE41DA8241247D48BBEB061A50599C5)
* [Posso avere più di un sito sul mio Adobe...](#section_AFA8825182094660A71EEC84B8329D6D)
* [Posso cercare più di un dominio?](#section_BFBB0E9861D942F095B56CF0A8F16596)
* [Posso suddividere il mio sito in sezioni separate in modo che...](#section_52153A9DE9F9493B967A70583848B2A4)
* [Come posso escludere alcune parti del mio sito web dall&#39;essere...](#section_D452EDE153654EF398F4A87780C6D43B)
* [Quali set di caratteri sono supportati?](#section_A62A6F8F15804F968C77F2DEBDE8F8FD)
* [Cosa succede se cambio o aggiorno il mio sito web?](#section_489050E0EBC14D0594DBBAA0CCF4F6BA)
* [Il mio sito può essere indicizzato automaticamente?](#section_9C7D41636238488691ECDFEE4D4E5103)
* [Io uso delle password sul mio sito web. Posso ancora utilizzare il sito search/merchandising?](#section_4618EB5B66704640B5502D1B5CB4B32E)
* [Supporti la ricerca per indicizzazione e l&#39;indicizzazione di https o...](#section_D5BB8B8FBEA4405583E86B4AEC37151B)
* [Il sito web search/merchandising rispetta il file robots.txt sul mio sito web?](#section_73BBF6FE93C64C109F45CBC2FA394DB2)
* [Alcune parti del mio sito web devono essere aggiornate frequentemente in modo che...](#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3)
* [Posso utilizzare script o programmi per avviare un incrementale?](#section_0B6BB039557A42AA876D35D748E17DD0)

## Devo installare un software per utilizzare la ricerca/merchandising sul sito? {#section_02AB2AFF71984F9DAA3AF2B7C0847A22}

No. Questo è il vantaggio principale della ricerca/merchandising del sito. Il motore è un&#39;applicazione professionale ospitata e gestita interamente sui nostri server ad alte prestazioni. Questo rende il software più facile da usare rispetto ad altre soluzioni di ricerca. L’unica cosa da fare è aggiungere una piccola quantità di codice HTML alle tue pagine in modo che i clienti del tuo sito web possano inserire le ricerche. La ricerca/merchandising del sito si occupa di tutto il resto.

## Cosa succede quando il mio sito supera il limite di pagina? {#section_ECA5FA01032D4322BABA4E2C7FE498C1}

Continuiamo a servire le tue ricerche in modo che i visitatori possano cercare il tuo sito web senza interruzioni. Per vedere se il tuo sito web supera il limite di pagina, controlla lo stato del tuo Full Index o Live Log.

Vedere [Informazioni sull&#39;indice completo](../c-about-index-menu/c-about-full-index.md#concept_C69BD21863FD4856B49326F35DB570D3).

Vedere [Visualizzazione dell&#39;intero registro dell&#39;indice di una live o di una staging...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

## Come posso modificare l’indirizzo e-mail in cui vengono inviati i rapporti settimanali? {#section_AE27F63DD13F425B940C8E7D9ED5C614}

I rapporti settimanali vengono inviati al proprietario di ciascun account attivo. Per modificare l’indirizzo e-mail, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**. Se disponi di più account di ricerca attivi, tutte le newsletter vengono inviate al nuovo indirizzo.

Consulta [Configurazione delle informazioni utente personali](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

## Quanto sono sicure le informazioni del mio cliente sulla ricerca del sito/merchandising? {#section_5484CB954167412BB7F0480CB0C504B8}

Ricerca/merchandising del sito è sicuro, veloce, stabile e facile da usare. Non sei obbligato a utilizzare i cookie (anche se puoi farlo se vuoi) per utilizzare i nostri prodotti, e le informazioni sensibili, come le password, non vengono mai messe su alcun collegamento URL che può essere recuperato dal tuo browser.

## E la privacy delle informazioni sui miei clienti? {#section_8FB493F15E51454BA92A0C83E14C0CC7}

Adobe si impegna a rispettare la privacy dei propri clienti e visitatori. Vedi l&#39;Adobe [Centro per la privacy](https://www.adobe.com/privacy.html).

## Posso mostrare i miei banner pubblicitari sulle pagine dei risultati della ricerca? {#section_611EB8B32C16418386CB7DC7FB6954B8}

Sì. Puoi controllare l’aspetto e il contenuto dei risultati della ricerca. All’interno del modello di risultati di ricerca per il sito web, puoi creare collegamenti alla tua rete di scambio banner, ad esempio LinkExchange o SmartClicks. Eventuali hit creati dai visitatori vengono accreditati correttamente nel tuo account di scambio banner.

## Posso personalizzare i risultati della ricerca per il mio sito? {#section_A64B3A621B794DF78D35ED06D9C43D0B}

Sì. Questa è una funzione esclusiva di ricerca/merchandising del sito. Grazie alla tecnologia avanzata dei modelli e alla poca conoscenza dell’HTML, puoi controllare esattamente come vengono visualizzati i risultati della ricerca.

Consulta [Ricerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

La transizione tra i server e i server di ricerca/merchandising del sito è completamente semplice e invisibile per i clienti. Se non conosci l’HTML o non hai il tempo di creare un modello personalizzato, puoi scegliere tra un assortimento di modelli attraenti e pronti all’uso creati dal team interno di sviluppatori web professionisti.

## Posso vedere quali clienti stanno cercando sul mio sito? {#section_73709E1B0E82478DA7B4D15B6C845F33}

Sì. Manteniamo le statistiche di ricerca per le ricerche effettuate dai visitatori sul tuo sito web negli ultimi due mesi. Puoi esaminare queste statistiche in qualsiasi momento in Rapporti nel menu prodotto. I rapporti di ricerca forniscono informazioni vitali riguardo esattamente ciò che i visitatori stanno cercando sul tuo sito web. Puoi utilizzare queste informazioni per migliorare la progettazione o per ottimizzare il motore di ricerca/merchandising del sito in modo che sia più adatto ai visitatori.

## Come posso controllare quali tipi di contenuto (PDF, testo, Flash, MP3 e Microsoft Office) vengono indicizzati e cercati? {#section_0AB8CB4B6BFA4286AA082055FEBFBE1C}

È possibile configurare facilmente gli account per abilitare o disabilitare l&#39;indicizzazione e la ricerca del testo trovato all&#39;interno di documenti PDF, documenti di testo normale, filmati di Flash, file MP3 o documenti Microsoft Office.

Queste impostazioni sono controllate nella pagina [!DNL Staged Content Types] .

Consulta [Informazioni sui tipi di contenuto](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Sono supportate le pagine web generate dinamicamente tramite contenuti basati su ASP, JSP, PHP, CFM o Perl? {#section_E279F004F1C542A2B9773B832E7B013F}

Le pagine web HTML statiche o generate dinamicamente vengono indicizzate, incluse le pagine create da database o qualsiasi altro processo back-end. Poiché il codice HTML visualizzato da un browser è indicizzato, puoi utilizzare la ricerca/merchandising sui siti web, purché queste architetture back-end risultino in pagine HTML.

Il robot di ricerca esegue la ricerca per indicizzazione del sito web partendo dalla prima pagina all&#39;indirizzo del sito web specificato in [!DNL Account Settings] e segue i collegamenti da pagina a pagina.

Consulta [Configurazione delle impostazioni account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Quando il robot di ricerca esegue la ricerca per indicizzazione di tutte le pagine del sito web, è possibile utilizzare il motore di ricerca per cercare il sito. In altre parole, se i documenti generati dinamicamente vengono intrecciati nel sito web con collegamenti provenienti da altre pagine, il robot di ricerca può comunque eseguire la ricerca per indicizzazione e indicizzare il contenuto dinamico.

Una volta effettuato l’indicizzazione e la ricerca per indicizzazione del contenuto del sito web, i clienti possono cercare informazioni all’interno del contenuto indicizzato.

## Come posso utilizzare i sinonimi per migliorare i risultati della ricerca per il mio sito? {#section_E6E36E12514F4D7BAB01F8D1AB61D57B}

Puoi utilizzare i sinonimi quando desideri che i visitatori trovino pagine correlate alla query di ricerca.

Ad esempio, supponiamo che tu abbia una pagina che contiene un listino prezzi dei prodotti in vendita sul tuo sito. Tuttavia, dopo aver esaminato i rapporti di ricerca forniti dalla ricerca/merchandising del sito, si scopre che i clienti stanno cercando la parola &quot;costo&quot;, &quot;spesa&quot;, &quot;costo&quot; o &quot;tassa&quot; nelle loro ricerche. Queste parole non visualizzano la pagina del listino prezzi nei risultati della ricerca. Con la funzione [!DNL Add Synonyms] in [!DNL Dictionaries], è possibile specificare che queste parole sono tutti sinonimi e il cliente può trovare il proprio listino prezzi, indipendentemente dal termine di ricerca utilizzato.

Vedere [Informazioni sui dizionari](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034).

## Ho il controllo sull&#39;ordine dei risultati della ricerca? {#section_C6361048502745779D9749A842C4C370}

Sì. Utilizzando l’interfaccia di rilevanza avanzata, puoi controllare quali pagine vengono restituite per una query di ricerca specifica. Questa funzione è utile se si desidera essere certi che i clienti visualizzino una pagina specifica quando eseguono una query per determinate parole.

Consulta [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Posso cambiare la lingua della pagina dei risultati della ricerca? {#section_6EE41DA8241247D48BBEB061A50599C5}

Sì. Il modello di ricerca/merchandising del sito è flessibile quando si tratta di consentire la creazione di una pagina di risultati che utilizza la lingua scelta e corrisponde all’aspetto del sito web.

Il modello è costituito da una combinazione di testo, tag HTML standard e tag speciali definiti per visualizzare i risultati della ricerca. Quando un cliente esegue una ricerca, il robot di ricerca legge il modello, invia il testo utilizzando tag HTML standard e inserisce i collegamenti ai risultati in base ai tag modello speciali.

Consulta [Ricerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Se si desidera modificare la lingua dei risultati, è possibile modificare il testo inglese visualizzato nel modello.

Vedere [Modifica di una presentazione o di un modello di trasporto](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).

## Posso avere più di un sito sul mio accesso Adobe al cliente? {#section_AFA8825182094660A71EEC84B8329D6D}

Sì. Con un singolo Adobe Accesso cliente, puoi gestire un motore di ricerca diverso per molti siti web diversi. Selezionare e gestire gli account in &quot;Account&quot;.

Consulta [Selezione di un account diverso da utilizzare](../c-about-accounts-menu.md#task_03C0FE918E2D44529CDC3B8DB75D1B26).

## Posso cercare più di un dominio? {#section_BFBB0E9861D942F095B56CF0A8F16596}

Sì. Puoi configurare l’accesso a più domini utilizzando [!DNL URL Entrypoints]. Fornisci punti di ingresso URL per domini aggiuntivi di tua proprietà. Ricorda che devi disporre dell’autorizzazione per indicizzare domini che non sono di tua proprietà.

Consulta [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Posso suddividere il mio sito in sezioni separate in modo che i clienti possano cercare una qualsiasi di queste aree singolarmente o nell’intero sito? {#section_52153A9DE9F9493B967A70583848B2A4}

Sì. È inclusa una funzione &quot;Raccolte&quot; che consente ai clienti di cercare aree specifiche del sito web per trovare rapidamente ciò che stanno cercando.

Consulta [Informazioni sulle raccolte](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127).

Ad esempio, i clienti possono cercare una raccolta di URL relativi alle informazioni di vendita dei prodotti o una raccolta di URL relativi ai servizi di supporto. È possibile impostare le raccolte in modo che i clienti visualizzino un elenco a discesa di raccolte o un gruppo di caselle di controllo.

## Come si impedisce la ricerca di parti del sito web? {#section_D452EDE153654EF398F4A87780C6D43B}

Sì. Specifica le maschere URL per determinare quali pagine del sito web includere o escludere dall’indicizzazione. Le maschere URL determinano se le pagine del sito web vengono visualizzate nei risultati della ricerca.

Consulta [Informazioni sulle maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Consulta [Informazioni sullo script delle maschere URL](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

Per impedire la ricerca di parti di singole pagine web, è possibile escludere parti di una pagina dall’indicizzazione. Circonda il testo con i tag `<noindex>` e `</noindex>` . Questo metodo è utile se si desidera escludere il testo di navigazione dalle ricerche.

## Quali set di caratteri sono supportati? {#section_A62A6F8F15804F968C77F2DEBDE8F8FD}

Le pagine web in genere specificano il set di caratteri con un tag meta simile al seguente:

`<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-1">`

Il motore di ricerca/merchandising del sito indicizza correttamente le pagine web utilizzando tutti i set di caratteri comuni attualmente in uso su Internet. Alcuni dei set di caratteri supportati includono:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Arabo (ISO-8859-6) </p> </td> 
   <td colname="col2"> <p>Cinese (tradizionale; Big5) </p> </td> 
   <td colname="col3"> <p>Giapponese (Shift_JIS) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Arabo (Windows-1256) </p> </td> 
   <td colname="col2"> <p>Cinese (tradizionale; EUC-TW) </p> </td> 
   <td colname="col3"> <p>Russo (KOI8-R) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Baltico (ISO-8859-4) </p> </td> 
   <td colname="col2"> <p>Cirillico (ISO-8859-5) </p> </td> 
   <td colname="col3"> <p>Europa meridionale (ISO-8859-3) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Baltico (Windows-1257) </p> </td> 
   <td colname="col2"> <p>Cirillico (Windows-1251) </p> </td> 
   <td colname="col3"> <p>Turco (ISO-8859-9) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Europa centrale (ISO-8859-2) </p> </td> 
   <td colname="col2"> <p>Greco (ISO-8859-7) </p> </td> 
   <td colname="col3"> <p>Turco (Windows-1254) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Europa centrale (Windows-1250) </p> </td> 
   <td colname="col2"> <p>Greco (Windows-1253) </p> </td> 
   <td colname="col3"> <p>Unicode (UTF-8) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cinese (ISO-2022-CN) </p> </td> 
   <td colname="col2"> <p>Ebraico (ISO-8859-8) </p> </td> 
   <td colname="col3"> <p>US-ASCII (us-ascii) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cinese (ISO-2022-CN-EXT) </p> </td> 
   <td colname="col2"> <p>Ebraico (Windows-1255) </p> </td> 
   <td colname="col3"> <p>Europa occidentale (ISO-8859-1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cinese (semplificato; EUC-NC) </p> </td> 
   <td colname="col2"> <p>Giapponese (EUC-JP) </p> </td> 
   <td colname="col3"> <p>Europa occidentale (ISO-8859-15) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cinese (semplificato; (GB2312) </p> </td> 
   <td colname="col2"> <p>Giapponese (ISO-2022-JP) </p> </td> 
   <td colname="col3"> <p>Europa occidentale (Windows-1252) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cinese (semplificato; GBK) </p> </td> 
   <td colname="col2"> <p>Giapponese (ISO-2022-JP-1) </p> </td> 
   <td colname="col3"> <p>Europa occidentale (x-mac-roman) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cinese (semplificato; (HZ-GB-2312) </p> </td> 
   <td colname="col2"> <p>Giapponese (ISO-2022-JP-2) </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Per informazioni sui set di caratteri non elencati sopra, contatta il supporto tecnico .

## Cosa succede se cambio o aggiorno il mio sito web? {#section_489050E0EBC14D0594DBBAA0CCF4F6BA}

Dopo aver modificato il contenuto del sito web, puoi eseguire un indice completo o un indice incrementale. La ricerca nel sito/merchandising scarica e indicizza qualsiasi contenuto del sito Web modificato. Al termine dell’indicizzazione, i clienti possono cercare il nuovo contenuto. Puoi anche pianificare un&#39;indicizzazione automatica del tuo sito in un determinato momento e in un giorno specifico.

Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

Consulta [Impostazione della pianificazione completa dell&#39;indice per un sito web live](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

Consulta [Impostazione della pianificazione incrementale dell&#39;indice per un sito web live](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Il mio sito può essere indicizzato automaticamente? {#section_9C7D41636238488691ECDFEE4D4E5103}

Sì. Puoi pianificare un indice automatico del sito ogni giorno.

Oltre all&#39;indicizzazione automatica giornaliera, è possibile scegliere di aver cambiato frequentemente parti del loro sito in modo incrementale indicizzato. Nei giorni in cui è pianificato un indice automatico, puoi controllare l&#39;ora del giorno in cui avviene l&#39;indice. Inoltre, puoi sempre avviare manualmente un indice del sito ogni volta che lo desideri.

Consulta [Impostazione della pianificazione completa dell&#39;indice per un sito web live](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

Consulta [Impostazione della pianificazione incrementale dell&#39;indice per un sito web live](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Io uso delle password sul mio sito web. Posso ancora utilizzare la ricerca/merchandising del sito? {#section_4618EB5B66704640B5502D1B5CB4B32E}

Se si utilizza l&#39;autenticazione HTTP di base per proteggere tramite password determinate parti del sito web, è possibile specificare realm e password che la ricerca/merchandising del sito può utilizzare per indicizzare il sito.

Consulta [Aggiunta di password per accedere alle aree del sito Web che richiedono...](../c-about-settings-menu/c-about-crawling-menu.md#task_DED19D476FF04B48BB6456D5ECB8628A).

## Supporti la ricerca per indicizzazione e la ricerca per indicizzazione di contenuto https o server protetto? {#section_D5BB8B8FBEA4405583E86B4AEC37151B}

Sì. È possibile eseguire ricerche per indicizzazione e indicizzazione del contenuto sui server sicuri (https).

## Il sito web search/merchandising rispetta il file robots.txt sul mio sito web? {#section_73BBF6FE93C64C109F45CBC2FA394DB2}

Sì. Il protocollo di esclusione dei robot è conforme. Il robot di ricerca esamina il file robots.txt se è presente sul tuo sito web. Se il file robots.txt esclude tutti i robot dalla ricerca per indicizzazione del sito, viene escluso anche il robot di ricerca/merchandising del sito. Per consentire solo al robot di ricerca/merchandising del sito di eseguire la ricerca per indicizzazione del sito, impostare il contenuto del file robots.txt su quanto segue:

```
User-agent: Atomz/1.0 
Disallow:
```

```
User-agent: * 
Disallow: /
```

Per ulteriori informazioni sui robot web e sul protocollo di esclusione robot, consulta:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

## Alcune parti del mio sito web devono essere aggiornate frequentemente in modo che i miei clienti ottengano risultati di ricerca più precisi. L’indicizzazione incrementale aiuta con questo problema? {#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3}

Sì. Questo è lo scenario in cui è stata creata la funzione di indicizzazione incrementale per facilitare la ricerca/merchandising del sito. Il vantaggio principale dell&#39;indicizzazione incrementale è che consente alle aziende di indicizzare frequentemente parti del loro sito web che cambiano dinamicamente. Questa funzionalità assicura che i risultati della ricerca vengano visualizzati con precisione &quot;fino al minuto&quot;.

Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

Consulta [Impostazione della pianificazione incrementale dell&#39;indice per un sito web live](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Le pagine web generate in modo dinamico sono supportate da un database back-end, ad esempio cataloghi di prodotti o sistemi di gestione dell’inventario? {#section_26896C556483457E879785E751583B16}

Vengono indicizzate le pagine web HTML statiche o generate dinamicamente, comprese le pagine create da database o qualsiasi altro processo back-end. Poiché il codice HTML, visualizzato da un browser, è indicizzato, puoi utilizzare la ricerca/merchandising sul sito web, purché le informazioni sul database di back-end risultino in pagine HTML.

Il robot di ricerca esegue la ricerca per indicizzazione del sito web partendo dalla prima pagina all&#39;indirizzo del sito web specificato in [!DNL Account Settings] e segue i collegamenti da pagina a pagina.

Consulta [Configurazione delle impostazioni account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Quando il robot di ricerca esegue la ricerca per indicizzazione di tutte le pagine del sito web, è possibile utilizzare il motore di ricerca per cercare il sito. In altre parole, se i documenti generati dinamicamente vengono intrecciati nel sito web con collegamenti provenienti da altre pagine, il robot di ricerca può comunque eseguire la ricerca per indicizzazione e indicizzare il contenuto dinamico del database.

Una volta effettuato l’indicizzazione e la ricerca per indicizzazione del contenuto del sito web, i clienti possono cercare informazioni all’interno del contenuto indicizzato.

È possibile abilitare facilmente la ricerca di contenuti completi o una ricerca basata su argomenti più ristretta, limitata alle informazioni contenute nel titolo, nella metamodescrizione, nei tag del documento delle parole chiave meta o in tutti e tre. Utilizzando le definizioni dei metadati, puoi anche creare campi di visualizzazione personalizzati, ad esempio un’immagine di prodotto, nei risultati di ricerca effettivi.

Consulta [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## È possibile utilizzare script o programmi per avviare un indice incrementale del sito? {#section_0B6BB039557A42AA876D35D748E17DD0}

Sì. È possibile utilizzare script o programmi per avviare un indice incrementale del sito Web, nonché per eseguire il ping dei server per indicizzare il sito ogni volta che il contenuto viene modificato o aggiornato.

Consultare [Informazioni sull&#39;indice con script](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D).

## Implementazioni delle funzioni {#reference_2D0C4A80B8D64051BA9694D562DCE663}

Pagina delle domande frequenti che illustra diverse implementazioni di funzioni in [!DNL Search&Promote].

Di seguito sono riportate le domande comuni relative alle implementazioni di funzioni in [!DNL Search&Promote] su un sito web:

* [Perché le mie regole di business non sono in esecuzione?](#section_7FEB60383D8A4B11A60DFF9067274699)
* [Perché ho problemi di pianificazione dell&#39;indicizzazione, errori durante l&#39;indicizzazione e problemi di avvio dell&#39;indicizzazione temporanea?](#section_E05758193DF5436784B0145839989F75)
* [Il limite di dimensione dell&#39;indice supera il limite consentito. Perché succede e come lo riparo?](#section_12E7DA979C4C4B1D8A3A6415FC3DDA70)

## Perché le mie regole di business non sono in esecuzione? {#section_7FEB60383D8A4B11A60DFF9067274699}

Configura le regole di business quando vengono visualizzati i banner o per aiutarti a decidere quali risultati visualizzare e in quale ordine. Puoi anche configurare la posizione di un elemento nel facet e il modello utilizzato per una determinata ricerca.
Riordinare le regole business per modificare l&#39;ordine in cui vengono eseguite sui modelli di presentazione. Le regole aziendali vengono eseguite nell&#39;ordine in cui sono state definite; cioè, più alto è il numero dell&#39;ordine di una regola, più tardi viene eseguito nel processo, trumping regole precedenti. È possibile riordinare le regole immettendo un nuovo numero nella colonna Ordine della tabella nella pagina Regole business.

Consultare [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Perché ho problemi di pianificazione dell&#39;indicizzazione, errori durante l&#39;indicizzazione e problemi di avvio dell&#39;indicizzazione temporanea? {#section_E05758193DF5436784B0145839989F75}

Quando si genera un indice, che sia pieno o incrementale, le informazioni sullo stato della ricerca per indicizzazione vengono visualizzate in tempo reale. Ad esempio, puoi visualizzare il tempo di inizio, il tempo trascorso e tutti gli errori che si sono verificati durante il processo di indicizzazione. Vengono visualizzate anche informazioni sullo stato dell&#39;ultimo indice. Usa queste informazioni per risolvere eventuali errori di indicizzazione riscontrati.

Per pianificare un indice, vedi [Impostazione della pianificazione dell&#39;indice completo per un sito web live](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0) e [Impostazione della pianificazione dell&#39;indice incrementale per un sito web live](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

Per avviare un indice di staging, vedere [Esecuzione di un indice completo di un sito web live o di staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D) o [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Il limite di dimensione dell&#39;indice supera il limite consentito. Perché succede e come lo riparo? {#section_12E7DA979C4C4B1D8A3A6415FC3DDA70}

Un sito web può tendere a crescere e nel tempo Search&amp;Promote &quot;scopre&quot; più documenti e pagine web che sono stati aggiunti. Alla fine, il tuo account potrebbe superare il limite di dimensioni dell&#39;indicizzazione. In questi casi, puoi prendere in considerazione l&#39;utilizzo di **[!UICONTROL URL Mask]**. Questa funzione nasconde documenti e pagine web dalla ricerca per indicizzazione che non si desidera o non è necessario avere indicizzato, riducendo in tal modo la dimensione dell&#39;indice. Un&#39;altra opzione potrebbe essere quella di contattare il Supporto Tecnico per avere il limite di dimensione dell&#39;indicizzazione impostato più grande nel tuo account.

Consulta [Informazioni sulle maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Se non sai cosa fare, contatta il supporto tecnico. Ci possono essere molte altre variabili che influiscono sulla dimensione dell&#39;indice che, se regolate, possono anche influenzare la fatturazione del tuo account.

## Internazionale {#reference_F017C2968BFB446499EF1D3CE2CAC0FE}

Una pagina delle domande più frequenti che illustra il supporto dell’indicizzazione e della ricerca di più di 19 lingue, incluse le lingue asiatiche multibyte come cinese (semplificato e tradizionale), giapponese e coreano.

Di seguito sono riportate le domande comuni relative alle lingue e ai set di caratteri:

* [Controllo della codifica del set di caratteri della query di ricerca in corso...](#section_DF2E8570AFC2480FA199FD26C941A22F)
* [Sono cercate solo le pagine la cui codifica corrisponde alla codifica di...](#section_9E544F3DB7DE41618DC1BC8224B32C5A)
* [Quale codifica viene utilizzata per la pagina dei risultati di ricerca?](#section_DA68670F35D54EAABF7DBB010F4409BF)
* [Posso utilizzare la ricerca/merchandising del sito su pagine codificate Unicode, UTF-8?](#section_130997CB08934A13A5261D85CF88040C)
* [Perché non è possibile cercare i file PDF cinesi, giapponesi o coreani sul mio sito web?](#section_539AFF482F814D28B5929F683D2F2175)
* [Come mai non riesco a cercare i file SWF cinesi, giapponesi o coreani sul mio sito web?](#section_9C0849528AFF4C10AA97A2C912992638)
* [Perché non è possibile cercare i file Microsoft Office cinesi, giapponesi o coreani sul sito web?](#section_6764BA6863AF492EBA9BE5CCC12CDD1F)
* [Perché non posso cercare i file MP3 cinesi, giapponesi o coreani sul mio sito web?](#section_DB6D60CF46F94125BF4E54AF3036DBFC)
* [Devo fare qualcosa di speciale per...](#section_A8BA6DDD3A6048319D3530BCFD6DA1A5)
* [Come mai i font cinesi, giapponesi o coreani compaiono nei risultati di ricerca in Netscape 4.7 e versioni precedenti?](#section_DF42567063304F918D406AC76529DFB7)

## Cosa controlla la codifica del set di caratteri della query di ricerca? {#section_DF2E8570AFC2480FA199FD26C941A22F}

La sezione &quot;Moduli web&quot; dell’account di ricerca contiene moduli di ricerca di esempio utilizzati per aggiungere funzionalità di ricerca al sito web. Se osservi questo codice dei moduli di ricerca, puoi trovare una riga simile alla seguente:

`<input type=hidden name="sp_f" value="iso-8859-1">`

Questa riga di codice indica al motore di ricerca che la query in arrivo è codificata in iso-8859-1, una codifica comune per le lingue dell&#39;Europa occidentale. Per modificare questa impostazione, vai al menu del prodotto e fai clic su **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**. Nella pagina [!DNL Personal Information], seleziona una nuova codifica dall’elenco a discesa **[!UICONTROL Character Encoding]** .

Consulta [Configurazione delle informazioni utente personali](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Puoi anche modificare manualmente il valore di codifica nelle pagine web modificando la riga `sp_f` del modulo di ricerca. Tenere presente che il valore `sp_f` del modulo di ricerca deve corrispondere alla codifica del set di caratteri della pagina in cui viene visualizzato.

## Vengono cercate solo le pagine la cui codifica corrisponde alla codifica della query di ricerca? {#section_9E544F3DB7DE41618DC1BC8224B32C5A}

Per impostazione predefinita, no. Se le pagine del sito web identificano correttamente la codifica del set di caratteri, vengono effettuate le conversioni necessarie tra la codifica della query di ricerca e quella delle pagine, anche quando le pagine utilizzano più codifiche.

## Quale codifica viene utilizzata per la pagina dei risultati di ricerca? {#section_DA68670F35D54EAABF7DBB010F4409BF}

La codifica set di caratteri dell’account determina la codifica predefinita per il modello di risultati.

Consulta [Configurazione delle informazioni utente personali](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Per ulteriori informazioni sulla specifica di un set di caratteri in un modello HTML, consulta la sezione .

Consulta [Ricerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## Posso utilizzare la ricerca/merchandising del sito su pagine codificate Unicode, UTF-8? {#section_130997CB08934A13A5261D85CF88040C}

Sì. Tuttavia, i set di caratteri Unicode, come UTF-8, non forniscono informazioni sufficienti per determinare la lingua in cui sono scritte le pagine. Per cercare correttamente queste pagine, è necessario specificare la lingua. Per determinare la lingua del documento, le informazioni vengono elaborate nel seguente ordine:

* Intestazione HTTP Content-Language distribuita per il documento dal server.
* Elementi META (ad esempio, `META HTTP-EQUIV="Content-Language" Content="ja_JP"`) nella sezione `<HEAD>` del documento.

* Attributo LANG del tag `<HTML>` (ad esempio, `<HTML LANG="ja_JP">`).

Se il server non è configurato per distribuire l’intestazione HTTP Content-Language e i documenti non contengono né l’elemento META della lingua né l’attributo della lingua per il tag `<HTML>` , è possibile utilizzare le iniezioni di metadati per specificare la lingua appropriata.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Perché non è possibile cercare i file PDF cinesi, giapponesi o coreani sul mio sito web? {#section_539AFF482F814D28B5929F683D2F2175}

Ricerca nel sito/merchandising ottiene UTF-8 dai file Adobe PDF senza indicazione di lingua. Se hai selezionato **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), devi utilizzare le iniezioni di metadati per specificare la lingua utilizzata nel file PDF.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Come mai non riesco a cercare i file SWF cinesi, giapponesi o coreani sul mio sito web? {#section_9C0849528AFF4C10AA97A2C912992638}

La ricerca nel sito/merchandising ottiene l&#39;UTF-8 dai file video di Flash Adobe creati con Adobe Flash senza indicazione della lingua. Se è stato selezionato il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare la lingua utilizzata nel file SWF.

Per il Flash versione 4 o versioni precedenti dei file SWF, il set di caratteri dei caratteri nel file non è specificato. Se è stato selezionato il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare il set di caratteri utilizzato nel file SWF.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Perché non è possibile cercare i file Microsoft Office cinesi, giapponesi o coreani sul sito web? {#section_6764BA6863AF492EBA9BE5CCC12CDD1F}

La ricerca/merchandising del sito ottiene UTF-8 da file di Microsoft Office (Microsoft Word, Microsoft Excel e Microsoft PowerPoint) senza alcuna indicazione di lingua. Se è stato selezionato il tipo di contenuto **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare la lingua utilizzata nei file di Microsoft Office.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Perché non posso cercare i file MP3 cinesi, giapponesi o coreani sul mio sito web? {#section_DB6D60CF46F94125BF4E54AF3036DBFC}

Se si seleziona il tipo di contenuto **[!UICONTROL Text in MP3 Music Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare il set di caratteri utilizzato per codificare i file MP3.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Devo fare qualcosa di speciale per ottenere i file .txt sul mio sito web per indicizzarli correttamente? {#section_A8BA6DDD3A6048319D3530BCFD6DA1A5}

Se hai selezionato il tipo di contenuto **[!UICONTROL Text Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), devi utilizzare le iniezioni di metadati per specificare il set di caratteri utilizzato per codificare i file .txt.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Come mai i font cinesi, giapponesi o coreani compaiono nei risultati di ricerca in Netscape 4.7 e versioni precedenti? {#section_DF42567063304F918D406AC76529DFB7}

Se l’account utilizza il modello predefinito, uno dei modelli pronti all’uso o un modello basato su uno di questi modelli, può contenere i tag dei font che specificano Arial o Helvetica come font. Ad esempio, `<font face="arial, helvetica" size="+1">`. Netscape 4.7 e versioni precedenti non visualizza i caratteri cinesi, giapponesi o coreani quando si utilizza il carattere Arial o Helvetica. Rimuovi l&#39;attributo `face` o sostituisci la faccia del font con una più appropriata per cinese, giapponese o coreano.

## Numero di pagine basso {#reference_4344E3E3CB2948939860F8C078BD7773}

Pagina delle domande frequenti che illustra i problemi comuni associati a un basso conteggio delle pagine di indicizzazione.

Di seguito sono riportate le domande comuni relative ai conteggi bassi delle pagine di indicizzazione:

* [Hai esaminato il tuo registro degli indici?](#section_D6626536DC3D40DDA4A1224F1CB276BF)
* [Hai degli errori di digitazione nell&#39;URL?](#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676)
* [La pagina web entrypoint ha collegamenti ad altre pagine?](#section_1C2D6ED54E7249268B555D9DC33352B3)
* [Sono collegamenti ad altre pagine del sito web incorporati in...](#section_EE34A67D60A844EBB0921C03544FF63E)
* [I tag HTML nella pagina web sono in un...](#section_F31A2F5D2C284AC084158A5BD763DC5D)
* [Hai formato in modo errato i tag di commento HTML nel tuo...](#section_D1C39D79341845CB9C38579AABDF3A24)
* [La pagina Web contiene collegamenti a pagine in un altro...](#section_F8082759184049AAA8FA6342C1F84389)
* [Stai utilizzando un servizio di dominio virtuale per il tuo URL...](#section_2861F09EA21A45E6B7E15F032739CDF3)
* [La tua pagina web utilizza un tag di aggiornamento meta?](#section_5A2F544C237C49B8B1A7FE0C45371C0D)
* [La tua pagina web utilizza un tag meta robots?](#section_36275A33DDFE4620BABA948F8A63DBD2)
* [Il tuo sito web utilizza un file di esclusione robot?](#section_BF7B663347814F58AD736066C86B7D25)

## Hai esaminato il tuo registro degli indici? {#section_D6626536DC3D40DDA4A1224F1CB276BF}

Il registro dell&#39;indice contiene informazioni dettagliate che il robot di ricerca/merchandising del sito raccoglie durante l&#39;indicizzazione del sito web. Il registro include un elenco dei collegamenti sottoposti a ricerca per indicizzazione e degli errori rilevati. Esaminare il registro degli indici è il punto migliore per iniziare a determinare perché tutte le pagine del sito web non sono indicizzate.

Vedere [Visualizzazione dell&#39;intero registro dell&#39;indice di una live o di una staging...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

Vedere [Visualizzazione del registro dell&#39;indice incrementale di una Live o Staged...](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

## Hai degli errori di digitazione nell&#39;URL? {#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676}

Quando si digitano URL lunghi nei moduli HTML, è possibile che si verifichino uno o più errori tipografici. Gli URL non devono contenere spazi. Inoltre, alcuni server web gestiscono gli URL in modo sensibile a maiuscole e minuscole.

Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Nella pagina [!DNL Staged URL Entrypoints] , verifica quanto segue:

* Negli URL non sono presenti errori tipografici.
* I caratteri negli URL usano tutti il casing corretto.
* Gli URL non contengono caratteri di spazio.

Per testare i punti di ingresso dell’URL, copia e incolla un URL in un browser web per verificare se il sito web viene visualizzato. Se non viene visualizzato, controlla di nuovo per assicurarti di non aver commesso errori nel percorso URL.

Consulta [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## La pagina web entrypoint include collegamenti ad altre pagine del sito web? {#section_1C2D6ED54E7249268B555D9DC33352B3}

Il robot di ricerca del sito/merchandising esamina il tuo sito web proprio come fa il tuo cliente; seguendo i collegamenti da pagina a pagina. I collegamenti devono essere presenti nella pagina web di entrypoint prima che il robot di ricerca possa trovare e indicizzare altre pagine del sito.

Consulta [Aggiunta di più punti di ingresso URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## I collegamenti ad altre pagine del tuo sito web sono incorporati in JavaScript? {#section_EE34A67D60A844EBB0921C03544FF63E}

È possibile utilizzare sofisticate tecniche di navigazione sul sito web, ad esempio azioni e menu di scorrimento, che utilizzano JavaScript per il collegamento ad altre pagine. Tuttavia, il robot di ricerca/merchandising del sito non può seguire i collegamenti incorporati in JavaScript.

Una soluzione che è possibile utilizzare per superare questo problema è quella di inserire collegamenti nascosti ad altre pagine nell&#39;HTML che contiene il JavaScript. Anche se i clienti del tuo sito web non vedono questi link, il robot di ricerca continua a trovarli e li striscia. Puoi posizionare i tag nascosti nella parte inferiore della pagina immediatamente prima del tag `</body>` . Potrebbero avere il seguente aspetto:

```
<a href="/mydir/mypag1.html"></a> 
<a href="/mydir/mypag2.html"></a>
```

Un’altra soluzione consiste nell’elencare gli URL delle pagine aggiuntive sul sito web come punti di ingresso da esaminare e indicizzare. Inizia gli URL con `https://` come illustrato di seguito:

```
https://www.mydomain.com/mydir/mypag1.html 
https://www.mydomain.com/mydir/mypag2.html
```

Consulta [Aggiunta di più punti di ingresso URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## I tag HTML nella pagina web sono in una sequenza non valida? {#section_F31A2F5D2C284AC084158A5BD763DC5D}

La specifica HTML richiede che i tag `<html>`, `<head>` e `<body>` seguano una sequenza specifica in un documento HTML. I tag in tutte le pagine web devono avere la seguente sequenza:

```
<html> 
<head> 
...  
<i>head tags go here</i> ... 
</head> 
<body> 
...  
<i>body tags go here</i> ... 
</body> 
</html>
```

Se i tag HTML non sono nell&#39;ordine corretto, il robot di ricerca/merchandising del sito non è in grado di analizzare e indicizzare correttamente la pagina web. Di seguito è riportato un esempio di tag che non si trovano nella sequenza corretta:

```
<body> 
<head> 
...  
<i>head tags are here</i> ... 
</head> 
...  
<i>body tags are here</i> ... 
</body>
```

In questo caso, inserisci i tag `<html>`, `<head>` e `<body>` nella sequenza corretta della pagina web.

## Hai dei tag di commento HTML non formattati correttamente nella tua pagina web? {#section_D1C39D79341845CB9C38579AABDF3A24}

Assicurati di esaminare attentamente e correggere eventuali commenti HTML non validi nelle pagine web.

La specifica HTML richiede che un commento HTML inizi con i caratteri `<!--` e termini con i caratteri `-->`. È facile ignorare i commenti formattati in modo errato che causano l&#39;analisi errata dei tag del robot di ricerca/merchandising del sito sulla pagina Web. Un commento formato in modo errato può causare la perdita di altri tag importanti da analizzare al robot di ricerca/merchandising del sito. Presta attenzione ai commenti immediatamente prima del tag `<body>` nella tua pagina web.

Di seguito è riportato un esempio di commento correttamente formato:

`<!-- This HTML comment is OK. -->`

Di seguito è riportato un esempio di commenti non correttamente formati:

```
<!- This HTML comment is improperly formed. -> 
<! This HTML comment is also improperly formed. >
```

## La tua pagina web contiene collegamenti a pagine su un altro dominio? {#section_F8082759184049AAA8FA6342C1F84389}

Spesso un sito web può essere costituito da pagine che in realtà esistono su un server web con un indirizzo di dominio diverso. Ad esempio, se l’indirizzo del sito Web principale è il seguente:

`https://www.mydomain.com/`

Il tuo sito web può anche contenere pagine su un altro dominio, ad esempio:

`https://www.otherdomain.com/`

Per impostazione predefinita, il robot di ricerca/merchandising del sito non segue i collegamenti su un dominio diverso da quello principale. Tuttavia, impostando altri punti di ingresso per il tuo account di ricerca, puoi facilmente indicizzare più domini.

Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Aggiungi l&#39;URL &quot;principale sito web entrypoint&quot; del tuo sito. Quindi, aggiungi altri punti di ingresso URL a qualsiasi altro dominio che contiene pagine del sito. Ad esempio, puoi impostare il tuo punto di ingresso URL principale su:

`https://www.mydomain.com/`

e aggiungi il seguente punto di ingresso URL del sito aggiuntivo:

`https://www.otherdomain.com/`

## Utilizzi un servizio di dominio virtuale per il tuo URL? {#section_2861F09EA21A45E6B7E15F032739CDF3}

Potresti utilizzare un servizio di dominio virtuale (talvolta denominato &quot;servizio di reindirizzamento del dominio&quot;) per fornire un URL migliore ai clienti per l’accesso al tuo sito web. Ad esempio, supponiamo che l’indirizzo reale del sito web sia il seguente:

`https://www.myispdomain.com/~myname/mywebpages/`

Tuttavia, puoi utilizzare un servizio di dominio virtuale in modo che i clienti possano accedere al tuo sito ai seguenti indirizzi:

`https://myname.adomain.com/`

 oppure 

`https://adomain.com/myname/`

Per impostazione predefinita, il robot di ricerca/merchandising del sito non segue i collegamenti su un dominio diverso da quello principale. Tuttavia, impostando altri punti di ingresso per il tuo account di ricerca, puoi facilmente indicizzare più domini.

Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Aggiungi il &quot;punto di ingresso dell’URL del sito web principale&quot; al nome di dominio virtuale del sito. Quindi, aggiungi ulteriori punti di ingresso al dominio in cui il tuo sito web vive effettivamente.

Ad esempio, imposta il punto di ingresso dell’URL principale su quanto segue:

`https://myname.adomain.com/`

E aggiungi il seguente punto di ingresso URL del sito Web aggiuntivo:

`https://www.myispdomain.com/~myname/mywebpages/`

## La tua pagina web utilizza un tag di aggiornamento meta? {#section_5A2F544C237C49B8B1A7FE0C45371C0D}

Molti siti web dispongono di una prima pagina che include un tag di aggiornamento meta tra i tag `<head>...</head>` simili ai seguenti:

`<meta http-equiv="Refresh" content="0;URL=https://www.adomain.com/apath/afile.html">`

In alcune circostanze, il robot di ricerca/merchandising del sito non è in grado di seguire l&#39;URL di aggiornamento del meta per indicizzare il contenuto del tuo sito web. Questo problema è facile da risolvere impostando altri punti di ingresso.

Scegliere **[!UICONTROL Settings]** > Ricerca per indicizzazione > **[!UICONTROL URL Entrypoints]** dal menu del prodotto. Aggiungi un altro punto di ingresso all’URL del tag di aggiornamento metadati.

## La tua pagina web utilizza un tag meta robots? {#section_36275A33DDFE4620BABA948F8A63DBD2}

A volte le pagine web utilizzano i tag meta robots per controllare i robot web che cercano periodicamente di cercare un sito web. I tag Meta robots vengono visualizzati tra i tag `<head>...</head>` di una pagina web e hanno un aspetto simile al seguente:

`<meta name="robots" content="noindex, nofollow">`

Poiché il robot di ricerca/merchandising del sito è esso stesso un robot web, segue le indicazioni del tag dei meta robot. Escludendo altri robot in questo modo si esclude anche il robot di ricerca/merchandising del sito.

Per ulteriori informazioni sui robot web e sul protocollo di esclusione robot, consulta:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

Rimuovi o modifica il tag meta robots sulle pagine web che desideri indicizzare sul tuo sito web.

## Il tuo sito web utilizza un file di esclusione robot? {#section_BF7B663347814F58AD736066C86B7D25}

A volte un sito web ha una pagina chiamata robots.txt che esclude tutti o alcuni robot dalla ricerca per indicizzazione. Per vedere se il tuo sito web ha un file robots.txt, cercarlo appena sotto il dominio di primo livello come mostrato in:

`https://www.yourdomain.com/robots.txt`

Il contenuto del file robots.txt è simile al seguente testo:

```
User-agent: * 
Disallow: /
```

Poiché il robot di ricerca/merchandising del sito è esso stesso un robot web, segue le indicazioni nel file robots.txt-esclude il robot di ricerca/merchandising del sito. Per risolvere questo problema, modifica il file di esclusione dei robot (robots.txt) per consentire al robot di ricerca del sito/merchandising di esaminare e indicizzare il tuo sito web come segue:

```
User-agent: Atomz/1.0 
Disallow: 
 
User-agent: * 
Disallow: /
```

## Microsoft Office {#reference_A85FCC8A96514A7584F4D2A8AC8111D1}

Pagina delle domande frequenti che illustra il supporto dell&#39;indicizzazione e della ricerca dei file di Microsoft® Office su un sito web.

Di seguito sono riportate le domande comuni relative ai file di Microsoft Office:

* [Cosa viene indicizzato in un file di Microsoft Office?](#section_8681DADFCFE24B7787B1FC08D431EE28)
* [Cosa non viene indicizzato in un file di Microsoft Office...](#section_BD53BDABFDD94D7EB0E1F55EC18017BB)
* [Come vengono indicizzati i file di Microsoft Office in modo diverso rispetto alle pagine HTML?](#section_C104B44684F340549A6B9EB8F39EDDBB)
* [Come evitare l&#39;indicizzazione dei file di Microsoft Office...](#section_FEBA71274CD14CB99731ADF982087F4C)

## Cosa viene indicizzato in un file di Microsoft Office? {#section_8681DADFCFE24B7787B1FC08D431EE28}

Il contenuto completo dei file di Microsoft Word, dei file di Microsoft Excel e dei file di Microsoft PowerPoint viene indicizzato.

Le parti seguenti di un file Microsoft Word sono indicizzate:

* Titolo
* Parole chiave
* Oggetto (descrizione)
* Contenuto basato su testo
* Collegamenti ipertestuali ad altri documenti

Le parti seguenti di un file Microsoft Excel sono indicizzate:

* Titolo
* Parole chiave
* Oggetto (descrizione)
* Testo nelle celle
* Valori da formule numeriche nelle celle

Le parti seguenti di un file Microsoft PowerPoint sono indicizzate:

* Titolo
* Parole chiave
* Oggetto (descrizione)
* Testo su ogni diapositiva

## Cosa non viene indicizzato in un file di Microsoft Office? {#section_BD53BDABFDD94D7EB0E1F55EC18017BB}

Gli elementi grafici contenuti nei file di Microsoft Office o in qualsiasi testo contenuto in un elemento grafico non vengono indicizzati. Le definizioni delle proprietà personalizzate non sono indicizzate come metadati. Anche alcuni testi in campi speciali, come intestazioni e piè di pagina in un file PowerPoint, non sono indicizzati.

## In che modo i file di Microsoft Office vengono indicizzati in modo diverso rispetto alle pagine HTML? {#section_C104B44684F340549A6B9EB8F39EDDBB}

La differenza tra il modo in cui il robot di ricerca indicizza i file Microsoft Office e i file HTML è che ogni file HTML è una singola pagina e un singolo file Microsoft Office può rappresentare centinaia di pagine. Per questo motivo, ogni pagina viene conteggiata all&#39;interno di un file di Microsoft Office come pagina separata nell&#39;account di ricerca.

## Come si impedisce l&#39;indicizzazione dei file di Microsoft Office sul sito web? {#section_FEBA71274CD14CB99731ADF982087F4C}

Se non si desidera che il robot di ricerca esegua la ricerca per indicizzazione e indicizzi i file di Microsoft Office, deselezionare il tipo di contenuto **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

È inoltre possibile utilizzare [!DNL URL Masks] per disabilitare l&#39;indicizzazione dei file di Microsoft Office.

Inserisci le seguenti maschere URL:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Se non utilizzi espressioni regolari </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DFEC911DA11C484C8E4671A0F00E1F88"> 
     <li id="li_2E50374E3869426B97353A5A8CBE09EC">escludi *.doc </li> 
     <li id="li_9089D11161524D90849CA88F703772B6">escludi *.xls </li> 
     <li id="li_7F6CFC6212E64C04AAF38E21A667C763">escludi *.ppt </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se utilizzi espressioni regolari </p> </td> 
   <td colname="col2"> 
    <ul id="ul_012A45C3EC04460EA09C0ECFB49A8FA9"> 
     <li id="li_0C239F0A536D465F85A98EBF7B6ADF27">escludi regexp ^.*\.doc$ </li> 
     <li id="li_9F91DA35A2A646ACAFF2BA37F9136E2A">escludi regexp ^.*\.xls$ </li> 
     <li id="li_9D768D9EA2DB44FBB00A1979E21672E2">escludi regexp ^.*\.ppt$ </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Consulta [Aggiunta di maschere URL per indicizzare o meno parti di indice di...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## MP3 {#reference_7614250EE81C4EEFA43E57A6A74E83D7}

Una pagina delle domande più frequenti che discute il supporto dell&#39;indicizzazione e della ricerca di file musicali MP3 su un sito web.

Di seguito sono riportate le domande comuni relative ai file MP3.

* [Quando un file MP3 viene sottoposto a ricerca per indicizzazione e indicizzato?](#section_538EA1682C9C47E3A62640BB25D84C36)
* [Cosa devo fare per cercare e indicizzare...](#section_3CD794446E3545379C14E9F222118665)
* [Come viene riconosciuto un file MP3?](#section_230E7336965A424F96C5CCF1D3C2D103)
* [Cosa viene indicizzato in un file MP3?](#section_E99D252B27CA4946AED3FCD3ABD8779D)
* [Un file MP3 viene conteggiato come pagina?](#section_9910BEB6617D4D2090558CDF6C65D16B)
* [Come posso impedire l&#39;indicizzazione di singoli file MP3...](#section_C989DC1D3D3841B38F683A462195DC05)
* [Come posso evitare l’indicizzazione dei file MP3?](#section_305D2B28D1124776B6DC0C62A17827C6)
* [Perché non posso cercare i file MP3 cinesi, giapponesi o coreani sul mio sito?](#section_06A48DA3F9E742CC93CC8B5CCD7382FA)

## Quando un file MP3 viene sottoposto a ricerca per indicizzazione e indicizzato? {#section_538EA1682C9C47E3A62640BB25D84C36}

I file MP3 vengono sottoposti a ricerca per indicizzazione in uno dei due modi. Il modo più comune è quello di un tag href di ancoraggio in un file HTML:

`<a href="MP3-file-URL"></a>`

Un secondo modo è quello di inserire l&#39;URL del file MP3 come punto di ingresso dell&#39;URL.

Consulta [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Cosa devo fare per eseguire la ricerca per indicizzazione dei file MP3 sul mio sito? {#section_3CD794446E3545379C14E9F222118665}

Per attivare la ricerca per indicizzazione e l&#39;indicizzazione MP3 per il tuo account, scegliere **[!UICONTROL Settings]** dal menu prodotto > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**. Nella pagina [!DNL Staged Content Types], seleziona **[!UICONTROL Text in MP3 Music Files]**.

Consulta [Informazioni sui tipi di contenuto](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Come viene riconosciuto un file MP3? {#section_230E7336965A424F96C5CCF1D3C2D103}

Un file MP3 è riconosciuto dal suo tipo MIME che è &quot;audio/mpeg&quot;.

## Cosa viene indicizzato in un file MP3? {#section_E99D252B27CA4946AED3FCD3ABD8779D}

Facoltativamente, i file MP3 memorizzano una piccola quantità di informazioni testuali. Tali informazioni possono includere il nome dell&#39;album, il nome dell&#39;artista, il titolo della canzone, il genere della canzone, l&#39;anno di pubblicazione e un commento. Queste informazioni vengono memorizzate alla fine del file in quello che viene chiamato TAG. I file MP3 che contengono informazioni TAG sono indicizzati nel modo seguente:

* Il titolo della canzone viene trattato come il titolo di una pagina HTML.
* Il commento viene trattato come una descrizione definita per una pagina HTML.
* Il genere viene trattato come una parola chiave definita per una pagina HTML.
* Il nome dell&#39;artista, il nome dell&#39;album e l&#39;anno di rilascio vengono trattati come il corpo di un documento HTML.

## Un file MP3 viene conteggiato come pagina? {#section_9910BEB6617D4D2090558CDF6C65D16B}

Sì, ogni file MP3 sottoposto a ricerca per indicizzazione e indicizzato sul tuo sito web viene conteggiato come una pagina.

## Come posso impedire l&#39;indicizzazione di singoli file MP3? {#section_C989DC1D3D3841B38F683A462195DC05}

Racchiudi i tag di ancoraggio che collegano ai file MP3 con tag `<nofollow>` e `</nofollow>` . Il robot di ricerca non segue i collegamenti tra questi tag.

Un altro metodo è quello di aggiungere gli URL dei file MP3 come maschere di esclusione.

Consulta [Informazioni sulle maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Consulta [Informazioni sullo script delle maschere URL](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

## Come posso evitare l’indicizzazione dei file MP3? {#section_305D2B28D1124776B6DC0C62A17827C6}

Il modo più semplice per controllare l&#39;indicizzazione MP3 per il tuo account è quello di deselezionare **[!UICONTROL Text in MP3 Music Files]** nella pagina [!DNL Staged Content Types] .

Consulta [Selezione dei tipi di contenuto per la ricerca per indicizzazione e l&#39;indice](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

Puoi anche utilizzare la funzione URL Mask per disabilitare l&#39;indicizzazione MP3 per estensione di file. A questo scopo, nel menu del prodotto fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. Inserisci una delle seguenti maschere:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Se il tuo account.. </p> </th> 
   <th colname="col2" class="entry"> <p>Inserisci la seguente maschera URL </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Non utilizza espressioni regolari </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> escludi *.mp3  </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilizza espressioni regolari </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> escludi regexp ^.*\.mp3$ </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Perché non posso cercare i file MP3 cinesi, giapponesi o coreani sul mio sito? {#section_06A48DA3F9E742CC93CC8B5CCD7382FA}

Per cercare i file MP3 cinesi, giapponesi o coreani, scegliere **[!UICONTROL Settings]** dal menu del prodotto > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** > **[!UICONTROL Text in MP3 Music Files]**. Quindi, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]** e specifica il set di caratteri utilizzato per codificare i file MP3.

Consulta [Selezione dei tipi di contenuto per la ricerca per indicizzazione e l&#39;indice](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

Vedere [Informazioni sulle iniezioni](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

## PDF {#reference_F127C4915A0D436DA34E5D75ABFBB21B}

Una pagina delle domande frequenti in cui viene discusso il supporto dell&#39;indicizzazione e della ricerca di file PDF su un sito web.

Di seguito sono riportate le domande comuni relative ai file PDF:

* [Cosa viene indicizzato in un file PDF?](#section_62BFCD7158B44F2BB3B1864224B50174)
* [Cosa non viene indicizzato in un file PDF?](#section_A14B353AE503408896BACBBF3F748FA0)
* [Come vengono conteggiati i file PDF indicizzati?](#section_C35DE36A65D649BD8FF314E9EFD990A6)
* [I risultati della ricerca possono visualizzare un’icona PDF?](#section_829CE82CC3544502A13D27C4DB820189)
* [I risultati della ricerca possono collegarsi a una pagina particolare in...](#section_A06E7F7017E6441E98209D288EE57BF6)
* [Come si impedisce l&#39;indicizzazione dei file PDF su...](#section_96671419A822486AAC654D8DAD819940)
* [Perché non è possibile cercare i file PDF cinesi, giapponesi o coreani sul mio sito web?](#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8)

## Cosa viene indicizzato in un file PDF? {#section_62BFCD7158B44F2BB3B1864224B50174}

Il contenuto completo dei file PDF è indicizzato. Sono indicizzate le parti seguenti di un file PDF:

* Titolo
* Parole chiave
* Oggetto (descrizione)
* Contenuto basato su testo

## Cosa non viene indicizzato in un file PDF? {#section_A14B353AE503408896BACBBF3F748FA0}

Il sommario PDF, gli elementi grafici all’interno del file o qualsiasi testo che fa parte di un elemento grafico contenuto non sono indicizzati.

## Come vengono conteggiati i file PDF indicizzati? {#section_C35DE36A65D649BD8FF314E9EFD990A6}

Ogni file PDF viene conteggiato come un singolo documento, inclusi i PDF che contengono più pagine.

## I risultati della ricerca possono visualizzare un’icona PDF? {#section_829CE82CC3544502A13D27C4DB820189}

Sì. Utilizza il tag `<search-if-link-extension>` all’interno del modello per includere nei risultati di ricerca un’icona PDF o altri elementi grafici o testo:

```
<search-results> 
  ... 
  <search-if-link-extension value=".pdf"> 
    <img src="/search/i/pdficon.gif"> 
  </search-if-link-extension> 
  ... 
</search-results>
```

Le icone PDF consentono ai clienti di sapere che un risultato della ricerca si collega a un file PDF di grandi dimensioni. Le dimensioni dei file possono essere importanti per i clienti che accedono al tuo sito web tramite un modem o un dispositivo mobile.

## I risultati della ricerca possono collegarsi a una pagina particolare in un file PDF? {#section_A06E7F7017E6441E98209D288EE57BF6}

Sì. Utilizzando il tag modello per collegamenti avanzati ( `<search-smart-link>...</search-smart-link>`), i clienti possono fare clic per aprire la prima pagina PDF contenente il risultato della ricerca.

Per utilizzare i collegamenti avanzati, sostituisci i tag `<search-link>...</search-link>` nella sezione dei risultati di ricerca del modello con i tag `<search-smart-link>...</search-smart-link>` . Quando un cliente fa clic su un collegamento generato dai tag di collegamento intelligente, passa alla prima pagina PDF rilevante per la query di ricerca.

>[!NOTE]
>
>Per utilizzare questa funzione, il cliente deve utilizzare una versione recente del Reader Adobe Acrobat o Adobe Acrobat, che deve includere il plug-in di evidenziazione e il plug-in EWH (External Window Handler). Inoltre, il browser deve utilizzare il plug-in Adobe Acrobat per Netscape Navigator (è possibile utilizzare qualsiasi browser che accetta questo plug-in Netscape Navigator) o il controllo Acrobat ActiveX per Internet Explorer 4.0 e versioni successive.

Consulta [Ricerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## Come si impedisce l’indicizzazione dei file PDF sul sito web? {#section_96671419A822486AAC654D8DAD819940}

Se non desideri che il robot di ricerca esegua ricerche per indicizzazione e indicizzazione dei file PDF, deseleziona il tipo di contenuto **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Puoi anche scegliere di utilizzare [!DNL URL Masks] per disabilitare l’indicizzazione PDF.

Consulta [Aggiunta di maschere URL per indicizzare o meno parti di indice di...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Per disabilitare l’indicizzazione PDF, immetti una delle seguenti maschere URL:

* `exclude *.pdf` (se non utilizzi espressioni regolari)
* `exclude regexp ^.*\.pdf$` (se utilizzi espressioni regolari)

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Perché non è possibile cercare i file PDF cinesi, giapponesi o coreani sul mio sito web? {#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8}

Ricerca nel sito/merchandising ottiene UTF-8 da file PDF senza indicazione di lingua. Se è stato selezionato il tipo di contenuto **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare la lingua utilizzata nel file PDF.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Troppe pagine {#reference_48A748BC1ED14844ACAC2735C8388E8A}

Una pagina delle domande frequenti che spiega alcuni dei motivi per cui l’indicizzatore ha conteggiato più pagine di quante ne abbiate effettivamente, e qual è la soluzione in ogni caso.

Se sei sicuro che il tuo sito web sia al di sotto del limite di pagina, ma l&#39;indicizzatore ti sta dicendo che il limite è raggiunto, dovresti esaminare queste domande comuni e le risposte per le possibili soluzioni.

* [Hai esaminato i tuoi vari registri dell&#39;indice?](#section_C929BF9FDA6B4C9A9078C45AFE80EFE8)
* [I programmi CGI vengono indicizzati sul tuo sito web?](#section_86ED8A641B3841EC80153B4F107548FD)
* [È abilitata la navigazione nelle directory nel server?](#section_073C88EEE74F4CA0AD2C7145D4810B22)
* [Ci sono forum o newsgroup sul tuo sito web?](#section_8DCB94F0850A41B9B2EA885F779E2F84)
* [Sul sito Web sono presenti file PDF o Microsoft Office...](#section_455FC5438DF74E68AB9A31D359EAD4D9)
* [Hai più punti di ingresso URL?](#section_8C54AFD7DF56472A9364D516482B534C)
* [Hai superato i byte interni o i limiti di tempo di...](#section_AE1BE61A58864FFE81F0BCEED2EBB15D)

## Hai esaminato i tuoi vari registri dell&#39;indice? {#section_C929BF9FDA6B4C9A9078C45AFE80EFE8}

Il registro dell&#39;indice contiene informazioni dettagliate raccolte dal robot di ricerca/merchandising del sito durante l&#39;indicizzazione del sito web. Il registro include un elenco di tutti i collegamenti sottoposti a ricerca per indicizzazione ed è stato rilevato un errore. L&#39;esame del registro degli indici è il punto migliore da cui iniziare quando si cerca di determinare quali pagine vengono indicizzate.

Vedere [Visualizzazione dell&#39;intero registro dell&#39;indice di una live o di una staging...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

Vedere [Visualizzazione del registro dell&#39;indice incrementale di una Live o Staged...](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

Vedere [Visualizzazione del registro dell&#39;indice incrementale script di un live o...](../c-about-index-menu/c-about-scripted-index.md#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7).

Vedere [Visualizzazione del registro dell&#39;indice rigenerato di un live o di una staging...](../c-about-index-menu/c-about-regenerate-index.md#task_61CE8F9E7BF84BA89A8D482B2106BB15).

Consulta [Visualizzazione del registro dell&#39;indice classificato di un sito web live o di staging](../c-about-index-menu/c-about-re-rank-index.md#task_3C76107DFAC1495FACD3ABB0A688208D).

## I programmi CGI vengono indicizzati sul tuo sito web? {#section_86ED8A641B3841EC80153B4F107548FD}

I programmi CGI utilizzano parametri URL che talvolta fanno sì che l’indicizzatore esegua la ricerca per indicizzazione di più URL &quot;falsi&quot;. Se la ricerca/merchandising del sito sta leggendo i tuoi programmi CGI e segue gli URL con parametri CGI, probabilmente ci sono diversi multipli di pagine che vengono sottoposte a ricerca per indicizzazione e indicizzate che non sono utili per il tuo indice di ricerca. I parametri CGI tipici compaiono negli URL con caratteri `?` o `&`.

Puoi impedire che i programmi CGI vengano indicizzati utilizzando la funzione URL Mask. Puoi mascherare un prefisso URL o utilizzare espressioni regolari per mascherare gli script CGI.

Consulta [Informazioni sulle maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Consulta [Informazioni sullo script delle maschere URL](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

Consulta [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## È abilitata la navigazione nelle directory nel server? {#section_073C88EEE74F4CA0AD2C7145D4810B22}

Quando un server web ha abilitato la navigazione nelle directory e non è presente alcun file index.html in una determinata directory, una visita a tale directory può mostrare l’elenco dei file presenti in tale directory. Di solito, ci sono collegamenti nella parte superiore della pagina per consentire di ordinare l’elenco in modi diversi semplicemente facendo clic su **[!UICONTROL Name]**, **[!UICONTROL Last modified]**, **[!UICONTROL Size]** e così via. In genere questi vengono visualizzati nel registro dell&#39;indice di ricerca/merchandising del sito come URL con caratteri come `?M=A` alla fine. L’indicizzatore di ricerca/merchandising del sito segue questi come collegamenti e questo può portare all’indicizzazione di più URL &quot;falsi&quot;.

In genere, un sito web ben progettato ha file di indice situati in ogni directory, o ha la navigazione della directory disabilitata per quelle directory senza file di indice. Fortunatamente, c&#39;è un modo semplice per mascherare questi &quot;falsi&quot; URL se non si è in grado di cambiare le pagine o disabilitare gli elenchi di directory sul lato server.

Per eseguire questa attività, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. Aggiungi una maschera per mascherare qualsiasi URL contenente il carattere `?`. Per eseguire questa operazione, immetti la seguente maschera di espressione regolare:

`exclude regexp ^.*\?.*$`

Dopo aver creato la maschera, assicurati di reindicizzare il sito web.

Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Ci sono forum o newsgroup sul tuo sito web? {#section_8DCB94F0850A41B9B2EA885F779E2F84}

Se sul sito Web viene effettuata la ricerca per indicizzazione di forum o newsgroup, è possibile che gli URL seguano per diverse opzioni di visualizzazione o di ordinamento. Questo comportamento significa che la stessa pagina viene indicizzata più volte.

In genere, i forum o i newsgroup sono dotati di motori di ricerca personalizzati. In tal caso, puoi utilizzare [!DNL URL Masks] per mascherare i forum da ricerca/merchandising del sito.

Dal menu del prodotto, fai clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. Nella pagina [!DNL Staged URL Masks] , maschera i forum inserendo i loro URL come maschere di esclusione URL.

Consulta [Aggiunta di maschere URL per indicizzare o meno parti di indice di...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Dopo aver creato le maschere, assicurati di reindicizzare il sito web.

Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Sul sito Web sono presenti file PDF o Microsoft Office? {#section_455FC5438DF74E68AB9A31D359EAD4D9}

Se sul tuo sito web sono presenti file PDF o [!DNL Microsoft Office] file, potresti notare che la dimensione dell&#39;indice di solo pochi file conta molte pagine. Il motivo per cui ci sono più pagine che vengono indicizzate dei documenti è perché ogni pagina in un file PDF o Microsoft Office viene conteggiata come pagina separata.

Dal menu del prodotto, fai clic su **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**. Nella pagina [!DNL Full Index] , seleziona **[!UICONTROL Count All Pages]**, quindi fai clic su **[!UICONTROL Full Index Now]** per visualizzare il conteggio totale delle pagine. Se non si desidera indicizzare i file PDF o Microsoft Office, è possibile disattivare questo tipo di contenuto in **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**.

Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Consulta [Informazioni sui tipi di contenuto](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Hai più punti di ingresso URL? {#section_8C54AFD7DF56472A9364D516482B534C}

Il robot di ricerca/merchandising del sito inizia a eseguire la ricerca per indicizzazione nei punti di ingresso dell&#39;URL specificato e segue tutti i collegamenti trovati a tutti i contenuti di quel particolare dominio. Se hai specificato molti punti di ingresso URL, è possibile che venga effettuata la ricerca per indicizzazione di un numero significativo di pagine.

Utilizza il tag `nofollow` del protocollo di esclusione robot nelle intestazioni dei documenti di ingresso sui domini aggiuntivi come segue:

```
<html> 
<head> 
<meta name="robots" content="nofollow"> 
</head>
```

Il codice di cui sopra comunica al robot di ricerca/merchandising del sito di indicizzare il contenuto della pagina, ma di non seguire i collegamenti a pagine aggiuntive.

Per ulteriori informazioni sui robot web e sul protocollo di esclusione robot, consulta:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

Se non hai accesso all’origine delle pagine su domini aggiuntivi, puoi rimuovere i diversi punti di ingresso URL. In questo modo puoi limitare l’attività di indicizzazione solo ai domini di cui desideri che i clienti siano in grado di effettuare ricerche nel contenuto.

Consulta [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Hai superato i byte interni o i limiti di tempo di ricerca/merchandising del sito? {#section_AE1BE61A58864FFE81F0BCEED2EBB15D}

Controlla se il tuo account ha raggiunto il suo limite nella schermata &quot;Full Index Status&quot; (Stato indice completo). Se lo stato segnala che l’indice è più grande del consentito o che ci è voluto più tempo del consentito, il sito web non è completamente indicizzato. È possibile correggere questo errore in modo da ottenere una copertura adeguata e il conteggio delle pagine del sito web.

Per proteggere i server di ricerca/merchandising del sito, esistono limiti interni di byte e tempo. Solo quando i file sottoposti a ricerca per indicizzazione sono molto grandi o quando il server che la ricerca/merchandising del sito sta cercando di raggiungere è lento sono questi limiti raggiunti.

Se raggiungi un limite di tempo, assicurati che il server sia online e riprova in un secondo momento. Se raggiungi un limite di byte, controlla i file sottoposti a ricerca per indicizzazione visualizzando il registro dell&#39;indice. Sono insolitamente grandi? Contatta il supporto tecnico se viene visualizzato uno di questi messaggi.
