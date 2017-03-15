---
title: "Erreur du compilateur C2486 | Microsoft Docs"
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
  - "C2486"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2486"
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2486
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_LOCAL\_SIZE' uniquement autorisé dans les fonctions ayant l'attribut 'naked'  
  
 Dans les fonctions d'assembly inline, le nom `__LOCAL_SIZE` est réservé aux fonctions déclarées avec l'attribut [naked](../../cpp/naked-cpp.md).  
  
 L'exemple suivant génère l'erreur C2486 :  
  
```  
// C2486.cpp  
// processor: x86  
void __declspec(naked) f1() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE  
   }  
}  
void f2() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE   // C2486  
   }  
}  
```