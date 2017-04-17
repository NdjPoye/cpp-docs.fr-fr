---
title: Erreur du compilateur C2669 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2669
dev_langs:
- C++
helpviewer_keywords:
- C2669
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 78a55159984f995724b04a49387b6b46fba7caf2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2669"></a>Erreur du compilateur C2669
fonction membre non autorisée dans une union anonyme  
  
[Les unions anonymes](../../cpp/unions.md#anonymous_unions) ne peut pas avoir de fonctions membres.  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère l’erreur C2669 :  
  
```cpp  
// C2669.cpp  
struct X {  
   union {  
      int i;  
      void f() {   // C2669, remove function  
         i = 0;   
      }  
   };  
};  
```  
  