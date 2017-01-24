---
title: "Erreur du compilateur C2627 | Microsoft Docs"
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
  - "C2627"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2627"
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2627
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : fonction membre non autorisée dans une union anonyme  
  
 Une [union anonyme](../../misc/anonymous-unions.md) ne peut pas avoir de fonctions membre.  
  
 L'exemple suivant génère l'erreur C2627 :  
  
```  
// C2627.cpp  
int main() {  
   union { void f(){} };   // C2627  
   union X { void f(){} };  
}  
```