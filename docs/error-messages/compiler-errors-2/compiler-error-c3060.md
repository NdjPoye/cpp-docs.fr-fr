---
title: Erreur du compilateur C3060 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3060
dev_langs:
- C++
helpviewer_keywords:
- C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
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
ms.openlocfilehash: 859472e3509a04412b413306714b74087d987578
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3060"></a>Erreur du compilateur C3060
'membre' : une fonction friend ne peut pas être définie dans une classe à l’aide d’un nom qualifié (elle peut uniquement être déclarée)  
  
 Une fonction friend a été définie à l’aide d’un nom qualifié, ce qui n’est pas autorisé.  
  
 L’exemple suivant génère l’erreur C3060 :  
  
```  
// C3060.cpp  
class A {  
public:  
   void func();  
};  
  
class C {  
public:  
   friend void A::func() { }   // C3060  
   // Try the following line and the out of class definition:  
   // friend void A::func();  
};  
  
// void A::func(){}  
```