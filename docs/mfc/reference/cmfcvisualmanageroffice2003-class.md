---
title: "CMFCVisualManagerOffice2003 Class | Microsoft Docs"
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
  - "CMFCVisualManagerOffice2003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerOffice2003 class"
ms.assetid: 115482cd-e349-450a-8dc4-c6023d092aab
caps.latest.revision: 31
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCVisualManagerOffice2003 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerOffice2003` donne à une application une apparence Microsoft Office 2003.  
  
## Syntaxe  
  
```  
class CMFCVisualManagerOffice2003 : public CMFCVisualManagerOfficeXP  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCVisualManagerOffice2003::DrawComboBorderWinXP](../Topic/CMFCVisualManagerOffice2003::DrawComboBorderWinXP.md)|Dessine la bordure de la zone de liste déroulante à l'aide de le thème actuel Windows XP.  \(Substitutions [CMFCVisualManager::DrawComboBorderWinXP](../Topic/CMFCVisualManager::DrawComboBorderWinXP.md).\)|  
|[CMFCVisualManagerOffice2003::DrawComboDropButtonWinXP](../Topic/CMFCVisualManagerOffice2003::DrawComboDropButtonWinXP.md)|Dessine un bouton de liste déroulante de la zone de liste déroulante à l'aide de le thème actuel Windows XP.  \(Substitutions [CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md).\)|  
|[CMFCVisualManagerOffice2003::DrawCustomizeButton](../Topic/CMFCVisualManagerOffice2003::DrawCustomizeButton.md)|Dessine un bouton de personnaliser.|  
|[CMFCVisualManagerOffice2003::DrawPushButtonWinXP](../Topic/CMFCVisualManagerOffice2003::DrawPushButtonWinXP.md)|Dessine un bouton de commande à l'aide de le thème actuel Windows XP.  \(Substitutions [CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md).\)|  
|[CMFCVisualManagerOffice2003::GetBaseThemeColor](../Topic/CMFCVisualManagerOffice2003::GetBaseThemeColor.md)|Obtient la couleur de base de thème.|  
|[CMFCVisualManagerOffice2003::GetHighlightMenuItemColor](../Topic/CMFCVisualManagerOffice2003::GetHighlightMenuItemColor.md)|Obtient la couleur utilisée pour l'élément de menu en surbrillance.|  
|[CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../Topic/CMFCVisualManagerOffice2003::GetPropertyGridGroupColor.md)|L'infrastructure appelle cette méthode pour obtenir la couleur d'arrière\-plan d'une liste de propriétés.  \(Substitutions `CMFCVisualManagerOfficeXP::GetPropertyGridGroupColor`.\)|  
|[CMFCVisualManagerOffice2003::GetPropertyGridGroupTextColor](../Topic/CMFCVisualManagerOffice2003::GetPropertyGridGroupTextColor.md)|L'infrastructure appelle cette méthode pour récupérer la couleur du texte d'une liste de propriétés.  \(Substitutions `CMFCVisualManagerOfficeXP::GetPropertyGridGroupTextColor`.\)|  
|[CMFCVisualManagerOffice2003::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManagerOffice2003::GetShowAllMenuItemsHeight.md)|Retourne la hauteur de tous les éléments de menu.  \(Substitutions [CMFCVisualManager::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManager::GetShowAllMenuItemsHeight.md).\)|  
|[CMFCVisualManagerOffice2003::GetSmartDockingBaseGuideColors](../Topic/CMFCVisualManagerOffice2003::GetSmartDockingBaseGuideColors.md)|Définit la couleur d'arrière\-plan spécifiée et la couleur de la bordure de groupe de base.  \(Substitutions `CMFCVisualManagerOfficeXP::GetSmartDockingBaseGuideColors`.\)|  
|[CMFCVisualManagerOffice2003::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManagerOffice2003::GetSmartDockingHighlightToneColor.md)|Obtient la couleur de ton en surbrillance.  \(Substitutions [CMFCVisualManager::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManager::GetSmartDockingHighlightToneColor.md).\)|  
|[CMFCVisualManagerOffice2003::GetTabFrameColors](../Topic/CMFCVisualManagerOffice2003::GetTabFrameColors.md)|L'infrastructure appelle cette fonction lorsqu'il doit extraire le jeu de couleurs pour dessiner une fenêtre d'onglet.  \(Substitutions [CMFCVisualManager::GetTabFrameColors](../Topic/CMFCVisualManager::GetTabFrameColors.md).\)|  
|[CMFCVisualManagerOffice2003::GetToolBarCustomizeButtonMargin](../Topic/CMFCVisualManagerOffice2003::GetToolBarCustomizeButtonMargin.md)|Obtient la marge de la barre d'outils personnaliser le bouton.  \(Substitutions `CMFCVisualManager::GetToolBarCustomizeButtonMargin`.\)|  
|[CMFCVisualManagerOffice2003::GetToolbarDisabledColor](../Topic/CMFCVisualManagerOffice2003::GetToolbarDisabledColor.md)|Obtient la couleur de désactivé pour la barre d'outils.  \(Substitutions `CMFCVisualManager::GetToolbarDisabledColor`.\)|  
|[CMFCVisualManagerOffice2003::GetToolTipInfo](../Topic/CMFCVisualManagerOffice2003::GetToolTipInfo.md)|Appelé par l'infrastructure pour obtenir les informations de l'info\-bulle.  \(Substitutions [CMFCVisualManager::GetToolTipInfo](../Topic/CMFCVisualManager::GetToolTipInfo.md).\)|  
|[CMFCVisualManagerOffice2003::IsDefaultWinXPColorsEnabled](../Topic/CMFCVisualManagerOffice2003::IsDefaultWinXPColorsEnabled.md)|Indique si le thème visuel Windows XP natifs d'utilisation du gestionnaire couleurs.|  
|[CMFCVisualManagerOffice2003::IsDockingTabHasBorder](../Topic/CMFCVisualManagerOffice2003::IsDockingTabHasBorder.md)|Retourne si le gestionnaire visuel actuel dessine des bordures autour de les volets qui sont ancrés et tabulés.  \(Substitutions [CMFCVisualManager::IsDockingTabHasBorder](../Topic/CMFCVisualManager::IsDockingTabHasBorder.md).\)|  
|[CMFCVisualManagerOffice2003::IsHighlightOneNoteTabs](../Topic/CMFCVisualManagerOffice2003::IsHighlightOneNoteTabs.md)|Indique si les onglets OneNote doivent être mis en surbrillance.  \(Substitutions `CMFCVisualManager::IsHighlightOneNoteTabs`.\)|  
|[CMFCVisualManagerOffice2003::IsOffsetPressedButton](../Topic/CMFCVisualManagerOffice2003::IsOffsetPressedButton.md)|Appelé par l'infrastructure en dessinant un bouton de barre d'outils.  \(Substitutions `CMFCVisualManager::IsOffsetPressedButton`.\)|  
|[CMFCVisualManagerOffice2003::IsStatusBarOfficeXPLook](../Topic/CMFCVisualManagerOffice2003::IsStatusBarOfficeXPLook.md)|Indique si une barre d'état avec une apparence Office XP.|  
|[CMFCVisualManagerOffice2003::IsToolbarRoundShape](../Topic/CMFCVisualManagerOffice2003::IsToolbarRoundShape.md)|Indique si une barre d'outils spécifiée a une forme ronde.  \(Substitutions [CMFCVisualManager::IsToolbarRoundShape](../Topic/CMFCVisualManager::IsToolbarRoundShape.md).\)|  
|[CMFCVisualManagerOffice2003::IsUseGlobalTheme](../Topic/CMFCVisualManagerOffice2003::IsUseGlobalTheme.md)|Indique si un thème global Windows XP est utilisé.|  
|[CMFCVisualManagerOffice2003::IsWindowsThemingSupported](../Topic/CMFCVisualManagerOffice2003::IsWindowsThemingSupported.md)|Indique si les thèmes windows en charge.  \(Substitutions [CMFCVisualManager::IsWindowsThemingSupported](../Topic/CMFCVisualManager::IsWindowsThemingSupported.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure d'un bouton de masquer automatiquement.  \(Substitutions [CMFCVisualManager::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManager::OnDrawAutoHideButtonBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawBarGripper](../Topic/CMFCVisualManagerOffice2003::OnDrawBarGripper.md)|Appelé par l'infrastructure lorsqu'il dessine la pince pour une barre de contrôles.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawBarGripper`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawBrowseButton](../Topic/CMFCVisualManagerOffice2003::OnDrawBrowseButton.md)|L'infrastructure appelle cette méthode lorsqu'il dessine le bouton rechercher un contrôle d'édition.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawBrowseButton`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawButtonBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure d'un bouton de barre d'outils.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawButtonBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawCaptionBarBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawCaptionBarBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure d'un objet de [CMFCCaptionBar, Classe](../../mfc/reference/cmfccaptionbar-class.md) .  \(Substitutions [CMFCVisualManager::OnDrawCaptionBarBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerOffice2003::OnDrawCheckBoxEx.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une case à cocher.  \(Substitutions [CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawComboBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawComboBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure autour d'un objet de [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawComboBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawComboDropButton](../Topic/CMFCVisualManagerOffice2003::OnDrawComboDropButton.md)|L'infrastructure appelle cette méthode lorsqu'il dessine le bouton de déplacement de [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawComboDropButton`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawControlBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawControlBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure d'un contrôle.  \(Substitutions [CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawExpandingBox](../Topic/CMFCVisualManagerOffice2003::OnDrawExpandingBox.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une zone développement.  \(Substitutions [CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawHeaderCtrlBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure autour d'une instance de [CMFCHeaderCtrl Class](../../mfc/reference/cmfcheaderctrl-class.md).  \(Substitutions [CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawMenuBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawMenuBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine la bordure de [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md).  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawMenuBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManagerOffice2003::OnDrawOutlookBarSplitter.md)|L'infrastructure appelle cette méthode lorsqu'il dessine le séparateur pour une barre Outlook.  \(Substitutions[CMFCVisualManager::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManager::OnDrawOutlookBarSplitter.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawOutlookPageButtonBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure d'un bouton de page Outlook.  \(Substitutions [CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawPaneBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawPaneBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure d'un objet de [CPane Class](../../mfc/reference/cpane-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawPaneBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPaneCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawPaneCaption.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une légende pour un objet de [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawPaneCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawPopupWindowBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure d'une fenêtre contextuelle.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawPopupWindowBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawPopupWindowButtonBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure d'un bouton dans une fenêtre contextuelle.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawPopupWindowCaption.md)|L'infrastructure appelle cette méthode lorsqu'il dessine la légende d'une fenêtre contextuelle.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawPopupWindowCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonButtonsGroup.md)|L'infrastructure appelle cette méthode lorsqu'il dessine un groupe de boutons sur le ruban.  \(Substitutions [CMFCVisualManager::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManager::OnDrawRibbonButtonsGroup.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonCategoryCaption.md)|L'infrastructure appelle cette méthode lorsqu'il dessine la barre de légende pour une catégorie ruban.  \(Substitutions [CMFCVisualManager::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManager::OnDrawRibbonCategoryCaption.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonCategoryTab.md)|L'infrastructure appelle cette méthode lorsqu'il dessine l'onglet pour une catégorie ruban.  \(Substitutions [CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonProgressBar](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonProgressBar.md)|L'infrastructure appelle cette méthode lorsqu'il dessine [CMFCRibbonProgressBar Class](../../mfc/reference/cmfcribbonprogressbar-class.md).  \(Substitutions [CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonQuickAccessToolBarSeparator](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonQuickAccessToolBarSeparator.md)|L'infrastructure appelle cette méthode lorsqu'il dessine un séparateur dans la Barre d'outils Accès rapide d'un ruban.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawRibbonQuickAccessToolBarSeparator`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonSliderChannel.md)|L'infrastructure appelle cette méthode lorsqu'il dessine le canal de [CMFCRibbonSlider Class](../../mfc/reference/cmfcribbonslider-class.md).  \(Substitutions [CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonSliderThumb.md)|L'infrastructure appelle cette méthode lorsqu'il dessine le curseur d'un objet d' [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) .  \(Substitutions [CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonSliderZoomButton.md)|L'infrastructure appelle cette méthode lorsqu'il dessine des boutons de zoom correspondant à un objet d' [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) .  \(Substitutions [CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonStatusBarPane.md)|L'infrastructure appelle cette méthode lorsqu'il dessine un volet dans la barre d'état.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawRibbonStatusBarPane`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawScrollButtons](../Topic/CMFCVisualManagerOffice2003::OnDrawScrollButtons.md)|L'infrastructure appelle cette méthode lorsqu'il dessine des boutons de défilement.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawScrollButtons`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawSeparator](../Topic/CMFCVisualManagerOffice2003::OnDrawSeparator.md)|L'infrastructure appelle cette méthode lorsqu'il dessine un séparateur.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawSeparator`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawShowAllMenuItems](../Topic/CMFCVisualManagerOffice2003::OnDrawShowAllMenuItems.md)|L'infrastructure appelle cette méthode lorsqu'il dessine tous les éléments d'un menu.  \(Substitutions [CMFCVisualManager::OnDrawShowAllMenuItems](../Topic/CMFCVisualManager::OnDrawShowAllMenuItems.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawStatusBarPaneBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure pour un objet de [CMFCStatusBar Class](../../mfc/reference/cmfcstatusbar-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarProgress](../Topic/CMFCVisualManagerOffice2003::OnDrawStatusBarProgress.md)|L'infrastructure appelle cette méthode lorsqu'il dessine l'indicateur de progression sur l'objet d' [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) .  \(Substitutions [CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerOffice2003::OnDrawStatusBarSizeBox.md)|L'infrastructure appelle cette méthode lorsqu'il dessine la zone de taille pour [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md).  \(Substitutions [CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawTab](../Topic/CMFCVisualManagerOffice2003::OnDrawTab.md)|L'infrastructure appelle cette méthode lorsqu'il dessine des onglets pour un objet de [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawTab`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTabsButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawTabsButtonBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure d'un bouton d'onglet.  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTask](../Topic/CMFCVisualManagerOffice2003::OnDrawTask.md)|L'infrastructure appelle cette méthode lorsqu'il dessine un objet de [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawTask`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawTasksGroupAreaBorder.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une bordure autour d'un groupe sur un objet de [CMFCTasksPane Class](../../mfc/reference/cmfctaskspane-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTasksGroupCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawTasksGroupCaption.md)|L'infrastructure appelle cette méthode lorsqu'il dessine la légende pour un objet de [CMFCTasksPaneTaskGroup Class](../../mfc/reference/cmfctaskspanetaskgroup-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTearOffCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawTearOffCaption.md)|L'infrastructure appelle cette méthode lorsqu'il dessine la légende pour un objet de [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnDrawTearOffCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnErasePopupWindowButton](../Topic/CMFCVisualManagerOffice2003::OnErasePopupWindowButton.md)|L'infrastructure appelle cette méthode lorsqu'elle efface un bouton dans une fenêtre contextuelle.  \(Substitutions `CMFCVisualManagerOfficeXP::OnErasePopupWindowButton`.\)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsArea](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsArea.md)|L'infrastructure appelle cette méthode lorsqu'elle efface la zone de l'onglet de la fenêtre d'onglet.  \(Substitutions `CMFCVisualManagerOfficeXP::OnEraseTabsArea`.\)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsButton](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsButton.md)|L'infrastructure appelle cette méthode lorsqu'elle efface le texte et l'icône d'un bouton d'onglet.  \(Substitutions `CMFCVisualManagerOfficeXP::OnEraseTabsButton`.\)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsFrame](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsFrame.md)|L'infrastructure appelle cette méthode lorsqu'elle efface un frame sur [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md).  \(Substitutions [CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit arrière\-plan d'un bouton de masquer automatiquement.  \(Substitutions [CMFCVisualManager::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManager::OnFillAutoHideButtonBackground.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillBarBackground](../Topic/CMFCVisualManagerOffice2003::OnFillBarBackground.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit arrière\-plan d'un objet de [CBasePane Class](../../mfc/reference/cbasepane-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnFillBarBackground`.\)|  
|[CMFCVisualManagerOffice2003::OnFillButtonInterior](../Topic/CMFCVisualManagerOffice2003::OnFillButtonInterior.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit arrière\-plan d'un bouton de barre d'outils.  \(Substitutions `CMFCVisualManagerOfficeXP::OnFillButtonInterior`.\)|  
|[CMFCVisualManagerOffice2003::OnFillCommandsListBackground](../Topic/CMFCVisualManagerOffice2003::OnFillCommandsListBackground.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit arrière\-plan d'un bouton de barre d'outils qui appartient à une commande dossier.  \(Substitutions `CMFCVisualManagerOfficeXP::OnFillCommandsListBackground`.\)|  
|[CMFCVisualManagerOffice2003::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManagerOffice2003::OnFillHeaderCtrlBackground.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit arrière\-plan d'un contrôle header.  \(Substitutions [CMFCVisualManager::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManager::OnFillHeaderCtrlBackground.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillHighlightedArea](../Topic/CMFCVisualManagerOffice2003::OnFillHighlightedArea.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit une zone en surbrillance d'un bouton de barre d'outils.  \(Substitutions `CMFCVisualManagerOfficeXP::OnFillHighlightedArea`.\)|  
|[CMFCVisualManagerOffice2003::OnFillOutlookBarCaption](../Topic/CMFCVisualManagerOffice2003::OnFillOutlookBarCaption.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit arrière\-plan d'une barre de légende Outlook.  \(Substitutions [CMFCVisualManager::OnFillOutlookBarCaption](../Topic/CMFCVisualManager::OnFillOutlookBarCaption.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillOutlookPageButton](../Topic/CMFCVisualManagerOffice2003::OnFillOutlookPageButton.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit intérieur d'un bouton de page Outlook.  \(Substitutions [CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillPopupWindowBackground](../Topic/CMFCVisualManagerOffice2003::OnFillPopupWindowBackground.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit arrière\-plan d'une fenêtre indépendante.  \(Substitutions `CMFCVisualManagerOfficeXP::OnFillPopupWindowBackground`.\)|  
|[CMFCVisualManagerOffice2003::OnFillTab](../Topic/CMFCVisualManagerOffice2003::OnFillTab.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit arrière\-plan d'une fenêtre d'onglet.  \(Substitutions `CMFCVisualManagerOfficeXP::OnFillTab`.\)|  
|[CMFCVisualManagerOffice2003::OnFillTasksGroupInterior](../Topic/CMFCVisualManagerOffice2003::OnFillTasksGroupInterior.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit intérieur d'un objet de [CMFCTasksPaneTaskGroup Class](../../mfc/reference/cmfctaskspanetaskgroup-class.md) .  \(Substitutions `CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior`.\)|  
|[CMFCVisualManagerOffice2003::OnFillTasksPaneBackground](../Topic/CMFCVisualManagerOffice2003::OnFillTasksPaneBackground.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit l'arrière\-plan d'un contrôle d' [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) .  \(Substitutions [CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md).\)|  
|[CMFCVisualManagerOffice2003::OnHighlightQuickCustomizeMenuButton](../Topic/CMFCVisualManagerOffice2003::OnHighlightQuickCustomizeMenuButton.md)|L'infrastructure appelle cette méthode lorsqu'il dessine en surbrillance rapide personnaliser le bouton de menu.  \(Substitutions `CMFCVisualManagerOfficeXP::OnHighlightQuickCustomizeMenuButton`.\)|  
|[CMFCVisualManagerOffice2003::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManagerOffice2003::OnHighlightRarelyUsedMenuItems.md)|L'infrastructure appelle cette méthode lorsqu'il dessine une commande de menu en surbrillance.  \(Substitutions `CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems`.\)|  
|[CMFCVisualManagerOffice2003::OnUpdateSystemColors](../Topic/CMFCVisualManagerOffice2003::OnUpdateSystemColors.md)|L'infrastructure appelle cette fonction lorsque les couleurs système sont modifiées.  \(Substitutions `CMFCVisualManagerOfficeXP::OnUpdateSystemColors`.\)|  
|[CMFCVisualManagerOffice2003::SetDefaultWinXPColors](../Topic/CMFCVisualManagerOffice2003::SetDefaultWinXPColors.md)|Spécifie si le gestionnaire visuel doit utiliser le natif que thème Windows XP couleurs ou couleurs obtenues à partir de [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371).|  
|[CMFCVisualManagerOffice2003::SetStatusBarOfficeXPLook](../Topic/CMFCVisualManagerOffice2003::SetStatusBarOfficeXPLook.md)|Spécifie que le thème global Windows XP doit être utilisé.|  
|[CMFCVisualManagerOffice2003::SetUseGlobalTheme](../Topic/CMFCVisualManagerOffice2003::SetUseGlobalTheme.md)|Spécifie si le gestionnaire visuel utilise un thème global.|  
  
## Notes  
 Vous utilisez la classe d' `CMFCVisualManagerOffice2003` pour modifier l'apparence visuelle de votre application pour qu'elle ressemble à Microsoft Office 2003.  
  
## Exemple  
 L'exemple suivant montre comment définir le gestionnaire de visuel du bureau 2003.  Cet extrait de code fait partie d' [Exemple d'alerte de démonstration de Bureau](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#6](../../mfc/reference/codesnippet/CPP/cmfcvisualmanageroffice2003-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)  
  
## Configuration requise  
 **En\-tête :** afxvisualmanageroffice2003.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)