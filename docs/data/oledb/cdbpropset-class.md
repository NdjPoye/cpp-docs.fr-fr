---
title: CDBPropSet, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 716b0785ba4f785063709d989eb95c5c4f390f4a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdbpropset-class"></a>CDBPropSet, classe
Hérite de la **DBPROPSET** structurer et ajoute un constructeur qui initialise les champs clés, ainsi que les `AddProperty` accéder à la méthode.  
  
## <a name="syntax"></a>Syntaxe

```cpp
class CDBPropSet : public tagDBPROPSET  
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|Ajoute une propriété au jeu de propriétés.|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|Constructeur.|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|Définit le **guidPropertySet** champ le **DBPROPSET** structure.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator =](../../data/oledb/cdbpropset-operator-equal.md)|Assigne le contenu d’une propriété définie sur un autre.|  
  
## <a name="remarks"></a>Notes  
 Utilisation de fournisseurs et consommateurs OLE DB **DBPROPSET** pour passer des tableaux de structures `DBPROP` structures. Chaque `DBPROP` structure représente une seule propriété peut être définie.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles de consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CDBPropIDSet (classe)](../../data/oledb/cdbpropidset-class.md)   
 [Structure DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [Structure DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)