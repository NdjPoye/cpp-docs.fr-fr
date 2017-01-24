---
title: "Fmax, fmaxf, fmaxl | Microsoft Docs"
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
  - "fmax"
  - "fmaxf"
  - "fmaxl"
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
  - "fmax"
  - "fmaxf"
  - "fmaxl"
  - "math/fmax"
  - "math/fmaxf"
  - "math/fmaxl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fmax (fonction)"
  - "fmaxf (fonction)"
  - "fmaxl (fonction)"
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fmax, fmaxf, fmaxl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déterminer la plus grande des deux valeurs numériques spécifiées.  
  
## Syntaxe  
  
```  
double fmax(  
   double x,   
   double y  
);  
  
float fmax(  
   float x,   
   float y  
); //C++ only  
  
long double fmax(  
   long double x,   
   long double y  
); //C++ only  
  
float fmaxf(  
   float x,   
   float y  
);  
  
long double fmaxl(  
   long double x,   
   long double y  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 Première valeur à comparer.  
  
 \[in\] `y`  
 Deuxième valeur à comparer.  
  
## Valeur de retour  
 En cas de réussite, retourne le plus grand de `x` ou `y`. La valeur retournée est exacte et ne dépend pas de n’importe quel écran de l’arrondi.  
  
 Dans le cas contraire, peut retourner l’une des valeurs suivantes :  
  
|Problème|Retourner|  
|--------------|---------------|  
|`x` \= NaN|`y`|  
|`y` \= NaN|`x`|  
|`x` et `y` \= NaN|NaN|  
  
 Cette fonction n’utilise pas les erreurs spécifiés dans  [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de fmax qui acceptent et retournent des types float et doubles long. Dans un programme C, fmax toujours prend et retourne une valeur double.  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`fmax`, `fmaxf`, `fmaxl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmin, fminf, fminl](../Topic/fmin,%20fminf,%20fminl1.md)