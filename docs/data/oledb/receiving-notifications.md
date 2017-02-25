---
title: "R&#233;ception des notifications | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "événements (C++), notifications dans OLE DB"
  - "notifications (C++), événements"
  - "notifications (C++), consommateurs OLE DB"
  - "consommateurs OLE DB, notifications"
  - "fournisseurs OLE DB, notifications"
  - "recevoir des notifications dans OLE DB"
  - "jeux de lignes, notifications d'événement"
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# R&#233;ception des notifications
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB fournit des interfaces pour la réception des notifications quand des événements se produisent.  Ces notifications sont décrites dans [Notifications relatives à l'objet OLE DB](https://msdn.microsoft.com/en-us/library/ms725406.aspx), dans le Guide de référence du programmeur *OLE DB*.  La configuration de ces événements utilise le mécanisme des points de connexion COM standard.  Par exemple, un objet ATL qui souhaite récupérer des événements par l'intermédiaire de `IRowsetNotify` implémente l'interface `IRowsetNotify` en ajoutant `IRowsetNotify` à la liste dérivée de la classe et en l'exposant via une macro **COM\_INTERFACE\_ENTRY**.  
  
 `IRowsetNotify` possède trois méthodes, qui peuvent être appelées à différents moments.  Si vous voulez répondre à une seule de ces méthodes, vous pouvez utiliser la classe [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md), qui retourne **E\_NOTIMPL** pour les méthodes qui ne vous intéressent pas.  
  
 Lorsque vous créez le jeu de lignes, vous devez indiquer au fournisseur que vous voulez que l'objet jeu de lignes retourné prenne en charge **IConnectionPointContainer**, qui est nécessaire pour configurer la notification.  
  
 Le code suivant indique comment ouvrir l'ensemble de lignes d'un objet ATL et utiliser la fonction `AtlAdvise` pour installer le récepteur de notification.  `AtlAdvise` retourne un cookie utilisé lorsque vous appelez `AtlUnadvise`.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  
product.Open(session, _T("Products"), &propset);  
  
AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)