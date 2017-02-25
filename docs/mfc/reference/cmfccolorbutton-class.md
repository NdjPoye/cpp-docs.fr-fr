---
title: "CMFCColorButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorButton class"
  - "CMFCColorButton::m_bAltColorDlg data member"
  - "CMFCColorButton::m_bAutoSetFocus data member"
  - "CMFCColorButton::m_Color data member"
  - "CMFCColorButton::m_ColorAutomatic data member"
  - "CMFCColorButton::m_lstDocColors data member"
  - "CMFCColorButton::m_nColumns data member"
  - "CMFCColorButton::m_pPalette data member"
  - "CMFCColorButton::m_pPopup data member"
  - "CMFCColorButton::m_strAutoColorText data member"
  - "CMFCColorButton::m_strDocColorsText data member"
  - "CMFCColorButton::m_strOtherText data member"
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# CMFCColorButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorButton` et les classes de [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md) sont utilisés ensemble pour implémenter un contrôle de sélecteur de couleurs.  
  
## Syntaxe  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorButton::CMFCColorButton](../Topic/CMFCColorButton::CMFCColorButton.md)|Construit un nouvel objet `CMFCColorButton`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](../Topic/CMFCColorButton::EnableAutomaticButton.md)|Active et désactive un bouton « automatique » qui est positionnée au\-dessus de les boutons normaux de couleur.  \(Le bouton automatique du système standard est étiqueté **Automatique**.\)|  
|[CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md)|Active et désactive un « autre » bouton qui est positionné sous les boutons normaux de couleur.  \(Le système standard « autre » bouton est étiqueté **Plus les couleurs…**.\)|  
|[CMFCColorButton::GetAutomaticColor](../Topic/CMFCColorButton::GetAutomaticColor.md)|Extrait la couleur automatique actuelle.|  
|[CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md)|Extrait la couleur d'un bouton.|  
|[CMFCColorButton::SetColor](../Topic/CMFCColorButton::SetColor.md)|Définit la couleur d'un bouton.|  
|[CMFCColorButton::SetColorName](../Topic/CMFCColorButton::SetColorName.md)|Définit un nom de couleur.|  
|[CMFCColorButton::SetColumnsNumber](../Topic/CMFCColorButton::SetColumnsNumber.md)|Définit le nombre de colonnes dans la boîte de dialogue du sélecteur de couleurs.|  
|[CMFCColorButton::SetDocumentColors](../Topic/CMFCColorButton::SetDocumentColors.md)|Spécifie une liste de couleurs de document spécifique qui s'affichent dans la boîte de dialogue du sélecteur de couleurs.|  
|[CMFCColorButton::SetPalette](../Topic/CMFCColorButton::SetPalette.md)|Spécifie une palette de couleurs de l'affichage standard.|  
|[CMFCColorButton::SizeToContent](../Topic/CMFCColorButton::SizeToContent.md)|Modifie la taille du contrôle bouton, selon son texte et sa taille de l'image.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](../Topic/CMFCColorButton::IsDrawXPTheme.md)|Indique si le bouton en cours de couleur est affiché dans le style de Windows XP.|  
|[CMFCColorButton::OnDraw](../Topic/CMFCColorButton::OnDraw.md)|Appelé par l'infrastructure pour afficher une image du bouton.|  
|[CMFCColorButton::OnDrawBorder](../Topic/CMFCColorButton::OnDrawBorder.md)|Appelé par l'infrastructure pour afficher la bordure du bouton.|  
|[CMFCColorButton::OnDrawFocusRect](../Topic/CMFCColorButton::OnDrawFocusRect.md)|Appelé par l'infrastructure pour afficher un rectangle de focus lorsque le bouton a le focus.|  
|[CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)|Appelé par l'infrastructure lorsque la boîte de dialogue du sélecteur de couleurs est sur le point d'être affiché.|  
|[CMFCColorButton::RebuildPalette](../Topic/CMFCColorButton::RebuildPalette.md)|Initialise le membre protégée par `m_pPalette` à la palette spécifiée ou à la palette système par défaut.|  
|[CMFCColorButton::UpdateColor](../Topic/CMFCColorButton::UpdateColor.md)|Appelé par l'infrastructure lorsque l'utilisateur sélectionne une couleur dans la palette de la boîte de dialogue du sélecteur de couleurs.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|`m_bAltColorDlg`|Valeur booléenne.  Si `TRUE`, l'infrastructure affiche la boîte de dialogue de couleur de [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) lorsque *l'autre* utilisateur clique sur, ou si `FALSE`, la boîte de dialogue de couleur système.  La valeur par défaut est `TRUE`.  Pour plus d'informations, consultez [CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md).|  
|`m_bAutoSetFocus`|Valeur booléenne.  Si `TRUE`, l'infrastructure place le focus dans le menu de couleur lorsque le menu s'affiche, ou si `FALSE`, ne modifie pas le focus.  La valeur par défaut est `TRUE`.|  
|[CMFCColorButton::m\_bEnabledInCustomizeMode](../Topic/CMFCColorButton::m_bEnabledInCustomizeMode.md)|Indique si le mode de personnalisation est activé pour le bouton de couleur.|  
|`m_Color`|Une valeur de [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) .  Contient la couleur sélectionnée.|  
|`m_ColorAutomatic`|Une valeur de [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) .  Contient la couleur par défaut sélectionnée.|  
|`m_Colors`|[CArray](../../mfc/reference/carray-class.md) des valeurs de [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) .  Contient les couleurs disponibles.|  
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) des valeurs de [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) .  Contient les couleurs du document actif.|  
|`m_nColumns`|Entier.  Contient le nombre de colonnes à afficher dans la grille de couleurs dans un menu de sélection de couleurs.|  
|`m_pPalette`|Un pointeur vers [CPalette](../../mfc/reference/cpalette-class.md).  Contient les couleurs disponibles dans le menu actuel de sélection de couleurs.|  
|`m_pPopup`|Un pointeur vers un objet de [CMFCColorPopupMenu Class](../../mfc/reference/cmfccolorpopupmenu-class.md) .  Le menu de sélection de couleurs qui s'affiche lorsque vous cliquez sur le bouton de couleur.|  
|`m_strAutoColorText`|une chaîne ;  L'étiquette du bouton « automatique » dans un menu de sélection de couleurs.|  
|`m_strDocColorsText`|une chaîne ;  L'étiquette du bouton dans un menu de sélection de couleurs qui affiche le document couleurs.|  
|`m_strOtherText`|une chaîne ;  L'étiquette de la « nouvelle » bouton dans un menu de sélection de couleurs.|  
  
## Notes  
 Par défaut, la classe d' `CMFCColorButton` se comporte comme un bouton de commande qui ouvre une boîte de dialogue du sélecteur de couleurs.  La boîte de dialogue du sélecteur de couleurs contient un tableau de petits boutons de couleur et d'un « autre » bouton qui affiche un sélecteur de couleurs personnalisé.  \(Le système standard « autre » bouton est étiqueté **Plus les couleurs…**.\) Lorsqu'un utilisateur sélectionne une nouvelle couleur, l'objet d' `CMFCColorButton` reflète la modification et affiche la couleur sélectionnée.  
  
 Créez un contrôle bouton de couleur directement dans votre code, ou en utilisant l'outil **ClassWizard** et d'un modèle de boîte de dialogue.  Si vous créez un contrôle bouton de couleur directement, ajoutez une variable d' `CMFCColorButton` à votre application, puis appelez le constructeur et les méthodes d' `Create` d' `CMFCColorButton` objet.  Si vous utilisez **ClassWizard**, ajoutez une variable d' `CButton` à votre application, puis modifiez le type de la variable d' `CButton` par `CMFCColorButton`.  
  
 La boîte de dialogue du sélecteur de couleurs \([CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)\) est affichée par la méthode d' [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md) lorsque l'infrastructure appelle le gestionnaire d'événements d' `OnLButtonDown` .  La méthode d' [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md) peut être substituée pour prendre en charge la sélection de couleurs personnalisée.  
  
 l'objet d' `CMFCColorButton` informe son parent qu'une couleur change en l'envoyant une notification d' `WM_COMMAND | BN_CLICKED` .  Le parent utilise la méthode de [CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md) pour récupérer la couleur actuelle.  
  
## Exemple  
 L'exemple suivant montre comment configurer un bouton de couleur en utilisant différentes méthodes dans la classe d' `CMFCColorButton` .  Les méthodes fixent la couleur du bouton de couleur et de son nombre de colonnes, et permettent les boutons automatiques et autres.  Cet exemple est extrait d' [Exemple de démonstration de barre d'état](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/CPP/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/CPP/cmfccolorbutton-class_2.cpp)]  
  
## Configuration requise  
 **en\-tête :** afxcolorbutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette Class](../../mfc/reference/cpalette-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)   
 [CList Class](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)