---
title: CRowset::GetApproximatePosition | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRowset::GetApproximatePosition
- ATL::CRowset<TAccessor>::GetApproximatePosition
- CRowset.GetApproximatePosition
- CRowset::GetApproximatePosition
- GetApproximatePosition
- ATL.CRowset.GetApproximatePosition
- CRowset<TAccessor>::GetApproximatePosition
dev_langs:
- C++
helpviewer_keywords:
- GetApproximatePosition method
ms.assetid: 8f9ccd41-0590-468e-b202-6731d0f99d21
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 07d0f816579fb7097389d676e241143d4891677d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetgetapproximateposition"></a>CRowset::GetApproximatePosition
Retourne la position approximative d’une ligne correspondant à un signet.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetApproximatePosition(const CBookmarkBase* pBookmark,   
   DBCOUNTITEM* pPosition,   
   DBCOUNTITEM* pcRows) throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pBookmark`  
 [in] Pointeur vers un signet qui identifie la ligne dont la position doit être trouvé. **NULL** si seul le nombre de lignes est requis.  
  
 *pPosition*  
 [out] Un pointeur vers l’emplacement où `GetApproximatePosition` retourne la position de la ligne. **NULL** si la position n’est pas nécessaire.  
  
 `pcRows`  
 [out] Un pointeur vers l’emplacement où `GetApproximatePosition` retourne le nombre total de lignes. **NULL** si le nombre de lignes n’est pas nécessaire.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Cette méthode requiert l’interface facultative `IRowsetScroll`, qui ne peut pas être pris en charge sur tous les fournisseurs ; si c’est le cas, la méthode retourne **E_NOINTERFACE**. Vous devez également définir **DBPROP_IRowsetScroll** à `VARIANT_TRUE` avant d’appeler **ouvrir** sur la table ou d’une commande qui contient l’ensemble de lignes.  
  
 Pour plus d’informations sur l’utilisation de signets dans des consommateurs, consultez [à l’aide de signets](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset (classe)](../../data/oledb/crowset-class.md)   
 [IRowsetScroll::GetApproximatePosition](https://msdn.microsoft.com/en-us/library/ms712901.aspx)