---
title: "iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iscntrl"
  - "_iswcntrl_l"
  - "_iscntrl_l"
  - "iswcntrl"
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
  - "_istcntrl_l"
  - "_iswcntrl_l"
  - "iswcntrl"
  - "_iscntrl_l"
  - "iscntrl"
  - "_istcntrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_iscntrl_l (fonction)"
  - "_istcntrl (fonction)"
  - "_istcntrl_l (fonction)"
  - "_iswcntrl_l (fonction)"
  - "iscntrl (fonction)"
  - "istcntrl (fonction)"
  - "iswcntrl (fonction)"
ms.assetid: 616eebf9-aed4-49ba-ba2c-8677c8fe6fb5
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un entier représente un caractère de contrôle.  
  
## Syntaxe  
  
```  
int iscntrl(   
   int c   
);  
int iswcntrl(   
   wint_t c   
);  
int _iscntrl_l(   
   int c,  
   _locale_t locale  
);  
int _iswcntrl_l(   
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
 Chacune de ces routines retourne une valeur différente de zéro si `c` est une représentation particulière d'un caractère de contrôle.  `iscntrl` retourne une valeur différente de zéro si `c` est un caractère de contrôle \(0x00 – 0x1F ou 0x7F\).  `iswcntrl` retourne une valeur différente de zéro si `c` est un caractère élargi de contrôle.  Chacune de ces routines retourne 0 si `c` ne remplit pas la condition de test.  
  
 Les versions de ces fonctions possédant le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Le comportement d'`iscntrl` et d'`_iscntrl_l` n'est pas défini si `c` n'a pas la valeur EOF ni n'est compris entre 0 et 0xFF, inclus.  Lorsqu'une bibliothèque CRT de débogage est utilisée et que `c` ne fait pas partie de ces valeurs, les fonctions déclenchent une assertion.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_istcntrl`|`iscntrl`|`iscntrl`|`iswcntrl`|  
|`_istcntrl_l`|`_iscntrl_l`|`_iscntrl_l`|`_iswcntrl_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`iscntrl`|\<ctype.h\>|  
|`iswcntrl`|\<ctype.h\> ou \<wchar.h\>|  
|`_iscntrl_l`|\<ctype.h\>|  
|`_iswcntrl_l`|\<ctype.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::Char::IsControl](https://msdn.microsoft.com/en-us/library/system.char.iscontrol.aspx)  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)