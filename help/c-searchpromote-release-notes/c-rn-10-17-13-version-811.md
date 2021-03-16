---
description: Search&amp;Note sulla versione di Promote 8.11.0.
solution: Target
title: Search&amp;Promuovi note sulla versione 8.11.0 (29/10/2013)
topic: Note sulla versione, Ricerca nel sito e merchandising
uuid: 973f9608-a5c7-4571-ae2b-6f1fa05bc862
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---


# Note sulla versione di Search&amp;Promote 8.11.0 (29/10/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nuova funzionalità </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Scomposizione danese </p> </td> 
   <td colname="col2"> <p> È ora disponibile un meccanismo che consente a <span class="keyword"> Adobe Search&amp;Promote</span> di accedere ai servizi di rilevamento, decomposizione, stelo e segmentazione della lingua (danese) forniti dall'Adobe. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti e correzioni**

* Miglioramenti apportati alle funzionalità di corrispondenza delle tabelle [!DNL Search&Promote] esistenti. I miglioramenti forniscono un migliore supporto dei requisiti dei clienti relativi a relazioni sempre più complesse tra SKU e i dati di prodotto.

   >[!NOTE]
   >
   >Questa funzione non è abilitata per impostazione predefinita. Contatta l’Assistenza clienti Adobe per attivare la funzione in Search&amp;Promote per il tuo utilizzo.

* È stata aggiunta un’opzione che consente a Ricerca guidata di ordinare i facet utilizzando l’impostazione della lingua dell’account.

   >[!NOTE]
   Questa funzione non è abilitata per impostazione predefinita. Contatta l’Assistenza clienti Adobe per attivare la funzione in Search&amp;Promote per il tuo utilizzo.

* È stata aggiunta un’opzione per aumentare il numero di valori di facet che un utente può specificare per i facet a selezione multipla.

   >[!NOTE]
   Questa funzione non è abilitata per impostazione predefinita. Contatta l’Assistenza clienti Adobe per attivare la funzione in Search&amp;Promote per il tuo utilizzo.

* È stata aggiunta l’opzione casella di controllo **[!UICONTROL Only allow searches that use HTTPS]** a **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]**.

   Consultare [Informazioni sulle restrizioni](../c-about-settings-menu/c-about-searching-menu.md#concept_B5B527E04EBF4E9AB5956EEF881DDBF1).

* È stata aggiunta un’opzione a **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]** > **[!UICONTROL Generic Feed]** per mantenere i caratteri di tabulazione nel pannello [!DNL File Submission] della procedura guidata.

   Consulta [Creazione di un feed](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250).

* È stata aumentata la dimensione dei dati accettati in ciascuno dei campi superiore e inferiore del nuovo modulo di definizione del facet da 80 caratteri a 1000.

   Consultare [Informazioni sui facet](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

* I parametri di debug della ricerca guidata ora riportano correttamente i numeri delle regole business.
* Le regole aziendali vengono ora applicate nell’ambiente live.
* La ricerca per prossimità ora funziona durante la ricerca per longitudine/latitudine, per account configurati con Lingua = &quot;Danese (Danimarca)&quot;.
* Ora vengono attivati i trigger basati su risultati privi di pianificazione assegnata.
* Ora vengono riportati risultati coerenti quando si utilizza l’opzione **[!UICONTROL Ignore Apostrophes]** in **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**.

   Consulta [Informazioni su parole e lingua](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79).

* L’interfaccia utente dell’elenco di parole con completamento automatico ora funziona su un gran numero di facet.

