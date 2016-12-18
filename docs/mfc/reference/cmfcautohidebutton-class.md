---
title: "CMFCAutoHideButton Class | Microsoft Docs"
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
  - "CMFCAutoHideButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAutoHideButton class"
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCAutoHideButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bouton qui affiche ou masque une [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) configurée pour être masquée.  
  
## Syntaxe  
  
```  
class CMFCAutoHideButton : public CObject  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCAutoHideButton::BringToTop](../Topic/CMFCAutoHideButton::BringToTop.md)||  
|[CMFCAutoHideButton::Create](../Topic/CMFCAutoHideButton::Create.md)|Crée et initialise les bouton masquer automatiquement.|  
|[CMFCAutoHideButton::GetAlignment](../Topic/CMFCAutoHideButton::GetAlignment.md)|Récupère l'alignement du bouton masquer automatiquement.|  
|[CMFCAutoHideButton::GetAutoHideWindow](../Topic/CMFCAutoHideButton::GetAutoHideWindow.md)|Retourne l'objet [CDockablePane](../../mfc/reference/cdockablepane-class.md) associé au bouton Masquer automatiquement.|  
|[CMFCAutoHideButton::GetParentToolBar](../Topic/CMFCAutoHideButton::GetParentToolBar.md)||  
|[CMFCAutoHideButton::GetRect](../Topic/CMFCAutoHideButton::GetRect.md)||  
|[CMFCAutoHideButton::GetSize](../Topic/CMFCAutoHideButton::GetSize.md)|Détermine la taille du bouton masquer automatiquement.|  
|[CMFCAutoHideButton::GetTextSize](../Topic/CMFCAutoHideButton::GetTextSize.md)|Retourne la taille de l'étiquette de texte du bouton masquer automatiquement.|  
|[CMFCAutoHideButton::HighlightButton](../Topic/CMFCAutoHideButton::HighlightButton.md)|Met en évidence le bouton masquer automatiquement.|  
|[CMFCAutoHideButton::IsActive](../Topic/CMFCAutoHideButton::IsActive.md)|Indique si le bouton masquer automatiquement est actif.|  
|[CMFCAutoHideButton::IsHighlighted](../Topic/CMFCAutoHideButton::IsHighlighted.md)|Fait état de la mise en évidence du bouton masquer automatiquement.|  
|[CMFCAutoHideButton::IsHorizontal](../Topic/CMFCAutoHideButton::IsHorizontal.md)|Détermine si le bouton masquer automatiquement est horizontal ou vertical.|  
|[CMFCAutoHideButton::IsTop](../Topic/CMFCAutoHideButton::IsTop.md)||  
|[CMFCAutoHideButton::IsVisible](../Topic/CMFCAutoHideButton::IsVisible.md)|Indique si le bouton est visible.|  
|[CMFCAutoHideButton::Move](../Topic/CMFCAutoHideButton::Move.md)||  
|[CMFCAutoHideButton::OnDraw](../Topic/CMFCAutoHideButton::OnDraw.md)|L'infrastructure appelle cette méthode au moment de dessiner le bouton masquer automatiquement.|  
|[CMFCAutoHideButton::OnDrawBorder](../Topic/CMFCAutoHideButton::OnDrawBorder.md)|L'infrastructure appelle cette méthode au moment de dessiner la bordure d'un bouton masquer automatiquement.|  
|[CMFCAutoHideButton::OnFillBackground](../Topic/CMFCAutoHideButton::OnFillBackground.md)|L'infrastructure appelle cette méthode au moment de remplir l'arrière\-plan d'un bouton masquer automatiquement.|  
|[CMFCAutoHideButton::ReplacePane](../Topic/CMFCAutoHideButton::ReplacePane.md)||  
|[CMFCAutoHideButton::ShowAttachedWindow](../Topic/CMFCAutoHideButton::ShowAttachedWindow.md)|Affiche ou masque la [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) associée.|  
|[CMFCAutoHideButton::ShowButton](../Topic/CMFCAutoHideButton::ShowButton.md)|Affiche ou masque le bouton masquer automatiquement.|  
|[CMFCAutoHideButton::UnSetAutoHideMode](../Topic/CMFCAutoHideButton::UnSetAutoHideMode.md)||  
  
## Notes  
 Au moment de la création, l'objet `CMFCAutoHideButton` est attaché à une [CDockablePane Class](../../mfc/reference/cdockablepane-class.md).  L'objet `CDockablePane` est masqué ou affiché quand l'utilisateur interagit avec l'objet `CMFCAutoHideButton`.  
  
 Par défaut, l'infrastructure crée automatiquement un `CMFCAutoHideButton` quand l'utilisateur active le bouton masquer automatiquement.  L'infrastructure peut créer un élément d'une classe d'interface utilisateur personnalisée à la place de la classe `CMFCAutoHideButton`.  Pour spécifier la classe d'interface utilisateur personnalisée que l'infrastructure doit utiliser, attribuez à la variable de membre statique `CMFCAutoHideBar::m_pAutoHideButtonRTS` la même valeur que la classe d'interface utilisateur personnalisée.  Par défaut, cette variable a la valeur `CMFCAutoHideButton`.  
  
## Exemple  
 L'exemple suivant montre comment construire un objet `CMFCAutoHideButton` et utiliser différentes méthodes de la classe `CMFCAutoHideButton`.  L'exemple montre comment initialiser un objet `CMFCAutoHideButton` en utilisant sa méthode `Create`, afficher la classe `CDockablePane` associée et afficher le bouton masquer automatiquement.  
  
 [!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/CPP/cmfcautohidebutton-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)  
  
## Configuration requise  
 **En\-tête :** afxautohidebutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCAutoHideBar Class](../../mfc/reference/cmfcautohidebar-class.md)   
 [CAutoHideDockSite Class](../../mfc/reference/cautohidedocksite-class.md)