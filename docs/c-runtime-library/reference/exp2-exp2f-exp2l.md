---
title: "exp2, exp2f, exp2l | Microsoft Docs"
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
  - "exp2"
  - "exp2f"
  - "exp2l"
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
  - "exp2"
  - "math/exp2"
  - "exp2f"
  - "math/exp2f"
  - "exp2l"
  - "math/exp2l"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "exp2 (fonction)"
  - "exp2f (fonction)"
  - "exp2l (fonction)"
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exp2, exp2f, exp2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule 2 élevé à la valeur spécifiée \(c'est\-à\-dire 2ˣ\).  
  
## Syntaxe  
  
```  
double exp2(  
   double x  
);  
  
float exp2(  
   float x  
);  // C++ only  
  
long double exp2(  
   long double x  
); // C++ only  
  
float exp2f(  
   float x  
);  
  
long double exp2l(  
   long double x  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 La valeur de l’exposant.  
  
## Valeur de retour  
 En cas de réussite, retourne l’exposant de base 2 de `x` \(2ˣ\). Dans le cas contraire, peut retourner l’une des valeurs suivantes :  
  
|Problème|Retourner|  
|--------------|---------------|  
|`x` \= ±0|1|  
|`x` \= \- INFINITY|\+0|  
|`x` \= \+ INFINITY|\+ INFINI|  
|`x` \= NaN|NaN|  
|Erreur de plage de dépassement de capacité|\+ HUGE\_VAL \+ HUGE\_VALF, ou \+ HUGE\_VALL|  
|Erreur de dépassement de plage|résultat correct, après arrondi|  
  
 Les erreurs sont signalées comme spécifié dans [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `exp2` qui acceptent et retournent des types float et doubles long. Dans un programme C, `exp2` toujours prend et retourne une valeur double.  
  
## Configuration requise  
  
|Routine|En\-tête C|En\-tête C\+\+|  
|-------------|----------------|--------------------|  
|`exp`, `expf`, `expl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [LOG2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)