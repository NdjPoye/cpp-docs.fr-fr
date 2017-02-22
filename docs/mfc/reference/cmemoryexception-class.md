---
title: "CMemoryException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMemoryException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion d'exceptions C++, mémoire"
  - "CMemoryException class"
  - "exceptions, memory type"
  - "memory exceptions"
  - "mémoire, gestion des exceptions"
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMemoryException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une condition d'exception de mémoire insuffisante.  
  
## Syntaxe  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMemoryException::CMemoryException](../Topic/CMemoryException::CMemoryException.md)|Construit un objet `CMemoryException`.|  
  
## Notes  
 Aucune autre qualification n'est nécessaire ou possible.  Les exceptions de mémoire sont levées automatiquement par **nouveau**.  Si vous écrivez vos propres fonctions de mémoire, à l'aide de `malloc`, par exemple, vous êtes chargé de lever des exceptions de mémoire.  
  
 Pour plus d'informations sur `CMemoryException`, consultez l'article [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)