---
title: "IDBSchemaRowsetImpl::GetSchemas | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IDBSchemaRowsetImpl::GetSchemas"
  - "GetSchemas"
  - "IDBSchemaRowsetImpl<SessionClass>::GetSchemas"
  - "ATL.IDBSchemaRowsetImpl.GetSchemas"
  - "ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas"
  - "IDBSchemaRowsetImpl.GetSchemas"
  - "IDBSchemaRowsetImpl::GetSchemas"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSchemas (méthode)"
ms.assetid: fbe725a6-3acd-45f8-bcaf-10a6c1239cd2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBSchemaRowsetImpl::GetSchemas
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne une liste d’ensembles de lignes de schéma accessible par [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).  
  
## Syntaxe  
  
```  
  
STDMETHOD  
( GetSchema s )(  
   ULONG *   
pcSchemas  
,  
   GUID **   
prgSchemas  
,  
   ULONG**   
prgRest  
);  
  
```  
  
#### Paramètres  
 *pcSchemas*  
 \[out\] Pointeur désignant un **ULONG** complété du nombre de schémas.  
  
 *prgSchemas*  
 \[out\] Pointeur désignant un tableau de GUID complété d’un pointeur désignant un tableau de GUID d’ensembles de lignes de schéma.  
  
 *prgRest*  
 \[out\] Pointeur désignant un tableau de **ULONG** qui doit être complété du tableau de restrictions.  
  
## Notes  
 Cette méthode retourne un tableau de tous les ensembles de lignes de schéma pris en charge par le fournisseur. Consultez [IDBSchemaRowset::GetSchemas](https://msdn.microsoft.com/en-us/library/ms719605.aspx) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 L’implémentation de cette fonction impose à l’utilisateur de disposer d’un mappage de schéma dans la classe session. À partir des informations de mappage de schéma, elle répond ensuite avec le tableau de GUID des schémas contenus dans le mappage. Il s’agit des schémas pris en charge par le fournisseur.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBSchemaRowsetImpl, classe](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/fr-fr/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)   
 [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)   
 [Classes de jeu de lignes du schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)