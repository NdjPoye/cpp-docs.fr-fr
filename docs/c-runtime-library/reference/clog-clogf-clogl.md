---
title: "CLOG, clogf, clogl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clog"
  - "clogf"
  - "clogl"
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
  - "clog"
  - "clogf"
  - "clogl"
  - "complex/clog"
  - "complex/clogf"
  - "complex/clogl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "clog (fonction)"
  - "clogf (fonction)"
  - "clogl (fonction)"
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CLOG, clogf, clogl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère le logarithme népérien d’un nombre complexe, avec une branche coupe l’axe réel négatif.  
  
## Syntaxe  
  
```  
_Dcomplex clog(   
   _Dcomplex z   
);  
_Fcomplex clog(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex clog(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex clogf(   
   _Fcomplex z   
);  
_Lcomplex clogl(   
   _Lcomplex z   
);  
```  
  
#### Paramètres  
 `z`  
 Base du logarithme.  
  
## Valeur de retour  
 Le logarithme népérien de `z`. Le résultat est illimité sur l’axe réel et dans l’intervalle \[−iπ \+ iπ\] sur l’axe imaginaire.  
  
 Les valeurs de retournés possibles sont :  
  
|paramètre z|Valeur de retour|  
|-----------------|----------------------|  
|Positif|Logarithme de base 10 de z|  
|Zéro|\- ∞|  
|Négatif|NaN|  
|NaN|NaN|  
|\+ ∞|\+ ∞|  
  
## Notes  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `clog` qui acceptent et retournent des valeurs `_Fcomplex` et `_Lcomplex`. Dans un programme C, `clog` accepte et retourne toujours un `_Dcomplex` valeur.  
  
## Configuration requise  
  
|Routine|En\-tête C|En\-tête C\+\+|  
|-------------|----------------|--------------------|  
|`clog`, `clogf`, `clogl`|\<complex.h\>|\< ccomplex \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp, cexpf, cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [cpow, cpowf, cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [clog10, clog10f, clog10l](../../c-runtime-library/reference/clog10-clog10f-clog10l.md)