---
description: È possibile definire i formati di data utilizzati per analizzare e indicizzare qualsiasi campo con un tipo di dati "data".
seo-description: È possibile definire i formati di data utilizzati per analizzare e indicizzare qualsiasi campo con un tipo di dati "data".
seo-title: Formati data
solution: Target
title: Formati data
topic: Appendices,Site search and merchandising
uuid: 148914b5-33ef-41db-8404-67c03f6f0832
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 2%

---


# Formati data{#date-formats}

È possibile definire i formati di data utilizzati per analizzare e indicizzare qualsiasi campo con un tipo di dati &quot;data&quot;.

Il formato della data e dell&#39;ora è specificato con una stringa di formato. La stringa di formato è costituita da zero o più specifiche di conversione (una specifica di conversione è costituita da un segno di percentuale e un altro carattere) e da caratteri ordinari. Viene fornito un elenco predefinito di stringhe di formato data per ciascun campo data.

Hai il controllo completo su questo elenco e puoi aggiungerlo o modificarlo in base alle esigenze del tuo sito. La stringa del formato principale ha la precedenza e le stringhe di formato successive vengono utilizzate solo se l&#39;analisi del contenuto di un determinato tag di metadati genera un errore.

Ad esempio, se hai specificato i seguenti formati di data:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d, %Y %T %Z </p> <p>%b %d, %Y %T %Z </p> <p>%A %B %d, %Y %T %Z </p> <p>%A %b %d, %Y %T %Z </p> <p>%a %B %d, %Y %T %Z </p> <p>%a %b %d, %Y %T %Z </p> <p>%d %b %Y %T %Z </p> </td> 
  </tr> 
 </tbody> 
</table>

Il primo formato, &quot;%B %d, %Y %T %Z&quot;, corrisponde alle date indicate di seguito &quot;20 settembre 2014 13:12:00 PDT&quot;. Se il contenuto del tag di metadati non può essere analizzato con questa stringa di formato, verrà provato il formato disponibile successivo &quot;%b %d, %Y %T %Z&quot;. Questo formato corrisponde alle date seguenti: &quot;20 settembre 2014 3:12:00 PDT&quot;. Se il contenuto dei tag di metadati non può essere analizzato con questa stringa di formato, la ricerca nel sito/merchandising sposta l’elenco delle stringhe di formato fino a quando non trova una stringa di formato che funzioni.

Nella tabella seguente sono descritte le stringhe di formato della data disponibili:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Formato dati </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p>Corrisponde alla rappresentazione nazionale del nome completo del giorno della settimana, ad esempio "Monday". La rappresentanza nazionale è determinata dall'impostazione "Lingua" sull'opzione "Parole e lingue" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> corrisponde alla rappresentazione nazionale del nome abbreviato del giorno della settimana, dove l'abbreviazione è costituita dai primi tre caratteri, ad esempio "Lun." La rappresentanza nazionale è determinata dall'impostazione "Lingua" sull'opzione "Parole e lingue" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> corrisponde alla rappresentazione nazionale del nome completo del mese, ad esempio "Giugno." La rappresentanza nazionale è determinata dall'impostazione "Lingua" sull'opzione "Parole e lingue" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> corrisponde alla rappresentazione nazionale del nome abbreviato del mese, dove l'abbreviazione è costituita dai primi tre caratteri, ad esempio "Giu." La rappresentanza nazionale è determinata dall'impostazione "Lingua" sull'opzione "Parole e lingue" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p> equivale a "%m/%d/%y", ad esempio "06/06/01" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> corrisponde al giorno del mese come numero decimale (01-31) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> corrisponde al giorno del mese come numero decimale (1-31); le cifre singole sono precedute da uno spazio vuoto </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> corrisponde all'ora (orologio a 24 ore) come numero decimale (00-23) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> corrisponde alla rappresentazione nazionale del nome abbreviato del mese, dove l'abbreviazione è costituita dai primi tre caratteri, ad esempio "Giu" (uguale a %b) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> corrisponde all'ora (orologio di 12 ore) come numero decimale (01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> corrisponde al giorno dell'anno come numero decimale (001-366) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> corrisponde all'ora (orologio a 24 ore) come numero decimale (0-23); le cifre singole sono precedute da uno spazio vuoto </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> corrisponde all’ora (orologio di 12 ore) come numero decimale (1-12); le cifre singole sono precedute da uno spazio vuoto </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> corrisponde al minuto come numero decimale (00-59) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> restituisce il mese come numero decimale (01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> corrisponde alla rappresentanza nazionale di "ante meridiem" o "post meridiem", a seconda dei casi, ad esempio "PM." La rappresentanza nazionale è determinata dall'impostazione "Lingua" sull'opzione "Parole e lingue" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p> equivale a "%H:%M", ad esempio "13:23" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p> equivale a "%I:%M:%S %p", ad esempio "01:23:45 PM" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> restituisce il secondo come numero decimale (00-60) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p> equivale a "%H:%M:%S", ad esempio "13:26:47" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> corrisponde al numero della settimana dell'anno (domenica come primo giorno della settimana) come numero decimale (00-53) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p> equivale a "%e-%b-%Y", ad esempio "6 giugno 2001" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> corrisponde all'anno con un numero decimale, ad esempio "2001" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> corrisponde all'anno senza secolo come numero decimale (00-99) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> corrisponde al nome del fuso orario </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> matches "%" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Stringhe formato predefinite**

Le seguenti stringhe di formato predefinite sono utilizzate dai modelli. È possibile aggiungere o modificare l&#39;elenco come necessario.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Stringa formato predefinita </p> </th> 
   <th colname="col2" class="entry"> <p>Esempio risultante </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 5 settembre 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 5 settembre 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Domenica 5 settembre 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Domenica 5 settembre 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sun 5 settembre 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sun 5 settembre 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d %b %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 5 set 1999 13:12:00 PDT </p> </td> 
  </tr> 
 </tbody> 
</table>

