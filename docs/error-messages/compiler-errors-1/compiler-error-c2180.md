---
title: "Erreur du compilateur C2180 | Microsoft Docs"
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
  - "C2180"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2180"
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2180
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'expression de contrôle a le type 'type'  
  
 L'expression de contrôle dans une instruction `if`, `while`, `for` ou `do` est une expression convertie vers `void`.  Pour résoudre ce problème, remplacez l'expression de contrôle par une expression qui génère un `bool` ou un type pouvant être converti en `bool`.  
  
 L'exemple suivant génère l'erreur C2180 :  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```