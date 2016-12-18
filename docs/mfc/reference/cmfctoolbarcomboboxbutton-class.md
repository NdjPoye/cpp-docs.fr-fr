---
title: "CMFCToolBarComboBoxButton Class | Microsoft Docs"
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
  - "CMFCToolBarComboBoxButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarComboBoxButton class"
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
caps.latest.revision: 30
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarComboBoxButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un bouton de barre d'outils qui contient un contrôle zone de liste déroulante \([CComboBox Class](../../mfc/reference/ccombobox-class.md)\).  
  
## Syntaxe  
  
```  
class CMFCToolBarComboBoxButton : public CMFCToolBarButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](../Topic/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton.md)|Construit un `CMFCToolBarComboBoxButton`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarComboBoxButton::AddItem](../Topic/CMFCToolBarComboBoxButton::AddItem.md)|Ajoute un élément à la fin de la liste déroulante.|  
|[CMFCToolBarComboBoxButton::AddSortedItem](../Topic/CMFCToolBarComboBoxButton::AddSortedItem.md)|Ajoute un élément à la liste déroulante.  L'ordre des éléments de la liste est spécifiée par `Compare`.|  
|[CMFCToolBarComboBoxButton::Compare](../Topic/CMFCToolBarComboBoxButton::Compare.md)|Compare deux éléments.  Appelé pour trier les éléments qu' `AddSortedItems` ajoute à la liste déroulante.|  
|[CMFCToolBarComboBoxButton::CreateEdit](../Topic/CMFCToolBarComboBoxButton::CreateEdit.md)|Crée un nouveau contrôle d'édition pour le bouton de zone de liste déroulante.|  
|[CMFCToolBarComboBoxButton::DeleteItem](../Topic/CMFCToolBarComboBoxButton::DeleteItem.md)|Supprime un élément de la liste déroulante.|  
|[CMFCToolBarComboBoxButton::FindItem](../Topic/CMFCToolBarComboBoxButton::FindItem.md)|Retourne l'index de l'élément qui contient une chaîne spécifiée.|  
|[CMFCToolBarComboBoxButton::GetByCmd](../Topic/CMFCToolBarComboBoxButton::GetByCmd.md)|Retourne un pointeur vers le bouton de zone de liste déroulante avec un ID de commande spécifiée|  
|[CMFCToolBarComboBoxButton::GetComboBox](../Topic/CMFCToolBarComboBoxButton::GetComboBox.md)|Retourne un pointeur vers le contrôle zone de liste déroulante incorporé dans le bouton de zone de liste déroulante.|  
|[CMFCToolBarComboBoxButton::GetCount](../Topic/CMFCToolBarComboBoxButton::GetCount.md)|Retourne le nombre d'éléments dans la liste déroulante.|  
|[CMFCToolBarComboBoxButton::GetCountAll](../Topic/CMFCToolBarComboBoxButton::GetCountAll.md)|Recherche le bouton de zone de liste déroulante qui a un ID de commande spécifiée  Retourne le nombre d'éléments dans la liste déroulante de ce bouton.|  
|[CMFCToolBarComboBoxButton::GetCurSel](../Topic/CMFCToolBarComboBoxButton::GetCurSel.md)|Retourne l'index de l'élément sélectionné dans la liste déroulante.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](../Topic/CMFCToolBarComboBoxButton::GetCurSelAll.md)|Recherche le bouton de zone de liste déroulante qui a un ID de commande spécifié, et retourne l'index de l'élément sélectionné dans la liste déroulante de ce bouton.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](../Topic/CMFCToolBarComboBoxButton::GetEditCtrl.md)|Retourne un pointeur vers le contrôle d'édition qui est incorporé dans le bouton de zone de liste déroulante.|  
|[CMFCToolBarComboBoxButton::GetItem](../Topic/CMFCToolBarComboBoxButton::GetItem.md)|Retourne la chaîne associée à un index spécifié dans la liste déroulante.|  
|[CMFCToolBarComboBoxButton::GetItemAll](../Topic/CMFCToolBarComboBoxButton::GetItemAll.md)|Recherche le bouton de zone de liste déroulante qui a un ID de commande spécifié, et retourne la chaîne associée à un index dans la liste déroulante de ce bouton.|  
|[CMFCToolBarComboBoxButton::GetItemData](../Topic/CMFCToolBarComboBoxButton::GetItemData.md)|Retourne la valeur 32 bits qui est associée à un index spécifié dans la liste déroulante.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](../Topic/CMFCToolBarComboBoxButton::GetItemDataAll.md)|Recherche le bouton de zone de liste déroulante qui a un ID de commande spécifié, et retourne la valeur 32 bits qui est associée à un index dans la liste déroulante de ce bouton.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](../Topic/CMFCToolBarComboBoxButton::GetItemDataPtrAll.md)|Recherche le bouton de zone de liste déroulante qui a un ID de commande spécifiée  Extrait la valeur 32 bits qui est associée à un index dans la liste déroulante de ce bouton, puis retourne la valeur 32 bits en tant que pointeur.|  
|[CMFCToolBarComboBoxButton::GetText](../Topic/CMFCToolBarComboBoxButton::GetText.md)|Retourne le texte du contrôle d'édition de la zone de liste déroulante.|  
|[CMFCToolBarComboBoxButton::GetTextAll](../Topic/CMFCToolBarComboBoxButton::GetTextAll.md)|Recherche le bouton de zone de liste déroulante qui a un ID de commande spécifiée, puis retourne le texte du contrôle d'édition de ce bouton.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](../Topic/CMFCToolBarComboBoxButton::IsCenterVert.md)|Détermine si les boutons de zone de liste déroulante dans l'application sont centrés ou alignés au début de la barre d'outils.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](../Topic/CMFCToolBarComboBoxButton::IsFlatMode.md)|Détermine si les boutons de zone de liste déroulante dans l'application ont une apparence à deux dimensions.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](../Topic/CMFCToolBarComboBoxButton::RemoveAllItems.md)|Supprime tous les éléments de la zone de liste et du contrôle d'édition de la zone de liste déroulante.|  
|[CMFCToolBarComboBoxButton::SelectItem](../Topic/CMFCToolBarComboBoxButton::SelectItem.md)|Sélectionne un élément dans la zone de liste déroulante en fonction de son index, valeur 32 bits, ou chaîne, et notifie le contrôle zone de liste déroulante sur la sélection.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](../Topic/CMFCToolBarComboBoxButton::SelectItemAll.md)|Recherche le bouton de zone de liste déroulante qui a un ID de commande spécifiée  Appelle `SelectItem` pour sélectionner un élément dans la zone de liste déroulante de ce bouton en fonction de sa chaîne, index, ou valeur 32 bits.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](../Topic/CMFCToolBarComboBoxButton::SetCenterVert.md)|Spécifie si les boutons de zone de liste déroulante dans l'application sont centrés verticalement ou alignés au début de la barre d'outils.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](../Topic/CMFCToolBarComboBoxButton::SetDropDownHeight.md)|Définit la hauteur de la zone de liste déroulante.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](../Topic/CMFCToolBarComboBoxButton::SetFlatMode.md)|Spécifie si les boutons de zone de liste déroulante dans l'application ont une apparence à deux dimensions.|  
  
## Notes  
 Pour ajouter un bouton de zone de liste déroulante à une barre d'outils, suivez ces étapes :  
  
 1.  Réservez un ID de ressource factice pour le bouton dans la ressource parente de barre d'outils.  
  
 2.  Construisez un objet `CMFCToolBarComboBoxButton`.  
  
 3.  Dans le gestionnaire de messages qui traite le message d' `AFX_WM_RESETTOOLBAR` , remplacez le bouton factice avec le nouveau bouton de zone de liste déroulante à l'aide de [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
 Pour plus d'informations, consultez [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md).  Pour obtenir un exemple d'un bouton de barre d'outils de zone de liste déroulante, consultez le projet VisualStudioDemo d'exemple.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCToolBarComboBoxButton` .  L'exemple montre comment activer la modification et les zones de liste déroulante, définissez la position verticale des boutons de zone de liste déroulante dans l'application, est fixé la hauteur de la zone de liste lorsqu'il est déplacé vers le bas, est fixé l'apparence en deux dimensions de style de boutons de zone de liste déroulante dans l'application, puis affectez le texte dans la zone d'édition du bouton de zone de liste déroulante.  Cet extrait de code fait partie d' [Exemple de démonstration de Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/CPP/cmfctoolbarcomboboxbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/CPP/cmfctoolbarcomboboxbutton-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxtoolbarcomboboxbutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md)