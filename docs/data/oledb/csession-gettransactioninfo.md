---
title: CSession::GetTransactionInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
dev_langs: C++
helpviewer_keywords: GetTransactionInfo method
ms.assetid: 9fa62808-3162-4b5a-8610-e1abb8cf9a71
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8dd9c6d945fc838d787c19e776194261c40d32bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="csessiongettransactioninfo"></a>CSession::GetTransactionInfo
Retourne des informations relatives à une transaction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT GetTransactionInfo(   
   XACTTRANSINFO* pInfo    
) const throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/en-us/library/ms714975.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/en-us/library/ms714975.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CSession, classe](../../data/oledb/csession-class.md)