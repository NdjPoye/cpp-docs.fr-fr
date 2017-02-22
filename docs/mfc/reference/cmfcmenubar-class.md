---
title: "CMFCMenuBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMenuBar class"
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMFCMenuBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une barre de menus qui implémente l'ancrage.  
  
## Syntaxe  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCMenuBar::AdjustLocations](../Topic/CMFCMenuBar::AdjustLocations.md)|\(Substitutions `CMFCToolBar::AdjustLocations`.\)|  
|[CMFCMenuBar::AllowChangeTextLabels](../Topic/CMFCMenuBar::AllowChangeTextLabels.md)|Spécifie si les étiquettes de texte peuvent être affichées sous des images sur les boutons de barre d'outils.  \(Substitutions [CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md).\)|  
|[CMFCMenuBar::AllowShowOnPaneMenu](../Topic/CMFCMenuBar::AllowShowOnPaneMenu.md)|\(Substitutions `CPane::AllowShowOnPaneMenu`.\)|  
|[CMFCMenuBar::CalcFixedLayout](../Topic/CMFCMenuBar::CalcFixedLayout.md)|Calcule la taille horizontale de la barre d'outils.  \(Substitutions [CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md).\)|  
|[CMFCMenuBar::CalcLayout](../Topic/CMFCMenuBar::CalcLayout.md)|\(Substitutions `CMFCToolBar::CalcLayout`.\)|  
|[CMFCMenuBar::CalcMaxButtonHeight](../Topic/CMFCMenuBar::CalcMaxButtonHeight.md)|Calcule la valeur maximale de boutons dans la barre d'outils.  \(Substitutions [CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md).\)|  
|[CMFCMenuBar::CanBeClosed](../Topic/CMFCMenuBar::CanBeClosed.md)|Spécifie si un utilisateur peut fermer la barre d'outils.  \(Substitutions [CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md).\)|  
|[CMFCMenuBar::CanBeRestored](../Topic/CMFCMenuBar::CanBeRestored.md)|Détermine si le système peut restaurer une barre d'outils à son état d'origine après personnalisation.  \(Substitutions [CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md).\)|  
|[CMFCMenuBar::Create](../Topic/CMFCMenuBar::Create.md)|Crée un contrôle de menu et l'attache à un objet d' `CMFCMenuBar` .|  
|[CMFCMenuBar::CreateEx](../Topic/CMFCMenuBar::CreateEx.md)|Crée un objet d' `CMFCMenuBar` avec des options supplémentaires de style.|  
|[CMFCMenuBar::CreateFromMenu](../Topic/CMFCMenuBar::CreateFromMenu.md)|Initialise un objet `CMFCMenuBar`.  Accepte un paramètre d' `HMENU` qui sert de modèle pour `CMFCMenuBar`rempli.|  
|[CMFCMenuBar::EnableHelpCombobox](../Topic/CMFCMenuBar::EnableHelpCombobox.md)|Active une zone de liste déroulante **Aide** située à droite de la barre de menus.|  
|[CMFCMenuBar::EnableMenuShadows](../Topic/CMFCMenuBar::EnableMenuShadows.md)|Spécifie si l'affichage de ombres pour les menus contextuels.|  
|[CMFCMenuBar::GetAvailableExpandSize](../Topic/CMFCMenuBar::GetAvailableExpandSize.md)|\(Substitutions [CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md).\)|  
|[CMFCMenuBar::GetColumnWidth](../Topic/CMFCMenuBar::GetColumnWidth.md)|Retourne la largeur des boutons de barre d'outils.  \(Substitutions [CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md).\)|  
|[CMFCMenuBar::GetDefaultMenu](../Topic/CMFCMenuBar::GetDefaultMenu.md)|Retourne un handle vers le menu d'origine dans le fichier de ressources.|  
|[CMFCMenuBar::GetDefaultMenuResId](../Topic/CMFCMenuBar::GetDefaultMenuResId.md)|Retourne l'identificateur de ressource pour le menu d'origine dans le fichier de ressources.|  
|[CMFCMenuBar::GetFloatPopupDirection](../Topic/CMFCMenuBar::GetFloatPopupDirection.md)||  
|[CMFCMenuBar::GetForceDownArrows](../Topic/CMFCMenuBar::GetForceDownArrows.md)||  
|[CMFCMenuBar::GetHelpCombobox](../Topic/CMFCMenuBar::GetHelpCombobox.md)|Retourne un pointeur vers la zone de liste déroulante **Aide** .|  
|[CMFCMenuBar::GetHMenu](../Topic/CMFCMenuBar::GetHMenu.md)|Retourne le handle de menu associé à l'objet d' `CMFCMenuBar` .|  
|[CMFCMenuBar::GetMenuFont](../Topic/CMFCMenuBar::GetMenuFont.md)|Retourne la police globale actuelle pour les objets de menu.|  
|[CMFCMenuBar::GetMenuItem](../Topic/CMFCMenuBar::GetMenuItem.md)|Retourne le bouton de barre d'outils associé à l'index fourni d'élément.|  
|[CMFCMenuBar::GetRowHeight](../Topic/CMFCMenuBar::GetRowHeight.md)|Retourne la hauteur de boutons de barre d'outils.  \(Substitutions [CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md).\)|  
|[CMFCMenuBar::GetSystemButton](../Topic/CMFCMenuBar::GetSystemButton.md)||  
|[CMFCMenuBar::GetSystemButtonsCount](../Topic/CMFCMenuBar::GetSystemButtonsCount.md)||  
|[CMFCMenuBar::GetSystemMenu](../Topic/CMFCMenuBar::GetSystemMenu.md)||  
|[CMFCMenuBar::HighlightDisabledItems](../Topic/CMFCMenuBar::HighlightDisabledItems.md)|Indique si les éléments de menu désactivés sont mis en surbrillance.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](../Topic/CMFCMenuBar::IsButtonExtraSizeAvailable.md)|Détermine si la barre d'outils peut afficher des boutons qui ont étendu des bordures.  \(Substitutions [CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md).\)|  
|[CMFCMenuBar::IsHighlightDisabledItems](../Topic/CMFCMenuBar::IsHighlightDisabledItems.md)|Indique si les éléments désactivés sont mis en surbrillance.|  
|[CMFCMenuBar::IsMenuShadows](../Topic/CMFCMenuBar::IsMenuShadows.md)|Indique si les ombres sont dessinées pour les menus contextuels.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](../Topic/CMFCMenuBar::IsRecentlyUsedMenus.md)|Indique si les commandes de menu utilisés récemment sont affichées dans la barre de menus.|  
|[CMFCMenuBar::IsShowAllCommands](../Topic/CMFCMenuBar::IsShowAllCommands.md)|Indique si les menus contextuels affichent toutes les commandes.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](../Topic/CMFCMenuBar::IsShowAllCommandsDelay.md)|Indique si les menus affichent toutes les commandes après un court délai.|  
|[CMFCMenuBar::LoadState](../Topic/CMFCMenuBar::LoadState.md)|Charge l'état de l'objet d' `CMFCMenuBar` du Registre.|  
|[CMFCMenuBar::OnChangeHot](../Topic/CMFCMenuBar::OnChangeHot.md)|Appelé par l'infrastructure lorsqu'un utilisateur sélectionne un bouton dans la barre d'outils.  \(Substitutions [CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md).\)|  
|[CMFCMenuBar::OnDefaultMenuLoaded](../Topic/CMFCMenuBar::OnDefaultMenuLoaded.md)|Appelé par l'infrastructure lorsqu'une fenêtre frame charge le menu par défaut du fichier de ressources.|  
|[CMFCMenuBar::OnSendCommand](../Topic/CMFCMenuBar::OnSendCommand.md)|\(Substitutions `CMFCToolBar::OnSendCommand`.\)|  
|[CMFCMenuBar::OnSetDefaultButtonText](../Topic/CMFCMenuBar::OnSetDefaultButtonText.md)|Appelé par l'infrastructure lorsqu'un menu est en mode de personnalisation et l'utilisateur modifie le texte d'un élément de menu.|  
|[CMFCMenuBar::OnToolHitTest](../Topic/CMFCMenuBar::OnToolHitTest.md)|\(Substitutions `CMFCToolBar::OnToolHitTest`.\)|  
|[CMFCMenuBar::PreTranslateMessage](../Topic/CMFCMenuBar::PreTranslateMessage.md)|\(Substitutions `CMFCToolBar::PreTranslateMessage`.\)|  
|[CMFCMenuBar::RestoreOriginalstate](../Topic/CMFCMenuBar::RestoreOriginalstate.md)|Appelé par l'infrastructure lorsqu'un menu est en mode de personnalisation et l'utilisateur sélectionne **Réinitialiser** pour une barre de menus.|  
|[CMFCMenuBar::SaveState](../Topic/CMFCMenuBar::SaveState.md)|Enregistre l'état de l'objet d' `CMFCMenuBar` au Registre.|  
|[CMFCMenuBar::SetDefaultMenuResId](../Topic/CMFCMenuBar::SetDefaultMenuResId.md)|Définit le menu d'origine dans le fichier de ressources.|  
|[CMFCMenuBar::SetForceDownArrows](../Topic/CMFCMenuBar::SetForceDownArrows.md)||  
|[CMFCMenuBar::SetMaximizeMode](../Topic/CMFCMenuBar::SetMaximizeMode.md)|Appelé par l'infrastructure lorsqu'une fenêtre MDI enfant modifie son mode d'affichage.  Si la fenêtre enfant MDI est récemment agrandie ou n'est plus agrandie, les mises à jour de cette méthode la barre de menus.|  
|[CMFCMenuBar::SetMenuButtonRTC](../Topic/CMFCMenuBar::SetMenuButtonRTC.md)|Définit les informations de classe de runtime qui sont générées lorsque l'utilisateur crée dynamiquement des boutons de menu.|  
|[CMFCMenuBar::SetMenuFont](../Topic/CMFCMenuBar::SetMenuFont.md)|Définit la police pour tous les menus de l'application.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](../Topic/CMFCMenuBar::SetRecentlyUsedMenus.md)|Spécifie si une barre de menus affiche les commandes de menu utilisées en dernier.|  
|[CMFCMenuBar::SetShowAllCommands](../Topic/CMFCMenuBar::SetShowAllCommands.md)|Spécifie si la barre de menus affiche toutes les commandes.|  
  
## Notes  
 La classe d' `CMFCMenuBar` est une barre de menus qui implémente les fonctionnalités d'ancrage.  Elle ressemble à une barre d'outils, bien qu'elle ne puisse pas être fermée \- il est toujours affichée.  
  
 `CMFCMenuBar` prend en charge l'option d'afficher les objets utilisés récemment d'élément de menu.  Si cette option est activée, `CMFCMenuBar` affiche uniquement un sous\-ensemble des commandes disponibles dans le premier affichage.  Ensuite, les commandes utilisées récemment sont affichées avec le sous\-ensemble d'origine de commandes.  En outre, l'utilisateur peut toujours développer le menu pour afficher toutes les commandes disponibles.  Ainsi, chaque commande disponible est configurée pour afficher constamment, ou d'afficher uniquement si elle a été récemment sélectionnée.  
  
 Pour utiliser un objet d' `CMFCMenuBar` , incluez\- le dans l'objet principal du frame de fenêtre.  Lors de le traitement du message d' `WM_CREATE` , appelez `CMFCMenuBar::Create` ou `CMFCMenuBar::CreateEx`.  Quelle que soit l'fonction de création vous utilisez, passez un pointeur à la fenêtre frame principale.  Activez l'ancrage en appelant [CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md).  Ancrez ce menu en appelant [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md).  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCMenuBar` .  L'exemple suivant indique comment définir le style du volet, activer le bouton de personnaliser, activer une zone d'aide, activer des ombres pour les menus contextuels, et mettre à jour la barre de menus.  Cet extrait de code fait partie d' [Exemple de démonstration d'IE](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/CPP/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/CPP/cmfcmenubar-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)  
  
## Configuration requise  
 **en\-tête :** afxmenubar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)