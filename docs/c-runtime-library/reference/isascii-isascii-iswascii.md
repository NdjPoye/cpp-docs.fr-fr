---
title: "isascii, __isascii, iswascii | Microsoft Docs"
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
  - "iswascii"
  - "__isascii"
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
  - "iswascii"
  - "istascii"
  - "__isascii"
  - "_istascii"
  - "isascii"
  - "ctype/isascii"
  - "ctype/__isascii"
  - "corecrt_wctype/iswascii"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__isascii (fonction)"
  - "_isascii (fonction)"
  - "isascii (fonction)"
  - "_istascii (fonction)"
  - "istascii (fonction)"
  - "iswascii (fonction)"
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isascii, __isascii, iswascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un caractère particulier est un caractère ASCII.  
  
## Syntaxe  
  
```  
int __isascii(   
   int c   
);  
int iswascii(   
   wint_t c   
);  
#define isascii __isascii  
```  
  
#### Paramètres  
 `c`  
 Entier à tester.  
  
## Valeur de retour  
 Chacun de ces routines retourne zéro si `c` est une représentation particulière d’un caractère ASCII.`__isascii` Retourne une valeur différente de zéro si `c` est un caractère ASCII \(dans la plage 0 x 00 à 0x7F\).`iswascii` Retourne une valeur différente de zéro si `c` est une représentation de caractères larges d’un caractère ASCII. Chacune de ces routines retourne 0 si `c` ne répond pas à la condition de test.  
  
## Notes  
 Les deux `__isascii` et `iswascii` sont implémentés en tant que macros, sauf si la macro de préprocesseur \_CTYPE\_DISABLE\_MACROS est défini.  
  
 Pour la compatibilité descendante, `isascii` est implémenté comme un si seule macro [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) n’est pas défini ou est défini sur 0 ; sinon, il n’est pas défini.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`isascii`, `__isascii`|C: \< ctype.h \><br /><br /> C\+\+ : \< cctype \> ou \< ctype.h \>|  
|`iswascii`|C: \< wctype.h \>, \< ctype.h \>, ou \< wchar.h \><br /><br /> C\+\+ : \< cwctype \>, \< cctype \>, \< wctype.h \>, \< ctype.h \>, ou \< wchar.h \>|  
  
 Le `isascii`, `__isascii` et `iswascii` les fonctions sont spécifiques de Microsoft. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)