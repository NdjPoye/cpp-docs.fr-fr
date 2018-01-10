---
title: "Asyncbase::Close, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35b7fda0ab10ff80df0f4a27f6e79028e73574fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbaseclose-method"></a>AsyncBase::Close, méthode
Ferme l’opération asynchrone.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération se termine ou est déjà fermé ; dans le cas contraire, E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Notes  
 Close() est une implémentation par défaut de IAsyncInfo::Close et n’effectue aucun travail réel. Pour réellement fermer une opération asynchrone, substituez la méthode virtuelle pure de OnClose().  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** async.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)