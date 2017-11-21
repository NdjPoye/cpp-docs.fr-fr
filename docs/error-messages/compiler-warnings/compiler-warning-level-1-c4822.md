---
title: Compilateur avertissement (niveau 1) C4822 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4822
dev_langs: C++
helpviewer_keywords: C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8c57b23d23faf27b0f59f9c1ad1cc1065105c7e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4822"></a>Avertissement du compilateur (niveau 1) C4822
’membre’ : la fonction membre de classe locale n’a pas de corps  
  
 Une fonction membre de classe locale a été déclarée mais n’a pas été définie dans la classe. Pour utiliser une fonction membre de classe locale, vous devez la définir dans la classe. Vous ne pouvez pas la déclarer dans la classe et la définir hors classe.  
  
 Toute définition hors classe pour une fonction membre de classe locale constitue une erreur.  
  
 L’exemple suivant génère l’erreur C4822 :  
  
```  
// C4822.cpp  
// compile with: /W1  
int main() {  
   struct C {  
      void func1(int);   // C4822  
      // try the following line instead  
      // void func1(int){}  
  };  
}  
```