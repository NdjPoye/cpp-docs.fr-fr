---
title: Erreur du compilateur C2561 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2561
dev_langs:
- C++
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ce30ffb454deb7bc847e736458295d037826a0ad
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2561"></a>Erreur du compilateur C2561
'identificateur' : fonction doit retourner une valeur  
  
 La fonction a été déclarée comme retournant une valeur, mais la définition de fonction ne contient-elle pas un `return` instruction.  
  
 Cette erreur peut résulter d’un prototype de fonction incorrect :  
  
1.  Si la fonction ne retourne pas de valeur, déclarez la fonction avec le type de retour [void](../../cpp/void-cpp.md).  
  
2.  Vérifiez que toutes les branches possibles de la fonction retournent une valeur du type déclaré dans le prototype.  
  
3.  Les fonctions C++ contenant des routines d’assembly inline qui stockent la valeur de retour dans le `AX` register peut-être demander une instruction return. Copiez la valeur dans `AX` dans une variable temporaire et retournez cette variable à partir de la fonction.  
  
 L’exemple suivant génère l’erreur C2561 :  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```
