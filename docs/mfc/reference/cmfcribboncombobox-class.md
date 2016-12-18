---
title: "CMFCRibbonComboBox Class | Microsoft Docs"
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
  - "CMFCRibbonComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonComboBox class"
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCRibbonComboBox` implémente un contrôle zone de liste déroulante que vous pouvez ajouter une barre de ruban, dans un panneau de ruban, ou à un menu contextuel du ruban.  
  
## Syntaxe  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## Membres  
  
### Constructeurs  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](../Topic/CMFCRibbonComboBox::CMFCRibbonComboBox.md)|Crée un objet de CMFCRibbonComboBox.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonComboBox::AddItem](../Topic/CMFCRibbonComboBox::AddItem.md)|Ajoute un seul élément à la zone de liste.|  
|[CMFCRibbonComboBox::DeleteItem](../Topic/CMFCRibbonComboBox::DeleteItem.md)|Supprime un élément spécifié de la zone de liste.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](../Topic/CMFCRibbonComboBox::EnableDropDownListResize.md)|Spécifie si la zone de liste peut modifier la taille lorsqu'elle supprime le bas.|  
|[CMFCRibbonComboBox::FindItem](../Topic/CMFCRibbonComboBox::FindItem.md)|Retourne l'index du premier élément de la zone de liste qui correspond à une chaîne spécifiée.|  
|[CMFCRibbonComboBox::GetCount](../Topic/CMFCRibbonComboBox::GetCount.md)|Retourne le nombre d'éléments dans la zone de liste.|  
|[CMFCRibbonComboBox::GetCurSel](../Topic/CMFCRibbonComboBox::GetCurSel.md)|Obtient l'index actuel de l'élément sélectionné dans la zone de liste.|  
|[CMFCRibbonComboBox::GetDropDownHeight](../Topic/CMFCRibbonComboBox::GetDropDownHeight.md)|Obtient la hauteur de la zone de liste lorsque la zone de liste est supprimée vers le bas.|  
|[CMFCRibbonComboBox::GetIntermediateSize](../Topic/CMFCRibbonComboBox::GetIntermediateSize.md)|Retourne la taille de la zone de liste déroulante comme affiché dans le mode intermédiaire.|  
|[CMFCRibbonComboBox::GetItem](../Topic/CMFCRibbonComboBox::GetItem.md)|Retourne la chaîne associée à un élément à un index spécifié dans la zone de liste.|  
|[CMFCRibbonComboBox::GetItemData](../Topic/CMFCRibbonComboBox::GetItemData.md)|Retourne les données associées à un élément à un index spécifié dans la zone de liste.|  
|[CMFCRibbonComboBox::HasEditBox](../Topic/CMFCRibbonComboBox::HasEditBox.md)|Indique si le contrôle contient une zone d'édition.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](../Topic/CMFCRibbonComboBox::IsResizeDropDownList.md)|Indique si la zone de liste peut être redimensionné.|  
|[CMFCRibbonComboBox::OnSelectItem](../Topic/CMFCRibbonComboBox::OnSelectItem.md)|Appelé par l'infrastructure lorsque l'utilisateur sélectionne un élément dans la zone de liste.|  
|[CMFCRibbonComboBox::RemoveAllItems](../Topic/CMFCRibbonComboBox::RemoveAllItems.md)|Supprime tous les éléments de la zone de liste et efface la zone d'édition.|  
|[CMFCRibbonComboBox::SelectItem](../Topic/CMFCRibbonComboBox::SelectItem.md)|Sélectionne un élément dans la zone de liste.|  
|[CMFCRibbonComboBox::SetDropDownHeight](../Topic/CMFCRibbonComboBox::SetDropDownHeight.md)|Définit la hauteur de la zone de liste lorsqu'elle est supprimée vers le bas.|  
  
## Notes  
 La zone de liste déroulante du ruban se compose d'une zone de liste combinée avec une étiquette statique ou l'étiquette qui peuvent être modifiées par l'utilisateur.  Vous devez spécifier que vous tapez souhaitent lorsque vous créez votre zone de liste déroulante du ruban.  
  
## Exemple  
 L'exemple suivant montre comment construire un objet avec de la classe d' `CMFCRibbonComboBox` , ajouter un élément à la zone de liste déroulante, sélectionnez un élément dans la zone de liste déroulante, puis ajouter une zone de liste déroulante dans un panneau.  
  
 [!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/CPP/cmfcribboncombobox-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## Configuration requise  
 **en\-tête :** afxribboncombobox.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonEdit Class](../../mfc/reference/cmfcribbonedit-class.md)