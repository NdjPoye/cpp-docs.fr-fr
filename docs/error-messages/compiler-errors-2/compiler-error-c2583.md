---
title: "Erreur du compilateur C2583 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2583"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2583"
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2583
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : pointeur 'this' 'const\/volatile' non conforme pour les constructeurs\/destructeurs  
  
 Un constructeur ou un destructeur est déclaré `const` ou `volatile`.  Cela n'est pas autorisé.  
  
 L'exemple suivant génère l'erreur C2583 :  
  
```  
// C2583.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
   A() const;   // C2583  
  
   // try the following line instead  
   // A();  
};  
```