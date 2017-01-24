---
title: "Avertissement du compilateur (niveau&#160;4) C4127 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4127"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4127"
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 12
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4127
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'expression conditionnelle est une constante  
  
 L’expression de contrôle d’une instruction `if` ou d’une boucle `while` correspond à une constante. Si l’expression de contrôle d’une boucle `while` est une constante car la boucle s’arrête au milieu, vous pouvez remplacer la boucle `while` par une boucle `for`. Vous pouvez omettre l’initialisation, le test de fin et l’incrément de boucle d’une boucle `for`, ce qui en fait une boucle infinie \(comme `while(1)`\), et vous pouvez quitter la boucle à partir du corps de l’instruction `for`.  
  
 L’exemple suivant génère l’avertissement C4127 :  
  
```  
// C4127.cpp // compile with: /W4 #include <stdio.h> int main() { if (1 == 1) {}   // C4127 while (1) { break; }   // C4127 // OK for ( ; ; ) { printf("test\n"); break; } }  
```