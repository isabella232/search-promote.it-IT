---
description: Search&amp;Note sulla versione di Promote 8.13.0.
solution: Target
title: Search&amp;Promote 8.13.0 Note sulla versione (16/04/2014)
topic: Note sulla versione, Ricerca nel sito e merchandising
uuid: b3524992-ff00-4a7c-a404-078242456734
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---


# Note sulla versione di Search&amp;Promote 8.13.0 (16/04/2014){#search-promote-release-notes}

| Nuove funzionalità e miglioramenti | Descrizione |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Facet dinamici con supporto completo per la corrispondenza delle tabelle | Alcuni clienti avevano molti attributi di &quot;livello SKU&quot; che volevano selezionare e visualizzare tramite i facet dinamici. È quindi ora possibile associare facoltativamente ogni campo facet dinamico a un massimo di un nome di tabella in una configurazione account statica. Tali relazioni di tabella possono quindi essere applicate in fase di ricerca per qualsiasi campo di facet dinamico coinvolto nella ricerca. Consulta [Informazioni sui fatti dinamici](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899). |

**Problemi risolti**

* È stato modificato il campo di descrizione della visualizzazione dati per utilizzare il tag `<search-display-field>` anziché `<search-description>`.
* È stata aggiunta una funzione nel connettore indice per rendere la chiave primaria la concatenazione di due o più campi.
* Lo script AttributeLoader-Regen-Enabled `attributeloader-regen.pl` è stato modificato in valori non codificati in HTML.
* Trattamento corrispondente del tempo di indicizzazione e del tempo di ricerca degli spazi bianchi per le query di &quot;ricerca degli intervalli&quot;.
* L’aggiunta di una regola business a volte causava un errore quando i facet dinamici venivano abilitati.

   Consultare [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Errore JavaScript durante l&#39;aggiunta o la modifica di una definizione in **Impostazioni** > **SPIN** > **IndexConnector**.
* Dopo il salvataggio di una Regola aziendale, veniva visualizzato che, quando l&#39;ora era selezionata durante la creazione della Regola aziendale, veniva impostata sul fuso orario GMT per impostazione predefinita. Dopo il salvataggio, è apparso che il Fuso orario dell&#39;account ha poi preso effetto.

   Consultare [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* L&#39;ordinamento delle regole business in Stage non funzionava correttamente.

   Consultare [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Il reporting sulle prestazioni di ricerca è stato migliorato grazie alla possibilità di pianificare i rapporti per la consegna delle e-mail.
* La pianificazione fissa della regola business veniva automaticamente modificata in Ora legale.

   Consultare [Informazioni sulle regole aziendali](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Se è stato definito un numero elevato di campi dei facet dinamici, gli utenti hanno registrato tempi di risposta di ricerca di base lenti.
* Si sono verificati errori di indice dell&#39;intervallo.
* L&#39;accesso a Dynamic Media Classic nei datacenter non nordamericani è stato interrotto.
* La funzione di convalida SPIN XPath restituiva un errore di falso positivo.

* Dopo un&#39;operazione di abilitazione/disattivazione SPIN, l&#39;utente è stato reindirizzato alla pagina di accesso al centro membri.

