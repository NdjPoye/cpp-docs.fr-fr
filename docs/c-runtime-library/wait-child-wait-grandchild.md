---
title: _WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
dev_langs:
- C++
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1ac83e22e906a4e885860ec2254b2b732e31d38a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <process.h>  
  
```  
  
## <a name="remarks"></a>Notes  
 La fonction `_cwait` peut être utilisée par n’importe quel processus pour attendre un autre processus (si l’ID du processus est connu). L’argument action peut être une des valeurs suivantes :  
  
|Constante|Signification|  
|--------------|-------------|  
|`_WAIT_CHILD`|Le processus appelant attend jusqu'à l’arrêt du nouveau processus spécifié.|  
|`_WAIT_GRANDCHILD`|Le processus appelant attend jusqu'à l’arrêt du nouveau processus spécifié et de tous les processus qu’il crée.|  
  
## <a name="see-also"></a>Voir aussi  
 [_cwait](../c-runtime-library/reference/cwait.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)