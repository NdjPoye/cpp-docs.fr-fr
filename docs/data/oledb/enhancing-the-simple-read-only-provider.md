---
title: "Am&#233;lioration du fournisseur simple accessible en lecture seule | Microsoft Docs"
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
  - "IRowsetLocate (classe)"
  - "IRowsetLocate (classe), ajouter aux fournisseurs de modèles OLE DB"
  - "lecture seule (fournisseur) (C++)"
  - "lecture seule (fournisseur simple) (C++)"
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Am&#233;lioration du fournisseur simple accessible en lecture seule
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette section montre comment améliorer le [fournisseur en lecture seule simple](../../data/oledb/implementing-the-simple-read-only-provider.md) créé dans la section précédente.  `IRowsetLocateImpl` crée une implémentation pour l'interface `IRowsetLocate` et ajoute la prise en charge de signets.  
  
 Une fois que vous avez un fournisseur opérationnel, vous pouvez l'améliorer afin de pouvoir l'actualiser, gérer des transactions ou améliorer les performances de l'algorithme d'extraction de lignes.  La plupart des améliorations du fournisseur impliquent l'ajout d'une interface à un objet COM existant.  
  
 L'exemple fourni dans les rubriques suivantes améliore le mécanisme d'extraction de lignes en ajoutant l'interface `IRowsetLocate` à `CAgentRowset`.  Ces rubriques montrent comment :  
  
-   [Modification de l'héritage de RMyProviderRowset](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md)  
  
-   [Détermination de manière dynamique des colonnes retournées au consommateur](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## Voir aussi  
 [Création d'un fournisseur simple accessible en lecture seule](../../data/oledb/creating-a-simple-read-only-provider.md)