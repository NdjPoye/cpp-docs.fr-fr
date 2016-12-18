---
title: "Accesseurs et jeux de lignes | Microsoft Docs"
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
  - "accesseurs (C++)"
  - "accesseurs (C++), jeux de lignes"
  - "jeux de lignes de type tableau"
  - "jeux de lignes en bloc"
  - "CAccessorBase (classe)"
  - "CAccessorRowset (classe), types d'accesseurs"
  - "CArrayRowset (classe), accesseurs"
  - "CBulkRowset (classe), accesseurs"
  - "CRowset (classe), accesseurs et jeux de lignes"
  - "OLE DB (modèles du consommateur), accesseurs"
  - "OLE DB (modèles du consommateur), prise en charge des jeux de lignes"
  - "jeux de lignes (C++), accéder"
  - "jeux de lignes (C++), types pris en charge"
  - "jeux de lignes simples"
ms.assetid: edc9c8b3-1a2d-4c2d-869f-7e058c631042
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Accesseurs et jeux de lignes
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour définir et récupérer des données, les modèles OLE DB utilisent un accesseur et un ensemble de lignes au moyen de la classe [CAccessorRowset](../../data/oledb/caccessorrowset-class.md).  Cette classe peut gérer plusieurs accesseurs de différents types.  
  
## Types d'accesseurs  
 Tous les accesseurs dérivent de [CAccessorBase](../../data/oledb/caccessorbase-class.md).  `CAccessorBase` fournit la liaison de paramètre et de colonne.  
  
 L'illustration suivante représente les types d'accesseurs.  
  
 ![Types d'accesseurs](../../data/oledb/media/vcaccessortypes.png "vcAccessorTypes")  
Classes d'accesseurs  
  
-   [CAccessor](../../data/oledb/caccessor-class.md) Utilisez cet accesseur si vous connaissez la structure de la source de base de données au moment du design.  `CAccessor` lie statiquement un enregistrement de base de données, qui contient la mémoire tampon, à la source de données.  
  
-   [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) Utilisez cet accesseur si vous ne connaissez pas la structure de la base de données au moment du design.  `CDynamicAccessor` appelle `IColumnsInfo::GetColumnInfo` pour obtenir les informations sur les colonnes de base de données.  Elle crée et gère un accesseur et la mémoire tampon.  
  
-   [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) Utilisez cette classe d'accesseur pour gérer des types de commandes inconnus.  Lorsque vous préparez les commandes, `CDynamicParameterAccessor` peut obtenir les informations sur les paramètres à partir de l'interface `ICommandWithParameters`, si le fournisseur prend en charge `ICommandWithParameters`.  
  
-   [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md) et [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md) Utilisez ces classes lorsque vous ne connaissez pas du tout le schéma de base de données.  `CDynamicStringAccessorA` récupère les données sous forme de chaînes ANSI ; `CDynamicStringAccessorW` récupère les données sous forme de chaînes Unicode.  
  
-   [CManualAccessor](../../data/oledb/cmanualaccessor-class.md) Avec cette classe, vous pouvez utiliser les types de données de votre choix, à condition que le fournisseur puisse convertir le type choisi.  Elle gère à la fois les colonnes résultantes et les paramètres des commandes.  
  
 Le tableau suivant récapitule la prise en charge dans les types d'accesseurs des modèles OLE DB.  
  
|Type d'accesseur|Dynamique|Gère les paramètres|Mémoire tampon|Plusieurs accesseurs|  
|----------------------|---------------|-------------------------|--------------------|--------------------------|  
|`CAccessor`|Non|Oui|Utilisateur|Oui|  
|`CDynamicAccessor`|Oui|Non|Modèles OLE DB|Non|  
|`CDynamicParameterAccessor`|Oui|Oui|Modèles OLE DB|Non|  
|`CDynamicStringAccessor[A,W]`|Oui|Non|Modèles OLE DB|Non|  
|`CManualAccessor`|Oui|Oui|Utilisateur|Oui|  
  
## Types d'ensembles de lignes  
 Les modèles OLE DB prennent en charge trois genres d'ensembles de lignes \(consultez l'illustration précédente\) : des ensembles de lignes simples \(implémentés par [CRowset](../../data/oledb/crowset-class.md)\), des ensembles de lignes en bloc \(implémentés par [CBulkRowset](../../data/oledb/cbulkrowset-class.md)\) et des ensembles de lignes de type tableau \(implémentés par [CArrayRowset](../../data/oledb/carrayrowset-class.md)\).  Les ensembles de lignes simples extraient un handle de ligne simple lors d'un appel de `MoveNext`.  Les ensembles de lignes en bloc peuvent extraire plusieurs handles de ligne.  Les ensembles de lignes de type tableau sont des ensembles de lignes qui sont accessibles à l'aide d'une syntaxe de tableau.  
  
 L'illustration suivante représente les différents types de ensembles de lignes.  
  
 ![Graphique RowsetType](../../data/oledb/media/vcrowsettypes.png "vcRowsetTypes")  
Classes d'ensemble de lignes  
  
 Les [ensembles de lignes du schéma](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) n'accèdent pas aux données qui se trouvent dans le magasin de données ; ils accèdent plutôt aux informations relatives au magasin de données, appelées métadonnées.  Les ensembles de lignes du schéma sont généralement utilisés dans les situations où la structure de la base de données n'est pas connue au moment de la compilation, et doit être obtenue à ce moment\-là.  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)