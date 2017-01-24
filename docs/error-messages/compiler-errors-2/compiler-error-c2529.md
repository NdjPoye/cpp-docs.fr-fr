---
title: "Erreur du compilateur C2529 | Microsoft Docs"
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
  - "C2529"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2529"
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2529
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom' : la référence à une référence n'est pas conforme  
  
 Cette erreur peut être résolue en utilisant la syntaxe de pointeur et en déclarant une référence à un pointeur.  
  
 L'exemple suivant génère l'erreur C2529 :  
  
```  
// C2529.cpp  
// compile with: /c  
int i;  
int &ri = i;  
int &(&rri) = ri;   // C2529  
```