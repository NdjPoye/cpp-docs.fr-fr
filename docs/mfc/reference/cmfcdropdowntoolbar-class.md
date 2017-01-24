---
title: "CMFCDropDownToolBar Class | Microsoft Docs"
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
  - "CMFCDropDownToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolBar class"
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une barre d'outils qui s'affiche lorsque l'utilisateur appuie sur et contient un bouton de barre d'outils de niveau supérieur.  
  
## Syntaxe  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](../Topic/CMFCDropDownToolBar::AllowShowOnPaneMenu.md)|\(Substitutions `CPane::AllowShowOnPaneMenu`.\)|  
|[CMFCDropDownToolBar::LoadBitmap](../Topic/CMFCDropDownToolBar::LoadBitmap.md)|\(Substitutions [CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md).\)|  
|[CMFCDropDownToolBar::LoadToolBar](../Topic/CMFCDropDownToolBar::LoadToolBar.md)|\(Substitutions [CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md).\)|  
|[CMFCDropDownToolBar::OnLButtonUp](../Topic/CMFCDropDownToolBar::OnLButtonUp.md)||  
|[CMFCDropDownToolBar::OnMouseMove](../Topic/CMFCDropDownToolBar::OnMouseMove.md)||  
|[CMFCDropDownToolBar::OnSendCommand](../Topic/CMFCDropDownToolBar::OnSendCommand.md)|\(Substitutions `CMFCToolBar::OnSendCommand`.\)|  
|[CMFCDropDownToolBar::OnUpdateCmdUI](../Topic/CMFCDropDownToolBar::OnUpdateCmdUI.md)|\(Substitutions [CMFCToolBar::OnUpdateCmdUI](http://msdn.microsoft.com/fr-fr/571a38ab-2a56-4968-9796-273516126f80).\)|  
  
### Remarques  
 Un objet d' `CMFCDropDownToolBar` combine l'apparence visuelle d'une barre d'outils avec le comportement d'un menu contextuel.  Lorsqu'un utilisateur appuie et de contient un bouton de barre d'outils déroulant \(consultez [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)\), une barre d'outils déroulante s'affiche, et l'utilisateur peut sélectionner un bouton de la barre d'outils déroulante en faisant défiler à celui\-ci et en libérant le bouton de la souris.  Une fois que l'utilisateur sélectionne un bouton dans la barre d'outils déroulante, ce bouton est affiché comme bouton actuellement dans la barre d'outils de niveau supérieur.  
  
 Une barre d'outils déroulante ne peut pas être personnalisée ou ancrée, et il n'a pas d'état d'arrachement.  
  
 l'illustration suivante montre un objet d' `CMFCDropDownToolBar` :  
  
 ![Exemple de CMFCDropDownToolbar](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDown")  
  
 Vous créez un objet d' `CMFCDropDownToolBar` la même façon que vous créez une barre d'outils ordinaire \(consultez [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)\).  
  
 Pour insérer la barre d'outils déroulante dans la barre d'outils parente :  
  
 1.  Réservez un ID de ressource factice pour le bouton dans la ressource parente de barre d'outils.  
  
 2.  Créez un objet d' `CMFCDropDownToolBarButton` qui contient la barre d'outils déroulante \(pour plus d'informations, consultez [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)\).  
  
 3.  Remplacez le bouton factice avec l'objet d' `CMFCDropDownToolBarButton` à l'aide de [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
 Pour plus d'informations sur les boutons de barre d'outils, consultez [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md).  Pour obtenir un exemple d'une barre d'outils déroulante, consultez l'exemple VisualStudioDemo de projet.  
  
## Exemple  
 L'exemple suivant montre comment utiliser la méthode d' `Create` dans la classe d' `CMFCDropDownToolBar` .  Cet extrait de code fait partie d' [Exemple de démonstration de Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/CPP/cmfcdropdowntoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/CPP/cmfcdropdowntoolbar-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## Configuration requise  
 **en\-tête :** afxdropdowntoolbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md)