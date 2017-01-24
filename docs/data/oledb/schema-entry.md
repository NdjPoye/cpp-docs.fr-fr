---
title: "SCHEMA_ENTRY | Microsoft Docs"
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
  - "SCHEMA_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SCHEMA_ENTRY (macro)"
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SCHEMA_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Associe un GUID à une classe.  
  
## Syntaxe  
  
```  
  
      SCHEMA_ENTRY(  
   guid,  
   rowsetClass   
);   
```  
  
#### Paramètres  
 `guid`  
 Un schéma en colonnes du GUID.  Voir le [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans *OLE DB guide de référence du programmeur* pour obtenir la liste des ensembles de lignes de schéma et de son GUID.  
  
 *rowsetClass*  
 La classe qui sera créée pour représenter l'ensemble de lignes de schéma.  
  
## Notes  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) peut alors interroger la carte pour obtenir la liste des GUID, ou elle peut créer un ensemble de lignes si elle est fournie GUID.  L'ensemble de lignes de schéma `IDBSchemaRowsetImpl` crée est similaire à une norme `CRowsetImpl`\- classe dérivée, à moins qu'elle doive fournir une méthode de **Exécuter** dont la signature est la suivante :  
  
 `HRESULT Execute (LONG* pcRowsAffected, ULONG cRestrictions,`  
  
 `const VARIANT* rgRestrictions)`  
  
 Cette fonction de **Exécuter** remplit les données de l'ensemble de lignes.  L'Assistant Projet bibliothèque ATL crée, comme décrit dans [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans *OLE DB guide de référence du programmeur*, trois ensembles de lignes de schéma initial du projet pour les trois liaison de schéma OLE DB :  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA\_COLUMNS**  
  
-   **DBSCHEMA\_PROVIDER\_TYPES**  
  
 L'Assistant ajoute également trois entrées correspondantes dans le schéma de mappage.  Voir le [Créer un fournisseur de modèle OLE DB](../../data/oledb/creating-an-ole-db-provider.md) pour plus d'informations sur l'utilisation de l'Assistant pour créer un fournisseur.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN\_SCHEMA\_MAP](../../data/oledb/begin-schema-map.md)   
 [END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)