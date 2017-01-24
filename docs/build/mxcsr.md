---
title: "MxCsr | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MxCsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'état du registre inclut également MxCsr.  La convention d'appel divise ce registre en une partie volatile et une partie non volatile.  La partie volatile se compose des 6 indicateurs d'état, MXCSR \[0:5\], alors que le reste du registre, MXCSR \[6:15\], est considéré non volatil.  
  
 La partie non volatile possède les valeurs standard suivantes au démarrage de l'exécution du programme :  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 Un appelé qui modifie l'un des champs non volatils dans MXCSR doit les restaurer avant de retourner à son appelant.  En outre, un appelant qui a modifié l'un de ces champs doit rétablir leur valeur standard avant d'appeler un appelé, à moins que, selon les termes d'un contrat, l'appelé attende les valeurs modifiées.  
  
 Il existe deux exceptions aux règles relatives à la rémanence des indicateurs de contrôle :  
  
-   dans les fonctions dont l'objectif documenté consiste à modifier les indicateurs MxCsr non volatils ;  
  
-   lorsqu'il peut être prouvé que la violation des résultats de ces règles dans un programme qui se comporte de la même manière ou a la même signification qu'un programme où ces règles ne sont pas enfreintes \(par exemple, par le biais d'une analyse de l'intégralité d'un programme\).  
  
 aucune supposition ne peut être faite à propos de l'état de la partie volatile de MXCSR au\-delà de la limite d'une fonction, sauf spécification contraire dans la documentation de celle\-ci.  
  
## Voir aussi  
 [Convention d'appel](../build/calling-convention.md)