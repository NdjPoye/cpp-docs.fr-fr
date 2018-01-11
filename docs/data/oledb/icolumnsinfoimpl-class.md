---
title: Icolumnsinfoimpl, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
dev_langs: C++
helpviewer_keywords: IColumnsInfoImpl class
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18d23120a4a84f9d637a50e379a579389354ff08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl, classe
Fournit une implémentation de la [IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) interface.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IColumnsInfoImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/icolumnsinfoimpl-getcolumninfo.md)|Retourne les métadonnées de colonne requises par la plupart des consommateurs.|  
|[MapColumnIDs](../../data/oledb/icolumnsinfoimpl-mapcolumnids.md)|Retourne un tableau d’ordinaux des colonnes dans un ensemble de lignes qui sont identifiés par l’ID de colonne spécifié.|  
  
## <a name="remarks"></a>Notes  
 Une interface obligatoire sur les commandes et les ensembles de lignes. Pour modifier le comportement de votre fournisseur de `IColumnsInfo` mise en œuvre, vous devez modifier le mappage de colonnes du fournisseur.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)