---
title: "IDBSchemaRowsetImpl::SetRestrictions | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBSchemaRowsetImpl::SetRestrictions"
  - "SetRestrictions"
  - "IDBSchemaRowsetImpl.SetRestrictions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetRestrictions (méthode)"
ms.assetid: 707d5065-b853-4d38-9b67-3066b4d3b279
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::SetRestrictions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie les restrictions que vous prenez en charge sur un ensemble de lignes de schéma particulier.  
  
## Syntaxe  
  
```  
  
void SetRestrictions(  
   ULONG   
cRestrictions  
,  
   GUID* /*   
rguidSchema  
*/,  
   ULONG*   
rgRestrictions  
);  
  
```  
  
#### Paramètres  
 `cRestrictions`  
 \[in\] Nombre de restrictions présentes dans le tableau `rgRestrictions` et nombre de GUID figurant dans le tableau `rguidSchema`.  
  
 `rguidSchema`  
 \[in\] Tableau des GUID des ensembles de lignes de schéma pour lesquels les restrictions doivent être récupérées. Chaque élément de tableau contient le GUID d’un ensemble de lignes de schéma \(par exemple, `DBSCHEMA_TABLES`\).  
  
 `rgRestrictions`  
 \[in\] Tableau de longueur `cRestrictions` des valeurs de restriction à définir. Chaque élément correspond aux restrictions de l’ensemble de lignes de schéma identifié par le GUID. Si un ensemble de lignes de schéma n’est pas pris en charge par le fournisseur, la valeur définie de l’élément est zéro. Dans le cas contraire, la valeur **ULONG** contient un masque de bits qui représente les restrictions prises en charge sur cet ensemble de lignes de schéma. Pour plus d’informations sur les restrictions correspondant à un ensemble de lignes de schéma déterminé, consultez le tableau des GUID d’ensemble de lignes de schéma dans [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans les *Informations de référence du programmeur OLE DB* du [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Notes  
 L’objet **IDBSchemaRowset** appelle la méthode `SetRestrictions` pour identifier les restrictions que vous prenez en charge sur un ensemble de lignes de schéma déterminé \(elle est appelée par [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) via un pointeur converti en supertype\). Les restrictions permettent aux consommateurs de récupérer uniquement les lignes correspondantes \(par exemple, toutes les colonnes de la table « MaTable »\). Les restrictions sont facultatives, et dans le cas où aucune n’est prise en charge \(par défaut\), toutes les données sont systématiquement retournées.  
  
 L’implémentation par défaut de cette méthode attribue aux éléments de tableau `rgRestrictions` la valeur 0. Remplacez la valeur par défaut dans votre classe session pour définir d’autres restrictions que celle par défaut.  
  
 Pour plus d’informations sur l’implémentation de la prise en charge des ensembles de lignes de schéma, consultez [Prise en charge des ensembles de lignes de schéma](../../data/oledb/supporting-schema-rowsets.md).  
  
 Pour obtenir un exemple de fournisseur qui prend en charge les ensembles de lignes de schéma, consultez l’exemple [UpdatePV](../../top/visual-cpp-samples.md).  
  
 Pour plus d’informations sur les ensembles de lignes de schéma, consultez [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans les *Informations de référence du programmeur OLE DB* du [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBSchemaRowsetImpl, classe](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/fr-fr/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Classes de jeu de lignes du schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Prise en charge des jeux de lignes du schéma](../../data/oledb/supporting-schema-rowsets.md)   
 [UpdatePV](../../top/visual-cpp-samples.md)