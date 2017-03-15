---
title: "Avertissement du compilateur (niveau 2) C4156 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4156"
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 2) C4156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

suppression d'une expression array sans utiliser la forme 'delete' ; substituée par la forme array  
  
 La forme non\-tableau de **delete** ne peut pas supprimer un tableau.  Le compilateur a traduit **delete** en sa forme tableau.  
  
 Cet avertissement n'apparaît que sous les extensions Microsoft \(\/Ze\).  
  
## Exemple  
  
```  
// C4156.cpp  
// compile with: /W2  
int main()  
{  
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];  
   delete array; // C4156, changed by compiler to "delete [] array;"  
}  
```