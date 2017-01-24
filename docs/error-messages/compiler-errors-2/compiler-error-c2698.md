---
title: "Erreur du compilateur C2698 | Microsoft Docs"
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
  - "C2698"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2698"
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2698
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la déclaration using pour 'déclaration1' ne peut pas coexister avec la déclaration using existante pour 'déclaration2'  
  
 Une fois que vous avez une [using declaration](../../cpp/using-declaration.md) pour des données membres, toute déclaration using dans la même portée qui emploie le même nom est interdite, car seules les fonctions peuvent être surchargées.  
  
 L'exemple suivant génère l'erreur C2698 :  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```