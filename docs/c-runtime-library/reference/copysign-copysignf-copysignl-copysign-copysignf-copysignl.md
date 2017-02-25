---
title: "copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "copysignf"
  - "copysignl"
  - "_copysignl"
  - "_copysign"
  - "_copysignf"
  - "copysign"
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
  - "_copysignl"
  - "copysign"
  - "copysignf"
  - "_copysign"
  - "copysignl"
  - "_copysignf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_copysign (fonction)"
  - "_copysignf (fonction)"
  - "_copysignl (fonction)"
  - "copysign (fonction)"
  - "copysignf (fonction)"
  - "copysignl (fonction)"
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Renvoie une valeur qui a l'importance d'un argument et le signe des autres.  
  
## Syntaxe  
  
```  
double copysign(   
   double x,  
   double y   
);  
float copysign(   
   float x,  
   float y   
); // C++ only  
long double copysign(   
   long double x,  
   long double y   
); // C++ only  
float copysignf(   
   float x,  
   float y   
); // C++ only  
long double copysignl(   
   long double x,  
   long double y   
); // C++ only  
double _copysign(   
   double x,  
   double y   
);  
long double _copysignl(   
   long double x,  
   long double y   
);  
```  
  
#### Paramètres  
 `x`  
 La valeur à virgule flottante qui est retournée comme importance du résultat.  
  
 `y`  
 La valeur à virgule flottante qui est retournée en tant que signe du résultat.  
  
 [Routines de support à virgule flottante](../../c-runtime-library/floating-point-support.md)  
  
## Valeur de retour  
 Les fonctions `copysign` retournent une valeur à virgule flottante qui combine l'importance du `x` et le signe du `y`.  Aucun retour d'erreur.  
  
## Notes  
 Comme C\+\+ permet la surcharge, vous pouvez appeler les surcharges de `copysign` qui acceptent et retournent les valeurs `float` ou `long double`.  Dans un programme C, `copysign` prend et retourne toujours `double`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_copysign`|\<float.h\>|  
|`copysign`, `copysignf`, `copysignl`, `_copysignf` `_copysignl`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [\_chgsign, \_chgsignf, \_chgsignl](../../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)