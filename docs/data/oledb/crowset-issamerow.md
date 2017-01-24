---
title: "CRowset::IsSameRow | Microsoft Docs"
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
  - "CRowset::IsSameRow"
  - "CRowset.IsSameRow"
  - "IsSameRow"
  - "ATL::CRowset::IsSameRow"
  - "ATL.CRowset.IsSameRow"
  - "CRowset<TAccessor>::IsSameRow"
  - "ATL.CRowset<TAccessor>.IsSameRow"
  - "CRowset<TAccessor>.IsSameRow"
  - "ATL::CRowset<TAccessor>::IsSameRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsSameRow (méthode)"
ms.assetid: 53cba847-52f5-4dd9-973f-bbe7454c425c
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::IsSameRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare la rangée spécifiée à la rangée actuelle.  
  
## Syntaxe  
  
```  
  
      HRESULT IsSameRow(   
   HROW hRow    
) const throw( );  
```  
  
#### Paramètres  
 `hRow`  
 \[in\] Le maniement d'une ligne à comparer à la ligne actuelle.  
  
## Valeur de retour  
 Un `HRESULT` standard.  `S_OK` indique que les lignes sont identiques.  Pour les autres valeurs, consultez [IRowsetIndentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) dans le *guide de référence du programmeur OLE DB* dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)