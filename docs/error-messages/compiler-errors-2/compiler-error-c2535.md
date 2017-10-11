---
title: Erreur du compilateur C2535 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0af3ce8f0f3fe89d8e2f120f1b9b16383f11ef6a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2535"></a>Erreur du compilateur C2535
'identificateur' : fonction membre déjà définie ou déclarée  
  
 Cette erreur peut être dû à l’aide de la même liste de paramètres formels dans plus d’une définition ou déclaration d’une fonction surchargée.  
  
 Si vous obtenez C2535 en raison de la fonction Dispose, consultez [destructeurs et finaliseurs](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) pour plus d’informations.  
  
 Si vous compilez un projet ATL, consultez l’article Q241852 de la Base de connaissances Microsoft.  
  
 L’exemple suivant génère l’erreur C2535 :  
  
```  
// C2535.cpp  
// compile with: /c  
class C {  
public:  
   void func();   // forward declaration  
   void func() {}   // C2535  
};  
```
