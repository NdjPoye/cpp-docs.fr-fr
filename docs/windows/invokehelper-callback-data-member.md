---
title: "InvokeHelper::callback, membre de données | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::InvokeHelper::callback_
dev_langs: C++
helpviewer_keywords: callback_ data member
ms.assetid: 6f0cbf6d-0448-46f8-ba71-bd6fd8702e3a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6fc6f6876bffbad693d05c4f1154df2dbba77811
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="invokehelpercallback-data-member"></a>InvokeHelper::callback_, donnée de membre
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
TCallback callback_;  
```  
  
## <a name="remarks"></a>Remarques  
 Représente un gestionnaire d’événements à appeler lorsqu’un événement se produit.  
  
 Le `TCallback` paramètre de modèle spécifie le type du Gestionnaire d’événements.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [InvokeHelper (Structure)](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)