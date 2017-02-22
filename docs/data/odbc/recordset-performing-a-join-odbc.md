---
title: "Recordset&#160;: cr&#233;ation d&#39;une jointure (ODBC) | Microsoft Docs"
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
  - "liaison de données (C++), colonnes dans les recordsets"
  - "liaison de données (C++), colonnes de recordsets"
  - "filtres (C++), conditions de jointure pour les recordsets"
  - "jointures (C++), dans les recordsets"
  - "ODBC (recordsets C++), jointures"
  - "recordsets (C++), lier des données"
  - "recordsets (C++), joindre des tables"
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset&#160;: cr&#233;ation d&#39;une jointure (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
## Définition d'une jointure  
 L'opération de jointure, tâche fréquente d'accès aux données, permet de travailler avec les données provenant de plusieurs tables à l'aide d'un seul objet recordset.  La jointure de deux ou de plusieurs tables génère un recordset pouvant contenir les colonnes provenant de chaque table, mais apparaît sous forme d'une table unique pour l'application.  Parfois, la jointure utilise toutes les colonnes de toutes les tables, mais il arrive que la clause SQL **SELECT** d'une jointure n'utilise que quelques colonnes de chaque table.  Les classes de base de données prennent en charge les jointures en lecture seule mais non les jointures modifiables.  
  
 Pour sélectionner les enregistrements contenant des colonnes provenant des tables jointes, les éléments suivants sont nécessaires :  
  
-   Une liste contenant les noms de toutes les tables jointes.  
  
-   Une liste contenant les noms de toutes les colonnes impliquées.  Les colonnes ayant un même nom mais provenant de tables différentes sont qualifiées par le nom de table.  
  
-   Un filtre \(clause SQL **WHERE**\) spécifiant les colonnes sur lesquelles les tables sont jointes.  Le filtre est de la forme « Table1.KeyCol \= Table2.KeyCol » et concrètement, c'est lui qui effectue la jointure.  
  
 Vous pouvez joindre plus de deux tables de la même façon en associant plusieurs paires de colonnes, chaque paire étant jointe par le mot clé SQL **AND**.  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : déclaration de la classe d'une requête prédéfinie \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)   
 [Recordset : déclaration de la classe d'une table \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Recordset : lancement d'une nouvelle requête sur un recordset \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)