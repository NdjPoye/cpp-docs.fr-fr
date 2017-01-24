---
title: "isupper, _isupper_l, iswupper, _iswupper_l | Microsoft Docs"
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
  - "isupper"
  - "iswupper"
  - "_iswupper_l"
  - "_isupper_l"
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
  - "isupper"
  - "_istupper"
  - "iswupper"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_istupper (fonction)"
  - "_isupper_l (fonction)"
  - "_iswupper_l (fonction)"
  - "istupper (fonction)"
  - "isupper (fonction)"
  - "isupper_l (fonction)"
  - "iswupper (fonction)"
  - "iswupper_l (fonction)"
ms.assetid: da2bcc9f-241c-48c0-9a0e-ad273827e16a
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isupper, _isupper_l, iswupper, _iswupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un entier représente un caractère en majuscules.  
  
## Syntaxe  
  
```  
int isupper(  
   int c   
);  
int _isupper_l (  
   int c,  
   _locale_t locale  
);  
int iswupper(  
   wint_t c   
);  
int _iwsupper_l(  
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
 Chacune de ces routines retourne une valeur différente de zéro si `c` est une représentation particulière d'une majuscule.  `isupper` retourne une valeur différente de zéro si `c` est une majuscule \(A – Z\).  `iswupper` retourne une valeur différente de zéro si `c` est un caractère large correspondant à une majuscule, ou si `c` est un jeu de caractères larges défini par l'implémentation pour lequel aucuns de`iswcntrl`, `iswdigit`,`iswpunct`, ou `iswspace` n'est différent de zéro.  Chacune de ces routines retourne 0 si `c` ne remplit pas la condition de test.  
  
 Les versions de ces fonctions qui ont le suffixe `_l` utilisent les paramètres régionaux passés plutôt que les paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Le comportement d'`isupper` et d'`_isupper_l` n'est pas défini si `c` n'a pas la valeur EOF ni n'est compris entre 0 et 0xFF, inclus.  Lorsqu'une bibliothèque CRT de débogage est utilisée et que `c` ne fait pas partie de ces valeurs, les fonctions déclenchent une assertion.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_istupper`|`isupper`|[\_ismbcupper](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`iswupper`|  
|`_istupper_l`|`_isupper_l`|[\_ismbclower, \_ismbclower\_l, \_ismbcupper, \_ismbcupper\_l](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`_iswupper_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`isupper`|\<ctype.h\>|  
|`_isupper_l`|\<ctype.h\>|  
|`iswupper`|\<ctype.h\> ou \<wchar.h\>|  
|`_iswupper_l`|\<ctype.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::Char::IsUpper](https://msdn.microsoft.com/en-us/library/system.char.isupper.aspx)  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)