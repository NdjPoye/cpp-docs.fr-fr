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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2bc9be3cfa38b4789feb35ae57015b78ad079c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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