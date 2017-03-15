---
title: "Erreur du compilateur C3285 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3285"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3285"
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3285
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une instruction for each ne peut pas fonctionner sur des variables de type 'type'  
  
 L’instruction `for each` répète un groupe d’instructions incorporées pour chaque élément d’un tableau ou d’une collection d’objets.  
  
 Pour plus d'informations, voir [for each, in](../../dotnet/for-each-in.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3285.  
  
```  
// C3285.cpp // compile with: /clr int main() { for each (int i in 0) {}   // C3285 array<int> ^p = { 1, 2, 3 }; for each (int j in p) {}   // OK }  
```