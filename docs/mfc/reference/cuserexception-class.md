---
title: "CUserException Class | Microsoft Docs"
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
  - "CUserException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserException class"
  - "erreurs (C++), intercepter"
  - "exceptions, lever"
  - "operations [C++]"
  - "operations [C++], arrêter"
  - "lever des exceptions, stopping user operations"
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUserException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Levée pour arrêter une opération d'utilisateur.  
  
## Syntaxe  
  
```  
class CUserException : public CSimpleException  
```  
  
## Notes  
 Utilisation `CUserException` lorsque vous souhaitez utiliser le mécanisme d'exception throw\/Catch pour des exceptions spécifiques à l'application. "  L'utilisateur » dans le nom de classe peut être interprète comme « mon utilisateur a exécute une action exceptionnelle que je dois traiter. »  
  
 `CUserException` est généralement levée après avoir appelé la fonction globale `AfxMessageBox` pour informer l'utilisateur qu'une opération a échoué.  Lorsque vous écrivez un gestionnaire d'exceptions, gérez l'exception particulièrement étant donné que l'utilisateur qui a déjà été averti de l'échec.  l'infrastructure lève cette exception dans certains cas.  Pour lever `CUserException` vous\-même, alerter l'utilisateur puis appelez la fonction globale `AfxThrowUserException`.  
  
 Dans l'exemple ci\-dessous, une fonction contenant les opérations susceptibles de provoquer des alertes l'utilisateur et lèvent `CUserException`.  L'appel de la fonction intercepte l'exception et la gère spécialement :  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/CPP/cuserexception-class_1.cpp)]  
  
 Pour plus d'informations sur l'utilisation `CUserException`, consultez l'article [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [AfxMessageBox](../Topic/AfxMessageBox.md)   
 [AfxThrowUserException](../Topic/AfxThrowUserException.md)   
 [Comment faire : Créez mes propres Classes exceptions personnalisées ?](http://go.microsoft.com/fwlink/?LinkId=128045)