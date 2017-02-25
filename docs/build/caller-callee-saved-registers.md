---
title: "Registres enregistr&#233;s des appelants/appel&#233;s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Registres enregistr&#233;s des appelants/appel&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les registres RAX, RCX, RDX, R8, R9, R10, R11 sont considérés comme volatils et on doit estimer qu'ils sont détruits sur les appels de fonction \(sauf si leur sécurité peut être prouvée par une analyse telle que l'optimisation de l'intégralité d'un programme\).  
  
 Les registres RBX, RBP, RDI, RSI, RSP, R12, R13, R14 et R15 sont considérés comme non volatiles et doivent être enregistrés et restaurés par une fonction qui les utilise.  
  
## Voir aussi  
 [Convention d'appel](../build/calling-convention.md)