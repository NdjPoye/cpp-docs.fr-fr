---
title: Compilateur avertissement (niveau 4) C4130 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4130
dev_langs:
- C++
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
caps.latest.revision: 6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 32ec1055c5da769c026b778897a5bd9b741b2d40
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4130"></a>Avertissement du compilateur (niveau 4) C4130
'opérateur' : opération logique sur l’adresse d’une constante de chaîne  
  
 L’utilisation de l’opérateur avec l’adresse d’un littéral de chaîne génère du code inattendu.  
  
 L’exemple suivant génère l’avertissement C4130 :  
  
```  
// C4130.cpp  
// compile with: /W4  
int main()  
{  
   char *pc;  
   pc = "Hello";  
   if (pc == "Hello") // C4130  
   {  
   }  
}  
```  
  
 L’ instruction **If** compare la valeur stockée dans le pointeur `pc` à l’adresse de la chaîne « Hello », qui est allouée séparément à chaque occurrence de la chaîne dans le code. L’ instruction **If** ne compare pas la chaîne vers laquelle `pc` pointe avec la chaîne « Hello ».  
  
 Pour comparer des chaînes, utilisez la fonction `strcmp` .
