---
title: "Avertissement du compilateur (niveau 4) C4238 | Microsoft Docs"
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
  - "C4238"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4238"
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4238
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : classe rvalue utilisée comme lvalue  
  
 Pour compatibilité avec les versions précédentes de Visual C\+\+, les extensions Microsoft \(**\/Ze**\) permettent d'utiliser un type de classe comme rvalue dans un contexte qui prend son adresse de façon implicite ou explicite.  Dans certains cas, comme dans l'exemple ci\-dessous, ce peut être dangereux.  
  
## Exemple  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 Cette utilisation génère une erreur sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).