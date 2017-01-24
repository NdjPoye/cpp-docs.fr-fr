---
title: "carg, cargf, cargl | Microsoft Docs"
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
  - "carg"
  - "cargf"
  - "cargl"
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
  - "carg"
  - "cargf"
  - "cargl"
  - "complex/carg"
  - "complex/cargf"
  - "complex/cargl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "carg (fonction)"
  - "cargf (fonction)"
  - "cargl (fonction)"
ms.assetid: 610d6a93-b929-46ab-a966-b77db0b804be
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# carg, cargf, cargl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère l’argument d’un nombre complexe, avec une branche coupe l’axe réel négatif.  
  
## Syntaxe  
  
```  
double carg(   
   _Dcomplex z   
);  
float carg(   
   _Fcomplex z   
);  // C++ only  
long double carg(   
   _Lcomplex z   
);  // C++ only  
float cargf(   
   _Fcomplex z   
);  
long double cargl(   
   _Lcomplex z   
);  
```  
  
#### Paramètres  
 `z`  
 Nombre complexe.  
  
## Valeur de retour  
 L’argument \(également appelé phase\) de `z`. Le résultat est dans l’intervalle \[−π \+ π\].  
  
## Notes  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `carg` acceptant `_Fcomplex` ou `_Lcomplex` valeurs et retourner `float` ou `long double` valeurs. Dans un programme C, `carg` a toujours un `_Dcomplex` valeur et retourne un `double` valeur.  
  
## Configuration requise  
  
|Routine|En\-tête C|En\-tête C\+\+|  
|-------------|----------------|--------------------|  
|`carg`, `cargf`, `cargl`|\<complex.h\>|\< ccomplex \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [Conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [fichiers CAB, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)