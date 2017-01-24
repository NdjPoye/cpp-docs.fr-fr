---
title: "CDBPropSet, classe | Microsoft Docs"
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
  - "CDBPropSet"
  - "ATL.CDBPropSet"
  - "ATL::CDBPropSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropSet (classe)"
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropSet, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Hérite de la structure de **DBPROPSET** et ajoute un constructeur qui initialise les champs clés ainsi que la méthode d'accès de `AddProperty`.  
  
## Syntaxe  
  
```  
class CDBPropSet : public tagDBPROPSET  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|Ajoute une propriété au jeu de propriétés.|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|Constructeur.|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|Affecte la valeur au champ **EnsembleProprietesGuide** dans la structure de **DBPROPSET**.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../../data/oledb/cdbpropset-operator-equal.md)|Affecte le contenu d'une propriété définie à une autre valeur.|  
  
## Notes  
 Les fournisseurs et les consommateurs OLE DB utilisent des structures de **DBPROPSET** pour passer les options de structures `DBPROP`.  Chaque structure `DBPROP` représente une seule propriété qui peut être définie.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CDBPropIDSet, classe](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET Structure](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)