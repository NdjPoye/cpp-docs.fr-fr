---
title: "CMFCToolBarEditBoxButton Class | Microsoft Docs"
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
  - "OnDrawOnCustomizeList"
  - "OnDraw"
  - "CMFCToolBarEditBoxButton::OnDrawOnCustomizeList"
  - "CMFCToolBarEditBoxButton.SetACCData"
  - "CMFCToolBarEditBoxButton::OnDraw"
  - "OnCalculateSize"
  - "SetACCData"
  - "CMFCToolBarEditBoxButton"
  - "CMFCToolBarEditBoxButton::SetACCData"
  - "CMFCToolBarEditBoxButton::Serialize"
  - "CMFCToolBarEditBoxButton.OnDraw"
  - "CMFCToolBarEditBoxButton.OnDrawOnCustomizeList"
  - "CMFCToolBarEditBoxButton::OnCalculateSize"
  - "Serialize"
  - "CMFCToolBarEditBoxButton.Serialize"
  - "CMFCToolBarEditBoxButton.OnCalculateSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarEditBoxButton class"
  - "OnCalculateSize method"
  - "OnDraw method"
  - "OnDrawOnCustomizeList method"
  - "Serialize method"
  - "SetACCData method"
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarEditBoxButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un bouton de barre d'outils qui contient un contrôle d'édition \([CEdit Class](../../mfc/reference/cedit-class.md)\).  
  
## Syntaxe  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](../Topic/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton.md)|Construit un objet `CMFCToolBarEditBoxButton`.|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](../Topic/CMFCToolBarEditBoxButton::CanBeStretched.md)|Spécifie si un utilisateur peut étirer le bouton pendant la personnalisation.  \(Substitutions [CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md).\)|  
|[CMFCToolBarEditBoxButton::CopyFrom](../Topic/CMFCToolBarEditBoxButton::CopyFrom.md)|Copie les propriétés d'un autre bouton de barre d'outils sur le bouton actuel.  \(Substitutions [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](../Topic/CMFCToolBarEditBoxButton::CreateEdit.md)|Crée un nouveau contrôle d'édition du bouton.|  
|`CMFCToolBarEditBoxButton::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCToolBarEditBoxButton::GetByCmd](../Topic/CMFCToolBarEditBoxButton::GetByCmd.md)|Récupère le premier objet d' `CMFCToolBarEditBoxButton` dans l'application ayant l'ID de commande spécifiée|  
|[CMFCToolBarEditBoxButton::GetContentsAll](../Topic/CMFCToolBarEditBoxButton::GetContentsAll.md)|Extrait le texte du premier contrôle de barre d'outils de la zone d'édition avec l'ID de commande spécifiée|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](../Topic/CMFCToolBarEditBoxButton::GetContextMenuID.md)|Extrait l'ID de ressource dans le menu contextuel associé au bouton.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](../Topic/CMFCToolBarEditBoxButton::GetEditBorder.md)|Récupère le rectangle englobant de la partie d'édition du bouton de la zone d'édition.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](../Topic/CMFCToolBarEditBoxButton::GetEditBox.md)|Retourne un pointeur vers le contrôle d'édition qui est incorporé dans le bouton.|  
|[CMFCToolBarEditBoxButton::GetHwnd](../Topic/CMFCToolBarEditBoxButton::GetHwnd.md)|Récupère le handle de fenêtre associée au bouton de barre d'outils.  \(Substitutions [CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md).\)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](../Topic/CMFCToolBarEditBoxButton::GetInvalidateRect.md)|Extrait la zone de la zone cliente du bouton qui doit être redessiné.  \(Substitutions [CMFCToolBarButton::GetInvalidateRect](../Topic/CMFCToolBarButton::GetInvalidateRect.md).\)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](../Topic/CMFCToolBarEditBoxButton::HaveHotBorder.md)|Détermine si une bordure du bouton s'affiche lorsqu'un utilisateur clique sur le bouton.  \(Substitutions [CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md).\)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](../Topic/CMFCToolBarEditBoxButton::IsFlatMode.md)|Détermine si les boutons de la zone d'édition ont un style à deux dimensions.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](../Topic/CMFCToolBarEditBoxButton::NotifyCommand.md)|Spécifie si le bouton traite le message de [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) .  \(Substitutions [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md).\)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](../Topic/CMFCToolBarEditBoxButton::OnAddToCustomizePage.md)|Appelé par l'infrastructure lorsque le bouton est ajouté à une boîte de dialogue **Personnaliser** .  \(Substitutions [CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md).\)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Appelé par l'infrastructure pour calculer la taille du bouton pour le contexte de périphérique et l'état spécifié d'ancrage.  \(Substitutions [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](../Topic/CMFCToolBarEditBoxButton::OnChangeParentWnd.md)|Appelé par l'infrastructure lorsque le bouton est inséré dans une nouvelle barre d'outils.  \(Substitutions [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCToolBarEditBoxButton::OnClick](../Topic/CMFCToolBarEditBoxButton::OnClick.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton de la souris.  \(Substitutions [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](../Topic/CMFCToolBarEditBoxButton::OnCtlColor.md)|Appelé par l'infrastructure lorsque la barre d'outils parent gère un message d' `WM_CTLCOLOR` .  \(Substitutions [CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md).\)|  
|`CMFCToolBarEditBoxButton::OnDraw`|Appelé par l'infrastructure pour dessiner le bouton en utilisant des styles et des options spécifiés.  \(Substitutions [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Appelé par l'infrastructure pour dessiner le bouton dans le volet **Commandes** de la boîte de dialogue **Personnaliser** .  \(Substitutions [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](../Topic/CMFCToolBarEditBoxButton::OnGlobalFontsChanged.md)|Appelé par l'infrastructure lorsque la police globale a changé.  \(Substitutions [CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md).\)|  
|[CMFCToolBarEditBoxButton::OnMove](../Topic/CMFCToolBarEditBoxButton::OnMove.md)|Appelé par l'infrastructure lorsque la barre d'outils parent passe.  \(Substitutions [CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md).\)|  
|[CMFCToolBarEditBoxButton::OnShow](../Topic/CMFCToolBarEditBoxButton::OnShow.md)|Appelé par l'infrastructure lorsque le bouton devient visible ou invisible.  \(Substitutions [CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md).\)|  
|[CMFCToolBarEditBoxButton::OnSize](../Topic/CMFCToolBarEditBoxButton::OnSize.md)|Appelé par l'infrastructure lorsque la barre d'outils parent modifie ses causes de taille ou de position et de cette modification que le bouton à la modification de dimensionnement automatique.  \(Substitutions [CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md).\)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](../Topic/CMFCToolBarEditBoxButton::OnUpdateToolTip.md)|Appelé par l'infrastructure lorsque la barre d'outils parent gère son texte d'info\-bulle.  \(Substitutions [CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md).\)|  
|`CMFCToolBarEditBoxButton::Serialize`|Lit cet objet d'une archive ou l'écrit dans une archive.  \(Substitutions [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|`CMFCToolBarEditBoxButton::SetACCData`|Remplit l'objet fourni d' `CAccessibilityData` avec les données d'accessibilité du bouton de barre d'outils.  \(Substitutions [CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md).\)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](../Topic/CMFCToolBarEditBoxButton::SetContents.md)|Définit le texte du contrôle d'édition du bouton.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](../Topic/CMFCToolBarEditBoxButton::SetContentsAll.md)|Recherche le bouton de contrôle d'édition qui a un ID de commande spécifié, et définit le texte dans le contrôle d'édition de ce bouton.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](../Topic/CMFCToolBarEditBoxButton::SetContextMenuID.md)|Spécifie l'ID de ressource dans le menu contextuel associé au bouton.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](../Topic/CMFCToolBarEditBoxButton::SetFlatMode.md)|Spécifie l'apparence en deux dimensions de style de boutons de la zone d'édition dans l'application.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](../Topic/CMFCToolBarEditBoxButton::SetStyle.md)|Spécifie le style du bouton.  \(Substitutions [CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md).\)|  
  
## Notes  
 Pour ajouter un bouton de la zone d'édition à une barre d'outils, suivez ces étapes :  
  
 1.  Réservez un ID de ressource factice pour le bouton dans la ressource parente de barre d'outils.  
  
 2.  Construisez un objet `CMFCToolBarEditBoxButton`.  
  
 3.  Dans le gestionnaire de messages qui traite le message d' `AFX_WM_RESETTOOLBAR` , remplacez le bouton factice avec le nouveau bouton de zone de liste déroulante à l'aide de [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
 Pour plus d'informations, consultez [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCToolBarEditBoxButton` .  L'exemple montre comment spécifier qu'un utilisateur peut étirer le bouton pendant la personnalisation, spécifiez qu'une bordure du bouton s'affiche lorsqu'un utilisateur clique sur le bouton, définissez le texte dans le contrôle de zone de texte, spécifie l'apparence en deux dimensions de style de boutons de la zone d'édition dans l'application, et spécifie le style d'un contrôle de zone d'édition de barre d'outils.  
  
 [!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/CPP/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxtoolbareditboxbutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md)