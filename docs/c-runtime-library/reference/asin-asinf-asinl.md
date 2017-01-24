---
title: "asin, asinf, asinl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "asinf"
  - "asinl"
  - "asin"
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
  - "asin"
  - "asinl"
  - "asinf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "arcsine (fonction)"
  - "asin (fonction)"
  - "asinf (fonction)"
  - "asinl (fonction)"
  - "fonctions trigonométriques"
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# asin, asinf, asinl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule l'arcsinus.  
  
## Syntaxe  
  
```  
double asin(   
   double x   
);  
float asin(  
   float x  
);  // C++ only  
long double asin(  
   long double x  
);  // C++ only  
float asinf (   
   float x   
);  
long double asinl(  
   long double x  
);  
```  
  
#### Paramètres  
 `x`  
 La valeur dont l'arcsinus doit être calculé.  
  
## Valeur de retour  
 La fonction `asin` retourne l'arcsinus \(la fonction inverse du sinus\) de `x` dans la plage –π\/2 à –π\/2 radians.  
  
 Par défaut, si `x` est inférieur à \-1, ou supérieur à 1 `asin` retourne un indéfini.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± `QNAN`,`IND`|aucun|`_DOMAIN`|  
|&#124;x&#124;\>1|`INVALID`|`_DOMAIN`|  
  
## Notes  
 Puisque C\+\+ permet la surcharge, vous pouvez appeler des surcharges de `asin` avec les valeurs `float` et `long double`.  Dans un programme C, `asin` prend en argument et retourne toujours un double.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`asin`, `asinf`, `asinl`|\<math.h\>|  
  
## Exemple  
 Pour plus d'informations, consultez [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md).  
  
## Équivalent .NET Framework  
 [System::Math::Asin](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)