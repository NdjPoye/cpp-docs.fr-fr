---
title: Erreur du compilateur C3797 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3797
dev_langs: C++
helpviewer_keywords: C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5157e8b63bf15c2d972235e38f692e2ba356a629
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3797"></a>Erreur du compilateur C3797
'override' : déclaration d’événement ne peut pas avoir de spécificateur de substitution (doit être sur les méthodes d’ajout/remove/raise événement à la place)  
  
 Vous ne pouvez pas remplacer un événement trivial (un événement sans méthodes d’accesseur définie explicitement) avec un autre événement trivial. L’événement de substitution doit définir son comportement avec des fonctions d’accesseur.  
  
 Pour plus d’informations, consultez [événement](../../windows/event-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3797.  
  
```  
// C3797.cpp  
// compile with: /clr /c  
delegate void MyDel();  
  
ref class Class1 {  
public:  
   virtual event MyDel ^ E;  
};  
  
ref class Class2 : public Class1 {  
public:  
   virtual event MyDel ^ E override;   // C3797  
};  
  
// OK  
ref class Class3 : public Class1 {  
public:  
   virtual event MyDel ^ E {  
      void add(MyDel ^ d) override {}  
      void remove(MyDel ^ d) override {}  
   }  
};  
```