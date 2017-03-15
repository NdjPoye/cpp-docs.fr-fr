---
title: "cexp, cexpf, cexpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "cexp"
  - "cexpf"
  - "cexpl"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "cexp"
  - "cexpf"
  - "cexpl"
  - "complex/cepx"
  - "complex/cexpf"
  - "complex/cexpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cexp (fonction)"
  - "cexpl (fonction)"
  - "cexpf (fonction)"
ms.assetid: f27fd5a9-70c7-4957-a7ee-5256d19bd1da
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# cexp, cexpf, cexpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule la valeur exponentielle de base e d’un nombre complexe.  
  
## Syntaxe  
  
```  
_Dcomplex cexp(   
   _Dcomplex z   
);  
_Fcomplex cexp(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex cexp(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex cexpf(   
  _Fcomplex z   
);  
_Lcomplex cexpl(   
   _Lcomplex z   
);  
```  
  
#### Paramètres  
 `z`  
 Nombre complexe qui représente l’exposant.  
  
## Valeur de retour  
 Valeur de `e` élevée à la puissance de `z`.  
  
## Notes  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `cexp` qui acceptent et retournent des valeurs `_Fcomplex` et `_Lcomplex`. Dans un programme C, `cexp` accepte et retourne toujours une valeur `_Dcomplex`.  
  
## Configuration requise  
  
|Routine|En\-tête C|En\-tête C\+\+|  
|-------------|----------------|--------------------|  
|`cexp`, `cexpf`, `cexpl`|\<complex.h\>|\<complex.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cpow, cpowf, cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [clog10, clog10f, clog10l](../../c-runtime-library/reference/clog10-clog10f-clog10l.md)   
 [CLOG, clogf, clogl](../../c-runtime-library/reference/clog-clogf-clogl.md)