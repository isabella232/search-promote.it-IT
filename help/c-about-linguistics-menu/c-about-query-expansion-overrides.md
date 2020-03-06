---
description: È possibile ignorare l'espansione dei risultati della query di ricerca.
seo-description: È possibile ignorare l'espansione dei risultati della query di ricerca.
seo-title: Informazioni sulle sostituzioni di espansione delle query
solution: Target
title: Informazioni sulle sostituzioni di espansione delle query
topic: Linguistics,Site search and merchandising
uuid: dfe18004-b8fd-4889-b01c-72a3b0c82b9c
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Informazioni sulle sostituzioni di espansione delle query{#about-query-expansion-overrides}

È possibile ignorare l&#39;espansione dei risultati della query di ricerca.

## Utilizzo delle sostituzioni di espansione delle query {#concept_6895B469B0E044299E93361BFA06B554}

Quando configurate una sostituzione di espansione query, create un set di &quot;regole&quot;. Ogni regola dice, essenzialmente, &quot;Non espandersi `<this>` al momento della ricerca&quot;, dove `<that>` è una parola o una frase di testo semplice, e `<this>` `<that>` è una parola o una frase di testo, o una classificazione.

>[!NOTE]
>
>Per impostazione predefinita, questa funzione non è abilitata in Search&amp;Promote. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. Una volta attivata la funzione di esclusione dell&#39;espansione delle query, è necessario &quot;attivarla&quot; nell&#39;interfaccia utente.

**Funzionamento dell&#39;override di espansione query**

Quando un valore di testo e termine viene specificato nella pagina Aggiungi sostituzioni di espansione query, il codice agisce sul accoppiamento specifico. Quando un tipo di classificazione è specificato come Termine, ad esempio Dizionari o Moduli Word alternativi, il valore Non espandere non viene convertito in nessun modulo creato dalla classificazione indicata.

Ad esempio, supponete di avere la seguente definizione:

`Do Not Expand = "dog"`

`Type = Text`

`Term = "dogs"`

Una query di ricerca per &quot;cane&quot;, che si espande per includere &quot;cane&quot; e &quot;cani&quot; tramite Alternate Word Forms, non includerebbe &quot;cani&quot;.

Tuttavia, se la definizione era la seguente:

`Do Not Expand = "dog"`

`Type = Alternate Word Forms`

La query non include &quot;cane&quot; o &quot;cani&quot; (i moduli alternativi per &quot;cane&quot; disponibili per Word Forms).

Potete specificare più termini, più classificazioni o entrambi. Tuttavia, se selezionate All come Tipo, qualsiasi elenco a più termini viene compresso in una sola voce &quot;All&quot;.

Se le voci di testo e classificazione sono miste in una regola, vengono riorganizzate nell&#39;interfaccia utente per mostrare prima i valori di testo. Tuttavia, ciò non implica né incide sull&#39;ordine di valutazione al momento della ricerca.

I termini di testo vengono convalidati per rimuovere i riferimenti privi di significato. In altre parole, confronta il termine con il valore Non espandere e rimuove il termine in presenza di una corrispondenza. Inoltre, i valori di termine duplicati, testo o classificazione, vengono rimossi.

Se si aggiunge una nuova regola con un valore Non espandere che replica una definizione precedente, i Termini della nuova definizione vengono aggiunti all&#39;originale.

## Configurazione delle sostituzioni di espansione delle query {#task_A087354A509D4997BA275186C224160E}

Definizione e aggiunta di un override di espansione query in Search&amp;Promote.

<!-- 

t_configuring_query_expansion_overrides.xml

 -->

>[!NOTE]
Per impostazione predefinita, questa funzione non è abilitata in Search&amp;Promote. Contattate il supporto tecnico per attivare la funzione per l’utilizzo. Una volta attivata la funzione di esclusione dell&#39;espansione delle query, è necessario &quot;attivarla&quot; nell&#39;interfaccia utente. I primi passaggi descritti di seguito illustrano come farlo.

**Per configurare le sostituzioni di espansione delle query**

1. In Search&amp;Promote, fai clic su **Impostazioni** > **Utente** > **Visualizza ruoli**.
1. Nella pagina Visualizza ruoli, nella colonna Azioni della tabella, fare clic su **Modifica** a destra del ruolo che si desidera assegnare all&#39;accesso alle sostituzioni di espansione query nel menu Linguistica.
1. Nella pagina Modifica ruolo, espandere la struttura Linguistica.
1. Selezionare Ignora **espansione** query, quindi fare clic su **Salva modifiche**.
1. Fate clic su **Linguistica** > **Sovrapposizioni** espansione query.
1. Fate clic su **Aggiungi sostituzioni** di espansione query.
1. Nella pagina Aggiungi sostituzioni di espansione query, impostate le opzioni desiderate.

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
      <td colname="col2"> <p>Selezionare <b>Testo</b> per specificare un'associazione di parole o frasi specifica. In alternativa, selezionare una classificazione per specificare che la parola o la frase Non espandere non viene convertita tramite la classificazione selezionata. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Termine </p> </td> 
      <td colname="col2"> <p>Disponibile solo se è stato selezionato <b>Testo</b> come Tipo. Specifica la parola o la frase da escludere dall'espansione della ricerca. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Azione </p> </td> 
      <td colname="col2"> <p> Fare clic <b>+</b> o <b>-</b> per aggiungere o eliminare i termini, rispettivamente, alla definizione. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Al termine, fate clic su **Aggiungi**.

   Dalla pagina Definizioni di esclusione dell&#39;espansione delle query è possibile modificare o eliminare le definizioni aggiunte.
1. Per visualizzare in anteprima i risultati delle aggiunte, fate clic su **Rigenera l’indice** del sito nella casella blu per ricreare rapidamente l’indice del sito Web in fase di creazione.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic su **Live**.

      Consultate [Visualizzazione delle impostazioni dal vivo](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)

   * Fate clic su **Push Live**(Invia push in tempo reale).

      Consultate [Attivazione live delle impostazioni dell’area di visualizzazione](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

