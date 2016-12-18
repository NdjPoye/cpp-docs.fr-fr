---
title: "trunc, truncf, truncl | Microsoft Docs"
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
  - "trunc"
  - "truncf"
  - "truncl"
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
  - "trunc"
  - "truncf"
  - "truncl"
  - "math/trunc"
  - "math/truncf"
  - "math/truncl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "trunc (fonction)"
  - "truncf (fonction)"
  - "truncl (fonction)"
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# trunc, truncf, truncl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine l’entier le plus proche qui est inférieure ou égale à la valeur à virgule flottante spécifiée.  
  
## Syntaxe  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 Valeur à tronquer.  
  
## Valeur de retour  
 En cas de réussite, retourne une valeur entière de `x`, il est arrondi vers zéro.  
  
 Dans le cas contraire, peut retourner l’une des opérations suivantes :  
  
|Problème|Retourner|  
|--------------|---------------|  
|`x` \= ±INFINITY|x|  
|`x` \=  ±0|x|  
|`x` \= NaN|NaN|  
  
 Les erreurs sont signalées comme spécifié dans [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `trunc` qui acceptent et retournent des types float et doubles long. Dans un programme C, `trunc` toujours prend et retourne une valeur double.  
  
 Étant donné que les plus grandes valeurs à virgule flottante sont des entiers exactes, cette fonction ne sera pas déborder sur son propre. Toutefois, vous vous exposez à la fonction de dépassement de capacité en retournant une valeur en un type entier.  
  
 Vous pouvez aussi arrondir en convertissant implicitement à partir de virgule flottante à intégral ; Toutefois, cette opération est donc limitée aux valeurs qui peuvent être stockées dans le type cible.  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`trunc`, `truncf`,  `truncl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)