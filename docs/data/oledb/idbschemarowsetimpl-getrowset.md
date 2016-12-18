---
title: "IDBSchemaRowsetImpl::GetRowset | Microsoft Docs"
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
  - "ATL::IDBSchemaRowsetImpl::GetRowset"
  - "ATL.IDBSchemaRowsetImpl.GetRowset"
  - "IDBSchemaRowsetImpl<SessionClass>::GetRowset"
  - "IDBSchemaRowsetImpl.GetRowset"
  - "IDBSchemaRowsetImpl::GetRowset"
  - "ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset"
  - "GetRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowset (méthode)"
ms.assetid: 3ae28c22-e186-4a15-8591-b0192e784a6f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::GetRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne un ensemble de lignes de schéma.  
  
## Syntaxe  
  
```  
  
STDMETHOD (GetRowset)(  
   IUnknown *  
pUnkOuter  
,  
   REFGUID   
rguidSchema  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[],  
   REFIID   
riid  
,  
   ULONG   
cPropertySets  
,  
   DBPROPSET   
rgPropertySets  
[],  
   IUnknown **  
ppRowset  
);  
  
```  
  
#### Paramètres  
 `pUnkOuter`  
 \[in\] **IUnknown** externe pendant l’agrégation ; sinon, **NULL**.  
  
 `rguidSchema`  
 \[in\] Référence au GUID d’ensemble de lignes de schéma demandé \(par exemple, `DBSCHEMA_TABLES`\).  
  
 `cRestrictions`  
 \[in\] Nombre de restrictions à appliquer à l’ensemble de lignes.  
  
 `rgRestrictions`  
 \[in\] Tableau d’objets `cRestrictions` **VARIANT** qui représentent les restrictions.  
  
 `riid`  
 \[in\] IID associé à la demande portant sur l’ensemble de lignes de schéma nouvellement créé.  
  
 `cPropertySets`  
 \[in\] Nombre de sets de propriétés à définir.  
  
 `rgPropertySets`  
 \[in\/out\] Tableau de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) à définir sur l’ensemble de lignes de schéma nouvellement créé.  
  
 `ppRowset`  
 \[out\] Pointeur désignant l’interface demandée sur l’ensemble de lignes de schéma nouvellement créé.  
  
## Notes  
 Cette méthode impose à l’utilisateur de disposer d’un mappage de schéma dans la classe session. À partir des informations de mappage de schéma, `GetRowset` crée un objet rowset donné si le paramètre `rguidSchema` est égal à l’un des GUID d’entrée de mappage. Consultez [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md) pour obtenir une description de l’entrée de mappage.  
  
 Consultez [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBSchemaRowsetImpl, classe](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/fr-fr/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)   
 [Classes de jeu de lignes du schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)