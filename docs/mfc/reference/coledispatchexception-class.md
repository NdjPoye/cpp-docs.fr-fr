---
title: "COleDispatchException Class | Microsoft Docs"
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
  - "COleDispatchException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation, exceptions"
  - "COleDispatchException class"
  - "exceptions, OLE"
  - "OLE exceptions, to IDispatch interface"
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDispatchException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère les exceptions spécifiques à OLE interface d' `IDispatch` , qui est une partie fondamentale OLE automation de.  
  
## Syntaxe  
  
```  
class COleDispatchException : public CException  
```  
  
## Membres  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDispatchException::m\_dwHelpContext](../Topic/COleDispatchException::m_dwHelpContext.md)|Contexte d'aide pour l'erreur.|  
|[COleDispatchException::m\_strDescription](../Topic/COleDispatchException::m_strDescription.md)|Description de l'erreur verbale.|  
|[COleDispatchException::m\_strHelpFile](../Topic/COleDispatchException::m_strHelpFile.md)|Fichier d'aide à utiliser avec `m_dwHelpContext`.|  
|[COleDispatchException::m\_strSource](../Topic/COleDispatchException::m_strSource.md)|Application qui a généré l'exception.|  
|[COleDispatchException::m\_wCode](../Topic/COleDispatchException::m_wCode.md)|`IDispatch`\- code d'erreur spécifique.|  
  
## Notes  
 Comme les autres classes d'exceptions dérivées de la classe de base d' `CException` , `COleDispatchException` peut être utilisé avec **directionnel**, `THROW_LAST`, **TRY**, **collecteur**, `AND_CATCH`, les macros et d' `END_CATCH` .  
  
 En général vous devez appeler [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md) pour créer et lever un objet d' `COleDispatchException` .  
  
 Pour plus d'informations sur les exceptions, consultez les articles [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md) et [exceptions : Exceptions OLE](../../mfc/exceptions-ole-exceptions.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## Configuration requise  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [exemple MFC CALCDRIV](../../top/visual-cpp-samples.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDispatchDriver Class](../../mfc/reference/coledispatchdriver-class.md)   
 [COleException Class](../../mfc/reference/coleexception-class.md)