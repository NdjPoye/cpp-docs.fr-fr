---
title: "Erreur du compilateur C2275 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2275"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2275"
ms.assetid: c1eafa71-48de-46e0-82f3-b575538ef205
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2275
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : utilisation non conforme de ce type comme expression  
  
 Une expression utilise l'opérateur `->` avec un identificateur `typedef`.  
  
 L'exemple suivant génère l'erreur C2275 :  
  
```  
// C2275.cpp  
typedef struct S {  
    int mem;  
} *S_t;  
void func1( int *parm );  
void func2() {  
    func1( &S_t->mem );   // C2275, S_t is a typedef  
}  
```