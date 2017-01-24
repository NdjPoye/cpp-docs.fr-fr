---
title: "Erreur du compilateur C3176 | Microsoft Docs"
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
  - "C3176"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3176"
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3176
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : impossible de déclarer un type valeur local  
  
 Une classe peut seulement être déclarée comme un type valeur au niveau de la portée globale.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3176 :  
  
```  
// C3176.cpp  
// compile with: /clr  
int main () {  
   enum class C {};   // C3176  
}  
```