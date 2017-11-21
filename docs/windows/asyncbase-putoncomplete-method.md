---
title: "Asyncbase::putoncomplete, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::PutOnComplete
dev_langs: C++
helpviewer_keywords: PutOnComplete method
ms.assetid: 1c469ff9-b2df-4637-bf05-01a617043149
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6eeddf1f94d72407b90b9f99c4755b6e0a865ec5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbaseputoncomplete-method"></a>AsyncBase::PutOnComplete, méthode
Définit l’adresse du Gestionnaire d’événements de fin à la valeur spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHOD(  
   PutOnComplete  
)(TComplete* completeHandler);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `completeHandler`  
 L’adresse à laquelle le Gestionnaire d’événements de fin est défini.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK en cas de réussite ; dans le cas contraire, E_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** async.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)