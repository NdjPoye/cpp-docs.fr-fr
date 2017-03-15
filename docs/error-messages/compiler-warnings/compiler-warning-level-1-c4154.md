---
title: "Avertissement du compilateur (niveau 1) C4154 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4154"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4154"
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau 1) C4154
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

suppression d'une expression array ; conversion en pointeur fournie  
  
 Étant donné que vous ne pouvez pas utiliser `delete` sur un tableau, le compilateur convertit le tableau en pointeur.  
  
## Exemple  
  
```  
// C4154.cpp  
// compile with: /c /W1  
int main() {  
   int array[ 10 ];  
   delete array;   // C4154 can't delete stack object  
  
   int *parray2 = new int [10];  
   int (&array2)[10] = (int(&)[10]) parray2;  
   delete [] array2;   // C4154  
  
   // try the following line instead  
   delete [] &array2;  
}  
```