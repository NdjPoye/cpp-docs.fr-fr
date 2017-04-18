---
title: Compilateur avertissement (niveau 3) C4645 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4645
dev_langs:
- C++
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
caps.latest.revision: 7
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 45e3b60602ce80deeea5dcd89594741a324ebec2
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4645"></a>Avertissement du compilateur (niveau 3) C4645
la fonction déclarée avec __declspec(noreturn) a une instruction return  
  
 A [retourner](../../cpp/return-statement-in-program-termination-cpp.md) instruction a été trouvée dans une fonction qui est marquée avec la [noreturn](../../cpp/noreturn.md) `__declspec` modificateur. L’instruction `return` a été ignorée.  
  
 L’exemple suivant génère l’avertissement C4645 :  
  
```  
// C4645.cpp  
// compile with:  /W3  
void __declspec(noreturn) func() {  
   return;   // C4645, delete this line to resolve  
}  
  
int main() {  
}  
```
