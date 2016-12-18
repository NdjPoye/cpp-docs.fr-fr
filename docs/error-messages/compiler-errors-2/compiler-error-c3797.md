---
title: "Erreur du compilateur C3797 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3797"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3797"
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3797
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'substitution' : la déclaration event ne peut pas avoir de spécificateur de substitution \(vous devez l'ajouter aux méthodes add\/remove\/raise de l'événement à la place\)  
  
 Vous ne pouvez pas substituer d'événement trivial \(un événement dépourvu de méthode d'accesseur définie explicitement\) avec un autre événement trivial.  L'événement de substitution doit définir son comportement avec des fonctions d'accesseur.  
  
 Pour plus d'informations, consultez [event](../../windows/event-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3797 :  
  
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