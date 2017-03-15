---
title: "nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft Docs"
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
  - "nextafterf"
  - "_nextafterf"
  - "nextafter"
  - "nextafterl"
  - "_nextafter"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
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
  - "nextafter"
  - "_nextafter"
  - "nextafterf"
  - "nextafterl"
  - "_nextafterf"
  - "math/nextafter"
  - "math/nextafterf"
  - "math/nextafterl"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
  - "math/nexttoward"
  - "math/nexttowardf"
  - "math/nexttowardl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_nextafter (fonction)"
  - "nextafter (fonction)"
  - "_nextafterf (fonction)"
  - "nextafterf (fonction)"
  - "nextafterl (fonction)"
  - "nexttoward (fonction)"
  - "nexttowardf (fonction)"
  - "nexttowardl (fonction)"
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne la valeur représentable à virgule flottante.  
  
## Syntaxe  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante à démarrer à partir de.  
  
 `y`  
 Valeur à virgule flottante accèdent.  
  
## Valeur de retour  
 Retourne la valeur à virgule flottante représentable du type de retour après `x` dans la direction de `y`. Si `x`\=`y`, la fonction retourne `y`, il est converti en type de retour, aucune exception déclenchée. Si `x` n’est pas égal à `y`, le résultat est un denormal ou égal à zéro, les États d’exception de virgule flottante FE\_UNDERFLOW et FE\_INEXACT sont définies et le résultat correct est renvoyé. Si le paramètre `x` ou `y` est une valeur NAN, la valeur de retour est parmi les valeurs NaN d’entrée. Si `x` est fixe et le résultat est l’infini ou n’est pas représentable dans le type, un infini correctement signé ou les NAN est retournée, les États d’exception de virgule flottante FE\_OVERFLOW et FE\_INEXACT sont définis, et `errno` a la valeur ERANGE.  
  
## Notes  
 Le `nextafter` et `nexttoward` familles de fonction sont équivalents, à l’exception du type de paramètre `y`. Si `x` et `y` sont égaux, la valeur retournée est `y` converti au type de retour.  
  
 C\+\+ autorisant la surcharge, si vous incluez \< cmath \> vous pouvez appeler des surcharges de `nextafter` et `nexttoward` qui retournent `float` et `long double` types. Dans un programme C, `nextafter` et `nexttoward` retournent toujours `double`.  
  
 Le `_nextafter` et `_nextafterf` les fonctions sont spécifiques de Microsoft. Le `_nextafterf` fonction est disponible uniquement lors de la compilation pour x64.  
  
## Configuration requise  
  
|Routine|En\-tête requis \(C\)|En\-tête requis \(C\+\+\)|  
|-------------|---------------------------|-------------------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h\>|\<math.h\> ou \<cmath\>|  
|`_nextafter`|\<float.h\>|\< float.h \> ou \< cfloat \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [isNaN, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)