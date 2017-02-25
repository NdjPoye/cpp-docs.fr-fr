---
title: "operator . | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "operator ."
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dot operator (.)"
  - "operator ."
  - ". operator"
ms.assetid: 468ea0c8-5b08-47be-991b-38abacb77611
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# operator .
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le premier opérateur retourne *l'expression* avec l'offset *du champ* dans leur structure ou union.  La deuxième valeur de retour d'opérateur à l'emplacement indiquée par *le registre* avec l'offset *du champ* dans leur structure ou union.  
  
## Syntaxe  
  
```  
  
      expression  
      . field [[. field]]...  
[register]. field [[. field]]...  
```  
  
## Voir aussi  
 [Operators Reference](../../assembler/masm/operators-reference.md)