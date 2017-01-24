---
title: "Erreur du compilateur C3766 | Microsoft Docs"
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
  - "C3766"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3766"
ms.assetid: b5af2089-2e1e-4e45-a41d-495b6c55656e
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3766
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' doit fournir une implémentation de la méthode d'interface 'fonction'  
  
 Une classe qui hérite d'une interface doit implémenter les membres de l'interface.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3766 :  
  
```  
// C3766.cpp  
// compile with: /clr /c  
  
delegate void MyDel();  
  
interface struct IFace {  
   virtual event MyDel ^ E;  
};  
  
ref struct Class1 : public IFace {};   // C3766  
  
// OK  
ref struct Class2 : public IFace {  
   virtual event MyDel ^ E {  
      void add(MyDel ^) {}  
      void remove(MyDel ^) {}  
   }  
};  
```