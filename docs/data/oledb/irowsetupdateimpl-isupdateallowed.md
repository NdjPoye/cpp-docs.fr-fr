---
title: IRowsetUpdateImpl::IsUpdateAllowed | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs: C++
helpviewer_keywords: IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 312d0488afc73d38ebd1ceb8a3f4334468607ed9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
Substituez cette méthode pour contrôler la sécurité, l’intégrité, et ainsi de suite avant les mises à jour.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT IsUpdateAllowed(  
   DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *status*  
 [in] L’état des opérations sur les lignes en attente.  
  
 *hRowUpdate*  
 [in] Handle pour les lignes que l’utilisateur veut mettre à jour.  
  
 *pRowStatus*  
 [out] L’état renvoyé à l’utilisateur.  
  
## <a name="remarks"></a>Notes  
 Si vous déterminez qu’une mise à jour doit être autorisé, retourne `S_OK`; sinon, retourne **E_FAIL**. Si vous autorisez une mise à jour, vous devez également définir le **DBROWSTATUS** dans [IRowsetUpdateImpl::Update](../../data/oledb/irowsetupdateimpl-update.md) aux [état de la ligne](https://msdn.microsoft.com/en-us/library/ms722752.aspx).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetUpdateImpl, classe](../../data/oledb/irowsetupdateimpl-class.md)