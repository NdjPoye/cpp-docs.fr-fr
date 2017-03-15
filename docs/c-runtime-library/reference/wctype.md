---
title: "wctype | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wctype"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wctype"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wctype (fonction)"
  - "caractères larges"
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wctype
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine une règle de classification pour les codes de caractères étendus.  
  
## Syntaxe  
  
```  
wctype_t wctype(  
   const char * property   
);  
```  
  
#### Paramètres  
 `property`  
 Propriété de chaîne.  
  
## Valeur de retour  
 Si la catégorie `LC_CTYPE` des paramètres régionaux actuels ne définit pas de règle de classification dont le nom correspond à la catégorie chaîne de caractères `property`, la fonction retourne zéro.  Sinon, elle retourne une valeur non nulle appropriée à utiliser comme deuxième argument pour un appel suivant à [towctrans](../../c-runtime-library/reference/towctrans.md).  
  
## Notes  
 La fonction détermine une règle de classification pour les codes de caractères étendus.  Les paires suivantes d'appels ont le même comportement dans les paramètres régionaux \(mais une implémentation peut définir des règles supplémentaires de classification même dans les paramètres régionaux « c » c\) :  
  
|Fonction|Identique à .|  
|--------------|-------------------|  
|`iswalnum(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alnum" ) )`|  
|`iswalpha(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alpha" ) )`|  
|`iswcntrl(`  `c`  `)`|`iswctype(`  `c` `, wctype( "cntrl" ) )`|  
|`iswdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "digit" ) )`|  
|`iswgraph(`  `c`  `)`|`iswctype(`  `c` `, wctype( "graph" ) )`|  
|`iswlower(`  `c`  `)`|`iswctype(`  `c` `, wctype( "lower" ) )`|  
|`iswprint(`  `c`  `)`|`iswctype(`  `c` `, wctype( "print" ) )`|  
|`iswpunct(`  `c`  `)`|`iswctype(`  `c` `, wctype( "punct" ) )`|  
|`iswspace(`  `c`  `)`|`iswctype(`  `c` `, wctype( "space" ) )`|  
|`iswupper(`  `c`  `)`|`iswctype(`  `c` `, wctype( "upper" ) )`|  
|`iswxdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "xdigit" ) )`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`wctype`|\<wctype.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)