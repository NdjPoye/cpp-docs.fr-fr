---
title: "FpCsr | Microsoft Docs"
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
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# FpCsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'état du registre inclut également le mot de commande FPUx87.  La convention d'appel définit ce registre comme non volatil.  
  
 Le registre du mot de commande FPU x87 possède les valeurs standard suivantes au démarrage de l'exécution du programme :  
  
```  
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)  
FPCSR[7]: Reserved – 0  
FPCSR[8:9]: Precision Control – 10B (double precision)  
FPCSR[10:11]: Rounding  control - 0 (round to nearest)  
FPCSR[12]: Infinity control – 0 (not used)  
```  
  
 Un appelé qui modifie l'un des champs dans FPCSR doit les restaurer avant de retourner à son appelant.  En outre, un appelant qui a modifié l'un de ces champs doit rétablir leur valeur standard avant d'appeler un appelé, à moins que, selon les termes d'un contrat, l'appelé attende les valeurs modifiées.  
  
 Il existe deux exceptions aux règles relatives à la rémanence des indicateurs de contrôle :  
  
1.  dans les fonctions dont l'objectif documenté consiste à modifier les indicateurs MxFpCsrCsr non volatils ;  
  
2.  lorsqu'il peut être prouvé que la violation des résultats de ces règles dans un programme qui se comporte de la même manière ou a la même signification qu'un programme où ces règles ne sont pas enfreintes \(par exemple, par le biais d'une analyse de l'intégralité d'un programme\).  
  
## Voir aussi  
 [Convention d'appel](../build/calling-convention.md)