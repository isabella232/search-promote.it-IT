---
description: È possibile definire frasi comuni utilizzate sul sito web in modo che, quando un cliente inserisce una query di ricerca, non debba inserire virgolette intorno a una delle frasi definite.
solution: Target
title: Informazioni sulle frasi comuni
topic: Linguistics,Site search and merchandising
uuid: 0f980a22-d826-4476-97de-0e9c14549bc8
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 1%

---


# Informazioni sulle frasi comuni{#about-common-phrases}

È possibile definire frasi comuni utilizzate sul sito web in modo che, quando un cliente inserisce una query di ricerca, non debba inserire virgolette intorno a una delle frasi definite.

## Utilizzo di frasi comuni {#concept_4946E53586DF492EAEB1B7F757FD440F}

>[!NOTE]
>
>La funzione Common Phrase non viene visualizzata nell&#39;interfaccia utente perché non è abilitata per impostazione predefinita. Contatta il supporto tecnico per attivare questa funzione.

Le frasi comuni sono una raccolta di frasi con più parole riconosciute durante la ricerca di un cliente. Tratta le frasi come un gruppo combinato di parole invece che singole parole. Quando un cliente inserisce una query di ricerca nel sito web, può identificare delle frasi circondando i termini con virgolette doppie, come &quot;Oceano Pacifico&quot;. Tuttavia, quando si aggiungono gruppi di frasi comuni, i passaggi di virgolette vengono eseguiti automaticamente per il cliente, in quanto trova frasi corrispondenti nella query di ricerca.

Ad esempio, supponiamo che un cliente del sito web immetta la seguente query di ricerca:

`hotels near the pacific ocean`

Senza l&#39;aggiunta di virgolette intorno a `pacific ocean`, la ricerca del cliente restituisce i risultati per gli hotel vicino a qualsiasi oceano nel mondo, che non è quello che il cliente intendeva.

Tuttavia, quando aggiungi la frase comune &quot;Oceano Pacifico&quot;, la relativa query di ricerca viene automaticamente convertita nella seguente:

`hotels near the "pacific ocean"`

L’uso di Frasi comuni non impedisce ai clienti di utilizzare esplicitamente virgolette intorno a frasi di parole, ma semplicemente aggiunge virgolette, quando tali frasi definite vengono trovate nella loro query di ricerca.

Questa espansione della query di ricerca si applica ai parametri CGI di ricerca back-end `sp_q` e `sp_q_#`,

Vedi le righe 25, 26 e 32 della tabella in [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

## Aggiunta di un gruppo di frasi comuni {#task_35C84FABCD9042C5B48C5C788B752871}

È possibile aggiungere gruppi di frasi comuni per garantire che le query di ricerca restituiscano con precisione pagine web con tutte le parole, nell’ordine esatto e in prossimità, digitate da un cliente.

Quando si aggiungono gruppi di frasi comuni, è possibile utilizzare la funzione Trova nella pagina principale Gruppo di frasi comuni. La funzione Trova consente di cercare una frase esistente e di individuare il gruppo in cui si trova.

Vedere [Ricerca di gruppi che contengono parole particolari in una frase](../c-about-linguistics-menu/c-about-common-phrases.md#task_20714969274740A7BB4DC71E705EA15E).

**Per aggiungere un gruppo di frasi comuni**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella pagina [!DNL Common Phrases Groups], fai clic su **Aggiungi gruppo di frasi**.
1. Nella pagina [!DNL Add Common Phrase Group] , imposta le opzioni desiderate e aggiungi tutte le frasi che compongono il gruppo.

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
      <td colname="col2"> <p>Obbligatorio. </p> <p>Nome univoco del gruppo di frasi comuni. </p> <p>Se successivamente modifichi un gruppo di frasi comuni, tieni presente che non è possibile modificare il nome del gruppo. Per modificare il Nome gruppo, utilizza la funzione <span class="uicontrol"> Rinomina</span> . </p> <p>Vedere <a href="../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB" format="dita" scope="local"> Ridenominazione di un gruppo di frasi comuni</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Note </p> </td> 
      <td colname="col2"> <p>Facoltativo. </p> <p>Aggiungi informazioni relative al gruppo di frasi comuni. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Frasi </p> </td> 
      <td colname="col2"> <p>Obbligatorio. </p> <p>Consente di specificare una frase fino a un massimo di cinque parole. Per regolare l'impostazione massima delle parole, contattare il supporto tecnico. </p> <p>Ogni frase immessa deve essere univoca all’interno di qualsiasi gruppo di frasi comuni. </p> <p>Utilizza le icone più (+) e meno (-) nella colonna Azione per aggiungere la frase inserita o per eliminare una frase. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Fai clic su **Aggiungi**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Verifica di una frase comune {#task_A0C344E051CA45A9A0588242F9DA675D}

Se hai selezionato i campi di metadati da associare a un gruppo di frasi, puoi testare l’espansione di una particolare frase.

Quando si verifica l’espansione di una frase, si cerca una frase esatta rispetto ai campi di metadati associati al gruppo di frasi. La frase viene cercata tra virgolette. Tutti gli altri campi di metadati cercano solo le parole all’interno della frase, senza le virgolette. Supponiamo, ad esempio, di aver testato la frase `audi TT`. I risultati restituiti possono essere visualizzati come segue:

`title|body|field3:"Audi TT" url|desc|keys|target|alt:Audi TT`

**Per testare una frase comune**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella pagina [!DNL Common Phrases Groups], nella frase **Test che contiene** campo di testo, immetti la frase di cui desideri verificare l’espansione dei metadati.
1. Clic **[!UICONTROL Test]**.

   I risultati dell’espansione vengono visualizzati nella casella di testo.
1. (Facoltativo) Trascinare l’angolo inferiore destro della casella di testo per espandere l’area di visualizzazione.

## Ricerca di gruppi che contengono parole particolari in una frase {#task_20714969274740A7BB4DC71E705EA15E}

È possibile utilizzare [!DNL Find] per cercare parole specifiche in una frase tra tutti i gruppi esistenti aggiunti.

Quando si utilizza Trova, vengono individuate le seguenti posizioni:

* Dove si trova la stessa frase tra tutti i gruppi.
* Qualsiasi parola nella frase tra tutti i gruppi, indipendentemente dalla parola ordine e vicinanza nella frase.

Vedere anche [Modifica di un gruppo di frasi comuni](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61).

**Per trovare gruppi che contengono parole particolari in una frase**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella pagina [!DNL Common Phrases Groups] , immetti una frase nel campo di testo **[!UICONTROL Find groups with phrases that contain]** .
1. Clic **[!UICONTROL Find]**.

   I risultati vengono visualizzati nella casella di testo.
1. (Facoltativo) Effettua una o più delle seguenti operazioni:

   * Trascinare l&#39;angolo inferiore destro della casella di testo per espandere l&#39;area di visualizzazione.
   * Nella finestra dei risultati, fai clic su una frase con collegamento ipertestuale per aprire la pagina Modifica gruppo di frasi comuni del gruppo associato.

## Modifica di un gruppo di frasi comuni {#task_5CAC3A133C5342EEAFE55A7EABCBCD61}

È possibile modificare i campi, le note e le frasi esistenti di un gruppo di frasi comune aggiunto. Tuttavia, per modificare il Nome gruppo, è necessario utilizzare la funzione [!DNL Rename] .

Vedere anche [Ridenominazione di un gruppo di frasi comuni](../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB).

**Per modificare un gruppo di frasi comuni**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella pagina [!DNL Common Phrases Groups] , fai clic su **[!UICONTROL Edit]** all’estrema destra del nome di un gruppo.
1. Nella pagina [!DNL Edit Common Phrase Group] , imposta le opzioni desiderate.

   Vedi la tabella delle opzioni in [Aggiunta di un gruppo di frasi comuni](../c-about-linguistics-menu/c-about-common-phrases.md#task_35C84FABCD9042C5B48C5C788B752871).
1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ridenominazione di un gruppo di frasi comuni {#task_168E07C59C0F40989D43E7010EFF22EB}

È possibile modificare il nome di un gruppo di frasi comuni esistente. Tuttavia, se si desidera modificare i campi, le note e le frasi esistenti di un gruppo di frasi comune, è necessario utilizzare la funzione [!DNL Edit].

Consulta [Modifica di un gruppo di frasi comuni](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61) .

**Per rinominare un gruppo di frasi comuni**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella pagina [!DNL Common Phrases Groups] , fai clic su **[!UICONTROL Rename]** all’estrema destra del nome di un gruppo.
1. Nella pagina [!DNL Rename Common Phrase Group] , immetti il nuovo nome del gruppo nel campo di testo **[!UICONTROL Group Name]** .
1. Fare clic su **Rinomina**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Eliminazione di un gruppo di frasi comuni {#task_4106D282A2ED4A27B09EE5A8CAAEDA36}

Puoi eliminare qualsiasi gruppo di frasi comuni aggiunto. Se elimini un gruppo per errore, puoi utilizzare [!DNL History] per ripristinarlo.

Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

**Per eliminare un gruppo di frasi comuni**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** dal menu del prodotto.
1. Nella pagina [!DNL Common Phrases Groups] , fai clic su **[!UICONTROL Delete]** all’estrema destra del nome di un gruppo.
1. Nella pagina [!DNL Delete Common Phrase Group], fai clic su **[!UICONTROL Delete]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

