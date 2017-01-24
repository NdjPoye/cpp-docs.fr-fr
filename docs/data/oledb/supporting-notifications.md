---
title: "Prise en charge des notifications | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
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
  - "notifications (C++), consommateurs OLE DB"
  - "consommateurs OLE DB, notifications"
  - "modèles du fournisseur OLE DB, notifications"
  - "fournisseurs OLE DB, notifications"
  - "jeux de lignes, notifications d'événement"
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge des notifications
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Implémentation des interfaces des points de connexion sur le fournisseur et le consommateur  
 Pour implémenter des notifications, une classe de fournisseur doit hériter de [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) et de [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md).  
  
 `IRowsetNotifyCP` implémente le site de fournisseur pour l'interface de point de connexion [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  `IRowsetNotifyCP` implémente des fonctions de diffusion pour informer les écouteurs sur le point de connexion **IID\_IRowsetNotify** des modifications apportées au contenu de l'ensemble de lignes.  
  
 Notez que vous devez également implémenter et inscrire `IRowsetNotify` sur le consommateur \(appelé également récepteur\) en utilisant [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) de façon que le consommateur puisse gérer les notifications.  Pour plus d'informations sur l'implémentation de l'interface de point de connexion sur le consommateur, consultez [Réception des notifications](../../data/oledb/receiving-notifications.md).  
  
 En outre, la classe doit également contenir un mappage qui définit l'entrée du point de connexion, comme ceci :  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## Ajout de IRowsetNotify  
 Pour ajouter `IRowsetNotify`, vous devez ajouter `IConnectionPointContainerImpl<rowset-name>` et `IRowsetNotifyCP<rowset-name>` à votre chaîne d'héritage.  
  
 Par exemple, voici la chaîne d'héritage pour `RUpdateRowset` dans [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f) :  
  
> [!NOTE]
>  Si l'exemple de code et le texte répertorié dans les rubriques suivantes diffèrent, c'est l'exemple de code qui doit être considéré comme étant la version la plus récente.  
  
```  
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan> >, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll > >,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### Définition des entrées du mappage COM  
 Vous devez également ajouter le texte suivant au mappage COM dans votre jeu de lignes :  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 Ces macros permettent à ceux qui appellent `QueryInterface` pour votre conteneur de point de connexion \(la base de `IRowsetNotify`\) de trouver l'interface demandée sur votre fournisseur.  Pour obtenir un exemple du mode d'utilisation des points de connexion, consultez l'exemple ATL POLYGON et le didacticiel qui s'y rapporte.  
  
### Définition des entrées de mappage des points de connexion  
 Vous devez également ajouter une table des points de connexion.  Elle doit ressembler à ceci :  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 Cette table des points de connexion permet à un composant recherchant l'interface `IRowsetNotify` de la trouver dans votre fournisseur.  
  
### Définition de propriétés  
 Vous devez aussi ajouter les propriétés suivantes à votre fournisseur.  Seules les propriétés basées sur les interfaces que vous prenez en charge doivent être ajoutées.  
  
|Propriété|À ajouter si vous prenez en charge|  
|---------------|----------------------------------------|  
|**DBPROP\_IConnectionPointContainer**|Toujours|  
|**DBPROP\_NOTIFICATIONGRANULARITY**|Toujours|  
|**DBPROP\_NOTIFICATIONPHASES**|Toujours|  
|**DBPROP\_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWSETFETCHPOSITIONCHANGE**|Toujours|  
|**DBPROP\_NOTIFYROWFIRSTCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWSETRELEASE**|Toujours|  
|**DBPROP\_NOTIFYROWUNDOCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 L'essentiel de l'implémentation des notifications est déjà incorporé dans les modèles du fournisseur OLE DB.  Compte tenu d'une fonctionnalité du compilateur dans Visual C\+\+ .NET, si vous n'ajoutez pas `IRowsetNotifyCP` à votre chaîne d'héritage, le compilateur supprime tout ce code de votre flux de compilation, réduisant ainsi la taille du code.  
  
## Voir aussi  
 [Techniques avancées du fournisseur](../../data/oledb/advanced-provider-techniques.md)