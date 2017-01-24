---
title: "erf, erff, erfl, erfc, erfcf, erfcl | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "erff"
  - "erfl"
  - "erf"
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
  - "erfl"
  - "erf"
  - "erff"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erf (fonction)"
  - "erff (fonction)"
  - "erfl (fonction)"
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# erf, erff, erfl, erfc, erfcf, erfcl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule la fonction d'erreur ou la fonction d'erreur complémentaire d'une valeur.  
  
## Syntaxe  
  
```  
double erf(    double x ); float erf(    float x ); // C++ only long double erf(    long double x ); // C++ only float erff(    float x ); long double erfl(    long double x ); double erfc(    double x ); float erfc(    float x ); // C++ only long double erfc(    long double x ); // C++ only float erfcf(    float x ); long double erfcl(    long double x );  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
## Valeur de retour  
 La fonction `erf` retourne la fonction d'erreur de Gauss de `x`.  La fonction `erfc` retourne la fonction d'erreur de Gauss complémentaire de `x`.  
  
## Notes  
 La fonction `erf` calcule la fonction d'erreur de Gauss de x, qui est définie comme suit :  
  
 ![Fonction d'erreur de x](../../c-runtime-library/reference/media/crt_erf_formula.png "CRT\_erf\_formula")  
  
 La fonction d'erreur de Gauss complémentaire est définie comme ceci : 1 – erf\(x\).  La fonction `erf` retourne une valeur comprise dans la plage \-1,0 à 1,0.  Aucun retour d'erreur.  La fonction `erfc` retourne une valeur comprise dans la plage 0 à 2.  Si `x` est trop grand pour `erfc`, la variable `errno` prend la valeur `ERANGE`.  
  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `erf` et `erfc` qui acceptent et retournent les types `float` et `long double`.  Dans un programme C, `erf` et `erfc` acceptent et retournent toujours un `double`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`erf`, `erff`, `erfl`, `erfc`, `erfcf`, `erfcl`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, voir [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)