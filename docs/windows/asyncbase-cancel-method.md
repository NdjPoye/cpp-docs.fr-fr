---
title: "Asyncbase::Cancel, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::Cancel
dev_langs: C++
helpviewer_keywords: Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b6215c871da92087a7555bfb5a97f48d60223de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasecancel-method"></a>AsyncBase::Cancel, méthode
Annule une opération asynchrone.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Par défaut, retourne toujours S_OK.  
  
## <a name="remarks"></a>Notes  
 Cancel() est une implémentation par défaut de IAsyncInfo::Cancel et n’effectue aucun travail réel. Pour réellement annuler une opération asynchrone, substituez la méthode virtuelle pure de OnCancel().  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** async.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)