---
title: "DeferrableEventArgs::InvokeAllFinished (méthode) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: acae8467ceeaaafea6668d4fbf6b5e2f4884b373
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="deferrableeventargsinvokeallfinished-method"></a>DeferrableEventArgs::InvokeAllFinished (méthode)
Appelé pour indiquer que le traitement d'un événement différé est terminé.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void InvokeAllFinished()  
```  
  
## <a name="remarks"></a>Remarques  
 Vous devez appeler cette méthode après les appels de source d’événement [InvokeAll](../windows/eventsource-invokeall-method.md). L'appel à cette méthode empêche tout autre report et force l'exécution du gestionnaire d'achèvement en l'absence de report.  
  
 Pour obtenir un exemple de code, consultez [deferrableeventargs, classe](../windows/deferrableeventargs-class.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Deferrableeventargs, classe](../windows/deferrableeventargs-class.md)   
 [EventSource::InvokeAll, méthode](../windows/eventsource-invokeall-method.md)