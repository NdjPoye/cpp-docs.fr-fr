---
title: "ispunct, iswpunct, _ispunct_l, _iswpunct_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ispunct"
  - "_iswpunct_l"
  - "iswpunct"
  - "_ispunct_l"
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
  - "iswpunct"
  - "_istpunct"
  - "ispunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ispunct_l (fonction)"
  - "_istpunct (fonction)"
  - "_iswpunct_l (fonction)"
  - "ispunct (fonction)"
  - "ispunct_l (fonction)"
  - "istpunct (fonction)"
  - "iswpunct (fonction)"
  - "iswpunct_l (fonction)"
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# ispunct, iswpunct, _ispunct_l, _iswpunct_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un entier représente un caractère de ponctuation.  
  
## Syntaxe  
  
```  
int ispunct(  
   int c   
);  
int iswpunct(  
   wint_t c   
);  
int _ispunct_l(  
   int c,  
   _locale_t locale  
);  
int _iswpunct_l(  
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
 Chacune de ces routines retourne une valeur différente de zéro si `c` est une représentation particulière d'un caractère de ponctuation.  `ispunct` retourne une valeur différente de zéro pour tout caractère imprimable qui n'est pas un espace ou un caractère pour lequel `isalnum` est différent de zéro.  `iswpunct` retourne une valeur différente de zéro pour tout caractère large imprimable qui n'est ni un caractère large d'espace ni un caractère large pour lequel `iswalnum` est différent de zéro.  Chacune de ces routines retourne zéro si `c` ne satisfait pas à la condition de test.  
  
 Le résultat de la condition de test pour la fonction `ispunct` dépend du paramètre de catégorie `LC_CTYPE` des paramètres régionaux. Pour plus d'informations, consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Le comportement d' `ispunct` et d' thème global`_ispunct_l` n'est pas défini si `c` n'a pas la valeur EOF ni n'est compris entre 0 et 0xFF, inclus.  Lorsqu'une bibliothèque CRT de débogage est utilisée et que `c` ne fait pas partie de ces valeurs, les fonctions déclenchent une assertion.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|**\_** `istpunct`|`ispunct`|[\_ismbcpunct](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswpunct`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`ispunct`|\<ctype.h\>|  
|`iswpunct`|\<ctype.h\> ou \<wchar.h\>|  
|`_ispunct_l`|\<ctype.h\>|  
|`_iswpunct_l`|\<ctype.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)