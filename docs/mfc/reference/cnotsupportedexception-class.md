---
title: "CNotSupportedException Class | Microsoft Docs"
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
  - "CNotSupportedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNotSupportedException class"
  - "exceptions, not supported"
  - "unsupported features"
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CNotSupportedException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une exception qui est le résultat d'une requête d'une fonctionnalité non prise en charge.  
  
## Syntaxe  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CNotSupportedException::CNotSupportedException](../Topic/CNotSupportedException::CNotSupportedException.md)|Construit un objet `CNotSupportedException`.|  
  
## Notes  
 Aucune autre qualification n'est nécessaire ou possible.  
  
 Pour plus d'informations sur l'utilisation `CNotSupportedException`, consultez l'article [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)