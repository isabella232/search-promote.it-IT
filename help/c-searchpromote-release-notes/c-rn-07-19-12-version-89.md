---
description: Search&amp;Note sulla versione di Promote 8.9.
solution: Target
title: Search&amp;Promote 8.9 Note sulla versione (19/07/2012)
topic: Release Notes,Site search and merchandising
uuid: 3853c75d-19ed-4e36-9e81-dcbffe5f5b0c
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 1%

---


# Note sulla versione di Search&amp;Promote 8.9 (19/07/2012){#search-promote-release-notes}

**Nuova funzionalità**

* Miglioramenti alla gestione dei metadati - Definizione dei metadati dinamici dai feed dei clienti

   Crea uno schema per riconfigurare dinamicamente l’account di Search&amp;Promote in base alle definizioni dei metadati fornite dal cliente.
* Miglioramenti delle prestazioni dell&#39;indicizzazione - Index Loader

   Index Loader è un nuovo modo per importare il contenuto XML direttamente in un indice Search&amp;Promote. Si tratta di un sottoinsieme della funzionalità del connettore indice esistente progettata per importare rapidamente i nostri file di feed XML standard.

**Problemi risolti e miglioramenti**

* È stato aggiunto il supporto per la modifica dell&#39;opzione di ordinamento da parte di una regola business.
* Nel sistema della Guida `<search-description>` il tag mostra invece il corpo quando il tag meta per la descrizione ha contenuto vuoto.
* È stata aggiunta la possibilità di tenere traccia degli hit di tabella applicabili per i risultati aggiunti tramite azioni basate sui risultati.
* È stato aggiunto il supporto per l’invio di parametri di query tramite POST
* Durante la ricerca per indicizzazione, in alcuni casi è possibile saltare un&#39;operazione mirror_account finale.
* Gli URL di Adobe Analytics non includono gli argomenti CGI e il codice Search&amp;Promote che esegue le ricerche Adobe Analytics necessarie per rimuovere in modo simile gli argomenti CGI dalle chiavi URL.
* Le regole di riscrittura sono scomparse a intermittenza dall’interfaccia utente dopo che sono state inviate a Live.
* Le impostazioni Search&amp;Promote con Did You Mean impostate per formulare suggerimenti a causa di risultati ridotti possono avere risultati intermittenti.
* L&#39;output del test della regola di riscrittura non conteneva interruzioni di riga.
* La pagina Regole URL di ricerca e la pagina Regole URL archivio elenchi ricerca per indicizzazione puntata alla pagina Cronologia errata.
* Quando si fa clic su Modifica su alcuni banner, la pagina Modifica non viene visualizzata.
* A volte la riclassificazione del codice di aggiornamento potrebbe essere straordinariamente lenta.
* La rimozione o il push di un elemento facet non funzionava se il nome del facet utilizzava lettere maiuscole/minuscole.

