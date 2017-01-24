---
title: "Erreur du compilateur C2637 | Microsoft Docs"
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
  - "C2637"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2637"
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2637
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : impossible de modifier les pointeurs sur données membres  
  
 Un pointeur vers une donnée membre ne peut pas posséder de convention d'appel.  Pour remédier à cela, supprimez la convention d'appel ou déclarez un pointeur vers une fonction membre.  
  
 L'exemple suivant génère l'erreur C2637 :  
  
```  
// C2637.cpp  
// compile with: /c  
struct S {};  
int __stdcall S::*pms1;   // C2637  
  
// OK  
int S::*pms2;  
int (__stdcall S::*pms3)(...);  
```