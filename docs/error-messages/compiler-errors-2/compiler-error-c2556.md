---
title: "Erreur du compilateur C2556 | Microsoft Docs"
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
  - "C2556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2556"
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : les fonctions surchargées ne diffèrent que par le type de retour  
  
 Les fonctions surchargées ont des types de retour différents mais la même liste de paramètres.  Chaque fonction surchargée doit avoir une liste de paramètres formels distincte.  
  
 L'exemple suivant génère l'erreur C2556 :  
  
```  
// C2556.cpp  
// compile with: /c  
class C {  
   int func();  
   double func();   // C2556  
   int func(int i);   // ok parameter lists differ  
};  
```