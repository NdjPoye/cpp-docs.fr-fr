---
title: "Fmax, fminf, fminl2 | Microsoft Docs"
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
  - "fmin"
  - "fminf"
  - "fminl"
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
  - "fmin"
  - "fminf"
  - "fminl"
  - "math/fmin"
  - "math/fminf"
  - "math/fminl"
helpviewer_keywords: 
  - "fmin (fonction)"
  - "fminf (fonction)"
  - "fminl (fonction)"
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Fmax, fminf, fminl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine la plus petite des deux valeurs spécifiées.  
  
## Syntaxe  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
  
```  
  
#### Paramètres  
 `x`  
 Première valeur à comparer.  
  
 `y`  
 Deuxième valeur à comparer.  
  
## Valeur de retour  
 En cas de réussite, retourne le plus petit de `x` ou `y`.  
  
|Entrée|Résultat|  
|------------|--------------|  
|`x` est une valeur NaN|`y`|  
|`y` est une valeur NaN|`x`|  
|`x` et `y` sont des valeurs NaN|NaN|  
  
 La fonction n’entraîne pas [\_matherr](../../c-runtime-library/reference/matherr.md) pour être appelé, provoquer des exceptions en virgule flottante, ou modifiez la valeur de `errno`.  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `fmin` qui acceptent et retournent des types float et doubles long. Dans un programme C, `fmin` toujours prend et retourne une valeur double.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`fmin`, `fminf`,  `fminl`|C: \< math.h \><br /><br /> C\+\+ : \< math.h \> ou \< cmath \>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)