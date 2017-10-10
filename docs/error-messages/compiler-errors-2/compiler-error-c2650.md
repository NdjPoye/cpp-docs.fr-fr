---
title: Erreur du compilateur C2650 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2650
dev_langs:
- C++
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c3352820434c8d794d4980a606cb945bd8ecc4a8
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2650"></a>Erreur du compilateur C2650
'opérateur' : ne peut pas être une fonction virtuelle  
  
 A `new` ou `delete` opérateur est déclaré `virtual`. Ces opérateurs sont `static` les fonctions de membre et ne peut pas être `virtual`.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C2650 :  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```
