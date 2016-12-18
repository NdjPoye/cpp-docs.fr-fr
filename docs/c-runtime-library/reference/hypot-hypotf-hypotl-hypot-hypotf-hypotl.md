---
title: "hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_hypotf"
  - "hypot"
  - "hypotf"
  - "_hypot"
  - "_hypotl"
  - "hypotl"
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
  - "hypotf"
  - "hypotl"
  - "_hypotl"
  - "hypot"
  - "_hypot"
  - "_hypotf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_hypot (fonction)"
  - "calculer les hypoténuses"
  - "hypot (fonction)"
  - "calcul des hypoténuses"
  - "hypotf (fonction)"
  - "hypotl (fonction)"
  - "triangles, calculer l'hypoténuse"
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule l'hypoténuse.  
  
## Syntaxe  
  
```  
double hypot(   
   double x,  
   double y   
);  
float hypotf(   
   float x,  
   float y   
);  
long double hypotl(  
   long double x,  
   long double y  
);  
double _hypot(   
   double x,  
   double y   
);  
float _hypotf(   
   float x,  
   float y   
);  
long double _hypotl(  
   long double x,  
   long double y  
);  
```  
  
#### Paramètres  
 `x`, `y`  
 Valeurs à virgule flottante  
  
## Valeur de retour  
 En cas de réussite, `hypot` retourne la longueur de l'hypoténuse ; sur un dépassement de capacité, `hypot` retourne INF \(Infini\) et la variable `errno` a la valeur `ERANGE`.  Vous pouvez utiliser `_matherr` pour modifier la gestion des erreurs.  
  
 Pour plus d'informations sur les codes de retour, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Les fonctions `hypot` calculent la longueur de l'hypoténuse d'un triangle rectangle, selon la longueur des deux côtés `x` et `y` \(en d'autres termes, la racine carrée de <sup>2</sup>`x`\+ <sup>2</sup>`y`\).  
  
 Les versions des fonctions qui ont des traits de soulignement sont fournies pour la compatibilité avec les précédents standards.  Leur comportement est identique aux versions qui n'ont pas des traits de soulignement.  Nous recommandons d'utiliser les versions sans principaux traits de soulignement pour le nouveau code.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`hypot`, `hypotf`, `hypotl`, `_hypot`, `_hypotf`, `_hypotl`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_hypot.c  
// This program prints the hypotenuse of a right triangle.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 3.0, y = 4.0;  
  
   printf( "If a right triangle has sides %2.1f and %2.1f, "  
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );  
}  
```  
  
  **Si un triangle rectangle a ses côtés de longueur 3,0 et 4,0, son hypoténuse est 5,0**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_cabs](../../c-runtime-library/reference/cabs.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)