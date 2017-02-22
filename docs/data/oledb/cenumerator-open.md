---
title: "CEnumerator::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CEnumerator.Open"
  - "CEnumerator::Open"
  - "ATL::CEnumerator::Open"
  - "CEnumerator.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open (méthode)"
ms.assetid: b22821a0-257a-4543-ad0c-2649d4ac092e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CEnumerator::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lie le moniker pour l'énumérateur, s'il y en a un de spécifié, puis récupère l'ensemble de lignes de l'énumérateur en appelant [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/en-us/library/ms711200.aspx).  
  
## Syntaxe  
  
```  
  
      HRESULT Open(   
   LPMONIKER pMoniker    
) throw( );  
HRESULT Open(   
   const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR    
) throw( );  
HRESULT Open(   
   const CEnumerator& enumerator    
) throw( );  
```  
  
#### Paramètres  
 `pMoniker`  
 \[in\] pointeur à un moniker pour un énumérateur.  
  
 *pClsid*  
 \[in\] pointeur au **CLSID** d'un énumérateur.  
  
 `enumerator`  
 \[in\] référence à un énumérateur.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CEnumerator, classe](../../data/oledb/cenumerator-class.md)