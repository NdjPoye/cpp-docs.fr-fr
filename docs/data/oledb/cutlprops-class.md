---
title: CUtlProps, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUtlProps
dev_langs:
- C++
helpviewer_keywords:
- CUtlProps class
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8c8aa99a4ad1642ea14b85e3e68f00a68c005bb4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cutlprops-class"></a>CUtlProps, classe
Implémente des propriétés pour un large éventail d’interfaces de propriété OLE DB (par exemple, `IDBProperties`, `IDBProperties`, et `IRowsetInfo`).  
  
## <a name="syntax"></a>Syntaxe

```cpp
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 La classe qui contient la `BEGIN_PROPSET_MAP`.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)|Obtient une propriété à partir d’un jeu de propriétés.|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|Permet de valider une valeur avant de définir une propriété.|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|Gère les demandes d’une interface facultative lorsqu’un consommateur appelle une méthode sur une interface de création d’objet.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|Appelé après la définition d’une propriété de gérer des propriétés chaînées.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|Définit une propriété dans un jeu de propriétés.|  
  
## <a name="remarks"></a>Notes  
 La plupart de cette classe est un détail d’implémentation.  
  
 `CUtlProps` contient deux membres pour définir les propriétés en interne : [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) et [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 Pour plus d’informations sur les macros utilisées dans un mappage de jeu de propriétés, consultez [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) et [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)