---
title: "Erreur du compilateur C2790 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2790"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2790"
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2790
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super' : ce mot clé peut seulement être utilisé dans le corps d'une fonction membre de classe  
  
 Ce message d'erreur apparaît si l'utilisateur tente d'utiliser le mot clé [super](../../cpp/super.md) en dehors du contexte d'une fonction membre.  
  
 L'exemple suivant génère l'erreur C2790 :  
  
```  
// C2790.cpp  
void f() {  
   __super::g();   // C2790  
}  
```