---
title: "Erreur du compilateur C2674 | Microsoft Docs"
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
  - "C2674"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2674"
ms.assetid: 7cbd70d8-d992-44d7-a5cb-dd8cf9c759d2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2674
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

une déclaration générique n'est pas autorisée dans ce contexte  
  
 Un générique a été déclaré de façon incorrecte.  Pour plus d'informations, consultez [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2674 :  
  
```  
// C2674.cpp  
// compile with: /clr /c  
void F(generic <class T> ref class R1);   // C2674  
generic <class T> ref class R2 {};   // OK  
```