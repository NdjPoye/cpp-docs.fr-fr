---
title: "Erreur du compilateur C2213 | Microsoft Docs"
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
  - "C2213"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2213"
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2213
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'modificateur' : argument non conforme pour \_\_based  
  
 L'argument modificateur de `__based` n'est pas valide.  
  
 L'exemple suivant génère l'erreur C2213 :  
  
```  
// C2213.cpp  
// compile with: /c  
int i;  
int *j;  
char __based(i) *p;   // C2213  
char __based(j) *p2;   // OK  
```