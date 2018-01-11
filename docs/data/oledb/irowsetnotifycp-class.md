---
title: IRowsetNotifyCP, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IRowsetNotifyCP
dev_langs: C++
helpviewer_keywords: IRowsetNotifyCP class
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bae872c90a6df76e3efc1fce1aab6e77bc8fd313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP, classe
Implémente le site du fournisseur pour l’interface de point de connexion [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   class T,   
   class ReentrantEventSync = CComSharedMutex   
>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray  
   >,  
   public ReentrantEventSync  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Une classe dérivée de `IRowsetNotifyCP`.  
  
 `ReentrantEventSync`  
 Une mutex (classe) qui prend en charge la réentrance (la valeur par défaut est **CComSharedMutex**). Un mutex est un objet de synchronisation qui permet à un thread l’accès mutuellement exclusif à une ressource.  
  
 `piid`  
 Un pointeur d’interface ID (**IID\***) pour un **IRowsetNotify** interface point de connexion. La valeur par défaut est **& __uuidof(IRowsetNotify)**.  
  
 `DynamicUnkArray`  
 Un tableau de type [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), qui est un tableau alloué dynamiquement de **IUnknown** interfaces de récepteur des pointeurs vers le client.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[Fire_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|Notifie le consommateur d’une modification à la valeur d’une colonne.|  
|[Fire_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|Notifie le consommateur d’une modification qui affectent les lignes.|  
|[Fire_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|Notifie le consommateur d’une modification affectant l’ensemble de lignes.|  
  
## <a name="remarks"></a>Notes  
 `IRowsetNotifyCP`implémente des fonctions pour informer les écouteurs sur le point de connexion de diffusion **IID_IRowsetNotify** des modifications apportées au contenu de l’ensemble de lignes.  
  
 Notez que vous devez également implémenter et inscrire `IRowsetNotify` sur le consommateur (également appelé « récepteur ») à l’aide de [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) afin que le consommateur puisse gérer les notifications. Consultez [réception des Notifications](../../data/oledb/receiving-notifications.md) sur l’implémentation de l’interface de point de connexion sur le consommateur.  
  
 Pour plus d’informations sur l’implémentation des notifications, consultez « Prise en charge des Notifications » dans [création d’un fournisseur actualisable](../../data/oledb/creating-an-updatable-provider.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Notifications (COM)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)   
 [END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)   
 [CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)   
 [Création d’un fournisseur actualisable](../../data/oledb/creating-an-updatable-provider.md)