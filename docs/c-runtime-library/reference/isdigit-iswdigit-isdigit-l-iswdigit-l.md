---
title: "isdigit, iswdigit, _isdigit_l, _iswdigit_l | Microsoft Docs"
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
  - "_isdigit_l"
  - "iswdigit"
  - "_iswdigit_l"
  - "isdigit"
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
  - "_iswdigit_l"
  - "_isdigit_l"
  - "iswdigit"
  - "isdigit"
  - "_istdigit"
  - "_istdigit_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "iswdigit (fonction)"
  - "iswdigit_l (fonction)"
  - "_iswdigit_l (fonction)"
  - "_istdigit_l (fonction)"
  - "_istdigit (fonction)"
  - "istdigit (fonction)"
  - "isdigit (fonction)"
  - "isdigit_l (fonction)"
  - "_ismbcdigit_l (fonction)"
  - "_isdigit_l (fonction)"
ms.assetid: 350b0093-843a-47b0-954e-c1776e8a3853
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isdigit, iswdigit, _isdigit_l, _iswdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un entier représente un chiffre décimal.  
  
## Syntaxe  
  
```  
int isdigit(   
   int c   
);  
int iswdigit(   
   wint_t c   
);  
int _isdigit_l(   
   int c,  
   _locale_t locale  
);  
int _iswdigit_l(   
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
 Chacune de ces routines retourne une valeur différente de zéro si `c` est une représentation particulière d'un caractère de chiffre décimal.  `isdigit` retourne une valeur différente de zéro si `c` est un chiffre décimal \(0 à 9\).  `iswdigit` retourne une valeur différente de zéro si `c` est un caractère élargi correspondant au caractère d'un chiffre décimal.  Chacune de ces routines retourne 0 si `c` ne remplit pas la condition de test.  
  
 Les versions de ces fonctions qui ont le suffixe `_l` utilisent les paramètres régionaux passés plutôt que les paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Le comportement d'`isdigit` et d'`_isdigit_l` n'est pas défini si `c` n'a pas la valeur EOF ni n'est compris entre 0 et 0xFF, inclus.  Lorsqu'une bibliothèque CRT de débogage est utilisée et que `c` ne fait pas partie de ces valeurs, les fonctions déclenchent une assertion.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_istdigit`|`isdigit`|[\_ismbcdigit](../../c-runtime-library/reference/ismbcalnum-functions.md)|`iswdigit`|  
|`_istdigit_l`|`_isdigit_l`|[\_ismbcdigit\_l](../../c-runtime-library/reference/ismbcalnum-functions.md)|`_iswdigit_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`isdigit`|\<ctype.h\>|  
|`iswdigit`|\<ctype.h\> ou \<wchar.h\>|  
|`_isdigit_l`|\<ctype.h\>|  
|`_iswdigit_l`|\<ctype.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::Char::IsDigit](https://msdn.microsoft.com/en-us/library/system.char.isdigit.aspx)  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)