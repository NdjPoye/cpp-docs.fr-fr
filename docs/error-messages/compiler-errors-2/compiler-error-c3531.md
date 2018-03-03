---
title: Erreur du compilateur C3531 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c7c8158d798df3fb48c45194ff6a01a1cbf3ab4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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