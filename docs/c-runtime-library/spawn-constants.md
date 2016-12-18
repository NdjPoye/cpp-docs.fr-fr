---
title: "spawn, constantes | Microsoft Docs"
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
  - "_P_NOWAIT"
  - "_P_OVERLAY"
  - "_P_WAIT"
  - "_P_DETACH"
  - "_P_NOWAITO"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_P_DETACH (constante)"
  - "_P_NOWAIT (constante)"
  - "_P_NOWAITO (constante)"
  - "_P_OVERLAY (constante)"
  - "_P_WAIT (constante)"
  - "P_DETACH (constante)"
  - "P_NOWAIT (constante)"
  - "P_NOWAITO (constante)"
  - "P_OVERLAY (constante)"
  - "P_WAIT (constante)"
  - "spawn (constantes)"
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# spawn, constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
#include <process.h>  
```  
  
## Notes  
 L'argument `mode` détermine l'action entreprise par le processus appelant avant et pendant une opération de création.  Les valeurs suivantes pour `mode` sont possibles :  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_P_OVERLAY`|Recouvre un processus appellant par un nouveau processus, détruisant le processus appelant \(le même effet que des appels à`_exec` \).|  
|`_P_WAIT`|Interrompt un thread appelant jusqu'à ce que l'exécution du nouveau processus soit terminée \(`_spawn`synchrone\).|  
|`_P_NOWAIT`, `_P_NOWAITO`|Continue d'exécuter un processus appelant en même temps que le nouveau processus \( `_spawn`asynchrones\).|  
|`_P_DETACH`|Continue d'exécuter le processus appelant ; le nouveau processus est exécuté en arrière\-plan sans accès à la console ou au clavier.  Les appels à `_cwait` sur le nouveau processus échoueront.  Il s'agit d'un `_spawn` asynchrone.|  
  
## Voir aussi  
 [\_spawn, \_wspawn, fonctions](../c-runtime-library/spawn-wspawn-functions.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)