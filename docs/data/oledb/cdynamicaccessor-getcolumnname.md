---
title: CDynamicAccessor::GetColumnName | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDynamicAccessor::GetColumnName
- GetColumnName
- ATL.CDynamicAccessor.GetColumnName
- CDynamicAccessor::GetColumnName
- CDynamicAccessor.GetColumnName
dev_langs: C++
helpviewer_keywords: GetColumnName method
ms.assetid: 96a7452a-1f5b-41e9-ab37-88dac026f961
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9b8c48e7a33d413b494d662c4354c2aeb60b5f53
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorgetcolumnname"></a>CDynamicAccessor::GetColumnName
Récupère le nom de la colonne spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      LPOLESTR GetColumnName(   
   DBORDINAL nColumn    
) const throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nColumn`  
 [in] Le numéro de colonne. Les numéros de colonne commencent à 1. La valeur 0 fait référence à la colonne de signet, le cas échéant.  
  
## <a name="return-value"></a>Valeur de retour  
 Nom de la colonne spécifiée.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)