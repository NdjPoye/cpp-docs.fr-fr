---
title: "abort, fonction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort (fonction)"
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# abort, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fonction **abort**, déclarée également dans le fichier Include standard STDLIB.H, arrête un programme C\+\+.  La différence entre **exit** et **abort** est que **exit** permet au processus d'arrêt du runtime C\+\+ d'avoir lieu \(les destructeurs d'objets globaux seront appelés\), alors que **abort** arrête le programme immédiatement.  Pour plus d'informations, consultez [abort](../c-runtime-library/reference/abort.md) dans la *Référence de la bibliothèque runtime*.  
  
## Voir aussi  
 [Terminaison du programme](../cpp/program-termination.md)