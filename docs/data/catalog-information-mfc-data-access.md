---
title: "Informations relatives au catalogue (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "base de données des informations de catalogue (C++)"
  - "DAO (C++), informations de catalogue"
  - "bases de données (C++), base de données des informations de catalogue"
  - "ODBC (C++), informations de catalogue"
  - "tables (C++)"
  - "tables (C++), informations de catalogue"
ms.assetid: c184e80f-ff17-409f-9df8-05275080bb8d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Informations relatives au catalogue (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les informations sur les tables d'une source de données peuvent inclure les noms des tables et de leurs colonnes, les privilèges de table, les noms des clés primaires et étrangères, des informations sur les procédures stockées ou les requêtes prédéfinies, des informations sur les index des tables et des statistiques sur les tables.  
  
 Pour plus d'informations, consultez [Source de données : détermination du schéma de la source de données \(ODBC\)](../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md).  
  
> [!NOTE]
>  Dans les classes DAO MFC, vous pouvez obtenir des informations de catalogue comme suit : utilisez [CDaoDatabase::GetTableDefCount](../Topic/CDaoDatabase::GetTableDefCount.md) et [CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md) pour énumérer les tables dans la base de données et obtenir des informations concernant chaque table dans une structure [CDaoTableDefInfo](../mfc/reference/cdaotabledefinfo-structure.md).  
  
## Voir aussi  
 [Programmation de l'accès aux données \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)