---
title: "isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_iswxdigit_l"
  - "iswxdigit"
  - "isxdigit"
  - "_isxdigit_l"
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
  - "iswxdigit"
  - "isxdigit"
  - "_istxdigit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_istxdigit (fonction)"
  - "_iswxdigit_l (fonction)"
  - "_isxdigit_l (fonction)"
  - "caractères hexadécimaux"
  - "istxdigit (fonction)"
  - "iswxdigit (fonction)"
  - "iswxdigit_l (fonction)"
  - "isxdigit (fonction)"
  - "isxdigit_l (fonction)"
ms.assetid: c8bc5146-0b58-4e3f-bee3-f2318dd0f829
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un entier représente un caractère qui est un chiffre hexadécimal.  
  
## Syntaxe  
  
```  
int isxdigit(  
   int c   
);  
int iswxdigit(  
   wint_t c   
);  
int _isxdigit_l(  
   int c,  
   _locale_t locale  
);  
int _iswxdigit_l(  
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
 Chacune de ces routines retourne une valeur non nulle si `c` est une représentation particulière d'un chiffre hexadécimal.  `isxdigit` retourne une valeur non nulle si `c` est un chiffre hexadécimal \(A \- F, a \- f, ou 0 \- 9\).  `iswxdigit` retourne une valeur non nulle si `c` est un caractère large correspondant à un caractère qui est un chiffre hexadécimal.  Chacune de ces routines retourne zéro si `c` ne satisfait pas à la condition de test.  
  
 Pour le paramètre "C", la fonction `iswxdigit` ne gère pas les caractères pleine chasse hexadécimaux Unicode.  
  
 Les versions de ces fonctions avec le suffixe `_l` utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Le comportement d'`isxdigit` et d'`_isxdigit_l` n'est pas défini si `c` n'a pas la valeur EOF ni n'est compris entre 0 et 0xFF, inclus.  Lorsqu'une bibliothèque CRT de débogage est utilisée et que `c` ne fait pas partie de ces valeurs, les fonctions déclenchent une assertion.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_istxdigit`|`isxdigit`|`isxdigit`|`iswxdigit`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`isxdigit`|\<ctype.h\>|  
|`iswxdigit`|\<ctype.h\> ou \<wchar.h\>|  
|`_isxdigit_l`|\<ctype.h\>|  
|`_iswxdigit_l`|\<ctype.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::Char::IsNumber](https://msdn.microsoft.com/en-us/library/system.char.isnumber.aspx)  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)