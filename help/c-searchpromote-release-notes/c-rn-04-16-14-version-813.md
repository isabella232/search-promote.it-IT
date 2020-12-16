---
description: nulle
seo-description: nulle
seo-title: Search&amp;Promote 8.13.0 - Note sulla versione (16/04/2014)
solution: Target
title: Search&amp;Promote 8.13.0 - Note sulla versione (16/04/2014)
topic: Release Notes,Site search and merchandising
uuid: b3524992-ff00-4a7c-a404-078242456734
translation-type: tm+mt
source-git-commit: 9d5ac055d665b39d09b28063179d74a389d7f830
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---


# Note sulla versione di Search&amp;Promote 8.13.0 (16/04/2014){#search-promote-release-notes}

| Nuove funzioni e miglioramenti | Descrizione |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Facet dinamici con supporto completo per le corrispondenze tra tabelle | Alcuni clienti avevano molti attributi &quot;livello SKU&quot; che volevano selezionare e visualizzare tramite facet dinamici. Pertanto, è ora possibile associare facoltativamente ogni campo facet dinamico con un massimo di un nome di tabella in una configurazione account statica. Tali relazioni di tabella possono quindi essere applicate in fase di ricerca per qualsiasi campo facet dinamico coinvolto nella ricerca. Vedere [Informazioni sui fatti dinamici](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899). |

**Problemi risolti**

* È stato modificato il campo di descrizione della visualizzazione dati in modo da utilizzare il tag `<search-display-field>` invece di `<search-description>`.
* È stata aggiunta una funzionalità al connettore indice per rendere la chiave primaria la concatenazione di due o più campi.
* Lo script AttributeLoader-Regen-Enabled `attributeloader-regen.pl` è stato modificato in valori non codificati in HTML.
* Corrispondenza tra tempo indice e tempo di ricerca per le query &quot;range search&quot;.
* L&#39;aggiunta di una regola business a volte causava un errore quando Facet dinamici era abilitato.

   Vedere [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Errore Javascript durante l&#39;aggiunta o la modifica di una definizione in **Settings** > **SPIN** > **IndexConnector**.
* Dopo il salvataggio di una regola business, veniva visualizzato che quando l&#39;ora veniva selezionata durante la creazione della regola business, per impostazione predefinita veniva impostata sul fuso orario GMT. Dopo il salvataggio, sembrava che il Fuso orario dell&#39;account fosse diventato effettivo.

   Vedere [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* L&#39;ordinamento delle regole di business in Stage non funzionava correttamente.

   Vedere [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* La generazione di rapporti sulle prestazioni di ricerca è stata migliorata grazie alla possibilità di pianificare i rapporti per la consegna delle e-mail.
* La pianificazione fissa della regola business veniva automaticamente modificata in Ora legale.

   Vedere [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Se sono stati definiti numerosi campi di facet dinamici, gli utenti hanno riscontrato tempi di risposta di ricerca di base lenti.
* Si sono verificati errori di indice dell&#39;intervallo falsi.
* L&#39;accesso Dynamic Media Classic nei datacenter non nordamericani è stato interrotto.
* La funzione di convalida SPIN XPath restituiva un errore falso positivo.

* Dopo un&#39;operazione di attivazione/disattivazione SPIN, l&#39;utente è stato reindirizzato alla pagina di accesso del centro membri.

