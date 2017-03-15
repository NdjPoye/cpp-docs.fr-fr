---
title: "Avertissement du compilateur (niveau&#160;1) C4822 | Microsoft Docs"
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
  - "C4822"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4822"
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4822
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

’membre’ : la fonction membre de classe locale n’a pas de corps  
  
 Une fonction membre de classe locale a été déclarée mais n’a pas été définie dans la classe. Pour utiliser une fonction membre de classe locale, vous devez la définir dans la classe. Vous ne pouvez pas la déclarer dans la classe et la définir hors classe.  
  
 Toute définition hors classe pour une fonction membre de classe locale constitue une erreur.  
  
 L’exemple suivant génère l’erreur C4822 :  
  
```  
// C4822.cpp // compile with: /W1 int main() { struct C { void func1(int);   // C4822 // try the following line instead // void func1(int){} }; }  
```