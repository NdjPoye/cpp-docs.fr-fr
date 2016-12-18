---
title: "CMFCButton Class | Microsoft Docs"
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
  - "CMFCButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCButton class"
  - "CMFCButton constructor"
  - "CMFCButton::CreateObject method"
  - "CMFCButton::DrawItem method"
  - "CMFCButton::OnDrawParentBackground method"
  - "CMFCButton::PreTranslateMessage method"
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
caps.latest.revision: 35
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCButton` ajoute des fonctionnalités à la classe de [CButton](../../mfc/reference/cbutton-class.md) comme aligner le texte du bouton, combiner le texte du bouton et une image, sélectionnez un curseur, et spécifier une info\-bulle.  
  
## Syntaxe  
  
```  
class CMFCButton : public CButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCButton::CMFCButton`|Constructeur par défaut.|  
|`CMFCButton::~CMFCButton`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCButton::CleanUp](../Topic/CMFCButton::CleanUp.md)|Réinitialise les variables internes et libère les ressources allouées telles que les images, des images, des icônes.|  
|`CMFCButton::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCButton::DrawItem`|Appelé par l'infrastructure lorsqu'un aspect visuel d'un bouton owner\-drawn a changé.  \(Substitutions [CButton::DrawItem](../Topic/CButton::DrawItem.md).\)|  
|[CMFCButton::EnableFullTextTooltip](../Topic/CMFCButton::EnableFullTextTooltip.md)|Spécifie s'il faut afficher le texte intégral d'une info\-bulle dans une large fenêtre d'info\-bulle ou une version tronquée du texte dans une petite fenêtre d'info\-bulle.|  
|[CMFCButton::EnableMenuFont](../Topic/CMFCButton::EnableMenuFont.md)|Spécifie si la police du texte du bouton est la même que la police de menu application.|  
|[CMFCButton::EnableWindowsTheming](../Topic/CMFCButton::EnableWindowsTheming.md)|Spécifie si le style de la bordure du bouton correspond au thème windows actuel.|  
|`CMFCButton::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCButton::GetToolTipCtrl](../Topic/CMFCButton::GetToolTipCtrl.md)|Retourne une référence au contrôle d'info\-bulle sous\-jacent.|  
|[CMFCButton::IsAutoCheck](../Topic/CMFCButton::IsAutoCheck.md)|Indique si une case à cocher ou une case d'option est un bouton automatique.|  
|[CMFCButton::IsAutorepeatCommandMode](../Topic/CMFCButton::IsAutorepeatCommandMode.md)|Indique si un bouton est défini en mode de répétition automatique.|  
|[CMFCButton::IsCheckBox](../Topic/CMFCButton::IsCheckBox.md)|Indique si un bouton est un bouton de case à cocher.|  
|[CMFCButton::IsChecked](../Topic/CMFCButton::IsChecked.md)|Indique si le bouton actuel est activée.|  
|[CMFCButton::IsHighlighted](../Topic/CMFCButton::IsHighlighted.md)|Indique si un bouton est mis en surbrillance.|  
|[CMFCButton::IsPressed](../Topic/CMFCButton::IsPressed.md)|Indique si un bouton est enfoncé et mis en surbrillance.|  
|[CMFCButton::IsPushed](../Topic/CMFCButton::IsPushed.md)|Indique si un bouton est enfoncé.|  
|[CMFCButton::IsRadioButton](../Topic/CMFCButton::IsRadioButton.md)|Indique si un bouton est une case d'option.|  
|[CMFCButton::IsWindowsThemingEnabled](../Topic/CMFCButton::IsWindowsThemingEnabled.md)|Indique si le style de la bordure du bouton correspond au thème windows actuel.|  
|`CMFCButton::OnDrawParentBackground`|Dessine l'arrière\-plan du parent d'un bouton dans la zone spécifiée.  \(Substitutions [AFX\_GLOBAL\_DATA::DrawParentBackground](../Topic/AFX_GLOBAL_DATA::DrawParentBackground.md).\)|  
|`CMFCButton::PreTranslateMessage`|Traduit des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows de [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et de [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  \(Substitutions [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCButton::SetAutorepeatMode](../Topic/CMFCButton::SetAutorepeatMode.md)|Définit un bouton au mode de répétition automatique.|  
|[CMFCButton::SetCheckedImage](../Topic/CMFCButton::SetCheckedImage.md)|Définit l'image pour un bouton est activé.|  
|[CMFCButton::SetFaceColor](../Topic/CMFCButton::SetFaceColor.md)|Définit la couleur d'arrière\-plan pour le texte du bouton.|  
|[CMFCButton::SetImage](../Topic/CMFCButton::SetImage.md)|Définit l'image pour un bouton.|  
|[CMFCButton::SetMouseCursor](../Topic/CMFCButton::SetMouseCursor.md)|Définit l'image du curseur.|  
|[CMFCButton::SetMouseCursorHand](../Topic/CMFCButton::SetMouseCursorHand.md)|Place le curseur vers l'image d'une main.|  
|[CMFCButton::SetStdImage](../Topic/CMFCButton::SetStdImage.md)|Utilise un objet d' `CMenuImages` pour définir l'image de bouton.|  
|[CMFCButton::SetTextColor](../Topic/CMFCButton::SetTextColor.md)|Définit la couleur du texte du bouton pour un bouton qui n'est pas sélectionné.|  
|[CMFCButton::SetTextHotColor](../Topic/CMFCButton::SetTextHotColor.md)|Définit la couleur du texte du bouton pour un bouton qui est sélectionné.|  
|[CMFCButton::SetTooltip](../Topic/CMFCButton::SetTooltip.md)|Associe une info\-bulle avec un bouton.|  
|[CMFCButton::SizeToContent](../Topic/CMFCButton::SizeToContent.md)|Redimensionne un bouton pour contenir le texte du bouton et image.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCButton::OnDraw](../Topic/CMFCButton::OnDraw.md)|Appelé par l'infrastructure pour dessiner un bouton.|  
|[CMFCButton::OnDrawBorder](../Topic/CMFCButton::OnDrawBorder.md)|Appelé par l'infrastructure pour dessiner la bordure d'un bouton.|  
|[CMFCButton::OnDrawFocusRect](../Topic/CMFCButton::OnDrawFocusRect.md)|Appelé par l'infrastructure pour dessiner un rectangle de focus d'un bouton.|  
|[CMFCButton::OnDrawText](../Topic/CMFCButton::OnDrawText.md)|Appelé par l'infrastructure pour dessiner le texte du bouton.|  
|[CMFCButton::OnFillBackground](../Topic/CMFCButton::OnFillBackground.md)|Appelé par l'infrastructure pour dessiner l'arrière\-plan du texte du bouton.|  
|[CMFCButton::SelectFont](../Topic/CMFCButton::SelectFont.md)|Extrait la police associée au contexte spécifié de périphérique.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCButton::m\_bDrawFocus](../Topic/CMFCButton::m_bDrawFocus.md)|Indique si dessiner un rectangle de focus autour d'un bouton.|  
|[CMFCButton::m\_bHighlightChecked](../Topic/CMFCButton::m_bHighlightChecked.md)|Indique si la mise en surbrillance un BS\_CHECKBOX\-style bouton événements lorsque le curseur pointe sur lui.|  
|[CMFCButton::m\_bRightImage](../Topic/CMFCButton::m_bRightImage.md)|Indique s'afficher une image à droite du bouton.|  
|[CMFCButton::m\_bTransparent](../Topic/CMFCButton::m_bTransparent.md)|Indique si le bouton est transparent.|  
|[CMFCButton::m\_nAlignStyle](../Topic/CMFCButton::m_nAlignStyle.md)|Spécifie l'alignement du texte du bouton.|  
|[CMFCButton::m\_nFlatStyle](../Topic/CMFCButton::m_nFlatStyle.md)|Spécifie le style du bouton, tel que sans frontière, en deux dimensions, le semi\- plate, ou le 3D.|  
  
## Notes  
 D'autres types de boutons sont dérivés de la classe d' `CMFCButton` , comme la classe de [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) , qui prend en charge des liens hypertexte, et la classe d' `CMFCColorButton` , qui prend en charge une boîte de dialogue du sélecteur de couleurs.  
  
 Le style d'un objet d' `CMFCButton` peut être *3D*, *plate*, *semi\- plate* ou *aucune bordure*.  Le texte du bouton peut être aligné à gauche, haut, ou centre d'un bouton.  Au moment de l'exécution, vous pouvez contrôler si les affichages de bouton du texte, une image, ou texte et une image.  Vous pouvez également spécifier qu'une image particulière du curseur soit affichée lorsque le curseur pointe sur un bouton.  
  
 Créez un contrôle bouton directement dans votre code, ou en utilisant l'outil **assistant Classe MFC** et d'un modèle de boîte de dialogue.  Si vous créez un contrôle bouton directement, ajoutez une variable d' `CMFCButton` à votre application, puis appelez le constructeur et les méthodes d' `Create` d' `CMFCButton` objet.  Si vous utilisez **assistant Classe MFC**, ajoutez une variable d' `CButton` à votre application, puis modifiez le type de la variable d' `CButton` par `CMFCButton`.  
  
 Pour gérer des messages de notification dans une application de boîte de dialogue, ajoutez une entrée de la table des messages et un gestionnaire d'événements pour chaque notification.  Les notifications envoyées par un objet d' `CMFCButton` sont les mêmes que celles envoyées par un objet d' `CButton` .  
  
## Exemple  
 L'exemple suivant montre comment configurer les propriétés du bouton en utilisant différentes méthodes dans la classe d' `CMFCButton` .  l'exemple fait partie de [Nouvel exemples de contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_4.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxbutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCLinkCtrl Class](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md)   
 [CMFCMenuButton, Classe](../../mfc/reference/cmfcmenubutton-class.md)