---
title: "IDBSchemaRowsetImpl, classe | Microsoft Docs"
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
  - "IDBSchemaRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBSchemaRowsetImpl (classe)"
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit l’implémentation pour les ensembles de lignes de schéma.  
  
## Syntaxe  
  
```  
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### Paramètres  
 `SessionClass`  
 Classe par laquelle `IDBSchemaRowsetImpl` est hérité. En général, cette classe est la classe session de l’utilisateur.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|Vérifie la validité des restrictions par rapport à un ensemble de lignes de schéma.|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|Implémente une fonction du créateur d’objet COM pour l’objet spécifié par le paramètre de modèle.|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|Spécifie les restrictions que vous prenez en charge sur un ensemble de lignes de schéma particulier.|  
  
### Méthodes d’interface  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|Retourne un ensemble de lignes de schéma.|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|Retourne une liste d’ensembles de lignes de schéma accessibles par [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).|  
  
## Notes  
 Cette classe implémente l’interface [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) et la fonction de créateur mise en modèle [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB utilise les ensembles de lignes de schéma pour retourner des données à propos des données d’un fournisseur. Ces données sont souvent appelées « métadonnées ». Par défaut, un fournisseur doit toujours prendre en charge `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** et **DBSCHEMA\_PROVIDER\_TYPES**, comme décrit dans [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans les *Informations de référence du programmeur OLE DB*. Les ensembles de lignes de schéma sont désignés dans un mappage de schéma. Pour plus d’informations sur les entrées de mappage de schéma, consultez [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md).  
  
 L’Assistant Fournisseur OLE DB, dans l’Assistant Objet ATL, génère automatiquement le code pour les ensembles de lignes de schéma dans votre projet. \(Par défaut, l’Assistant prend en charge les ensembles de lignes de schéma obligatoires précédemment mentionnés.\) Quand vous créez un consommateur à l’aide de l’Assistant Objet ATL, l’Assistant utilise les ensembles de lignes de schéma pour lier les données appropriées à un fournisseur. Si vous n’implémentez pas vos ensembles de lignes de schéma pour fournir les métadonnées correctes, l’Assistant ne lie pas les bonnes données.  
  
 Pour plus d’informations sur la prise en charge des ensembles de lignes de schéma dans votre fournisseur, consultez [Prise en charge des ensembles de lignes de schéma](../../data/oledb/supporting-schema-rowsets.md).  
  
 Pour plus d’informations sur les ensembles de lignes de schéma, consultez [Ensembles de lignes de schéma](https://msdn.microsoft.com/en-us/library/ms712921.aspx) dans les *Informations de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/fr-fr/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Classes de jeu de lignes du schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Prise en charge des jeux de lignes du schéma](../../data/oledb/supporting-schema-rowsets.md)