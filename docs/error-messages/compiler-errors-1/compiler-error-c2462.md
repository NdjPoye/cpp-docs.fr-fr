---
title: "Erreur du compilateur C2462 | Microsoft Docs"
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
  - "C2462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2462"
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : impossible de définir un type dans une 'new\-expression'  
  
 Vous ne pouvez pas définir un type dans la zone opérande de l'opérateur `new`.  Mettez la définition de type dans une instruction séparée.  
  
 L'exemple suivant génère l'erreur C2462 :  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```