---
title: "Erreur du compilateur C2791 | Microsoft Docs"
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
  - "C2791"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2791"
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2791
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

utilisation non conforme de 'super' : 'classe' n'a aucune classe de base  
  
 Le mot clé [super](../../cpp/super.md) a été utilisé dans le contexte d'une fonction membre d'une classe dépourvue de classes de base.  
  
 L'exemple suivant génère l'erreur C2791 :  
  
```  
// C2791.cpp  
struct D {  
   void mf() {  
      __super::mf();   // C2791  
   }  
};  
```