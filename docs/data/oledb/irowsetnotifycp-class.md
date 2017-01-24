---
title: "IRowsetNotifyCP, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetNotifyCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetNotifyCP (classe)"
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetNotifyCP, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente le site de fournisseur pour l'interface de point de connexion [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `T`  
 Une classe dérivée de `IRowsetNotifyCP`.  
  
 `ReentrantEventSync`  
 Une classe d'exclusion mutuelle qui prend en charge la réentrée \(la valeur par défaut est **CComSharedMutex**\).  Un mutex est un objet de synchronisation qui permet à un thread l'accès mutuellement exclusif à une ressource.  
  
 `piid`  
 Un pointeur d'ID d'interface \(**IID\***\) pour une interface de délai de connexion **IRowsetNotify** .  La valeur par défaut est **&\_\_uuidof\(IRowsetNotify\)**.  
  
 `DynamicUnkArray`  
 Un tableau de type [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) qui est un tableau dynamique alloué de pointeurs **IUnknown** aux interfaces de récepteur du client.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Fire\_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|Notifie le consommateur d'une modification apportée à la valeur d'une colonne.|  
|[Fire\_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|Notifie le consommateur d'une modification qui affecte les lignes.|  
|[Fire\_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|Notifie le consommateur d'une modification qui affecte le jeu de lignes entier.|  
  
## Notes  
 `IRowsetNotifyCP` implémente des fonctions de diffusion pour informer les écouteurs sur le point de connexion **IID\_IRowsetNotify** des modifications apportées au contenu de l'ensemble de lignes.  
  
 Notez que vous devez également implémenter et inscrire `IRowsetNotify` sur le consommateur \(appelé également récepteur\) en utilisant [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) de façon que le consommateur puisse gérer les notifications.  Consultez [Réception des notifications](../../data/oledb/receiving-notifications.md) au sujet de l'implémentation de l'interface du point de connexion sur le consommateur.  
  
 Pour plus d'informations sur l'implémentation des notifications, consultez la rubrique relative aux "notifications du support " dans [Créer un fournisseur pouvant être mis à jour](../../data/oledb/creating-an-updatable-provider.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Notifications \(COM\)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [Overview of Notifications \(OLE DB\)](https://msdn.microsoft.com/en-us/library/ms725406.aspx)   
 [BEGIN\_CONNECTION\_POINT\_MAP](../Topic/BEGIN_CONNECTION_POINT_MAP.md)   
 [END\_CONNECTION\_POINT\_MAP](../Topic/END_CONNECTION_POINT_MAP.md)   
 [CONNECTION\_POINT\_ENTRY](../Topic/CONNECTION_POINT_ENTRY.md)   
 [Création d'un fournisseur actualisable](../../data/oledb/creating-an-updatable-provider.md)