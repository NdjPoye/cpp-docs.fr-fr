---
title: "Erreur du compilateur C3531 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3531"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3531"
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3531
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

« symbole » : un symbole dont le type contient « auto » doit avoir un initialiseur  
  
 La variable spécifiée n'a pas d'expression d'initialiseur.  
  
### Pour corriger cette erreur  
  
1.  Spécifiez une expression d'initialiseur, telle qu'une assignation simple qui utilise la syntaxe de signe égal, lorsque vous déclarez la variable.  
  
## Exemple  
 L'exemple suivant donne C3531 parce que les variables `x1`, `y1, y2, y3` et `z2` ne sont pas initialisées.  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)