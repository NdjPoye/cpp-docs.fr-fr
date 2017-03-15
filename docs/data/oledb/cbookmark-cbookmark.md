---
title: "CBookmark::CBookmark | Microsoft Docs"
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
  - "CBookmark<0>.CBookmark<0>"
  - "CBookmark::CBookmark"
  - "ATL.CBookmark.CBookmark"
  - "CBookmark.CBookmark"
  - "CBookmark"
  - "ATL::CBookmark<0>::CBookmark<0>"
  - "ATL.CBookmark<0>.CBookmark<0>"
  - "CBookmark<0>::CBookmark<0>"
  - "ATL::CBookmark::CBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBookmark (classe), constructeur"
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBookmark::CBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Constructeur.  
  
## Syntaxe  
  
```  
  
      CBookmark( );   
CBookmark(  
   DBLENGTH nSize   
);  
```  
  
#### Paramètres  
 `nSize`  
 \[in\] Size of the bookmark buffer in bytes.  
  
## Notes  
 The first function sets the buffer to **NULL** and the buffer size to 0.  The second function sets the buffer size to `nSize`, and the buffer to a byte array of `nSize` bytes.  
  
> [!NOTE]
>  This function is only available in **CBookmark\<0\>**.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CBookmark, classe](../../data/oledb/cbookmark-class.md)