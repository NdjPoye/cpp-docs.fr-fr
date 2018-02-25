---
title: CStreamRowset (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 817d9454ad97580cdfb3eb6d68fbc819ed64dd90
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cstreamrowset-class"></a>CStreamRowset, classe
Utilisé dans un `CCommand` ou `CTable` déclaration.  
  
## <a name="syntax"></a>Syntaxe

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### <a name="parameters"></a>Paramètres  
 `TAccessor`  
 Une classe d’accesseur.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|Constructeur. Instancie et initialise le `CStreamRowset` objet.|  
|[Fermer](../../data/oledb/cstreamrowset-close.md)|Versions du [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx) pointeur d’interface dans la classe.|  
  
## <a name="remarks"></a>Notes  
 Utilisez `CStreamRowset` dans votre `CCommand` ou `CTable` déclaration, par exemple :  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
 ou  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` Retourne un `ISequentialStream` pointeur, qui est stocké dans `m_spStream`. Vous utilisez ensuite le **en lecture** méthode pour récupérer les données (chaîne Unicode) au format XML. Exemple :  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 effectue la mise en forme XML et retourne toutes les colonnes et toutes les lignes de l’ensemble de lignes sous forme de chaîne XML.  
  
> [!NOTE]
>  Cette fonctionnalité fonctionne uniquement avec SQL Server 2000.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)