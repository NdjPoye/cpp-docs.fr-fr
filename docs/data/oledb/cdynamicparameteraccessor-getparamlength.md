---
title: CDynamicParameterAccessor::GetParamLength | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
dev_langs: C++
helpviewer_keywords: GetParamLength method
ms.assetid: 04d76931-911a-4915-9c2c-ad585a9f3854
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1fe89c4734102cbd9f5928642092f2bca41db0dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorgetparamlength"></a>CDynamicParameterAccessor::GetParamLength
Récupère la longueur du paramètre spécifié stocké en mémoire tampon.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool GetParamLength(  
   DBORDINAL nParam,  
   DBLENGTH* pLength  
);  
DBLENGTH* GetParamLength(   
   DBORDINAL nParam    
) const throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nParam`  
 [in] Le numéro de paramètre (offset à partir de 1). Le paramètre 0 est réservé pour les valeurs de retournés. Le paramètre est l’index du paramètre en fonction de son ordre dans le SQL ou d’un appel de procédure stockée. Consultez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour obtenir un exemple.  
  
 `pLength`  
 [out] Pointeur vers la variable qui contient la longueur en octets du paramètre spécifié.  
  
## <a name="remarks"></a>Notes  
 La première supplante **true** en cas de réussite ou **false** en cas d’échec. La seconde remplacer pointe vers la mémoire qui contient la longueur du paramètre.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)