---
title: "nearbyint, nearbyintf, nearbyintl | Microsoft Docs"
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
  - "nearbyint"
  - "nearbyintf"
  - "nerabyintl"
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
  - "nearbyint"
  - "nearbyintf"
  - "nearbyintl"
  - "math/nearbyint"
  - "math/narbyintf"
  - "math/narbyintl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "nearbyint (fonction)"
  - "nearbyintf (fonction)"
  - "nearbyintl (fonction)"
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nearbyint, nearbyintf, nearbyintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Arrondit la valeur à virgule flottante spécifiée en un entier et retourne cette valeur dans un format à virgule flottante.  
  
## Syntaxe  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 Valeur à arrondir.  
  
## Valeur de retour  
 En cas de réussite, retourne `x`, arrondie à l’entier le plus proche, en utilisant le format d’arrondi actuel comme défini par fegetround. Sinon, la fonction peut retourner l’une des valeurs suivantes :  
  
|Problème|Retourner|  
|--------------|---------------|  
|`x` \= ±INFINITY|±Infinity, non modifié|  
|`x` \= ±0|±0, non modifié|  
|`x` \= NaN|NaN|  
  
 Les erreurs ne sont pas signalés via [\_matherr](../../c-runtime-library/reference/matherr.md); plus précisément, cette fonction ne signale pas les exceptions FE\_INEXACT.  
  
## Remarques  
 La principale différence entre cette fonction et `rint` est que cette fonction ne déclenche pas l’exception à virgule flottante inexact.  
  
 Étant donné que les valeurs à virgule flottante sont des entiers exactes, cette fonction sera jamais déborder par lui\-même. au lieu de cela, la sortie peut\-être dépasser la valeur de retour, selon la version de la fonction que vous utilisez.  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`nearbyint`, `nearbyintf`,  `nearbyintl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)