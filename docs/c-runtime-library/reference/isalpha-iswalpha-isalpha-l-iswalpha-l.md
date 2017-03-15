---
title: "isalpha, iswalpha, _isalpha_l, _iswalpha_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iswalpha"
  - "_iswalpha_l"
  - "isalpha"
  - "_isalpha_l"
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
  - "_istalpha"
  - "_ismbcalpha_l"
  - "isalpha"
  - "_isalpha_l"
  - "iswalpha"
  - "_istalpha_l"
  - "_iswalpha_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_isalpha_l (fonction)"
  - "_ismbcalpha (fonction)"
  - "_ismbcalpha_l (fonction)"
  - "_istalpha (fonction)"
  - "_istalpha_l (fonction)"
  - "_iswalpha_l (fonction)"
  - "isalpha (fonction)"
  - "istalpha (fonction)"
  - "iswalpha (fonction)"
ms.assetid: ed6cc2be-c4b0-4475-87ac-bc06d8c23064
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# isalpha, iswalpha, _isalpha_l, _iswalpha_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un entier représente un caractère alphanumérique.  
  
## Syntaxe  
  
```  
int isalpha(   
   int c   
);  
int iswalpha(   
   wint_t c   
);  
int _isalpha_l(   
   int c,  
   _locale_t locale   
);  
int _iswalpha_l(   
   wint_t c,  
   _locale_t locale   
);  
```  
  
#### Paramètres  
 `c`  
 Entier à tester.  
  
 `locale`  
 Les paramètres régionaux à utiliser au lieu des paramètres régionaux actuels.  
  
## Valeur de retour  
 Chacune de ces routines retourne une valeur différente de zéro si `c` est une représentation particulière d'un caractère alphabétique.  `isalpha` retourne une valeur différente de zéro si `c` est dans les limites A – Z ou a – Z.  `iswalpha` retourne une valeur différente de zéro uniquement pour les caractères larges pour lesquels `iswupper` ou `iswlower` est différent de zéro ; autrement dit, pour tout caractère élargi qui est un ensemble défini par l'implémentation  pour lequel aucun de `iswcntrl`, `iswdigit`, `iswpunct`, ou `iswspace` n'est différent de zéro.  Chacune de ces routines retourne 0 si `c` ne remplit pas la condition de test.  
  
 Les versions de ces fonctions possédant le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Le comportement d'`isalpha` et d'`_isalpha_l` n'est pas défini si `c` n'a pas la valeur EOF ni n'est compris entre 0 et 0xFF, inclus.  Lorsqu'une bibliothèque CRT de débogage est utilisée et que `c` ne fait pas partie de ces valeurs, les fonctions déclenchent une assertion.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_istalpha`|`isalpha`|`_ismbcalpha`|`iswalpha`|  
|`_istalpha_l`|`_isalpha_l`|`_ismbcalpha_l`|`_iswalpha_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`isalpha`|\<ctype.h\>|  
|`iswalpha`|\<ctype.h\> ou \<wchar.h\>|  
|`_isalpha_l`|\<ctype.h\>|  
|`_iswalpha_l`|\<ctype.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::Char::IsLetter](https://msdn.microsoft.com/en-us/library/system.char.isletter.aspx)  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)