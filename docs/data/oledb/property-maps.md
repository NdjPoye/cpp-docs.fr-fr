---
title: "Mappages des propri&#233;t&#233;s | Microsoft Docs"
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
  - "mappages, propriété"
  - "fournisseurs OLE DB, propriétés"
  - "mappage de propriétés"
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mappages des propri&#233;t&#233;s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Outre les objets session, rowset et l'objet facultatif command, chaque fournisseur prend en charge une ou plusieurs propriétés.  Ces propriétés sont définies dans les mappages des propriétés contenus dans les fichiers d'en\-tête créés par l'Assistant Fournisseur OLE DB.  Chaque fichier d'en\-tête contient un mappage pour les propriétés du groupe de propriétés OLE DB spécifié pour les objets définis dans ce fichier.  Le fichier d'en\-tête contenant l'objet data source contient également le mappage des propriétés pour les [propriétés DataSource](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx).  Session.h contient le mappage des propriétés pour les [propriétés Session](https://msdn.microsoft.com/en-us/library/ms714221.aspx).  Les objets de commande et ensemble de lignes résident dans un fichier d'en\-tête unique appelé *nomprojet*RS.h.  Ces propriétés sont membres du groupe [propriétés Ensemble de lignes](https://msdn.microsoft.com/en-us/library/ms711252.aspx).  
  
## Voir aussi  
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)