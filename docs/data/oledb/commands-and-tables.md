---
title: "Commandes et tables | Microsoft Docs"
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
  - "CAccessorRowset (classe), classes de commande et de table"
  - "CCommand (classe), OLE DB (modèles du consommateur)"
  - "commandes (C++), modèles du consommateur OLE DB"
  - "CTable (classe)"
  - "OLE DB (modèles du consommateur), prise en charge de commande"
  - "OLE DB (modèles du consommateur), prise en charge de table"
  - "jeux de lignes, accéder"
  - "tables (C++), modèles du consommateur OLE DB"
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Commandes et tables
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les commandes et les tables permettent d'accéder aux jeux de lignes, c'est\-à\-dire, d'ouvrir des jeux de lignes, d'exécuter des commandes et de lier des colonnes.  Les classes [CCommand](../../data/oledb/ccommand-class.md) et [CTable](../../data/oledb/ctable-class.md) instancient les objets commande et table, respectivement.  Ces classes dérivent de [CAccessorRowset](../../data/oledb/caccessorrowset-class.md), comme le montre l'illustration ci\-dessous.  
  
 ![CCommand et CTable](../../data/oledb/media/vccommandstables.png "vcCommandsTables")  
Classes de commande et de table  
  
 Dans le tableau qui précède, `TAccessor` peut représenter n'importe quel type d'accesseur répertorié dans [Types d'accesseurs](../../data/oledb/accessors-and-rowsets.md).  *TRowset* peut correspondre à n'importe quel type de jeu de lignes répertorié dans [Types de jeux de lignes](../../data/oledb/accessors-and-rowsets.md).  *TMultiple* spécifie le type de résultat \(un jeu de résultats simple ou multiple\).  
  
 L'[Assistant Consommateur OLE DB ATL](../../atl/reference/atl-ole-db-consumer-wizard.md) vous permet de spécifier si vous voulez un objet commande ou table.  
  
-   Pour les sources de données sans commande, vous pouvez utiliser la classe `CTable`.  Vous l'utilisez généralement pour des jeux de lignes simples qui ne spécifient pas de paramètre et n'exigent aucun résultat multiple.  Cette classe simple ouvre une table sur une source de données en utilisant un nom de table que vous spécifiez.  
  
-   Pour les sources de données qui prennent en charge les commandes, utilisez de préférence la classe `CCommand`.  Pour exécuter une commande, appelez la méthode [Open](../../data/oledb/ccommand-open.md) sur cette classe.  Sinon, vous pouvez appeler la méthode `Prepare` pour préparer une commande que vous voulez exécuter plusieurs fois.  
  
     **CCommand** possède trois arguments template : un type d'accesseur, un type de jeu de lignes et un type de résultat \(`CNoMultipleResults`, par défaut, ou `CMultipleResults`\).  Si vous spécifiez `CMultipleResults`, la classe `CCommand` prend en charge l'interface **IMultipleResults** et gère les jeux de lignes multiples.  L'exemple [DBVIEWER](http://msdn.microsoft.com/fr-fr/07620f99-c347-4d09-9ebc-2459e8049832) montre comment gérer les résultats multiples.  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)