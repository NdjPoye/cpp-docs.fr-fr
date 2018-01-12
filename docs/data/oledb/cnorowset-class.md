---
title: Cnorowset, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs: C++
helpviewer_keywords: CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 901d857b5095dd882a368b9a87e8a7d38d20bc42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cnorowset-class"></a>CNoRowset, classe
Peut être utilisé comme argument de modèle (`TRowset`) pour [CCommand](../../data/oledb/ccommand-class.md) ou [CTable](../../data/oledb/ctable-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### <a name="parameters"></a>Paramètres  
 `TAccessor`  
 Une classe d’accesseur. La valeur par défaut est `CAccessorBase`.  
  
## <a name="remarks"></a>Notes  
 Utilisez `CNoRowset` comme argument de modèle, si la commande ne renvoie pas un ensemble de lignes.  
  
 `CNoRowset`implémente les méthodes stub suivantes, chacune d’elles correspondent aux autres méthodes d’accesseur de classe :  
  
-   **BindFinished** -indique lorsque la liaison est terminée (retourne `S_OK`).  
  
-   **Fermer** -mises à jour de lignes et l’interface IRowset actuelle.  
  
-   `GetIID`-Récupère l’ID d’interface d’un point de connexion.  
  
-   **GetInterface** -extrait une interface.  
  
-   `GetInterfacePtr`-Récupère un pointeur d’interface encapsulé.  
  
-   **SetAccessor** -définit un pointeur vers l’accesseur.  
  
-   **SetupOptionalRowsetInterfaces** -définit les interfaces facultatives pour l’ensemble de lignes.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)