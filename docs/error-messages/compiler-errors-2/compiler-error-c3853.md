---
title: Erreur du compilateur C3853 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3853
dev_langs:
- C++
helpviewer_keywords:
- C3853
ms.assetid: 5b71805d-52b4-44ec-80ae-37c68d876f6a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 67d28c19d873c57c2566254077e605769534b1f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3853"></a>Erreur du compilateur C3853
'=' : réinitialisation d’une référence ou une assignation via une référence de fonction est non conforme  
  
 Impossible d’assigner à une référence à une fonction, car les fonctions ne sont pas des valeurs lvalues.  
  
 Les exemples suivants génèrent C3853 :  
  
```  
// C3853.cpp  
// compile with: /EHsc  
#include <iostream>  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   rf = afunc;   // C3853, can't reassign to a ref that's an lvalue  
   int i = 99;  
   int & ri = i;  
   std::cout << i << std::endl;  
   ri = 0;   // OK, i = 88;  
   std::cout << i << std::endl;  
}  
```