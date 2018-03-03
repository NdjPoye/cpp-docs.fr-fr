---
title: Compilateur avertissement (niveau 4) C4127 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1a5bbd86b6197907f043478df225dceb79679f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4127"></a>Avertissement du compilateur (niveau 4) C4127
l'expression conditionnelle est une constante  
  
 L’expression de contrôle d’une instruction `if` ou d’une boucle `while` correspond à une constante. En raison de leur utilisation IDIOMATIQUE commune, constantes triviales tels que 1 ou `true` ne déclenchent pas l’avertissement, sauf s’ils sont le résultat d’une opération dans une expression. Si l’expression de contrôle d’un `while` boucle est une constante, car la boucle s’arrête au milieu, envisagez de remplacer le `while` boucle avec un `for` boucle. Vous pouvez omettre l’initialisation, le test de fin et l’incrément de boucle d’une `for` boucle, ce qui entraîne une boucle infinie, tout comme `while(1)`, et vous pouvez quitter la boucle à partir du corps de la `for` instruction.  
  
 L’exemple suivant montre deux façons C4127 est généré et montre comment utiliser une boucle for pour éviter cet avertissement :  
  
```  
// C4127.cpp  
// compile with: /W4  
#include <stdio.h>  
int main() {  
   if (1 == 1) {}   // C4127  
   while (42) { break; }   // C4127  
  
   // OK  
   for ( ; ; ) {  
      printf("test\n");  
      break;  
   }  
}  
```