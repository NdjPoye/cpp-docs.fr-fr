---
title: "Ordre des op&#233;rations pour la cr&#233;ation d&#39;applications OLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications (OLE)"
  - "applications (OLE), créer"
  - "OLE (applications) (C++)"
  - "OLE (applications) (C++), créer"
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ordre des op&#233;rations pour la cr&#233;ation d&#39;applications OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following table shows your role and the framework's role in creating OLE linking and embedding applications.  These represent options available rather than a sequence of steps to perform.  
  
### Creating OLE Applications  
  
|Tâche|You do|The framework does|  
|-----------|------------|------------------------|  
|Create a COM component.|Run the MFC Application Wizard.  Choose **Full\-server** or **Mini\-server** in the **Compound Document Support** tab.|The framework generates a skeleton application with COM component capability enabled.  All of the COM capability can be transferred to your existing application with only slight modification.|  
|Create a container application from scratch.|Run the MFC Application Wizard.  Choose **Container** in the **Compound Document Support** tab.  Using Class View, go to the source code editor.  Fill in code for your COM handler functions.|The framework generates a skeleton application that can insert COM objects created by COM component \(server\) applications.|  
|Create an application that supports Automation from scratch.|Run the MFC Application Wizard.  Choose **Automation** from the **Advanced Features** tab.  Use Class View to expose methods and properties in your application for automation.|The framework generates a skeleton application that can be activated and automated by other applications.|  
  
## Voir aussi  
 [Génération à partir du Framework](../mfc/building-on-the-framework.md)   
 [Ordre des opérations pour la génération d'applications MFC](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Ordre des opérations pour la création de contrôles ActiveX](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [Ordre des opérations pour la création d'applications de base de données](../mfc/sequence-of-operations-for-creating-database-applications.md)