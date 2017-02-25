---
title: "Erreur du compilateur C2148 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2148"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2148"
ms.assetid: e510c2c9-7b57-4ce8-be03-ba363e2cc5d9
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Erreur du compilateur C2148
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la taille totale du tableau ne doit pas dépasser 0x7fffffff octets  
  
 Un tableau dépasse la limite.  Réduisez la taille du tableau.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2148 :  
  
```  
// C2148.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( ) {  
   char MyArray[0x7ffffffff];   // C2148  
   char * MyArray2 = (char *)malloc(0x7fffffff);  
  
   if (MyArray2)  
      printf_s("It worked!");  
   else  
      printf_s("It didn't work.");  
}  
```