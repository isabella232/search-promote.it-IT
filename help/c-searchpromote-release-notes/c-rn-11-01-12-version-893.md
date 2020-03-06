---
description: nulle
seo-description: nulle
seo-title: Search&amp;Promote 8.9.3 - Note sulla versione (01/11/2012)
solution: Target
title: Search&amp;Promote 8.9.3 - Note sulla versione (01/11/2012)
topic: Release Notes,Site search and merchandising
uuid: 7bc7bcb6-f47f-4e05-94e5-a22a13a187b7
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.9.3 Release Notes (11/01/2012){#search-promote-release-notes}

## Search&amp;Promote 8.9.3 Release Notes (11/01/2012) {#concept_85F5B4B4C40C43FEA3AD63E6EA5593CF}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nuove funzioni e miglioramenti </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Barra laterale </p> </td> 
   <td colname="col2"> <p> 
     <!--3309390--> Aggiunta la nuova opzione <span class="uicontrol"> Barra</span> facet per consentire un maggiore controllo sull’ordine delle famiglie di facet e dei nomi dei facet (per numero, ordine alfabetico). </p> <p>Consultate <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> La Barra</a>Facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Facet nidificati </p> </td> 
   <td colname="col2"> <p> È stato aggiunto il supporto per l'ordinamento alternativo dei facet nidificati. </p> <p>Consultate <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> La Barra</a>Facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo Note nelle regole di classificazione </p> </td> 
   <td colname="col2"> <p> 
     <!--3063772--> È stato aggiunto un campo <span class="wintitle"> Note</span> su più righe nelle finestre di dialogo <span class="wintitle"> Aggiungi metrica</span> classificazione e <span class="wintitle"> Modifica metrica</span> classificazione per le regole di classificazione e le definizioni dei gruppi di regole. </p> <p>Le note sulle regole di classificazione vengono visualizzate nella pagina <span class="wintitle"> Definisci regole</span> di classificazione. Le note dei gruppi di regole vengono visualizzate quando modificate la definizione. </p> <p>Vedere <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" format="dita" scope="local"> Informazioni sulle regole</a>di classificazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regole aziendali </p> </td> 
   <td colname="col2"> <p> 
     <!--3331637--> È stato migliorato il supporto della pagina di destinazione rimuovendo i risultati naturali in una regola business utilizzando la nuova opzione <span class="uicontrol"> Rimuovi tutti i risultati</span> . </p> <p>Utilizzate questa nuova opzione insieme ad altre azioni della regola business per creare "pagine di destinazione in scatola". In altre parole, si desidera creare il contenuto di una pagina esclusivamente in base alle azioni delle regole aziendali e si devono eliminare i risultati "naturali" della ricerca. </p> <p>Consultate <a href="../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7" format="dita" scope="local"> Aggiunta di una nuova regola</a> business o <a href="../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087" format="dita" scope="local"> Modifica di una regola</a>business. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Banner e regole aziendali </p> </td> 
   <td colname="col2"> <p> È stata aggiunta un'opzione di supporto in cui potete scegliere di rifiutare il push dei banner live in base alla regola business che fa riferimento al banner. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Problemi risolti**

* Le regole aziendali funzionavano in modo incoerente quando c&#39;era un [!DNL Stage] indice.
* Le regole di analisi automatica ora sono applicate alle pagine di destinazione in scatola.

   Vedere la tabella delle opzioni in [Aggiunta di una regola](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)di classificazione.

* [!DNL promosearch.cgi] non restituiva promozioni.

   Consultate [Le Ricerche](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

* Invio di regole che a volte fanno riferimento a molti banner non riuscito.

   Consultate [I banner](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA).

* **[!UICONTROL Did You Mean]** il caching delle query di ricerca ora è disabilitato.

   Vedete [Che Intendete](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E).

