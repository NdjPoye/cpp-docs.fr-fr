---
title: Erreur du compilateur C2250 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2250
dev_langs:
- C++
helpviewer_keywords:
- C2250
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a50443932a2b8cb3ef6e66989ee53322de29868d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2250"></a>Erreur du compilateur C2250
'identificateur' : héritage ambigu de 'classe::membre'  
  
 La classe dérivée hérite de plusieurs substitutions d’une fonction virtuelle d’une classe de base virtuelle. Ces substitutions sont ambiguës dans la classe dérivée.  
  
 L’exemple suivant génère l’erreur C2286 :  
  
```  
// C2250.cpp  
// compile with: /c  
// C2250 expected  
struct V {  
   virtual void vf();  
};  
  
struct A : virtual V {  
   void vf();  
};  
  
struct B : virtual V {  
   void vf();  
};  
  
struct D : A, B {  
   // Uncomment the following line to resolve.  
   // void vf();  
};  
```