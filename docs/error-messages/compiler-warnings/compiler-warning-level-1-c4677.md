---
title: "Avertissement du compilateur (niveau 1) C4677 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4677"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4677"
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Avertissement du compilateur (niveau 1) C4677
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la signature de membre non privée contient un type privé d'assembly 'type\_privé'  
  
 Un type ayant une accessibilité publique en dehors de l'assembly utilise un type qui a un accès privé en dehors de l'assembly.  Un composant qui fait référence au type d'assembly public ne pourra pas utiliser le ou les membres du type faisant référence au type privé d'assembly.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4677 :  
  
```  
// C4677.cpp  
// compile with: /clr /c /W1  
delegate void TestDel();  
public delegate void TestDel2();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;   // C4677  
   static event TestDel2^ MyClass_Event2;   // OK  
};  
```