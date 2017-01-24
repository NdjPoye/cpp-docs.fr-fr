---
title: "Erreur du compilateur C2460 | Microsoft Docs"
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
  - "C2460"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2460"
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2460
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur1' : utilise 'identificateur2', en cours de définition  
  
 Une classe ou une structure \(`identifier2`\) est déclarée comme un membre d'elle\-même \(`identifier1`\).  Les définitions récursives des classes et des structures ne sont pas autorisées.  
  
 L'exemple suivant génère l'erreur C2460 :  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 À la place, utilisez une référence de pointeur dans la classe.  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```