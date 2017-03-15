---
title: "CDBPropIDSet, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropIDSet"
  - "ATL.CDBPropIDSet"
  - "ATL::CDBPropIDSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropIDSet (classe)"
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDBPropIDSet, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Hérite de la structure de **DBPROPIDSET** et ajoute un constructeur qui initialise les champs clés ainsi que la méthode d'accès de [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md).  
  
## Syntaxe  
  
```  
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|Ajoute une propriété à l'ensemble des ID de propriété.|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|Constructeur.|  
|[SetGUID](../../data/oledb/cdbpropidset-setguid.md)|Initialise le GUID de la propriété ID à définir.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../../data/oledb/cdbpropidset-operator-equal.md)|Affecte le contenu d'un ID de propriété définie à une autre.|  
  
## Notes  
 Les consommateurs OLE DB utilisent des structures de **DBPROPIDSET** pour transmettre un tableau d'ID de propriété dont le consommateur souhaite obtenir des informations de propriété.  Les propriétés identifiées dans une même structure [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) appartiennent à un jeu de propriétés.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)