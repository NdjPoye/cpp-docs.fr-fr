---
title: "Avertissement du compilateur (niveau&#160;4) C4130 | Microsoft Docs"
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
  - "C4130"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4130"
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4130
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : opération logique sur l’adresse d’une constante de chaîne  
  
 L’utilisation de l’opérateur avec l’adresse d’un littéral de chaîne génère du code inattendu.  
  
 L’exemple suivant génère l’avertissement C4130 :  
  
```  
// C4130.cpp // compile with: /W4 int main() { char *pc; pc = "Hello"; if (pc == "Hello") // C4130 { } }  
```  
  
 L’ instruction **If** compare la valeur stockée dans le pointeur `pc` à l’adresse de la chaîne « Hello », qui est allouée séparément à chaque occurrence de la chaîne dans le code. L’ instruction **If** ne compare pas la chaîne vers laquelle `pc` pointe avec la chaîne « Hello ».  
  
 Pour comparer des chaînes, utilisez la fonction `strcmp`.