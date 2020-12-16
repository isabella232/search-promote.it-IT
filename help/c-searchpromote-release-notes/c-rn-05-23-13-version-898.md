---
description: nulle
seo-description: nulle
seo-title: Search&amp;Promote 8.9.8 - Note sulla versione (23/05/2013)
solution: Target
title: Search&amp;Promote 8.9.8 - Note sulla versione (23/05/2013)
topic: Release Notes,Site search and merchandising
uuid: ff4bfc53-1d0e-4b7d-83ad-54c81d3f9769
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 3%

---


# Search&amp;Promote 8.9.8 - Note sulla versione (23/05/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nuova funzionalità </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Frasi comuni - Supporto di corrispondenza esatto </p> </td> 
   <td colname="col2"> <p> Le frasi comuni contengono termini di due o più parole che vengono ricercate come un insieme, come "taglio di avvio" o "top serbatoio", e non come parti separate. Una frase comune ha un significato unico e diverso da una delle sue singole parti. </p> <p> Si mantiene un dizionario di frasi comuni relative alla propria attività. Quando un cliente esegue una query di ricerca contenente più parole, viene eseguita una ricerca sul dizionario per la stessa corrispondenza esatta. </p> <p>È possibile aggiungere, modificare o eliminare frasi comuni. Potete anche raggruppare frasi comuni simili ai dizionari di dominio. Ad esempio, potete raggruppare le frasi comuni per abbigliamento, tessuto, gioielli, misure, acquisti e generale. </p> <p>Vedere <a href="../c-about-linguistics-menu/c-about-common-phrases.md#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local"> Informazioni sulle frasi comuni </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Problemi risolti e miglioramenti**

* Il parametro CGI di ricerca back-end `sp_date_range_#` non funzionava per i campi definiti dall&#39;utente.

   Vedere [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

* Il ripristino della versione **[!UICONTROL History]** non ha aggiornato il contenuto del campo dei punti di ingresso dell&#39;URL.

   Vedere [Utilizzo dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   Vedere anche [Informazioni sui punti di entrata URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

* La codifica JSON non gestiva i caratteri codificati erroneamente.
* È stato aggiunto il supporto che consente di inviare in remoto un indice in tempo reale.

   Vedere [Informazioni sul telecomando per l&#39;indicizzazione](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

