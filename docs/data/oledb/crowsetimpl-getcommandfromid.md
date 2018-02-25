---
title: CRowsetImpl::GetCommandFromID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
dev_langs:
- C++
helpviewer_keywords:
- GetCommandFromID method
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8f58da41c878fba322d51bdecd8283646a94bdf2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplgetcommandfromid"></a>CRowsetImpl::GetCommandFromID
Vérifie si un ou les deux paramètres contiennent des valeurs de chaîne et dans ce cas, copie les valeurs de chaîne dans les données membres [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pTableID`  
 [in] Un pointeur vers le **DBID** représentant l’ID de Table.  
  
 `pIndexID`  
 [in] Un pointeur vers le **DBID** représentant l’ID d’Index.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Cette méthode est appelée via un upcast statique par `CRowsetImpl` pour remplir les données membres [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). Par défaut, cette méthode vérifie si un ou les deux paramètres contiennent des valeurs de chaîne. S’ils contiennent des valeurs de chaîne, cette méthode copie les valeurs de chaîne pour les membres de données. En plaçant une méthode avec cette signature dans votre `CRowsetImpl`-classe dérivée, votre méthode sera appelée au lieu de l’implémentation de base.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowsetImpl, classe](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)