---
description: È possibile utilizzare Aggiornamento verticale per aggiornare rapidamente parti dell'indice senza dover elaborare grandi quantità di dati.
seo-description: È possibile utilizzare Aggiornamento verticale per aggiornare rapidamente parti dell'indice senza dover elaborare grandi quantità di dati.
seo-title: Aggiornamento verticale
solution: Target
subtopic: Vertical Update
title: Aggiornamento verticale
topic: Index,Site search and merchandising
uuid: ded09e89-5a52-4e8c-a6f7-3e25b4191183
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# Aggiornamento verticale{#about-vertical-update}

È possibile utilizzare Aggiornamento verticale per aggiornare rapidamente parti dell&#39;indice senza dover elaborare grandi quantità di dati.

## Utilizzo dell&#39;aggiornamento verticale {#concept_E65A70C9C2E04804BF24FBE1B3CAD899}

L&#39;esecuzione di un indice verticale richiede solo secondi ed è utile sui siti eCommerce di grandi dimensioni che possono richiedere molte ore per indicizzare completamente o in modo incrementale.

Quando si genera un indice verticale, durante il processo di indicizzazione vengono visualizzate informazioni sullo stato, ad esempio ora di inizio, tempo trascorso ed errori.

È possibile arrestare o riavviare il processo di indicizzazione verticale in qualsiasi momento.

Mentre il nuovo indice verticale aggiorna il sito Web live, i clienti possono continuare a cercare sul sito utilizzando l&#39;indice corrente.

>[!NOTE]
>
>Per impostazione predefinita, questa funzione non è abilitata in [!DNL Adobe Search&Promote]. Contattate il supporto tecnico per attivare la funzione per l’utilizzo.

Gli aggiornamenti verticali sono destinati in modo specifico ad essere utilizzati negli account in stile eCommerce che utilizzano IndexConnector per fornire il contenuto per l&#39;indice di ricerca. [!DNL Adobe Search&Promote] Il caso d’uso tipico è quello in cui l’ [!DNL Adobe Search&Promote] indice rappresenta un catalogo di prodotti ricercabile, e la necessità esiste per essere in grado di aggiornare rapidamente i valori che cambiano frequentemente, come scorte disponibili, disponibilità e/o prezzo. Un aggiornamento verticale è in qualche modo simile a un indice incrementale, con la differenza che aggiorna solo parti di ciascun documento, mentre un indice incrementale sostituisce interi documenti con nuove versioni.

Il termine &quot;Aggiornamento verticale&quot; si riferisce alla nozione che un [!DNL Adobe Search&Promote] indice può essere rappresentato come una tabella di colonne, con ogni colonna corrispondente a una definizione di campo [!DNL Adobe Search&Promote] Metadati e ogni riga corrispondente a un documento. Il processo di aggiornamento verticale sostituisce una o più colonne senza dover modificare il contenuto delle altre colonne.

Se l&#39;origine principale del contenuto, un feed IndexConnector, contiene tutti gli elementi di dati richiesti necessari per creare l&#39;indice, il feed di aggiornamento verticale è un sottoinsieme del feed principale, uno che utilizza lo stesso &quot;schema&quot; IndexConnector per definire gli elementi di dati, ma contiene *solo* gli elementi di dati che devono essere aggiornati.

Come minimo, il feed di aggiornamento verticale deve contenere l&#39;elemento &quot;chiave primaria&quot; (identificato con la casella di controllo Chiave **** principale nella configurazione IndexConnector) e almeno un elemento dati da aggiornare.

Ad esempio, un feed IndexConnector primario potrebbe avere l&#39;aspetto seguente (ma in genere con molti altri elementi di dati):

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

Un requisito consiste nel poter aggiornare rapidamente solo i valori `<price>` e `<inventory>` , in quanto tali valori possono cambiare rapidamente sul sito del cliente. A questo punto, un feed di aggiornamento verticale potrebbe essere simile al seguente:

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

Queste informazioni vengono in genere memorizzate in un file separato sul server del cliente e l&#39;impostazione di configurazione IndexConnector &quot;Percorso file verticale&quot; punta a questo file. Il processo di aggiornamento verticale legge questo nuovo contenuto e aggiorna l&#39; [!DNL Adobe Search&Promote] indice esistente, aggiornando solo i valori per `<price>` e, in questo caso, `<inventory>`. Le ricerche successive restituiscono il contenuto appena aggiornato.

>[!NOTE]
In questo esempio, i campi `<price>` e `<inventory>` metadati dovranno essere stati definiti con l’opzione Campo **aggiornamento** verticale selezionata.

Vedere anche [Informazioni sul controllo remoto per l&#39;indicizzazione](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F) e l&#39; [aggiunta di un nuovo campo](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)tag meta.

## Configurazione di un aggiornamento verticale di un sito Web in fase {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

Puoi configurare quali origini del connettore indice includere nell&#39;aggiornamento verticale specificando gli URL.

**Per configurare un aggiornamento verticale di un sito Web in una pagina**

1. Nel menu del prodotto, fate clic su **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Configuration]**.
1. Nella **[!UICONTROL Vertical Update Configuration]** pagina, nel campo Aggiorna URL, specificate gli URL delle pagine da indicizzare.

   Il robot di ricerca aggiorna solo i documenti identificati nelle sorgenti del connettore indice specificate.

   Questo campo deve contenere gli URL del connettore indice solo come nell&#39;esempio seguente:

   `index:product_catalog`.
1. Clic **[!UICONTROL Save Changes]**.
1. (Facoltativo) Effettuate una delle seguenti operazioni:

   * Fate clic **[!UICONTROL History]** per annullare le modifiche apportate.

      Consultate [Utilizzo dell’opzione](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Cronologia.

   * Clic **[!UICONTROL Live]**.

      Consultate [Visualizzazione delle impostazioni](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)dal vivo.

   * Clic **[!UICONTROL Push Live]**.

      Consultate [Invio live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)delle impostazioni dell’area di visualizzazione.

## Visualizzazione del registro degli aggiornamenti verticali di un sito Web live o in fase {#task_E668E1F1240C476DAA1CA783DC728232}

Al termine di un aggiornamento verticale in diretta o di un aggiornamento verticale in fase, puoi visualizzare il registro associato per risolvere eventuali errori che si sono verificati.

Non potete esportare i file di registro degli aggiornamenti verticali né salvarli. Il file di registro rimane disponibile per la visualizzazione fino a quando non si verifica l&#39;indice successivo.

**Per visualizzare il registro dell&#39;aggiornamento verticale di un sito Web live o in una fase**

1. Nel menu del prodotto, effettuate una delle seguenti operazioni:

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Live Log]**.

   * Fai clic su **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Staged Log]**.

1. Nella pagina di registro, in alto o in basso, effettuate una delle seguenti operazioni:

   * Utilizzate le opzioni di navigazione **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** o **[!UICONTROL Go to line]** per spostarsi nel registro.

   * Utilizzate le opzioni di visualizzazione **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** o **[!UICONTROL Show]** per perfezionare il contenuto visualizzato.

