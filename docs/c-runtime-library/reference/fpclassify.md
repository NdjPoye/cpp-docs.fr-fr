---
title: "fpclassify | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fpclassify"
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
apitype: "HeaderDef"
f1_keywords: 
  - "fpclassify"
  - "math/fpclassify"
helpviewer_keywords: 
  - "fpclassify macro"
  - "fpclassify (fonction)"
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# fpclassify
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne la classification de l’argument à virgule flottante.  
  
## Syntaxe  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante à tester.  
  
## Valeur de retour  
 `fpclassify` Retourne une valeur entière qui indique la classe de l’argument à virgule flottante `x`. Ce tableau montre les valeurs possibles retournées par `fpclassify`, défini dans \< math.h \>.  
  
|Valeur|Description|  
|------------|-----------------|  
|`FP_NAN`|Un mode silencieux, signalisation ou NaN indéterminé|  
|`FP_INFINITE`|Une infinité positive ou négative|  
|`FP_NORMAL`|Une valeur différente de zéro positive ou négative normalisée|  
|`FP_SUBNORMAL`|Valeur positive ou négative dénormalisée|  
|`FP_ZERO`|Positif ou négatif de la valeur zéro|  
  
## Notes  
 En C, `fpclassify` est une macro ; en C\+\+, `fpclassify` est une fonction surchargée à l’aide des types d’arguments de `float`, `double`, ou `long double`. Dans les deux cas, la valeur retournée dépend du type de l’expression d’argument efficace et non sur toute représentation intermédiaire. Par exemple, un normal `double` ou `long double` valeur peut devenir un infini, denormal ou zéro valeur lorsque converti en un `float`.  
  
## Configuration requise  
  
|Fonction \/ \(macro\)|En\-tête requis \(C\)|En\-tête requis \(C\+\+\)|  
|---------------------------|---------------------------|-------------------------------|  
|`fpclassify`|\<math.h\>|\<math.h\> ou \<cmath\>|  
  
 Le `fpclassify` macro et `fpclassify` fonctions conformes à la norme C99 et C \+\+ 11 spécifications. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [isNaN, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)