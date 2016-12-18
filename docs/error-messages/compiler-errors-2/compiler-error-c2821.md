---
title: "Erreur du compilateur C2821 | Microsoft Docs"
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
  - "C2821"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2821"
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2821
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le premier paramètre formel de 'operator new' doit être 'unsigned int'  
  
 Le premier paramètre formel de [opérateur new](../Topic/operator%20new%20\(%3Cnew%3E\).md) doit être unsigned `int`non signé.  
  
 L'exemple suivant génère l'erreur C2821 :  
  
```  
// C2821.cpp  
// compile with: /c  
void * operator new( /* unsigned int,*/ void * );   // C2821  
void * operator new( unsigned int, void * );  
```