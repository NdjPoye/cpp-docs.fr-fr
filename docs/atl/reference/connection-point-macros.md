---
title: Macros de Point de connexion | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
dev_langs: C++
helpviewer_keywords: connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 19eb60af9da72f3c158b9eacbfbfbdf478f1382d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="connection-point-macros"></a>Macros de Point de connexion
Ces macros définissent les mappages de point de connexion et les entrées.  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Marque le début des entrées de mappage de point de connexion.|  
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Entre les points de connexion dans la classe map.|  
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017) Similaire à CONNECTION_POINT_ENTRY mais prend un pointeur vers un iid.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Marque la fin des entrées de mappage de point de connexion.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h 
   
##  <a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP  
 Marque le début des entrées de mappage de point de connexion.  
  
```
BEGIN_CONNECTION_POINT_MAP(x)
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom de la classe contenant les points de connexion.  
  
### <a name="remarks"></a>Remarques  
 Démarrer votre mappage de point de connexion avec le `BEGIN_CONNECTION_POINT_MAP` (macro), ajouter des entrées pour chacun de vos points de connexion avec le [CONNECTION_POINT_ENTRY](#connection_point_entry) (macro) et effectuer un mappage avec le [END_CONNECTION_POINT_MAP](#end_connection_point_map) (macro).  
  
 Pour plus d’informations sur les points de connexion dans les ATL, consultez l’article [Points de connexion](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]  
  
##  <a name="connection_point_entry"></a>CONNECTION_POINT_ENTRY et CONNECTION_POINT_ENTRY_P  
 Ajoute un point de connexion pour l’interface spécifiée dans le mappage de point de connexion afin qu’il est accessible.  
  
```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface ajoutée à la carte de point de connexion. 
 
 `piid`  
 [in] Pointeur vers le GUID de l’interface en cours enregistrées.   
  
### <a name="remarks"></a>Remarques  
 Entrées de point de connexion de la table sont utilisées par [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md). La classe contenant le mappage de point de connexion doit hériter de `IConnectionPointContainerImpl`.  
  
 Démarrer votre mappage de point de connexion avec le [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) (macro), ajouter des entrées pour chacun de vos points de connexion avec le `CONNECTION_POINT_ENTRY` (macro) et effectuer un mappage avec le [END_CONNECTION_POINT_MAP ](#end_connection_point_map) (macro).  
  
 Pour plus d’informations sur les points de connexion dans les ATL, consultez l’article [Points de connexion](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]  
  
##  <a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP  
 Marque la fin des entrées de mappage de point de connexion.  
  
```
END_CONNECTION_POINT_MAP()
```  
  
### <a name="remarks"></a>Remarques  
 Démarrer votre mappage de point de connexion avec le [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) (macro), ajouter des entrées pour chacun de vos points de connexion avec le [CONNECTION_POINT_ENTRY](#connection_point_entry) (macro) et effectuer un mappage avec le `END_CONNECTION_POINT_MAP` (macro).  
  
 Pour plus d’informations sur les points de connexion dans les ATL, consultez l’article [Points de connexion](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)   
 [Fonctions globales de point de connexion](../../atl/reference/connection-point-global-functions.md)
