---
description: Search&amp;Note sulla versione di Promote 8.9.8.
solution: Target
title: Search&amp;Promote 8.9.8 Note sulla versione (23/05/2013)
topic: Note sulla versione, Ricerca nel sito e merchandising
uuid: ff4bfc53-1d0e-4b7d-83ad-54c81d3f9769
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 2%

---


# Note sulla versione di Search&amp;Promote 8.9.8 (23/05/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nuova funzionalità </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Espressioni comuni - supporto esatto delle corrispondenze </p> </td> 
   <td colname="col2"> <p> Le frasi comuni contengono termini di due o più parole che vengono cercate nel loro insieme, come "taglio di avvio" o "top serbatoio", e non come parti separate. Una frase comune ha un significato unico e diverso da qualsiasi sua singola parte. </p> <p> Tu mantieni un dizionario di frasi comuni relative alla tua attività. Quando un cliente esegue una query di ricerca contenente più parole, viene eseguita una ricerca sul dizionario per la stessa corrispondenza esatta. </p> <p>È possibile aggiungere, modificare o eliminare frasi comuni. È inoltre possibile raggruppare frasi comuni simili a dizionari di dominio. Ad esempio, è possibile raggruppare frasi comuni per abbigliamento, tessuto, gioielli, misure, acquisti e generale. </p> <p>Vedere <a href="../c-about-linguistics-menu/c-about-common-phrases.md#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local"> Informazioni sulle frasi comuni </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Problemi risolti e miglioramenti**

* Il parametro CGI di ricerca back-end `sp_date_range_#` non funzionava per i campi definiti dall&#39;utente.

   Consulta [Parametri CGI di ricerca back-end](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

* Il ripristino della versione **[!UICONTROL History]** non ha aggiornato il contenuto del campo dei punti di ingresso dell’URL.

   Vedere [Uso dell&#39;opzione Cronologia](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   Consulta anche [Informazioni sui punti di ingresso URL](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

* La codifica JSON non gestiva i caratteri codificati in modo errato.
* È stato aggiunto il supporto che consente di inviare in remoto un indice in tempo reale.

   Vedere [Informazioni sul telecomando per l&#39;indicizzazione](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

