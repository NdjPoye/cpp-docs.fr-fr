---
title: "IRowsetNotifyImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetNotifyImpl"
  - "ATL::IRowsetNotifyImpl"
  - "IRowsetNotifyImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetNotifyImpl (classe)"
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetNotifyImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente et stocke [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) sur le consommateur \(également appelée « récepteur »\) afin qu'il puisse traiter les notifications.  
  
## Syntaxe  
  
```  
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[OnFieldChange](../../data/oledb/irowsetnotifyimpl-onfieldchange.md)|Notifie le consommateur de toute modification apportée à la valeur d'une colonne.|  
|[OnRowChange](../../data/oledb/irowsetnotifyimpl-onrowchange.md)|Notifie le consommateur de la première modification apportée à une ligne ou de toute modification qui affecte la ligne entière.|  
|[OnRowsetChange](../../data/oledb/irowsetnotifyimpl-onrowsetchange.md)|Notifie le consommateur de toute modification qui affecte le jeu de lignes entier.|  
  
## Notes  
 Consultez [Réception des notifications](../../data/oledb/receiving-notifications.md) au sujet de l'implémentation de l'interface du point de connexion sur le consommateur.  
  
 `IRowsetNotifyImpl` fournit une implémentation factice pour `IRowsetNotify`, avec des fonctions vides pour les méthodes `IRowsetNotify` [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx), [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx), et [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx).  Si vous héritez de cette classe lorsque vous implémentez une interface `IRowsetNotify`, n'implémentez que les méthodes dont vous avez besoin.  Vous devez également fournir des implémentations vides pour les autres méthodes vous\-même.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)   
 [IRowsetNotifyCP, classe](../../data/oledb/irowsetnotifycp-class.md)