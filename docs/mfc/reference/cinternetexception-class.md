---
title: "CInternetException Class | Microsoft Docs"
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
  - "CInternetException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetException class"
  - "gestion des exceptions, Internet operations"
  - "exceptions, Internet"
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInternetException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une condition d'exception liée à une opération Internet.  
  
## Syntaxe  
  
```  
class CInternetException : public CException  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetException::CInternetException](../Topic/CInternetException::CInternetException.md)|Construit un objet `CInternetException`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetException::m\_dwContext](../Topic/CInternetException::m_dwContext.md)|La valeur de contexte associée à l'opération qui a provoqué l'exception.|  
|[CInternetException::m\_dwError](../Topic/CInternetException::m_dwError.md)|L'erreur qui a provoqué l'exception.|  
  
## Notes  
 La classe d' `CInternetException` inclut deux données membres publiques : il juge code d'erreur associé à l'exception, et l'autre contient l'identificateur de contexte de l'application Web associée à l'erreur.  
  
 Pour plus d'informations sur les identificateurs de contexte pour les applications Web, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)