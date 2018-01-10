---
title: CDataConnection::operator BOOL | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
dev_langs: C++
helpviewer_keywords:
- BOOL operator
- operator bool
ms.assetid: ad0bea7f-61ff-47f7-8127-32a31e3e9b9d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 342a8074f61a6f05505534ff497010b8a752293c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdataconnectionoperator-bool"></a>CDataConnection::operator BOOL
Détermine si la session active est ouverte ou non.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
operator BOOL( ) throw( );  
  
```  
  
## <a name="remarks"></a>Notes  
 Retourne **BOOL** (MFC typedef) valeur. **TRUE** signifie que la session active est ouverte ; **FALSE** signifie que la session active est fermée.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataConnection (classe)](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)