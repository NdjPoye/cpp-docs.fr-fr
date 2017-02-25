---
title: "CStreamRowset, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CStreamRowset<TAccessor>"
  - "ATL::CStreamRowset"
  - "CStreamRowset"
  - "ATL.CStreamRowset<TAccessor>"
  - "ATL.CStreamRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStreamRowset (classe)"
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CStreamRowset, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisée dans une déclaration de `CCommand` ou de `CTable`.  
  
## Syntaxe  
  
```  
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### Paramètres  
 `TAccessor`  
 Un classe accesseur.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|Constructeur.  Instancie et initialise l'objet `CStreamRowset`.|  
|[Fermer](../../data/oledb/cstreamrowset-close.md)|Libère le pointeur d'interface de [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx) de la classe.|  
  
## Notes  
 Utilisez `CStreamRowset` dans votre déclaration de `CCommand` ou de `CTable`, par exemple :  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/CPP/cstreamrowset-class_1.cpp)]  
  
 ou  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/CPP/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` retourne un pointeur de `ISequentialStream`, stocké dans `m_spStream`.  Vous pouvez alors utiliser la méthode **Lire** pour récupérer les données \(chaîne Unicode\) au format XML.  Par exemple :  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/CPP/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 effectue la mise en forme XML et retournera toutes les colonnes et toutes les lignes du jeu de lignes en tant que chaînes XML uniques.  
  
> [!NOTE]
>  Cette fonctionnalité fonctionne avec SQL Server 2000 uniquement.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)