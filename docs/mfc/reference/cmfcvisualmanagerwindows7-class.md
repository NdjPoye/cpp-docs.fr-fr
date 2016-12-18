---
title: "CMFCVisualManagerWindows7 Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxvisualmanagerwindows7/CMFCVisualManagerWindows7"
  - "CMFCVisualManagerWindows7"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerWindows7 class"
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCVisualManagerWindows7 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerWindows7` donne à une application de l'apparence d'une application d' [!INCLUDE[win7](../../build/includes/win7_md.md)] .  
  
## Syntaxe  
  
```  
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7.md)|Constructeur par défaut.|  
|[CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7.md)|Est la valeur par défaut le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCVisualManagerWindows7::CleanStyle`|Efface le style visuel actuel et réinitialise le style visuel par défaut.|  
|`CMFCVisualManagerWindows7::CleanUp`|Efface tous les objets de l'interface utilisateur et réinitialise les menus.|  
|`CMFCVisualManagerWindows7::DrawNcBtn`|Dessine un bouton dans la zone non cliente sur le frame.  L'infrastructure utilise la méthode pour dessiner réduit, agrandissent, fermez et boutons de restauration dans le coin supérieur droit du frame de fenêtre.  Cette méthode n'est pas appelée lorsque le programme utilise un thème Aero non.|  
|`CMFCVisualManagerWindows7::DrawNcText`|Dessine du texte dans la zone non cliente sur le frame.  L'infrastructure utilise la méthode pour dessiner le titre de l'application dans la barre de titre en haut de la fenêtre frame.|  
|`CMFCVisualManagerWindows7::DrawSeparator`|Dessine un séparateur sur [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).|  
|`CMFCVisualManagerWindows7::GetRibbonBar`|Récupère [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) associé à l'interface utilisateur.|  
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](../Topic/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor.md)|Obtient une couleur d'arrière\-plan de la zone d'édition du ruban.|  
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|Substitue [CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md)|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|Substitue [CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset.md)|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|Substitue [CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin.md)|  
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|Substitue [CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../Topic/CMFCVisualManagerWindows::IsHighlightWholeMenuItem.md)|  
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|Substitue [CMFCVisualManager::IsOwnerDrawMenuCheck](../Topic/CMFCVisualManager::IsOwnerDrawMenuCheck.md)|  
|`CMFCVisualManagerWindows7::IsRibbonPresent`|Détermine si `CMFCRibbonBar` est présent et visible.|  
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|Substitue [CMFCVisualManagerWindows::OnDrawButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawButtonBorder.md)|  
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|Substitue [CMFCVisualManagerWindows::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerWindows::OnDrawCheckBoxEx.md)|  
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|Substitue [CMFCVisualManagerWindows::OnDrawComboDropButton](../Topic/CMFCVisualManagerWindows::OnDrawComboDropButton.md)|  
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|Substitue [CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md)|  
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|Substitue [CMFCVisualManagerWindows::OnDrawMenuBorder](../Topic/CMFCVisualManagerWindows::OnDrawMenuBorder.md)|  
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|Substitue [CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md)|  
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|Substitue [CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md)|  
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Substitue `CMFCVisualManager::OnDrawRadioButton`|  
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|Substitue [CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|Substitue [CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|Substitue [CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|Substitue [CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|Substitue [CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|Substitue [CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|Substitue [CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|Substitue [CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Substitue `CMFCVisualManager::OnDrawRibbonLaunchButton`|  
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|Substitue [CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|Substitue [CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|Substitue [CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|Substitue [CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|Substitue [CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|Substitue [CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|Substitue [CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|Substitue [CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|Substitue [CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|Substitue [CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md)|  
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|Substitue [CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarSizeBox.md)|  
|`CMFCVisualManagerWindows7::OnFillBarBackground`|Substitue [CMFCVisualManagerWindows::OnFillBarBackground](../Topic/CMFCVisualManagerWindows::OnFillBarBackground.md)|  
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|Substitue [CMFCVisualManagerWindows::OnFillButtonInterior](../Topic/CMFCVisualManagerWindows::OnFillButtonInterior.md)|  
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](../Topic/CMFCVisualManagerWindows7::OnFillMenuImageRect.md)|L'infrastructure appelle cette méthode lorsqu'elle remplit la zone autour de les images d'élément de menu.|  
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|Substitue [CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md)|  
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|Substitue [CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md)|  
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|Substitue [CMFCVisualManagerWindows::OnHighlightMenuItem](../Topic/CMFCVisualManagerWindows::OnHighlightMenuItem.md)|  
|`CMFCVisualManagerWindows7::OnNcActivate`|Substitue [CMFCVisualManager::OnNcActivate](../Topic/CMFCVisualManager::OnNcActivate.md)|  
|`CMFCVisualManagerWindows7::OnNcPaint`|Substitue [CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md)|  
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|Substitue [CMFCVisualManagerWindows::OnUpdateSystemColors](../Topic/CMFCVisualManagerWindows::OnUpdateSystemColors.md)|  
|`CMFCVisualManagerWindows7::SetResourceHandle`|Définit le handle de ressource qui décrit les attributs de gestionnaire visuel.|  
|`CMFCVisualManagerWindows7::SetStyle`|Définit le modèle de couleurs d' `CMFCVisualManagerWindows7` interface GUI.|  
  
## Notes  
 Utilisez la classe d' `CMFCVisualManagerWindows7` pour modifier l'apparence de votre application pour reproduire une application par défaut d' [!INCLUDE[win7](../../build/includes/win7_md.md)] .  Cette classe ne peut pas être valide si votre application s'exécute sur une version de Windows antérieures à [!INCLUDE[win7](../../build/includes/win7_md.md)].  Dans ce cas, l'application utilise le gestionnaire visuel par défaut défini dans [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).  
  
 Le CMFCVisualManagerWindows7 hérite de plusieurs méthodes de [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md) et de la classe d' `CMFCVisualManager` .  Les méthodes répertoriées dans la section précédente sont des nouvelles méthodes à la classe d' `CMFCVisualManagerWindows7` .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
 `CMFCVisualManagerWindows7`  
  
## Configuration requise  
 **en\-tête :** afxvisualmanagerwindows7.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)