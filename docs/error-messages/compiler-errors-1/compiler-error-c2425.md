---
title: "Erreur du compilateur C2425 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2425"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2425"
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2425
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'jeton' : expression non constante dans 'contexte'  
  
 Le jeton fait partie d'une expression non constante dans ce contexte.  
  
 Pour résoudre ce problème, remplacez le jeton par une constante littérale ou un calcul.  
  
 L'exemple suivant génère l'erreur C2425 :  
  
```  
// C2425.cpp  
// processor: x86  
int main() {  
   int i = 3;  
   __asm {  
      mov eax, [ebp - i]   // C2425  
      mov eax, [ebp - 3]   // OK  
   }  
}  
```