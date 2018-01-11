---
title: IRowsetImpl::m_bReset | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
dev_langs: C++
helpviewer_keywords: m_bReset
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4cd9840b37157aed050bb71d48a275efd2849035
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplmbreset"></a>IRowsetImpl::m_bReset
Un indicateur de bit utilisé pour déterminer si la position du curseur est définie sur l’ensemble de lignes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
unsigned m_bReset:1;  
  
```  
  
## <a name="remarks"></a>Notes  
 Si le consommateur appelle [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) avec une valeur négative `lOffset` ou *cRows* et `m_bReset` a la valeur true, `GetNextRows` se déplace vers la fin de l’ensemble de lignes. Si `m_bReset` a la valeur false, le consommateur reçoit un code d’erreur, conformément à la spécification OLE DB. Le `m_bReset` indicateur obtient la valeur **true** lors de la première création de l’ensemble de lignes et lorsque le consommateur appelle [IRowsetImpl::RestartPosition](../../data/oledb/irowsetimpl-restartposition.md). Elle obtient la valeur **false** lorsque vous appelez `GetNextRows`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)