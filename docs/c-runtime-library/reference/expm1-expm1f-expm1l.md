---
title: "expm1, expm1f, expm1l | Microsoft Docs"
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
  - "expm1l"
  - "expm1"
  - "expm1f"
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
  - "expm1l"
  - "expm1"
  - "expm1f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expm1 (fonction)"
  - "expm1f (fonction)"
  - "expm1l (fonction)"
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# expm1, expm1f, expm1l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule l'exponentiel e de base d'une valeur, moins un.  
  
## Syntaxe  
  
```  
double expm1(   
   double x   
);  
float expm1(  
   float x  
);  // C++ only  
long double expm1(  
   long double x  
);  // C++ only  
float expm1f(  
   float x  
);  
long double expm1l(  
   long double x  
);  
```  
  
#### Paramètres  
 `x`  
 Valeur exponentielle à virgule flottante.  
  
## Valeur de retour  
 Les fonctions `expm1` retournent une valeur à virgule flottante qui représente e<sup>x</sup> – 1, en cas de succès.  En cas de dépassement de capacité, `expm1` retourne `HUGE_VAL`, `expm1f` retourne `HUGE_VALF`, `expm1l` retourne `HUGE_VALL` et `errno` est défini sur `ERANGE` Pour plus d'informations sur les codes de retour, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Comme C\+\+ permet la surcharge, vous pouvez appeler les surcharges de `expm1` qui acceptent et retournent les valeurs `float` et `long double`.  Dans un programme C, `expm1` prend et retourne toujours `double`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`expm1`, `expm1f`, `expm1l`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [exp2, exp2f, exp2l](http://msdn.microsoft.com/fr-fr/a7974629-be1e-4196-a562-6624a0732003)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)