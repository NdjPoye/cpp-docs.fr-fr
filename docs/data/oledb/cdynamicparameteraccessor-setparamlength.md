---
title: CDynamicParameterAccessor::SetParamLength | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
dev_langs: C++
helpviewer_keywords: SetParamLength method
ms.assetid: d8e0bbfe-e1ae-4a8f-9567-584fbb0c8385
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9430ac2a250c41cafce7d8efc7b190625510aa62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorsetparamlength"></a>CDynamicParameterAccessor::SetParamLength
Définit la longueur du paramètre spécifié stocké en mémoire tampon.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool SetParamLength(  
   DBORDINAL nParam,  
   DBLENGTH length  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nParam`  
 [in] Le numéro de paramètre (offset à partir de 1). Le paramètre 0 est réservé pour les valeurs de retournés. Le paramètre est l’index du paramètre en fonction de son ordre dans le SQL ou d’un appel de procédure stockée. Consultez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour obtenir un exemple.  
  
 *length*  
 [in] La longueur en octets du paramètre spécifié.  
  
## <a name="remarks"></a>Notes  
 Retourne **true** en cas de réussite ou **false** en cas d’échec.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)