---
title: "CMFCRibbonPanel Class | Microsoft Docs"
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
  - "CMFCRibbonPanel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonPanel class"
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
caps.latest.revision: 34
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonPanel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un panneau qui contient un ensemble d'éléments du ruban.  Lorsque le panneau est dessiné, il affiche autant d'éléments que possible, vu la taille du panneau.  
  
## Syntaxe  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](../Topic/CMFCRibbonPanel::CMFCRibbonPanel.md)|Les éléments et initialise un objet d' `CMFCRibbonPanel` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md)|Ajoute un élément ruban dans le panneau.|  
|[CMFCRibbonPanel::AddSeparator](../Topic/CMFCRibbonPanel::AddSeparator.md)|Ajoute un séparateur dans le panneau de ruban.|  
|[CMFCRibbonPanel::AddToolBar](../Topic/CMFCRibbonPanel::AddToolBar.md)|Ajoute une barre d'outils dans le panneau de ruban.|  
|[CMFCRibbonPanel::FindByData](../Topic/CMFCRibbonPanel::FindByData.md)||  
|[CMFCRibbonPanel::FindByID](../Topic/CMFCRibbonPanel::FindByID.md)|Retourne un élément identifié par un ID de commande spécifiée|  
|[CMFCRibbonPanel::GetCaptionHeight](../Topic/CMFCRibbonPanel::GetCaptionHeight.md)||  
|[CMFCRibbonPanel::GetCount](../Topic/CMFCRibbonPanel::GetCount.md)|Retourne le nombre d'éléments dans le panneau de ruban.|  
|[CMFCRibbonPanel::GetData](../Topic/CMFCRibbonPanel::GetData.md)|Retourne des données définies par l'utilisateur associées au panneau.|  
|[CMFCRibbonPanel::GetDefaultButton](../Topic/CMFCRibbonPanel::GetDefaultButton.md)||  
|[CMFCRibbonPanel::GetDroppedDown](../Topic/CMFCRibbonPanel::GetDroppedDown.md)||  
|[CMFCRibbonPanel::GetElement](../Topic/CMFCRibbonPanel::GetElement.md)|Retourne l'élément ruban trouve à une position d'index spécifiée.|  
|[CMFCRibbonPanel::GetElements](../Topic/CMFCRibbonPanel::GetElements.md)|Récupère tous les éléments contenus dans le panneau de ruban.|  
|[CMFCRibbonPanel::GetElementsByID](../Topic/CMFCRibbonPanel::GetElementsByID.md)||  
|[CMFCRibbonPanel::GetFocused](../Topic/CMFCRibbonPanel::GetFocused.md)|Retourne un élément ayant le focus.|  
|[CMFCRibbonPanel::GetGalleryRect](../Topic/CMFCRibbonPanel::GetGalleryRect.md)|Retourne un rectangle englobant d'élément de la galerie.|  
|[CMFCRibbonPanel::GetHighlighted](../Topic/CMFCRibbonPanel::GetHighlighted.md)||  
|[CMFCRibbonPanel::GetIndex](../Topic/CMFCRibbonPanel::GetIndex.md)||  
|[CMFCRibbonPanel::GetItemIDsList](../Topic/CMFCRibbonPanel::GetItemIDsList.md)||  
|[CMFCRibbonPanel::GetName](../Topic/CMFCRibbonPanel::GetName.md)||  
|[CMFCRibbonPanel::GetParentButton](../Topic/CMFCRibbonPanel::GetParentButton.md)||  
|[CMFCRibbonPanel::GetParentCategory](../Topic/CMFCRibbonPanel::GetParentCategory.md)|Retourne la catégorie parente du panneau de ruban.|  
|[CMFCRibbonPanel::GetParentMenuBar](../Topic/CMFCRibbonPanel::GetParentMenuBar.md)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](../Topic/CMFCRibbonPanel::GetPreferedMenuLocation.md)||  
|[CMFCRibbonPanel::GetPressed](../Topic/CMFCRibbonPanel::GetPressed.md)||  
|[CMFCRibbonPanel::GetRect](../Topic/CMFCRibbonPanel::GetRect.md)||  
|[CMFCRibbonPanel::GetVisibleElements](../Topic/CMFCRibbonPanel::GetVisibleElements.md)|Obtient un tableau d'éléments visibles.|  
|[CMFCRibbonPanel::HasElement](../Topic/CMFCRibbonPanel::HasElement.md)||  
|[CMFCRibbonPanel::HitTest](../Topic/CMFCRibbonPanel::HitTest.md)||  
|[CMFCRibbonPanel::HitTestEx](../Topic/CMFCRibbonPanel::HitTestEx.md)||  
|[CMFCRibbonPanel::Insert](../Topic/CMFCRibbonPanel::Insert.md)|Insère un élément ruban à la position donnée.|  
|[CMFCRibbonPanel::InsertSeparator](../Topic/CMFCRibbonPanel::InsertSeparator.md)|Insère un séparateur à la position donnée.|  
|[CMFCRibbonPanel::IsCenterColumnVert](../Topic/CMFCRibbonPanel::IsCenterColumnVert.md)|Spécifie si tous les éléments du panneau doivent être centrés \(\) aligné verticalement, par la colonne.|  
|[CMFCRibbonPanel::IsCollapsed](../Topic/CMFCRibbonPanel::IsCollapsed.md)||  
|[CMFCRibbonPanel::IsHighlighted](../Topic/CMFCRibbonPanel::IsHighlighted.md)||  
|[CMFCRibbonPanel::IsJustifyColumns](../Topic/CMFCRibbonPanel::IsJustifyColumns.md)|Spécifie si toutes les colonnes de panneau ont la même largeur.|  
|[CMFCRibbonPanel::IsMainPanel](../Topic/CMFCRibbonPanel::IsMainPanel.md)||  
|[CMFCRibbonPanel::IsMenuMode](../Topic/CMFCRibbonPanel::IsMenuMode.md)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](../Topic/CMFCRibbonPanel::MakeGalleryItemVisible.md)|Fait défiler la galerie pour rendre l'élément spécifié de ruban visible.|  
|[CMFCRibbonPanel::OnKey](../Topic/CMFCRibbonPanel::OnKey.md)||  
|[CMFCRibbonPanel::RecalcWidths](../Topic/CMFCRibbonPanel::RecalcWidths.md)||  
|[CMFCRibbonPanel::Remove](../Topic/CMFCRibbonPanel::Remove.md)|Supprime et supprime éventuellement un élément situé à l'index spécifié.|  
|[CMFCRibbonPanel::RemoveAll](../Topic/CMFCRibbonPanel::RemoveAll.md)|Supprime tous les éléments du panneau de ruban.|  
|[CMFCRibbonPanel::Replace](../Topic/CMFCRibbonPanel::Replace.md)|Remplace un élément par un autre en fonction de leurs valeurs d'index respectives.|  
|[CMFCRibbonPanel::ReplaceByID](../Topic/CMFCRibbonPanel::ReplaceByID.md)|Remplace un élément par un autre en fonction d'un ID de commande spécifiée|  
|[CMFCRibbonPanel::SetCenterColumnVert](../Topic/CMFCRibbonPanel::SetCenterColumnVert.md)|Classe le panneau pour aligner les éléments verticalement, par la colonne.|  
|[CMFCRibbonPanel::SetData](../Topic/CMFCRibbonPanel::SetData.md)|Données définies par l'utilisateur associés au panneau de ruban.|  
|[CMFCRibbonPanel::SetElementMenu](../Topic/CMFCRibbonPanel::SetElementMenu.md)|Assigne un menu contextuel à l'élément dont l'ID de commande donnée|  
|[CMFCRibbonPanel::SetElementRTC](../Topic/CMFCRibbonPanel::SetElementRTC.md)|Ajoute un élément ruban spécifié par les informations fournies de classe de runtime dans le panneau de ruban.|  
|[CMFCRibbonPanel::SetElementRTCByID](../Topic/CMFCRibbonPanel::SetElementRTCByID.md)|Ajoute un élément ruban spécifié par les informations fournies de classe de runtime dans le panneau de ruban.|  
|[CMFCRibbonPanel::SetFocused](../Topic/CMFCRibbonPanel::SetFocused.md)|Définit le focus à l'élément spécifié de ruban.|  
|[CMFCRibbonPanel::SetJustifyColumns](../Topic/CMFCRibbonPanel::SetJustifyColumns.md)|Active ou désactive la justification de colonne.|  
|[CMFCRibbonPanel::SetKeys](../Topic/CMFCRibbonPanel::SetKeys.md)|Définit le raccourci clavier qui affiche le volet du ruban.|  
|[CMFCRibbonPanel::ShowPopup](../Topic/CMFCRibbonPanel::ShowPopup.md)||  
  
## Notes  
 Les panneaux de ruban sont des regroupements logiques les tâches associées que vous créez dans des catégories ruban.  À mesure que la taille du ruban change, la disposition du panneau règle automatiquement pour afficher autant d'éléments que possible.  
  
 Vous pouvez obtenir des panneaux d'un ruban qui est contenu dans une catégorie ruban en appelant la méthode de [CMFCRibbonCategory::GetPanel](../Topic/CMFCRibbonCategory::GetPanel.md) .  
  
## Exemple  
 L'exemple suivant montre comment configurer un objet d' `CMFCRibbonPanel` en utilisant différentes méthodes dans la classe d' `CMFCRibbonPanel` .  L'exemple suivant indique comment définir le raccourci clavier qui affiche le panneau de ruban, alignent les éléments du panneau verticalement par la colonne, et permettent la justification de colonne.  Cet extrait de code fait partie d' [Exemple 2007 de démonstration de MS Office](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#10](../../mfc/reference/codesnippet/CPP/cmfcribbonpanel-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## Configuration requise  
 **en\-tête :** afxRibbonPanel.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CMFCRibbonCategory Class](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)