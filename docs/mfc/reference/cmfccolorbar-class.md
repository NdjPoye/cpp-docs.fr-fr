---
title: "CMFCColorBar Class | Microsoft Docs"
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
  - "CMFCColorBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorBar class"
  - "CMFCColorBar::m_bInternal data member"
  - "CMFCColorBar::m_bIsEnabled data member"
  - "CMFCColorBar::m_bIsTearOff data member"
  - "CMFCColorBar::m_BoxSize data member"
  - "CMFCColorBar::m_bShowDocColorsWhenDocked data member"
  - "CMFCColorBar::m_bStdColorDlg data member"
  - "CMFCColorBar::m_ColorAutomatic data member"
  - "CMFCColorBar::m_ColorNames data member"
  - "CMFCColorBar::m_colors data member"
  - "CMFCColorBar::m_ColorSelected data member"
  - "CMFCColorBar::m_lstDocColors data member"
  - "CMFCColorBar::m_nCommandID data member"
  - "CMFCColorBar::m_nHorzMargin data member"
  - "CMFCColorBar::m_nHorzOffset data member"
  - "CMFCColorBar::m_nNumColumns data member"
  - "CMFCColorBar::m_nNumColumnsVert data member"
  - "CMFCColorBar::m_nNumRowsHorz data member"
  - "CMFCColorBar::m_nRowHeight data member"
  - "CMFCColorBar::m_nVertMargin data member"
  - "CMFCColorBar::m_nVertOffset data member"
  - "CMFCColorBar::m_Palette data member"
  - "CMFCColorBar::m_pParentBtn data member"
  - "CMFCColorBar::m_pParentRibbonBtn data member"
  - "CMFCColorBar::m_pWndPropList data member"
  - "CMFCColorBar::m_strAutoColor data member"
  - "CMFCColorBar::m_strDocColors data member"
  - "CMFCColorBar::m_strOtherColor data member"
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCColorBar` représente une barre de contrôles d'ancrage qui peut sélectionner des couleurs dans un document ou une application.  
  
## Syntaxe  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorBar::CMFCColorBar](../Topic/CMFCColorBar::CMFCColorBar.md)|Construit un objet `CMFCColorBar`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorBar::ContextToSize](../Topic/CMFCColorBar::ContextToSize.md)|Calcule la verticale et les marges horizontales qui sont requises pour contenir les boutons sur le contrôle de la barre de couleurs puis règle l'emplacement de ces boutons.|  
|[CMFCColorBar::CreateControl](../Topic/CMFCColorBar::CreateControl.md)|Crée une fenêtre de contrôle de la barre de couleurs, la attaché à l'objet d' `CMFCColorBar` , et le contrôle se redimensionne pour contenir la palette de couleurs spécifiée.|  
|[CMFCColorBar::Create](../Topic/CMFCColorBar::Create.md)|Crée une fenêtre de contrôle de la barre de couleurs et la attaché à l'objet d' `CMFCColorBar` .|  
|[CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md)|Affiche ou masque le bouton automatique.|  
|[CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)|Active ou désactive l'affichage d'une boîte de dialogue qui permet à l'utilisateur de sélectionner plus de couleurs.|  
|[CMFCColorBar::GetColor](../Topic/CMFCColorBar::GetColor.md)|Extrait la couleur sélectionnée.|  
|[CMFCColorBar::GetCommandID](../Topic/CMFCColorBar::GetCommandID.md)|Extrait l'ID de commande du contrôle de la barre de couleurs actuelle.|  
|[CMFCColorBar::GetHighlightedColor](../Topic/CMFCColorBar::GetHighlightedColor.md)|Extrait la couleur qui signifie qu'un bouton de couleur a le focus ; autrement dit, le bouton est à *chaud*.|  
|[CMFCColorBar::GetHorzMargin](../Topic/CMFCColorBar::GetHorzMargin.md)|Extrait la marge horizontale, qui est l'espace entre la cellule gauche ou droit de couleur et la limite de zone cliente.|  
|[CMFCColorBar::GetVertMargin](../Topic/CMFCColorBar::GetVertMargin.md)|Extrait la marge vertical, qui est l'espace entre le début ou la cellule de couleur inférieur et la limite de zone cliente.|  
|[CMFCColorBar::IsTearOff](../Topic/CMFCColorBar::IsTearOff.md)|Indique si la discrimination raciale actuelle est ancrable.|  
|[CMFCColorBar::SetColor](../Topic/CMFCColorBar::SetColor.md)|Définit la couleur actuellement sélectionnée.|  
|[CMFCColorBar::SetColorName](../Topic/CMFCColorBar::SetColorName.md)|Définit un nouveau nom pour une couleur spécifiée.|  
|[CMFCColorBar::SetCommandID](../Topic/CMFCColorBar::SetCommandID.md)|Définit un nouvel ID de commande pour un contrôle de la barre de couleurs.|  
|[CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md)|Définit la liste de couleurs utilisées dans le document actif.|  
|[CMFCColorBar::SetHorzMargin](../Topic/CMFCColorBar::SetHorzMargin.md)|Définit la marge horizontale, qui est l'espace entre la cellule gauche ou droit de couleur et la limite de zone cliente.|  
|[CMFCColorBar::SetVertMargin](../Topic/CMFCColorBar::SetVertMargin.md)|Définit la marge vertical, qui est l'espace entre le début ou la cellule de couleur inférieur et la limite de zone cliente.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorBar::AdjustLocations](../Topic/CMFCColorBar::AdjustLocations.md)|Ajuste les positions des boutons de couleur sur le contrôle de la barre de couleurs.|  
|[CMFCColorBar::AllowChangeTextLabels](../Topic/CMFCColorBar::AllowChangeTextLabels.md)|Indique si l'étiquette de texte des boutons de couleur peut changer.|  
|[CMFCColorBar::AllowShowOnList](../Topic/CMFCColorBar::AllowShowOnList.md)|Indique si l'objet contrôle de la barre de couleurs peuvent apparaître dans une liste de barre d'outils pendant le processus de personnalisation.|  
|[CMFCColorBar::CalcSize](../Topic/CMFCColorBar::CalcSize.md)|Appelé par l'infrastructure dans le cadre de le processus de calcul de disposition.|  
|[CMFCColorBar::CreatePalette](../Topic/CMFCColorBar::CreatePalette.md)|Initalizes une palette des couleurs dans un tableau spécifié de couleurs.|  
|[CMFCColorBar::GetColorGridSize](../Topic/CMFCColorBar::GetColorGridSize.md)|Calcule le nombre de lignes et de colonnes de la grille d'un contrôle de la barre de couleurs.|  
|[CMFCColorBar::GetExtraHeight](../Topic/CMFCColorBar::GetExtraHeight.md)|Calcule la hauteur supplémentaire dont la discrimination raciale actuelle a besoin pour afficher de divers éléments de l'interface utilisateur tels que le bouton **autre** , documentent les couleurs, et ainsi de suite.|  
|[CMFCColorBar::InitColors](../Topic/CMFCColorBar::InitColors.md)|Initialise un choix de couleurs avec les couleurs dans une palette spécifiée ou la palette par défaut du système.|  
|[CMFCColorBar::OnKey](../Topic/CMFCColorBar::OnKey.md)|Appelé par l'infrastructure lorsqu'un utilisateur appuie sur un bouton de clavier.|  
|[CMFCColorBar::OnSendCommand](../Topic/CMFCColorBar::OnSendCommand.md)|Appelé par l'infrastructure pour fermer une hiérarchie de contrôles instantanés.|  
|[CMFCColorBar::OnUpdateCmdUI](../Topic/CMFCColorBar::OnUpdateCmdUI.md)|Appelé par l'infrastructure pour activer ou désactiver un élément d'interface utilisateur d'un contrôle de la barre de couleurs avant l'élément s'affiche.|  
|[CMFCColorBar::OpenColorDialog](../Topic/CMFCColorBar::OpenColorDialog.md)|Ouvre une boîte de dialogue de couleur.|  
|[CMFCColorBar::Rebuild](../Topic/CMFCColorBar::Rebuild.md)|Redessine complètement le contrôle de la barre de couleurs.|  
|[CMFCColorBar::SelectPalette](../Topic/CMFCColorBar::SelectPalette.md)|Définit la palette logique du contexte spécifié de périphérique à la palette du bouton parent du contrôle de la barre de couleurs actuelle.|  
|[CMFCColorBar::SetPropList](../Topic/CMFCColorBar::SetPropList.md)|Définit le membre protégée par `m_pWndPropList` au pointeur spécifié à un contrôle de grille des propriétés.|  
|[CMFCColorBar::ShowCommandMessageString](../Topic/CMFCColorBar::ShowCommandMessageString.md)|Demande la fenêtre frame qui possède le contrôle de la barre de couleurs pour mettre à jour la ligne de message dans la barre d'état.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|`m_bInternal`|Un champ booléen qui détermine si les événements de souris sont traités.  En général, les événements de souris sont traités lorsque ce champ est `TRUE` et le mode de personnalisation est `FALSE`.|  
|`m_bIsEnabled`|Une valeur booléenne qui indique si un contrôle est activé.|  
|`m_bIsTearOff`|Une valeur booléenne qui indique si le contrôle de la barre de couleurs en charge l'ancrage.|  
|`m_BoxSize`|Un objet de [CSize](../../atl-mfc-shared/reference/csize-class.md) qui spécifie la taille d'une cellule dans une grille de discrimination raciale.|  
|`m_bShowDocColorsWhenDocked`|Une valeur booléenne qui indique si l'affichage des couleurs du document lorsque la discrimination raciale est ancrée.  Pour plus d'informations, consultez [CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md).|  
|`m_bStdColorDlg`|Une valeur booléenne qui indique si afficher la boîte de dialogue standard de couleur système ou la boîte de dialogue de [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) .  Pour plus d'informations, consultez [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md).|  
|`m_ColorAutomatic`|[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) qui stocke la couleur automatique actuelle.  Pour plus d'informations, consultez [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md).|  
|`m_ColorNames`|Un objet de [CMap](../../mfc/reference/cmap-class.md) qui associe un ensemble RVB couleurs avec leurs noms.|  
|`m_colors`|[CArray](../../mfc/reference/carray-class.md) des valeurs de [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) qui contient les couleurs affichées dans le contrôle de la barre de couleurs.|  
|`m_ColorSelected`|Une valeur de [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) qui est la couleur que l'utilisateur a sélectionnée du contrôle de la barre de couleurs.|  
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) des valeurs de [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) qui contient les couleurs qui sont actuellement utilisées dans un document.|  
|`m_nCommandID`|Entier non signé qui est l'ID de commande d'un bouton de couleur.|  
|`m_nHorzMargin`|Un entier qui représente la marge horizontale entre la couleur boutons dans une grille de couleurs.|  
|`m_nHorzOffset`|Un entier qui représente l'offset horizontal au centre du bouton de couleur.  Cette valeur est importante si les affichages de bouton du texte ou une image en plus d'une couleur.|  
|`m_nNumColumns`|Un entier qui représente le nombre de colonnes d'une grille de contrôle de la barre de couleurs de couleurs.|  
|`m_nNumColumnsVert`|Un entier qui représente le nombre de colonnes d'une grille verticalement orientée de couleurs.|  
|`m_nNumRowsHorz`|Un entier qui représente le nombre de colonnes d'une grille orientée horizontalement de couleurs.|  
|`m_nRowHeight`|Un entier qui est la hauteur d'une ligne de couleur boutons dans une grille de couleurs.|  
|`m_nVertMargin`|Un entier qui représente la marge vertical entre la couleur boutons dans une grille de couleurs.|  
|`m_nVertOffset`|Un entier qui représente le décalage vertical au centre du bouton de couleur.  Cette valeur est importante si les affichages de bouton du texte ou une image en plus d'une couleur.|  
|`m_Palette`|[CPalette](../../mfc/reference/cpalette-class.md) des couleurs utilisées dans le contrôle de la barre de couleurs.|  
|`m_pParentBtn`|Un pointeur vers un objet de [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) qui est le parent du bouton actuel.  Cette valeur est importante si le bouton de couleur est dans une hiérarchie de contrôles de barre d'outils ou est dans un contrôle de grille des propriétés de couleur.|  
|`m_pParentRibbonBtn`|Un pointeur vers un objet de [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) basé sur le ruban et est le bouton parent du bouton actuel.  Cette valeur est importante si le bouton de couleur est dans une hiérarchie de contrôles de barre d'outils ou est dans un contrôle de grille des propriétés de couleur.|  
|`m_pWndPropList`|Un pointeur vers un objet de [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) .|  
|`m_strAutoColor`|[CString](../../atl-mfc-shared/reference/cstringt-class.md) qui est le texte affiché sur le bouton **Automatique** .  Pour plus d'informations, consultez [CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md).|  
|`m_strDocColors`|[CString](../../atl-mfc-shared/reference/cstringt-class.md) qui est le texte affiché sur le bouton de couleurs de document.  Pour plus d'informations, consultez [CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md).|  
|`m_strOtherColor`|[CString](../../atl-mfc-shared/reference/cstringt-class.md) qui est le texte affiché sur *l'autre* bouton.  Pour plus d'informations, consultez [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md).|  
  
## Notes  
 Généralement, vous ne créez pas un objet d' `CMFCColorBar` directement.  À la place, [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) \(utilisé dans les menus et les barres d'outils\) ou [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md) crée l'objet d' `CMFCColorBar` .  
  
 La classe d' `CMFCColorBar` fournit les fonctionnalités suivantes :  
  
-   Ajuste automatiquement la liste de couleurs de document.  
  
-   Enregistre et restaure son état, ainsi que l'état de document.  
  
-   Gère le bouton « automatique ».  
  
-   Utilise le contrôle de [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md) pour sélectionner une couleur personnalisée.  
  
-   Prend en charge « arrachent » l'état \(s'il est créé à l'aide de [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md)\).  
  
 Pour incorporer la fonctionnalité d' `CMFCColorBar` à votre application :  
  
1.  Créez un bouton de menu normal et assignez \-lui un ID, par exemple ID\_CHAR\_COLOR.  
  
2.  Dans votre classe de fenêtre frame, substituez la méthode de [CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md) et remplacez le bouton de menu normal par un objet de [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) \(en appelant [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)\).  
  
3.  Définissez les styles et activer ou désactiver les fonctionnalités de l'objet d' `CMFCColorBar` pendant la création de [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) .  L'objet d' `CMFCColorMenuButton` crée dynamiquement l'objet d' `CMFCColorBar` lorsque l'infrastructure appelle la méthode d' `CreatePopupMenu` .  
  
 Lorsque l'utilisateur clique sur un bouton de la barre de couleurs, l'infrastructure utilise la macro d' `ON_COMMAND` pour informer le parent du contrôle de la barre de couleurs.  Dans la macro, le paramètre d'ID de commande est la valeur que vous avez assignée au bouton de la barre de couleurs à l'étape 1 \(ID\_CHAR\_COLOR dans cet exemple\).  Pour plus d'informations, consultez les classes de [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md), de [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md), de [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md), de [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md), et de [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md) .  
  
## Exemple  
 L'exemple suivant montre comment configurer une discrimination raciale en utilisant différentes méthodes dans la classe d' `CMFCColorBar` .  Les méthodes définissent l'horizontale et les marges verticales, permettent l'autre bouton, créent une fenêtre de contrôle de la barre de couleurs, et affecte la couleur sélectionnée.  Cet exemple fait partie de [Nouvel exemples de contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/CPP/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/CPP/cmfccolorbar-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## Configuration requise  
 **en\-tête :** afxcolorbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)