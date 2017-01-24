---
title: "Avertissement du compilateur (niveau&#160;1) C4739 | Microsoft Docs"
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
  - "C4739"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4739"
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4739
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la référence à la variable ’var’ dépasse la taille de son espace de stockage  
  
 Une valeur a été assignée à une variable, mais la valeur est supérieure à la taille de la variable. La mémoire sera écrite au delà de l’emplacement de mémoire de la variable, et une perte de données est possible.  
  
 Pour résoudre cet avertissement, affectez une valeur uniquement à une variable dont la taille lui permet de contenir la valeur.  
  
 L’exemple suivant génère l’erreur C4739 :  
  
```  
// C4739.cpp // compile with: /RTCs /Zi /W1 /c char *pc; int main() { char c; *(int *)&c = 1;   // C4739 // OK *(char *)&c = 1; }  
```