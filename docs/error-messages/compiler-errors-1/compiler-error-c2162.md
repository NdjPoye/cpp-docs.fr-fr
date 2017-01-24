---
title: "Erreur du compilateur C2162 | Microsoft Docs"
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
  - "C2162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2162"
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

paramètre formel de macro attendu  
  
 Le jeton suivant un opérateur de transformation en chaîne \(\#\) n'est pas un nom de paramètre formel.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2162 :  
  
```  
// C2162.cpp  
// compile with: /c  
#include <stdio.h>  
  
#define print(a) printf_s(b)   // OK  
#define print(a) printf_s(#b)    // C2162  
```