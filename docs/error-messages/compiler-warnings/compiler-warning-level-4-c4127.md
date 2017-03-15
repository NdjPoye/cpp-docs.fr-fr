---
title: Compilateur avertissement (niveau 4) C4127 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6197f0018ebb6f23b4608e376282b32cd030ba30
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4127"></a>Avertissement du compilateur (niveau 4) C4127
l'expression conditionnelle est une constante  
  
 L’expression de contrôle d’une instruction `if` ou d’une boucle `while` correspond à une constante. En raison de leur utilisation IDIOMATIQUE commune, constantes simples telle que 1 ou `true` ne déclenchent pas d’avertissement, sauf s’ils sont le résultat d’une opération dans une expression. Si l’expression de contrôle d’un `while` boucle est une constante parce que la boucle s’arrête au milieu, vous pouvez remplacer le `while` une boucle avec une `for` boucle. Vous pouvez omettre l’initialisation, le test de fin et l’incrément de boucle d’une `for` boucle, ce qui entraîne une boucle infinie, tout comme `while(1)`, et vous pouvez quitter la boucle du corps de la `for` instruction.  
  
 L’exemple suivant montre deux façons de C4127 est générée et indique comment utiliser une boucle éviter l’avertissement :  
  
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
