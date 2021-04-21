---
description: È possibile utilizzare Indice incrementale per indicizzare "parti" del sito web live o di staging, ad esempio una raccolta di pagine modificate di frequente.
solution: Target
subtopic: Incremental Index
title: Informazioni sull'indice incrementale
topic-legacy: Index,Site search and merchandising
uuid: b1ee9b08-dcbe-4ffe-b0b4-d379daaac9b5
exl-id: 41943f84-23f0-434c-8eef-a9075dd5c03d
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 1%

---

# Informazioni su Incremental Index{#about-incremental-index}

È possibile utilizzare Indice incrementale per indicizzare &quot;parti&quot; del sito web live o di staging, ad esempio una raccolta di pagine modificate di frequente.

## Utilizzo dell&#39;indice incrementale {#concept_A7770F0552D14C47B3DDB65DB78FFFEE}

L&#39;esecuzione di un indice incrementale richiede solo pochi secondi ed è utile su siti web a grande capacità che possono richiedere molte ore per l&#39;indicizzazione completa.

Quando si genera un indice incrementale, vengono visualizzate informazioni sullo stato, ad esempio il tempo di avvio, il tempo trascorso e gli errori durante il processo di indicizzazione. Vengono visualizzate anche informazioni sullo stato dell&#39;ultimo indice.

Puoi interrompere o riavviare il processo di indicizzazione incrementale in qualsiasi momento.

Mentre il nuovo indice incrementale viene creato per il sito web live, i clienti possono continuare a cercare il sito utilizzando l&#39;ultimo indice incrementale.

## Configurazione di un indice incrementale di un sito web di staging {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

Puoi configurare quali pagine del sito web desideri includere nell’indice incrementale specificando gli URL del sito web e le maschere URL.

**Per configurare un indice incrementale di un sito web in staging**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Configuration]**.
1. Nella pagina **[!UICONTROL Incremental Index Configuration]**, utilizza i vari campi per specificare quali pagine desideri indicizzare.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Campo </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Aggiungi o aggiorna URL </p> </td> 
      <td colname="col2"> <p>Specifica gli URL. </p> <p>Il robot di ricerca indicizza solo i documenti specificati che sono stati modificati dall'ultima volta che hai indicizzato. </p> <p>Inoltre, il robot di ricerca segue i collegamenti contenuti nei documenti specificati e indicizza solo i documenti modificati. </p> <p>Questo campo deve contenere solo gli URL del documento e non le maschere come nell’esempio seguente: </p> <p> 
        <code>
          https://www.mydomain.com/products/new.html 
        </code> </p> <p>È possibile utilizzare le seguenti parole chiave con l’URL: </p> <p> 
        <ul id="ul_62D1082ACBD547D092B10D72C56A3A1E"> 
          <li id="li_32C2B21DE75C4459908384CC44822F7D"> 
          <code>
            noindex 
          </code> <p>Se non desideri indicizzare il testo nella pagina che corrisponde a un URL specificato, ma desideri seguire i collegamenti della pagina, aggiungi 
            <code>
              noindex 
            </code> dopo l'URL come nell'esempio seguente: </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html noindex 
            </code> </p> <p>Assicurati di separarti 
            <code>
              noindex 
            </code> dall'URL con uno spazio; una virgola non è un separatore valido. </p> </li> 
          <li id="li_33AB62B669084BF7B976F4308715E435"> 
          <code>
            nofollow 
          </code> <p>Se desideri indicizzare il testo nella pagina che corrisponde all’URL specificato, ma non desideri seguire i collegamenti della pagina, aggiungi 
            <code>
              nofollow 
            </code> dopo l'URL come nell'esempio seguente: </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html nofollow 
            </code> </p> <p> Assicurati di separarti 
            <code>
              nofollow 
            </code> dall'URL con uno spazio; una virgola non è un separatore valido. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Trovare e aggiornare le maschere URL </p> </td> 
      <td colname="col2"> <p>Specifica maschere URL semplici: percorso completo, percorso parziale o percorsi che utilizzano caratteri jolly o espressioni regolari. </p> <p>Il robot di ricerca trova tutti i documenti corrispondenti e indicizza solo i documenti che sono cambiati dall'ultima volta che hai indicizzato. </p> <p>Inoltre, il robot di ricerca segue i collegamenti contenuti nei documenti corrispondenti e indicizza solo le pagine che sono state modificate. Ad esempio: </p> <p> 
      <code>
        https://www.mydomain.com/products/household/*.html 
      </code> </p> <p>È inoltre possibile utilizzare espressioni regolari come nell’esempio seguente: </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/household/.*\.html$ 
      </code> </p> <p>Consulta <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari</a>. </p> <p>È inoltre possibile utilizzare le parole chiave 
      <code>
        nofollow 
      </code> e 
      <code>
        noindex 
      </code> come descritto in <span class="uicontrol"> Aggiungi o aggiorna URL </span> sopra. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includere ed escludere le maschere URL </p> </td> 
      <td colname="col2"> <p>Specifica maschere URL semplici da includere o escludere: percorso completo, percorso parziale o percorsi che utilizzano caratteri jolly o espressioni regolari. </p> <p>Il robot di ricerca trova e indicizza ("include") o ignora i documenti ("escludi") in base al tipo di maschera specificato. </p> <p> Quando si indicizza un sito, le indicazioni vengono seguite in ordine di aspetto. Ad esempio, il seguente elenco di maschere: </p> <p> 
      <code>
        include https://www.mydomain.com/products/household/lightbulbs*.html 
      </code> </p> <p> 
      <code>
        exclude https://www.mydomain.com/products/ 
      </code> </p> <p>indicizza le pagine 
      <code>
        lightbulbs1.html 
      </code> e 
      <code>
        lightbulbs2.html 
      </code>. Tuttavia, non indicizza altre pagine elencate nella directory dei prodotti. </p> <p>Una maschera URL che appare per prima ha sempre la precedenza su una che appare successivamente nell’elenco. Inoltre, se il robot di ricerca rileva un documento che corrisponde sia a una maschera di inclusione che a una maschera di esclusione, la maschera elencata per prima ha la precedenza. </p> <p>È inoltre possibile utilizzare le parole chiave 
      <code>
        nofollow 
      </code> e 
      <code>
        noindex 
      </code> come descritto in <span class="uicontrol"> Aggiungi o aggiorna URL </span> sopra. </p> <p>Consulta <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> Informazioni sulle maschere URL</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Includi ed escludi maschere di data </p> </td> 
      <td colname="col2"> <p>Specifica maschere di data di inclusione o esclusione semplici: percorso completo, percorso parziale o percorsi che utilizzano caratteri jolly o espressioni regolari. </p> <p>Il robot di ricerca trova e indicizza ("include") o ignora i documenti ("escludi") in base sia all'URL che alla data dei documenti. </p> <p>È possibile utilizzare i seguenti tipi di maschere data: </p> <p> 
      <ul id="ul_8958ED54C8EF405AA259236595ED3ABA"> 
      <li id="li_0A7841767E004F088CA6FA42E99B9F32"> 
      <code>
        include-days NNN 
      </code> <p>Il robot di ricerca indicizza tutti i documenti che corrispondono alla maschera URL specificata e sono giorni NNN o più vecchi. </p> <p>Puoi seguire la maschera URL con una o più delle seguenti parole chiave: 
        <ul id="ul_22A38D5F38B344ABB02B16EB1865813B"> 
        <li id="li_B89CC37DC2A1428185E86FFCB9DDB193">nofollow </li> 
        <li id="li_C2579B3A338D4AF987C3F518806734B0">noindex </li> 
        <li id="li_0527BF7103F34B83AC3E684069B899F7">data server </li> 
        </ul> </p> <p>Ad esempio, la maschera seguente include tutti i documenti presenti nella cartella /archive/support che sono di 0 giorni o più: </p> <p> 
        <code>
          include-days 0 https://www.mydomain.com/archive/support/ 
        </code> </p> </li> 
      <li id="li_7663ABED40DD4E159F746E4F92BB6407"> 
      <code>
        include-date YYYY-MM-DD 
      </code> <p>Il robot di ricerca indicizza tutti i documenti che corrispondono alla maschera URL specificata e sono vecchi o più della data AAAA-MM-GG. </p> <p>Puoi seguire la maschera URL con una o più delle seguenti parole chiave: </p> <p> 
        <ul id="ul_57BF37A413BB4A4D962863DACE56F395"> 
        <li id="li_88CAB9AB583B4754A5C53478BD1108FF">nofollow </li> 
        <li id="li_999E1CD34FDE4A1B9C332B4AA8C2887D">noindex </li> 
        <li id="li_05646FACF3524D2A9E201A23770E357F"> data server </li> 
        </ul> </p> <p>L’esempio di maschera seguente include tutti i documenti presenti nella cartella /archive/ datata il 25 luglio 2011 o prima di tale data: </p> <p> 
        <code>
          include-date 2011-07-25 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      <li id="li_172692DEDA8744B3AA492701D24C2D80"> 
      <code>
        exclude-days NNN 
      </code> <p>Disabilita l'indicizzazione di tutti i documenti che corrispondono alla maschera URL specificata e sono giorni NNN o più vecchi. </p> <p>Facoltativamente, puoi seguire la maschera URL dalla parola chiave 
        <code>
          server-date 
        </code>. </p> <p>L'esempio di maschera seguente esclude dall'indice tutti i file PDF che hanno 90 giorni o più di età: </p> <p> 
        <code>
          exclude-days 90 *.pdf 
        </code> </p> </li> 
      <li id="li_26078517744D4AECBE1351008926CBAE"> 
      <code>
        exclude-date YYYY-MM-DD 
      </code> <p>Disabilita l'indicizzazione di tutti i documenti che corrispondono alla maschera URL specificata e sono vecchi o precedenti alla data AAAA-MM-GG. </p> <p>Facoltativamente, puoi seguire la maschera URL dalla parola chiave 
        <code>
          server-date 
        </code>. </p> <p>L'esempio di maschera seguente esclude tutti i documenti presenti nella cartella /archive/ datata il 23 aprile 2004 o prima di tale data: </p> <p> 
        <code>
          exclude-date 2004-04-23 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      </ul> </p> <p>Consulta <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_F4F1F58A646F4A86B8650EC46FDCEF66" type="concept" format="dita" scope="local"> Informazioni sulle maschere di data</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Eliminare gli URL </p> </td> 
      <td colname="col2"> <p>Specifica gli URL. </p> <p>Il robot di ricerca trova ed elimina i documenti specificati dall'indice di ricerca. Se una pagina specificata è già nell'indice di ricerca, il robot la elimina prima di aggiungere o aggiornare altre pagine. </p> <p>Questo campo deve contenere solo gli URL del documento e non le maschere. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Trovare ed eliminare le maschere URL </p> </td> 
      <td colname="col2"> <p>Specifica maschere URL semplici: percorso completo, percorso parziale o quelle che utilizzano caratteri jolly o espressioni regolari. </p> <p>Se la maschera URL specificata corrisponde alle pagine nell'indice di ricerca, il robot di ricerca elimina le pagine prima di aggiungere o aggiornare altre pagine. Ad esempio: </p> <p> 
      <code>
        https://www.mydomain.com/products/1998/household/* 
      </code> </p> <p>È inoltre possibile utilizzare espressioni regolari come nell’esempio seguente: </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/199[567]/.*$ 
      </code> </p> <p>Consulta <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Espressioni regolari</a>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Impostazione della pianificazione incrementale dell&#39;indice per un sito web live {#task_2A46BA189ECC4317A9D5C6E99A336F33}

È possibile selezionare la frequenza dell&#39;indice incrementale e il tempo di base utilizzati per eseguire la ricerca per indicizzazione e aggiornare l&#39;indice incrementale.

L&#39;ora selezionata è locale in base al fuso orario configurato in Impostazioni account.

Consulta [Configurazione delle impostazioni account](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

I server web sono spesso programmati per la manutenzione nel bel mezzo della notte. Se il server è inattivo durante un&#39;ora di indicizzazione pianificata, il processo di indicizzazione non riuscirà. Assicurati di selezionare un’ora del giorno in cui il server web è disponibile.

La pianificazione dell&#39;indice si applica solo al tuo indice live; non è possibile pianificare gli indici di staging.

**Impostazione della pianificazione incrementale dell&#39;indice per un sito web live**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Schedule]**.
1. Nella pagina **[!UICONTROL Incremental Index Schedule]** , seleziona la frequenza di indicizzazione nell’elenco a discesa **[!UICONTROL Incrementally Index]** in ore o minuti.
1. Nell&#39;elenco a discesa **[!UICONTROL Base Time]**, selezionare l&#39;ora di inizio quando si desidera rigenerare un nuovo indice incrementale.
1. Clic **[!UICONTROL Save Changes]**.

## Esecuzione di un indice incrementale di un sito web live o in staging {#task_9BFB6157F3884B2FAECB7E0E9CA318CB}

È possibile utilizzare Indice incrementale per indicizzare &quot;parti&quot; del sito web live o di staging, ad esempio una raccolta di pagine modificate di frequente.

**Per eseguire un indice incrementale di un sito web live o in staging**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Index]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Index]**.

1. Clic **[!UICONTROL Incremental Index Now]**.
1. (Facoltativo) Se si sono verificati errori di indicizzazione, fai clic su **[!UICONTROL View Errors]** per visualizzare il registro associato.

## Visualizzazione del registro dell&#39;indice incrementale di un sito web live o in staging {#task_E668E1F1240C476DAA1CA783DC728232}

Al termine di un indice incrementale attivo o di un indice incrementale pianificato, puoi visualizzare il registro associato per risolvere eventuali errori.


Non puoi esportare i registri né salvarli. Il registro rimane disponibile per la visualizzazione fino a quando non si verifica il nuovo indice.

**Per visualizzare il registro dell&#39;indice incrementale di un sito web live o in staging**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di log, in alto o in basso, effettua una delle seguenti operazioni:

   * Utilizza le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi all’interno del registro.

   * Utilizza le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare la visualizzazione.
