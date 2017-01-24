---
title: "CMFCRibbonBaseElement Class | Microsoft Docs"
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
  - "CMFCRibbonBaseElement"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonBaseElement class"
ms.assetid: 419ea91b-5062-44cc-b0a3-f87d29566f62
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonBaseElement Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCRibbonBaseElement` est la classe de base pour tous les éléments que vous pouvez ajouter à [barre de ruban](../../mfc/reference/cmfcribbonbar-class.md).  Les exemples des éléments du ruban sont des boutons de ruban, des cases à cocher de ruban, et les zones de liste déroulante du ruban.  
  
## Syntaxe  
  
```  
class CMFCRibbonBaseElement : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCRibbonBaseElement`|Construit un objet `CMFCRibbonBaseElement`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonBaseElement::AddToKeyList](../Topic/CMFCRibbonBaseElement::AddToKeyList.md)|Ajoute un keytip pour l'élément ruban à un tableau de keytips.|  
|[CMFCRibbonBaseElement::AddToListBox](../Topic/CMFCRibbonBaseElement::AddToListBox.md)|Ajoute un élément ruban à la zone de liste spécifiée de commandes de ruban.|  
|[CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar](../Topic/CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar.md)|Indique si l'élément ruban peut être ajouté à la barre d'outils d'accès rapide.|  
|[CMFCRibbonBaseElement::CanBeCompacted](../Topic/CMFCRibbonBaseElement::CanBeCompacted.md)|Indique si la taille de l'élément ruban peut être compacte.|  
|[CMFCRibbonBaseElement::CanBeStretched](../Topic/CMFCRibbonBaseElement::CanBeStretched.md)|Indique si la hauteur de l'élément ruban peut grimper verticalement jusqu'à la hauteur d'une ligne de ruban.|  
|[CMFCRibbonBaseElement::CanBeStretchedHorizontally](../Topic/CMFCRibbonBaseElement::CanBeStretchedHorizontally.md)|Indique si la largeur de l'élément ruban peut changer.|  
|[CMFCRibbonBaseElement::CleanUpSizes](../Topic/CMFCRibbonBaseElement::CleanUpSizes.md)|Nettoie les paramètres de dimension pour l'élément ruban.|  
|[CMFCRibbonBaseElement::ClosePopupMenu](../Topic/CMFCRibbonBaseElement::ClosePopupMenu.md)|Ferme le menu popup pour l'élément ruban.|  
|[CMFCRibbonBaseElement::CopyFrom](../Topic/CMFCRibbonBaseElement::CopyFrom.md)|Copie l'état d' `CMFCRibbonBaseElement` spécifié à l'objet actuel.|  
|[CMFCRibbonBaseElement::DestroyCtrl](../Topic/CMFCRibbonBaseElement::DestroyCtrl.md)|Détruit l'élément ruban.|  
|[CMFCRibbonBaseElement::DrawImage](../Topic/CMFCRibbonBaseElement::DrawImage.md)|Dessine l'image pour l'élément ruban.|  
|[CMFCRibbonBaseElement::Find](../Topic/CMFCRibbonBaseElement::Find.md)|Retourne le pointeur spécifié à l'élément ruban s'il indique l'objet actuel.|  
|[CMFCRibbonBaseElement::FindByData](../Topic/CMFCRibbonBaseElement::FindByData.md)|Extrait un pointeur vers l'élément ruban s'il contient les données spécifiées.|  
|[CMFCRibbonBaseElement::FindByID](../Topic/CMFCRibbonBaseElement::FindByID.md)|Extrait un pointeur vers l'élément ruban si cet élément est identifié par l'ID de commande spécifiée|  
|[CMFCRibbonBaseElement::FindByOriginal](../Topic/CMFCRibbonBaseElement::FindByOriginal.md)|Extrait un pointeur vers l'élément ruban si son élément ruban d'origine correspond à l'élément spécifié de ruban.|  
|[CMFCRibbonBaseElement::GetCompactSize](../Topic/CMFCRibbonBaseElement::GetCompactSize.md)|Retourne la taille compacte de l'élément ruban.|  
|[CMFCRibbonBaseElement::GetData](../Topic/CMFCRibbonBaseElement::GetData.md)|Récupère des données définies par l'utilisateur associées à l'élément ruban.|  
|[CMFCRibbonBaseElement::GetDescription](../Topic/CMFCRibbonBaseElement::GetDescription.md)|Retourne la description de l'élément ruban.|  
|[CMFCRibbonBaseElement::GetDroppedDown](../Topic/CMFCRibbonBaseElement::GetDroppedDown.md)|Extrait un pointeur vers l'élément ruban si son menu contextuel est déplacé vers le bas.|  
|[CMFCRibbonBaseElement::GetElements](../Topic/CMFCRibbonBaseElement::GetElements.md)|Ajoute l'élément actuel de ruban au tableau spécifiée.|  
|[CMFCRibbonBaseElement::GetElementsByID](../Topic/CMFCRibbonBaseElement::GetElementsByID.md)|Ajoute l'élément actuel de ruban au tableau spécifié si l'élément actuel de ruban contient l'ID de commande spécifiée|  
|[CMFCRibbonBaseElement::GetHighlighted](../Topic/CMFCRibbonBaseElement::GetHighlighted.md)|Extrait un pointeur vers l'élément ruban s'il est mis en surbrillance.|  
|[CMFCRibbonBaseElement::GetID](../Topic/CMFCRibbonBaseElement::GetID.md)|Retourne l'ID de commande de l'élément ruban.|  
|[CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md)|Retourne la taille de l'image de l'élément ruban.|  
|[CMFCRibbonBaseElement::GetIntermediateSize](../Topic/CMFCRibbonBaseElement::GetIntermediateSize.md)|Retourne la taille de l'élément ruban dans son état intermédiaire.|  
|[CMFCRibbonBaseElement::GetKeys](../Topic/CMFCRibbonBaseElement::GetKeys.md)|Retourne le keytip associé à l'élément ruban.|  
|[CMFCRibbonBaseElement::GetKeyTipRect](../Topic/CMFCRibbonBaseElement::GetKeyTipRect.md)|Récupère le rectangle de limite de keytip pour l'élément ruban.|  
|[CMFCRibbonBaseElement::GetKeyTipSize](../Topic/CMFCRibbonBaseElement::GetKeyTipSize.md)|Extrait la taille du texte de keytip.|  
|[CMFCRibbonBaseElement::GetLocationInGroup](../Topic/CMFCRibbonBaseElement::GetLocationInGroup.md)|Indique l'emplacement d'affichage de l'élément ruban à un groupe de ruban.|  
|[CMFCRibbonBaseElement::GetMenuKeys](../Topic/CMFCRibbonBaseElement::GetMenuKeys.md)|Retourne les keytips associés à un bouton.|  
|[CMFCRibbonBaseElement::GetNotifyID](../Topic/CMFCRibbonBaseElement::GetNotifyID.md)|Extrait l'ID de commande de notification pour l'élément ruban.|  
|[CMFCRibbonBaseElement::GetOriginal](../Topic/CMFCRibbonBaseElement::GetOriginal.md)|Récupère l'élément d'origine du ruban.|  
|[CMFCRibbonBaseElement::GetParentCategory](../Topic/CMFCRibbonBaseElement::GetParentCategory.md)|Extrait la catégorie ruban pour l'élément ruban.|  
|[CMFCRibbonBaseElement::GetParentPanel](../Topic/CMFCRibbonBaseElement::GetParentPanel.md)|Récupère le panneau de ruban qui contient l'élément ruban.|  
|[CMFCRibbonBaseElement::GetParentRibbonBar](../Topic/CMFCRibbonBaseElement::GetParentRibbonBar.md)|Extrait la barre parente de ruban pour l'élément ruban.|  
|[CMFCRibbonBaseElement::GetParentWnd](../Topic/CMFCRibbonBaseElement::GetParentWnd.md)|Extrait la fenêtre parente pour l'élément ruban.|  
|[CMFCRibbonBaseElement::GetPressed](../Topic/CMFCRibbonBaseElement::GetPressed.md)|Extrait un pointeur vers l'élément ruban si l'utilisateur appuie actuel.|  
|[CMFCRibbonBaseElement::GetQuickAccessToolBarID](../Topic/CMFCRibbonBaseElement::GetQuickAccessToolBarID.md)|Extrait l'ID de commande de l'élément ruban lorsqu'il se trouve dans la barre d'outils d'accès rapide.|  
|[CMFCRibbonBaseElement::GetRect](../Topic/CMFCRibbonBaseElement::GetRect.md)|Retourne le rectangle englobant de l'élément ruban.|  
|[CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md)|Retourne la taille normale de l'élément ruban.|  
|[CMFCRibbonBaseElement::GetSize](../Topic/CMFCRibbonBaseElement::GetSize.md)|Retourne la taille actuelle de l'élément ruban.|  
|[CMFCRibbonBaseElement::GetText](../Topic/CMFCRibbonBaseElement::GetText.md)|Retourne le texte associé à l'élément ruban.|  
|[CMFCRibbonBaseElement::GetToolTipText](../Topic/CMFCRibbonBaseElement::GetToolTipText.md)|Texte d'info\-bulle de la valeur de l'élément ruban.|  
|[CMFCRibbonBaseElement::GetTopLevelRibbonBar](../Topic/CMFCRibbonBaseElement::GetTopLevelRibbonBar.md)|Extrait la barre de ruban de niveau supérieur pour l'élément ruban.|  
|[CMFCRibbonBaseElement::HasCompactMode](../Topic/CMFCRibbonBaseElement::HasCompactMode.md)|Spécifie si l'élément ruban a un état compact.|  
|[CMFCRibbonBaseElement::HasFocus](../Topic/CMFCRibbonBaseElement::HasFocus.md)|Indique si l'élément parent a le focus clavier.|  
|[CMFCRibbonBaseElement::HasIntermediateMode](../Topic/CMFCRibbonBaseElement::HasIntermediateMode.md)|Spécifie si l'élément ruban a un état intermédiaire.|  
|[CMFCRibbonBaseElement::HasLargeMode](../Topic/CMFCRibbonBaseElement::HasLargeMode.md)|Spécifie si l'élément ruban possède un grand mode.|  
|[CMFCRibbonBaseElement::HasMenu](../Topic/CMFCRibbonBaseElement::HasMenu.md)|Indique si l'élément ruban possède un menu.|  
|[CMFCRibbonBaseElement::HitTest](../Topic/CMFCRibbonBaseElement::HitTest.md)|Extrait un pointeur vers l'élément ruban si le point spécifié est placé dans celui\-ci.|  
|[CMFCRibbonBaseElement::IsAlignByColumn](../Topic/CMFCRibbonBaseElement::IsAlignByColumn.md)|Indique si l'élément ruban est aligné verticalement avec d'autres éléments du ruban.|  
|[CMFCRibbonBaseElement::IsAlwaysLargeImage](../Topic/CMFCRibbonBaseElement::IsAlwaysLargeImage.md)|Indique si la taille de l'image de l'élément ruban est toujours grande.|  
|[CMFCRibbonBaseElement::IsAutoRepeatMode](../Topic/CMFCRibbonBaseElement::IsAutoRepeatMode.md)|Indique si l'élément ruban est en mode automatique à répétition.|  
|[CMFCRibbonBaseElement::IsChecked](../Topic/CMFCRibbonBaseElement::IsChecked.md)|Spécifie si l'élément ruban est activée.|  
|[CMFCRibbonBaseElement::IsCompactMode](../Topic/CMFCRibbonBaseElement::IsCompactMode.md)|Spécifie si l'élément ruban est dans un état compact.|  
|[CMFCRibbonBaseElement::IsDefaultMenuLook](../Topic/CMFCRibbonBaseElement::IsDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::IsDisabled](../Topic/CMFCRibbonBaseElement::IsDisabled.md)|Spécifie si l'élément ruban est désactivé.|  
|[CMFCRibbonBaseElement::IsDroppedDown](../Topic/CMFCRibbonBaseElement::IsDroppedDown.md)|Détermine si l'élément ruban affiche un menu contextuel et est déplacé vers le bas.|  
|[CMFCRibbonBaseElement::IsFocused](../Topic/CMFCRibbonBaseElement::IsFocused.md)|Spécifie si l'élément ruban a le focus.|  
|[CMFCRibbonBaseElement::IsGalleryIcon](../Topic/CMFCRibbonBaseElement::IsGalleryIcon.md)|Indique si l'élément ruban est contenu dans une galerie de ruban.|  
|[CMFCRibbonBaseElement::IsHighlighted](../Topic/CMFCRibbonBaseElement::IsHighlighted.md)|Spécifie si l'élément ruban est mis en surbrillance.|  
|[CMFCRibbonBaseElement::IsIntermediateMode](../Topic/CMFCRibbonBaseElement::IsIntermediateMode.md)|Indique si l'image actuelle pour l'élément ruban est taille intermédiaire.|  
|[CMFCRibbonBaseElement::IsLargeMode](../Topic/CMFCRibbonBaseElement::IsLargeMode.md)|Indique si l'image actuelle pour l'élément ruban est volumineuse.|  
|[CMFCRibbonBaseElement::IsMenuMode](../Topic/CMFCRibbonBaseElement::IsMenuMode.md)|Indique si l'élément ruban est contenu dans un menu.|  
|[CMFCRibbonBaseElement::IsPressed](../Topic/CMFCRibbonBaseElement::IsPressed.md)|Indique si l'utilisateur a cliqué l'élément ruban.|  
|[CMFCRibbonBaseElement::IsQATMode](../Topic/CMFCRibbonBaseElement::IsQATMode.md)|Indique si l'élément ruban est contenu dans la barre d'outils d'accès rapide.|  
|[CMFCRibbonBaseElement::IsSeparator](../Topic/CMFCRibbonBaseElement::IsSeparator.md)|Indique si l'élément ruban est un séparateur d'affichage.|  
|[CMFCRibbonBaseElement::IsShowGroupBorder](../Topic/CMFCRibbonBaseElement::IsShowGroupBorder.md)|Indique si l'élément ruban est contenu à un groupe qui affiche une bordure commune.|  
|[CMFCRibbonBaseElement::IsShowTooltipOnBottom](../Topic/CMFCRibbonBaseElement::IsShowTooltipOnBottom.md)|Indique si l'info\-bulle s'affiche sous l'élément ruban.|  
|[CMFCRibbonBaseElement::IsTabStop](../Topic/CMFCRibbonBaseElement::IsTabStop.md)|Indique si l'élément ruban peut être sélectionné à l'aide de le clavier.|  
|[CMFCRibbonBaseElement::IsTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::IsTextAlwaysOnRight.md)|Indique si le texte de l'élément ruban s'affiche à droite.|  
|[CMFCRibbonBaseElement::IsVisible](../Topic/CMFCRibbonBaseElement::IsVisible.md)|Indique si l'élément ruban est actuellement affiché.|  
|[CMFCRibbonBaseElement::IsWholeRowHeight](../Topic/CMFCRibbonBaseElement::IsWholeRowHeight.md)|Indique si le heigth d'affichage de l'élément ruban est identique à la hauteur d'affichage du panneau de ruban qui le contient.|  
|[CMFCRibbonBaseElement::NotifyCommand](../Topic/CMFCRibbonBaseElement::NotifyCommand.md)|Envoie une notification de commande à la fenêtre parente de l'élément ruban.|  
|[CMFCRibbonBaseElement::NotifyHighlightListItem](../Topic/CMFCRibbonBaseElement::NotifyHighlightListItem.md)|Notifie la fenêtre parente de la barre de ruban lorsqu'un utilisateur met en surbrillance un élément ruban qui est défini dans une liste.|  
|[CMFCRibbonBaseElement::OnAddToQAToolbar](../Topic/CMFCRibbonBaseElement::OnAddToQAToolbar.md)|Ajoute l'élément ruban à la barre d'outils d'accès rapide spécifiée.|  
|[CMFCRibbonBaseElement::OnAfterChangeRect](../Topic/CMFCRibbonBaseElement::OnAfterChangeRect.md)|Met à jour l'info\-bulle pour l'élément ruban.|  
|[CMFCRibbonBaseElement::OnAutoRepeat](../Topic/CMFCRibbonBaseElement::OnAutoRepeat.md)|Met à jour l'élément ruban en réponse à l'entrée d'utilisateur stockée.|  
|[CMFCRibbonBaseElement::OnCalcTextSize](../Topic/CMFCRibbonBaseElement::OnCalcTextSize.md)|Calcule la taille du texte pour l'élément ruban.|  
|[CMFCRibbonBaseElement::OnChangeMenuHighlight](../Topic/CMFCRibbonBaseElement::OnChangeMenuHighlight.md)|Appelé par l'infrastructure lorsque la mise en surbrillance change pour un élément ruban qui est défini dans un menu.|  
|[CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md)|Appelé par l'infrastructure pour dessiner l'élément ruban.|  
|[CMFCRibbonBaseElement::OnDrawKeyTip](../Topic/CMFCRibbonBaseElement::OnDrawKeyTip.md)|Appelé par l'infrastructure pour dessiner le keytip pour l'élément ruban.|  
|[CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md)|Appelé par l'infrastructure lorsque l'image de menu pour l'élément ruban est dessinée.|  
|[CMFCRibbonBaseElement::OnDrawOnList](../Topic/CMFCRibbonBaseElement::OnDrawOnList.md)|Appelé par l'infrastructure pour dessiner l'élément ruban dans une zone de liste de commandes.|  
|[CMFCRibbonBaseElement::OnKey](../Topic/CMFCRibbonBaseElement::OnKey.md)|Appelé par l'infrastructure lorsque l'utilisateur appuie sur un keytip et l'élément ruban a le focus.|  
|[CMFCRibbonBaseElement::OnMenuKey](../Topic/CMFCRibbonBaseElement::OnMenuKey.md)||  
|[CMFCRibbonBaseElement::OnRTLChanged](../Topic/CMFCRibbonBaseElement::OnRTLChanged.md)|Appelé par l'infrastructure lorsque la disposition change la direction.|  
|[CMFCRibbonBaseElement::OnShow](../Topic/CMFCRibbonBaseElement::OnShow.md)|Appelé par l'infrastructure pour afficher ou masquer l'élément ruban.|  
|[CMFCRibbonBaseElement::OnShowPopupMenu](../Topic/CMFCRibbonBaseElement::OnShowPopupMenu.md)|Appelé par l'infrastructure lorsque l'élément ruban devient afficher un menu contextuel.|  
|[CMFCRibbonBaseElement::PostMenuCommand](../Topic/CMFCRibbonBaseElement::PostMenuCommand.md)||  
|[CMFCRibbonBaseElement::Redraw](../Topic/CMFCRibbonBaseElement::Redraw.md)|Met à jour l'affichage pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetACCData](../Topic/CMFCRibbonBaseElement::SetACCData.md)|Définit les données d'accessibilité pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetCompactMode](../Topic/CMFCRibbonBaseElement::SetCompactMode.md)|Définit la taille d'affichage pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetData](../Topic/CMFCRibbonBaseElement::SetData.md)|Associe un élément de données avec l'élément ruban.|  
|[CMFCRibbonBaseElement::SetDefaultMenuLook](../Topic/CMFCRibbonBaseElement::SetDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::SetDescription](../Topic/CMFCRibbonBaseElement::SetDescription.md)|Définit la description de l'élément ruban.|  
|[CMFCRibbonBaseElement::SetID](../Topic/CMFCRibbonBaseElement::SetID.md)|Définit l'ID de commande de l'élément ruban.|  
|[CMFCRibbonBaseElement::SetInitialMode](../Topic/CMFCRibbonBaseElement::SetInitialMode.md)|Définit la taille d'affichage initial pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetKeys](../Topic/CMFCRibbonBaseElement::SetKeys.md)|Définit un keytip pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetOriginal](../Topic/CMFCRibbonBaseElement::SetOriginal.md)|Définit l'élément d'origine de ruban pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md)|Définit la catégorie parente pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetParentMenu](../Topic/CMFCRibbonBaseElement::SetParentMenu.md)|Définit le conteneur parent de menu pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetParentRibbonBar](../Topic/CMFCRibbonBaseElement::SetParentRibbonBar.md)|Définit la barre parente de ruban pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetRect](../Topic/CMFCRibbonBaseElement::SetRect.md)|Définit les dimensions Franco Camion qu'il affichent le rectangle pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetText](../Topic/CMFCRibbonBaseElement::SetText.md)|Définit le texte de l'élément ruban.|  
|[CMFCRibbonBaseElement::SetTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::SetTextAlwaysOnRight.md)|Définit le texte de l'élément ruban à afficher sur la droite.|  
|[CMFCRibbonBaseElement::SetToolTipText](../Topic/CMFCRibbonBaseElement::SetToolTipText.md)|Définit le texte d'info\-bulle pour l'élément ruban.|  
|[CMFCRibbonBaseElement::SetVisible](../Topic/CMFCRibbonBaseElement::SetVisible.md)|Définit l'état de visibilité de l'élément ruban.|  
|[CMFCRibbonBaseElement::StretchHorizontally](../Topic/CMFCRibbonBaseElement::StretchHorizontally.md)|Étire la largeur de l'élément ruban.|  
|[CMFCRibbonBaseElement::StretchToWholeRow](../Topic/CMFCRibbonBaseElement::StretchToWholeRow.md)|Modifie la hauteur d'affichage de l'élément ruban en hauteur de ligne spécifiée.|  
|[CMFCRibbonBaseElement::UpdateTooltipInfo](../Topic/CMFCRibbonBaseElement::UpdateTooltipInfo.md)|Met à jour le texte d'info\-bulle à l'aide de la ressource de commande pour l'élément ruban.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonBaseElement::OnProcessKey](../Topic/CMFCRibbonBaseElement::OnProcessKey.md)|Appelé par l'infrastructure lorsque l'utilisateur appuie sur une touche de raccourci.|  
|[CMFCRibbonBaseElement::OnSetFocus](../Topic/CMFCRibbonBaseElement::OnSetFocus.md)|Appelé par l'infrastructure lorsqu'un élément ruban accepte ou perd le focus d'entrée.|  
  
## Notes  
 La classe d' `CMFCRibbonBaseElement` définit les propriétés communes à tous les éléments du ruban qui incluent l'ID de commande, l'étiquette de texte, le texte d'info\-bulle, la description de l'élément, et l'état \(qui peut être le focus, en surbrillance, enfoncé, désactivé, vérifié, ou supprimé vers le bas\).  
  
 La taille de l'image d'un élément ruban est définie par le membre d' `RibbonImageType` , qui peut être l'une des valeurs suivantes :  
  
-   `RibbonImageLarge`  
  
-   `RibbonImageSmall`  
  
 Selon sa taille, un élément ruban affiche une petite ou grande image.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCRibbonBaseElement` .  L'exemple montre comment obtenir un objet d' `CMFCRibbonBaseElement` d'une classe d' `CMFCRibbonStatusBar` , définir la description de l'élément ruban, définir le texte, définir un keytip, et définir le texte d'info\-bulle pour l'élément ruban.  Cet extrait de code fait partie d' [Exemple de client de dessin](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#8](../../mfc/reference/codesnippet/CPP/cmfcribbonbaseelement-class_1.cpp)]  
[!code-cpp[NVC_MFC_DrawClient#9](../../mfc/reference/codesnippet/CPP/cmfcribbonbaseelement-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
## Configuration requise  
 **en\-tête :** afxbaseribbonelement.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)