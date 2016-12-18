---
title: "CXMLAccessor, classe | Microsoft Docs"
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
  - "ATL::CXMLAccessor"
  - "CXMLAccessor"
  - "ATL.CXMLAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CXMLAccessor (classe)"
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CXMLAccessor, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous permet d'accéder à une source de données comme données de chaîne lorsque vous n'avez aucune connaissance du schéma \(structure sous\-jacente\) du magasin de données.  
  
## Syntaxe  
  
```  
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|Récupère les informations de colonne.|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|Récupère le contenu entier de la table par lignes.|  
  
## Notes  
 Cependant, `CXMLAccessor` est différent de `CDynamicStringAccessorW`, car il convertit toutes les données accessibles depuis le magasin de données au format XML \(référencé\).  Cela est particulièrement utile pour la sortie des pages Web XML\-aware  Les noms des balises XML correspondent aux noms des colonnes du magasin de données aussi étroitement que possible.  
  
 Utilisez les méthodes `CDynamicAccessor` pour récupérer des informations sur les colonnes.  Vous utilisez ces informations sur les colonnes pour créer un accesseur de manière dynamique au moment de l'exécution.  
  
 Les informations sur les colonnes sont stockées dans une mémoire tampon qui est créée et managée par cette classe.  Obtenez des informations sur la colonne en utilisant [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) ou obtenez les données des colonnes par lignes en utilisant [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md).  
  
## Exemple  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/CPP/cxmlaccessor-class_1.cpp)]  
  
## Configuration requise  
 **En\-tête :**: atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor, classe](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor, classe](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA, classe](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW, classe](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor, classe](../../data/oledb/cmanualaccessor-class.md)