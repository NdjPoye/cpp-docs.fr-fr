---
title: "Avertissement du compilateur (niveau 1) C4114 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4114"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4114"
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4114
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

même qualificateur de type utilisé plusieurs fois  
  
 Une déclaration ou une définition de type utilise plus d'une fois un qualificateur de type \(**const**, `volatile`, **signed** ou `unsigned`\).  Ceci génère un avertissement avec les extensions Microsoft \(\/Ze\) et une erreur sous compatibilité ANSI \(\/Za\).  
  
 L'exemple suivant génère l'erreur C4114 :  
  
```  
// C4114.cpp  
// compile with: /W1 /c  
volatile volatile int i;   // C4114  
```  
  
 L'exemple suivant génère l'erreur C4114 :  
  
```  
// C4114_b.cpp  
// compile with: /W1 /c  
static const int const * ii;   // C4114  
static const int * const iii;   // OK  
```