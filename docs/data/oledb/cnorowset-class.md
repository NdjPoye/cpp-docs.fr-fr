---
title: Cnorowset, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs:
- C++
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a509f93a72e1f48bc6af0e372f0353cdebb3edb8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cnorowset-class"></a>CNoRowset, classe
Peut être utilisé comme argument de modèle (`TRowset`) pour [CCommand](../../data/oledb/ccommand-class.md) ou [CTable](../../data/oledb/ctable-class.md).  
  
## <a name="syntax"></a>Syntaxe

```cpp
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### <a name="parameters"></a>Paramètres  
 `TAccessor`  
 Une classe d’accesseur. La valeur par défaut est `CAccessorBase`.  
  
## <a name="remarks"></a>Notes  
 Utilisez `CNoRowset` comme argument de modèle, si la commande ne renvoie pas un ensemble de lignes.  
  
 `CNoRowset` implémente les méthodes stub suivantes, chacune d’elles correspondent aux autres méthodes d’accesseur de classe :  
  
-   **BindFinished** -indique lorsque la liaison est terminée (retourne `S_OK`).  
  
-   **Fermer** -mises à jour de lignes et l’interface IRowset actuelle.  
  
-   `GetIID` -Récupère l’ID d’interface d’un point de connexion.  
  
-   **GetInterface** -extrait une interface.  
  
-   `GetInterfacePtr` -Récupère un pointeur d’interface encapsulé.  
  
-   **SetAccessor** -définit un pointeur vers l’accesseur.  
  
-   **SetupOptionalRowsetInterfaces** -définit les interfaces facultatives pour l’ensemble de lignes.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)