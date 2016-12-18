---
title: "Erreur du compilateur C2733 | Microsoft Docs"
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
  - "C2733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2733"
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

seconde liaison C d'une fonction surchargée 'fonction' non autorisée  
  
 Plusieurs fonctions surchargées sont déclarées avec la liaison C.  Lors de l'utilisation de la liaison C, seule une forme d'une fonction spécifiée peut être externe.  Comme les fonctions surchargées portent le même nom non décoré, elles ne peuvent être utilisées avec les programmes en langage C.  
  
 L'exemple suivant génère l'erreur C2733 :  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```