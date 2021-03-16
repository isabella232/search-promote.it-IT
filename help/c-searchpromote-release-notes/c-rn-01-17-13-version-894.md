---
description: Search&amp;Note sulla versione di Promote 8.9.4.
solution: Target
title: Search&amp;Promote 8.9.4 Note sulla versione (17/01/2013)
topic: Note sulla versione, Ricerca nel sito e merchandising
uuid: a9d550f6-0a23-4c71-b123-c31b997e7384
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---


# Note sulla versione di Search&amp;Promote 8.9.4 (17/01/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nuove funzioni e miglioramenti </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Regole </p> </td> 
   <td colname="col2"> <p> Aggiunta la possibilità di creare note in linea quando si creano regole di pulizia delle query, regole di pre-ricerca e regole di post-ricerca. Il campo Note consente di documentare e spiegare le regole. </p> <p>Consultare <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" format="dita" scope="local"> Informazioni sulle regole di pulizia delle query</a>. </p> <p>Consulta <a href="../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F" format="dita" scope="local"> Informazioni sulle regole di pre-ricerca</a>. </p> <p>Consulta <a href="../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE" format="dita" scope="local"> Informazioni sulle regole di post-ricerca</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ricerca guidata </p> </td> 
   <td colname="col2"> <p> Sono stati aggiunti tag di Ricerca guidata per indicare il tempo totale impiegato da una ricerca. </p> <p> <span class="codeph"> &lt;guided-search-time&gt;</span> - Identifica il tempo impiegato dalla ricerca. Il valore del tempo di ricerca restituito è specificato in ms. </p> <p> <span class="codeph"> &lt;guided-fall-through-searches&gt;</span> - Restituisce il numero di ricerche core utilizzate per creare la pagina dei risultati di ricerca. </p> <p> <span class="codeph"> &lt;guided-if-fall-through-search&gt;</span> - Verifica se il conteggio delle ricerche principali è maggiore di 1. </p> <p>Vedere anche Varie lingue in <a href="../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64" format="dita" scope="local"> Tag del modello di presentazione</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Problemi risolti**

* Il rapporto Termini ignora ora il carattere asterisco.

   Consultare [Visualizzazione del rapporto Termini o dei termini di ricerca Null..](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* Apri **[!UICONTROL Reports > Null Search Terms Report]**, seleziona un intervallo di tempo e visualizza il rapporto. Fare clic su una parola nel rapporto per aprire la ricerca, quindi fare di nuovo clic su Visualizza rapporto. Il conteggio di ricerca della parola chiave selezionata è aumentato due volte. Questo problema è stato adesso risolto.

   Consultare [Visualizzazione del rapporto Termini o dei termini di ricerca Null..](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* È stata eseguita un&#39;ottimizzazione delle prestazioni per quando si inviano in diretta le regole aziendali.

   Consultare [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* La possibilità di rimuovere in [!DNL Breadcrumbs] non ha funzionato tutte le volte.

   Consultare [Informazioni sulle breadcrumb](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03).

* A meno che non sia stata rigenerata, la funzione di riclassificazione non consentiva che le regole di classificazione modificate diventassero effettive nei risultati di ricerca.

   Consulta [Informazioni sulle regole di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

   Consultare [Informazioni sull&#39;indice di classificazione ](../c-about-index-menu/c-about-re-rank-index.md#concept_147B0A9FCD51451787DA898E06F7C692).

