---
title: "Erreur du compilateur C2488 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2488"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2488"
ms.assetid: cd435909-43e4-43c6-a57c-5d02468ef75f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C2488
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : 'naked' ne peut s'appliquer qu'aux définitions de fonctions non membres  
  
 L'attribut [naked](../../cpp/naked-cpp.md) a été appliqué à une déclaration de fonction.  
  
 L'exemple suivant génère l'erreur C2488 :  
  
```  
// C2488.cpp  
// compile with: /c  
// processor: x86  
__declspec( naked ) void func();   // C2488  declaration, not definition  
__declspec( naked ) void i;   // C2488  i is not a function  
  
__declspec( naked ) void func() {}   // OK  
```