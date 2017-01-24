---
title: "fdim, fdimf, fdiml | Microsoft Docs"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
  - "math/fdim"
  - "math/fdimf"
  - "math/fdiml"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fdim (fonction)"
  - "fdimf (fonction)"
  - "fdiml (fonction)"
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fdim, fdimf, fdiml
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine la différence entre la première et deuxième valeur positive.  
  
## Syntaxe  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 Première valeur.  
  
 \[in\] `y`  
 Seconde valeur.  
  
## Valeur de retour  
 Retourne la différence positive entre `x` et `y`:  
  
|Valeur de retour|Scénario|  
|----------------------|--------------|  
|x\-y|Si x \> y|  
|0|Si x \< \= y|  
  
 Dans le cas contraire, peut retourner l’une des erreurs suivantes :  
  
|Problème|Retourner|  
|--------------|---------------|  
|Erreur de plage de dépassement de capacité|\+ HUGE\_VAL \+ HUGE\_VALF, ou \+ HUGE\_VALL|  
|Erreur de dépassement de plage|valeur correcte \(après arrondi\)|  
|`x` ou `y` est une valeur NaN|NaN|  
  
 Les erreurs sont signalées comme spécifié dans [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `fdim` qui acceptent et retournent des types float et doubles long. Dans un programme C, `fdim` toujours prend et retourne une valeur double.  
  
 À l’exception de la gestion des NaN, cette fonction est équivalente à [Fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)\(`x`\-`y,` 0\).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`fdim`, `fdimf`,  `fdiml`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [ABS, laboratoires, llabs, \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)