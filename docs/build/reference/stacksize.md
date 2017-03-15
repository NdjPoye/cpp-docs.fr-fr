---
title: "STACKSIZE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "STACKSIZE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STACKSIZE (instruction de fichier .def)"
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# STACKSIZE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit la taille de la pile en octets.  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## Notes  
 Vous pouvez définir la pile d'une manière équivalente à l'aide de l'option [Allocations de la pile](../../build/reference/stack-stack-allocations.md) \(\/STACK\).  Consultez la documentation relative à cette option pour plus de détails sur les arguments *reserve* et `commit`.  
  
 Cette option ne produit aucun effet sur les DLL.  
  
## Voir aussi  
 [Règles s'appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)