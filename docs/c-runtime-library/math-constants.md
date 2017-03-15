---
title: "Math, constantes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.constants"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_USE_MATH_DEFINES (constante)"
  - "constantes, math"
  - "M_1_PI (constante)"
  - "M_2_PI (constante)"
  - "M_2_SQRTPI (constante)"
  - "M_E (constante)"
  - "M_LN10 (constante)"
  - "M_LN2 (constante)"
  - "M_LOG10E (constante)"
  - "M_LOG2E (constante)"
  - "M_PI (constante)"
  - "M_PI_2 (constante)"
  - "M_PI_4 (constante)"
  - "M_SQRT1_2 (constante)"
  - "M_SQRT2 (constante)"
  - "math (constantes)"
  - "USE_MATH_DEFINES (constante)"
ms.assetid: db533c3f-6ae8-4520-9d35-c8fabbef3529
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Math, constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
#define _USE_MATH_DEFINES // for C++  
#include <cmath>  
  
#define _USE_MATH_DEFINES // for C  
#include <math.h>  
```  
  
## Notes  
 Les symboles suivants sont définis pour les valeurs de leurs expressions indiquées:  
  
|Symbole|Expression|Valeur|  
|-------------|----------------|------------|  
|M\_E|e|2.71828182845904523536|  
|M\_LOG2E|log2\(e\)|1.44269504088896340736|  
|M\_LOG10E|log10\(e\)|0.434294481903251827651|  
|M\_LN2|ln\(2\)|0.693147180559945309417|  
|M\_LN10|ln\(10\)|2.30258509299404568402|  
|M\_PI|PI|3.14159265358979323846|  
|M\_PI\_2|pi\/2|1.57079632679489661923|  
|M\_PI\_4|pi\/4|0.785398163397448309616|  
|M\_1\_PI|1\/pi|0.318309886183790671538|  
|M\_2\_PI|2\/pi|0.636619772367581343076|  
|M\_2\_SQRTPI|2\/sqrt \(pi\)|1.12837916709551257390|  
|M\_SQRT2|sqrt\(2\)|1.41421356237309504880|  
|M\_SQRT1\_2|1\/sqrt\(2\)|0.707106781186547524401|  
  
 Les constantes de mathématique ne sont pas définies dans la norme C\/C\+\+.  Pour les utiliser, vous devez d'abord définir `_USE_MATH_DEFINES` puis inclure cmath ou math.h.  
  
 Le fichier ATLComTime.h inclut math.h lorsque votre projet est généré en mode Release.  Si vous utilisez une ou plusieurs des constantes mathématiques dans un projet qui inclut également ATLComTime.h, vous devez définir `_USE_MATH_DEFINES` avant d'inclure ATLComTime.h.  
  
## Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)