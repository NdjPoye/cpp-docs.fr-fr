---
title: "CDynamicStringAccessorW, classe | Microsoft Docs"
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
  - "CDynamicStringAccessorW"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessorW (classe)"
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessorW, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les accesseurs dynamiques vous permettent d'accéder à une source de données lorsque vous ignorez tout du schéma de la base de données \(sa structure sous\-jacente\).  
  
## Syntaxe  
  
```  
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;  
```  
  
## Notes  
 Ces deux\-ci demandent que le fournisseur fasse l'extraction de toutes les données accessibles depuis le dépôt des données en données de type string , mais `CDynamicStringAccessor` demande des données de chaîne Unicode.  
  
 `CDynamicStringAccessorW` hérite **GetString** et `SetString` de `CDynamicStringAccessor`.  Lorsque vous utilisez ces méthodes dans `CDynamicStringAccessorW` objet, ***BaseType*** est **WCHAR**.  
  
## Configuration requise  
 **En\-tête :**: atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor, classe](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor, classe](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor, classe](../../data/oledb/cdynamicstringaccessor-class.md)