---
title: Erreur du compilateur C2698 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 654367e882b16c18cc4bd58c339d61c653dc68e9
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2698"></a>Erreur du compilateur C2698
la déclaration using pour ' déclaration 1' ne peuvent pas coexister avec la déclaration using existante pour ' déclaration 2'  
  
 Une fois que vous avez un [à l’aide de la déclaration](../../cpp/using-declaration.md) pour un membre de données, à l’aide de toute déclaration dans la même portée qui utilise le même nom n’est pas autorisée, car seules les fonctions peuvent être surchargées.  
  
 L’exemple suivant génère C2698 :  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```
