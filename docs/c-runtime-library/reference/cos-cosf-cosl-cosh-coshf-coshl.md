---
title: "cos, cosf, cosl, cosh, coshf, coshl | Microsoft Docs"
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
  - "coshl"
  - "cosh"
  - "cos"
  - "cosl"
  - "cosf"
  - "coshf"
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
  - "coshl"
  - "cos"
  - "cosf"
  - "cosh"
  - "cosl"
  - "coshf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "calculer le cosinus"
  - "cos (fonction)"
  - "cosf (fonction)"
  - "cosh (fonction)"
  - "coshf (fonction)"
  - "coshl (fonction)"
  - "cosinus"
  - "cosinus, calculer"
  - "cosl (fonction)"
  - "fonctions hyperboliques"
  - "fonctions trigonométriques"
ms.assetid: ae90435e-6b68-4a47-a81f-be87d5c08f16
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# cos, cosf, cosl, cosh, coshf, coshl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule le cosinus \(`cos`, `cosf`, ou `cosl`\), ou le cosinus hyperbolique \(`cosh`, `coshf`, ou `coshl`\).  
  
## Syntaxe  
  
```  
double cos(   
   double x   
);  
float cos(  
   float x   
);  // C++ only  
long double cos(  
   long double x  
);  // C++ only  
float cosf(   
   float x   
);  
long double cosl(  
   long double x  
);  
double cosh(   
   double x   
);  
float cosh(  
   float x   
);  // C++ only  
long double cosh(  
   long double x  
);  // C++ only  
float coshf(  
   float x   
);  
long double coshl(  
   long double x  
);  
```  
  
#### Paramètres  
 `x`  
 Angle en radians.  
  
## Valeur de retour  
 Cosinus ou cosinus hyperbolique de `x`.  Si `x` est supérieur ou égale à 263, ou inférieur ou égale à – 263, une perte d'importance dans le résultat d'un appel à `cos`, `cosf`, ou `cosl` se produit.  
  
 Par défaut, si le résultat est trop important dans un `cosh`, `coshf`, ou un appel de `coshl`, la fonction retourne `HUGE_VAL` et affecte `errno` à la valeur `ERANGE`.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± `QNAN`,`IND`|aucun|`_DOMAIN`|  
|± ∞  \(`cosf`, `cos`, `cosl`\)|`INVALID`|`_DOMAIN`|  
|X ≥ 7,104760e\+002 \(`cosh`, `coshf`, `coshl`\)|`INEXACT`\+`OVERFLOW`|`OVERFLOW`|  
  
## Notes  
 Comme C\+\+ permet la surcharge, il est possible d'appeler les surcharges de `cos` et `cosh` qui acceptent et renvoient les valeurs `float` ou `long double` .  Dans un programme C, `cos` et `cosh` prennent et retournent toujours `double`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`cos`, `cosh`, `cosf`, `coshf`, `cosl`, `coshl`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple dans [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md).  
  
## Équivalent .NET Framework  
  
-   [System::Math::Cos](https://msdn.microsoft.com/en-us/library/system.math.cos.aspx)  
  
-   [System::Math::Cosh](https://msdn.microsoft.com/en-us/library/system.math.cosh.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CIcos](../../c-runtime-library/cicos.md)