---
title: "CDynamicAccessor::GetBookmark | Microsoft Docs"
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
  - "CDynamicAccessor.GetBookmark"
  - "GetBookmark"
  - "CDynamicAccessor::GetBookmark"
  - "ATL.CDynamicAccessor.GetBookmark"
  - "ATL::CDynamicAccessor::GetBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBookmark (méthode)"
ms.assetid: 6d0a2970-0c62-4a34-bac7-149d8e990f81
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère le signet pour la ligne actuelle.  
  
## Syntaxe  
  
```  
  
      HRESULT GetBookmark(   
   CBookmark< >* pBookmark    
) const throw( );  
```  
  
#### Paramètres  
 `pBookmark`  
 \[out\] pointeur à l'objet [CBookmark](../../data/oledb/cbookmark-class.md).  
  
## Valeur de retour  
 Une des valeurs standard `HRESULT`.  
  
## Notes  
 Vous devez définir **DBPROP\_IRowsetLocate** à `VARIANT_TRUE` pour extraire un signet.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)