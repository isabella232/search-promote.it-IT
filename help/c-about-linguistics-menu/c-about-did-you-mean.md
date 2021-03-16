---
description: È possibile configurare Did You Signan in modo che i clienti ricevano suggerimenti per termini di ricerca validi quando tentano ricerche non riuscite. I suggerimenti vengono formati cercando ortografia e digitando correzioni ai termini di ricerca che si traducono in una ricerca valida.
solution: Target
title: A Riguardo Intendevi
topic: Linguistica, Ricerca sul sito e merchandising
uuid: c5973541-3d6b-4fc9-bad4-66d4d3559fe8
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 1%

---


# Informazioni su {#about-did-you-mean}

È possibile configurare Did You Signan in modo che i clienti ricevano suggerimenti per termini di ricerca validi quando tentano ricerche non riuscite. I suggerimenti vengono formati cercando ortografia e digitando correzioni ai termini di ricerca che si traducono in una ricerca valida.

## Configurazione intendeva {#task_B539D6A0043547EFB1CA19B67E762371}

Puoi personalizzare il modo in cui [!DNL site search/merchandising] formula i suggerimenti di ricerca quando la query di un cliente restituisce risultati di ricerca minimi o nulli.

<!-- 

t_configuring_did_you_mean.xml

 -->

**Per configurare intendevi**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Did You Mean]** dal menu del prodotto.
1. Nella pagina [!DNL Did You Mean] , nel campo di testo **Rimuovi queste parole da suggerimenti** , immetti spazi o parole separate da riga per filtrare suggerimenti indesiderati.

   Sono parole nell&#39;indice di ricerca che non vengono visualizzate come termini di ricerca alternativi consigliati. È possibile escludere qualsiasi parola che corrisponda a un pattern utilizzando espressioni regolari. In caso contrario, viene rimossa solo la parola esatta.

1. Impostare le opzioni **Did You Mean** desiderate.

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
      <td colname="col2"> <p>Regola la portata del software per trovare suggerimenti. Se un utente commette un errore di una lettera, tutti gli algoritmi presentano gli stessi suggerimenti. Il motivo è che ci vuole solo una modifica per arrivare a un suggerimento funzionante, e tutti gli algoritmi trovano parole vicine all'originale. Ma quando i termini di ricerca originali non sono simili ai termini esistenti nell'indice, gli <b>Profondi</b> e <b>Speller</b> Algoritmi Suggerimenti continuano a cercare possibili suggerimenti. Questo scenario è utile se un cliente prova un nome corretto che è difficile digitare e ne esegue l’audio. Tuttavia, se desideri visualizzare solo suggerimenti simili, puoi scegliere l'algoritmo <b>Quick</b> . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Conteggio predefinito dei suggerimenti da visualizzare </p> </td> 
      <td colname="col2"> <p>Specifica il numero di suggerimenti (0-20) relativi al termine utilizzato per indicare quando la ricerca di un cliente non restituisce alcun risultato. Il valore predefinito è 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lunghezza minima della parola suggerita </p> </td> 
      <td colname="col2"> <p>Prunes intendeva termini specificando il numero minimo di lettere per una parola suggerita. </p> <p>Ad esempio, se imposti il valore su 4, il software non suggerisce una parola lunga 1, 2 o 3 caratteri. Se si specifica un valore pari a 0, non vengono rimosse parole brevi dai suggerimenti dei termini. Se specifichi un valore elevato, in genere non genera alcun suggerimento per i termini. Il valore predefinito è 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Frequenza minima dell'indice </p> </td> 
      <td colname="col2"> <p> Specifica il numero minimo di volte in cui una parola deve essere visualizzata nell'indice prima che venga inclusa nel dizionario Did You Mean. </p> <p>Non è possibile specificare un numero negativo nel campo . </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Cerca il termine suggerito se nessun risultato </p> </td> 
      <td colname="col2"> <p>Ricerca automaticamente il primo termine suggerito quando la ricerca di un cliente non produce risultati ed è presente almeno un suggerimento a termine "Did You Mean". </p> <p>È possibile utilizzare i seguenti tag nel modello di presentazione per indicare che la ricerca/merchandising del sito cerca automaticamente un termine diverso: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> <p>Puoi anche mostrare altri suggerimenti qui. </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;There&nbsp;was&nbsp;0&nbsp;matches&nbsp;for&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&nbsp;&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&lt;guided-param&nbsp;gsname="q"&gt;?&nbsp;Here&nbsp;are&nbsp;the&nbsp;results&nbsp;for&nbsp;that&nbsp;search.&nbsp;&nbsp;&nbsp;Or&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestions&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suggerimenti a causa di risultati bassi </p> </td> 
      <td colname="col2"> <p>Se un cliente cerca un termine che produce meno di dieci risultati, il motore di ricerca controlla se ha un suggerimento che può produrre più di 100 risultati. In caso affermativo, è possibile utilizzare i seguenti tag per indicare all’utente che, pur disponendo di risultati, potrebbe essere utile cercare qualcos’altro: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-low-results&gt; &nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;Search&nbsp;for&nbsp;guided-param&nbsp;gsname="q"&gt;.&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestion&gt;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-low-results&gt;</code> </p> <p> Nello scenario precedente, il numero di suggerimenti è controllato dal valore specificato in <span class="uicontrol"> Conteggio predefinito dei suggerimenti da visualizzare</span>. La soglia bassa e alta sono configurabili dalle opzioni sottostanti. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suggerisci quando i risultati iniziali sono inferiori a </p> </td> 
      <td colname="col2"> <p>Controlla il numero di risultati quando il sistema inizia a offrire suggerimenti. </p> <p>Questa opzione viene visualizzata solo quando si seleziona <span class="uicontrol"> Suggerisci a causa di risultati bassi</span>. </p> <p>Il valore predefinito è 10. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Un suggerimento deve generare almeno questo numero di risultati </p> </td> 
      <td colname="col2"> <p>Filtra i suggerimenti che vengono effettuati a causa di risultati bassi nella ricerca primaria in base al loro conteggio dei risultati. </p> <p>Questa opzione viene visualizzata solo quando si seleziona <span class="uicontrol"> Suggerisci a causa di risultati bassi</span>. </p> <p>Il valore predefinito è 100. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Fai clic su **Salva le modifiche**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

