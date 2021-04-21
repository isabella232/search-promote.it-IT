---
description: Search&amp;Note sulla versione di Promote 8.8.
solution: Target
title: Search&amp;Promote 8.8 Note sulla versione (26/04/2012)
topic-legacy: Release Notes,Site search and merchandising
uuid: ddb9f1af-92a4-4f85-be8f-a36f34d31add
exl-id: 3bd9b6af-99a2-4631-b7a7-0a792122c157
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 1%

---

# Note sulla versione di Search&amp;Promote 8.8 (26/04/2012){#search-promote-release-notes}

**Nuova funzionalità**

* Facet dinamico

   Possibilità di eseguire il facet dinamico rispetto a un set gratuito di attributi associati a ciascuna pagina di contenuto del sito, che potenzialmente cambiano (vengono aggiunti nuovi attributi, quelli vecchi vengono rimossi o rinominati) da indice a indice. Il facet dinamico mappa automaticamente i facet di slot con i facet reali. Il livello di ricerca guidata facilita questa funzione con le regole aziendali.
* Interfaccia utente di Adobe Search&amp;Promote

   Implementazione dell’interfaccia utente Adobe in tutte le pagine web di Adobe Search&amp;Promote.
* Integrazione più stretta con il portale di accesso di Adobe

   I clienti di Adobe Search&amp;Promote possono utilizzare esclusivamente il portale di accesso di Adobe. I clienti attuali [!DNL Adobe Publish], Adobe SiteSearch e Atomz continueranno a utilizzare l’accesso legacy.
* Nuovo analizzatore morfologico per il supporto di cinesi e giapponesi

   L&#39;analizzatore morfologico viene applicato sull&#39;indice e sul tempo di ricerca per supportare cinese e giapponese.
* Supporto per nuovi tipi di documenti, ad esempio Microsoft Office 2010

   La ricerca può convertire in HTML vari tipi di documenti, ad esempio .doc, .docx, .pdf e .mp3 prima di inserirsi nell’indicizzatore.
* Nuovo Adobe Guida in linea di Search&amp;Promote

   Il sistema di Guida in linea dispone di una nuova interfaccia utente e ora è basato su attività.

**Problemi risolti e miglioramenti**

* È stato corretto il push in diretta di un banner utilizzando Stage Manager, con conseguente interruzione delle funzionalità di Dynamic Media Classic in tempo reale.
* È stato risolto un problema a causa del quale la modifica di una regola con il trigger &quot;Query Parameter does not exist&quot; (Parametro query non esiste) veniva tradotta in modo errato in &quot;Keyword contains&quot; (Parola chiave contiene).
* È stato risolto un problema che impediva di modificare il parametro la seconda volta.
* È stato risolto un problema relativo al connettore indice a causa del quale due o più definizioni di mappa non potevano puntare allo stesso valore di metadati/campi.
* Sono stati risolti dei problemi relativi alla ricerca per indicizzazione di alcuni documenti PDF. L&#39;aggiornamento a 3.03 risolve i recenti arresti anomali.
* Aggiunta la possibilità di descrizioni più brevi delle regole business (ad esempio, non visualizzare field_table nel manager).
* Il menu di navigazione Ricerca guidata contiene un massimo di nove elementi. Ora il massimo è 20.
* Miglioramenti delle prestazioni apportati al connettore indice.
