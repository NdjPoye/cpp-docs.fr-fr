---
title: IErrorRecordsImpl::GetErrorSource | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
dev_langs: C++
helpviewer_keywords: GetErrorSource method
ms.assetid: 5436f1ce-c5a4-403b-a62b-c58e70e5c925
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 312b8e28201447def0f09da9bcefc4a78e15d8ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ierrorrecordsimplgeterrorsource"></a>IErrorRecordsImpl::GetErrorSource
Obtient le code source qui a provoqué l’erreur à partir d’un enregistrement d’erreur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      LPOLESTR GetErrorSource(  
   ERRORINFO& rCurError   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `rCurError`  
 Un `ERRORINFO` enregistrement dans un **IErrorInfo** interface.  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur vers une chaîne contenant le code source de l’erreur.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IErrorRecordsImpl, classe](../../data/oledb/ierrorrecordsimpl-class.md)