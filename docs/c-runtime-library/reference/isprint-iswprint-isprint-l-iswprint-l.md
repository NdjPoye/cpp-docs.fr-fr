---
title: "isprint, iswprint, _isprint_l, _iswprint_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iswprint"
  - "isprint"
  - "_isprint_l"
  - "_iswprint_l"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "iswprint"
  - "_istprint"
  - "isprint"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isprint_l (fonction)"
  - "_istprint (fonction)"
  - "_iswprint_l (fonction)"
  - "isprint (fonction)"
  - "isprint_l (fonction)"
  - "istprint (fonction)"
  - "iswprint (fonction)"
  - "iswprint_l (fonction)"
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isprint, iswprint, _isprint_l, _iswprint_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un entier représente un caractère imprimable.  
  
## Syntaxe  
  
```  
int isprint(  
   int c   
);  
int iswprint(  
   wint_t c   
);  
int _isprint_l(  
   int c,  
   _locale_t locale  
);  
int _iswprint_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `c`  
 Entier à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces routines retourne une valeur différente de zéro si `c` est une représentation particulière d'un caractère imprimable.  `isprint` retourne une valeur différente de zéro si `c` est un caractère imprimable \- ceci inclut l'espace \(0x20 – 0x7E\).  `iswprint` retourne une valeur différente de zéro si `c` est un caractère large imprimable \- ceci inclut l'espace large \(0x20 – 0x7E\).  Chacune de ces routines retourne zéro si `c` ne satisfait pas à la condition de test.  
  
 Le résultat de la condition de test pour ces fonctions dépend du paramètre de catégorie `LC_CTYPE` des paramètres régionaux. Pour plus d'informations, consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Le comportement d' `isprint` et d' `_isprint_l` n'est pas défini si `c` n'a pas la valeur EOF ni n'est compris entre 0 et 0xFF, inclus.  Lorsqu'une bibliothèque CRT de débogage est utilisée et que `c` ne fait pas partie de ces valeurs, les fonctions déclenchent une assertion.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_unicode défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|**\_** `istprint`|`isprint`|[\_ismbcprint](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswprint`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`isprint`|\<ctype.h\>|  
|`iswprint`|\<ctype.h\> ou \<wchar.h\>|  
|`_isprint_l`|\<ctype.h\>|  
|`_iswprint_l`|\<ctype.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)