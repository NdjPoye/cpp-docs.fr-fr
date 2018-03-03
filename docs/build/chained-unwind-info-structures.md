---
title: "Chaînés Structures d’informations de déroulement | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ac09c1f107b51542b7a17c8661eb784b4abf14a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="chained-unwind-info-structures"></a>Structures d'informations de déroulement chaînées
Si l’indicateur UNW_FLAG_CHAININFO est défini, une structure d’informations de déroulement est secondaire, et le champ adresse exception-Gestionnaire/informations chaînées partagée contient les informations de déroulement principales. Le code suivant extrait le réplica principal informations de déroulement, en supposant que `unwindInfo` est la structure qui a le UNW_FLAG_CHAININFO l’indicateur.  
  
```  
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);  
```  
  
 Informations chaînées sont utile dans deux situations. Tout d’abord, il peut être utilisé pour les segments de code non contigus. À l’aide des informations chaînées, vous pouvez réduire la taille des informations de déroulement requises, car vous ne disposez pas de dupliquer le tableau de codes de déroulement à partir des informations de déroulement principales.  
  
 Vous pouvez également utiliser des informations chaînées pour regrouper les registres volatils. Le compilateur peut différer de l’enregistrement des registres volatils jusqu'à ce qu’il se trouve en dehors du prologue d’entrée de fonction. Vous pouvez l’enregistrer en ayant des informations de déroulement principales pour la partie de la fonction avant le code groupé, puis le paramétrage des informations chaînées avec une taille différente de zéro du prologue, où les codes de déroulement dans les informations chaînées reflètent les enregistrements des registres non volatils. Dans ce cas, les codes de déroulement sont toutes les instances de UWOP_SAVE_NONVOL. Un regroupement qui enregistre des registres non volatils à l’aide d’un PUSH ou modifie le registre RSP à l’aide d’une allocation de pile fixe supplémentaire n’est pas pris en charge.  
  
 Un élément UNWIND_INFO dont UNW_FLAG_CHAININFO définie peut contenir une entrée RUNTIME_FUNCTION dont l’élément UNWIND_INFO possède également un UNW_FLAG_CHAININFO défini (plusieurs emballages). Finalement, les informations de déroulement chaînées pointeurs arriveront à un élément UNWIND_INFO avec UNW_FLAG_CHAININFO désactivée ; Il s’agit de l’élément UNWIND_INFO principal pointant vers le point d’entrée de procédure réel.  
  
## <a name="see-also"></a>Voir aussi  
 [Données de déroulement pour la gestion des exceptions et la prise en charge du débogueur](../build/unwind-data-for-exception-handling-debugger-support.md)