---
title: "Erreur du compilateur C2439 | Microsoft Docs"
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
  - "C2439"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2439"
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2439
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : impossible d'initialiser le membre  
  
 Un membre de classe, de structure ou d'union ne peut être initialisé.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Tentative d'initialisation d'une classe ou d'une structure de base indirecte.  
  
2.  Tentative d'initialisation d'un membre hérité d'une classe ou d'une structure.  Un membre hérité doit être initialisé par le constructeur de la classe ou de la structure.