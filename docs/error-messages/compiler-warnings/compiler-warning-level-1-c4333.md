---
title: "Avertissement du compilateur (niveau 1) C4333 | Microsoft Docs"
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
  - "C4333"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4333"
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4333
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : décalage vers la droite trop important, perte de données  
  
 Une opération de décalage vers la droite était trop importante.  Tous les bits significatifs sont  éliminés et le résultat est toujours zéro.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4333 :  
  
```  
// C4333.cpp  
// compile with: /c /W1  
unsigned shift8 (unsigned char c) {  
   return c >> 8;   // C4333  
  
   // try the following line instead  
   // return c >> 4;   // OK  
}  
```