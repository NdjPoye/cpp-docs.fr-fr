---
title: CEnumerator::Open | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: b22821a0-257a-4543-ad0c-2649d4ac092e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3a5c35b3806e04f20417c7053248d1a098456403
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cenumeratoropen"></a>CEnumerator::Open
Lie le moniker de l’énumérateur, si un est spécifié, puis récupère l’ensemble de lignes de l’énumérateur en appelant [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/en-us/library/ms711200.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT Open(   
   LPMONIKER pMoniker    
) throw( );  
HRESULT Open(   
   const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR    
) throw( );  
HRESULT Open(   
   const CEnumerator& enumerator    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pMoniker`  
 [in] Pointeur vers un moniker pour un énumérateur.  
  
 *pClsid*  
 [in] Un pointeur vers le **CLSID** d’un énumérateur.  
  
 `enumerator`  
 [in] Une référence à un énumérateur.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CEnumerator, classe](../../data/oledb/cenumerator-class.md)