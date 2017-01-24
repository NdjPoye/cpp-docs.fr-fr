---
title: "isalnum, iswalnum, _isalnum_l, _iswalnum_l | Microsoft Docs"
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
  - "_iswalnum_l"
  - "_isalnum_l"
  - "iswalnum"
  - "isalnum"
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
  - "_istalnum_l"
  - "_iswalnum_l"
  - "iswalnum"
  - "_isalnum_l"
  - "isalnum"
  - "_istalnum"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isalnum_l (fonction)"
  - "_ismbcalnum_l (fonction)"
  - "_istalnum (fonction)"
  - "_istalnum_l (fonction)"
  - "_iswalnum_l (fonction)"
  - "isalnum (fonction)"
  - "istalnum (fonction)"
  - "iswalnum (fonction)"
ms.assetid: 0dc51306-ade8-4944-af27-e4176fc89093
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isalnum, iswalnum, _isalnum_l, _iswalnum_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un entier représente un caractère alphanumérique.  
  
## Syntaxe  
  
```  
int isalnum(   
   int c   
);  
int iswalnum(   
   wint_t c   
);  
int _isalnum_l(   
   int c,  
   _locale_t locale  
);  
int _iswalnum_l(   
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
 Chacune de ces routines retourne une valeur différente de zéro si `c` est une représentation particulière d'un caractère alphanumérique.  `isalnum` retourne une valeur différente de zéro si `isalpha` ou `isdigit` est différent de zéro pour `c`. Autrement dit, si `c` est dans les limites A – Z, a – z, ou 0 – 9.  `iswalnum` retourne une valeur différente de zéro si `iswalpha` ou `iswdigit` est différent de zéro pour `c`.  Chacune de ces routines retourne 0 si `c` ne remplit pas la condition de test.  
  
 Les versions de ces fonctions possédant le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Le comportement d'`isalnum` et d'`_isalnum_l` n'est pas défini si `c` n'a pas la valeur EOF ni n'est compris entre 0 et 0xFF, inclus.  Lorsqu'une bibliothèque CRT de débogage est utilisée et que `c` ne fait pas partie de ces valeurs, les fonctions déclenchent une assertion.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_istalnum`|`isalnum`|[\_ismbcalnum](../../c-runtime-library/reference/ismbcalnum-functions.md)|`iswalnum`|  
|`_istalnum_l`|`_isalnum_l`|`_ismbcalnum_l`|`_iswalnum_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`isalnum`|\<ctype.h\>|  
|`iswalnum`|\<ctype.h\> ou \<wchar.h\>|  
|`_isalnum_l`|\<ctype.h\>|  
|`_iswalnum_l`|\<ctype.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::Char::IsLetterOrDigit](https://msdn.microsoft.com/en-us/library/system.char.isletterordigit.aspx).  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)