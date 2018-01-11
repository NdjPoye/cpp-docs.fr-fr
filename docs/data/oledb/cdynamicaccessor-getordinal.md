---
title: CDynamicAccessor::GetOrdinal | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor.GetOrdinal
- ATL::CDynamicAccessor::GetOrdinal
- CDynamicAccessor::GetOrdinal
- ATL.CDynamicAccessor.GetOrdinal
- GetOrdinal
dev_langs: C++
helpviewer_keywords: GetOrdinal method
ms.assetid: 2095b71c-a7a4-4034-89a1-77a78cb9633f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b86ce9f5b27e7dc51cbebdbbd24b90dd9effa5fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorgetordinal"></a>CDynamicAccessor::GetOrdinal
Récupère le numéro de colonne donné un nom de colonne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool GetOrdinal(  
   const CHAR* pColumnName,  
   DBORDINAL* pOrdinal   
) const throw( );  
bool GetOrdinal(  
   const WCHAR* pColumnName,  
   DBORDINAL* pOrdinal   
) const throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pColumnName`  
 [in] Pointeur vers une chaîne de caractères contenant le nom de colonne.  
  
 *pOrdinal*  
 [out] Pointeur vers le numéro de colonne.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne **true** si une colonne portant le nom spécifié est trouvée. Sinon, cette fonction retourne **false**.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)