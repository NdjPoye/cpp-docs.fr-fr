---
title: "IDBPropertiesImpl, classe | Microsoft Docs"
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
  - "IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBPropertiesImpl (classe)"
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBPropertiesImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation de l'interface `IDBProperties`.  
  
## Syntaxe  
  
```  
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IDBPropertiesImpl`.  
  
## Membres  
  
### Méthodes d'interface  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|Retourne les valeurs des propriétés des groupes de source de données, des informations de la source de données, et des propriétés d'initialisation qui sont actuellement définis sur l'objet source de données ou les valeurs des propriétés dans le groupe de propriétés d'initialisation qui sont actuellement définies pour l'énumérateur.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|Retourne des informations sur toutes les propriétés prises en charge par le fournisseur.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|Définit les propriétés des groupes de source de données et de propriétés d'initialisation, les objets sources de données, ou le groupe de propriétés d'initialisation, pour les énumérateurs.|  
  
## Notes  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) est une interface de liaison pour les objets sources de données et une interface facultative pour les énumérateurs.  Toutefois, si un énumérateur expose [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx), il doit exposer `IDBProperties`.  `IDBPropertiesImpl` implémente `IDBProperties` à l'aide d'une fonction statique définie par [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)