---
title: "CDynamicAccessor::GetBlobSizeLimit | Microsoft Docs"
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
  - "ATL::CDynamicAccessor::GetBlobSizeLimit"
  - "CDynamicAccessor.GetBlobSizeLimit"
  - "CDynamicAccessor::GetBlobSizeLimit"
  - "GetBlobSizeLimit"
  - "ATL.CDynamicAccessor.GetBlobSizeLimit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBlobSizeLimit (méthode)"
ms.assetid: 7131e7c4-6e05-42f3-9d87-110301b672f2
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetBlobSizeLimit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère la taille maximale du BLOB en octets.  
  
## Syntaxe  
  
```  
  
const DBLENGTH GetBlobSizeLimit( ) const;  
  
```  
  
## Notes  
 Retourne la valeur `nBlobSize` de gestion d'objets BLOB défini par [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)