---
title: "Erreur du compilateur C2250 | Microsoft Docs"
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
  - "C2250"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2250"
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2250
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : héritage ambigu de 'classe::membre'  
  
 La classe dérivée hérite de plusieurs substitutions d'une fonction virtuelle ou d'une classe de base virtuelle.  Ces substitutions sont ambiguës dans la classe dérivée.  
  
 L'exemple suivant génère l'erreur C2286 :  
  
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