---
title: "Avertissement du compilateur (niveau 3) C4738 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4738"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4738"
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4738
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

stockage de résultat flottant 32 bits en mémoire, perte possible de performances  
  
 L'erreur C4738 signale que le résultat d'une assignation, d'un cast, d'un argument passé, ou d'une autre opération risque de devoir être arrondi ou que l'opération est tombée à court de registres et a dû utiliser de la mémoire \(débordement\).  Cela peut entraîner une perte de performances.  
  
 Pour remédier à cet avertissement et éviter tout arrondi, compilez avec [\/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md) ou utilisez des `double` plutôt que des `float`.  
  
 Pour remédier à cet avertissement et éviter de manquer de registres, modifiez l'ordre de calcul et votre utilisation de la fonctionnalité inlining  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4738 :  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```