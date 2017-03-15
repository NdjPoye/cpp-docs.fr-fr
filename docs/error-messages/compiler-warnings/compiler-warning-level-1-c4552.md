---
title: "Avertissement du compilateur (niveau 1) C4552 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4552"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4552"
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4552
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : opérateur sans effet ; opérateur avec effet secondaire attendu  
  
 Si une instruction d'expression contient un opérateur sans effet au début de l'expression, c'est sans doute une erreur.  
  
 Pour substituer cet avertissement, mettez l'expression entre parenthèses.  
  
 L'exemple suivant génère l'erreur C4552 :  
  
```  
// C4552.cpp  
// compile with: /W1  
int main() {  
   int i, j;  
   i + j;   // C4552  
   // try the following line instead  
   // (i + j);  
}  
```