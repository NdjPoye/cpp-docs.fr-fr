---
title: "Avertissement du compilateur&#160;(niveau&#160;3) C4316 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4316"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4316"
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Avertissement du compilateur&#160;(niveau&#160;3) C4316
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Il se peut que l'objet alloué sur le tas ne soit pas aligné pour ce type.  
  
 Un objet sur\-aligné alloué avec `operator new` peut ne pas avoir l'alignement spécifié.  Remplacez [operator new](../../c-runtime-library/operator-new-crt.md) et [operator delete](../../c-runtime-library/operator-delete-crt.md) pour les types sur\-alignés afin qu'ils utilisent les routines d'allocation alignées, par exemple, [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) et [\_aligned\_free](../../c-runtime-library/reference/aligned-free.md).  L'exemple suivant génère l'erreur C4316 :  
  
```cpp  
// C4316.cpp  
// Test: cl /W3 /c C4316.cpp  
  
__declspec(align(32)) struct S {}; // C4324  
  
int main() {  
    new S; // C4316  
}  
```