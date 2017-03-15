---
title: "IRowsetImpl::m_bReset | Microsoft Docs"
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
  - "ATL.IRowsetImpl.m_bReset"
  - "IRowsetImpl.m_bReset"
  - "m_bReset"
  - "IRowsetImpl::m_bReset"
  - "ATL::IRowsetImpl::m_bReset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bReset"
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::m_bReset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un indicateur de bit utilisé pour déterminer si la position de curseur est définie dans l'ensemble de lignes.  
  
## Syntaxe  
  
```  
  
unsigned m_bReset:1;  
  
```  
  
## Notes  
 Si le consommateur appelle [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) avec `lOffset` négatif ou *les* paramètres crows et le `m_bReset` est vrai, `GetNextRows` passe à la fin de l'ensemble de lignes.  Si `m_bReset` est faux, le consommateur obtient un code d'erreur, conformément à la spécification OLE DB.  L'indicateur de `m_bReset` obtient la valeur **vrai** lorsque l'ensemble de lignes est d'abord créé et que le consommateur appelle [IRowsetImpl::RestartPosition](../../data/oledb/irowsetimpl-restartposition.md).  Elle obtient la valeur **faux** lorsque vous appelez `GetNextRows`.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)