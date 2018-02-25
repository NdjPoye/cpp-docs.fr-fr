---
title: CSession::Close | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: dc36c4c0-e588-4c0b-91d1-fc7dc5c8e7f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bfe56cbcd6403cf6e809a963d75774d1802c80e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="csessionclose"></a>CSession::Close
Ferme la session, ce qui a été ouverte en [CSession::Open](../../data/oledb/csession-open.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
void Close() throw();  
  
```  
  
## <a name="remarks"></a>Notes  
 Versions du **m_spOpenRowset** pointeur.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CSession, classe](../../data/oledb/csession-class.md)