---
title: "R&#233;f&#233;rence des mod&#232;les du consommateur OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-attr.db_param"
  - "vc-attr.db_column"
  - "vc-attr.db_accessor"
  - "vc-attr.db_command"
  - "vc-attr.db_table"
  - "vc.templates.ole"
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB (modèles du consommateur), classes"
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;f&#233;rence des mod&#232;les du consommateur OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les modèles du consommateur OLE DB contiennent les classes suivantes.  Des documents de référence comprennent également des rubriques sur les macros [pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## Classes de Session  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 Gère la connexion à la source de données.  C'est une classe utile pour créer des clients parce qu'elle encapsule les objets nécessaires \(source de données et session\) et une partie du travail à effectuer lors de la connexion à une source de données  
  
 [CDataSource](../../data/oledb/cdatasource-class.md)  
 Correspond à un objet de source de données OLE DB, qui représente une connexion par un fournisseur à une source de données.  Une ou plusieurs sessions de base de données, chacune représentée par un objet `CSession`, peuvent avoir lieu en une connexion unique.  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 Correspond à un objet énumérateur OLE DB, qui récupère des informations relatives à l'ensemble de lignes à propos des sources de données disponibles.  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 Utilisé par `CEnumerator` pour accéder aux données depuis un énumérateur d'ensemble de lignes.  Cet ensemble de lignes comprend les sources de données et les énumérateurs visibles depuis l'énumérateur actuel.  
  
 [CSession](../../data/oledb/csession-class.md)  
 Représente une seule session d'accès à la base de données.  Une ou plusieurs sessions peuvent être associées à chaque objet `CDataSource`.  
  
## Classes d'accesseurs  
 [CAccessor](../../data/oledb/caccessor-class.md)  
 Utilisé pour les enregistrements qui sont statiquement liés à une source de données.  Utilisez cette classe d'accesseur lorsque vous connaissez la structure de la source de données.  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 Classe de base pour toutes les classes d'accesseur.  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 Un accesseur qui peut être créé au moment de l'exécution, selon les informations de colonne de l'ensemble de lignes.  Utilisez cette classe pour récupérer des données si vous ne connaissez pas la structure de la source de données.  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 Un accesseur qui peut être utilisé lorsque les types de commande sont inconnus.  Obtient les informations de paramètre en appelant l'interface `ICommandWithParameters`, si le fournisseur prend en charge l'interface.  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 Cela vous permet d'accéder à la source des données lorsque vous n'avez aucune connaissance de la structure sous\-jacente de la base de données.  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 Similaire à `CDynamicStringAccessor` sauf que cette classe demande des données auxquelles on accède à partir de la banque de données comme donnée de chaîne ANSI.  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 Similaire à `CDynamicStringAccessor` sauf que cette classe demande des données auxquelles on accède à partir de la banque de données comme donnée de chaîne UNICODE.  
  
 [CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  
 Un accesseur dont les méthodes pour gérer les colonnes et les paramètres de commande.  Avec cette classe, vous pouvez utiliser tout type de données tant que le fournisseur peut convertir le type.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Cela peut\-être utilisé comme argument de modèle lorsque vous ne souhaitez pas que la classe prenne en charge les paramètres ou des colonnes de sortie.  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 Similaire à `CDynamicStringAccessor` sauf que cette classe convertir toutes les données auxquelles on accède depuis l'espace de stockage des données en tant que donnée formatée \(taggée\) XML.  
  
## Classes d'ensemble de lignes  
 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)  
 Inclut un ensemble de lignes et les accesseurs associés.  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 Utilisé pour accéder aux éléments d'un ensemble de lignes à l'aide de la syntaxe de table.  
  
 [CBulkRowset](../../data/oledb/cbulkrowset-class.md)  
 Utilisé pour extraire et manipuler des lignes en bloc en récupérant plusieurs descripteurs de ligne avec un appel unique.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Peut être utilisé comme argument de modèle si la commande ne retourne pas d'ensemble de lignes.  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md)  
 Utilisé pour spécifier des restrictions pour des schémas d'ensembles de lignes.  
  
 [CRowset](../../data/oledb/crowset-class.md)  
 Utilisé pour définir, manipuler, et récupérer des données d'un ensemble de lignes.  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 Retourne un objet `ISequentialStream` plutôt qu'un ensemble de lignes ; vous utilisez ensuite la méthode **Lecture** pour récupérer des données au format XML. \(SQL Server 2000 prend en charge la mise en forme ; notez que cette fonctionnalité fonctionne avec SQL Server 2000 uniquement.\)  
  
 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)  
 Fournit une implémentation factice pour `IRowsetNotify`, avec des fonctions vides pour les méthodes `IRowsetNotify` `OnFieldChange`, `OnRowChange`, et `OnRowsetChange`.  
  
 [Classes de jeu de lignes du schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)  
  
 Les modèles OLE DB vous fournissent un jeu de classes qui correspondent aux ensembles de lignes de schéma OLE DB.  
  
## Classe Commande  
 [CCommand](../../data/oledb/ccommand-class.md)  
 Permet de définir et exécuter une commande basée sur le paramètre OLE DB.  Pour ouvrir simplement un ensemble de lignes simple, utilisez `CTable` à la place.  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 Utilisé comme argument de modèle pour le modèle `CCommand` lorsque vous souhaitez que la commande ne gère plusieurs jeux de résultats.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Utilisé comme argument de modèle pour les classes de modèle, telles que `CCommand` et `CTable`, qui prend un argument de classe d'accesseur.  Utilisez `CNoAccessor` si vous ne souhaitez pas que la classe prenne en charge les paramètres ou les colonnes de sortie.  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 Utilisé comme argument de modèle pour le modèle `CCommand` lorsque vous souhaitez que la commande ne gère qu'un ensemble de lignes unique.  `CNoMultipleResults` est la valeur par défaut de l'argument modèle.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Utilisé comme argument modèle pour `CCommand` ou `CTable` si la commande ou la table ne retourne pas d'ensemble de lignes.  
  
 [CTable](../../data/oledb/ctable-class.md)  
 Utilisé pour accéder à un ensemble de lignes simple sans paramètre.  
  
## Classes de Propriété  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 Utilisé pour transmettre un tableau d'ID de propriété dont le consommateur souhaite obtenir des informations de propriété.  Les propriétés appartiennent à un jeu de propriétés.  
  
 [CDBPropSet](../../data/oledb/cdbpropset-class.md)  
 Utilisé pour définir des propriétés sur un fournisseur.  
  
## Classe Bookmark  
 [CBookmark](../../data/oledb/cbookmark-class.md)  
 Utilisé en tant qu'index pour accéder aux données d'un ensemble de lignes.  
  
## Classe d'Erreur  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 Utilisé pour récupérer des informations d'erreurs OLE DB.  
  
## Voir aussi  
 [Référence des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)   
 [modèles OLE DB](../../data/oledb/ole-db-templates.md)