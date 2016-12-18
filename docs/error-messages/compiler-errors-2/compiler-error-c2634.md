---
title: "Erreur du compilateur C2634 | Microsoft Docs"
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
  - "C2634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2634"
ms.assetid: 58c8f2db-ac95-4a81-9355-ef3cfb0ba7b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'&classe::membre' : pointeur non conforme vers un membre de référence  
  
 Un pointeur vers un membre de référence est déclaré.  
  
 L'exemple suivant génère l'erreur C2634 :  
  
```  
// C2634.cpp  
int mem;  
struct S {  
   S() : rf(mem) { }  
   int &rf;  
};  
int (S::*pdm) = &S::rf;   // C2634  
```