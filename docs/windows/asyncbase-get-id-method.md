---
title: "Asyncbase::get_id, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::get_Id
dev_langs: C++
helpviewer_keywords: get_Id method
ms.assetid: 591d8366-ea76-4deb-9278-9d3bc394a42b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f90a3b57f1691db67b6ba5a62704b91bd8e4eb7b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasegetid-method"></a>AsyncBase::get_Id, méthode
Récupère le handle de l’opération asynchrone.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHOD(  
   get_Id  
)(unsigned int *id) override;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `id`  
 L’emplacement où le handle doit être stocké.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK en cas de réussite ; dans le cas contraire, E_ILLEGAL_METHOD_CALL.  
  
## <a name="remarks"></a>Notes  
 Cette méthode implémente IAsyncInfo::get_Id.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** async.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)