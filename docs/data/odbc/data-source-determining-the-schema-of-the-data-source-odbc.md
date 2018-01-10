---
title: "Source de données : Détermination du schéma de la Source de données (ODBC) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fc425cf767db6939223288ebe74dcbc7fd4cf5b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>Source de données : détermination du schéma de la source de données (ODBC)
Cette rubrique s’applique aux classes ODBC MFC.  
  
 Pour définir les membres de données dans votre `CRecordset` objets, vous devez connaître le schéma de la source de données à laquelle vous vous connectez. Détermination du schéma d’une source de données, vous devez obtenir une liste des tables de la source de données, une liste de colonnes dans chaque table, le type de données de chaque colonne et l’existence de tous les index.  
  
## <a name="see-also"></a>Voir aussi  
 [Source de données (ODBC)](../../data/odbc/data-source-odbc.md)   
 [Source de données : gestion des connexions (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)