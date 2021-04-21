---
description: È possibile utilizzare l'aggiornamento verticale per aggiornare rapidamente parti dell'indice senza dover elaborare grandi quantità di dati.
solution: Target
subtopic: Vertical Update
title: Informazioni sull'aggiornamento verticale
topic-legacy: Index,Site search and merchandising
uuid: ded09e89-5a52-4e8c-a6f7-3e25b4191183
exl-id: 8d6a48c0-377d-4a15-bddc-c67e28037bfc
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 0%

---

# Informazioni sull&#39;aggiornamento verticale{#about-vertical-update}

È possibile utilizzare l&#39;aggiornamento verticale per aggiornare rapidamente parti dell&#39;indice senza dover elaborare grandi quantità di dati.

## Utilizzo dell&#39;aggiornamento verticale {#concept_E65A70C9C2E04804BF24FBE1B3CAD899}

L’esecuzione di un indice verticale richiede solo pochi secondi ed è utile sui siti web di e-commerce a grande capacità che possono richiedere molte ore per indicizzarlo in modo completo o incrementale.

Quando si genera un indice verticale, vengono visualizzate informazioni sullo stato, ad esempio il tempo di avvio, il tempo trascorso e gli errori durante il processo di indicizzazione.

Puoi interrompere o riavviare il processo di indicizzazione verticale in qualsiasi momento.

Mentre il nuovo indice verticale aggiorna il tuo sito web live, i clienti possono continuare a cercare il tuo sito utilizzando il tuo indice corrente.

>[!NOTE]
>
>Per impostazione predefinita, questa funzione non è abilitata in [!DNL Adobe Search&Promote]. Contatta il supporto tecnico per attivare la funzione.

Gli aggiornamenti verticali sono destinati in modo specifico all&#39;uso su account [!DNL Adobe Search&Promote] in stile eCommerce che utilizzano IndexConnector per fornire il contenuto dell&#39;indice di ricerca. Il caso d’uso tipico è quello in cui l’indice [!DNL Adobe Search&Promote] rappresenta un catalogo di prodotti ricercabile e la necessità di poter aggiornare rapidamente i valori che cambiano frequentemente, ad esempio inventario, disponibilità e/o prezzo. Un aggiornamento verticale è in qualche modo simile a un indice incrementale, tranne per il fatto che aggiorna solo parti di ciascun documento, mentre un Indice incrementale sostituisce interi documenti con nuove versioni.

Il termine &quot;Aggiornamento verticale&quot; si riferisce al concetto che un indice [!DNL Adobe Search&Promote] può essere rappresentato come una tabella di colonne, con ogni colonna corrispondente a una definizione di campo metadati [!DNL Adobe Search&Promote] e ogni riga corrispondente a un documento. Il processo di aggiornamento verticale sostituisce una o più colonne senza la necessità di modificare il contenuto delle altre colonne.

Se l&#39;origine principale del contenuto, un feed IndexConnector, contiene tutti gli elementi dati necessari per creare l&#39;indice, il feed di aggiornamento verticale è un sottoinsieme del feed principale, che utilizza lo stesso IndexConnector &quot;schema&quot; per definire gli elementi dati, ma contiene *solo* gli elementi dati che devono essere aggiornati.

Come minimo, il feed di aggiornamento verticale deve contenere l’elemento &quot;chiave primaria&quot; (identificato con la casella di controllo **Chiave primaria** nella configurazione IndexConnector) e almeno un elemento dati da aggiornare.

Ad esempio, un feed IndexConnector primario potrebbe avere un aspetto simile al seguente (ma in genere con molti altri elementi dati):

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <title><![CDATA[Title for product 123]]></title>
  <description><![CDATA[Description for product 123.]]></description>
  <price>3.99</price>
  <link><![CDATA[https://www.somewhere.com/products/123]]></link>
  <image><![CDATA[https://www.somewher.com/images/products/123.jpg]]></image>
  <label><![CDATA[PROD123]]></label>
  <inventory>100</inventory>
  <brand><![CDATA[brand123]]></brand>
  ...
</product>
<product>
...
</product>
</products>
```

È necessario essere in grado di aggiornare rapidamente solo i valori `<price>` e `<inventory>`, in quanto questi valori possono cambiare rapidamente sul sito del cliente. Un feed di aggiornamento verticale potrebbe quindi avere un aspetto simile al seguente:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <price>3.50</price>
  <inventory>90</inventory>
</product>
<product>
...
</product>
</products>
```

Queste informazioni vengono generalmente memorizzate in un file separato sul server del cliente e l&#39;impostazione di configurazione IndexConnector &quot;Vertical File Path&quot; punta a questo file. Il processo di aggiornamento verticale legge questo nuovo contenuto e aggiorna l&#39;indice esistente [!DNL Adobe Search&Promote], aggiornando solo i valori per `<price>` e `<inventory>`, in questo caso. Le ricerche successive restituiscono il contenuto appena aggiornato.

>[!NOTE]
In questo esempio, i campi `<price>` e `<inventory>` Metadati dovranno essere stati definiti con l&#39;opzione **Campo di aggiornamento verticale** selezionata.

Vedere anche [Informazioni sul telecomando per l&#39;indicizzazione](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F) e [Aggiunta di un nuovo campo meta tag](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Configurazione di un aggiornamento verticale di un sito web di staging {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

Puoi configurare le origini del connettore indice da includere nell&#39;aggiornamento verticale specificando gli URL.

**Per configurare un aggiornamento verticale di un sito web in staging**

1. Dal menu del prodotto, fai clic su **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Configuration]**.
1. Nella pagina **[!UICONTROL Vertical Update Configuration]** , specifica gli URL delle pagine da indicizzare nel campo Aggiorna URL .

   Il robot di ricerca aggiorna solo i documenti identificati nelle origini del connettore indice specificate.

   Questo campo deve contenere gli URL del connettore indice solo come nell&#39;esempio seguente:

   `index:product_catalog`.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettua una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL History]** per ripristinare le modifiche apportate.

      Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Clic **[!UICONTROL Live]**.

      Consulta [Visualizzazione delle impostazioni live](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Clic **[!UICONTROL Push Live]**.

      Consulta [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Visualizzazione del registro dell&#39;aggiornamento verticale di un sito web live o di staging {#task_E668E1F1240C476DAA1CA783DC728232}

Al termine di un aggiornamento verticale live o di un aggiornamento verticale in staging, puoi visualizzare il registro associato per risolvere eventuali errori.

Non è possibile esportare i file di registro di aggiornamento verticale, né salvarli. Il file di registro rimane disponibile per la visualizzazione fino a quando non si verifica l&#39;indice successivo.

**Per visualizzare il registro di aggiornamento verticale di un sito web live o in staging**

1. Scegliere una delle seguenti operazioni dal menu prodotto:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di log, in alto o in basso, effettua una delle seguenti operazioni:

   * Utilizza le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi all’interno del registro.

   * Utilizza le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare la visualizzazione.
