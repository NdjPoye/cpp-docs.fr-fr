---
title: "OLE DB Consumer Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], database"
  - "attributes [C++], data access"
  - "databases [C++], attributes"
  - "OLE DB consumers [C++], attributes"
  - "database attributes [C++]"
  - "attributes [C++], OLE DB consumer"
ms.assetid: 017b591f-8f9a-42b4-84d5-cc42a21ab0cc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB Consumer Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les attributs du consommateur OLE DB injectent un code, en fonction de [modèles du consommateur OLE DB](../data/oledb/ole-db-consumer-templates-reference.md), pour créer un consommateur OLE DB actif qui effectue des tâches telles que des tableaux d'ouverture, exécution des données de commandes, puis d'accès.  
  
|Attribut|Description|  
|--------------|-----------------|  
|[db\_accessor](../windows/db-accessor.md)|Lie les colonnes dans un jeu de lignes et des liens aux tables de correspondance d'accesseur.|  
|[db\_column](../windows/db-column.md)|Lie une colonne spécifiée dans l'ensemble de lignes.|  
|[db\_command](../windows/db-command.md)|Exécute une commande OLE DB.|  
|[db\_param](../windows/db-param.md)|associe la variable membre spécifiée avec un paramètre d'entrée ou de sortie.|  
|[db\_source](../windows/db-source.md)|Crée et encapsule une connexion, via un fournisseur, à une source de données.|  
|[db\_table](../windows/db-table.md)|Ouvre une table OLE DB.|  
  
## Voir aussi  
 [Attributes by Group](../windows/attributes-by-group.md)