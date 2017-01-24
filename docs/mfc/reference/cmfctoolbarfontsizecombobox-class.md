---
title: "CMFCToolBarFontSizeComboBox Class | Microsoft Docs"
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
  - "CMFCToolBarFontSizeComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarFontSizeComboBox class"
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarFontSizeComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un bouton de barre d'outils qui contient un contrôle zone de liste déroulante qui permet à l'utilisateur de sélectionner une taille de police.  
  
## Syntaxe  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](../Topic/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox.md)|Construit un objet `CMFCToolBarFontSizeComboBox`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](../Topic/CMFCToolBarFontSizeComboBox::GetTwipSize.md)|Retourne la taille de police sélectionnée dans les twips.|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](../Topic/CMFCToolBarFontSizeComboBox::RebuildFontSizes.md)|Remplit liste de zone de liste déroulante de toutes les tailles de police prises en charge pour une police spécifiée.|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](../Topic/CMFCToolBarFontSizeComboBox::SetTwipSize.md)|Définit la taille de police dans les twips.|  
  
## Notes  
 Vous pouvez utiliser un objet d' `CMFCToolBarFontSizeComboBox` avec un objet de [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md) pour permettre à un utilisateur de sélectionner une police et une taille de police.  
  
 Vous pouvez ajouter un bouton de zone de liste déroulante de taille de police à une barre d'outils comme vous ajoutez un bouton de zone de liste déroulante de la police.  Pour plus d'informations, consultez [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
 Lorsque l'utilisateur sélectionne une nouvelle police dans un objet d' `CMFCToolBarFontComboBox` , vous pouvez remplir une zone de liste déroulante de taille de police de tailles prises en charge pour cette police à l'aide de la méthode de [CMFCToolBarFontSizeComboBox::RebuildFontSizes](../Topic/CMFCToolBarFontSizeComboBox::RebuildFontSizes.md) .  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCToolBarFontSizeComboBox` pour configurer un objet d' `CMFCToolBarFontSizeComboBox` .  L'exemple montre comment récupérer la taille de police, dans les twips, de la zone de texte, remplir la zone de liste déroulante de taille de police avec toutes les tailles valides de police donnée, et spécifie la taille de police dans les twips.  Cet extrait de code fait partie d' [Exemple de protection de Word](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/CPP/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## Configuration requise  
 **en\-tête :** afxtoolbarfontcombobox.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [Procédure pas à pas : placement de contrôles dans les barres d'outils](../../mfc/walkthrough-putting-controls-on-toolbars.md)