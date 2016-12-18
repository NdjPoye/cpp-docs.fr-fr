---
title: "CMFCToolBar Class | Microsoft Docs"
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
  - "CMFCToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBar class"
ms.assetid: e7679c01-fb94-44c0-98c6-3af955292fb5
caps.latest.revision: 48
caps.handback.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCToolBar` ressemble à [CToolBar Class](../../mfc/reference/ctoolbar-class.md), mais fournit une prise en charge des fonctionnalités de l'interface utilisateur.  Celles\-ci incluent les barres d'outils en deux dimensions, les barres d'outils avec des images chaudes, les grandes icônes, les boutons du pagineur, les barres d'outils verrouillées, les contrôles, le rebar texte sous les images, les images d'arrière\-plan, et les barres d'outils à onglet.  La classe d' `CMFCToolBar` contient également la prise en charge intégrée de la personnalisation de l'utilisateur des barres d'outils et des menus, le glisser\-déplacer entre les barres d'outils et des menus, les boutons de zone de liste déroulante, les boutons de la zone d'édition, les sélecteurs de couleurs, les boutons et roulés.  
  
## Syntaxe  
  
```  
class CMFCToolBar : public CMFCBaseToolBar  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCToolBar::CMFCToolBar`|Constructeur par défaut.|  
|`CMFCToolBar::~CMFCToolBar`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBar::AddBasicCommand](../Topic/CMFCToolBar::AddBasicCommand.md)|Ajoute une commande de menu à la liste des commandes qui sont toujours affichés lorsqu'un utilisateur ouvre un menu.|  
|[CMFCToolBar::AddCommandUsage](../Topic/CMFCToolBar::AddCommandUsage.md)|Un index par le compteur associé à la commande donnée.|  
|[CMFCToolBar::AddToolBarForImageCollection](../Topic/CMFCToolBar::AddToolBarForImageCollection.md)|Ajoute des images des ressources d'interface utilisateur à la collection d'images dans l'application.|  
|[CMFCToolBar::AdjustLayout](../Topic/CMFCToolBar::AdjustLayout.md)|Recalcule la taille et la position d'une barre d'outils.  \(Substitue [CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md).\)|  
|[CMFCToolBar::AdjustSize](../Topic/CMFCToolBar::AdjustSize.md)|Recalcule la taille de la barre d'outils.|  
|[CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md)|Spécifie si les étiquettes de texte peuvent être affichées sous des images sur les boutons de barre d'outils.|  
|[CMFCToolBar::AreTextLabels](../Topic/CMFCToolBar::AreTextLabels.md)|Spécifie si les étiquettes de texte sous les images sont affichées actuellement sur les boutons de barre d'outils.|  
|[CMFCToolBar::AutoGrayInactiveImages](../Topic/CMFCToolBar::AutoGrayInactiveImages.md)|Activez ou les désactive la génération automatique d'images de bouton inactives.|  
|[CMFCToolBar::ButtonToIndex](../Topic/CMFCToolBar::ButtonToIndex.md)|Retourne l'index d'un objet spécifié de [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md) dans cette barre d'outils.|  
|[CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md)|Calcule la taille horizontale de la barre d'outils.  \(Substitutions [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCToolBar::CalcSize](../Topic/CMFCToolBar::CalcSize.md)|Appelé par l'infrastructure dans le cadre de le processus de calcul de disposition.  \(Substitutions [CPane::CalcSize](../Topic/CPane::CalcSize.md).\)|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|Détermine si la barre d'outils et ses frères sont positionnés sur le même volet.|  
|[CMFCToolBar::CleanUpImages](../Topic/CMFCToolBar::CleanUpImages.md)|Libère les ressources système allouées pour les images de barre d'outils.|  
|[CMFCToolBar::CleanUpLockedImages](../Topic/CMFCToolBar::CleanUpLockedImages.md)|Libère les ressources système allouées pour les images verrouillées de barre d'outils.|  
|[CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md)|Spécifie si un utilisateur peut fermer la barre d'outils.  \(Substitutions [CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md).\)|  
|[CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md)|Détermine si le système peut restaurer une barre d'outils à son état d'origine après personnalisation.|  
|[CMFCToolBar::CanFocus](../Topic/CMFCToolBar::CanFocus.md)|Spécifie si le volet peut recevoir le focus.  \(Substitutions [CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md).\)|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|Détermine si la barre d'outils et ses frères sont positionnés sur le même volet.|  
|[CMFCToolBar::CommandToIndex](../Topic/CMFCToolBar::CommandToIndex.md)|Retourne l'index du bouton dans la barre d'outils avec un ID de commande spécifiée|  
|[CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)|Crée un objet `CMFCToolBar`.|  
|[CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md)|Crée un objet d' `CMFCToolBar` qui utilise des options de style supplémentaires, telles que de grandes icônes.|  
|[CMFCToolBar::Deactivate](../Topic/CMFCToolBar::Deactivate.md)|Met la barre d'outils.|  
|[CMFCToolBar::EnableCustomizeButton](../Topic/CMFCToolBar::EnableCustomizeButton.md)|Active ou désactive le bouton **Ajouter ou supprimer des boutons** qui apparaît sur la fin de la barre d'outils.|  
|[CMFCToolBar::EnableDocking](../Topic/CMFCToolBar::EnableDocking.md)|Active l'ancrage du volet au frame principal.  \(Substitutions [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md).\)|  
|[CMFCToolBar::EnableLargeIcons](../Topic/CMFCToolBar::EnableLargeIcons.md)|Active ou désactive de grandes icônes sur les boutons de barre d'outils.|  
|[CMFCToolBar::EnableQuickCustomization](../Topic/CMFCToolBar::EnableQuickCustomization.md)|Active ou désactive la personnalisation rapide des barres d'outils afin que l'utilisateur puisse appuyer sur la touche **Alt** et glisser un bouton à un nouvel emplacement.|  
|[CMFCToolBar::EnableReflections](../Topic/CMFCToolBar::EnableReflections.md)|Active ou désactive la réflexion de commande.|  
|[CMFCToolBar::EnableTextLabels](../Topic/CMFCToolBar::EnableTextLabels.md)|Active ou désactive les étiquettes de texte sous des images de bouton de barre d'outils.|  
|[CMFCToolBar::FromHandlePermanent](../Topic/CMFCToolBar::FromHandlePermanent.md)|Extrait un pointeur vers l'objet d' `CMFCToolBar` qui contient le handle de fenêtre donnée.|  
|[CMFCToolBar::GetAllButtons](../Topic/CMFCToolBar::GetAllButtons.md)|Retourne une liste en lecture seule de boutons d'une barre d'outils.|  
|[CMFCToolBar::GetAllToolbars](../Topic/CMFCToolBar::GetAllToolbars.md)|Retourne une liste en lecture seule de toutes les barres d'outils de l'application.|  
|[CMFCToolBar::GetBasicCommands](../Topic/CMFCToolBar::GetBasicCommands.md)|Retourne une liste en lecture seule des commandes de base définies dans l'application.|  
|[CMFCToolBar::GetButton](../Topic/CMFCToolBar::GetButton.md)|Retourne un pointeur vers l'objet d' `CMFCToolBarButton` qui a un index spécifié de bouton de barre d'outils.|  
|[CMFCToolBar::GetButtonInfo](../Topic/CMFCToolBar::GetButtonInfo.md)|Retourne l'ID de commande, le style, et l'index d'image du bouton à un index spécifié.|  
|[CMFCToolBar::GetButtonSize](../Topic/CMFCToolBar::GetButtonSize.md)|Retourne les dimensions de chaque bouton dans la barre d'outils.|  
|[CMFCToolBar::GetButtonStyle](../Topic/CMFCToolBar::GetButtonStyle.md)|Retourne le style actuellement du bouton de barre d'outils qui se trouve à l'index spécifié.|  
|[CMFCToolBar::GetButtonText](../Topic/CMFCToolBar::GetButtonText.md)|Retourne l'étiquette de texte d'un bouton possédant un index spécifié.|  
|[CMFCToolBar::GetColdImages](../Topic/CMFCToolBar::GetColdImages.md)|Retourne un pointeur vers la collection d'images froides de bouton de barre d'outils de l'application.|  
|[CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md)|Retourne la largeur des boutons de barre d'outils.|  
|[CMFCToolBar::GetCommandButtons](../Topic/CMFCToolBar::GetCommandButtons.md)|Retourne une liste des boutons ayant un ID de commande spécifié de toutes les barres d'outils de l'application.|  
|[CMFCToolBar::GetCount](../Topic/CMFCToolBar::GetCount.md)|Retourne le nombre de boutons et de séparateurs dans la barre d'outils.|  
|[CMFCToolBar::GetCustomizeButton](../Topic/CMFCToolBar::GetCustomizeButton.md)|Extrait un pointeur vers l'objet d' `CMFCCustomizeButton` associé à la barre d'outils.|  
|[CMFCToolBar::GetDefaultImage](../Topic/CMFCToolBar::GetDefaultImage.md)|Retourne l'index de l'image par défaut pour un bouton de barre d'outils avec un ID de commande spécifiée|  
|[CMFCToolBar::GetDisabledImages](../Topic/CMFCToolBar::GetDisabledImages.md)|Retourne un pointeur vers la collection d'images utilisées pour les boutons de barre d'outils désactivés dans l'application.|  
|[CMFCToolBar::GetDisabledMenuImages](../Topic/CMFCToolBar::GetDisabledMenuImages.md)|Retourne un pointeur vers la collection d'images utilisées pour les boutons de menu désactivés dans l'application.|  
|[CMFCToolBar::GetDroppedDownMenu](../Topic/CMFCToolBar::GetDroppedDownMenu.md)|Extrait un pointeur vers l'objet de bouton de menu qui affiche actuellement le sous\-menu.|  
|[CMFCToolBar::GetGrayDisabledButtons](../Topic/CMFCToolBar::GetGrayDisabledButtons.md)|Spécifie si les images des boutons désactivés sont des versions estompées des images de bouton normales, ou pris de la collection d'images de bouton désactivées.|  
|[CMFCToolBar::GetHighlightedButton](../Topic/CMFCToolBar::GetHighlightedButton.md)|Retourne un pointeur vers le bouton de barre d'outils actuellement mis en surbrillance.|  
|[CMFCToolBar::GetHotBorder](../Topic/CMFCToolBar::GetHotBorder.md)|Détermine si les boutons de barre d'outils chaud\-sont suivis.|  
|[CMFCToolBar::GetHotTextColor](../Topic/CMFCToolBar::GetHotTextColor.md)|Retourne la couleur du texte des boutons de barre d'outils en surbrillance.|  
|[CMFCToolBar::GetHwndLastFocus](../Topic/CMFCToolBar::GetHwndLastFocus.md)|Retourne un handle vers la fenêtre qui avait le focus d'entrée juste avant la barre d'outils ait fini.|  
|[CMFCToolBar::GetIgnoreSetText](../Topic/CMFCToolBar::GetIgnoreSetText.md)|Spécifie si les appels définir les étiquettes de bouton sont ignorés.|  
|[CMFCToolBar::GetImageSize](../Topic/CMFCToolBar::GetImageSize.md)|Retourne la taille actuelle des images de bouton de barre d'outils.|  
|[CMFCToolBar::GetImages](../Topic/CMFCToolBar::GetImages.md)|Retourne un pointeur vers la collection d'images de bouton par défaut dans l'application.|  
|[CMFCToolBar::GetImagesOffset](../Topic/CMFCToolBar::GetImagesOffset.md)|Retourne l'index décalé utilisé pour rechercher les images de bouton de barre d'outils pour cette barre d'outils de la liste globale d'images de bouton de barre d'outils.|  
|[CMFCToolBar::GetInvalidateItemRect](../Topic/CMFCToolBar::GetInvalidateItemRect.md)|Extrait la zone de la zone cliente qui doit être redessinée pour le bouton à l'index donné.|  
|[CMFCToolBar::GetItemID](../Topic/CMFCToolBar::GetItemID.md)|Retourne l'ID de commande du bouton de barre d'outils à un index spécifié.|  
|[CMFCToolBar::GetItemRect](../Topic/CMFCToolBar::GetItemRect.md)|Retourne le rectangle englobant du bouton à un index spécifié.|  
|[CMFCToolBar::GetLargeColdImages](../Topic/CMFCToolBar::GetLargeColdImages.md)|Retourne un pointeur vers la collection de grandes froides images de bouton de barre d'outils de l'application.|  
|[CMFCToolBar::GetLargeDisabledImages](../Topic/CMFCToolBar::GetLargeDisabledImages.md)|Retourne un pointeur vers la collection de grandes désactivées images de bouton de barre d'outils de l'application.|  
|[CMFCToolBar::GetLargeImages](../Topic/CMFCToolBar::GetLargeImages.md)|Retourne un pointeur vers la collection de grandes images de bouton de barre d'outils de l'application.|  
|[CMFCToolBar::GetLockedColdImages](../Topic/CMFCToolBar::GetLockedColdImages.md)|Retourne un pointeur vers la collection d'images froides verrouillées dans la barre d'outils.|  
|[CMFCToolBar::GetLockedDisabledImages](../Topic/CMFCToolBar::GetLockedDisabledImages.md)|Retourne un pointeur vers la collection d'images désactivées verrouillées dans la barre d'outils.|  
|[CMFCToolBar::GetLockedImages](../Topic/CMFCToolBar::GetLockedImages.md)|Retourne un pointeur vers la collection d'images de bouton verrouillées dans la barre d'outils.|  
|[CMFCToolBar::GetLockedImageSize](../Topic/CMFCToolBar::GetLockedImageSize.md)|Retourne la taille par défaut des images verrouillées de barre d'outils.|  
|[CMFCToolBar::GetLockedMenuImages](../Topic/CMFCToolBar::GetLockedMenuImages.md)|Retourne un pointeur vers la collection d'images verrouillées de menu de la barre d'outils dans la barre d'outils.|  
|[CMFCToolBar::GetMenuButtonSize](../Topic/CMFCToolBar::GetMenuButtonSize.md)|Retourne la taille des boutons de menu dans l'application.|  
|[CMFCToolBar::GetMenuImageSize](../Topic/CMFCToolBar::GetMenuImageSize.md)|Retourne la taille des images de bouton de menu dans l'application.|  
|[CMFCToolBar::GetMenuImages](../Topic/CMFCToolBar::GetMenuImages.md)|Retourne un pointeur vers la collection d'images de bouton de menu dans l'application.|  
|[CMFCToolBar::GetOrigButtons](../Topic/CMFCToolBar::GetOrigButtons.md)|Extrait la collection de boutons non personnalisés de la barre d'outils.|  
|[CMFCToolBar::GetOrigResetButtons](../Topic/CMFCToolBar::GetOrigResetButtons.md)|Extrait la collection de boutons de redémarrage non personnalisés de la barre d'outils.|  
|[CMFCToolBar::GetResourceID](../Topic/CMFCToolBar::GetResourceID.md)|Extrait l'ID de ressource de la barre d'outils.|  
|[CMFCToolBar::GetRouteCommandsViaFrame](../Topic/CMFCToolBar::GetRouteCommandsViaFrame.md)|Détermine qu'objet, le frame parent ou le propriétaire, envoie des commandes de la barre d'outils.|  
|[CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md)|Retourne la hauteur de boutons de barre d'outils.|  
|[CMFCToolBar::GetShowTooltips](../Topic/CMFCToolBar::GetShowTooltips.md)|Spécifie si les info\-bulles s'affichent pour les boutons de barre d'outils.|  
|[CMFCToolBar::GetSiblingToolBar](../Topic/CMFCToolBar::GetSiblingToolBar.md)|Récupère le frère de la barre d'outils.|  
|[CMFCToolBar::GetUserImages](../Topic/CMFCToolBar::GetUserImages.md)|Retourne un pointeur vers la collection d'images définies par l'utilisateur de bouton de barre d'outils de l'application.|  
|[CMFCToolBar::HitTest](../Topic/CMFCToolBar::HitTest.md)|Retourne l'index du bouton de barre d'outils situé à la position spécifiée.|  
|[CMFCToolBar::InsertButton](../Topic/CMFCToolBar::InsertButton.md)|Insère un bouton dans la barre d'outils.|  
|[CMFCToolBar::InsertSeparator](../Topic/CMFCToolBar::InsertSeparator.md)|Insère un séparateur dans la barre d'outils.|  
|[CMFCToolBar::InvalidateButton](../Topic/CMFCToolBar::InvalidateButton.md)|Invalide la zone cliente du bouton de barre d'outils qui existe à l'index fourni.|  
|[CMFCToolBar::IsAddRemoveQuickCustomize](../Topic/CMFCToolBar::IsAddRemoveQuickCustomize.md)|Détermine si un utilisateur peut ajouter ou supprimer des boutons de barre d'outils à l'aide de l'option du menu **Personnaliser** .|  
|[CMFCToolBar::IsAltCustomizeMode](../Topic/CMFCToolBar::IsAltCustomizeMode.md)|Spécifie si *la personnalisation rapide* est utilisée pour faire glisser un bouton.|  
|[CMFCToolBar::IsAutoGrayInactiveImages](../Topic/CMFCToolBar::IsAutoGrayInactiveImages.md)|Spécifie si la génération automatique d'images de bouton \(non accentuées inactives\) est activée.|  
|[CMFCToolBar::IsBasicCommand](../Topic/CMFCToolBar::IsBasicCommand.md)|Détermine si une commande est dans la liste de commandes de base.|  
|[CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md)|Détermine si la barre d'outils peut afficher des boutons qui ont étendu des bordures.|  
|[CMFCToolBar::IsButtonHighlighted](../Topic/CMFCToolBar::IsButtonHighlighted.md)|Détermine si un bouton dans la barre d'outils est mis en surbrillance.|  
|[CMFCToolBar::IsCommandPermitted](../Topic/CMFCToolBar::IsCommandPermitted.md)|Détermine si une commande est autorisée.|  
|[CMFCToolBar::IsCommandRarelyUsed](../Topic/CMFCToolBar::IsCommandRarelyUsed.md)|Détermine si une commande est rarement utilisée \(consultez [CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)\).|  
|[CMFCToolBar::IsCustomizeMode](../Topic/CMFCToolBar::IsCustomizeMode.md)|Spécifie si l'infrastructure de barre d'outils est en mode de personnalisation.|  
|[CMFCToolBar::IsDragButton](../Topic/CMFCToolBar::IsDragButton.md)|Détermine si un bouton de barre d'outils est déplacé.|  
|[CMFCToolBar::IsExistCustomizeButton](../Topic/CMFCToolBar::IsExistCustomizeButton.md)|Détermine si la barre d'outils contient le bouton **Personnaliser** .|  
|[CMFCToolBar::IsFloating](../Topic/CMFCToolBar::IsFloating.md)|Détermine si la barre d'outils est flottante.|  
|[CMFCToolBar::IsLargeIcons](../Topic/CMFCToolBar::IsLargeIcons.md)|Spécifie si les barres d'outils dans l'application affichent en cours de grandes icônes.|  
|[CMFCToolBar::IsLastCommandFromButton](../Topic/CMFCToolBar::IsLastCommandFromButton.md)|Détermine si la commande récemment exécutée a été envoyée du bouton de barre d'outils spécifié.|  
|[CMFCToolBar::IsLocked](../Topic/CMFCToolBar::IsLocked.md)|Détermine si la barre d'outils est verrouillée.|  
|[CMFCToolBar::IsOneRowWithSibling](../Topic/CMFCToolBar::IsOneRowWithSibling.md)|Détermine si la barre d'outils et la barre d'outils sœurs sont positionnées sur la même ligne.|  
|[CMFCToolBar::IsUserDefined](../Topic/CMFCToolBar::IsUserDefined.md)|Spécifie si la barre d'outils est définie par l'utilisateur.|  
|[CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md)|Charge des images de barre d'outils des ressources d'application.|  
|[CMFCToolBar::LoadBitmapEx](../Topic/CMFCToolBar::LoadBitmapEx.md)|Charge des images de barre d'outils des ressources d'application.  Inclut de grandes images.|  
|[CMFCToolBar::LoadParameters](../Topic/CMFCToolBar::LoadParameters.md)|Charge des options globales de barre d'outils dans le Registre Windows.|  
|[CMFCToolBar::LoadState](../Topic/CMFCToolBar::LoadState.md)|Charge les informations d'état de la barre d'outils dans le Registre Windows.  \(Substitutions [CPane::LoadState](../Topic/CPane::LoadState.md).\)|  
|[CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md)|Charge la barre d'outils des ressources d'application.|  
|[CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)|Charge la barre d'outils des ressources d'application à l'aide de la classe d'assistance d' `CMFCToolBarInfo` pour permettre à l'application d'utiliser de grandes images.|  
|[CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md)|Appelé par l'infrastructure lorsqu'un utilisateur sélectionne un bouton dans la barre d'outils.|  
|[CMFCToolBar::OnFillBackground](../Topic/CMFCToolBar::OnFillBackground.md)|Appelé par l'infrastructure de [CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md) pour remplir arrière\-plan de barre d'outils.|  
|[CMFCToolBar::OnReset](../Topic/CMFCToolBar::OnReset.md)|Restaure la barre d'outils à son état d'origine.|  
|[CMFCToolBar::OnSetAccData](../Topic/CMFCToolBar::OnSetAccData.md)|\(Substitutions [CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md).\)|  
|[CMFCToolBar::OnSetDefaultButtonText](../Topic/CMFCToolBar::OnSetDefaultButtonText.md)|Restaure le texte d'un bouton de barre d'outils à son état par défaut.|  
|`CMFCToolBar::OnUpdateCmdUI`|Utilisé en interne.|  
|[CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md)|Supprime tous les boutons de la barre d'outils.|  
|[CMFCToolBar::RemoveButton](../Topic/CMFCToolBar::RemoveButton.md)|Supprime le bouton de l'index spécifié de la barre d'outils.|  
|[CMFCToolBar::RemoveStateFromRegistry](../Topic/CMFCToolBar::RemoveStateFromRegistry.md)|Supprime les informations d'état de la barre d'outils dans le Registre Windows.|  
|[CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)|Remplace un bouton de barre d'outils avec un autre bouton de barre d'outils.|  
|[CMFCToolBar::ResetAll](../Topic/CMFCToolBar::ResetAll.md)|Restaure les barres d'outils à leur état d'origine.|  
|[CMFCToolBar::ResetAllImages](../Topic/CMFCToolBar::ResetAllImages.md)|Efface toutes les collections d'image de barre d'outils de l'application.|  
|[CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md)|Restaure l'état d'origine d'une barre d'outils.|  
|[CMFCToolBar::SaveState](../Topic/CMFCToolBar::SaveState.md)|Enregistre les informations d'état de la barre d'outils dans le Registre Windows.  \(Substitutions [CPane::SaveState](../Topic/CPane::SaveState.md).\)|  
|`CMFCToolBar::Serialize`|\(Substitutions `CBasePane::Serialize`.\)|  
|[CMFCToolBar::SetBasicCommands](../Topic/CMFCToolBar::SetBasicCommands.md)|Définit la liste des commandes qui sont toujours affichés lorsqu'un utilisateur ouvre un menu.|  
|[CMFCToolBar::SetButtonInfo](../Topic/CMFCToolBar::SetButtonInfo.md)|Définit l'ID de commande, le style, et l'ID d'image d'un bouton de barre d'outils.|  
|[CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md)|Définit le style du bouton de barre d'outils à l'index donné.|  
|[CMFCToolBar::SetButtonText](../Topic/CMFCToolBar::SetButtonText.md)|Définit l'étiquette de texte d'un bouton de barre d'outils.|  
|[CMFCToolBar::SetButtons](../Topic/CMFCToolBar::SetButtons.md)|Définit les boutons de la barre d'outils.|  
|[CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)|Spécifie si les commandes rarement utilisées n'apparaissent pas dans le menu de l'application.|  
|[CMFCToolBar::SetCustomizeMode](../Topic/CMFCToolBar::SetCustomizeMode.md)|Active ou désactive le mode de personnalisation pour toutes les barres d'outils de l'application.|  
|[CMFCToolBar::SetGrayDisabledButtons](../Topic/CMFCToolBar::SetGrayDisabledButtons.md)|Spécifie si les boutons désactivés dans la barre d'outils sont grisés ou si les images désactivées sont utilisées pour les boutons désactivés.|  
|[CMFCToolBar::SetHeight](../Topic/CMFCToolBar::SetHeight.md)|Définit la hauteur de la barre d'outils.|  
|[CMFCToolBar::SetHotBorder](../Topic/CMFCToolBar::SetHotBorder.md)|Spécifie si les boutons de barre d'outils chaud\- sont suivis.|  
|[CMFCToolBar::SetHotTextColor](../Topic/CMFCToolBar::SetHotTextColor.md)|Définit la couleur de texte pour les boutons de barre d'outils chauds.|  
|[CMFCToolBar::SetLargeIcons](../Topic/CMFCToolBar::SetLargeIcons.md)|Spécifie si les boutons de barre d'outils afficher de grandes icônes.|  
|[CMFCToolBar::SetLockedSizes](../Topic/CMFCToolBar::SetLockedSizes.md)|Définit les tailles des boutons verrouillés et des images verrouillées dans la barre d'outils.|  
|[CMFCToolBar::SetMenuSizes](../Topic/CMFCToolBar::SetMenuSizes.md)|Définit la taille des boutons de menu de la barre d'outils et de leurs images.|  
|[CMFCToolBar::SetNonPermittedCommands](../Topic/CMFCToolBar::SetNonPermittedCommands.md)|Définit la liste des commandes qui ne peut pas être exécutée par l'utilisateur.|  
|[CMFCToolBar::SetOneRowWithSibling](../Topic/CMFCToolBar::SetOneRowWithSibling.md)|Positionne la barre d'outils et ses frères sur la même ligne les.|  
|[CMFCToolBar::SetPermament](../Topic/CMFCToolBar::SetPermament.md)|Spécifie si un utilisateur peut fermer la barre d'outils.|  
|[CMFCToolBar::SetRouteCommandsViaFrame](../Topic/CMFCToolBar::SetRouteCommandsViaFrame.md)|Spécifie si le frame parent ou le propriétaire envoie des commandes de la barre d'outils.|  
|[CMFCToolBar::SetShowTooltips](../Topic/CMFCToolBar::SetShowTooltips.md)|Spécifie si l'infrastructure affiche des info\-bulles.|  
|[CMFCToolBar::SetSiblingToolBar](../Topic/CMFCToolBar::SetSiblingToolBar.md)|Spécifie le frère de la barre d'outils.|  
|[CMFCToolBar::SetSizes](../Topic/CMFCToolBar::SetSizes.md)|Spécifie les tailles des boutons et des images sur les barres d'outils.|  
|[CMFCToolBar::SetToolBarBtnText](../Topic/CMFCToolBar::SetToolBarBtnText.md)|Spécifie les propriétés d'un bouton dans la barre d'outils.|  
|[CMFCToolBar::SetTwoRowsWithSibling](../Topic/CMFCToolBar::SetTwoRowsWithSibling.md)|Positionne la barre d'outils et ses frères sur les lignes distinctes.|  
|[CMFCToolBar::SetUserImages](../Topic/CMFCToolBar::SetUserImages.md)|Définit la collection d'images définies par l'utilisateur dans l'application.|  
|[CMFCToolBar::StretchPane](../Topic/CMFCToolBar::StretchPane.md)|Étire la barre d'outils verticalement ou horizontalement. \(Substitutions [CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md).\)|  
|[CMFCToolBar::TranslateChar](../Topic/CMFCToolBar::TranslateChar.md)|Exécute une commande de bouton si le code de touche spécifié correspond à un raccourci clavier valide.|  
|[CMFCToolBar::UpdateButton](../Topic/CMFCToolBar::UpdateButton.md)|Met à jour l'état du bouton spécifié.|  
|[CMFCToolBar::WrapToolBar](../Topic/CMFCToolBar::WrapToolBar.md)|Repositionne des boutons de barre d'outils dans les dimensions données.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBar::AllowShowOnList](../Topic/CMFCToolBar::AllowShowOnList.md)|Détermine si la barre d'outils s'affiche dans la liste dans le volet **Barres d'outils** de la boîte de dialogue **Personnaliser** .|  
|[CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md)|Calcule la hauteur maximale d'un bouton dans la barre d'outils.|  
|[CMFCToolBar::DoPaint](../Topic/CMFCToolBar::DoPaint.md)|Redessine une barre d'outils.|  
|[CMFCToolBar::DrawButton](../Topic/CMFCToolBar::DrawButton.md)|Redessine un bouton de barre d'outils.|  
|[CMFCToolBar::DrawSeparator](../Topic/CMFCToolBar::DrawSeparator.md)|Redessine un séparateur d'une barre d'outils.|  
|[CMFCToolBar::OnUserToolTip](../Topic/CMFCToolBar::OnUserToolTip.md)|Appelé par l'infrastructure lorsque l'info\-bulle pour un bouton est sur le point d'être affiché.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBar::m\_bDontScaleImages](../Topic/CMFCToolBar::m_bDontScaleImages.md)|Spécifie que, mettre à l'échelle ou non des images de barre d'outils en mode élevé PPP.|  
|[CMFCToolBar::m\_dblLargeImageRatio](../Topic/CMFCToolBar::m_dblLargeImageRatio.md)|Spécifie le taux de la dimension \(hauteur ou largeur\) de grandes icônes de la dimension des images normales.|  
  
## Notes  
 Pour lier un objet d' `CMFCToolBar` à votre application, suivez ces étapes :  
  
1.  Ajoutez un objet d' `CMFCToolBar` à la fenêtre frame principale.  
  
2.  Lorsque vous utilisez le message d' `WM_CREATE` de la fenêtre frame principale, appelez [CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md) ou [CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md) pour créer la barre d'outils et pour spécifier son style.  
  
3.  Appelez [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) pour spécifier le style d'ancrage.  
  
 Pour insérer un bouton particulier, tel qu'une zone de liste déroulante ou une barre d'outils de liste déroulante, réservent un bouton factice dans la ressource parent, et remplacent le bouton factice au moment de l'exécution à l'aide de [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  Pour plus d'informations, consultez [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
 `CMFCToolBar` est la classe de base pour les classes de la bibliothèque MFC [CMFCMenuBar Class](../../mfc/reference/cmfcmenubar-class.md), [CMFCPopupMenuBar, classe](../../mfc/reference/cmfcpopupmenubar-class.md), et [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCToolBar` .  L'exemple suivant indique comment définir le texte de l'étiquette de la fenêtre de la barre d'outils, définir les zones, définir le style du volet, et activer le bouton **Ajouter ou supprimer des boutons** qui apparaît sur la fin de la barre d'outils.  Cet extrait de code fait partie d' [Exemple de démonstration d'IE](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#6](../../mfc/reference/codesnippet/CPP/cmfctoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#8](../../mfc/reference/codesnippet/CPP/cmfctoolbar-class_2.cpp)]  
  
## Configuration requise  
 **en\-tête :** afxtoolbar.h  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCMenuBar Class](../../mfc/reference/cmfcmenubar-class.md)   
 [CMFCPopupMenuBar, classe](../../mfc/reference/cmfcpopupmenubar-class.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md)