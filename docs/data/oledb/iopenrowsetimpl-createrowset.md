---
title: "IOpenRowsetImpl::CreateRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IOpenRowsetImpl.CreateRowset"
  - "IOpenRowsetImpl::CreateRowset"
  - "CreateRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRowset (méthode)"
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IOpenRowsetImpl::CreateRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un objet d'un ensemble de lignes.  Pas appelé directement par l'utilisateur.  Consultez [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Syntaxe  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### Paramètres  
 `RowsetClass`  
 Un membre de la classe de modèle qui représente la classe d'ensemble de l'utilisateur.  Généralement généré par l'Assistant.  
  
 `pRowsetObj`  
 \[out\] pointeur à un objet d'ensemble de lignes.  Généralement ce paramètre n'est pas utilisé, mais il peut être utilisé si vous devez effectuer des tâches dans l'ensemble de lignes avant de le passer à un objet COM.  La durée de vie de `pRowsetObj` est liée par `ppRowset`.  
  
 Pour d'autres paramètres, consultez [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) dans *OLE DB guide de référence du programmeur.*  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IOpenRowsetImpl, classe](../../data/oledb/iopenrowsetimpl-class.md)