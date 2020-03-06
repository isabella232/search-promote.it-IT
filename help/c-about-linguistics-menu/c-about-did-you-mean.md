---
description: Potete configurare l’opzione Did You Mean (Hai voluto dire) in modo che i clienti ricevano suggerimenti per termini di ricerca validi quando hanno provato ricerche che hanno avuto esito negativo. I suggerimenti vengono generati cercando ortografia e digitando le correzioni necessarie per eseguire una ricerca valida.
seo-description: Potete configurare l’opzione Did You Mean (Hai voluto dire) in modo che i clienti ricevano suggerimenti per termini di ricerca validi quando hanno provato ricerche che hanno avuto esito negativo. I suggerimenti vengono generati cercando ortografia e digitando le correzioni necessarie per eseguire una ricerca valida.
seo-title: A Proposito
solution: Target
title: A Proposito
topic: Linguistics,Site search and merchandising
uuid: c5973541-3d6b-4fc9-bad4-66d4d3559fe8
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# A Proposito{#about-did-you-mean}

Potete configurare l’opzione Did You Mean (Hai voluto dire) in modo che i clienti ricevano suggerimenti per termini di ricerca validi quando hanno provato ricerche che hanno avuto esito negativo. I suggerimenti vengono generati cercando ortografia e digitando le correzioni necessarie per eseguire una ricerca valida.

## Configurazione {#task_B539D6A0043547EFB1CA19B67E762371}

Potete definire in che modo [!DNL site search/merchandising] vengono suggeriti i suggerimenti di ricerca quando la query di un cliente restituisce risultati di ricerca minimi o nulli.

<!-- 

t_configuring_did_you_mean.xml

 -->

**Per configurare, intendete**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Did You Mean]** dal menu del prodotto.
1. Nella [!DNL Did You Mean] pagina, nel campo di testo **Rimuovi queste parole dai suggerimenti** , immettete uno spazio o parole separate da riga per filtrare i suggerimenti indesiderati.

   Sono parole nell’indice di ricerca che non vengono visualizzate come termini di ricerca alternativi consigliati. È possibile escludere qualsiasi parola che corrisponda a un pattern mediante l&#39;uso di espressioni regolari. In caso contrario, viene rimossa solo la parola esatta.

1. Impostare le opzioni **Desiderate** .

   <!-- 
   
   r_did_you_mean_options.xml
   
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Opzione </p> </th> 
      <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Algoritmo di suggerimento </p> </td> 
      <td colname="col2"> <p>Consente di regolare la portata del software per trovare suggerimenti. Se un utente commette un errore di una lettera, tutti gli algoritmi presentano gli stessi suggerimenti. Il motivo è che ci vuole solo una modifica per arrivare a un suggerimento funzionante, e tutti gli algoritmi trovano parole vicine all'originale. Tuttavia, quando i termini di ricerca originali non sono simili ai termini esistenti nell'indice, gli <b>Algoritmi di Suggerimento per gli indicatori profondi</b> e <b>cattivi</b> continuano a cercare possibili suggerimenti. Questo scenario è utile se un cliente tenta un nome corretto che è difficile digitare ed esprime i nomi. Tuttavia, se desiderate visualizzare solo suggerimenti simili, potete scegliere l’algoritmo <b>Rapida</b> . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Conteggio predefinito dei suggerimenti da visualizzare </p> </td> 
      <td colname="col2"> <p>Specifica il numero di suggerimenti (0-20) relativi al termine "Did You Mean" che si desidera visualizzare quando la ricerca di un cliente non restituisce alcun risultato. Il valore predefinito è 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lunghezza minima parola suggerimento </p> </td> 
      <td colname="col2"> <p>Prunes intendeva dire termini specificando il numero minimo di lettere per una parola suggerita. </p> <p>Ad esempio, se si imposta il valore su 4, il software non suggerisce una parola lunga 1, 2 o 3 caratteri. Se si specifica un valore pari a 0, non vengono rimosse parole brevi dai suggerimenti dei termini. Se si specifica un valore elevato, in genere non si ottengono suggerimenti per i termini. Il valore predefinito è 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Frequenza minima indice </p> </td> 
      <td colname="col2"> <p> Specifica il numero minimo di volte in cui una parola deve essere visualizzata nell'indice prima che venga inclusa nel dizionario Did You Mean. </p> <p>Non è possibile specificare un numero negativo nel campo. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Cerca termine suggerito se non si ottengono risultati </p> </td> 
      <td colname="col2"> <p>Ricerca automaticamente il primo termine suggerito quando la ricerca di un cliente non genera risultati ed è presente almeno un suggerimento con il termine "Hai". </p> <p>Potete usare i seguenti tag nel modello di presentazione per indicare che la ricerca nel sito/merchandising esegue automaticamente la ricerca di un termine diverso: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> <p>Potete anche mostrare altri suggerimenti qui. </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;There&nbsp;was&nbsp;0&nbsp;matches&nbsp;for&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&nbsp;&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&lt;guided-param&nbsp;gsname="q"&gt;?&nbsp;Here&nbsp;are&nbsp;the&nbsp;results&nbsp;for&nbsp;that&nbsp;search.&nbsp;&nbsp;&nbsp;Or&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestions&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suggerimenti a causa di risultati limitati </p> </td> 
      <td colname="col2"> <p>Se un cliente cerca un termine che genera meno di dieci risultati, il motore di ricerca verifica se ha un suggerimento che può produrre più di 100 risultati. In caso contrario, potete utilizzare i seguenti tag per indicare all'utente che, pur avendo dei risultati, potrebbe essere necessario cercare qualcos'altro: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-low-results&gt; &nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;Search&nbsp;for&nbsp;guided-param&nbsp;gsname="q"&gt;.&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestion&gt;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-low-results&gt;</code> </p> <p> Nello scenario precedente, il numero di suggerimenti è controllato dal valore specificato nel conteggio <span class="uicontrol"> predefinito dei suggerimenti da visualizzare</span>. La soglia bassa e alta sono configurabili dalle opzioni riportate di seguito. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suggerimenti se i risultati iniziali sono inferiori a </p> </td> 
      <td colname="col2"> <p>Controlla il numero di risultati quando il sistema inizia a offrire suggerimenti. </p> <p>Questa opzione viene visualizzata solo quando selezionate <span class="uicontrol"> Crea suggerimenti a causa di risultati</span>ridotti. </p> <p>Il valore predefinito è 10. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Un suggerimento deve generare almeno questo numero di risultati </p> </td> 
      <td colname="col2"> <p>Filtra i suggerimenti che vengono fatti a causa di risultati limitati nella ricerca primaria in base al loro numero di risultati. </p> <p>Questa opzione viene visualizzata solo quando selezionate <span class="uicontrol"> Crea suggerimenti a causa di risultati</span>ridotti. </p> <p>Il valore predefinito è 100. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

