---
title: "Concurrency::fast_math, espace de noms | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_math/Concurrency::fast_math"
dev_langs: 
  - "C++"
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency::fast_math, espace de noms
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Les fonctions de l'espace de noms `fast_math` ont une précision inférieure, acceptent uniquement une précision simple \(`float`\) et appellent les intrinsèques DirectX.  Il existe deux versions de chaque fonction, par exemple `cos` et `cosf`.  Les deux versions prennent et retournent un `float`, mais chacune appelle la même fonction intrinsèque DirectX.  
  
## Syntaxe  
  
```  
namespace fast_math;  
```  
  
## Membres  
  
### Fonctions  
  
|Nom|Description|  
|---------|-----------------|  
|[Fonction cos \(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|Calcule l'arc cosinus de l'argument|  
|[cosf, fonction \(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|Calcule l'arc cosinus de l'argument|  
|[asin, fonction \(fast\_math\)](../Topic/asin%20Function%20\(fast_math\).md)|Calcule l'arc sinus de l'argument|  
|[asinf, fonction \(fast\_math\)](../Topic/asinf%20Function%20\(fast_math\).md)|Calcule l'arc sinus de l'argument|  
|[atan, fonction \(fast\_math\)](../Topic/atan%20Function%20\(fast_math\).md)|Calcule l'arc tangente de l'argument|  
|[atan2, fonction \(fast\_math\)](../Topic/atan2%20Function%20\(fast_math\).md)|Calcule l'arc tangente de \_Y\/\_X|  
|[atan2f, fonction \(fast\_math\)](../Topic/atan2f%20Function%20\(fast_math\).md)|Calcule l'arc tangente de \_Y\/\_X|  
|[atanf, fonction \(fast\_math\)](../Topic/atanf%20Function%20\(fast_math\).md)|Calcule l'arc tangente de l'argument|  
|[ceil, fonction \(fast\_math\)](../Topic/ceil%20Function%20\(fast_math\).md)|Calcule la valeur entière supérieure de l'argument|  
|[ceilf, fonction \(fast\_math\)](../Topic/ceilf%20Function%20\(fast_math\).md)|Calcule la valeur entière supérieure de l'argument|  
|[Fonction cos \(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|Calcule le cosinus de l'argument|  
|[cosf, fonction \(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|Calcule le cosinus de l'argument|  
|[cosh, fonction \(fast\_math\)](../Topic/cosh%20Function%20\(fast_math\).md)|Calcule la valeur du cosinus hyperbolique de l'argument|  
|[coshf, fonction \(fast\_math\)](../Topic/coshf%20Function%20\(fast_math\).md)|Calcule la valeur du cosinus hyperbolique de l'argument|  
|[exp, fonction \(fast\_math\)](../Topic/exp%20Function%20\(fast_math\).md)|Calcule l'exponentielle en base e de l'argument|  
|[exp2, fonction \(fast\_math\)](../Topic/exp2%20Function%20\(fast_math\).md)|Calcule l'exponentiel en base 2 de l'argument|  
|[exp2f, fonction \(fast\_math\)](../Topic/exp2f%20Function%20\(fast_math\).md)|Calcule l'exponentiel en base 2 de l'argument|  
|[expf, fonction \(fast\_math\)](../Topic/expf%20Function%20\(fast_math\).md)|Calcule l'exponentielle en base e de l'argument|  
|[fabs, fonction \(fast\_math\)](../Topic/fabs%20Function%20\(fast_math\).md)|Retourne la valeur absolue de l'argument|  
|[fabsf, fonction \(fast\_math\)](../Topic/fabsf%20Function%20\(fast_math\).md)|Retourne la valeur absolue de l'argument|  
|[floor, fonction \(fast\_math\)](../Topic/floor%20Function%20\(fast_math\).md)|Calcule la valeur plancher de l'argument.|  
|[floorf, fonction \(fast\_math\)](../Topic/floorf%20Function%20\(fast_math\).md)|Calcule la valeur plancher de l'argument.|  
|[fmax, fonction \(fast\_math\)](../Topic/fmax%20Function%20\(fast_math\).md)|Détermine la valeur numérique maximale des arguments|  
|[fmaxf, fonction \(fast\_math\)](../Topic/fmaxf%20Function%20\(fast_math\).md)|Détermine la valeur numérique maximale des arguments|  
|[fmin, fonction \(fast\_math\)](../Topic/fmin%20Function%20\(fast_math\).md)|Détermine la valeur numérique minimale des arguments|  
|[fminf, fonction \(fast\_math\)](../Topic/fminf%20Function%20\(fast_math\).md)|Détermine la valeur numérique minimale des arguments|  
|[fmod, fonction \(fast\_math\)](../Topic/fmod%20Function%20\(fast_math\).md)|Calcule le reste en virgule flottante de \_X\/\_Y.|  
|[fmodf, fonction \(fast\_math\)](../Topic/fmodf%20Function%20\(fast_math\).md)|Calcule le reste en virgule flottante de \_X\/\_Y.|  
|[frexp, fonction \(fast\_math\)](../Topic/frexp%20Function%20\(fast_math\).md)|Obtient la mantisse et l'exposant de \_X|  
|[frexpf, fonction \(fast\_math\)](../Topic/frexpf%20Function%20\(fast_math\).md)|Obtient la mantisse et l'exposant de \_X|  
|[isfinite, fonction \(fast\_math\)](../Topic/isfinite%20Function%20\(fast_math\).md)|Détermine si l'argument a une valeur finie|  
|[isinf, fonction \(fast\_math\)](../Topic/isinf%20Function%20\(fast_math\).md)|Détermine si l'argument est un infini|  
|[isnan, fonction \(fast\_math\)](../Topic/isnan%20Function%20\(fast_math\).md)|Détermine si l'argument est un NaN|  
|[ldexp, fonction \(fast\_math\)](../Topic/ldexp%20Function%20\(fast_math\).md)|Calcule un nombre réel à partir de la mantisse et de l'exposant.|  
|[ldexpf, fonction \(fast\_math\)](../Topic/ldexpf%20Function%20\(fast_math\).md)|Calcule un nombre réel à partir de la mantisse et de l'exposant.|  
|[log, fonction \(fast\_math\)](../Topic/log%20Function%20\(fast_math\).md)|Calcule le logarithme en base e de l'argument|  
|[log10, fonction \(fast\_math\)](../Topic/log10%20Function%20\(fast_math\).md)|Calcule le logarithme en base 10 de l'argument|  
|[log10f, fonction \(fast\_math\)](../Topic/log10f%20Function%20\(fast_math\).md)|Calcule le logarithme en base 10 de l'argument|  
|[log2, fonction \(fast\_math\)](../Topic/log2%20Function%20\(fast_math\).md)|Calcule le logarithme en base 2 de l'argument|  
|[log2f, fonction \(fast\_math\)](../Topic/log2f%20Function%20\(fast_math\).md)|Calcule le logarithme en base 2 de l'argument|  
|[logf, fonction \(fast\_math\)](../Topic/logf%20Function%20\(fast_math\).md)|Calcule le logarithme en base e de l'argument|  
|[modf, fonction \(fast\_math\)](../Topic/modf%20Function%20\(fast_math\).md)|Fractionne \_X en une partie fractionnaire et une partie entière.|  
|[modff, fonction \(fast\_math\)](../Topic/modff%20Function%20\(fast_math\).md)|Fractionne \_X en une partie fractionnaire et une partie entière.|  
|[pow, fonction \(fast\_math\)](../Topic/pow%20Function%20\(fast_math\).md)|Calcule \_X élevé à la puissance \_Y|  
|[powf, fonction \(fast\_math\)](../Topic/powf%20Function%20\(fast_math\).md)|Calcule \_X élevé à la puissance \_Y|  
|[round, fonction \(fast\_math\)](../Topic/round%20Function%20\(fast_math\).md)|Arrondit \_X à l'entier le plus proche|  
|[roundf, fonction \(fast\_math\)](../Topic/roundf%20Function%20\(fast_math\).md)|Arrondit \_X à l'entier le plus proche|  
|[rsqrt, fonction \(fast\_math\)](../Topic/rsqrt%20Function%20\(fast_math\).md)|Retourne la réciproque de la racine carrée de l'argument|  
|[rsqrtf, fonction \(fast\_math\)](../Topic/rsqrtf%20Function%20\(fast_math\).md)|Retourne la réciproque de la racine carrée de l'argument|  
|[signbit, fonction \(fast\_math\)](../Topic/signbit%20Function%20\(fast_math\).md)|Retourne le signe de l'argument|  
|[signbitf, fonction \(fast\_math\)](../Topic/signbitf%20Function%20\(fast_math\).md)|Retourne le signe de l'argument|  
|[sin, fonction \(fast\_math\)](../Topic/sin%20Function%20\(fast_math\).md)|Calcule la valeur du sinus de l'argument|  
|[sincos, fonction \(fast\_math\)](../Topic/sincos%20Function%20\(fast_math\).md)|Calcule la valeur du sinus et du cosinus de \_X|  
|[sincosf, fonction \(fast\_math\)](../Topic/sincosf%20Function%20\(fast_math\).md)|Calcule la valeur du sinus et du cosinus de \_X|  
|[sinf, fonction \(fast\_math\)](../Topic/sinf%20Function%20\(fast_math\).md)|Calcule la valeur du sinus de l'argument|  
|[sinh, fonction \(fast\_math\)](../Topic/sinh%20Function%20\(fast_math\).md)|Calcule la valeur du sinus hyperbolique de l'argument|  
|[sinhf, fonction \(fast\_math\)](../Topic/sinhf%20Function%20\(fast_math\).md)|Calcule la valeur du sinus hyperbolique de l'argument|  
|[sqrt, fonction \(fast\_math\)](../Topic/sqrt%20Function%20\(fast_math\).md)|Calcule la racine carrée de l'argument|  
|[sqrtf, fonction \(fast\_math\)](../Topic/sqrtf%20Function%20\(fast_math\).md)|Calcule la racine carrée de l'argument|  
|[tan, fonction \(fast\_math\)](../Topic/tan%20Function%20\(fast_math\).md)|Calcule la valeur de la tangente de l'argument|  
|[tanf, fonction \(fast\_math\)](../Topic/tanf%20Function%20\(fast_math\).md)|Calcule la valeur de la tangente de l'argument|  
|[tanh, fonction \(fast\_math\)](../Topic/tanh%20Function%20\(fast_math\).md)|Calcule la valeur de la tangente hyperbolique de l'argument|  
|[tanhf, fonction \(fast\_math\)](../Topic/tanhf%20Function%20\(fast_math\).md)|Calcule la valeur de la tangente hyperbolique de l'argument|  
|[trunc, fonction \(fast\_math\)](../Topic/trunc%20Function%20\(fast_math\).md)|Tronque l'argument en composant entier|  
|[truncf, fonction \(fast\_math\)](../Topic/truncf%20Function%20\(fast_math\).md)|Tronque l'argument en composant entier|  
  
## Configuration requise  
 **En\-tête :** amp\_math.h  
  
 **Espace de noms :** Concurrency::fast\_math  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)