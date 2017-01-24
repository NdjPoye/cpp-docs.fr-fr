---
title: "Erreur du compilateur C2794 | Microsoft Docs"
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
  - "C2794"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2794"
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2794
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : n'est membre d'aucune classe de base directe ou indirecte de 'classe'  
  
 Vous avez tenté d'utiliser [super](../../cpp/super.md) pour appeler une fonction membre qui n'existait pas.  
  
 L'exemple suivant génère l'avertissement C2794 :  
  
```  
// C2794.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::f();  // C2794  
   }  
};  
```