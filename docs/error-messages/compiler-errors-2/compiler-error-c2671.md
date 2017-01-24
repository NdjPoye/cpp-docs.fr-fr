---
title: "Erreur du compilateur C2671 | Microsoft Docs"
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
  - "C2671"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2671"
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2671
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : les fonctions membres static n'ont pas de pointeurs 'this'  
  
 Une fonction membre `static` a tenté d'accéder à `this`.  
  
 L'exemple suivant génère l'erreur C2671 :  
  
```  
// C2671.cpp  
struct S {  
   static S* const func() { return this; }  // C2671  
};  
```