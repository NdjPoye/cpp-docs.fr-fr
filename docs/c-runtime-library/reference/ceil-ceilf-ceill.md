---
title: "ceil, ceilf, ceill | Microsoft Docs"
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
  - "ceilf"
  - "ceil"
  - "ceill"
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
  - "ceil"
  - "ceilf"
  - "ceill"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "calculer les plafonds des valeurs"
  - "ceil (fonction)"
  - "ceilf (fonction)"
  - "ceill (fonction)"
ms.assetid: f4e5acab-5c8f-4b10-9ae2-9561e6453718
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ceil, ceilf, ceill
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule l'entier suivant la partie entière d'une valeur.  
  
## Syntaxe  
  
```  
double ceil(   
   double x   
);  
float ceil(  
   float x  
);  // C++ only  
long double ceil(  
   long double x  
);  // C++ only  
float ceilf(  
   float x  
);  
long double ceill(  
   long double x  
);  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante.  
  
## Valeur de retour  
 Les fonctions `ceil` retournent une valeur à virgule flottante qui représente le plus petit entier supérieur ou égal à `x`.  Aucun retour d'erreur.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± `QNAN`,`IND`|aucun|`_DOMAIN`|  
  
 `ceil` a une implémentation qui utilise les extensions Streaming SIMD 2 \(SSE2\).  Pour plus d'informations et de restrictions sur l'utilisation de l'implémentation SSE2, consultez [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
## Notes  
 Comme C\+\+ permet une surcharge, vous pouvez appeler des surcharges de `ceil`.  Dans un programme C, `ceil` prend et retourne toujours un double .  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`ceil`, `ceilf`, `ceill`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple de [floor](../../c-runtime-library/reference/floor-floorf-floorl.md).  
  
## Équivalent .NET Framework  
 [System::Math::Ceiling](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)