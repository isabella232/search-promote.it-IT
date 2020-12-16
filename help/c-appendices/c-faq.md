---
description: nulle
seo-description: nulle
seo-title: Domande frequenti
solution: Target
title: Domande frequenti
topic: Appendices,Site search and merchandising
uuid: 4ce454a4-e770-4587-91a0-a25491818ac6
translation-type: tm+mt
source-git-commit: 4270ea66ba645ad0f71c9c8b5c2a1fcc6eb02ad2
workflow-type: tm+mt
source-wordcount: '8639'
ht-degree: 0%

---


# Domande frequenti{#frequently-asked-questions}

## Flash Adobe  {#reference_4A25BBDE32214AF5A1A454F38FD51243}

Pagina delle domande frequenti in cui viene illustrato il supporto dell’indicizzazione e della ricerca di file SWF in un sito Web.

Di seguito sono riportati alcuni quesiti comuni relativi ai file SWF:

* [Quando si esegue la ricerca per indicizzazione e la ricerca per indicizzazione di un file SWF?](#section_01BB5259140D4D5FB04CCB7A1A63DE99)
* [Cosa devo fare per indicizzare un SWF...](#section_0A6A52CC70D4495BBE14D91906318F95)
* [Come vengono riconosciuti i file SWF?](#section_B36C0536AB544F509601DC6A11A8E656)
* [Come vengono indicizzati i file SWF?](#section_36856058A4B54FA5ABF921344F50410C)
* [Un file SWF viene conteggiato come pagina?](#section_0158D6DE70BC40D78E2374787B9F58AB)
* [Come posso impedire l&#39;indicizzazione di singoli file SWF?](#section_E38AD37989EF410B97AF5125057BFD22)
* [Come posso evitare che i file SWF vengano indicizzati in...](#section_DF2606A50E9A44859CFA0D44D7C5F2E4)
* [Com&#39;è possibile che non sia possibile effettuare ricerche nei file SWF cinesi, giapponesi o coreani sul sito Web?](#section_EE1A3A705AE74148BD195A0CE513A5C4)

## Quando si esegue la ricerca per indicizzazione e la ricerca per indicizzazione di un file SWF? {#section_01BB5259140D4D5FB04CCB7A1A63DE99}

Un file SWF viene sottoposto a ricerca per indicizzazione e indicizzazione se è contenuto in un tag embed o object in una pagina HTML, come nell&#39;esempio seguente:

```
<embed src="Flash-file-URL">  
 
<object>  
<param name=movie value="Flash-file-URL">  
</object> 
```

Un file SWF viene riconosciuto anche se l’URL del file è elencato come punto di ingresso.

Consultate [Aggiunta di più punti di immissione URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Cosa devo fare per indicizzare un file SWF? {#section_0A6A52CC70D4495BBE14D91906318F95}

Per eseguire ricerche per indicizzazione e indicizzare i file SWF, selezionare il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Fintanto che al file di Flash viene fatto riferimento da un tag `<embed>` o `<object>` in un documento HTML, il testo viene indicizzato e tutti gli URL elencati nel file vengono sottoposti a ricerca per indicizzazione.

Se al file non viene fatto riferimento da un tag `<embed>` o `<object>`, è possibile elencare il file SWF in un tag `<a href=...>` in un documento HTML o come punto di ingresso dell&#39;URL.

Consultate [Aggiunta di più punti di immissione URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Come vengono riconosciuti i file SWF? {#section_B36C0536AB544F509601DC6A11A8E656}

I file SWF sono identificati dal seguente tipo MIME:

`application/x-shockwave-flash`

I file SWF vengono riconosciuti anche con i tipi `application/octet-stream`&quot; o `text/plain` MIME, a condizione che l&#39;estensione del file sia .swf.

Un server non configurato correttamente potrebbe utilizzare un tipo MIME diverso per i file SWF. Accertatevi di controllare la configurazione del server in caso di problemi di ricerca per indicizzazione e indicizzazione dei file SWF.

## Come vengono indicizzati i file SWF? {#section_36856058A4B54FA5ABF921344F50410C}

Il testo contenuto in un file SWF è indicizzato come se fosse `<body>` testo nella pagina HTML di inclusione. Se un risultato della ricerca trova testo contenuto in un file SWF incorporato, il risultato effettivamente collega alla pagina HTML di cui fa parte e non al file SWF. In questo modo, il file SWF viene visualizzato nel contesto corretto.

Se un file SWF contiene un URL come azione &quot;Carica filmato&quot;, il testo nel file SWF a cui viene fatto riferimento viene indicizzato come parte della pagina HTML di cui fa riferimento.

Se un file SWF contiene un URL come azione &quot;Ottieni URL&quot;, l&#39;URL viene sottoposto a ricerca per indicizzazione e viene quindi indicizzato, proprio come un riferimento HTML `<a href=...>` viene sottoposto a ricerca per indicizzazione in un secondo momento.

Se un file SWF è elencato come punto di ingresso URL, il testo del file SWF viene indicizzato come una singola pagina. Un risultato di ricerca che trova testo da un collegamento SWF punto di ingresso direttamente al filmato, non a una pagina HTML di inclusione.

Consultate [Aggiunta di più punti di immissione URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Un file SWF viene conteggiato come pagina? {#section_0158D6DE70BC40D78E2374787B9F58AB}

No. Un file SWF è considerato parte della relativa pagina HTML di inclusione. Tutti gli URL &quot;Carica filmato&quot; contenuti nei file SWF sono considerati anche parte della pagina HTML di inclusione. Pertanto, i file SWF a cui viene fatto riferimento da una pagina HTML non vengono conteggiati come &quot;pagina&quot; per il totale di pagina dell&#39;account.

Se un file SWF è elencato come punto di ingresso dell&#39;URL, tale file SWF e tutti gli URL &quot;Carica filmato&quot; elencati in tale file SWF vengono conteggiati come una &quot;pagina&quot; per il totale della pagina dell&#39;account.

## Come posso impedire l&#39;indicizzazione di singoli file SWF? {#section_E38AD37989EF410B97AF5125057BFD22}

Per impedire l&#39;indicizzazione di un file SWF, è possibile aggiungere al documento HTML che lo contiene un tag meta robot ( `<meta name="ROBOTS" content="NOINDEX">`) o un tag `<noindex>`. ovvero il documento contenente il tag `<embed>` o `<object>`.

È inoltre possibile utilizzare il tag meta robot ( `<meta name="ROBOTS" content="NOFOLLOW">`) per impedire i seguenti URL contenuti nel file SWF. Se il documento HTML di cui fa parte è disattivato, le azioni &quot;Ottieni URL&quot; elencate nel file SWF non vengono seguite.

## Come posso impedire che i file SWF vengano indicizzati sul mio sito Web? {#section_DF2606A50E9A44859CFA0D44D7C5F2E4}

Per disattivare l&#39;indicizzazione SWF, deselezionare il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Potete anche scegliere di utilizzare [!DNL URL Masks] per disattivare l&#39;indicizzazione dei file SWF.

Consultate [Aggiunta di maschere URL per indicizzare o meno parti indice di...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Per disattivare l’indicizzazione SWF, immettete una delle seguenti maschere URL:

* `exclude *.swf` (se non si utilizzano espressioni regolari)
* `exclude regexp ^.*\.swf$` (se utilizzate espressioni regolari)

Vedere [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Com&#39;è possibile che non sia possibile effettuare ricerche nei file SWF cinesi, giapponesi o coreani sul sito Web? {#section_EE1A3A705AE74148BD195A0CE513A5C4}

Ricerca nel sito/merchandising ottiene UTF-8 dai file SWF creati con  Flash di Adobe. L&#39;UTF-8 non contiene alcuna indicazione di lingua. Se è stato selezionato il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare la lingua utilizzata dal file SWF.

Vedere [Aggiunta di definizioni di inserimento di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

I file SWF precedenti non specificano neanche un set di caratteri. Se è stato selezionato il tipo di contenuto SWF **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare i metadati Iniezioni per specificare il set di caratteri utilizzato nel file SWF.

## Ricerca generale {#reference_E2C675162789452A9B99C6633B12CBEF}

Pagina delle domande frequenti in cui viene illustrato come la ricerca/merchandising dei siti consente ai clienti che visitano il sito Web di trovare ciò che cercano.

Di seguito sono riportate le domande comuni relative alla ricerca generale:

* [È necessario installare un software per utilizzare il sito?...](#section_02AB2AFF71984F9DAA3AF2B7C0847A22)
* [Cosa accade quando il sito supera il limite di pagine?](#section_ECA5FA01032D4322BABA4E2C7FE498C1)
* [Come si modifica l&#39;indirizzo e-mail in cui la settimana...](#section_AE27F63DD13F425B940C8E7D9ED5C614)
* [Quanto sono sicure le informazioni dei clienti sulla ricerca/merchandising sul sito?](#section_5484CB954167412BB7F0480CB0C504B8)
* [E la privacy delle informazioni sui clienti?](#section_8FB493F15E51454BA92A0C83E14C0CC7)
* [Posso mostrare i miei banner pubblicitari nella ricerca...](#section_611EB8B32C16418386CB7DC7FB6954B8)

Di seguito sono riportate alcune domande comuni sulle funzioni di ricerca:

* [È possibile personalizzare i risultati della ricerca per il sito?](#section_A64B3A621B794DF78D35ED06D9C43D0B)
* [Posso vedere quali clienti stanno cercando sul mio...](#section_73709E1B0E82478DA7B4D15B6C845F33)
* [Come è possibile controllare quali tipi di contenuto (PDF, testo, Flash, MP3 e Microsoft Office) vengono indicizzati e sottoposti a ricerca?](#section_0AB8CB4B6BFA4286AA082055FEBFBE1C)
* [Le pagine Web generate in modo dinamico tramite contenuti basati su ASP, JSP, PHP, CFM o Perl sono supportate?](#section_E279F004F1C542A2B9773B832E7B013F)
* [Come posso utilizzare i sinonimi per migliorare i risultati della ricerca...](#section_E6E36E12514F4D7BAB01F8D1AB61D57B)
* [Posso controllare l&#39;ordine dei risultati della ricerca?](#section_C6361048502745779D9749A842C4C370)
* [Posso cambiare la lingua della pagina dei risultati della ricerca...](#section_6EE41DA8241247D48BBEB061A50599C5)
* [Posso avere più siti nel mio Adobe ...](#section_AFA8825182094660A71EEC84B8329D6D)
* [È possibile eseguire la ricerca in più di un dominio?](#section_BFBB0E9861D942F095B56CF0A8F16596)
* [Posso suddividere il mio sito in sezioni separate in modo che...](#section_52153A9DE9F9493B967A70583848B2A4)
* [Come posso escludere parti del mio sito Web dall&#39;essere...](#section_D452EDE153654EF398F4A87780C6D43B)
* [Quali set di caratteri sono supportati?](#section_A62A6F8F15804F968C77F2DEBDE8F8FD)
* [Cosa succede se si modifica o si aggiorna il sito Web?](#section_489050E0EBC14D0594DBBAA0CCF4F6BA)
* [Il sito può essere indicizzato automaticamente?](#section_9C7D41636238488691ECDFEE4D4E5103)
* [Io uso delle password sul mio sito web. È ancora possibile utilizzare la ricerca/merchandising del sito?](#section_4618EB5B66704640B5502D1B5CB4B32E)
* [Supportate la ricerca per indicizzazione e l&#39;indicizzazione di https o...](#section_D5BB8B8FBEA4405583E86B4AEC37151B)
* [Il sito Web di ricerca/merchandising rispetta il file robots.txt?](#section_73BBF6FE93C64C109F45CBC2FA394DB2)
* [Alcune parti del mio sito Web devono essere aggiornate frequentemente in modo che...](#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3)
* [È possibile utilizzare script o programmi per avviare un&#39;operazione incrementale...](#section_0B6BB039557A42AA876D35D748E17DD0)

## È necessario installare un software per utilizzare la ricerca/merchandising del sito? {#section_02AB2AFF71984F9DAA3AF2B7C0847A22}

No. Questo è il vantaggio principale della ricerca/merchandising del sito. Il motore è un&#39;applicazione professionale ospitata e mantenuta interamente sui nostri server ad alte prestazioni. Questo rende il software più facile da usare di altre soluzioni di ricerca. L’unica cosa da fare è aggiungere una piccola quantità di codice HTML alle pagine in modo che i clienti del sito Web possano inserire delle ricerche. Ricerca nel sito/merchandising si prende cura di tutto il resto.

## Cosa succede quando il sito supera il limite di pagine? {#section_ECA5FA01032D4322BABA4E2C7FE498C1}

Continuiamo a servire le tue ricerche in modo che i visitatori possano cercare il tuo sito Web senza interruzioni. Per verificare se il sito Web supera il limite di pagine, controlla il tuo stato Indice completo o Registro dal vivo.

Vedere [Informazioni sull&#39;indice completo](../c-about-index-menu/c-about-full-index.md#concept_C69BD21863FD4856B49326F35DB570D3).

Vedere [Visualizzazione dell&#39;intero registro di indice di un live o di uno stage...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

## Come posso cambiare l&#39;indirizzo e-mail in cui vengono inviati i rapporti settimanali? {#section_AE27F63DD13F425B940C8E7D9ED5C614}

I rapporti settimanali vengono inviati al proprietario di ciascun account attivo. Per modificare l&#39;indirizzo e-mail, fare clic su **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**. Se disponete di più account di ricerca attivi, tutte le newsletter vengono inviate al nuovo indirizzo.

Vedere [Configurazione delle informazioni personali dell&#39;utente](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

## Quanto sono sicure le informazioni del cliente sulla ricerca del sito/merchandising? {#section_5484CB954167412BB7F0480CB0C504B8}

Ricerca e merchandising sul sito sono sicuri, veloci, stabili e facili da usare. Non sei obbligato a utilizzare i cookie (anche se puoi farlo se vuoi) per i nostri prodotti, e le informazioni riservate, come le password, non vengono mai messe su alcun collegamento URL che possa essere successivamente recuperato dal tuo browser.

## E la privacy delle informazioni sui clienti? {#section_8FB493F15E51454BA92A0C83E14C0CC7}

 Adobe si impegna a rispettare la privacy dei propri clienti e visitatori. Vedere l&#39;Adobe  [Centro per la privacy](https://www.adobe.com/privacy.html).

## Posso mostrare i miei banner pubblicitari sulle pagine dei risultati della ricerca? {#section_611EB8B32C16418386CB7DC7FB6954B8}

Sì. Potete controllare l’aspetto e il contenuto dei risultati della ricerca. All’interno del modello di risultati della ricerca per il sito Web, potete creare collegamenti alla vostra rete di scambio banner, ad esempio LinkExchange o SmartClicks. Eventuali hit effettuati dai visitatori vengono correttamente accreditati sul vostro account di scambio banner.

## È possibile personalizzare i risultati della ricerca per il sito? {#section_A64B3A621B794DF78D35ED06D9C43D0B}

Sì. Questa è una funzione esclusiva di ricerca del sito/merchandising. Grazie alla nostra tecnologia avanzata per i modelli e alla poca conoscenza di HTML, potete controllare esattamente come vengono visualizzati i risultati della ricerca.

Vedere [Cerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

La transizione tra i propri server e i server di ricerca/merchandising del sito è completamente invisibile per i clienti. Se non conoscete l’HTML o non avete il tempo di creare un modello personalizzato, potete scegliere tra un assortimento di modelli attraenti e pronti all’uso che  Adobe  team interno di sviluppatori Web professionisti.

## Posso vedere quali clienti stanno cercando sul mio sito? {#section_73709E1B0E82478DA7B4D15B6C845F33}

Sì. Teniamo le statistiche di ricerca per le ricerche effettuate dai visitatori sul tuo sito Web negli ultimi due mesi. Potete esaminare queste statistiche in qualsiasi momento in Rapporti nel menu del prodotto. I rapporti di ricerca forniscono informazioni vitali riguardo esattamente ciò che i visitatori cercano sul sito Web. Potete utilizzare queste informazioni per migliorare la progettazione o per ottimizzare il motore di ricerca/merchandising del sito in modo da soddisfare meglio i visitatori.

## Come è possibile controllare quali tipi di contenuto (PDF, testo, Flash, MP3 e Microsoft Office) vengono indicizzati e cercati? {#section_0AB8CB4B6BFA4286AA082055FEBFBE1C}

È possibile configurare facilmente gli account per attivare o disattivare l&#39;indicizzazione e la ricerca del testo contenuto nei documenti PDF, nei documenti di testo normale, nei filmati di Flash, nei file MP3 o nei documenti di Microsoft Office.

Queste impostazioni sono controllate sulla pagina [!DNL Staged Content Types].

Vedere [Informazioni sui tipi di contenuto](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Sono supportate pagine Web generate dinamicamente tramite contenuti basati su ASP, JSP, PHP, CFM o Perl? {#section_E279F004F1C542A2B9773B832E7B013F}

Le pagine Web HTML statiche o generate dinamicamente sono indicizzate, comprese le pagine create da database o qualsiasi altro processo back-end. Poiché il codice HTML visualizzato da un browser è indicizzato, potete utilizzare la ricerca nel sito/merchandising sui siti Web purché queste architetture back-end producano risultati in pagine HTML.

Il robot di ricerca passa per il sito Web iniziando dalla prima pagina all&#39;indirizzo del sito Web specificato in [!DNL Account Settings], e segue i collegamenti da una pagina all&#39;altra.

Consultate [Configurazione delle impostazioni dell&#39;account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Quando il robot di ricerca si aggancia e indicizza tutte le pagine del tuo sito web, puoi usare il motore di ricerca per cercare il tuo sito. In altre parole, se nel sito Web sono collegati documenti generati dinamicamente con collegamenti provenienti da altre pagine, il robot di ricerca può comunque eseguire ricerche per indicizzazione e indicizzare il contenuto dinamico.

Una volta che il contenuto del sito Web è sottoposto a ricerca per indicizzazione e ricerca per indicizzazione, i clienti possono cercare informazioni all’interno del contenuto indicizzato.

## Come posso utilizzare i sinonimi per migliorare i risultati della ricerca per il mio sito? {#section_E6E36E12514F4D7BAB01F8D1AB61D57B}

È possibile utilizzare i sinonimi quando si desidera che i visitatori trovino pagine correlate alla query di ricerca.

Ad esempio, supponete di avere una pagina contenente un listino prezzi dei prodotti in vendita sul sito. Tuttavia, dopo aver esaminato i report di ricerca forniti dalla ricerca del sito/merchandising, si scopre che i clienti cercano nella ricerca la parola &quot;costo&quot;, &quot;spesa&quot;, &quot;addebito&quot; o &quot;tassa&quot;. Queste parole non visualizzano la pagina del listino prezzi nei risultati della ricerca. Con la funzione [!DNL Add Synonyms] in [!DNL Dictionaries], è possibile specificare che queste parole sono tutti sinonimi e che il cliente può trovare il proprio listino prezzi, indipendentemente dal termine utilizzato.

Vedere [Informazioni sui dizionari](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034).

## Posso controllare l&#39;ordine dei risultati della ricerca? {#section_C6361048502745779D9749A842C4C370}

Sì. Utilizzando l&#39;interfaccia di rilevanza avanzata, è possibile controllare le pagine restituite per una specifica query di ricerca. Questa funzione è utile se desiderate essere certi che i clienti visualizzino una pagina specifica quando effettuano una query per determinate parole.

Vedere [Aggiunta di un nuovo campo tag meta](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## È possibile modificare la lingua della pagina dei risultati della ricerca? {#section_6EE41DA8241247D48BBEB061A50599C5}

Sì. Il modello di ricerca del sito/merchandising è flessibile quando si tratta di consentire di creare una pagina di risultati che utilizza la lingua desiderata e che corrisponde all’aspetto del sito Web.

Il modello è costituito da una combinazione di testo, tag HTML standard e tag speciali definiti per visualizzare i risultati della ricerca. Quando un cliente esegue una ricerca, il robot di ricerca legge il modello, genera il testo utilizzando tag HTML standard e inserisce i collegamenti dei risultati in base ai tag modello speciali.

Vedere [Cerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Se desiderate modificare la lingua dei risultati, potete modificare il testo in inglese che appare sul modello.

Vedere [Modifica di una presentazione o di un modello di trasporto](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).

## Posso avere più di un sito sul mio  Adobe Customer Login? {#section_AFA8825182094660A71EEC84B8329D6D}

Sì. Con un singolo accesso  Adobe al cliente, potete gestire un motore di ricerca diverso per molti siti Web diversi. Seleziona e gestisci gli account in &quot;Account&quot;.

Vedere [Selezione di un account diverso da utilizzare](../c-about-accounts-menu.md#task_03C0FE918E2D44529CDC3B8DB75D1B26).

## Posso eseguire la ricerca in più domini? {#section_BFBB0E9861D942F095B56CF0A8F16596}

Sì. È possibile configurare l&#39;accesso a più domini utilizzando [!DNL URL Entrypoints]. Immetti i punti di ingresso URL per altri domini di tua proprietà. Ricorda che devi disporre dell&#39;autorizzazione per indicizzare domini che non possiedi.

Consultate [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## È possibile suddividere il sito in sezioni distinte in modo che i clienti possano eseguire una ricerca in una di queste aree singolarmente o in tutto il sito? {#section_52153A9DE9F9493B967A70583848B2A4}

Sì. È inclusa una funzione &quot;Raccolte&quot; che consente ai clienti di cercare aree specifiche del sito Web per trovare rapidamente ciò che stanno cercando.

Vedere [Informazioni sulle raccolte](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127).

Ad esempio, i clienti possono cercare una raccolta di URL relativi alle informazioni di vendita del prodotto o una raccolta di URL relativi ai servizi di supporto. Potete impostare le raccolte in modo che i clienti visualizzino un elenco a discesa di raccolte o un gruppo di caselle di controllo.

## Come si esclude la ricerca di parti del sito Web? {#section_D452EDE153654EF398F4A87780C6D43B}

Sì. Specificate le maschere URL per determinare quali pagine Web includere o escludere dall’indicizzazione. Le maschere URL determinano se nei risultati di ricerca vengono visualizzate le pagine del sito Web.

Consultate [Le maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Vedere [Lo script delle maschere URL](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

Per impedire la ricerca di parti di singole pagine Web, è possibile escludere parti di una pagina dall’indicizzazione. Circondare il testo con i tag `<noindex>` e `</noindex>`. Questo metodo è utile per escludere il testo di navigazione dalle ricerche.

## Quali set di caratteri sono supportati? {#section_A62A6F8F15804F968C77F2DEBDE8F8FD}

Le pagine Web in genere specificano il set di caratteri con un tag meta simile al seguente:

`<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-1">`

Il motore di ricerca del sito/merchandising indicizza correttamente le pagine Web utilizzando tutti i set di caratteri comuni attualmente in uso su Internet. Alcuni dei set di caratteri supportati includono quanto segue:

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
   <td colname="col1"> <p>Cinese (semplificato; EUC-CN) </p> </td> 
   <td colname="col2"> <p>Giapponese (EUC-JP) </p> </td> 
   <td colname="col3"> <p>Europa occidentale (ISO-8859-15) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cinese (semplificato; GB2312) </p> </td> 
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

Per informazioni sui set di caratteri non elencati sopra, contattate il supporto tecnico.

## Cosa succede se si modifica o si aggiorna il sito Web? {#section_489050E0EBC14D0594DBBAA0CCF4F6BA}

Dopo aver modificato il contenuto del sito Web, potete eseguire un indice completo o un indice incrementale. Consente di scaricare e indicizzare i contenuti dei siti Web modificati mediante la ricerca nel sito/merchandising. Al termine dell’indicizzazione, i clienti possono effettuare ricerche nel nuovo contenuto. Potete anche pianificare un&#39;indicizzazione automatica del sito in un determinato momento e in un giorno specifico.

Vedere [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Vedere [Esecuzione di un indice incrementale di un sito Web live o in fase...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

Vedere [Impostazione della pianificazione dell&#39;indice completa per un sito Web live](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

Vedere [Impostazione della pianificazione incrementale dell&#39;indice per un sito Web live](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## È possibile indicizzare automaticamente il sito? {#section_9C7D41636238488691ECDFEE4D4E5103}

Sì. Potete pianificare un indice automatico del sito ogni giorno.

Oltre all&#39;indicizzazione automatica giornaliera, è possibile scegliere di aver modificato frequentemente porzioni del sito indicizzate in modo incrementale. Nei giorni in cui è pianificato un indice automatico, potete controllare l&#39;ora del giorno in cui ha luogo l&#39;indice. Inoltre, potete sempre avviare manualmente un indice del sito ogni volta che lo desiderate.

Vedere [Impostazione della pianificazione dell&#39;indice completa per un sito Web live](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

Vedere [Impostazione della pianificazione incrementale dell&#39;indice per un sito Web live](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Io uso delle password sul mio sito web. Posso ancora utilizzare la ricerca nel sito/merchandising? {#section_4618EB5B66704640B5502D1B5CB4B32E}

Se utilizzate l&#39;autenticazione di base HTTP per proteggere con password determinate porzioni del sito Web, potete specificare aree di autenticazione e password che la ricerca o il merchandising del sito possono utilizzare per indicizzare il sito.

Vedere [Aggiunta di password per l&#39;accesso alle aree del sito Web che richiedono...](../c-about-settings-menu/c-about-crawling-menu.md#task_DED19D476FF04B48BB6456D5ECB8628A).

## Supportate la ricerca per indicizzazione e l&#39;indicizzazione di https o contenuto server protetto? {#section_D5BB8B8FBEA4405583E86B4AEC37151B}

Sì. È possibile eseguire ricerche per indicizzazione e indicizzazione del contenuto sui server protetti (https).

## La ricerca del sito/merchandising rispetta il file robots.txt sul mio sito Web? {#section_73BBF6FE93C64C109F45CBC2FA394DB2}

Sì. Il protocollo di esclusione dei robot è conforme. Il robot di ricerca esamina il file robots.txt se è presente sul vostro sito web. Se il file robots.txt esclude tutti i robot dalla ricerca per indicizzazione del sito, viene escluso anche il robot di ricerca/merchandising del sito. Per consentire solo al robot di ricerca del sito/merchandising di eseguire la ricerca per indicizzazione del sito, impostate il contenuto del file robots.txt su quanto segue:

```
User-agent: Atomz/1.0 
Disallow:
```

```
User-agent: * 
Disallow: /
```

Per ulteriori informazioni sui robot web e sul protocollo di esclusione dei robot, consulta:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

## Alcune parti del mio sito Web devono essere aggiornate frequentemente in modo che i miei clienti ottengano i risultati di ricerca più precisi. L&#39;indicizzazione incrementale è utile in questo caso? {#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3}

Sì. Questo scenario è il risultato della funzione di indicizzazione incrementale creata per facilitare la ricerca nel sito/merchandising. Il vantaggio principale dell&#39;indicizzazione incrementale è che consente alle aziende di indicizzare frequentemente parti del sito Web che cambiano dinamicamente. Questa funzionalità assicura che i risultati della ricerca vengano visualizzati con precisione &quot;fino al minuto&quot;.

Vedere [Esecuzione di un indice incrementale di un sito Web live o in fase...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

Vedere [Impostazione della pianificazione incrementale dell&#39;indice per un sito Web live](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Le pagine Web generate dinamicamente sono supportate da un database back-end, come cataloghi di prodotti o sistemi di gestione delle scorte? {#section_26896C556483457E879785E751583B16}

Le pagine Web HTML statiche o generate dinamicamente, incluse le pagine create da database o qualsiasi altro processo back-end, sono indicizzate. Poiché il codice HTML, visualizzato da un browser, è indicizzato, potete utilizzare la ricerca nel sito/merchandising sui siti Web purché le informazioni del database di back-end si traducano in pagine HTML.

Il robot di ricerca passa per il sito Web iniziando dalla prima pagina all&#39;indirizzo del sito Web specificato in [!DNL Account Settings], e segue i collegamenti da una pagina all&#39;altra.

Consultate [Configurazione delle impostazioni dell&#39;account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Quando il robot di ricerca si aggancia e indicizza tutte le pagine del tuo sito web, puoi usare il motore di ricerca per cercare il tuo sito. In altre parole, se nel sito Web sono collegati documenti generati dinamicamente con collegamenti provenienti da altre pagine, il robot di ricerca può comunque eseguire ricerche per indicizzazione e indicizzare il contenuto del database dinamico.

Una volta che il contenuto del sito Web è sottoposto a ricerca per indicizzazione e ricerca per indicizzazione, i clienti possono cercare informazioni all’interno del contenuto indicizzato.

Potete facilmente abilitare la ricerca per contenuti completi o una ricerca basata su argomenti più ristretta, limitata alle informazioni contenute nel titolo, nella meta-descrizione, nei tag del documento delle parole chiave meta o in tutti e tre i tag. Utilizzando le definizioni dei metadati, potete anche creare campi di visualizzazione personalizzati, come un&#39;immagine di prodotto, nei risultati effettivi della ricerca.

Vedere [Aggiunta di un nuovo campo tag meta](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## È possibile utilizzare script o programmi per avviare un indice incrementale del sito? {#section_0B6BB039557A42AA876D35D748E17DD0}

Sì. È possibile utilizzare script o programmi per avviare un indice incrementale del sito Web, nonché per eseguire il ping dei server per indicizzare il sito ogni volta che il contenuto viene modificato o aggiornato.

Vedere [Informazioni sull&#39;indice con script](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D).

## Implementazioni delle funzioni {#reference_2D0C4A80B8D64051BA9694D562DCE663}

Una pagina di domande frequenti che illustra le diverse implementazioni delle funzioni in [!DNL Search&Promote].

Seguono alcune domande comuni relative alle implementazioni di funzionalità in [!DNL Search&Promote] su un sito Web:

* [Perché le mie regole aziendali non sono in esecuzione?](#section_7FEB60383D8A4B11A60DFF9067274699)
* [Perché si verificano problemi durante la programmazione dell&#39;indicizzazione, errori durante l&#39;avvio dell&#39;indicizzazione e problemi durante l&#39;avvio dell&#39;indicizzazione in fase?](#section_E05758193DF5436784B0145839989F75)
* [Il limite di dimensione dell&#39;indice supera il limite consentito. Perché sta accadendo e come lo riparo?](#section_12E7DA979C4C4B1D8A3A6415FC3DDA70)

## Perché le mie regole aziendali non sono in esecuzione? {#section_7FEB60383D8A4B11A60DFF9067274699}

Configurate le regole di business quando vengono visualizzati i banner o per determinare quali risultati vengono visualizzati e in quale ordine. Potete anche configurare la posizione di un elemento nel facet e il modello da usare per una determinata ricerca.
Riordinate le regole business per modificare l&#39;ordine in cui vengono eseguite sui modelli di presentazione. Le regole aziendali vengono eseguite nell&#39;ordine in cui sono state definite; ossia, più alto è il numero dell&#39;ordine di una regola, più tardi verrà eseguito nel processo, superando le regole precedenti. Riordinare le regole immettendo un nuovo numero nella colonna Ordine della tabella nella pagina Regole business.

Vedere [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Perché si verificano problemi durante la programmazione dell&#39;indicizzazione, errori durante l&#39;avvio dell&#39;indicizzazione e problemi durante l&#39;avvio dell&#39;indicizzazione in fase? {#section_E05758193DF5436784B0145839989F75}

Quando si genera un indice, pieno o incrementale, le informazioni sullo stato di ricerca per indicizzazione vengono visualizzate in tempo reale. Ad esempio, potete visualizzare il tempo di inizio, il tempo trascorso e tutti gli errori che si sono verificati durante il processo di indicizzazione. Vengono visualizzate anche informazioni sullo stato dell&#39;ultimo indice. Utilizzate queste informazioni per risolvere eventuali errori di indicizzazione riscontrati.

Per pianificare un indice, vedere [Impostazione della pianificazione dell&#39;indice completo per un sito Web live](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0) e [Impostazione della pianificazione dell&#39;indice incrementale per un sito Web live](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

Per iniziare un indice in fase, vedere [Esecuzione di un indice completo di un sito Web attivo o in fase...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D) o [Esecuzione di un indice incrementale di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Il limite di dimensione dell&#39;indice supera il limite consentito. Perché sta accadendo e come lo riparo? {#section_12E7DA979C4C4B1D8A3A6415FC3DDA70}

Un sito Web può tendere a crescere e nel tempo &quot;scopre&quot; più documenti e pagine Web che sono stati aggiunti. Alla fine, il tuo account potrebbe superare il limite di dimensioni di indicizzazione. In questi casi, puoi prendere in considerazione l&#39;utilizzo di **[!UICONTROL URL Mask]**. Questa funzione consente di nascondere documenti e pagine Web dalla ricerca per indicizzazione che non si desidera o non è necessario includere nell&#39;indice, riducendo così la dimensione dell&#39;indice. Un&#39;altra opzione potrebbe consistere nel contattare il supporto tecnico per impostare il limite di dimensioni di indicizzazione su un valore maggiore nell&#39;account.

Consultate [Le maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Se non sai cosa fare, contatta il supporto tecnico. Possono essere presenti molte altre variabili che influiscono sulla dimensione dell&#39;indice e che, se modificate, possono anche influenzare la fatturazione dell&#39;account.

## Internazionale {#reference_F017C2968BFB446499EF1D3CE2CAC0FE}

Una pagina di domande frequenti che illustra il supporto dell’indicizzazione e della ricerca di più di 19 lingue, incluse le lingue asiatiche multibyte come cinese (semplificato e tradizionale), giapponese e coreano.

Di seguito sono riportate le domande comuni relative alle lingue e ai set di caratteri:

* [Controllo della codifica del set di caratteri della query di ricerca in corso...](#section_DF2E8570AFC2480FA199FD26C941A22F)
* [Sono ricercate solo pagine la cui codifica corrisponde alla codifica di...](#section_9E544F3DB7DE41618DC1BC8224B32C5A)
* [Quale codifica viene utilizzata per la pagina dei risultati della ricerca?](#section_DA68670F35D54EAABF7DBB010F4409BF)
* [È possibile utilizzare la ricerca del sito/merchandising su pagine codificate Unicode, UTF-8?](#section_130997CB08934A13A5261D85CF88040C)
* [Com&#39;è possibile che non sia possibile effettuare ricerche nei file PDF cinesi, giapponesi o coreani sul sito Web?](#section_539AFF482F814D28B5929F683D2F2175)
* [Com&#39;è possibile che non sia possibile effettuare ricerche nei file SWF cinesi, giapponesi o coreani sul sito Web?](#section_9C0849528AFF4C10AA97A2C912992638)
* [Com&#39;è possibile che non sia possibile effettuare ricerche nei file Microsoft Office cinesi, giapponesi o coreani sul sito Web?](#section_6764BA6863AF492EBA9BE5CCC12CDD1F)
* [Com&#39;è possibile che non sia possibile effettuare ricerche nei file MP3 cinesi, giapponesi o coreani sul sito Web?](#section_DB6D60CF46F94125BF4E54AF3036DBFC)
* [Devo fare qualcosa di speciale per...](#section_A8BA6DDD3A6048319D3530BCFD6DA1A5)
* [Com&#39;è possibile che i font cinesi, giapponesi o coreani vengano visualizzati nei risultati di ricerca in Netscape 4.7 e versioni precedenti?](#section_DF42567063304F918D406AC76529DFB7)

## Cosa controlla la codifica del set di caratteri della query di ricerca? {#section_DF2E8570AFC2480FA199FD26C941A22F}

La sezione &quot;Moduli Web&quot; dell&#39;account di ricerca contiene moduli di ricerca di esempio che consentono di aggiungere funzionalità di ricerca al sito Web. Se si guarda questo codice dei moduli di ricerca, è possibile trovare una riga simile alla seguente:

`<input type=hidden name="sp_f" value="iso-8859-1">`

Questa riga di codice indica al motore di ricerca che la query in entrata è codificata in iso-8859-1, una codifica comune per le lingue dell&#39;Europa occidentale. Per modificare questa impostazione, vai al menu prodotto e fai clic su **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**. Nella pagina [!DNL Personal Information], nell&#39;elenco a discesa **[!UICONTROL Character Encoding]**, selezionare una nuova codifica.

Vedere [Configurazione delle informazioni personali dell&#39;utente](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

È inoltre possibile modificare manualmente il valore di codifica nelle pagine Web modificando la riga `sp_f` del modulo di ricerca. Tenere presente che il valore `sp_f` del modulo di ricerca deve corrispondere alla codifica set di caratteri della pagina in cui viene visualizzato.

## Vengono cercate solo le pagine la cui codifica corrisponde alla codifica della query di ricerca? {#section_9E544F3DB7DE41618DC1BC8224B32C5A}

Per impostazione predefinita, no. Fintanto che le pagine del sito Web identificano correttamente la codifica del set di caratteri, vengono effettuate le conversioni necessarie tra la codifica della query di ricerca e quella delle pagine, anche quando le pagine utilizzano più codifiche.

## Quale codifica viene utilizzata per la pagina dei risultati della ricerca? {#section_DA68670F35D54EAABF7DBB010F4409BF}

La codifica set di caratteri dell’account determina la codifica predefinita per il modello di risultati.

Vedere [Configurazione delle informazioni personali dell&#39;utente](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Per ulteriori informazioni sulla specifica di un set di caratteri in un modello HTML.

Vedere [Cerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## È possibile utilizzare la ricerca del sito/merchandising su pagine codificate Unicode, UTF-8? {#section_130997CB08934A13A5261D85CF88040C}

Sì. Tuttavia, i set di caratteri Unicode, come UTF-8, non forniscono informazioni sufficienti per determinare la lingua in cui sono scritte le pagine. Per eseguire correttamente la ricerca in queste pagine, è necessario specificare la lingua. Per determinare la lingua del documento, le informazioni vengono elaborate nel seguente ordine:

* Intestazione HTTP Content-Language consegnata dal server al documento.
* Elementi META (ad esempio, `META HTTP-EQUIV="Content-Language" Content="ja_JP"`) nella sezione `<HEAD>` del documento.

* Attributo LANG del tag `<HTML>` (ad esempio, `<HTML LANG="ja_JP">`).

Se il server non è configurato per distribuire l&#39;intestazione HTTP Content-Language e i documenti non contengono né l&#39;elemento META della lingua né l&#39;attributo della lingua per il tag `<HTML>`, potete utilizzare le iniezioni di metadati per specificare la lingua appropriata.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Com&#39;è possibile che non sia possibile effettuare ricerche nei file PDF cinesi, giapponesi o coreani sul sito Web? {#section_539AFF482F814D28B5929F683D2F2175}

Ricerca nel sito/merchandising ottiene UTF-8 da  file Adobe PDF senza indicazione della lingua. Se è stato selezionato **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare la lingua utilizzata nel file PDF.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Com&#39;è possibile che non sia possibile effettuare ricerche nei file SWF cinesi, giapponesi o coreani sul sito Web? {#section_9C0849528AFF4C10AA97A2C912992638}

Ricerca nel sito/merchandising ottiene UTF-8 da  file di filmati Flash di Adobe creati con  Flash Adobe senza indicazione della lingua. Se è stato selezionato il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare la lingua utilizzata nel file SWF.

Ad Flash, versione 4 o versioni precedenti dei file SWF, il set di caratteri dei caratteri nel file non è specificato. Se è stato selezionato il tipo di contenuto **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare il set di caratteri utilizzato nel file SWF.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Com&#39;è possibile che non sia possibile effettuare ricerche nei file Microsoft Office cinesi, giapponesi o coreani sul sito Web? {#section_6764BA6863AF492EBA9BE5CCC12CDD1F}

Ricerca nel sito/merchandising ottiene UTF-8 da file di Microsoft Office (Microsoft Word, Microsoft Excel e Microsoft PowerPoint) senza alcuna indicazione di lingua. Se è stato selezionato il tipo di contenuto **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare la lingua utilizzata nei file di Microsoft Office.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Com&#39;è possibile che non sia possibile effettuare ricerche nei file MP3 cinesi, giapponesi o coreani sul sito Web? {#section_DB6D60CF46F94125BF4E54AF3036DBFC}

Se si seleziona il tipo di contenuto **[!UICONTROL Text in MP3 Music Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare il set di caratteri utilizzato per codificare i file MP3.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Devo fare qualcosa di speciale per far sì che i file .txt sul mio sito Web vengano indicizzati correttamente? {#section_A8BA6DDD3A6048319D3530BCFD6DA1A5}

Se è stato selezionato il tipo di contenuto **[!UICONTROL Text Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare il set di caratteri utilizzato per codificare i file .txt.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Com&#39;è possibile che i font cinesi, giapponesi o coreani vengano visualizzati nei risultati di ricerca in Netscape 4.7 e versioni precedenti? {#section_DF42567063304F918D406AC76529DFB7}

Se l&#39;account utilizza il modello predefinito, uno dei modelli pronti per l&#39;uso o un modello basato su uno di questi modelli, potrebbe contenere dei tag di font che specificano Arial o Helvetica come facce di font. Ad esempio, `<font face="arial, helvetica" size="+1">`. Netscape 4.7 e versioni precedenti non visualizza i caratteri cinesi, giapponesi o coreani quando si utilizza il carattere Arial o Helvetica. Rimuovete l&#39;attributo `face` o sostituite il tipo di carattere con uno più adatto per cinese, giapponese o coreano.

## Conteggio pagine basso {#reference_4344E3E3CB2948939860F8C078BD7773}

Pagina delle domande frequenti in cui vengono illustrati i problemi comuni associati a un numero di pagine con indice basso.

Di seguito sono riportate alcune domande comuni relative ai conteggi di pagina con indice basso:

* [Hai esaminato il tuo registro indice?](#section_D6626536DC3D40DDA4A1224F1CB276BF)
* [Si verificano errori di digitazione nell’URL?](#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676)
* [La pagina Web entrypoint contiene collegamenti verso altre pagine...](#section_1C2D6ED54E7249268B555D9DC33352B3)
* [Sono collegamenti ad altre pagine del sito Web incorporati in...](#section_EE34A67D60A844EBB0921C03544FF63E)
* [I tag HTML nella pagina Web in un...](#section_F31A2F5D2C284AC084158A5BD763DC5D)
* [Hai dei tag di commento HTML con formato errato nel tuo...](#section_D1C39D79341845CB9C38579AABDF3A24)
* [La pagina Web contiene collegamenti alle pagine di un altro sito...](#section_F8082759184049AAA8FA6342C1F84389)
* [Stai utilizzando un servizio di dominio virtuale per il tuo URL...](#section_2861F09EA21A45E6B7E15F032739CDF3)
* [La pagina Web utilizza un tag di aggiornamento meta?](#section_5A2F544C237C49B8B1A7FE0C45371C0D)
* [La vostra pagina Web utilizza un tag meta robots?](#section_36275A33DDFE4620BABA948F8A63DBD2)
* [Il vostro sito Web utilizza un file di esclusione robot?](#section_BF7B663347814F58AD736066C86B7D25)

## Hai esaminato il tuo registro indice? {#section_D6626536DC3D40DDA4A1224F1CB276BF}

Il registro indice contiene informazioni dettagliate che il robot di ricerca/merchandising raccoglie nel momento in cui indicizza il sito Web. Il registro include un elenco di collegamenti sottoposti a ricerca per indicizzazione ed errori rilevati. Esaminare il registro indice è il punto migliore per iniziare a determinare il motivo per cui tutte le pagine del sito Web non sono indicizzate.

Vedere [Visualizzazione dell&#39;intero registro di indice di un live o di uno stage...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

Vedere [Visualizzazione del registro di indice incrementale di un live o di uno stage...](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

## Si verificano errori di digitazione nell’URL? {#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676}

Quando si digitano URL lunghi nei moduli HTML, è possibile che si verifichino uno o più errori tipografici. Tenete presente che gli URL non devono contenere spazi. Inoltre, alcuni server Web gestiscono gli URL in modo sensibile alle maiuscole/minuscole.

Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]** dal menu del prodotto. Nella pagina [!DNL Staged URL Entrypoints], verifica quanto segue:

* Negli URL non sono presenti errori tipografici.
* I caratteri negli URL utilizzano tutti la combinazione di maiuscole e minuscole corretta.
* Gli URL non contengono spazi.

Per verificare i punti di ingresso dell’URL, copiate e incollate un URL in un browser Web per verificare se il sito Web è visualizzato. Se non viene visualizzato, verificate nuovamente di non aver commesso errori nel percorso dell’URL.

Consultate [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## La pagina Web entrypoint contiene collegamenti verso altre pagine del sito Web? {#section_1C2D6ED54E7249268B555D9DC33352B3}

Il robot di ricerca del sito/merchandising passa per il sito Web proprio come fa il cliente; tramite collegamenti da una pagina all’altra. I collegamenti devono essere presenti nella pagina Web del punto di ingresso prima che il robot di ricerca possa trovare e indicizzare altre pagine sul sito.

Consultate [Aggiunta di più punti di immissione URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## I collegamenti ad altre pagine del sito Web sono incorporati in JavaScript? {#section_EE34A67D60A844EBB0921C03544FF63E}

Potete utilizzare sofisticate tecniche di navigazione sul sito Web, ad esempio azioni di rollover e menu, che utilizzano JavaScript per il collegamento ad altre pagine. Tuttavia, il robot di ricerca del sito/merchandising non può seguire i collegamenti incorporati in JavaScript.

Una soluzione che è possibile utilizzare per superare questo problema consiste nell&#39;inserire collegamenti nascosti ad altre pagine nell&#39;HTML che contiene il codice JavaScript. Anche se i clienti del tuo sito Web non vedono questi collegamenti, il robot di ricerca li trova ancora e li setaccia. Potete posizionare i tag nascosti nella parte inferiore della pagina immediatamente prima del tag `</body>`. Potrebbero essere come segue:

```
<a href="/mydir/mypag1.html"></a> 
<a href="/mydir/mypag2.html"></a>
```

Un&#39;altra soluzione consiste nell&#39;elencare gli URL delle pagine aggiuntive sul sito Web come punti di ingresso per la ricerca per indicizzazione e l&#39;indicizzazione. Iniziate gli URL con `https://` come illustrato di seguito:

```
https://www.mydomain.com/mydir/mypag1.html 
https://www.mydomain.com/mydir/mypag2.html
```

Consultate [Aggiunta di più punti di immissione URL da indicizzare](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## I tag HTML presenti nella pagina Web sono in una sequenza non valida? {#section_F31A2F5D2C284AC084158A5BD763DC5D}

La specifica HTML richiede che i tag `<html>`, `<head>` e `<body>` seguano una sequenza specifica in un documento HTML. I tag in tutte le pagine Web devono avere la seguente sequenza:

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

Se i tag HTML non sono nell&#39;ordine corretto, il robot di ricerca/merchandising del sito non è in grado di analizzare e indicizzare correttamente la pagina Web. Di seguito è riportato un esempio di tag che non si trovano nella sequenza corretta:

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

In tal caso, posizionare i tag `<html>`, `<head>` e `<body>` nella sequenza corretta della pagina Web.

## Sono presenti tag di commento HTML non formattati correttamente nella pagina Web? {#section_D1C39D79341845CB9C38579AABDF3A24}

Verificate attentamente e correggete eventuali commenti HTML non validi presenti nelle pagine Web.

La specifica HTML richiede che un commento HTML inizi con i caratteri `<!--` e termini con i caratteri `-->`. È facile ignorare i commenti formattati in modo errato che causano l&#39;analisi errata dei tag nella pagina Web da parte del robot di ricerca del sito/merchandising. Un commento formato in modo errato può causare la perdita di altri tag importanti da parte del robot di ricerca/merchandising del sito. Ricorda i commenti immediatamente prima del tag `<body>` nella pagina Web.

Esempio di commento con formato corretto:

`<!-- This HTML comment is OK. -->`

Di seguito è riportato un esempio di commenti con formato non corretto:

```
<!- This HTML comment is improperly formed. -> 
<! This HTML comment is also improperly formed. >
```

## La pagina Web contiene collegamenti alle pagine di un altro dominio? {#section_F8082759184049AAA8FA6342C1F84389}

Spesso un sito Web può essere costituito da pagine effettivamente presenti su un server Web con un indirizzo di dominio diverso. Ad esempio, se l’indirizzo del sito Web principale è il seguente:

`https://www.mydomain.com/`

Il sito Web può anche contenere pagine in un altro dominio, ad esempio:

`https://www.otherdomain.com/`

Per impostazione predefinita, il robot di ricerca del sito/merchandising non segue collegamenti su un dominio diverso da quello principale. Tuttavia, impostando altri punti di ingresso per l’account di ricerca, potete facilmente indicizzare più domini.

Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]** dal menu del prodotto. Aggiungete l&#39;URL del &quot;sito Web principale&quot; del sito. Quindi, aggiungete altri punti di ingresso URL a qualsiasi altro dominio che contenga pagine del sito. Ad esempio, impostate il punto di ingresso dell’URL principale su:

`https://www.mydomain.com/`

e aggiungete il seguente punto di ingresso URL del sito:

`https://www.otherdomain.com/`

## Utilizzi un servizio di dominio virtuale per il tuo URL? {#section_2861F09EA21A45E6B7E15F032739CDF3}

È possibile che stiate utilizzando un servizio di dominio virtuale (talvolta denominato &quot;servizio di reindirizzamento del dominio&quot;) per fornire un URL migliore per consentire ai clienti di accedere al sito Web. Ad esempio, supponiamo che l’indirizzo reale del sito Web sia il seguente:

`https://www.myispdomain.com/~myname/mywebpages/`

Tuttavia, potete utilizzare un servizio di dominio virtuale per consentire ai clienti di accedere al vostro sito ai seguenti indirizzi:

`https://myname.adomain.com/`

 oppure 

`https://adomain.com/myname/`

Per impostazione predefinita, il robot di ricerca del sito/merchandising non segue collegamenti su un dominio diverso da quello principale. Tuttavia, impostando altri punti di ingresso per l’account di ricerca, potete facilmente indicizzare più domini.

Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]** dal menu del prodotto. Aggiungete il &quot;punto di ingresso dell’URL del sito Web principale&quot; al nome del dominio virtuale del sito. Quindi, aggiungete altri punti di ingresso al dominio in cui vive effettivamente il sito Web.

Ad esempio, impostate il punto di ingresso dell’URL principale su quanto segue:

`https://myname.adomain.com/`

Aggiungete il seguente punto di ingresso URL del sito Web:

`https://www.myispdomain.com/~myname/mywebpages/`

## La pagina Web utilizza un tag di aggiornamento meta? {#section_5A2F544C237C49B8B1A7FE0C45371C0D}

Molti siti Web dispongono di una pagina anteriore che include un tag di aggiornamento meta tra i tag `<head>...</head>`, simile al seguente:

`<meta http-equiv="Refresh" content="0;URL=https://www.adomain.com/apath/afile.html">`

In alcune circostanze, il robot di ricerca del sito/merchandising non è in grado di seguire l’URL di aggiornamento meta per indicizzare il contenuto del sito Web. Questo problema è facile da risolvere impostando altri punti di ingresso.

Scegliere **[!UICONTROL Settings]** > Ricerca per indicizzazione > **[!UICONTROL URL Entrypoints]** dal menu del prodotto. Aggiungete un altro punto di ingresso all’URL del tag di aggiornamento meta.

## La vostra pagina Web utilizza un tag meta robots? {#section_36275A33DDFE4620BABA948F8A63DBD2}

Talvolta le pagine Web utilizzano tag meta-robot per controllare i robot Web che tentano periodicamente di sfogliare un sito Web. I tag meta-robot vengono visualizzati tra i tag `<head>...</head>` di una pagina Web e hanno un aspetto simile al seguente tag:

`<meta name="robots" content="noindex, nofollow">`

Poiché il robot di ricerca/merchandising del sito è esso stesso un robot web, segue le indicazioni del tag meta robot. Escludendo altri robot in questo modo si esclude anche il robot di ricerca del sito/merchandising.

Per ulteriori informazioni sui robot web e sul protocollo di esclusione dei robot, consulta:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

Rimuovete o modificate il tag meta robot nelle pagine Web da indicizzare sul sito Web.

## Il vostro sito Web utilizza un file di esclusione robot? {#section_BF7B663347814F58AD736066C86B7D25}

A volte un sito Web ha una pagina chiamata robots.txt che esclude tutti o alcuni robot dalla ricerca per indicizzazione. Per verificare se nel sito Web è presente un file robots.txt, cercatelo appena sotto il dominio di primo livello come illustrato di seguito:

`https://www.yourdomain.com/robots.txt`

Il contenuto del file robots.txt è simile al testo seguente:

```
User-agent: * 
Disallow: /
```

Poiché il robot di ricerca del sito/merchandising è esso stesso un robot web, segue le indicazioni nel file robots.txt-esclude il robot di ricerca del sito/merchandising. Per risolvere questo problema, modificare il file di esclusione dei robot (robots.txt) per consentire al robot di ricerca del sito/merchandising di eseguire ricerche per indicizzazione e indicizzare il sito Web come segue:

```
User-agent: Atomz/1.0 
Disallow: 
 
User-agent: * 
Disallow: /
```

## Microsoft Office {#reference_A85FCC8A96514A7584F4D2A8AC8111D1}

Una pagina di domande frequenti che illustra il supporto per l&#39;indicizzazione e la ricerca di file di Microsoft® Office in un sito Web.

Seguono alcune domande comuni sui file di Microsoft Office:

* [Cosa viene indicizzato in un file di Microsoft Office?](#section_8681DADFCFE24B7787B1FC08D431EE28)
* [Elementi che non vengono indicizzati in un file di Microsoft Office...](#section_BD53BDABFDD94D7EB0E1F55EC18017BB)
* [Come vengono indicizzati i file di Microsoft Office in modo diverso dalle pagine HTML...](#section_C104B44684F340549A6B9EB8F39EDDBB)
* [Come si impedisce l&#39;indicizzazione dei file di Microsoft Office...](#section_FEBA71274CD14CB99731ADF982087F4C)

## Cosa viene indicizzato in un file di Microsoft Office? {#section_8681DADFCFE24B7787B1FC08D431EE28}

Il contenuto completo dei file di Microsoft Word, Microsoft Excel e Microsoft PowerPoint viene indicizzato.

Le parti seguenti di un file di Microsoft Word sono indicizzate:

* Titolo
* Parole chiave
* Oggetto (Descrizione)
* Contenuto basato su testo
* Collegamenti ipertestuali ad altri documenti

Le parti seguenti di un file Microsoft Excel sono indicizzate:

* Titolo
* Parole chiave
* Oggetto (Descrizione)
* Testo nelle celle
* Valori di formule numeriche nelle celle

Le parti seguenti di un file Microsoft PowerPoint sono indicizzate:

* Titolo
* Parole chiave
* Oggetto (Descrizione)
* Testo su ogni diapositiva

## Cosa non viene indicizzato in un file di Microsoft Office? {#section_BD53BDABFDD94D7EB0E1F55EC18017BB}

Gli elementi grafici contenuti nei file di Microsoft Office o in qualsiasi testo contenuto non sono indicizzati. Le definizioni delle proprietà personalizzate non sono indicizzate come metadati. Anche il testo in campi speciali, come intestazioni e piè di pagina in un file PowerPoint, non viene indicizzato.

## In che modo i file di Microsoft Office vengono indicizzati in modo diverso rispetto alle pagine HTML? {#section_C104B44684F340549A6B9EB8F39EDDBB}

La differenza tra il modo in cui il robot di ricerca indicizza i file Microsoft Office e HTML è che ogni file HTML è una singola pagina e un singolo file di Microsoft Office può rappresentare centinaia di pagine. Per questo motivo, ogni pagina viene conteggiata all’interno di un file di Microsoft Office come pagina separata nell’account di ricerca.

## Come si impedisce l&#39;indicizzazione dei file di Microsoft Office sul sito Web? {#section_FEBA71274CD14CB99731ADF982087F4C}

Se non si desidera che il robot di ricerca esegua ricerche per indicizzazione e indicizzi i file di Microsoft Office, deselezionare il tipo di contenuto **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

È inoltre possibile utilizzare [!DNL URL Masks] per disabilitare l&#39;indicizzazione dei file di Microsoft Office.

Immettete le seguenti maschere URL:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Se non si utilizzano espressioni regolari </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DFEC911DA11C484C8E4671A0F00E1F88"> 
     <li id="li_2E50374E3869426B97353A5A8CBE09EC">exclude *.doc </li> 
     <li id="li_9089D11161524D90849CA88F703772B6">exclude *.xls </li> 
     <li id="li_7F6CFC6212E64C04AAF38E21A667C763">exclude *.ppt </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se si utilizzano espressioni regolari </p> </td> 
   <td colname="col2"> 
    <ul id="ul_012A45C3EC04460EA09C0ECFB49A8FA9"> 
     <li id="li_0C239F0A536D465F85A98EBF7B6ADF27">Escludi regexp ^.*\.doc$ </li> 
     <li id="li_9F91DA35A2A646ACAFF2BA37F9136E2A">Escludi regexp ^.*\.xls$ </li> 
     <li id="li_9D768D9EA2DB44FBB00A1979E21672E2">Escludi regexp ^.*\.ppt$ </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Consultate [Aggiunta di maschere URL per indicizzare o meno parti indice di...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Vedere [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## MP3 {#reference_7614250EE81C4EEFA43E57A6A74E83D7}

Una pagina di domande frequenti che illustra il supporto dell&#39;indicizzazione e della ricerca di file musicali MP3 su un sito Web.

Di seguito sono riportate le domande più comuni sui file MP3.

* [Quando viene creato un file MP3 con scorrimento e indicizzazione?](#section_538EA1682C9C47E3A62640BB25D84C36)
* [Cosa devo fare per cercare e indicizzare...](#section_3CD794446E3545379C14E9F222118665)
* [Come viene riconosciuto un file MP3?](#section_230E7336965A424F96C5CCF1D3C2D103)
* [Cosa viene indicizzato in un file MP3?](#section_E99D252B27CA4946AED3FCD3ABD8779D)
* [Un file MP3 viene conteggiato come una pagina?](#section_9910BEB6617D4D2090558CDF6C65D16B)
* [Come posso impedire l&#39;indicizzazione di singoli file MP3...](#section_C989DC1D3D3841B38F683A462195DC05)
* [Come posso impedire che i file MP3 vengano indicizzati?](#section_305D2B28D1124776B6DC0C62A17827C6)
* [Perché non è possibile effettuare ricerche nei file MP3 cinesi, giapponesi o coreani sul sito?](#section_06A48DA3F9E742CC93CC8B5CCD7382FA)

## Quando viene creato un file MP3 con scorrimento e indicizzazione? {#section_538EA1682C9C47E3A62640BB25D84C36}

I file MP3 vengono sottoposti a ricerca per indicizzazione in due modi. Il metodo più comune è rappresentato da un tag href di ancoraggio in un file HTML:

`<a href="MP3-file-URL"></a>`

Un secondo modo consiste nell’inserire l’URL del file MP3 come punto di ingresso dell’URL.

Consultate [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Cosa devo fare per cercare e indicizzare i file MP3 sul mio sito? {#section_3CD794446E3545379C14E9F222118665}

Per attivare la ricerca per indicizzazione MP3 e l&#39;indicizzazione per il proprio account, scegliere **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** dal menu del prodotto. Nella pagina [!DNL Staged Content Types], selezionare **[!UICONTROL Text in MP3 Music Files]**.

Vedere [Informazioni sui tipi di contenuto](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Come viene riconosciuto un file MP3? {#section_230E7336965A424F96C5CCF1D3C2D103}

Un file MP3 viene riconosciuto dal tipo MIME corrispondente a &quot;audio/mpeg&quot;.

## Cosa viene indicizzato in un file MP3? {#section_E99D252B27CA4946AED3FCD3ABD8779D}

Se necessario, i file MP3 memorizzano una piccola quantità di informazioni testuali. Tali informazioni possono includere il nome dell&#39;album, il nome dell&#39;artista, il titolo della canzone, il genere della canzone, l&#39;anno di rilascio e un commento. Queste informazioni vengono memorizzate alla fine del file in quello che viene chiamato TAG. I file MP3 che contengono informazioni TAG sono indicizzati nel modo seguente:

* Il titolo del brano viene trattato come il titolo di una pagina HTML.
* Il commento viene trattato come una descrizione definita per una pagina HTML.
* Il genere viene trattato come una parola chiave definita per una pagina HTML.
* Il nome dell’artista, il nome dell’album e l’anno di rilascio vengono trattati come il corpo di un documento HTML.

## Un file MP3 viene conteggiato come una pagina? {#section_9910BEB6617D4D2090558CDF6C65D16B}

Sì, ogni file MP3 che viene sottoposto a ricerca per indicizzazione sul sito Web viene conteggiato come una pagina.

## Come posso impedire l&#39;indicizzazione di singoli file MP3? {#section_C989DC1D3D3841B38F683A462195DC05}

Circondare i tag di ancoraggio che collegano ai file MP3 con i tag `<nofollow>` e `</nofollow>`. Il robot di ricerca non segue i collegamenti tra tali tag.

Un altro metodo consiste nell’aggiungere gli URL dei file MP3 come maschere di esclusione.

Consultate [Le maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Vedere [Lo script delle maschere URL](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

## Come posso impedire che i file MP3 vengano indicizzati? {#section_305D2B28D1124776B6DC0C62A17827C6}

Il modo più semplice per controllare l&#39;indicizzazione MP3 per il tuo account è deselezionare **[!UICONTROL Text in MP3 Music Files]** nella pagina [!DNL Staged Content Types].

Vedere [Selezione dei tipi di contenuto per la ricerca per indicizzazione e l&#39;indice](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

Potete inoltre utilizzare la funzione Maschere URL per disattivare l&#39;indicizzazione MP3 per estensione di file. A tale scopo, scegliere **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]** dal menu del prodotto. Inserite una delle seguenti maschere:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Se il tuo account... </p> </th> 
   <th colname="col2" class="entry"> <p>Immettete la seguente maschera URL </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Non utilizza espressioni regolari </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exclude *.mp3  </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilizza espressioni regolari </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> Escludi regexp ^.*\.mp3$ </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vedere [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Perché non è possibile effettuare ricerche nei file MP3 cinesi, giapponesi o coreani sul sito? {#section_06A48DA3F9E742CC93CC8B5CCD7382FA}

Per cercare file MP3 cinesi, giapponesi o coreani, nel menu del prodotto fare clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** > **[!UICONTROL Text in MP3 Music Files]**. Quindi, fate clic su **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]** e specificate il set di caratteri utilizzato per codificare i file MP3.

Vedere [Selezione dei tipi di contenuto per la ricerca per indicizzazione e l&#39;indice](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

Vedere [Informazioni sulle iniezioni](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

## PDF {#reference_F127C4915A0D436DA34E5D75ABFBB21B}

Una pagina delle domande frequenti in cui viene discusso il supporto dell’indicizzazione e della ricerca di file PDF su un sito Web.

Seguono alcune domande comuni sui file PDF:

* [Cosa viene indicizzato in un file PDF?](#section_62BFCD7158B44F2BB3B1864224B50174)
* [Cosa non viene indicizzato in un file PDF?](#section_A14B353AE503408896BACBBF3F748FA0)
* [Come vengono conteggiati i file PDF indicizzati?](#section_C35DE36A65D649BD8FF314E9EFD990A6)
* [I risultati della ricerca possono visualizzare un&#39;icona PDF?](#section_829CE82CC3544502A13D27C4DB820189)
* [È possibile collegare i risultati della ricerca a una particolare pagina in...](#section_A06E7F7017E6441E98209D288EE57BF6)
* [Come si evita l&#39;indicizzazione dei file PDF in corso...](#section_96671419A822486AAC654D8DAD819940)
* [Com&#39;è possibile che non sia possibile effettuare ricerche nei file PDF cinesi, giapponesi o coreani sul sito Web?](#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8)

## Cosa viene indicizzato in un file PDF? {#section_62BFCD7158B44F2BB3B1864224B50174}

Il contenuto completo dei file PDF è indicizzato. Le parti seguenti di un file PDF sono indicizzate:

* Titolo
* Parole chiave
* Oggetto (Descrizione)
* Contenuto basato su testo

## Cosa non viene indicizzato in un file PDF? {#section_A14B353AE503408896BACBBF3F748FA0}

Il sommario PDF, gli elementi grafici all’interno del file o qualsiasi testo contenuto in un elemento grafico non sono indicizzati.

## Come vengono conteggiati i file PDF indicizzati? {#section_C35DE36A65D649BD8FF314E9EFD990A6}

Ogni file PDF viene conteggiato come singolo documento, inclusi i PDF che contengono più pagine.

## I risultati della ricerca possono visualizzare un&#39;icona PDF? {#section_829CE82CC3544502A13D27C4DB820189}

Sì. Utilizzate il tag `<search-if-link-extension>` all&#39;interno del modello per includere nei risultati di ricerca un&#39;icona PDF o altri elementi grafici o testo:

```
<search-results> 
  ... 
  <search-if-link-extension value=".pdf"> 
    <img src="/search/i/pdficon.gif"> 
  </search-if-link-extension> 
  ... 
</search-results>
```

Le icone PDF consentono ai clienti di sapere che il risultato di una ricerca è collegato a un file PDF di grandi dimensioni. Le dimensioni dei file possono essere importanti per i clienti che accedono al sito Web tramite un modem o un dispositivo mobile.

## È possibile collegare i risultati della ricerca a una particolare pagina in un file PDF? {#section_A06E7F7017E6441E98209D288EE57BF6}

Sì. Utilizzando il tag del modello di collegamenti intelligenti ( `<search-smart-link>...</search-smart-link>`), i clienti possono fare clic per aprire la prima pagina PDF che contiene il risultato della ricerca.

Per utilizzare i collegamenti intelligenti, sostituite i tag `<search-link>...</search-link>` nella sezione dei risultati di ricerca del modello con i tag `<search-smart-link>...</search-smart-link>`. Quando un cliente fa clic su un collegamento generato dai tag di collegamento avanzato, passa alla prima pagina PDF rilevante per la query di ricerca.

>[!NOTE]
>
>Per utilizzare questa funzione, il cliente deve utilizzare una versione recente dell&#39;Adobe Acrobat , o  Reader Adobe Acrobat, che deve includere il plug-in di evidenziazione e il plug-in EWH (External Window Handler). Inoltre, il browser deve utilizzare il  plug-in Adobe Acrobat per Netscape Navigator (è possibile utilizzare qualsiasi browser che accetta questo plug-in Netscape Navigator) o il  controllo Acrobat ActiveX per Internet Explorer 4.0 e versioni successive.

Vedere [Cerca tag modello](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## Come si evita che i file PDF vengano indicizzati sul sito Web? {#section_96671419A822486AAC654D8DAD819940}

Se non si desidera che il robot di ricerca esegua ricerche per indicizzazione e indicizzi i file PDF, deselezionare il tipo di contenuto **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

È inoltre possibile scegliere di utilizzare [!DNL URL Masks] per disattivare l&#39;indicizzazione PDF.

Consultate [Aggiunta di maschere URL per indicizzare o meno parti indice di...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Per disattivare l&#39;indicizzazione PDF, immettere una delle seguenti maschere URL:

* `exclude *.pdf` (se non si utilizzano espressioni regolari)
* `exclude regexp ^.*\.pdf$` (se utilizzate espressioni regolari)

Vedere [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Com&#39;è possibile che non sia possibile effettuare ricerche nei file PDF cinesi, giapponesi o coreani sul sito Web? {#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8}

Ricerca nel sito/merchandising ottiene l&#39;UTF-8 da file PDF senza indicazione di lingua. Se è stato selezionato il tipo di contenuto **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), è necessario utilizzare le iniezioni di metadati per specificare la lingua utilizzata nel file PDF.

Vedere [Aggiunta di definizioni di iniezione di campi](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Troppe pagine {#reference_48A748BC1ED14844ACAC2735C8388E8A}

Una pagina di domande frequenti che spiega alcuni dei motivi per cui l&#39;indicizzatore ha contato più pagine di quante ne possiate effettivamente, e qual è la soluzione in ogni caso.

Se siete certi che il sito Web è al di sotto del limite della pagina, ma l&#39;indicizzatore sta dicendo che il limite è raggiunto, è necessario esaminare queste domande comuni e le risposte per possibili soluzioni.

* [Hai esaminato i vari registri indice?](#section_C929BF9FDA6B4C9A9078C45AFE80EFE8)
* [I programmi CGI vengono indicizzati sul sito Web?](#section_86ED8A641B3841EC80153B4F107548FD)
* [Nel server è abilitata la navigazione nella directory?](#section_073C88EEE74F4CA0AD2C7145D4810B22)
* [Ci sono forum o newsgroup sul vostro sito Web?](#section_8DCB94F0850A41B9B2EA885F779E2F84)
* [Nel sito Web sono presenti file PDF o Microsoft Office...](#section_455FC5438DF74E68AB9A31D359EAD4D9)
* [Hai più punti di ingresso URL?](#section_8C54AFD7DF56472A9364D516482B534C)
* [Hai superato i byte interni o i limiti di tempo di...](#section_AE1BE61A58864FFE81F0BCEED2EBB15D)

## Hai esaminato i vari registri indice? {#section_C929BF9FDA6B4C9A9078C45AFE80EFE8}

Il registro indice contiene informazioni dettagliate raccolte dal robot di ricerca del sito/merchandising mentre indicizza il sito Web. Il registro include un elenco di tutti i collegamenti sottoposti a ricerca per indicizzazione ed è stato rilevato un errore. La verifica del registro di indice è la soluzione migliore per iniziare quando si tenta di determinare quali pagine vengono indicizzate.

Vedere [Visualizzazione dell&#39;intero registro di indice di un live o di uno stage...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

Vedere [Visualizzazione del registro di indice incrementale di un live o di uno stage...](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

Vedere [Visualizzazione del registro di indice incrementale con script di un live o...](../c-about-index-menu/c-about-scripted-index.md#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7).

Vedere [Visualizzazione del registro di indice rigenerato di un live o di uno stage...](../c-about-index-menu/c-about-regenerate-index.md#task_61CE8F9E7BF84BA89A8D482B2106BB15).

Vedere [Visualizzazione del registro di indice ri-classifica di un sito Web live o in fase](../c-about-index-menu/c-about-re-rank-index.md#task_3C76107DFAC1495FACD3ABB0A688208D).

## I programmi CGI vengono indicizzati sul sito Web? {#section_86ED8A641B3841EC80153B4F107548FD}

I programmi CGI utilizzano parametri URL che talvolta causano la ricerca per indicizzazione di più URL &quot;falsi&quot;. Se la ricerca del sito/merchandising sta leggendo i vostri programmi CGI e i seguenti URL con parametri CGI, probabilmente ci sono diversi multipli di pagine sottoposte a ricerca per indicizzazione e indicizzazione che non sono utili per il vostro indice di ricerca. I parametri CGI tipici vengono visualizzati negli URL con caratteri `?` o `&`.

Potete mascherare i programmi CGI dall’indicizzazione utilizzando la funzione Maschere URL. Potete mascherare un prefisso URL o usare espressioni regolari per mascherare gli script CGI.

Consultate [Le maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Vedere [Lo script delle maschere URL](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

Vedere [Espressioni regolari](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Nel server è abilitata la navigazione nella directory? {#section_073C88EEE74F4CA0AD2C7145D4810B22}

Quando un server Web ha attivato la navigazione nelle directory e non esiste alcun file index.html presente in una determinata directory, una visita a tale directory può mostrare l’elenco dei file presenti in tale directory. In genere, nella parte superiore della pagina sono presenti collegamenti che consentono di ordinare l&#39;elenco in modi diversi semplicemente facendo clic su **[!UICONTROL Name]**, **[!UICONTROL Last modified]**, **[!UICONTROL Size]** e così via. In genere, questi vengono visualizzati nel registro dell&#39;indice di ricerca/merchandising del sito come URL con caratteri come ad esempio `?M=A` alla fine. L’indicizzatore di ricerca/merchandising del sito segue questi collegamenti, e questo può causare l’indicizzazione di più URL &quot;falsi&quot;.

In genere, un sito Web ben progettato ha file indice situati in ogni directory, o ha la navigazione directory disabilitata per quelle directory senza file indice. Fortunatamente, c&#39;è un modo semplice per mascherare questi &quot;falsi&quot; URL se non si è in grado di cambiare le pagine o disabilitare gli elenchi di directory sul lato server.

Per eseguire questa operazione, fare clic su **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. Aggiungete una maschera per mascherare qualsiasi URL che contiene il carattere `?`. Per eseguire questa operazione, immettete la seguente maschera di espressione regolare:

`exclude regexp ^.*\?.*$`

Dopo aver creato la maschera, accertatevi di reindicizzare il sito Web.

Vedere [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Vedere [Esecuzione di un indice incrementale di un sito Web live o in fase...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Ci sono forum o newsgroup sul vostro sito Web? {#section_8DCB94F0850A41B9B2EA885F779E2F84}

Se i forum o i newsgroup vengono sottoposti a ricerca per indicizzazione sul sito Web, potrebbero essere presenti URL per opzioni di visualizzazione o ordinamento diverse. Questo significa che la stessa pagina viene indicizzata più volte.

In genere, i forum o i newsgroup sono dotati di motori di ricerca personalizzati. In tal caso, potete utilizzare [!DNL URL Masks] per mascherare i forum da ricerche e merchandising sul sito.

Scegliere **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]** dal menu del prodotto. Nella pagina [!DNL Staged URL Masks], mascherate i forum immettendo i relativi URL come maschere URL di esclusione.

Consultate [Aggiunta di maschere URL per indicizzare o meno parti indice di...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Dopo aver creato le maschere, accertatevi di reindicizzare il sito Web.

Vedere [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Vedere [Esecuzione di un indice incrementale di un sito Web live o in fase...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Nel sito Web sono presenti file PDF o Microsoft Office? {#section_455FC5438DF74E68AB9A31D359EAD4D9}

Se sul sito Web sono presenti file PDF o [!DNL Microsoft Office] file, è possibile che la dimensione indice di pochi file conteggi molte pagine. Il motivo per cui ci sono più pagine da indicizzare rispetto ai documenti è che ogni pagina di un file PDF o Microsoft Office viene conteggiata come una pagina separata.

Scegliere **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]** dal menu del prodotto. Nella pagina [!DNL Full Index], selezionare **[!UICONTROL Count All Pages]**, quindi fare clic su **[!UICONTROL Full Index Now]** per visualizzare il conteggio totale delle pagine. Se non si desidera che i file PDF o i file di Microsoft Office siano indicizzati, è possibile disattivare questo tipo di contenuto in **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**.

Vedere [Esecuzione di un indice completo di un sito Web attivo o in fase di esecuzione...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Vedere [Informazioni sui tipi di contenuto](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Hai più punti di ingresso URL? {#section_8C54AFD7DF56472A9364D516482B534C}

Il robot di ricerca del sito/merchandising inizia a eseguire ricerche per indicizzazione nei punti di ingresso dell’URL specificati e segue tutti i collegamenti trovati a tutto il contenuto in quel particolare dominio. Se avete specificato molti punti di ingresso URL, è possibile che venga applicato il crawled a un numero significativo di pagine.

Utilizzate il tag `nofollow` del protocollo di esclusione dei robot nelle intestazioni dei documenti di ingresso sui domini aggiuntivi come segue:

```
<html> 
<head> 
<meta name="robots" content="nofollow"> 
</head>
```

Il codice riportato sopra indica al robot di ricerca del sito/merchandising di indicizzare il contenuto della pagina, ma non di seguire i collegamenti verso altre pagine.

Per ulteriori informazioni sui robot web e sul protocollo di esclusione dei robot, consulta:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

Se non disponete dell&#39;accesso all&#39;origine delle pagine su domini aggiuntivi, potete rimuovere i diversi punti di ingresso URL. In questo modo potete limitare l&#39;attività di indicizzazione solo ai domini di cui desiderate che i clienti siano in grado di effettuare ricerche.

Consultate [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Hai superato i byte interni o i limiti di tempo di ricerca/merchandising del sito? {#section_AE1BE61A58864FFE81F0BCEED2EBB15D}

Verificate che il vostro account abbia raggiunto il limite nella schermata &quot;Stato indice completo&quot;. Se lo stato indica che l&#39;indice è superiore al consentito o che richiede più tempo del consentito, il sito Web non viene indicizzato completamente. Potete correggere questo errore in modo da ottenere la copertura e il conteggio corretti delle pagine del sito Web.

Per proteggere i server di ricerca/merchandising del sito, esistono limiti interni di byte e tempo. Solo quando i file sottoposti a ricerca per indicizzazione sono molto grandi, o quando il server che la ricerca/merchandising del sito sta tentando di raggiungere è lento, questi limiti sono raggiunti.

Se raggiungete un limite di tempo, accertatevi che il server sia online e tentate di nuovo l’indice in un secondo momento. Se si raggiunge un limite di byte, controllare i file sottoposti a ricerca per indicizzazione visualizzando il registro di indice. Sono insolitamente grandi? Se ricevete uno di questi messaggi, contattate l’assistenza tecnica.
