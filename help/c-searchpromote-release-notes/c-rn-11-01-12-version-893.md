---
description: Search&amp;Note sulla versione di Promote 8.9.3.
solution: Target
title: Search&amp;Promote 8.9.3 Note sulla versione (01/11/2012)
topic-legacy: Release Notes,Site search and merchandising
uuid: 7bc7bcb6-f47f-4e05-94e5-a22a13a187b7
exl-id: 9593a87d-2a84-41e1-b052-644d928f5053
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 2%

---

# Note sulla versione di Search&amp;Promote 8.9.3 (11/01/2012){#search-promote-release-notes}

## Note sulla versione di Search&amp;Promote 8.9.3 (11/01/2012) {#concept_85F5B4B4C40C43FEA3AD63E6EA5593CF}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nuove funzioni e miglioramenti </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Barra a sfaccettatura </p> </td> 
   <td colname="col2"> <p> 
     <!--3309390--> È stata aggiunta la nuova opzione  <span class="uicontrol"> Ferrovia </span> sfaccettatura per consentire un maggiore controllo sull'ordinamento delle famiglie di facet e dei nomi di facet (per conteggio, alfabetico). </p> <p>Consulta <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> Informazioni sulla barra laterale</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Facet nidificati </p> </td> 
   <td colname="col2"> <p> È stato aggiunto il supporto per l’ordinamento alternativo dei facet nidificati. </p> <p>Consulta <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> Informazioni sulla barra laterale</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo Note nelle regole di classificazione </p> </td> 
   <td colname="col2"> <p> 
     <!--3063772--> È stato aggiunto un campo  <span class="wintitle"> </span> Notizie su più righe alle finestre di dialogo  <span class="wintitle"> Aggiungi </span> metrica di classificazione e  <span class="wintitle"> Modifica </span> metrica di classificazione per le regole di classificazione e le definizioni dei gruppi di regole. </p> <p>Le note sulle regole di classificazione vengono visualizzate nella pagina <span class="wintitle"> Definisci regole di classificazione</span> . Le note del gruppo di regole vengono visualizzate quando si modifica la definizione. </p> <p>Consulta <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" format="dita" scope="local"> Informazioni sulle regole di classificazione</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regole aziendali </p> </td> 
   <td colname="col2"> <p> 
     <!--3331637--> È stato migliorato il supporto della pagina di destinazione rimuovendo i risultati naturali in una regola business utilizzando la nuova opzione  <span class="uicontrol"> Rimuovi tutti i risultati </span> . </p> <p>Utilizza questa nuova opzione insieme ad altre azioni della regola business per creare "pagine di destinazione in scatola". In altre parole, desideri creare il contenuto di una pagina esclusivamente tramite azioni di regola business e devi eliminare i risultati "naturali" della ricerca. </p> <p>Consulta <a href="../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7" format="dita" scope="local"> Aggiunta di una nuova regola business</a> o <a href="../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087" format="dita" scope="local"> Modifica di una regola business</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Banner e regole aziendali </p> </td> 
   <td colname="col2"> <p> È stata aggiunta un’opzione di supporto che consente di rinunciare condizionatamente al push dei banner live quando la regola business che fa riferimento al banner viene trasmessa in diretta. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Problemi risolti**

* Le regole di business funzionavano in modo incoerente quando c&#39;era un indice [!DNL Stage] .
* Le regole di authoring vengono ora applicate alle pagine di destinazione digitalizzate.

   Vedi la tabella delle opzioni in [Aggiunta di una regola di classificazione](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

* [!DNL promosearch.cgi] non restituiva promozioni.

   Consulta [Informazioni sulle ricerche](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

* L&#39;invio di regole che a volte fanno riferimento a molti banner non è riuscito.

   Consulta [Informazioni sui banner](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA).

* **[!UICONTROL Did You Mean]** il caching delle query di ricerca è ora disabilitato.

   Consultare [Informazioni su intendete](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E).
