---
description: Con l'Indice con script è possibile scrivere, aggiornare e mantenere opzioni di indicizzazione incrementale senza la necessità di accedere. Il robot di ricerca legge le istruzioni da un file di testo ospitato sul server.
solution: Target
subtopic: Scripted Index
title: Indice con script
topic: Index,Site search and merchandising
uuid: 51e726ad-414b-4cbd-8a68-fefc3cf9b565
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1730'
ht-degree: 1%

---


# Indice con script{#about-scripted-index}

Con l&#39;Indice con script è possibile scrivere, aggiornare e mantenere opzioni di indicizzazione incrementale senza la necessità di accedere. Il robot di ricerca legge le istruzioni da un file di testo ospitato sul server.

## Utilizzo dell&#39;indice con script {#concept_34F58D551BC04BFB8ADC294B9DA9199D}

## Informazioni sulla configurazione dell&#39;indicizzazione incrementale script {#section_161D254065E143F3A39F3FC09C400090}

Per utilizzare l&#39;indice con script, utilizzare la pagina Configurazione indice incrementale con script per specificare l&#39;URL di un file di script (un file di testo normale) che si trova sul server. Ad esempio, `https://www.mysite.com/indexlist.txt`. Man mano che il tuo sito cambia, puoi aggiungere blocchi di comando al file di testo manualmente o automaticamente (con uno script attivato dall&#39;arrivo di informazioni da un feed di notizie, un ticker di stock o altro file alterato).

Quando inizia l&#39;indice incrementale di script, il robot di ricerca legge il file di testo ed esegue i nuovi comandi che si trovano in quel file. Per impostazione predefinita, il robot di ricerca elabora solo i nuovi comandi, determinati dalla data del file. A meno che non si controlli **[!UICONTROL Clear Date]** al momento della configurazione di Indice script, il robot di ricerca &quot;ricorda&quot; l&#39;identificatore data del blocco elaborato più di recente.

## Informazioni sul file di script {#section_B312E40539F44C6583B4F9637D428E19}

Il file di script specificato nell’URL è un file di testo normale che si trova sul server. È possibile utilizzare ritorni a capo, feed di linea o entrambi per la sequenza di fine riga. Una riga vuota contiene zero o più caratteri di spazio vuoto seguiti da una sequenza di fine riga. Tutti i comandi sono senza distinzione tra maiuscole e minuscole.

Il file di testo è organizzato in blocchi che descrivono le informazioni utilizzate dal robot di ricerca quando esegue un indice incrementale script.

I blocchi sono ordinati per data, con i blocchi più vecchi nella parte superiore del file di testo e i blocchi più recenti nella parte inferiore. Ogni blocco inizia con un comando data-command a riga singola e un comando di identificatore data e termina con un separatore di riga vuoto, come nell&#39;esempio di blocco seguente (tra sono presenti diversi comandi):

Per tutte le date ordinali inferiori al 10° quando si utilizza lo stile HTTP 1.1 è necessario uno zero iniziale. Ad esempio, il 6 novembre è 06 nov, non 6 nov.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Comando </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>data-command </p> </td> 
   <td colname="col2"> <p>La prima riga di ogni blocco inizia con uno dei due comandi data: </p> <p> 
     <ul id="ul_9C1B229B7F1846C490B853FC34989E77"> 
      <li id="li_31FEF1A7163842BDBB0ABE779D07045A"> <span class="codeph"> date </span> <p>Utilizzare il comando "date" per indicare che l'identificatore data sarà costituito da un giorno, una data, un'ora e un fuso orario. </p> </li> 
      <li id="li_0918D5B090014C1A852CB80BB7C2867C"> <span class="codeph"> secondi  </span> <p>Utilizza <span class="codeph"> secondi </span> per indicare che l’identificatore data sarà costituito da un’ora in secondi epoch (ad esempio, 784111777). Quando utilizzi <span class="codeph"> secondi </span>, assicurati che il numero di secondi aumenti tra i blocchi. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>identificatore data </p> </td> 
   <td colname="col2"> <p>Il comando <span class="codeph"> identificatore data </span> registra in genere la data e l'ora ordinali (comando data) o l'ora in secondi epoch (comando secondi) in cui le informazioni sul blocco sono state aggiunte al file. Ad esempio: </p> <p> <code> date&nbsp;Sun,&nbsp;06&nbsp;Nov&nbsp;1994&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.1&nbsp;style) 
      date&nbsp;Sunday,&nbsp;06-Nov-94&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.0&nbsp;style) 
      date&nbsp;Sun&nbsp;Nov&nbsp;6&nbsp;08:49:37&nbsp;1994&nbsp;(Unix&nbsp;asctime()&nbsp;date&nbsp;style) 
      seconds&nbsp;784111777&nbsp;(Unix&nbsp;epoch-seconds&nbsp;style) </code> </p> <p>Per tutte le date ordinali inferiori al 10° quando si utilizza lo stile HTTP 1.1 è necessario uno zero iniziale. Ad esempio, il 6 novembre è 06 nov, non 6 nov. </p> <p>Il robot di ricerca "ricorda" l'identificatore della data del blocco elaborato più di recente e indicizza solo le informazioni che considera "più recenti". (Il tempo reale non ha importanza per il robot di ricerca. Invece, il tempo in relazione ad altri tempi elaborati in precedenza è ciò che conta.) </p> <p>Dopo che il robot di ricerca legge un blocco con un identificatore di data alle 10:00, per esempio, non legge alcun blocco che registra i tempi prima delle 10:00 p.m., indipendentemente da quando viene eseguito il funzionamento dell'indice. Nel peggiore dei casi, potresti erroneamente inserire l’anno "2040" invece di "2004" nel tuo identificatore data. In questo caso, il robot di ricerca indicizza il blocco 2040 durante l'operazione di indicizzazione successiva e poi rifiuta di leggere qualsiasi altro blocco di informazioni (a meno che non si tratti di un post-date 2040). In questo caso, rimuovi dal file di testo tutti i blocchi elaborati in precedenza, fai clic su <span class="uicontrol"> Cancella data </span>, quindi invialo in diretta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>riga commento </p> </td> 
   <td colname="col2"> <p>Inizia le righe del commento con il carattere "#". </p> <p>Ciascuna riga di commento deve essere una riga propria; non è possibile digitare commenti di fine riga. </p> <p>Una riga di commento non è considerata una riga vuota. Può anche essere visualizzato in qualsiasi punto di un blocco, anche prima di un comando data o secondi come nell'esempio seguente: </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;#Added&nbsp;by&nbsp;Cathy&nbsp;Read&nbsp;after&nbsp;the&nbsp;Y2K&nbsp;seminar 
      &nbsp;&nbsp;&nbsp;&nbsp;date&nbsp;Mon,&nbsp;29&nbsp;Dec&nbsp;1999&nbsp;09:32:20&nbsp;GMT&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>action-command </p> </td> 
   <td colname="col2"> <p>Ogni blocco di testo può contenere tutti i comandi di azione desiderati. Le seguenti opzioni di comando azione corrispondono a quelle per l'indicizzazione incrementale standard: </p> <p> 
     <ul id="ul_8E1435350A0F416BB8F7826CD3886E74"> 
      <li id="li_22181666628C48A28A6A0BA1F7CA8E77"> 
       <code>
         add 
       </code> <p>Utilizza con URL. Il robot di ricerca indicizza solo gli URL specificati modificati dall'ultima operazione di indicizzazione. Inoltre, il robot di ricerca segue i collegamenti contenuti in documenti specifici e indicizza solo i documenti che sono cambiati. </p> <p>Puoi seguire l’URL con 
        <code>
          nofollow 
        </code> o 
        <code>
          noindex 
        </code> parole chiave come nell'esempio seguente: </p> <p> <code> add&amp;nbsp;https://www.mydomain.com/&amp;nbsp;noindex </code> </p> </li> 
      <li id="li_8E47BF07DB24417083883F5BF40D6B9E"> 
       <code>
         update 
       </code> <p>Utilizza con maschera URL. Il robot di ricerca trova e aggiorna tutti i documenti che corrispondono alla maschera URL specificata. </p> <p>Puoi seguire l’URL con 
        <code>
          nofollow 
        </code> o 
        <code>
          noindex 
        </code> parole chiave come nell'esempio seguente: </p> <p> <code> update&amp;nbsp;https://www.mydomain.com/products/ </code> </p> </li> 
      <li id="li_B3EC8B1670D54F66A1D8411A694EF7E4"> 
       <code>
         include 
       </code> o 
       <code>
         exclude 
       </code> <p>Utilizza con maschera URL. Il robot di ricerca trova e indicizza ("include") o ignora i documenti ("escludi") in base al tipo di maschera specificato. </p> <p>Ad esempio, </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/products/household/lightbulbs*.html </code> </p> <p> oppure  </p> <p> <code> exclude&amp;nbsp;https://www.mydomain.com/archive/ </code> </p> </li> 
      <li id="li_050B54B735F0475E93806455FA6DC6A5"> 
       <code>
         include-date 
       </code> o 
       <code>
         exclude-date 
       </code> <p>Utilizza con maschera URL. Il robot di ricerca trova e indicizza ("include") o ignora i documenti ("escludi") in base sia all'URL che alla data dei documenti. Sono disponibili i seguenti tipi di maschere: </p> <p> 
        <ul id="ul_23A15CB492214B86BE84D8E6EA1820AE"> 
         <li id="li_0C7051AC3B5A4C57A3E477F7B6246611"> 
          <code>
            include-days NNN 
          </code> <p>Il robot di ricerca indicizza tutti i documenti che corrispondono alla maschera URL specificata e sono giorni NNN o più vecchi. </p> <p>Puoi seguire la maschera URL con le parole chiave 
           <code>
             nofollow 
           </code> 
           <code>
             noindex 
           </code> e/o 
           <code>
             server-date 
           </code>. </p> </li> 
         <li id="li_983A10E2ED5D434EA9031F32143F4EF4"> 
          <code>
            include-date YYYY-MM-DD 
          </code> <p> Il robot di ricerca indicizza tutti i documenti che corrispondono alla maschera URL specificata e sono vecchi o precedenti alla data AAAA-MM-GG, dove "AAAA" è l'anno a 4 cifre, "MM" è il mese a una o due cifre (1-12), e "GG" è il giorno a una o due cifre (1-31). </p> <p>Puoi seguire la maschera URL con le parole chiave 
           <code>
             nofollow 
           </code> 
           <code>
             noindex 
           </code> e/o 
           <code>
             server-date 
           </code>. </p> </li> 
         <li id="li_733CE1B748024CECA7FBE00D7BC7B88A"> 
          <code>
            exclude-days NNN 
          </code> <p> Disattiva l’indicizzazione di tutti i documenti che corrispondono alla maschera URL specificata e sono giorni NNN o più vecchi. </p> <p>Puoi seguire la maschera URL con la parola chiave 
           <code>
             server-date 
           </code>. </p> </li> 
         <li id="li_90056A0B96CC4DA3854711860A15CE89"> 
          <code>
            exclude-date YYYY-MM-DD 
          </code> <p>Disabilita l’indicizzazione di tutti i documenti che corrispondono alla maschera URL specificata e che hanno la data in formato AAAA-MM-GG o precedente. </p> <p>Puoi seguire la maschera URL con la parola chiave 
           <code>
             server-date 
           </code>. </p> </li> 
        </ul> </p> </li> 
      <li id="li_AA78F22B60FE4535BE73BA87A8992C08"> 
       <code>
         delete 
       </code> <p>Specifica gli URL. Il robot di ricerca rimuove dall'indice i documenti identificati dall'URL. </p> </li> 
      <li id="li_9C63061568AA4D57A4FEBCF6DB9194EC"> 
       <code>
         deletemask 
       </code> <p>Il robot di ricerca rimuove dall'indice i documenti che corrispondono alla maschera URL specificata. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulta anche [Informazioni sulle maschere URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

## Esempio di file script {#section_9F580F20E7214751B157A28B392BD64E}

Nell’esempio di file di script seguente, il robot di ricerca elabora i blocchi purché la data specifichi la data dopo la data dell’identificatore data del blocco elaborato più di recente. In questo caso, si verificano le seguenti operazioni di indicizzazione:

* Elimina `y2k-problems.html` dall&#39;indice.
* Aggiunge `no-y2k-problems.html` all&#39;indice di ricerca e non segue nessuno dei collegamenti per `no-y2k-problems.html`.

* Durante la ricerca per indicizzazione, escludi gli URL che corrispondono a `housewares.htm` e `lightfixtures.htm`l dall&#39;indice di ricerca.

* Includi tutte le altre directory e documenti in `www.mydomain.com`.
* Aggiorna tutti i documenti all&#39;interno delle directory `products` e `information`, eseguendo la ricerca per indicizzazione e indicizzando tutti i collegamenti sussidiari modificati dall&#39;ultima operazione di indicizzazione.

* Durante la ricerca per indicizzazione, escludi gli URL nella sezione `archive` del sito web se sono datati il 1° gennaio 1999 o prima di tale data.
* Escludi dall’indice di ricerca gli URL che corrispondono a `housewares.html` e `lightfixtures.html`.

* Indice i file nella directory `help`, ma non eseguire ricerche per indicizzazione o indicizzare i collegamenti di tali file.
* Esegui la ricerca per indicizzazione e indicizza tutti gli altri file rilevati per `www.mydomain.com`.

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

## Configurazione di un indice incrementale script {#task_05AE040FE75E40FFAA5E10B6B6D4D255}

È possibile specificare uno script creato che scrive, aggiorna e mantiene un indice incrementale senza la necessità di effettuare l&#39;accesso. Il robot di ricerca legge le istruzioni dal file di testo ospitato sul server per eseguire l&#39;indice incrementale.

**Per configurare un indice incrementale con script**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Configuration]**.
1. Nella pagina **[!UICONTROL Scripted Incremental Index Configuration]** , immetti l’URL dello script del file di testo sul server.**[!UICONTROL Script File URL]**

   Consultare [Informazioni sull&#39;indice con script](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D).
1. (Facoltativo) Controllare **[!UICONTROL Clear Date]** se non si desidera che il robot di ricerca &quot;ricordi&quot; l&#39;identificatore data del blocco elaborato più di recente.

   Per impostazione predefinita, il robot di ricerca elabora solo i nuovi blocchi di comandi presenti nel file di testo, determinati dalla data del file. Se non si desidera impostare il valore predefinito, selezionare **[!UICONTROL Clear Date]**.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Impostazione della pianificazione dell&#39;indice incrementale script per un sito web live {#task_B3A87AC4AC784507859C23B9062BA11C}

È possibile pianificare l&#39;indicizzazione incrementale script in modo che avvenga a intervalli regolari durante l&#39;intera giornata.

L&#39;ora di base selezionata è locale in base al fuso orario configurato in Impostazioni account.

Consulta [Configurazione delle impostazioni account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

I server web sono spesso programmati per la manutenzione nel bel mezzo della notte. Se il server è inattivo durante un&#39;ora di indicizzazione pianificata, il processo di indicizzazione non riuscirà. Assicurati di selezionare un’ora del giorno in cui il server web è disponibile.

La pianificazione dell&#39;indice si applica solo al tuo indice live; non è possibile pianificare indici incrementali in sequenza.

**Per impostare la pianificazione incrementale degli indici script per un sito web live**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Schedule]**.
1. Nella pagina **[!UICONTROL Scripted Incremental Index Schedule]**, selezionare nell&#39;elenco a discesa **[!UICONTROL Read the Scripted Incrementally Indexing File]** la frequenza con cui si desidera eseguire il file di testo dell&#39;indice incrementale script, in ore o minuti.
1. Nell&#39;elenco a discesa **[!UICONTROL Base Time]**, selezionare l&#39;ora di inizio quando si desidera rigenerare un nuovo indice incrementale con script.
1. Clic **[!UICONTROL Save Changes]**.

## Esecuzione di un indice incrementale script di un sito web live o di staging {#task_6E6FC76EE1E84A5FADB3B67AD7B1DACB}

È possibile utilizzare l&#39;Indice incrementale script per indicizzare &quot;parti&quot; del sito web live o in staging, ad esempio una raccolta di pagine modificate di frequente, il tutto senza la necessità di accedere.

Per utilizzare questa funzione, assicurarsi di aver configurato un file di testo di indice incrementale con script.

Vedere [Configurazione di un indice incrementale con script](../c-about-index-menu/c-about-scripted-index.md#task_05AE040FE75E40FFAA5E10B6B6D4D255).

**Per eseguire un indice incrementale script di un sito web live o in staging**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Index]**.
   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Index]**.

1. Clic **[!UICONTROL Scripted Index Now]**.
1. (Facoltativo) Se si sono verificati errori di indicizzazione, fai clic su **[!UICONTROL View Errors]** per visualizzare il registro associato.

## Visualizzazione del registro dell&#39;indice incrementale script di un sito web live o in staging {#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7}

Al termine di un indice live con script completo o di un indice con script completo in fase, puoi visualizzare il registro associato per risolvere eventuali errori.

Non puoi esportare i registri né salvarli. Tuttavia, il registro rimane disponibile per la visualizzazione fino a quando non si verifica il nuovo indice.

**Per visualizzare il registro dell&#39;indice incrementale di un sito web live o in staging**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di log, in alto o in basso, effettua una delle seguenti operazioni:

   * Utilizza le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi all’interno del registro.

   * Utilizza le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare la visualizzazione.

