---
title: "IDBPropertiesImpl::SetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBPropertiesImpl.SetProperties"
  - "SetProperties"
  - "IDBPropertiesImpl::SetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetProperties (méthode)"
ms.assetid: 2f9fc1de-7f35-4bca-bab3-7b427bf92c26
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBPropertiesImpl::SetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit les propriétés des groupes de source de données et de propriétés d'initialisation, les objets sources de données, ou le groupe de propriétés d'initialisation, pour les énumérateurs.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### Paramètres  
 Consultez [IDBProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms723049.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Notes  
 Si le fournisseur est initialisé, cette méthode définit les valeurs des propriétés dans les groupes de propriétés **DBPROPSET\_DATASOURCE**, **DBPROPSET\_DATASOURCEINFO**, **DBPROPSET\_DBINIT** pour l'objet source de données.  Si le fournisseur n'est pas initialisé, il définit des propriétés de groupe **DBPROPSET\_DBINIT** uniquement.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBPropertiesImpl, classe](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)