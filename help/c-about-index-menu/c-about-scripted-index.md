---
description: Con l'indice con script è possibile scrivere, aggiornare e mantenere opzioni di indicizzazione incrementale senza dover effettuare l'accesso. Il robot di ricerca legge le istruzioni da un file di testo ospitato sul server.
seo-description: Con l'indice con script è possibile scrivere, aggiornare e mantenere opzioni di indicizzazione incrementale senza dover effettuare l'accesso. Il robot di ricerca legge le istruzioni da un file di testo ospitato sul server.
seo-title: Indice con script
solution: Target
subtopic: Scripted Index
title: Indice con script
topic: Index,Site search and merchandising
uuid: 51e726ad-414b-4cbd-8a68-fefc3cf9b565
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# Indice con script{#about-scripted-index}

Con l&#39;indice con script è possibile scrivere, aggiornare e mantenere opzioni di indicizzazione incrementale senza dover effettuare l&#39;accesso. Il robot di ricerca legge le istruzioni da un file di testo ospitato sul server.

## Utilizzo dell&#39;indice con script {#concept_34F58D551BC04BFB8ADC294B9DA9199D}

## Informazioni sulla configurazione dell&#39;indicizzazione incrementale con script {#section_161D254065E143F3A39F3FC09C400090}

Per utilizzare l&#39;indice con script, è possibile utilizzare la pagina Configurazione indice incrementale con script per specificare l&#39;URL di un file di script (un file di testo normale) che si trova sul server. Ad esempio, `https://www.mysite.com/indexlist.txt`. Quando il sito cambia, potete aggiungere blocchi di comando al file di testo manualmente o automaticamente (con uno script avviato dall&#39;arrivo di informazioni da un feed di notizie, un ticker di azioni o altri file alterati).

Quando inizia l&#39;indice incrementale con script, il robot di ricerca legge il file di testo ed esegue i nuovi comandi che si trovano in quel file. Per impostazione predefinita, il robot di ricerca elabora solo i nuovi comandi, determinati dalla data del file. A meno che non si verifichi **[!UICONTROL Clear Date]** al momento della configurazione dell&#39;indice con script, il robot di ricerca &quot;ricorda&quot; l&#39;identificatore data del blocco elaborato più di recente.

## Informazioni sul file di script {#section_B312E40539F44C6583B4F9637D428E19}

Il file di script specificato nell&#39;URL è un file di testo normale che si trova sul server. È possibile utilizzare ritorni a capo, feed di linea o entrambi per la sequenza di fine riga. Una riga vuota contiene zero o più caratteri di spazio vuoto seguiti da una sequenza di fine riga. Tutti i comandi non fanno distinzione tra maiuscole e minuscole.

Il file di testo è organizzato in blocchi che descrivono le informazioni utilizzate dal robot di ricerca quando esegue un indice incrementale con script.

I blocchi sono ordinati per data, con i blocchi più vecchi nella parte superiore del file di testo e i blocchi più recenti nella parte inferiore. Ogni blocco inizia con un comando data-riga singola e un comando data-identificatore, e termina con un separatore di riga vuota come nell&#39;esempio di blocco seguente (tra i quali sono diversi comandi):

Per tutte le date ordinali inferiori al 10, è richiesto uno zero iniziale quando si utilizza lo stile HTTP 1.1. Ad esempio, il 6 novembre è 06 nov, non 6 nov.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Comando </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>date-command </p> </td> 
   <td colname="col2"> <p>La prima riga di ciascun blocco inizia con uno dei due comandi data: </p> <p> 
     <ul id="ul_9C1B229B7F1846C490B853FC34989E77"> 
      <li id="li_31FEF1A7163842BDBB0ABE779D07045A"> <span class="codeph"> date </span> <p>Utilizzate il comando "date" per indicare che l'identificatore data sarà composto da un giorno, una data, un'ora e un fuso orario. </p> </li> 
      <li id="li_0918D5B090014C1A852CB80BB7C2867C"> <span class="codeph"> secondi </span> <p>Utilizzate <span class="codeph"> secondi </span> per indicare che lo specificatore data sarà costituito da un tempo espresso in secondi epoch (ad esempio, 784111777). Quando si utilizzano <span class="codeph"> i secondi </span>, assicurarsi che il numero di secondi aumenti tra i blocchi. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>data-identificatore </p> </td> 
   <td colname="col2"> <p>Il comando <span class="codeph"> data-identificatore </span> registra in genere la data e l'ora ordinali (comando data) o l'ora in secondi epoch (comando secondi) in cui le informazioni del blocco sono state aggiunte al file. Ad esempio: </p> <p> <code> date&nbsp;Sun,&nbsp;06&nbsp;Nov&nbsp;1994&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.1&nbsp;style) 
      date&nbsp;Sunday,&nbsp;06-Nov-94&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.0&nbsp;style) 
      date&nbsp;Sun&nbsp;Nov&nbsp;6&nbsp;08:49:37&nbsp;1994&nbsp;(Unix&nbsp;asctime()&nbsp;date&nbsp;style) 
      seconds&nbsp;784111777&nbsp;(Unix&nbsp;epoch-seconds&nbsp;style) </code> </p> <p>Per tutte le date ordinali inferiori al 10, è richiesto uno zero iniziale quando si utilizza lo stile HTTP 1.1. Ad esempio, il 6 novembre è 06 nov, non 6 nov. </p> <p>Il robot di ricerca "ricorda" l'identificatore della data del blocco elaborato più di recente e indicizza solo le informazioni che considera "più recenti". (Il tempo reale non ha importanza per il robot di ricerca. Invece, il tempo in relazione ad altri tempi precedentemente elaborati è ciò che conta.) </p> <p>Dopo che il robot di ricerca legge un blocco con un identificatore data di 10:00 p.m., ad esempio, non legge blocchi che registrano i tempi prima delle 10:00 p.m., indipendentemente da quando l'operazione indice è in esecuzione. In uno scenario peggiore, potete immettere erroneamente l'anno "2040" invece di "2004" nel vostro identificatore data. In questo caso, il robot di ricerca indicizza il blocco 2040 durante l'operazione di indicizzazione successiva e rifiuta di leggere qualsiasi altro blocco di informazioni (a meno che un post-date 2040). In questo caso, rimuovere tutti i blocchi precedentemente elaborati dal file di testo, fare clic su <span class="uicontrol"> Cancella data </span>, quindi inviarli live. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>commento, riga </p> </td> 
   <td colname="col2"> <p>Iniziare le righe dei commenti con il carattere "#". </p> <p>Ogni riga di commento deve essere una riga propria; non è possibile digitare commenti di fine riga. </p> <p>Una riga di commento non è considerata una riga vuota. Può essere visualizzato anche in qualsiasi punto di un blocco, anche prima di un comando data o secondi, come nell'esempio seguente: </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;#Added&nbsp;by&nbsp;Cathy&nbsp;Read&nbsp;after&nbsp;the&nbsp;Y2K&nbsp;seminar 
      &nbsp;&nbsp;&nbsp;&nbsp;date&nbsp;Mon,&nbsp;29&nbsp;Dec&nbsp;1999&nbsp;09:32:20&nbsp;GMT&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>action-command </p> </td> 
   <td colname="col2"> <p>Ogni blocco di testo può contenere tutti i comandi di azione desiderati. Le seguenti opzioni di comando azione corrispondono a quelle per l'indicizzazione incrementale standard: </p> <p> 
     <ul id="ul_8E1435350A0F416BB8F7826CD3886E74"> 
      <li id="li_22181666628C48A28A6A0BA1F7CA8E77"> 
       <userinput>
         add 
       </userinput> <p>Utilizzate con URL. Il robot di ricerca indicizza solo gli URL specificati che sono stati modificati dall’ultima operazione di indicizzazione. Inoltre, il robot di ricerca segue i collegamenti contenuti in documenti specifici e indicizza solo i documenti che sono stati modificati. </p> <p>Potete seguire l’URL con 
        <userinput>
          nofollow 
        </userinput>  oppure  
        <userinput>
          noindex 
        </userinput> parole chiave come nell’esempio seguente: </p> <p> <code> add&amp;nbsp;https://www.mydomain.com/&amp;nbsp;noindex </code> </p> </li> 
      <li id="li_8E47BF07DB24417083883F5BF40D6B9E"> 
       <userinput>
         update 
       </userinput> <p>Utilizzate con la maschera URL. Il robot di ricerca trova e aggiorna tutti i documenti che corrispondono alla maschera URL specificata. </p> <p>Potete seguire l’URL con 
        <userinput>
          nofollow 
        </userinput>  oppure  
        <userinput>
          noindex 
        </userinput> parole chiave come nell’esempio seguente: </p> <p> <code> update&amp;nbsp;https://www.mydomain.com/products/ </code> </p> </li> 
      <li id="li_B3EC8B1670D54F66A1D8411A694EF7E4"> 
       <userinput>
         include 
       </userinput>  oppure  
       <userinput>
         exclude 
       </userinput> <p>Utilizzate con la maschera URL. Il robot di ricerca trova e indicizza ("include") o ignora i documenti ("exclude") in base al tipo di maschera specificata. </p> <p>Ad esempio, </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/products/household/lightbulbs*.html </code> </p> <p> oppure  </p> <p> <code> exclude&amp;nbsp;https://www.mydomain.com/archive/ </code> </p> </li> 
      <li id="li_050B54B735F0475E93806455FA6DC6A5"> 
       <userinput>
         include-date 
       </userinput>  oppure  
       <userinput>
         exclude-date 
       </userinput> <p>Utilizzate con la maschera URL. Il robot di ricerca trova e indicizza ("include") o ignora i documenti ("exclude") in base sia all'URL che alla data dei documenti. Sono disponibili i seguenti tipi di maschere: </p> <p> 
        <ul id="ul_23A15CB492214B86BE84D8E6EA1820AE"> 
         <li id="li_0C7051AC3B5A4C57A3E477F7B6246611"> 
          <userinput>
            includi giorni NNN 
          </userinput> <p>Il robot di ricerca indicizza tutti i documenti che corrispondono alla maschera URL specificata e che sono giorni NNN o più vecchi. </p> <p>Potete seguire la maschera URL con le parole chiave 
           <userinput>
             nofollow 
           </userinput>, 
           <userinput>
             noindex 
           </userinput>e/o 
           <userinput>
             data server 
           </userinput>. </p> </li> 
         <li id="li_983A10E2ED5D434EA9031F32143F4EF4"> 
          <userinput>
            include data AAAA-MM-GG 
          </userinput> <p> Il robot di ricerca indicizza tutti i documenti che corrispondono alla maschera URL specificata e che hanno la stessa data di AAAA-MM-GG, dove "AAAA" è l'anno di 4 cifre, "MM" è il mese di una o due cifre (1-12), e "GG" è il giorno di una o due cifre (1-31). </p> <p>Potete seguire la maschera URL con le parole chiave 
           <userinput>
             nofollow 
           </userinput>, 
           <userinput>
             noindex 
           </userinput>e/o 
           <userinput>
             data server 
           </userinput>. </p> </li> 
         <li id="li_733CE1B748024CECA7FBE00D7BC7B88A"> 
          <userinput>
            exclude-Days NNN 
          </userinput> <p> Disattiva l’indicizzazione di tutti i documenti che corrispondono alla maschera URL specificata e che sono giorni NNN o più vecchi. </p> <p>Potete seguire la maschera URL con la parola chiave 
           <userinput>
             data server 
           </userinput>. </p> </li> 
         <li id="li_90056A0B96CC4DA3854711860A15CE89"> 
          <userinput>
            exclude-date YYYY-MM-DD 
          </userinput> <p>Disattiva l’indicizzazione di tutti i documenti che corrispondono alla maschera URL specificata e che hanno la stessa data o meno della data AAAA-MM-GG. </p> <p>Potete seguire la maschera URL con la parola chiave 
           <userinput>
             data server 
           </userinput>. </p> </li> 
        </ul> </p> </li> 
      <li id="li_AA78F22B60FE4535BE73BA87A8992C08"> 
       <userinput>
         delete 
       </userinput> <p>Specificate gli URL. Il robot di ricerca rimuove dall’indice i documenti identificati dall’URL. </p> </li> 
      <li id="li_9C63061568AA4D57A4FEBCF6DB9194EC"> 
       <userinput>
         deletemask 
       </userinput> <p>Il robot di ricerca rimuove dall’indice i documenti che corrispondono alla maschera URL specificata. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Consultate anche [Le maschere](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)URL.

## Esempio di file di script {#section_9F580F20E7214751B157A28B392BD64E}

Nell&#39;esempio di file di script riportato di seguito, il robot di ricerca elabora i blocchi a condizione che gli identificatori data postino l&#39;identificatore data dell&#39;ultimo blocco elaborato. In tal caso, si verificano le seguenti operazioni di indicizzazione:

* Elimina `y2k-problems.html` dall&#39;indice.
* Aggiunge `no-y2k-problems.html` all&#39;indice di ricerca e non segue nessuno dei collegamenti per `no-y2k-problems.html`.

* Durante la ricerca per indicizzazione, escludete dall’indice di ricerca gli URL che corrispondono `housewares.htm` e `lightfixtures.htm`l.

* Include tutte le altre directory e documenti in `www.mydomain.com`.
* Aggiorna tutti i documenti all&#39;interno delle `products` directory e `information` delle directory, eseguendo la ricerca per indicizzazione e indicizzando tutti i collegamenti secondari modificati dall&#39;ultima operazione di indicizzazione.

* Durante la ricerca per indicizzazione, escludete gli URL nella `archive` sezione del sito Web, se datati il 1 gennaio 1999 o prima di tale data.
* Escludete gli URL che corrispondono `housewares.html` e `lightfixtures.html` dall’indice di ricerca.

* Indicizzare i file nella `help` directory, ma non eseguire ricerche per indicizzazione o indicizzare alcun collegamento da tali file.
* Eseguire la ricerca per indicizzazione e indicizzare qualsiasi altro file rilevato per `www.mydomain.com`.

```
# Start of file. 
# Added by John Smith 
date Sat, 01 Jan 2004 16:05:53 PST 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/ 
delete https://www.mydomain.com/y2k-problems.html 
add https://www.mydomain.com/no-y2k-problems.html nofollow 
 
date Sun, 02 Jan 2004 20:19:08 PST 
# Added by the wire service updater 
exclude-date 1999-01-01 https://www.mydomain.com/archive server-date 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/help/ nofollow 
include https://www.mydomain.com/ 
# no add files, just update existing files 
# update all files in the "products" directory 
update https://www.mydomain.com/products/ 
# update all files in the "information" directory 
update regexp ^https://www\.mydomain\.com/information/.*$ 
# End of file.
```

## Configurazione di un indice incrementale con script {#task_05AE040FE75E40FFAA5E10B6B6D4D255}

È possibile specificare uno script creato che scrive, aggiorna e mantiene un indice incrementale, senza la necessità di effettuare l&#39;accesso. Il robot di ricerca legge le istruzioni dal file di testo ospitato sul server per eseguire l&#39;indice incrementale.

**Per configurare un indice incrementale con script**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Configuration]**.
1. Nella **[!UICONTROL Scripted Incremental Index Configuration]** pagina, nella **[!UICONTROL Script File URL]**, immettete l’URL dello script del file di testo che si trova sul server.

   Vedere [Informazioni sull&#39;indice](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D)con script.
1. (Facoltativo) Controllare **[!UICONTROL Clear Date]** se non si desidera che il robot di ricerca &quot;ricordi&quot; l’identificatore data del blocco elaborato più di recente.

   Per impostazione predefinita, il robot di ricerca elabora solo nuovi blocchi di comandi che si trovano nel file di testo, che è determinato dalla data del file. Se non si desidera impostare il valore predefinito, selezionare **[!UICONTROL Clear Date]**.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Impostazione della pianificazione dell&#39;indice incrementale con script per un sito Web live {#task_B3A87AC4AC784507859C23B9062BA11C}

È possibile pianificare l&#39;indicizzazione incrementale con script in modo che venga eseguita a intervalli regolari durante l&#39;intera giornata.

L&#39;ora di base selezionata è locale in base al fuso orario configurato in Impostazioni account.

Consultate [Configurazione delle impostazioni](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)dell’account.

I server Web sono spesso programmati per la manutenzione nel bel mezzo della notte. Se il server è inattivo durante un periodo di tempo di indicizzazione pianificato, il processo di indicizzazione non riuscirà. Accertatevi di selezionare un&#39;ora del giorno in cui il server Web sarà disponibile.

La pianificazione dell&#39;indice si applica solo all&#39;indice live; non è possibile pianificare indici incrementali in fase.

**Impostazione della pianificazione dell&#39;indice incrementale con script per un sito Web attivo**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Schedule]**.
1. Nella **[!UICONTROL Scripted Incremental Index Schedule]** pagina, nell&#39;elenco a **[!UICONTROL Read the Scripted Incrementally Indexing File]** discesa, selezionare la frequenza con cui si desidera che venga eseguito il file di testo dell&#39;indice incrementale con script, in ore o minuti.
1. Nell&#39;elenco a **[!UICONTROL Base Time]** discesa, selezionare l&#39;ora di inizio per la rigenerazione di un nuovo indice incrementale con script.
1. Clic **[!UICONTROL Save Changes]**.

## Esecuzione di un indice incrementale con script di un sito Web live o in uno stage {#task_6E6FC76EE1E84A5FADB3B67AD7B1DACB}

È possibile utilizzare l&#39;indice incrementale con script per indicizzare &quot;parti&quot; del sito Web live o in uno stage, ad esempio una raccolta di pagine modificate di frequente, il tutto senza dover effettuare l&#39;accesso.

Per utilizzare questa funzione, accertatevi di aver configurato un file di testo indice incrementale con script.

Consultate [Configurazione di un indice](../c-about-index-menu/c-about-scripted-index.md#task_05AE040FE75E40FFAA5E10B6B6D4D255)incrementale con script.

**Per eseguire un indice incrementale con script di un sito Web attivo o in fase di esecuzione**

1. Nel menu del prodotto, effettuate una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Index]**.
   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Index]**.

1. Clic **[!UICONTROL Scripted Index Now]**.
1. (Facoltativo) In caso di errori di indicizzazione, fare clic **[!UICONTROL View Errors]** per visualizzare il registro associato.

## Visualizzazione del registro di indice incrementale con script di un sito Web live o in uno stage {#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7}

Quando un indice con script completo attivo o un indice con script completo in fase è completo, è possibile visualizzare il registro associato per risolvere eventuali errori che si sono verificati.

Non è possibile esportare i file di registro né salvarli. Tuttavia, il registro rimane disponibile per la visualizzazione fino a quando non si verifica il nuovo indice.

**Per visualizzare il registro dell&#39;indice incrementale di un sito Web attivo o in fase di esecuzione**

1. Nel menu del prodotto, effettuate una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di registro, in alto o in basso, effettuate una delle seguenti operazioni:

   * Utilizzate le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi nel registro.

   * Utilizzate le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare il contenuto visualizzato.

