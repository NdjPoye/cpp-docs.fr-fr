---
title: "Interpr&#233;tation des s&#233;quences de caract&#232;res multioctets | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.character.multibyte"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "MBCS (C++), page de codes de paramètres régionaux"
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Interpr&#233;tation des s&#233;quences de caract&#232;res multioctets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La plupart des routines de caractères multi\-octets dans la bibliothèque Runtime de Microsoft pour identifier les séquences de caractères multioctets liées à une page de codes multioctets.  La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  
  
### Routines multioctets dépendantes des paramètres régionaux  
  
|Routine|Utilisez|  
|-------------|--------------|  
|[\_mbclen, mblen, \_mblen\_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Validez et retournez le nombre d'octets dans un caractère multioctets|  
|[strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Pour les chaînes de caractères multioctets : valide chaque caractère de la chaîne ; retourne la longueur de chaîne  Pour les chaînes de caractères larges: retourne la longueur de chaîne.|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Convertit la séquence de caractères multioctets à la séquence correspondante de caractères larges|  
|[mbtowc, \_mbtowc\_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Convertit le caractère multioctets au caractère élargi correspondant|  
|[wcstombs, \_wcstombs\_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Convertit la séquence de caractères larges à la séquence correspondante de caractères multioctets|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Convertit le caractère élargi au caractère multioctets correspondant|  
  
## Voir aussi  
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)