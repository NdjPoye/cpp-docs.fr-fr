---
title: "CMFCCaptionBar, Classe | Microsoft Docs"
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
  - "CMFCCaptionBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCaptionBar, classe"
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCCaptionBar, Classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un objet d' `CMFCCaptionBar` est une barre de contrôles qui peut afficher trois éléments : un bouton, une étiquette de texte, et une bitmap.  Il ne peut afficher un élément de chaque type à la fois.  Vous pouvez aligner chaque élément aux bords gauche ou droit du contrôle ou centre.  Vous pouvez également appliquer un plate ou un style 3D aux zones de haut et bas de la barre de légende.  
  
## Syntaxe  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md)|Crée le contrôle de barre de titre et l'attache à l'objet d' `CMFCCaptionBar`.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](../Topic/CMFCCaptionBar::DoesAllowDynInsertBefore.md)|Indique si un autre volet peut être dynamiquement inséré entre la barre de légende et son frame parent.  \(Substitutions [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CMFCCaptionBar::EnableButton](../Topic/CMFCCaptionBar::EnableButton.md)|Active ou désactive le bouton dans la barre de légende.|  
|[CMFCCaptionBar::GetAlignment](../Topic/CMFCCaptionBar::GetAlignment.md)|Retourne l'alignement de l'élément spécifié.|  
|[CMFCCaptionBar::GetBorderSize](../Topic/CMFCCaptionBar::GetBorderSize.md)|Retourne la taille de la bordure de la barre de légende.|  
|[CMFCCaptionBar::GetButtonRect](../Topic/CMFCCaptionBar::GetButtonRect.md)|Récupère le rectangle englobant du bouton sur la barre de légende.|  
|[CMFCCaptionBar::GetMargin](../Topic/CMFCCaptionBar::GetMargin.md)|Retourne la distance entre le bord des éléments de barre de titre et le bord du contrôle de barre de titre.|  
|[CMFCCaptionBar::IsMessageBarMode](../Topic/CMFCCaptionBar::IsMessageBarMode.md)|Spécifie si la barre de légende est en mode de barre des messages.|  
|[CMFCCaptionBar::RemoveBitmap](../Topic/CMFCCaptionBar::RemoveBitmap.md)|Supprime l'image bitmap de la barre de légende.|  
|[CMFCCaptionBar::RemoveButton](../Topic/CMFCCaptionBar::RemoveButton.md)|Supprime le bouton de la barre de légende.|  
|[CMFCCaptionBar::RemoveIcon](../Topic/CMFCCaptionBar::RemoveIcon.md)|Supprime l'icône de la barre de légende.|  
|[CMFCCaptionBar::RemoveText](../Topic/CMFCCaptionBar::RemoveText.md)|Supprime l'étiquette de texte de la barre de légende.|  
|[CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md)|Définit l'image bitmap pour la barre de légende.|  
|[CMFCCaptionBar::SetBorderSize](../Topic/CMFCCaptionBar::SetBorderSize.md)|Définit la taille de la bordure de la barre de légende.|  
|[CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md)|Définit le bouton pour la barre de légende.|  
|[CMFCCaptionBar::SetButtonPressed](../Topic/CMFCCaptionBar::SetButtonPressed.md)|Spécifie si reste du bouton est enfoncé.|  
|[CMFCCaptionBar::SetButtonToolTip](../Topic/CMFCCaptionBar::SetButtonToolTip.md)|Définit l'info\-bulle pour le bouton.|  
|[CMFCCaptionBar::SetFlatBorder](../Topic/CMFCCaptionBar::SetFlatBorder.md)|Définit le style de bordure de la barre de légende.|  
|[CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md)|Définit l'icône pour une barre de légende.|  
|[CMFCCaptionBar::SetImageToolTip](../Topic/CMFCCaptionBar::SetImageToolTip.md)|Définit l'info\-bulle de l'image pour la barre de légende.|  
|[CMFCCaptionBar::SetMargin](../Topic/CMFCCaptionBar::SetMargin.md)|Définit la distance entre le bord de l'élément de la barre de légende et le bord du contrôle de barre de titre.|  
|[CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md)|Définit l'étiquette de texte de la barre de légende.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](../Topic/CMFCCaptionBar::OnDrawBackground.md)|Appelé par l'infrastructure pour remplir arrière\-plan de la barre de légende.|  
|[CMFCCaptionBar::OnDrawBorder](../Topic/CMFCCaptionBar::OnDrawBorder.md)|Appelé par l'infrastructure pour dessiner la bordure de la barre de légende.|  
|[CMFCCaptionBar::OnDrawButton](../Topic/CMFCCaptionBar::OnDrawButton.md)|Appelé par l'infrastructure pour dessiner le bouton de la barre de légende.|  
|[CMFCCaptionBar::OnDrawImage](../Topic/CMFCCaptionBar::OnDrawImage.md)|Appelé par l'infrastructure pour dessiner l'image de la barre de légende.|  
|[CMFCCaptionBar::OnDrawText](../Topic/CMFCCaptionBar::OnDrawText.md)|Appelé par l'infrastructure pour dessiner le texte de la barre de légende.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCCaptionBar::m\_clrBarBackground](../Topic/CMFCCaptionBar::m_clrBarBackground.md)|La couleur d'arrière\-plan de la barre de légende.|  
|[CMFCCaptionBar::m\_clrBarBorder](../Topic/CMFCCaptionBar::m_clrBarBorder.md)|La couleur de la bordure de la barre de légende.|  
|[CMFCCaptionBar::m\_clrBarText](../Topic/CMFCCaptionBar::m_clrBarText.md)|La couleur du texte de la barre de légende.|  
  
## Notes  
 Pour créer une barre de légende, suivez ces étapes :  
  
1.  Construisez l'objet d' `CMFCCaptionBar` .  En général, vous ajoutez la barre de titre à une classe de fenêtre frame.  
  
2.  Appelez la méthode [CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md) pour créer le contrôle de barre de titre et le lier à l'objet d' `CMFCCaptionBar` .  
  
3.  Appelez [CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md), [CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md), [CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md), et [CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md) pour définir les éléments de barre de titre.  
  
 Lorsque vous affectez à l'élément de bouton, vous devez assigner un ID de commande du bouton.  Lorsque l'utilisateur clique sur le bouton, la barre de légende route les messages d' `WM_COMMAND` qui ont cet ID à la fenêtre frame parente.  
  
 La barre de légende peut également s'exécuter en mode de barre des messages, qui émule la barre des messages qui apparaît dans les applications Microsoft Office 2007.  En mode de barre des messages, la barre de titre affiche une bitmap, un message, et un bouton \(qui ouvre généralement une boîte de dialogue.\) Vous pouvez assigner une info\-bulle à la bitmap.  
  
 Pour activer le mode de barre des messages, l'appel [CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md) et définir le quatrième paramètre \(bIsMessageBarMode\) à `TRUE`.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCCaptionBar` .  L'exemple montre comment créer le contrôle de barre de titre, définir une bordure 3D de la barre de légende, définir la distance, en pixels, entre le bord des éléments de barre de titre et le bord du contrôle de barre de titre, le positionnement du bouton pour la barre de légende, définir l'info\-bulle pour le bouton, définir l'étiquette de texte de la barre de légende, définir l'image bitmap pour la barre de légende, et définir l'info\-bulle de l'image dans la barre de légende.  Cet extrait de code fait partie d' [Exemple 2007 de démonstration de MS Office](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/CPP/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/CPP/cmfccaptionbar-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## Configuration requise  
 **En\-tête :** afxcaptionbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)