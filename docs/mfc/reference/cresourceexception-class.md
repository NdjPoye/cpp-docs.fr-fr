---
title: "CResourceException Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CResourceException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CResourceException class"
  - "exceptions, ressource"
  - "resource allocation exception"
  - "resource exceptions"
  - "ressources (C++), allouer"
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CResourceException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Généré lorsque les fenêtres ne peuvent pas trouver ou allouer une ressource demandée.  
  
## Syntaxe  
  
```  
class CResourceException : public CSimpleException  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CResourceException::CResourceException](../Topic/CResourceException::CResourceException.md)|Construit un objet `CResourceException`.|  
  
## Notes  
 Aucune autre qualification n'est nécessaire ou possible.  
  
 Pour plus d'informations sur l'utilisation `CResourceException`, consultez l'article [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)