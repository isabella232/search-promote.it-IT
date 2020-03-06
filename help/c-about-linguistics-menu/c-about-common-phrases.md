---
description: È possibile definire le frasi comuni utilizzate sul sito Web in modo che, quando un cliente inserisce una query di ricerca, non debba inserire virgolette intorno a nessuna delle frasi definite.
seo-description: È possibile definire le frasi comuni utilizzate sul sito Web in modo che, quando un cliente inserisce una query di ricerca, non debba inserire virgolette intorno a nessuna delle frasi definite.
seo-title: Informazioni sulle frasi comuni
solution: Target
title: Informazioni sulle frasi comuni
topic: Linguistics,Site search and merchandising
uuid: 0f980a22-d826-4476-97de-0e9c14549bc8
translation-type: tm+mt
source-git-commit: 8efa90ac2927b263b7d48ccbf25d4b0e917dac79

---


# Informazioni sulle frasi comuni{#about-common-phrases}

È possibile definire le frasi comuni utilizzate sul sito Web in modo che, quando un cliente inserisce una query di ricerca, non debba inserire virgolette intorno a nessuna delle frasi definite.

## Utilizzo di frasi comuni {#concept_4946E53586DF492EAEB1B7F757FD440F}

>[!NOTE]
>
>La funzione Common Phrase non viene visualizzata nell&#39;interfaccia utente perché non è abilitata per impostazione predefinita. Per attivare questa funzione, contattate il supporto tecnico.

Le frasi comuni sono un insieme di frasi di più parole riconosciute durante la ricerca di un cliente. Tratta le frasi come un insieme di parole invece che singole parole. Quando un cliente inserisce una query di ricerca nel sito Web, può identificare le frasi racchiudendo i termini con virgolette doppie, ad esempio &quot;Oceano Pacifico&quot;. Tuttavia, quando si aggiungono gruppi di frasi comuni, i passaggi di quotatura vengono eseguiti automaticamente per il cliente, poiché trova frasi corrispondenti nella query di ricerca.

Ad esempio, supponiamo che un cliente del sito Web immetta la seguente query di ricerca:

`hotels near the pacific ocean`

Senza l&#39;aggiunta di virgolette `pacific ocean`, la ricerca del cliente restituisce risultati per gli hotel vicino a qualsiasi oceano del mondo, che non è quello che il cliente intendeva.

Tuttavia, quando si aggiunge la frase comune &quot;Oceano Pacifico&quot;, la query di ricerca viene automaticamente convertita nel seguente:

`hotels near the "pacific ocean"`

L&#39;uso di Common Phrases non impedisce ai clienti di utilizzare in modo esplicito le virgolette intorno a frasi di parole, ma aggiunge semplicemente citazioni, quando queste frasi definite vengono trovate nella loro query di ricerca.

Questa espansione della query di ricerca si applica ai parametri CGI di ricerca di back-end `sp_q` e `sp_q_#`,

Consultate le righe di tabella 25, 26 e 32 nei parametri [CGI di ricerca](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)back-end.

## Aggiunta di un gruppo di frasi comuni {#task_35C84FABCD9042C5B48C5C788B752871}

È possibile aggiungere Gruppi di frasi comuni per garantire che le query di ricerca restituiscano con precisione pagine Web con tutte le parole digitate da un cliente nell&#39;ordine esatto e nella prossimità.

Quando aggiungete Gruppi di frasi comuni, potete utilizzare la funzione Trova nella pagina Gruppo di frasi comuni principale. La funzione Trova consente di cercare una frase esistente e di scoprire in quale gruppo si trova.

Consultate [Ricerca di gruppi che contengono parole particolari in una frase](../c-about-linguistics-menu/c-about-common-phrases.md#task_20714969274740A7BB4DC71E705EA15E).

**Per aggiungere un gruppo di frasi comuni**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella [!DNL Common Phrases Groups] pagina, fate clic su **Aggiungi gruppo** di frasi.
1. Nella [!DNL Add Common Phrase Group] pagina, impostate le opzioni desiderate e aggiungete tutte le frasi che compongono il gruppo.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Nome gruppo </p> </td> 
      <td colname="col2"> <p>Obbligatorio. </p> <p>Nome univoco del gruppo di frasi comuni. </p> <p>Se modificate un gruppo di frasi comuni in un secondo momento, tenete presente che non potete modificare il nome del gruppo. Per modificare il Nome gruppo, usate la funzione <span class="uicontrol"> Rinomina</span> . </p> <p>Consultate <a href="../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB" format="dita" scope="local"> Ridenominazione di un gruppo</a>di frasi comuni. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Note </p> </td> 
      <td colname="col2"> <p>Facoltativo. </p> <p>Aggiungete informazioni relative al Common Phrase Group. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Frasi </p> </td> 
      <td colname="col2"> <p>Obbligatorio. </p> <p>Consente di specificare una frase fino a un massimo di cinque parole. Per regolare l’impostazione massima della parola, contattate il supporto tecnico. </p> <p>Ogni frase immessa deve essere univoca all'interno di qualsiasi Common Phrase Group. </p> <p>Utilizzate le icone più (+) e meno (-) nella colonna Azione per aggiungere la frase inserita o per eliminare una frase. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Fai clic su **Aggiungi**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Verifica di una frase comune {#task_A0C344E051CA45A9A0588242F9DA675D}

Se avete selezionato dei campi di metadati da associare a un gruppo di frasi, potete verificare l&#39;espansione di una particolare frase.

Quando si prova l&#39;espansione di una frase, si cerca una frase esatta rispetto ai campi di metadati associati al gruppo di frasi. La ricerca della frase è simile alle virgolette. Tutti gli altri campi di metadati ricercano solo le parole all’interno della frase, senza le virgolette. Ad esempio, supponete di aver provato la frase `audi TT`. I risultati restituiti possono essere visualizzati come segue:

`title|body|field3:"Audi TT" url|desc|keys|target|alt:Audi TT`

**Per testare una frase comune**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella [!DNL Common Phrases Groups] pagina, nella frase **Test che contiene** il campo di testo, immettete la frase di cui desiderate verificare l’espansione dei metadati.
1. Clic **[!UICONTROL Test]**.

   I risultati dell&#39;espansione vengono visualizzati nella casella di testo.
1. (Facoltativo) Trascinate l’angolo inferiore destro della casella di testo per espandere l’area di visualizzazione.

## Ricerca di gruppi che contengono parole particolari in una frase {#task_20714969274740A7BB4DC71E705EA15E}

È possibile utilizzare [!DNL Find] per cercare parole specifiche in una frase tra tutti i gruppi esistenti aggiunti.

Quando si utilizza Trova, viene individuato quanto segue:

* Dove la stessa frase esatta si trova tra tutti i gruppi.
* Qualsiasi parola nella frase tra tutti i gruppi, indipendentemente dalla parola ordine e vicinanza nella frase.

Vedere anche [Modifica di un gruppo](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61)di frasi comuni.

**Per trovare gruppi che contengono parole particolari in una frase**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella [!DNL Common Phrases Groups] pagina, nel campo di **[!UICONTROL Find groups with phrases that contain]** testo, immettere una frase.
1. Clic **[!UICONTROL Find]**.

   I risultati vengono visualizzati nella casella di testo.
1. (Facoltativo) Effettuate una o più delle seguenti operazioni:

   * Trascinare l&#39;angolo inferiore destro della casella di testo per espandere l&#39;area di visualizzazione.
   * Nella finestra dei risultati, fate clic su una frase con collegamento ipertestuale per aprire la pagina Modifica gruppo di frasi comuni del gruppo associato.

## Modifica di un gruppo di frasi comuni {#task_5CAC3A133C5342EEAFE55A7EABCBCD61}

È possibile modificare i campi, le note e le frasi esistenti di un gruppo di frasi comuni aggiunto. Tuttavia, per modificare il Nome gruppo, è necessario utilizzare la [!DNL Rename] funzione.

Vedere anche [Ridenominazione di un gruppo](../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB)di frasi comuni.

**Per modificare un gruppo di frasi comuni**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella [!DNL Common Phrases Groups] pagina, fate clic **[!UICONTROL Edit]** all’estrema destra del nome di un gruppo.
1. Nella [!DNL Edit Common Phrase Group] pagina, impostate le opzioni desiderate.

   Vedere la tabella delle opzioni in [Aggiunta di un gruppo](../c-about-linguistics-menu/c-about-common-phrases.md#task_35C84FABCD9042C5B48C5C788B752871)di frasi comuni.
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Ridenominazione di un gruppo di frasi comuni {#task_168E07C59C0F40989D43E7010EFF22EB}

È possibile modificare il nome di un gruppo di frasi comuni esistente. Tuttavia, se si desidera modificare i campi, le note e le frasi esistenti di un gruppo di frasi comuni, è necessario utilizzare la [!DNL Edit] funzione.

Consultate [Modifica di un gruppo](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61) di frasi comuni .

**Per rinominare un gruppo di frasi comuni**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella [!DNL Common Phrases Groups] pagina, fate clic **[!UICONTROL Rename]** all’estrema destra del nome di un gruppo.
1. Nella [!DNL Rename Common Phrase Group] pagina, nel campo di **[!UICONTROL Group Name]** testo, immettete il nuovo nome del gruppo.
1. Fate clic su **Rinomina**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Eliminazione di un gruppo di frasi comuni {#task_4106D282A2ED4A27B09EE5A8CAAEDA36}

Puoi eliminare qualsiasi Common Phrase Group aggiunto. Se eliminate un gruppo per errore, potete usare [!DNL History] per ripristinarlo.

Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

**Per eliminare un gruppo di frasi comuni**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella [!DNL Common Phrases Groups] pagina, fate clic **[!UICONTROL Delete]** all’estrema destra del nome di un gruppo.
1. Sulla [!DNL Delete Common Phrase Group] pagina, fate clic su **[!UICONTROL Delete]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

