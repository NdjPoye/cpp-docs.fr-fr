---
title: IRowsetCreatorImpl, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetCreatorImpl class
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51d984f2254c8a2a135b5ecb386e8f195946366b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl, classe
Exécute les mêmes fonctions que `IObjectWithSite` mais permet également de propriétés OLE DB **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**.  
  
## <a name="syntax"></a>Syntaxe

```cpp
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Une classe dérivée de **IRowsetCreator**.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|Définit le site qui contient l’objet d’ensemble de lignes.|  
  
## <a name="remarks"></a>Notes  
 Cette classe hérite de [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) et remplacements [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). Lorsqu’un objet de commande ou de la session du fournisseur crée un ensemble de lignes, il appelle `QueryInterface` sur l’objet d’ensemble de lignes recherchez `IObjectWithSite` et appelle `SetSite` en passant l’objet de l’ensemble de lignes **IUnkown** interface en tant que l’interface du site.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)