---
title: "IDBPropertiesImpl::GetProperties | Microsoft Docs"
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
  - "IDBPropertiesImpl::GetProperties"
  - "IDBPropertiesImpl.GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties (méthode)"
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBPropertiesImpl::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne les valeurs des propriétés des groupes de source de données, des informations de la source de données, et des propriétés d'initialisation qui sont actuellement définis sur l'objet source de données ou les valeurs des propriétés dans le groupe de propriétés d'initialisation qui sont actuellement définies pour l'énumérateur.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(GetProperties)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties    
);  
```  
  
#### Paramètres  
 Voir [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
 Certains paramètres correspondent à des paramètres du *guide de référence du programmeur OLE DB* ayant des noms différents, qui sont décrits dans **IDBProperties::GetProperties**:  
  
|Paramètres de modèle OLE DB|Paramètres *Guide de référence du programmeur OLE DB*|  
|---------------------------------|-----------------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## Notes  
 Si le fournisseur est initialisé, cette méthode retourne les valeurs des propriétés dans les groupes de propriétés **DBPROPSET\_DATASOURCE**, **DBPROPSET\_DATASOURCEINFO**, **DBPROPSET\_DBINIT** qui sont actuellement définis sur l'objet source de données.  Si le fournisseur n'est pas initialisé, il retourne des propriétés de groupe **DBPROPSET\_DBINIT** uniquement.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBPropertiesImpl, classe](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)