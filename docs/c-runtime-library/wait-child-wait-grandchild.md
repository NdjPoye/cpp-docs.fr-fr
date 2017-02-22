---
title: "_WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_WAIT_GRANDCHILD"
  - "WAIT_CHILD"
  - "WAIT_GRANDCHILD"
  - "_WAIT_CHILD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_WAIT_CHILD (constante)"
  - "_WAIT_GRANDCHILD (constante)"
  - "WAIT_CHILD (constante)"
  - "WAIT_GRANDCHILD (constante)"
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _WAIT_CHILD, _WAIT_GRANDCHILD
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <process.h>  
  
```  
  
## Notes  
 La fonction `_cwait` peut être utilisée par tout processus pour attendre tout autre processus \(si l'ID de processus est connu\).  L'argument d'action peut être l'une des valeurs suivantes :  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_WAIT_CHILD`|Le processus appelant attend jusqu'à ce que le nouveau processus spécifié se termine.|  
|`_WAIT_GRANDCHILD`|Le processus appelant attend jusqu'à ce que le nouveau processus spécifié, et tous les processus créés par ce nouveau processus, se terminent.|  
  
## Voir aussi  
 [\_cwait](../c-runtime-library/reference/cwait.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)