---
title: "Contr&#244;les ActiveX MFC&#160;: ajout de m&#233;thodes personnalis&#233;es | Microsoft Docs"
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
  - "contrôles ActiveX MFC, méthodes"
  - "PtInCircle (méthode personnalisée)"
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: ajout de m&#233;thodes personnalis&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Custom methods differ from stock methods in that they are not already implemented by `COleControl`.  You must supply the implementation for each custom method you add to your control.  
  
 An ActiveX control user can call a custom method at any time to perform control\-specific actions.  The dispatch map entry for custom methods is of the form `DISP_FUNCTION`.  
  
##  <a name="_core_adding_a_custom_method_with_classwizard"></a> Adding a Custom Method With the Add Method Wizard  
 The following procedure demonstrates adding the custom method PtInCircle to an ActiveX control's skeleton code.  PtInCircle determines whether the coordinates passed to the control are inside or outside the circle.  This same procedure can also be used to add other custom methods.  Substitute your custom method name and its parameters for the PtInCircle method name and parameters.  
  
> [!NOTE]
>  This example uses the `InCircle` function from the article Events.  For more information on this function, see the article [MFC ActiveX Controls: Adding Custom Events to an ActiveX Control](../mfc/mfc-activex-controls-adding-custom-events.md).  
  
#### To add the PtInCircle custom method using the Add Method Wizard  
  
1.  Load the control's project.  
  
2.  In Class View, expand the library node of your control.  
  
3.  Right\-click the interface node for your control \(the second node of the library node\) to open the shortcut menu.  
  
4.  From the shortcut menu, click **Add** and then click **Add Method**.  
  
     This opens the Add Method Wizard.  
  
5.  In the **Method Name** box, type `PtInCircle`.  
  
6.  In the **Internal Name** box, type the name of the method's internal function or use the default value \(in this case, `PtInCircle`\).  
  
7.  In the **Return Type** box, click **VARIANT\_BOOL** for the method's return type.  
  
8.  Using the **Parameter Type** and **Parameter Name** controls, add a parameter called `xCoord` \(type **OLE\_XPOS\_PIXELS**\).  
  
9. Using the **Parameter Type** and **Parameter Name** controls, add a parameter called `yCoord` \(type **OLE\_YPOS\_PIXELS**\).  
  
10. Cliquez sur **Terminer**.  
  
##  <a name="_core_classwizard_changes_for_custom_methods"></a> Add Method Wizard Changes for Custom Methods  
 When you add a custom method, the Add Method Wizard makes some changes to the control class header \(.H\) and implementation \(.CPP\) files.  The following line is added to the dispatch map declaration in the control class header \(.H\) file:  
  
 [!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-methods_1.h)]  
  
 This code declares a dispatch method handler called `PtInCircle`.  This function can be called by the control user using the external name PtInCircle.  
  
 The following line is added to the control's .IDL file:  
  
 [!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-methods_2.idl)]  
  
 This line assigns the PtInCircle method a specific ID number, the method's position in the Add Method Wizard methods and properties list.  Because the Add Method Wizard was used to add the custom method, the entry for it was added automatically to the project's .IDL file.  
  
 In addition, the following line, located in the implementation \(.CPP\) file of the control class, is added to the control's dispatch map:  
  
 [!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-methods_3.cpp)]  
  
 The `DISP_FUNCTION` macro maps the method PtInCircle to the control's handler function, `PtInCircle`, declares the return type to be **VARIANT\_BOOL**, and declares two parameters of type **VTS\_XPOS\_PIXELS** and **VTS\_YPOSPIXELS** to be passed to `PtInCircle`.  
  
 Finally, the Add Method Wizard adds the stub function `CSampleCtrl::PtInCircle` to the bottom of the control's implementation \(.CPP\) file.  For `PtInCircle` to function as stated previously, it must be modified as follows:  
  
 [!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-methods_4.cpp)]  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Affichage de classes et Explorateur d'objets, icônes](../Topic/Class%20View%20and%20Object%20Browser%20Icons.md)