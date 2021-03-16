---
description: È possibile utilizzare Parole escluse per specificare frasi e parole comuni utilizzate di frequente, ad esempio "a" e "the", da escludere dai risultati della ricerca.
solution: Target
title: Informazioni sulle parole escluse
topic: Linguistica, Ricerca sul sito e merchandising
uuid: 1c879462-1b19-44f6-a3b2-20aa786b3221
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---


# Informazioni sulle parole escluse{#about-excluded-words}

È possibile utilizzare Parole escluse per specificare frasi e parole comuni utilizzate di frequente, ad esempio &quot;a&quot; e &quot;the&quot;, da escludere dai risultati della ricerca.

## Utilizzo di parole escluse {#concept_9DB67BD2F0DC43AC88741003D9F39812}

Vedere anche [Informazioni sulle ricerche](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

Senza parole escluse, le ricerche che contengono queste parole possono identificare numerosi risultati irrilevanti. Quando si escludono parole e frasi, i risultati della ricerca vengono omessi e corrispondono solo ai termini esclusi specificati. Se una query di ricerca contiene una parola esclusa, per trovare i documenti vengono utilizzate solo le parole non escluse.

Le parole di ricerca escluse non vengono evidenziate nei risultati della ricerca. Tuttavia, il punteggio di pertinenza di ciascun risultato è influenzato dalle parole escluse. In altre parole, le parole escluse vengono ignorate durante la ricerca di documenti, ma vengono comunque utilizzate per classificare i documenti nella pagina dei risultati della ricerca. Prima che gli effetti delle impostazioni Escludi parole (o modifiche a queste impostazioni) siano disponibili per i clienti, assicurati di rigenerare l’indice del sito.

Quando si immettono parole da escludere dai risultati della ricerca, si separano parole o frasi tra loro con virgole. È possibile immettere una o più parole di esclusione per riga. Di seguito è riportato un esempio di parole escluse su righe separate e divise per virgole.

![](assets/excluded_words_1.jpg)

Utilizzando l&#39;elenco di esempio delle parole escluse di cui sopra, se il cliente cerca &quot;gli stati uniti d&#39;america&quot;, la parola &quot;il&quot; e la parola &quot;di&quot; sono escluse dalla ricerca. Invece, la ricerca trova tutte le pagine che contengono le parole &quot;unito&quot;, &quot;stati&quot; e &quot;america&quot;. Le pagine che contengono solo la parola &quot;di&quot; o &quot;il&quot; non vengono visualizzate.

Alcuni siti contengono frasi specifiche sulla maggior parte o su tutte le pagine. Ad esempio, un sito web sul turismo a New York City potrebbe contenere le parole New York nel titolo di ogni pagina. Considera l&#39;aggiunta di questa frase e di altre simili all&#39;elenco di esclusione:

![](assets/excluded_words_2.jpg)

Quando una frase viene esclusa, le singole parole che la compongono vengono comunque utilizzate come termini di ricerca. Solo quando un visitatore cerca le parole esatte, nell’ordine esatto di una frase esclusa, è la frase esclusa dai risultati della ricerca. Utilizzando l&#39;esempio precedente, se un cliente ha cercato il &quot;balletto new york&quot;, sono esclusi la parola &quot;the&quot; e la frase &quot;new york&quot;; solo le pagine che contengono la parola &quot;balletto&quot; vengono restituite come risultato della ricerca. D&#39;altra parte, la ricerca di &quot;nuovi edifici&quot; o &quot;duca di york&quot; trova ancora pagine che contengono rispettivamente la parola &quot;nuovo&quot; o &quot;york&quot;.

## Configurazione delle parole escluse {#task_60BF6BB7A66C48479D2BBB32C0F38CDE}

È possibile escludere dai risultati della ricerca le frasi e le parole comuni utilizzate di frequente.

È possibile immettere una o più parole per riga. Separa ogni parola con virgole come nell&#39;esempio seguente:

![](assets/excluded_words_1.jpg)

È possibile scegliere di visualizzare i risultati della ricerca quando tutte le parole nella ricerca del cliente sono escluse dalle parole. Ad esempio, se hai escluso la parola &quot;il&quot; e un cliente sceglie di cercare solo &quot;il&quot;, i risultati della ricerca mostrano qualsiasi pagina contenente la parola &quot;il&quot;. Questo risultato è vero anche se la parola &quot;il&quot; è esclusa. Se non selezioni questa opzione, il cliente non riceve alcun risultato di ricerca. Questa impostazione non ha alcun effetto se la ricerca contiene almeno una parola non esclusa.

**Per configurare le parole escluse**

1. Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Excluded Words]** dal menu del prodotto.
1. Nella pagina [!DNL Excluded Words] , immetti le parole da escludere dai risultati della ricerca nel campo di testo **[!UICONTROL Words and Phrases]** .
1. (Facoltativo) Fai clic su **[!UICONTROL Show results when all words in the query are excluded words]**.

   Quando tutte le parole nella ricerca del cliente sono escluse, tutte le parole vengono utilizzate insieme per eseguire la ricerca.
1. Clic **[!UICONTROL Save Changes]**.
1. Per visualizzare in anteprima i risultati delle modifiche, fai clic su **[!UICONTROL regenerate your staged site index]** per ricreare l’indice del sito web in staging.

   Vedere [Esecuzione di un indice completo di un sito web live o in staging...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Vedi [Esecuzione di un indice incrementale di un sito web live o in staging...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Facoltativo) Scegliere **[!UICONTROL Linguistics]** > **[!UICONTROL Excluded Words]** dal menu del prodotto, quindi effettuare una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

