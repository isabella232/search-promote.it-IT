---
description: nulle
seo-description: nulle
seo-title: Search&amp;Promote 8.12.0 - Note sulla versione (16/01/2014)
solution: Target
title: Search&amp;Promote 8.12.0 - Note sulla versione (16/01/2014)
topic: Release Notes,Site search and merchandising
uuid: 4db10eb4-11bf-4483-a7f2-87981d9c7a50
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 3%

---


# Note sulla versione di Search&amp;Promote 8.12.0 (16/01/2014){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nuove funzioni e miglioramenti </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Aggiunta di dizionari </p> </td> 
   <td colname="col2"> <p> </p> <p> Per le lingue indonesiana e turca sono stati aggiunti dizionari di imitazione. </p> <p>Vedere <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" format="dita" scope="local"> Informazioni sui dizionari</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esportare i rapporti </p> </td> 
   <td colname="col2"> <p> 
     <!--3683368-->Ora puoi esportare i dati in formato CSV dai seguenti rapporti: 
     <ul id="ul_93B619DBB3444F64BD6D7F9E969AB1E1"> 
      <li id="li_96DDE1A196834845A0FA319903C5934B"> <p>Rapporto termini </p> </li> 
      <li id="li_4F1A19DE98C84F8CAD963EEA2B38ED7A"> <p>Rapporto termini ricerca Null </p> </li> 
      <li id="li_A7716C62C4D44CD69D411C3FEE246D96"> <p>Report richiesta di ricerca </p> </li> 
     </ul> </p> <p>Vedere <a href="../c-about-reports-menu/c-about-reports-menu.md#concept_5F901459C7AB461BAB30B305957EB00C" format="dita" scope="local"> Informazioni sul menu Rapporti</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non associare </p> </td> 
   <td colname="col2"> <p>Ora è possibile controllare quali due parole non devono essere associate insieme nei risultati di ricerca, come "Sweatshirt" e "Shirt". </p> <p> <p>Nota:  Questa funzione non è abilitata per impostazione predefinita. Contatta  Assistenza clienti di Adobe per attivare la funzione in Search&amp;Promote e utilizzarla. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Problemi risolti**

* Non è stato possibile aggiungere risultati in un&#39;area consigliata al di fuori dei criteri di facet attualmente selezionati.
* Non è stato possibile salvare le regole basate sui risultati per un account con ricerca solo HTTPS.
* L&#39;impostazione di una regola business per &quot;non è un telefono cellulare&quot; non funzionava.

   Vedere [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* L&#39;esecuzione di una ricerca filtro inventario non ha restituito risultati.
* L&#39;ordine dei facet Dimensione non veniva aggiornato.
* Aggiunta l&#39;opzione per una definizione di regola &quot;personalizzata&quot; alla pagina Pulizia query.

   Vedere [Informazioni sulle regole di pulizia delle query](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C).

* Il rapporto Termini ripeteva le voci in caso di dati insufficienti.

   Vedere [Visualizzazione del rapporto Termini o dei termini di ricerca Null...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* La trasmissione live di una singola regola business funzionava in modalità Staging, ma non riusciva in modalità Live.
* Le modifiche di completamento automatico agli elenchi Includi o Escludi non sono state salvate nella cronologia e non è stato quindi possibile ripristinarle.

   Vedere [Informazioni sulla funzione di completamento automatico](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578).

