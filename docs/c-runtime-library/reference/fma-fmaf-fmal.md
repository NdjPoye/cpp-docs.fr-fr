---
title: "FMA, fmaf, fmal | Microsoft Docs"
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
  - "fma"
  - "fmaf"
  - "fmal"
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
  - "fma"
  - "fmaf"
  - "fmal"
  - "math/fma"
  - "math/fmaf"
  - "math/fmal"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fma (fonction)"
  - "fmaf (fonction)"
  - "fmal (fonction)"
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# FMA, fmaf, fmal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Multiplie deux valeurs ensemble, ajoute une troisième valeur, puis arrondit le résultat, sans perdre toute précision en raison d’arrondi intermédiaire.  
  
## Syntaxe  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 Première valeur à multiplier.  
  
 \[in\] `y`  
 Seconde valeur à multiplier.  
  
 \[in\] `z`  
 Valeur à ajouter.  
  
## Valeur de retour  
 Returns \(`x` ×    `y`\) \+ `z`. La valeur de retour est ensuite arrondie à l’aide du format d’arrondi actuel.  
  
 Dans le cas contraire, peut retourner l’une des valeurs suivantes :  
  
|Problème|Retourner|  
|--------------|---------------|  
|`x` \= L’infini, `y` \= 0 ou<br /><br /> `x` \= 0, `y` \= L’INFINI|NaN|  
|`x` ou `y` \= exact à ± infini, `z` \= infini avec le signe opposé|NaN|  
|`x` ou `y` \= NaN|NaN|  
|non \(`x` \= 0, `y`\= indéfinie\) et `z` \= NaN<br /><br /> non \(`x`\= indéfini `y`\= 0\) et `z` \= NaN|NaN|  
|Erreur de plage de dépassement de capacité|±HUGE\_VAL, ±HUGE\_VALF ou ±HUGE\_VALL|  
|Erreur de dépassement de plage|valeur correcte, après arrondi.|  
  
 Les erreurs sont signalées comme spécifié dans [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `fma` qui acceptent et retournent des types float et doubles long. Dans un programme C, `fma` toujours prend et retourne une valeur double.  
  
 Cette fonction calcule la valeur comme si elle a été effectuée avec une précision infinie et puis arrondit le résultat final.  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`fma`, `fmaf`,  `fmal`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)