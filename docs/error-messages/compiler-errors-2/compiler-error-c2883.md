---
title: "Erreur du compilateur C2883 | Microsoft Docs"
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
  - "C2883"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2883"
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2883
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom' : conflits de déclaration de fonction avec 'identificateur' introduit par une déclaration using  
  
 Vous avez essayé de définir une fonction plus d'une fois.  La première définition a été effectuée depuis un espace de noms avec une déclaration `using`.  La deuxième était une définition locale.  
  
 L'exemple suivant génère l'erreur C2883 :  
  
```  
// C2883.cpp  
namespace A {  
   void z(int);  
}  
  
int main() {  
   using A::z;  
   void z(int);   // C2883  z is already defined  
}  
```