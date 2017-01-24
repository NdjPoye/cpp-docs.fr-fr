---
title: "CMFCVisualManager Class | Microsoft Docs"
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
  - "CMFCVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManager class"
ms.assetid: beed80f7-36a2-4d64-9f09-e807cfefc3fe
caps.latest.revision: 58
caps.handback.revision: 46
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCVisualManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit la prise en charge de modifier l'apparence de votre application à un niveau global.  La classe d' `CMFCVisualManager` collabore avec une classe qui fournit des instructions de dessiner des contrôles d'interface GUI de votre application à l'aide d'un style cohérent.  Ces autres classes sont mentionnées comme visuel des gestionnaires et il hérite d' `CMFCBaseVisualManager`.  
  
## Syntaxe  
  
```  
class CMFCVisualManager : public CMFCBaseVisualManager  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCVisualManager::CMFCVisualManager`|Constructeur par défaut.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCVisualManager::AdjustFrames](../Topic/CMFCVisualManager::AdjustFrames.md)||  
|[CMFCVisualManager::AdjustToolbars](../Topic/CMFCVisualManager::AdjustToolbars.md)||  
|[CMFCVisualManager::AlwaysHighlight3DTabs](../Topic/CMFCVisualManager::AlwaysHighlight3DTabs.md)|Appelé par l'infrastructure pour déterminer si les onglets 3D doivent toujours être dessinés à l'aide d'une couleur de surbrillance.|  
|[CMFCVisualManager::DestroyInstance](../Topic/CMFCVisualManager::DestroyInstance.md)||  
|[CMFCVisualManager::DoDrawHeaderSortArrow](../Topic/CMFCVisualManager::DoDrawHeaderSortArrow.md)||  
|[CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md)||  
|[CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md)||  
|[CMFCVisualManager::DrawTextOnGlass](../Topic/CMFCVisualManager::DrawTextOnGlass.md)||  
|[CMFCVisualManager::GetAutoHideButtonTextColor](../Topic/CMFCVisualManager::GetAutoHideButtonTextColor.md)|Appelé par l'infrastructure pour récupérer la couleur de texte pour un bouton de masquer automatiquement.|  
|[CMFCVisualManager::GetButtonExtraBorder](../Topic/CMFCVisualManager::GetButtonExtraBorder.md)|Appelé par l'infrastructure pour récupérer la taille augmentée de bouton dont le gestionnaire visuel actuel a besoin pour dessiner un bouton.|  
|[CMFCVisualManager::GetCaptionBarTextColor](../Topic/CMFCVisualManager::GetCaptionBarTextColor.md)|Appelé par l'infrastructure pour récupérer la couleur du texte d'une barre de légende.|  
|[CMFCVisualManager::GetDockingTabsBordersSize](../Topic/CMFCVisualManager::GetDockingTabsBordersSize.md)|Appelé par l'infrastructure pour récupérer la taille de la bordure d'une barre à ancrée onglet.|  
|[CMFCVisualManager::GetHighlightedMenuItemTextColor](../Topic/CMFCVisualManager::GetHighlightedMenuItemTextColor.md)||  
|[CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)|Retourne un pointeur vers l'objet d' `CMFCVisualManager` .|  
|[CMFCVisualManager::GetMDITabsBordersSize](../Topic/CMFCVisualManager::GetMDITabsBordersSize.md)|Appelé par l'infrastructure pour récupérer la taille de la bordure de la fenêtre de MDITabs.|  
|[CMFCVisualManager::GetMenuItemTextColor](../Topic/CMFCVisualManager::GetMenuItemTextColor.md)||  
|[CMFCVisualManager::GetMenuShadowDepth](../Topic/CMFCVisualManager::GetMenuShadowDepth.md)|Retourne une valeur qui détermine la largeur et la hauteur d'une ombre de menu.|  
|[CMFCVisualManager::GetNcBtnSize](../Topic/CMFCVisualManager::GetNcBtnSize.md)|Appelé par l'infrastructure pour déterminer la taille du système boutons selon le gestionnaire visuel actuel.  Les boutons de système sont les boutons dans la légende du frame principal qui mappent aux commandes **Fermer**, **Réduire**, **Agrandir**, et **Restaurer**.|  
|[CMFCVisualManager::GetPopupMenuBorderSize](../Topic/CMFCVisualManager::GetPopupMenuBorderSize.md)|Appelé par l'infrastructure pour récupérer la taille de la bordure pour un menu contextuel.|  
|[CMFCVisualManager::GetPropertyGridGroupColor](../Topic/CMFCVisualManager::GetPropertyGridGroupColor.md)|Appelé par l'infrastructure pour récupérer la couleur d'arrière\-plan d'une liste de propriétés.|  
|[CMFCVisualManager::GetPropertyGridGroupTextColor](../Topic/CMFCVisualManager::GetPropertyGridGroupTextColor.md)|Appelé par l'infrastructure pour récupérer la couleur du texte d'une liste de propriétés.|  
|[CMFCVisualManager::GetRibbonHyperlinkTextColor](../Topic/CMFCVisualManager::GetRibbonHyperlinkTextColor.md)||  
|[CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md)||  
|[CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor.md)||  
|[CMFCVisualManager::GetRibbonSliderColors](../Topic/CMFCVisualManager::GetRibbonSliderColors.md)||  
|[CMFCVisualManager::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManager::GetShowAllMenuItemsHeight.md)||  
|[CMFCVisualManager::GetSmartDockingBaseGuideColors](../Topic/CMFCVisualManager::GetSmartDockingBaseGuideColors.md)||  
|[CMFCVisualManager::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManager::GetSmartDockingHighlightToneColor.md)||  
|[CMFCVisualManager::GetSmartDockingTheme](../Topic/CMFCVisualManager::GetSmartDockingTheme.md)|Retourne un thème utilisé pour afficher le intelligentes d'ancrage.|  
|[CMFCVisualManager::GetStatusBarPaneTextColor](../Topic/CMFCVisualManager::GetStatusBarPaneTextColor.md)||  
|[CMFCVisualManager::GetTabFrameColors](../Topic/CMFCVisualManager::GetTabFrameColors.md)|Appelé par l'infrastructure pour récupérer le jeu de couleurs pour utiliser lorsqu'il dessine un frame d'onglet.|  
|[CMFCVisualManager::GetTabTextColor](../Topic/CMFCVisualManager::GetTabTextColor.md)||  
|[CMFCVisualManager::GetToolbarButtonTextColor](../Topic/CMFCVisualManager::GetToolbarButtonTextColor.md)|Appelé par l'infrastructure pour récupérer la couleur actuelle du texte sur le bouton de barre d'outils.  Cette couleur varie en fonction de le gestionnaire visuel actuel et l'état du bouton.|  
|[CMFCVisualManager::GetToolbarDisabledTextColor](../Topic/CMFCVisualManager::GetToolbarDisabledTextColor.md)|Appelé par l'infrastructure pour déterminer la couleur du texte affiché sur les éléments désactivés de barre d'outils.|  
|[CMFCVisualManager::GetToolbarHighlightColor](../Topic/CMFCVisualManager::GetToolbarHighlightColor.md)||  
|[CMFCVisualManager::GetToolTipInfo](../Topic/CMFCVisualManager::GetToolTipInfo.md)||  
|[CMFCVisualManager::HasOverlappedAutoHideButtons](../Topic/CMFCVisualManager::HasOverlappedAutoHideButtons.md)|Spécifie si masquer automatiquement la superposition de boutons.|  
|[CMFCVisualManager::IsDockingTabHasBorder](../Topic/CMFCVisualManager::IsDockingTabHasBorder.md)|Spécifie si le gestionnaire visuel actuel dessine une bordure autour de les barres avec onglets d'ancrage.|  
|[CMFCVisualManager::IsEmbossDisabledImage](../Topic/CMFCVisualManager::IsEmbossDisabledImage.md)|Spécifie si les images désactivées doivent être données de relief.|  
|[CMFCVisualManager::IsFadeInactiveImage](../Topic/CMFCVisualManager::IsFadeInactiveImage.md)|Appelé par l'infrastructure pour déterminer si les images inactives d'une barre d'outils ou de menu apparaissent estompées.|  
|[CMFCVisualManager::IsMenuFlatLook](../Topic/CMFCVisualManager::IsMenuFlatLook.md)|Spécifie si les boutons de menu ont une apparence aplatie.|  
|[CMFCVisualManager::IsOfficeXPStyleMenus](../Topic/CMFCVisualManager::IsOfficeXPStyleMenus.md)|Spécifie si le gestionnaire visuel implémente les menus de style de la XP Office.|  
|[CMFCVisualManager::IsOwnerDrawCaption](../Topic/CMFCVisualManager::IsOwnerDrawCaption.md)|Spécifie si le gestionnaire visuel actuel implémente les légendes owner\-drawn d'une fenêtre frame.|  
|[CMFCVisualManager::IsShadowHighlightedImage](../Topic/CMFCVisualManager::IsShadowHighlightedImage.md)|Spécifie si une image en surbrillance a une ombre.|  
|[CMFCVisualManager::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManager::OnDrawAutoHideButtonBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure d'un bouton de masquer automatiquement.|  
|[CMFCVisualManager::OnDrawBarGripper](../Topic/CMFCVisualManager::OnDrawBarGripper.md)|Appelé par l'infrastructure lorsqu'il dessine la pince d'une barre de contrôles.  L'utilisateur doit cliquer sur la pince pour déplacer la barre de contrôles.|  
|[CMFCVisualManager::OnDrawBrowseButton](../Topic/CMFCVisualManager::OnDrawBrowseButton.md)|Appelé par l'infrastructure lorsqu'il dessine un bouton Parcourir qui appartient à un contrôle d'édition \([CMFCEditBrowseCtrl Class](../../mfc/reference/cmfceditbrowsectrl-class.md)\).|  
|[CMFCVisualManager::OnDrawButtonBorder](../Topic/CMFCVisualManager::OnDrawButtonBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure d'un bouton de barre d'outils.|  
|[CMFCVisualManager::OnDrawButtonSeparator](../Topic/CMFCVisualManager::OnDrawButtonSeparator.md)||  
|[CMFCVisualManager::OnDrawCaptionBarBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarBorder.md)|Appelé par l'infrastructure lorsqu'il dessine la bordure de la barre de légende.|  
|[CMFCVisualManager::OnDrawCaptionBarButtonBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarButtonBorder.md)||  
|[CMFCVisualManager::OnDrawCaptionBarInfoArea](../Topic/CMFCVisualManager::OnDrawCaptionBarInfoArea.md)||  
|[CMFCVisualManager::OnDrawCaptionButton](../Topic/CMFCVisualManager::OnDrawCaptionButton.md)|Appelé par l'infrastructure lorsqu'il dessine un bouton de légende.|  
|[CMFCVisualManager::OnDrawCheckBox](../Topic/CMFCVisualManager::OnDrawCheckBox.md)||  
|[CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md)||  
|[CMFCVisualManager::OnDrawComboBorder](../Topic/CMFCVisualManager::OnDrawComboBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure d'un bouton de zone de liste déroulante.|  
|[CMFCVisualManager::OnDrawComboDropButton](../Topic/CMFCVisualManager::OnDrawComboDropButton.md)|Appelé par l'infrastructure lorsqu'il dessine un bouton de déplacement de la zone de liste déroulante.|  
|[CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md)||  
|[CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md)|Appelé par l'infrastructure lorsqu'il dessine l'image par défaut du ruban.|  
|[CMFCVisualManager::OnDrawEditBorder](../Topic/CMFCVisualManager::OnDrawEditBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure autour d'un objet de [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) .|  
|[CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md)||  
|[CMFCVisualManager::OnDrawFloatingToolbarBorder](../Topic/CMFCVisualManager::OnDrawFloatingToolbarBorder.md)|Appelé par l'infrastructure lorsqu'il dessine des zones d'une barre d'outils flottante.  La barre d'outils flottante est une barre d'outils qui apparaît comme une fenêtre mini\-frame.|  
|[CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure qui contient le contrôle header.|  
|[CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManager::OnDrawHeaderCtrlSortArrow.md)|Appelé par l'infrastructure lorsqu'il dessine la flèche de tri de contrôle header.|  
|[CMFCVisualManager::OnDrawMenuArrowOnCustomizeList](../Topic/CMFCVisualManager::OnDrawMenuArrowOnCustomizeList.md)||  
|[CMFCVisualManager::OnDrawMenuBorder](../Topic/CMFCVisualManager::OnDrawMenuBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure de menu.|  
|[CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md)||  
|[CMFCVisualManager::OnDrawMenuItemButton](../Topic/CMFCVisualManager::OnDrawMenuItemButton.md)||  
|[CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md)||  
|[CMFCVisualManager::OnDrawMenuResizeBar](../Topic/CMFCVisualManager::OnDrawMenuResizeBar.md)||  
|[CMFCVisualManager::OnDrawMenuScrollButton](../Topic/CMFCVisualManager::OnDrawMenuScrollButton.md)|Appelé par l'infrastructure lorsqu'il dessine un bouton de défilement de menu.|  
|[CMFCVisualManager::OnDrawMenuShadow](../Topic/CMFCVisualManager::OnDrawMenuShadow.md)||  
|[CMFCVisualManager::OnDrawMenuSystemButton](../Topic/CMFCVisualManager::OnDrawMenuSystemButton.md)|Appelé par l'infrastructure lorsqu'il dessine le système de menus, boutons **FermerRéduire**, **Agrandir**, et **Restaurer**.|  
|[CMFCVisualManager::OnDrawMiniFrameBorder](../Topic/CMFCVisualManager::OnDrawMiniFrameBorder.md)||  
|[CMFCVisualManager::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManager::OnDrawOutlookBarSplitter.md)|Appelé par l'infrastructure lorsqu'il dessine le séparateur pour une barre Outlook.  Le séparateur est une barre horizontale utilisée pour les contrôles de groupe.|  
|[CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure d'un bouton de page Outlook.  Les boutons de page Outlook s'affiche si le volet de barre Outlook contient plus de boutons qu'il peut afficher.|  
|[CMFCVisualManager::OnDrawPaneBorder](../Topic/CMFCVisualManager::OnDrawPaneBorder.md)|Appelé par l'infrastructure lorsqu'il dessine la bordure de [CPane Class](../../mfc/reference/cpane-class.md).|  
|[CMFCVisualManager::OnDrawPaneCaption](../Topic/CMFCVisualManager::OnDrawPaneCaption.md)|Appelé par l'infrastructure lorsqu'il dessine la légende pour `CPane`.|  
|[CMFCVisualManager::OnDrawPaneDivider](../Topic/CMFCVisualManager::OnDrawPaneDivider.md)||  
|[CMFCVisualManager::OnDrawPopupWindowBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowButtonBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowCaption](../Topic/CMFCVisualManager::OnDrawPopupWindowCaption.md)||  
|[CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md)|Appelé par l'infrastructure lorsqu'il dessine **bouton principal** sur le ruban.|  
|[CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure d'un bouton de ruban.|  
|[CMFCVisualManager::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManager::OnDrawRibbonButtonsGroup.md)|Appelé par l'infrastructure lorsqu'il dessine un groupe de boutons sur le ruban.|  
|[CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md)|Appelé par l'infrastructure lorsqu'il dessine la légende du frame principal, mais uniquement si la barre de ruban est intégrée au frame.|  
|[CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md)|Appelé par l'infrastructure lorsqu'il dessine un bouton de légende située dans la barre de ruban.|  
|[CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md)|Appelé par l'infrastructure lorsqu'il dessine une catégorie ruban.|  
|[CMFCVisualManager::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManager::OnDrawRibbonCategoryCaption.md)|Appelé par l'infrastructure lorsqu'il dessine la légende pour une catégorie ruban.|  
|[CMFCVisualManager::OnDrawRibbonCategoryScroll](../Topic/CMFCVisualManager::OnDrawRibbonCategoryScroll.md)||  
|[CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md)|Appelé par l'infrastructure lorsqu'il dessine l'onglet pour une catégorie ruban.|  
|[CMFCVisualManager::OnDrawRibbonCheckBoxOnList](../Topic/CMFCVisualManager::OnDrawRibbonCheckBoxOnList.md)||  
|[CMFCVisualManager::OnDrawRibbonColorPaletteBox](../Topic/CMFCVisualManager::OnDrawRibbonColorPaletteBox.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md)|Appelé par l'infrastructure lorsqu'il dessine le bouton par défaut de volet de ruban.  Le bouton par défaut s'affiche lorsque l'utilisateur réduite un panneau de ruban afin qu'il soit trop petit pour afficher les éléments du ruban.  Le bouton par défaut est dessiné à la place et les éléments du ruban sont ajoutés comme éléments dans un menu liste déroulante.|  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryBorder](../Topic/CMFCVisualManager::OnDrawRibbonGalleryBorder.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md)||  
|[CMFCVisualManager::OnDrawRibbonKeyTip](../Topic/CMFCVisualManager::OnDrawRibbonKeyTip.md)||  
|[CMFCVisualManager::OnDrawRibbonLabel](../Topic/CMFCVisualManager::OnDrawRibbonLabel.md)|Appelé par l'infrastructure lorsqu'il dessine l'étiquette du ruban.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure d'un bouton de ruban qui est positionné sur le panneau **Principal** .  Le panneau **Principal** est le panneau qui apparaît lorsqu'un utilisateur clique sur **bouton principal**.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelFrame](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelFrame.md)|Appelé par l'infrastructure lorsqu'il dessine le cadre autour de le panneau **Principal** .|  
|[CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md)||  
|[CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md)|Appelé par l'infrastructure lorsqu'il dessine un panneau de ruban.|  
|[CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md)|Appelé par l'infrastructure lorsqu'il dessine la légende d'un panneau de ruban.|  
|[CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md)|Appelé par l'infrastructure lorsqu'il dessine un objet de [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) .|  
|[CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator](../Topic/CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator.md)|Appelé par l'infrastructure lorsqu'il dessine un séparateur sur **Barre d'outils Accès rapide**d'un ruban.|  
|[CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md)|Appelé par l'infrastructure lorsqu'il dessine un cadre autour d'une liste de fichiers récente.|  
|[CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md)|Appelé par l'infrastructure lorsqu'il dessine le canal d'un objet de [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) .|  
|[CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md)|Appelé par l'infrastructure lorsqu'il dessine le curseur d'un objet d' `CMFCRibbonSlider` .|  
|[CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md)|Appelé par l'infrastructure lorsqu'il dessine des boutons de zoom d'un objet d' `CMFCRibbonSlider` .|  
|[CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md)|Appelé par l'infrastructure lorsqu'il dessine le volet de barre d'état d'un ruban.|  
|[CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md)|Appelé par l'infrastructure lorsqu'il dessine un cadre autour d'un groupe d'onglets du ruban.|  
|[CMFCVisualManager::OnDrawScrollButtons](../Topic/CMFCVisualManager::OnDrawScrollButtons.md)||  
|[CMFCVisualManager::OnDrawSeparator](../Topic/CMFCVisualManager::OnDrawSeparator.md)|Appelé par l'infrastructure lorsqu'il dessine un séparateur.  Le séparateur est généralement utilisé sur une barre de contrôles pour séparer des groupes d'icônes.|  
|[CMFCVisualManager::OnDrawShowAllMenuItems](../Topic/CMFCVisualManager::OnDrawShowAllMenuItems.md)||  
|[CMFCVisualManager::OnDrawSpinButtons](../Topic/CMFCVisualManager::OnDrawSpinButtons.md)|Appelé par l'infrastructure lorsqu'il dessine des toupies.|  
|[CMFCVisualManager::OnDrawSplitterBorder](../Topic/CMFCVisualManager::OnDrawSplitterBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure d'une fenêtre fractionnée.|  
|[CMFCVisualManager::OnDrawSplitterBox](../Topic/CMFCVisualManager::OnDrawSplitterBox.md)|Appelé par l'infrastructure lorsqu'il dessine la zone de glisser\-déplacer de séparateur pour une fenêtre fractionnée.|  
|[CMFCVisualManager::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManager::OnDrawStatusBarPaneBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure pour un volet de barre d'état.|  
|[CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md)|Appelé par l'infrastructure lorsqu'il dessine l'indicateur de progression de barre d'état.|  
|[CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md)|Appelé par l'infrastructure lorsqu'il dessine la zone de taille de barre d'état.|  
|[CMFCVisualManager::OnDrawTab](../Topic/CMFCVisualManager::OnDrawTab.md)|Appelé par l'infrastructure lorsqu'il dessine un objet de [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) .|  
|[CMFCVisualManager::OnDrawTabCloseButton](../Topic/CMFCVisualManager::OnDrawTabCloseButton.md)|Appelé par l'infrastructure lorsqu'il dessine le bouton **Fermer** sur l'onglet actif.|  
|[CMFCVisualManager::OnDrawTabContent](../Topic/CMFCVisualManager::OnDrawTabContent.md)|Appelé par l'infrastructure lorsqu'il dessine l'intérieur de l'onglet \(images, texte\).|  
|[CMFCVisualManager::OnDrawTabsButtonBorder](../Topic/CMFCVisualManager::OnDrawTabsButtonBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure d'un bouton d'onglet.|  
|[CMFCVisualManager::OnDrawTask](../Topic/CMFCVisualManager::OnDrawTask.md)|Appelé par l'infrastructure lorsqu'il dessine une tâche dans le volet de tâches.|  
|[CMFCVisualManager::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManager::OnDrawTasksGroupAreaBorder.md)|Appelé par l'infrastructure lorsqu'il dessine une bordure autour d'une zone de groupe dans le volet de tâches.|  
|[CMFCVisualManager::OnDrawTasksGroupCaption](../Topic/CMFCVisualManager::OnDrawTasksGroupCaption.md)|Appelé par l'infrastructure lorsqu'il dessine la légende pour un groupe de tâches dans le volet de tâches.|  
|[CMFCVisualManager::OnDrawTasksGroupIcon](../Topic/CMFCVisualManager::OnDrawTasksGroupIcon.md)||  
|[CMFCVisualManager::OnDrawTearOffCaption](../Topic/CMFCVisualManager::OnDrawTearOffCaption.md)|Appelé par l'infrastructure lorsqu'il dessine la légende d'arrachement pour une barre d'arrachement.|  
|[CMFCVisualManager::OnDrawToolBoxFrame](../Topic/CMFCVisualManager::OnDrawToolBoxFrame.md)||  
|[CMFCVisualManager::OnEraseMDIClientArea](../Topic/CMFCVisualManager::OnEraseMDIClientArea.md)|Appelé par l'infrastructure lorsqu'il efface la zone cliente MDI.|  
|[CMFCVisualManager::OnErasePopupWindowButton](../Topic/CMFCVisualManager::OnErasePopupWindowButton.md)||  
|[CMFCVisualManager::OnEraseTabsArea](../Topic/CMFCVisualManager::OnEraseTabsArea.md)|Appelé par l'infrastructure lorsqu'il efface la zone d'onglet dans une fenêtre d'onglet.|  
|[CMFCVisualManager::OnEraseTabsButton](../Topic/CMFCVisualManager::OnEraseTabsButton.md)|Appelé par l'infrastructure lorsqu'il efface l'icône et le texte d'un bouton d'onglet.|  
|[CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md)|Appelé par l'infrastructure lorsqu'il supprime un frame d'onglet.|  
|[CMFCVisualManager::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManager::OnFillAutoHideButtonBackground.md)|Appelé par l'infrastructure lorsqu'il remplit arrière\-plan d'un bouton de masquer automatiquement.|  
|[CMFCVisualManager::OnFillBarBackground](../Topic/CMFCVisualManager::OnFillBarBackground.md)|Appelé par l'infrastructure lorsqu'il remplit arrière\-plan d'une barre de contrôles.|  
|[CMFCVisualManager::OnFillButtonInterior](../Topic/CMFCVisualManager::OnFillButtonInterior.md)|Appelé par l'infrastructure lorsqu'il remplit arrière\-plan d'un bouton de barre d'outils.|  
|[CMFCVisualManager::OnFillCaptionBarButton](../Topic/CMFCVisualManager::OnFillCaptionBarButton.md)||  
|[CMFCVisualManager::OnFillCommandsListBackground](../Topic/CMFCVisualManager::OnFillCommandsListBackground.md)|Appelé par l'infrastructure lorsqu'il remplit arrière\-plan d'un bouton de barre d'outils qui appartient à une commande dossier qui, ensuite, fait partie d'une boîte de dialogue personnalisation.|  
|[CMFCVisualManager::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManager::OnFillHeaderCtrlBackground.md)|Appelé par l'infrastructure lorsqu'elle remplit arrière\-plan d'un contrôle header.|  
|[CMFCVisualManager::OnFillMiniFrameCaption](../Topic/CMFCVisualManager::OnFillMiniFrameCaption.md)|Appelé par l'infrastructure lorsqu'elle remplit légende d'un mini fenêtre frame.|  
|[CMFCVisualManager::OnFillOutlookBarCaption](../Topic/CMFCVisualManager::OnFillOutlookBarCaption.md)|Appelé par l'infrastructure lorsqu'elle remplit arrière\-plan d'une légende de barre Outlook.|  
|[CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md)|Appelé par l'infrastructure lorsqu'elle remplit intérieur d'un bouton de page Outlook.|  
|[CMFCVisualManager::OnFillPopupWindowBackground](../Topic/CMFCVisualManager::OnFillPopupWindowBackground.md)|Appelé par l'infrastructure lorsqu'elle remplit arrière\-plan d'une fenêtre contextuelle.|  
|[CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md)|Appelé par l'infrastructure lorsqu'elle remplit intérieur d'un bouton de ruban.|  
|[CMFCVisualManager::OnFillRibbonEdit](../Topic/CMFCVisualManager::OnFillRibbonEdit.md)|Appelé par l'infrastructure lorsqu'elle remplit intérieur d'un contrôle d'édition du ruban.|  
|[CMFCVisualManager::OnFillRibbonMainPanelButton](../Topic/CMFCVisualManager::OnFillRibbonMainPanelButton.md)|Appelé par l'infrastructure lorsqu'elle remplit intérieur d'un bouton de ruban trouve dans le panneau **Principal** .|  
|[CMFCVisualManager::OnFillRibbonMenuFrame](../Topic/CMFCVisualManager::OnFillRibbonMenuFrame.md)|Appelé par l'infrastructure lorsqu'elle remplit frame de menu dans le volet principal du ruban.|  
|[CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md)||  
|[CMFCVisualManager::OnFillSplitterBackground](../Topic/CMFCVisualManager::OnFillSplitterBackground.md)|Appelé par l'infrastructure lorsqu'elle remplit arrière\-plan d'une fenêtre fractionnée.|  
|[CMFCVisualManager::OnFillTab](../Topic/CMFCVisualManager::OnFillTab.md)|Appelé par l'infrastructure lorsqu'elle remplit arrière\-plan d'une table.|  
|[CMFCVisualManager::OnFillTasksGroupInterior](../Topic/CMFCVisualManager::OnFillTasksGroupInterior.md)|Appelé par l'infrastructure lorsqu'il remplit intérieur d'un objet de [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) sur [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md).|  
|[CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md)|Appelé par l'infrastructure lorsqu'il remplit l'arrière\-plan d'un contrôle d' `CMFCTasksPane` .|  
|[CMFCVisualManager::OnHighlightMenuItem](../Topic/CMFCVisualManager::OnHighlightMenuItem.md)|Appelé par l'infrastructure lorsqu'il dessine un élément de menu en surbrillance.|  
|[CMFCVisualManager::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManager::OnHighlightRarelyUsedMenuItems.md)|Appelé par l'infrastructure lorsqu'il dessine un élément de menu en surbrillance et rarement utilisé.|  
|[CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md)|Appelé par l'infrastructure lorsqu'il dessine la zone non cliente.|  
|[CMFCVisualManager::OnSetWindowRegion](../Topic/CMFCVisualManager::OnSetWindowRegion.md)|Appelé par l'infrastructure lorsqu'il définit une zone qui contient des frames et des menus instantanés.|  
|[CMFCVisualManager::OnUpdateSystemColors](../Topic/CMFCVisualManager::OnUpdateSystemColors.md)|Appelé par l'infrastructure lorsqu'elle modifie la configuration de couleur système.|  
|[CMFCVisualManager::RedrawAll](../Topic/CMFCVisualManager::RedrawAll.md)|Redessine toutes les barres de contrôles dans l'application.|  
|[CMFCVisualManager::RibbonCategoryColorToRGB](../Topic/CMFCVisualManager::RibbonCategoryColorToRGB.md)||  
|[CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)|Définit le gestionnaire visuel par défaut.|  
|[CMFCVisualManager::SetEmbossDisabledImage](../Topic/CMFCVisualManager::SetEmbossDisabledImage.md)|Active ou désactive le mode en relief pour les images désactivées de barre d'outils.|  
|[CMFCVisualManager::SetFadeInactiveImage](../Topic/CMFCVisualManager::SetFadeInactiveImage.md)|Active ou désactive l'effet de lumière pour les images inactives dans un menu ou une barre d'outils.|  
|[CMFCVisualManager::SetMenuFlatLook](../Topic/CMFCVisualManager::SetMenuFlatLook.md)|Place une balise qui indique si les boutons de menu application ont une apparence aplatie.|  
|[CMFCVisualManager::SetMenuShadowDepth](../Topic/CMFCVisualManager::SetMenuShadowDepth.md)|Définit la largeur et la hauteur de l'ombre de menu.|  
|[CMFCVisualManager::SetShadowHighlightedImage](../Topic/CMFCVisualManager::SetShadowHighlightedImage.md)|Place une balise qui indique s'il faut afficher l'ombre en affichant des images en surbrillance.|  
  
## Notes  
 Étant donné que la classe d' `CMFCVisualManager` contrôle l'interface GUI de l'application, chaque application peut avoir une instance d' `CMFCVisualManager`, ou une instance d'une classe dérivée d' `CMFCVisualManager`.  Votre application peut également s'exécuter sans `CMFCVisualManager`.  Utilisez la méthode statique `GetInstance` pour obtenir un pointeur vers `CMFCVisualManager`actuel objet dérivé.  
  
 Pour modifier l'apparence de votre application vous devez utiliser d'autres classes qui fournissent des méthodes pour dessiner tous les éléments visuels de votre application.  Quelques exemples de ces classes sont [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md), [CMFCVisualManagerOffice2003 Class](../../mfc/reference/cmfcvisualmanageroffice2003-class.md), et [CMFCVisualManagerOffice2007 Class](../../mfc/reference/cmfcvisualmanageroffice2007-class.md).  Lorsque vous souhaitez modifier l'apparence de votre application, passez un de ces gestionnaires visuels dans la méthode `SetDefaultManager`.  Pour obtenir un exemple qui montre comment votre application peut répliquer l'apparence de Microsoft Office 2003, consultez [CMFCVisualManagerOffice2003 Class](../../mfc/reference/cmfcvisualmanageroffice2003-class.md).  
  
 Toutes les méthodes de dessin sont virtuelles.  Cela vous permet de créer un style visuel personnalisé pour l'interface GUI de votre application.  Si vous voulez créer votre propre style visuel, dérivez une classe d'une des classes visuelles de gestionnaire et substituez les méthodes de dessin que vous souhaitez modifier.  
  
## Exemple  
 Cet exemple montre comment instancier des objets standard et personnalisés d' `CMFCVisualManager` .  
  
```  
void CMFCSkinsApp::SetSkin (int iIndex)  
{   // destroy the current visual manager  
   if (CMFCVisualManager::GetInstance () != NULL)  
   {  
      delete CMFCVisualManager::GetInstance ();  
   }  
   switch (iIndex)  
  {  
   case 0:  
      CMFCVisualManager::GetInstance (); // create the standard visual manager  
      break;  
   case 1:  
      new CMyVisualManager (); // create the first custom visual manager  
      break;  
   case 2:  
      new CMacStyle ();  // create the second custom visual manager  
      break;  
   }  
  
   // access the manager and set it properly  
   CMFCVisualManager::GetInstance ()->SetLook2000 ();  
   CMFCVisualManager::GetInstance ()->RedrawAll ();  
}  
```  
  
## Exemple  
 L'exemple suivant montre comment récupérer les valeurs par défaut d'un objet d' `CMFCVisualManager` .  Cet extrait de code fait partie d' [Exemple de volet de tâches](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_TasksPane#1](../../mfc/reference/codesnippet/CPP/cmfcvisualmanager-class_1.h)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxvisualmanager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)   
 [Gestionnaire de visualisation](../../mfc/visualization-manager.md)