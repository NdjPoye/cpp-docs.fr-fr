---
title: "Erreur du compilateur C2683 | Microsoft Docs"
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
  - "C2683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2683"
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'cast' : 'type' n'est pas un type polymorphe  
  
 Vous ne pouvez pas utiliser [dynamic\_cast](../../cpp/dynamic-cast-operator.md) pour effectuer une conversion depuis une classe non polymorphe \(une classe sans fonctions virtuelles\).  
  
 Vous pouvez utiliser [static\_cast](../../cpp/static-cast-operator.md) pour effectuer des conversions des types non polymorphes.  `static_cast` n'effectue cependant pas de contrôle à l'exécution.  
  
 L'exemple suivant génère l'erreur C2683 :  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```