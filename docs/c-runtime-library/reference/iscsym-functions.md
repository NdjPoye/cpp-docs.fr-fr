---
title: "iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l | Microsoft Docs"
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
  - "_iswcsym_l"
  - "__iswcsym"
  - "__iscsym"
  - "_iswcsymf_l"
  - "_iscsym_l"
  - "__iswcsymf"
  - "__iscsymf"
  - "_iscsymf_l"
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
  - "_iswcsym_l"
  - "_iswcsymf_l"
  - "iscsymf"
  - "iswcsymf"
  - "__iswcsym"
  - "__iswcsymf"
  - "iscsym"
  - "iswcsym"
  - "__iscsym"
  - "_iscsym_l"
  - "_iscsymf_l"
  - "__iscsymf"
  - "ctype/iscsym"
  - "ctype/iscsymf"
  - "ctype/__iscsym"
  - "ctype/__iscsymf"
  - "ctype/__iscsym_l"
  - "ctype/__iscsymf_l"
  - "ctype/__iswcsym"
  - "ctype/__iswcsymf"
  - "ctype/__iswcsym_l"
  - "ctype/__iswcsymf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "iscsymf_l (fonction)"
  - "iswsym_l (fonction)"
  - "_iswcsym_l (fonction)"
  - "iscsym_l (fonction)"
  - "_iscsymf_l (fonction)"
  - "_iswcsymf_l (fonction)"
  - "_iscsym_l (fonction)"
  - "__iscsym (fonction)"
  - "__iswcsymf (fonction)"
  - "iswsymf_l (fonction)"
  - "__iscsymf (fonction)"
  - "__iswcsym (fonction)"
  - "iscsym (fonction)"
  - "iscsymf (fonction)"
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déterminer si un entier représente un caractère qui peut être utilisé dans un identificateur.  
  
## Syntaxe  
  
```  
int __iscsym(   
   int c   
);  
int __iswcsym(   
   wint_t c   
);  
int __iscsymf(   
   int c   
);  
int __iswcsymf(   
   wint_t c   
);  
int _iscsym_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsym_l(   
   wint_t c,  
   _locale_t locale  
);  
int _iscsymf_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsymf_l(   
   wint_t c,  
   _locale_t locale  
);  
#define iscsym __iscsym  
#define iscsymf __iscsymf  
```  
  
#### Paramètres  
 `c`  
 Entier à tester.`c` doit être dans la plage de 0 à 255 pour la version de caractères étroits de la fonction.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Les deux `__iscsym` et `__iswcsym` retournent une valeur différente de zéro si `c` est une lettre, un trait de soulignement ou un chiffre. Les deux `__iscsymf` et `__iswcsymf` retournent une valeur différente de zéro si `c` est une lettre ou un trait de soulignement. Chacune de ces routines retourne 0 si `c` ne répond pas à la condition de test. Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux. Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Notes  
 Ces routines sont définis en tant que macros, sauf si la macro de préprocesseur \_CTYPE\_DISABLE\_MACROS est défini. Lorsque vous utilisez les versions macro de ces routines, les arguments peuvent être évaluées plusieurs fois. Soyez prudent lorsque vous utilisez des expressions qui ont des effets secondaires dans la liste d’arguments.  
  
 Pour la compatibilité descendante, `iscsym` et `iscsymf` sont définis en tant que macros uniquement lorsque [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) n’est pas défini ou est défini sur 0 ; sinon, elles ne sont pas définis.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, `_iswcsymf_l`|C: \< ctype.h \><br /><br /> C\+\+ : \< cctype \> ou \< ctype.h \>|  
  
 Le `iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, et `_iswcsymf_l` routines sont spécifiques de Microsoft. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)