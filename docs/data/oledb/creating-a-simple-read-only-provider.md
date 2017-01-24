---
title: "Cr&#233;ation d&#39;un fournisseur simple accessible en lecture seule | Microsoft Docs"
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
  - "modèles du fournisseur OLE DB, créer des fournisseurs"
  - "fournisseurs OLE DB, créer"
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un fournisseur simple accessible en lecture seule
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une fois que vous avez créé un fournisseur OLE DB par l'intermédiaire de l'Assistant Projet ATL et de l'Assistant Fournisseur OLE DB ATL, vous pouvez ajouter d'autres fonctionnalités que vous souhaitez prendre en charge.  Commencez la conception de votre fournisseur en examinant le type de données que vous enverrez au consommateur et les conditions dans lesquelles vous effectuerez cet envoi.  Il est particulièrement important de déterminer si vous avez besoin de prendre en charge des commandes, des transactions et d'autres objets facultatifs.  Une bonne conception en amont accélérera l'implémentation et les tests.  
  
 L'exemple est présenté en deux parties :  
  
-   la première partie montre comment [créer un fournisseur simple accessible en lecture seule](../../data/oledb/implementing-the-simple-read-only-provider.md) qui lit une paire de chaînes ;  
  
-   la seconde partie montre comment [améliorer le fournisseur simple accessible en lecture seule](../../data/oledb/enhancing-the-simple-read-only-provider.md) en ajoutant l'interface `IRowsetLocate`.  
  
## Voir aussi  
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)