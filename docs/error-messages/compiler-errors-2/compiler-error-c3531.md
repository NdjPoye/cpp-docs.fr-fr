---
title: Erreur du compilateur C3531 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3531
dev_langs: C++
helpviewer_keywords: C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7753e30e305b7b36adc3b4d2b535f755fa455bdd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3531"></a>Erreur du compilateur C3531
'symbole' : un symbole dont le type contient 'auto' doit avoir un initialiseur  
  
 La variable spécifiée n’a pas d’une expression d’initialiseur.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Spécifiez une expression d’initialiseur, par exemple une affectation simple qui utilise la syntaxe de signe égal, lorsque vous déclarez la variable.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant donne C3531 parce que les variables `x1`, `y1, y2, y3`, et `z2` ne sont pas initialisés.  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)