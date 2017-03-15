---
title: "Cat&#233;gories de param&#232;tres r&#233;gionaux | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LC_MAX"
  - "LC_MIN"
  - "LC_MONETARY"
  - "LC_TIME"
  - "LC_NUMERIC"
  - "LC_COLLATE"
  - "LC_CTYPE"
  - "LC_ALL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LC_ALL (constante)"
  - "LC_COLLATE (constante)"
  - "LC_CTYPE (constante)"
  - "LC_MAX (constante)"
  - "LC_MIN (constante)"
  - "LC_MONETARY (constante)"
  - "LC_NUMERIC (constante)"
  - "LC_TIME (constante)"
  - "constantes de paramètres régionaux"
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Cat&#233;gories de param&#232;tres r&#233;gionaux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <locale.h>  
  
```  
  
## Notes  
 Les catégories de paramètres régionaux sont des constantes manifestes utilisées par les routines de localisation pour spécifier quelle partie des informations de paramètres régionaux d'un programme sera utilisée.  Les paramètres régionaux font référence à la localité \(ou le pays ou la région\) pour lesquels certains aspects de votre programme peuvent être personnalisés.  Les zones dépendant des paramètres régionaux incluent par exemple la mise en forme des dates ou le format d'affichage des valeurs monétaires.  
  
|Catégorie de paramètres régionaux|Parties de programme affectées|  
|---------------------------------------|------------------------------------|  
|`LC_ALL`|Le comportement spécifique aux paramètres régionaux \(toutes les catégories\)|  
|`LC_COLLATE`|Comportement des fonctions `strcoll` et `strxfrm`|  
|`LC_CTYPE`|Le comportement des fonctions gérant les caractères \(à l'exception de **isdigit**, `isxdigit`, `mbstowcs`, et `mbtowc`, qui ne sont pas concernés\)|  
|`LC_MAX`|Identique à `LC_TIME`.|  
|`LC_MIN`|Identique à `LC_ALL`.|  
|`LC_MONETARY`|Les informations de mise en forme monétaire retournées par la fonction `localeconv`.|  
|`LC_NUMERIC`|Le caractère de virgule décimale pour les routines de sortie mises en forme \(par exemple `printf`\), les routines de conversion de données, et les informations de mise en forme non monétaires retournées par `localeconv`.|  
|`LC_TIME`|Comportement de la fonction `strftime`|  
  
 Pour obtenir un exemple, consultez [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
## Voir aussi  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll, fonctions](../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)