---
title: "COleException Class | Microsoft Docs"
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
  - "COleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleException class"
  - "exceptions, OLE"
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une condition d'exception liée à une opération OLE.  
  
## Syntaxe  
  
```  
class COleException : public CException  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleException::Process](../Topic/COleException::Process.md)|Traduit une exception interceptée dans OLE code de retour.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleException::m\_sc](../Topic/COleException::m_sc.md)|Contient le code d'état qui indique la raison de l'exception.|  
  
## Notes  
 La classe d' `COleException` inclut une donnée membre publique qui contient le code d'état qui indique la raison de l'exception.  
  
 En général vous ne devez pas créer un objet d' `COleException` directement ; à la place, vous devez appeler [AfxThrowOleException](../Topic/AfxThrowOleException.md).  
  
 Pour plus d'informations sur les exceptions, consultez les articles [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md) et [exceptions : Exceptions OLE](../../mfc/exceptions-ole-exceptions.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## Configuration requise  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [exemple MFC CALCDRIV](../../top/visual-cpp-samples.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)