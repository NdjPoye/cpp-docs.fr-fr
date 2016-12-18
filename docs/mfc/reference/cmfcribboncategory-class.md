---
title: "CMFCRibbonCategory Class | Microsoft Docs"
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
  - "CMFCRibbonCategory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonCategory class"
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
caps.latest.revision: 38
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonCategory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCRibbonCategory` implémente un onglet de ruban qui contient un groupe de [panneaux de ruban](../../mfc/reference/cmfcribbonpanel-class.md).  
  
## Syntaxe  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonCategory::CMFCRibbonCategory](../Topic/CMFCRibbonCategory::CMFCRibbonCategory.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonCategory::AddHidden](../Topic/CMFCRibbonCategory::AddHidden.md)|Ajoute un élément masqué à la catégorie ruban.|  
|[CMFCRibbonCategory::AddPanel](../Topic/CMFCRibbonCategory::AddPanel.md)|Ajoute un nouveau panneau à la catégorie ruban.|  
|[CMFCRibbonCategory::CopyFrom](../Topic/CMFCRibbonCategory::CopyFrom.md)||  
|[CMFCRibbonCategory::FindByData](../Topic/CMFCRibbonCategory::FindByData.md)||  
|[CMFCRibbonCategory::FindByID](../Topic/CMFCRibbonCategory::FindByID.md)||  
|[CMFCRibbonCategory::FindPanelWithElem](../Topic/CMFCRibbonCategory::FindPanelWithElem.md)||  
|[CMFCRibbonCategory::GetContextID](../Topic/CMFCRibbonCategory::GetContextID.md)|Retourne l'ID de contexte de la catégorie ruban.|  
|[CMFCRibbonCategory::GetData](../Topic/CMFCRibbonCategory::GetData.md)|Retourne des données définies par l'utilisateur associées à la catégorie ruban.|  
|[CMFCRibbonCategory::GetDroppedDown](../Topic/CMFCRibbonCategory::GetDroppedDown.md)||  
|[CMFCRibbonCategory::GetElements](../Topic/CMFCRibbonCategory::GetElements.md)||  
|[CMFCRibbonCategory::GetElementsByID](../Topic/CMFCRibbonCategory::GetElementsByID.md)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](../Topic/CMFCRibbonCategory::GetFirstVisibleElement.md)|Obtenez un premier élément visible qui appartiennent à la catégorie ruban.|  
|[CMFCRibbonCategory::GetFocused](../Topic/CMFCRibbonCategory::GetFocused.md)|Retourne un élément ayant le focus.|  
|[CMFCRibbonCategory::GetHighlighted](../Topic/CMFCRibbonCategory::GetHighlighted.md)|Retourne un élément en surbrillance.|  
|[CMFCRibbonCategory::GetImageCount](../Topic/CMFCRibbonCategory::GetImageCount.md)||  
|[CMFCRibbonCategory::GetImageSize](../Topic/CMFCRibbonCategory::GetImageSize.md)||  
|[CMFCRibbonCategory::GetItemIDsList](../Topic/CMFCRibbonCategory::GetItemIDsList.md)||  
|[CMFCRibbonCategory::GetLastVisibleElement](../Topic/CMFCRibbonCategory::GetLastVisibleElement.md)|Obtenez un dernier élément visible qui appartiennent à la catégorie ruban|  
|[CMFCRibbonCategory::GetLargeImages](../Topic/CMFCRibbonCategory::GetLargeImages.md)|Retourne une référence à la liste de grandes icônes que la catégorie ruban utilise.|  
|[CMFCRibbonCategory::GetMaxHeight](../Topic/CMFCRibbonCategory::GetMaxHeight.md)||  
|[CMFCRibbonCategory::GetName](../Topic/CMFCRibbonCategory::GetName.md)||  
|[CMFCRibbonCategory::GetPanel](../Topic/CMFCRibbonCategory::GetPanel.md)|Retourne un pointeur vers le panneau de ruban qui est défini à l'index spécifié.|  
|[CMFCRibbonCategory::GetPanelCount](../Topic/CMFCRibbonCategory::GetPanelCount.md)|Retourne le nombre de panneaux de ruban dans la catégorie ruban.|  
|[CMFCRibbonCategory::GetPanelFromPoint](../Topic/CMFCRibbonCategory::GetPanelFromPoint.md)||  
|[CMFCRibbonCategory::GetPanelIndex](../Topic/CMFCRibbonCategory::GetPanelIndex.md)|Retourne l'index du panneau spécifié de ruban.|  
|[CMFCRibbonCategory::GetParentButton](../Topic/CMFCRibbonCategory::GetParentButton.md)||  
|[CMFCRibbonCategory::GetParentMenuBar](../Topic/CMFCRibbonCategory::GetParentMenuBar.md)||  
|[CMFCRibbonCategory::GetParentRibbonBar](../Topic/CMFCRibbonCategory::GetParentRibbonBar.md)||  
|[CMFCRibbonCategory::GetRect](../Topic/CMFCRibbonCategory::GetRect.md)||  
|[CMFCRibbonCategory::GetSmallImages](../Topic/CMFCRibbonCategory::GetSmallImages.md)|Retourne une référence à la liste des petites images que la catégorie utilise.|  
|[CMFCRibbonCategory::GetTabColor](../Topic/CMFCRibbonCategory::GetTabColor.md)|Retourne la couleur actuelle de la catégorie ruban tableau.|  
|[CMFCRibbonCategory::GetTabRect](../Topic/CMFCRibbonCategory::GetTabRect.md)||  
|[CMFCRibbonCategory::GetTextTopLine](../Topic/CMFCRibbonCategory::GetTextTopLine.md)||  
|[CMFCRibbonCategory::GetVisibleElements](../Topic/CMFCRibbonCategory::GetVisibleElements.md)|Obtient tous les éléments visibles qui appartiennent à la catégorie ruban.|  
|[CMFCRibbonCategory::HighlightPanel](../Topic/CMFCRibbonCategory::HighlightPanel.md)||  
|[CMFCRibbonCategory::HitTest](../Topic/CMFCRibbonCategory::HitTest.md)||  
|[CMFCRibbonCategory::HitTestEx](../Topic/CMFCRibbonCategory::HitTestEx.md)||  
|[CMFCRibbonCategory::HitTestScrollButtons](../Topic/CMFCRibbonCategory::HitTestScrollButtons.md)||  
|[CMFCRibbonCategory::IsActive](../Topic/CMFCRibbonCategory::IsActive.md)||  
|[CMFCRibbonCategory::IsVisible](../Topic/CMFCRibbonCategory::IsVisible.md)|Détermine si la catégorie ruban est visible.|  
|[CMFCRibbonCategory::IsWindows7Look](../Topic/CMFCRibbonCategory::IsWindows7Look.md)|Indique si le ruban parent a l'apparence de style Windows 7 \(petite touche application rectangulaire\)|  
|[CMFCRibbonCategory::NotifyControlCommand](../Topic/CMFCRibbonCategory::NotifyControlCommand.md)||  
|[CMFCRibbonCategory::OnCancelMode](../Topic/CMFCRibbonCategory::OnCancelMode.md)||  
|[CMFCRibbonCategory::OnDraw](../Topic/CMFCRibbonCategory::OnDraw.md)||  
|[CMFCRibbonCategory::OnDrawImage](../Topic/CMFCRibbonCategory::OnDrawImage.md)||  
|[CMFCRibbonCategory::OnDrawMenuBorder](../Topic/CMFCRibbonCategory::OnDrawMenuBorder.md)||  
|[CMFCRibbonCategory::OnKey](../Topic/CMFCRibbonCategory::OnKey.md)|Appelé par l'infrastructure lorsqu'un utilisateur appuie sur un bouton de clavier.|  
|[CMFCRibbonCategory::OnLButtonDown](../Topic/CMFCRibbonCategory::OnLButtonDown.md)||  
|[CMFCRibbonCategory::OnLButtonUp](../Topic/CMFCRibbonCategory::OnLButtonUp.md)||  
|[CMFCRibbonCategory::OnMouseMove](../Topic/CMFCRibbonCategory::OnMouseMove.md)||  
|[CMFCRibbonCategory::OnRTLChanged](../Topic/CMFCRibbonCategory::OnRTLChanged.md)||  
|[CMFCRibbonCategory::OnScrollHorz](../Topic/CMFCRibbonCategory::OnScrollHorz.md)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](../Topic/CMFCRibbonCategory::OnUpdateCmdUI.md)||  
|[CMFCRibbonCategory::RecalcLayout](../Topic/CMFCRibbonCategory::RecalcLayout.md)||  
|[CMFCRibbonCategory::RemovePanel](../Topic/CMFCRibbonCategory::RemovePanel.md)||  
|[CMFCRibbonCategory::ReposPanels](../Topic/CMFCRibbonCategory::ReposPanels.md)||  
|[CMFCRibbonCategory::SetCollapseOrder](../Topic/CMFCRibbonCategory::SetCollapseOrder.md)|Définit l'ordre de réduction des panneaux de ruban qui sont présents dans la catégorie ruban.|  
|[CMFCRibbonCategory::SetData](../Topic/CMFCRibbonCategory::SetData.md)|Stocke des données définies par l'utilisateur dans la catégorie ruban.|  
|[CMFCRibbonCategory::SetKeys](../Topic/CMFCRibbonCategory::SetKeys.md)|Assigne un keytip à la catégorie ruban.|  
|[CMFCRibbonCategory::SetName](../Topic/CMFCRibbonCategory::SetName.md)||  
|[CMFCRibbonCategory::SetTabColor](../Topic/CMFCRibbonCategory::SetTabColor.md)|Définit la couleur de la catégorie ruban.|  
  
## Notes  
 En général, vous créez une catégorie ruban indirectement en appelant [CMFCRibbonBar::AddCategory](../Topic/CMFCRibbonBar::AddCategory.md), qui retourne un pointeur à la catégorie ruban nouvellement créée.  Vous ajoutez des panneaux à la catégorie en appelant [CMFCRibbonCategory::AddPanel](../Topic/CMFCRibbonCategory::AddPanel.md).  
  
 La classe d' `CMFCRibbonTab` dessine des catégories ruban.  Elle est dérivée de [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md).  
  
 Cet exemple suivant montre comment créer une catégorie ruban et ajouter un panneau à celui\-ci.  
  
 `// Create a new ribbon category and get a pointer to it`  
  
 `CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory`  
  
 `(_T("&Write"),           // Category name`  
  
 `IDB_WRITE,              // Category small images (16 x 16)`  
  
 `IDB_WRITE_LARGE);   // Category large images (32 x 32)`  
  
 `// Add a panel to the new category`  
  
 `CMFCRibbonPanel* pPanel = pCategory->AddPanel (`  
  
 `_T("Clipboard"),                       // Panel name`  
  
 `m_PanelIcons.ExtractIcon (0));  // Panel icon`  
  
 Le diagramme suivant illustre une illustration de la catégorie d'accueil de l'exemple d'application de RibbonApp.  
  
 ![Image CMFCRibbonCategory](../../mfc/reference/media/cmfcribboncategory.png "CMFCRibbonCategory")  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)  
  
## Configuration requise  
 **en\-tête :** afxribboncategory.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)