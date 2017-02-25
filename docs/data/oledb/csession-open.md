---
title: "CSession::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CSession::Open"
  - "CSession::Open"
  - "CSession.Open"
  - "ATL.CSession.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open (méthode)"
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CSession::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ouvre une nouvelle session pour l'objet de source de données.  
  
## Syntaxe  
  
```  
  
      HRESULT Open(  
   const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### Paramètres  
 `ds`  
 \[in\] la source de données pour laquelle la session doit être ouverte.  
  
 *pPropSet*  
 \[in\] pointeur sur un tableau de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) contenant les propriétés et valeurs à définir.  Voir le [Jeux de propriétés et de propriétés](https://msdn.microsoft.com/en-us/library/ms713696.aspx) dans *OLE DB guide de référence du programmeur* dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ulPropSets`  
 \[in\] nombre de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) passé dans l'argument *de pPropSet*.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Vous devez ouvrir l'objet source de données avec [CDataSource::Open](../../data/oledb/cdatasource-open.md) avant de le passer à `CSession::Open`.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CSession, classe](../../data/oledb/csession-class.md)