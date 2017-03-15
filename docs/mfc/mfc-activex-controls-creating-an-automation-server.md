---
title: "Contr&#244;les ActiveX MFC&#160;: cr&#233;ation d&#39;un serveur Automation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), Automation (serveur)"
  - "Automation (serveurs) (C++), contrôles ActiveX MFC"
  - "contrôles ActiveX MFC (C++), Automation (serveur)"
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Contr&#244;les ActiveX MFC&#160;: cr&#233;ation d&#39;un serveur Automation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You can develop an MFC ActiveX control as an Automation server for the purpose of programmatically embedding that control in another application and calling methods in the control from the application.  Such a control would still be available to be hosted in an ActiveX control container.  
  
### To create a control as an Automation server  
  
1.  [Create](../mfc/reference/mfc-activex-control-wizard.md) the control.  
  
2.  [Add methods](../mfc/mfc-activex-controls-methods.md).  
  
3.  Override [IsInvokeAllowed](../Topic/COleControl::IsInvokeAllowed.md).  Pour plus d'informations, consultez l'article Q146120 de la Base de Connaissances Microsoft.  
  
4.  Génération du contrôle.  
  
### To programmatically access the methods in an Automation server  
  
1.  Create an application, for example, an [MFC exe](../mfc/reference/mfc-application-wizard.md).  
  
2.  At the beginning of the `InitInstance` function, add the following line:  
  
     [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/CPP/mfc-activex-controls-creating-an-automation-server_1.cpp)]  
  
3.  In Class View, right\-click the project node and select **Add class from typelib** to import the type library.  
  
     This will add files with the file name extensions .h and .cpp to the project.  
  
4.  In the header file of the class where you will call one or more methods in the ActiveX control, add the following line: `#include filename.h`, where file name is the name of the header file that was created when you imported the type library.  
  
5.  In the function where a call will be made to a method in the ActiveX control, add code that creates an object of the control's wrapper class and create the ActiveX object.  For example, the following MFC code instantiates a `CCirc` control, gets the Caption property, and displays the result when the OK button is clicked in a dialog box:  
  
     [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/CPP/mfc-activex-controls-creating-an-automation-server_2.cpp)]  
  
 If you add methods to the ActiveX control after you use it in an application, you can begin using the latest version of the control in the application by deleting the files that were created when you imported the type library.  Then import the type library again.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)