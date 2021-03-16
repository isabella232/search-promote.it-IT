---
description: Utilizza la barra laterale facet per riordinare gruppi di facet in una pagina web.
solution: Target
subtopic: Navigation
title: Informazioni sulla barra laterale
topic: Progettazione, ricerca nel sito e merchandising
uuid: 6da2bd67-8c20-4955-9836-bc8ba88546c5
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---


# Informazioni sulla barra laterale{#about-facet-rail}

Utilizza la barra laterale facet per riordinare gruppi di facet in una pagina web.

## Utilizzo della barra laterale {#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB}

Un facet è una proprietà o una caratteristica, È un modo per classificare generalmente i risultati della ricerca. Ad esempio, il produttore, il prezzo e il colore possono essere considerati un gruppo di facet. Ogni facet può avere più vincoli o valori. Ad esempio, se il colore era un facet, i &quot;valori facet&quot; potrebbero essere rosso, arancione, giallo, verde, blu, indaco e viola.

Consultare [Informazioni sui facet](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

Utilizza la barra laterale facet per riordinare questi gruppi di facet in una pagina web. Si supponga, ad esempio, di avere una sezione dei risultati di ricerca sul lato sinistro di una pagina web. La sezione elencata, dall’alto verso il basso, un facet Categoria, un facet Marchio, un facet Prezzo e un facet Più popolare. Utilizzando una barra facet, potete, ad esempio, far apparire il facet Più popolare sopra o sotto il facet Categoria.

Il gruppo di facet che desideri riordinare insieme appartiene a un tag della barra dei facet. Un facet può appartenere solo a una barra dei facet. La barra dei facet è un tag del modello di presentazione e racchiude una singola rappresentazione di un facet. Tutti i facet che appartengono a questa barra condividono la rappresentazione di un solo facet.

Consulta [Informazioni sui modelli](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5) e i facet in [Tag dei modelli di presentazione](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

## Configurazione di una barra dei facet {#task_561A8FF1CAD1402B9DD33E276BBC6A0E}

Potete aggiungere una barra dei facet per personalizzare il livello della presentazione. Le barre degli facet forniscono ai clienti una ricerca guidata che consente loro di approfondire i risultati della ricerca in base all’ordine dei facet nella pagina web.

<!-- 

t_configuring_facet_rail.xml

-->

Le modifiche apportate alle barre dei facet possono essere ripristinate utilizzando la funzione Cronologia.

**Per configurare una barra dei facet**

1. Prima di configurare una barra dei facet, accertati di aver già aggiunto un facet e, come parte di tale attività, di aver specificato un nome della barra dei facet.

   Consulta [Aggiunta di un nuovo facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B).
1. Nel menu del prodotto, fai clic su **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facet Rail.]**
1. Nella pagina [!DNL Facet Rail] , seleziona i facet da includere nella barra dei facet, quindi imposta l’opzione **[!UICONTROL Sort Facets Method]** dall’elenco a discesa.

   <!-- 
   r_facet_rail_options.xml
   -->

   | Funzionalità/Opzione | Descrizione |
   |--- |--- |
   | Nome della barra di sfaccettatura | Identifica il nome della barra dei facet.  Il nome della barra facet viene creato al momento dell’aggiunta del facet.  Consulta [Aggiunta di un nuovo facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B) |
   | Facet inclusi | Elenco dei possibili facet che puoi selezionare per aggiungere alla barra dei facet.  Se si sceglie di ordinare i facet utilizzando `Custom`, l&#39;ordine in cui si selezionano i facet determina l&#39;ordine in cui vengono visualizzati nella casella di testo `Custom Facet Order`. |
   | Metodo di ordinamento dei facet | Scegliere una delle tre opzioni seguenti nell’elenco a discesa:<ul><li>`Alpha` I facet sono ordinati in ordine alfabetico rispetto ai loro nomi, inclusi i caratteri di punteggiatura.</li><li>`Alpha (not case sensitive)` I facet sono ordinati in ordine alfabetico rispetto ai loro nomi, ignorando le lettere maiuscole in minuscole e viceversa. </li><li>`Alpha (alphanumeric only)` I facet sono ordinati in ordine alfabetico rispetto ai loro nomi, ignorando i caratteri di punteggiatura. </li><li>`Alpha (not case sensitive, alphanumeric only)` I facet sono ordinati in ordine alfabetico rispetto ai loro nomi, ignorando le lettere maiuscole in minuscole e viceversa. </li><li>`Count` I facet sono ordinati in base al conteggio. </li><li>`Custom` Apre la casella di  `Custom Facet Order` testo che consente di definire l’ordine dei facet immettendo il nome esatto di ciascun facet. Tutte le etichette dei facet rimosse dall’elenco `Custom Facet Order` vengono rimosse.</li></ul> |
   | Ordine facet personalizzato | Questa opzione è disponibile solo se hai selezionato `Custom` dall’elenco a discesa `Sort Facets Method` .  Consente di elencare i nomi dei facet, uno per riga, o tutti su una riga e separati da virgole. Le etichette dei facet definite vengono visualizzate nell’elenco `Facets Included`, racchiuse tra parentesi.  Non includere le etichette dei facet nella casella di testo `Custom Facet Order`.  Quando si selezionano o si deselezionano i facet nell’elenco `Facets Included`, la casella di testo `Custom Facet Order` viene aggiornata automaticamente. |

1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Nella pagina [!DNL Facet Rail] , effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

1. Modificare il modello Presentazione eseguendo le operazioni seguenti:.

   * Crea un &quot;modello di facet&quot; sul modello di presentazione.
   * Circonda il &quot;modello di facet&quot; con i tag `<guided-facet-rail>` .

      Consulta Facet in [Tag del modello di presentazione](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

      Esempio:

      ```
      <guided-facet-rail>
        <guided-facet>
          <guided-facet-display-name/>
          ...
          </guided-facet>
        </guided-facet-rail>
      ```

      Questi tag disegnano una sezione del modello di presentazione per diventare un pattern ripetibile per ciascun facet nella barra dei facet. Ogni facet appartenente alla barra sfaccettatura utilizza questa sezione scolpita per valutarne l’output. Sul modello di presentazione finale può essere visualizzato un solo tag `<guided-facet-rail>`.

      I seguenti tag non hanno bisogno dell&#39;attributo `gsname` all&#39;interno di `<guided-facet-rail>` perché il valore è determinato dinamicamente al momento della ricerca e viene sostituito correttamente:

      `<guided-facet>`
      `<guided-facet-display-name>`
      `<guided-facet-total-count>`
      `<guided-facet-undo-link>`
      `<guided-facet-undo-path>`
      `<guided-facet-behavior>`

   * Salva il modello di presentazione e invialo in tempo reale.

      Vedere [Modifica di una presentazione o di un modello di trasporto](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).
