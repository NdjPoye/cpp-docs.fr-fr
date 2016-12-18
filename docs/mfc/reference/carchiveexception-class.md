---
title: "CArchiveException Class | Microsoft Docs"
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
  - "CArchiveException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "archive exceptions [C++]"
  - "CArchiveException class"
  - "exceptions [C++], archive"
  - "exceptions [C++], sérialisation"
  - "sérialisation (C++), exceptions"
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArchiveException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une condition d'exception de sérialisation  
  
## Syntaxe  
  
```  
class CArchiveException : public CException  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CArchiveException::CArchiveException](../Topic/CArchiveException::CArchiveException.md)|Construit un objet `CArchiveException`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CArchiveException::m\_cause](../Topic/CArchiveException::m_cause.md)|Indique la cause de l'exception.|  
|[CArchiveException::m\_strFileName](../Topic/CArchiveException::m_strFileName.md)|Spécifie le nom du fichier pour cette condition d'exception.|  
  
## Notes  
 La classe d' `CArchiveException` inclut une donnée membre privée qui indique la cause de l'exception.  
  
 Les objets d'`CArchiveException` sont construits les fonctions membres et intérieures levées de [CArchive](../../mfc/reference/carchive-class.md) .  Vous pouvez accéder à ces objets dans la portée d'une expression de **collecteur** .  Le code de cause est indépendant du système d'exploitation.  Pour plus d'informations sur l'exception de traitement, consultez [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CArchive Class](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)   
 [Traitement des exceptions](../../mfc/reference/exception-processing.md)