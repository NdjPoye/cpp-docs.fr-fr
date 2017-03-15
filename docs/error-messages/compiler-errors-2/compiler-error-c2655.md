---
title: "Erreur du compilateur C2655 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2655"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2655"
ms.assetid: beaefa6e-51b3-4df9-9150-960f3fbf40e0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2655
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : définition ou redéclaration non conforme dans la portée actuelle  
  
 Un identificateur ne peut être redéclaré qu'au niveau de la portée globale.  
  
 L'exemple suivant génère l'erreur C2655 :  
  
```  
// C2655.cpp  
class A {};  
class B {  
public:  
   static int i;  
};  
  
int B::i;  // OK  
  
int main() {  
   A B::i;  // C2655  
}  
```