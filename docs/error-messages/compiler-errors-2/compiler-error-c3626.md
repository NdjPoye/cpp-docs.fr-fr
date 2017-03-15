---
title: "Erreur du compilateur C3626 | Microsoft Docs"
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
  - "C3626"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3626"
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3626
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'MotClé' : le mot clé '\_\_event' ne peut être utilisé que sur les interfaces COM, les fonctions membre et les données membre qui sont des pointeurs vers les délégués  
  
 Un mot clé n'a pas été utilisé correctement.  
  
 L'exemple suivant génère l'erreur C3626 :  
  
```  
// C3626.cpp  
// compile with: /c  
struct A {  
   __event int i;   // C3626  
// try the following line instead  
// __event int i();  
};  
```