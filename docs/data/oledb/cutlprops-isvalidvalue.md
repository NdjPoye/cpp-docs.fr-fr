---
title: CUtlProps::IsValidValue | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
dev_langs:
- C++
helpviewer_keywords:
- IsValidValue method
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bd02ef7c27926b2be99ed900b82d53c77d8d6dd0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cutlpropsisvalidvalue"></a>CUtlProps::IsValidValue
Permet de valider une valeur avant de définir une propriété.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
      virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `iCurSet`  
 L’index dans le tableau de jeu de propriétés ; zéro s’il existe une seule propriété ensemble.  
  
 `pDBProp`  
 L’ID de propriété et la nouvelle valeur dans un [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) structure.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard. La valeur par défaut valeur de retour est `S_OK`.  
  
## <a name="remarks"></a>Notes  
 Si vous avez des routines de validation à exécuter sur une valeur que vous allez utiliser pour définir une propriété, vous devez substituer cette fonction. Par exemple, vous pourriez valider **DBPROP_AUTH_PASSWORD** sur une table de mot de passe pour déterminer une valeur valide.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [CUtlProps, classe](../../data/oledb/cutlprops-class.md)