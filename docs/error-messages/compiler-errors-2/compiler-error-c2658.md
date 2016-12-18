---
title: "Erreur du compilateur C2658 | Microsoft Docs"
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
  - "C2658"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2658"
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2658
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : redéfinition dans un struct\/union anonyme  
  
 Deux déclarations de membre contenues dans des structures ou des unions anonymes avec le même identificateur, mais avec des types différents.  Vous obtiendrez également cette erreur pour les membres ayant le même identificateur et le même type sous [\/Za](../../build/reference/za-ze-disable-language-extensions.md).  
  
 L'exemple suivant génère l'erreur C2658 :  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```