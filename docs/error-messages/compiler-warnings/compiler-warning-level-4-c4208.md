---
title: "Avertissement du compilateur (niveau 4) C4208 | Microsoft Docs"
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
  - "C4208"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4208"
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4208
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : delete \[exp\] \- exp analysée mais ignorée  
  
 Avec les extensions Microsoft \(\/Ze\), vous pouvez supprimer un tableau en utilisant une valeur entre accolades avec l'[opérateur delete](../../cpp/delete-operator-cpp.md).  La valeur est ignorée.  
  
```  
// C4208.cpp  
// compile with: /W4  
int main()  
{  
   int * MyArray = new int[18];  
   delete [18] MyArray;      // C4208  
   MyArray = new int[18];  
   delete [] MyArray;        // ok  
}  
```  
  
 Ces valeurs sont non conformes sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).