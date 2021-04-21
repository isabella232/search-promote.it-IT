---
description: È possibile ignorare l’espansione dei risultati della query di ricerca.
solution: Target
title: Informazioni sulle sostituzioni di espansione delle query
topic-legacy: Linguistics,Site search and merchandising
uuid: dfe18004-b8fd-4889-b01c-72a3b0c82b9c
exl-id: 6157ffcb-e696-419a-acb5-2076c12a6763
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 0%

---

# Informazioni sulle sostituzioni di espansione delle query{#about-query-expansion-overrides}

È possibile ignorare l’espansione dei risultati della query di ricerca.

## Utilizzo delle sostituzioni di espansione delle query {#concept_6895B469B0E044299E93361BFA06B554}

Quando configuri una sostituzione di espansione della query, crea un set di &quot;regole&quot;. Ogni regola dice, essenzialmente, &quot;Non espandere `<this>` in `<that>` al momento della ricerca&quot; dove `<this>` è una parola o una frase di testo semplice e `<that>` è una parola o una frase di testo o una classificazione.

>[!NOTE]
>
>Per impostazione predefinita, questa funzione non è abilitata in Search&amp;Promote. Contatta il supporto tecnico per attivare la funzione. Dopo aver abilitato la funzione di sovrascrittura dell’espansione delle query, devi &quot;attivarla&quot; nell’interfaccia utente.

**Funzionamento dell’override di espansione query**

Quando un valore di Testo e Termine viene specificato nella pagina Aggiungi sostituzioni di espansione query, il codice agisce sull&#39;associazione specifica. Quando un tipo di classificazione è specificato come Termine, ad esempio Dizionari o Forms Word alternativo, il valore Do Not Expand non viene convertito in alcun modulo creato dalla classificazione indicata.

Ad esempio, supponi di avere la seguente definizione:

`Do Not Expand = "dog"`

`Type = Text`

`Term = "dogs"`

Una query di ricerca per &quot;cane&quot;, che si espande per includere &quot;cane&quot; e &quot;cani&quot; attraverso Alternate Word Forms, non includerebbe &quot;cani&quot;.

Tuttavia, se la definizione era la seguente:

`Do Not Expand = "dog"`

`Type = Alternate Word Forms`

La query non include &quot;cane&quot; o &quot;cani&quot; (la disponibile Forms di parole alternative per &quot;cane&quot;).

Puoi specificare più termini, più classificazioni o entrambi. Tuttavia, se si seleziona Tutto come Tipo, qualsiasi elenco a più termini viene compresso in una sola voce &quot;Tutto&quot;.

Se le voci di testo e classificazione sono miste in una regola, vengono riorganizzate nell’interfaccia utente per mostrare prima i valori di testo. Tuttavia, ciò non implica né influisce sull&#39;ordine di valutazione al momento della ricerca.

I termini di testo vengono convalidati per rimuovere i riferimenti privi di significato. In altre parole, confronta il termine con il valore Do Not Expand e rimuove il termine in caso di corrispondenza. Inoltre, i valori dei termini duplicati, testo o classificazione, vengono rimossi.

Se aggiungi una nuova regola con un valore Do Not Expand che replica una definizione precedente, i Termini della nuova definizione vengono aggiunti all&#39;originale.

## Configurazione delle sostituzioni di espansione della query {#task_A087354A509D4997BA275186C224160E}

Definizione e aggiunta di un override di espansione query in Search&amp;Promote.

<!-- 

t_configuring_query_expansion_overrides.xml

 -->

>[!NOTE]
Per impostazione predefinita, questa funzione non è abilitata in Search&amp;Promote. Contatta il supporto tecnico per attivare la funzione. Dopo aver abilitato la funzione di sovrascrittura dell’espansione delle query, devi &quot;attivarla&quot; nell’interfaccia utente. I primi passi sotto delineano come farlo.

**Per configurare le sostituzioni dell’espansione delle query**

1. In Search&amp;Promote, fai clic su **Impostazioni** > **Utente** > **Visualizza ruoli**.
1. Nella colonna Azioni della tabella della pagina Visualizza ruoli fare clic su **Modifica** a destra del ruolo a cui si desidera concedere l&#39;accesso a Sostituzioni espansione query nel menu Linguistica.
1. Nella pagina Modifica ruolo espandere la struttura Linguistica.
1. Controlla **Sostituzioni espansione query**, quindi fai clic su **Salva modifiche**.
1. Fare clic su **LinguStatistics** > **Overrides di espansione delle query**.
1. Fai clic su **Aggiungi sostituzioni di espansione della query**.
1. Nella pagina Aggiungi sostituzioni di espansione della query impostare le opzioni desiderate.

   <!-- 
   
   r_query_expansion_override_definitions.xml
   
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
      <td colname="col1"> <p>Non espandere </p> </td> 
      <td colname="col2"> <p>Specifica la parola o la frase che non si desidera espandere. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> <p>Selezionare <b>Testo</b> per specificare un'associazione di parole o frasi specifica. In alternativa, selezionare una classificazione per specificare che la parola o la frase Do Not Expand non viene convertita tramite la classificazione selezionata. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Termine </p> </td> 
      <td colname="col2"> <p>Disponibile solo se come tipo è stato selezionato <b>Testo</b>. Specifica la parola o la frase da escludere dall'espansione della ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Azione </p> </td> 
      <td colname="col2"> <p> Fare clic su <b>+</b> o <b>-</b> per aggiungere o eliminare rispettivamente i Termini alla definizione. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Al termine, fai clic su **Aggiungi**.

   Nella pagina Definizioni di sostituzione dell’espansione della query è possibile modificare o eliminare le definizioni aggiunte.
1. Per visualizzare in anteprima i risultati delle aggiunte, fai clic su **rigenera l&#39;indice del sito in staging** nella casella blu per ricostruire rapidamente l&#39;indice del sito web in staging.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **Live**.

      Vedere [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)

   * Fai clic su **Push Live**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)
