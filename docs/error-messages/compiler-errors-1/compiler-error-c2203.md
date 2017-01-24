---
title: "Erreur du compilateur C2203 | Microsoft Docs"
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
  - "C2203"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2203"
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2203
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'opérateur delete ne peut pas spécifier de limites pour un tableau  
  
 Avec l'option **\/Za** \(ANSI\), l'opérateur `delete` peut supprimer la totalité d'un tableau, mais pas des parties ou des membres spécifiques du tableau.  
  
 L'exemple suivant génère l'erreur C2203 :  
  
```  
// C2203.cpp  
// compile with: /Za  
int main() {  
   int *ar = new int[10];  
   delete [4] ar;   // C2203  
   // try the following line instead  
   // delete [] ar;  
}  
```