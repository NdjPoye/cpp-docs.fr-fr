---
title: "CMFCFontComboBox Class | Microsoft Docs"
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
  - "CMFCFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontComboBox class"
  - "CMFCFontComboBox::CompareItem method"
  - "CMFCFontComboBox::DrawItem method"
  - "CMFCFontComboBox::MeasureItem method"
  - "CMFCFontComboBox::PreTranslateMessage method"
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: 29
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCFontComboBox` crée un contrôle zone de liste déroulante qui contient une liste des polices.  
  
## Syntaxe  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](../Topic/CMFCFontComboBox::CMFCFontComboBox.md)|Construit un objet `CMFCFontComboBox`.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCFontComboBox::CompareItem`|Appelé par l'infrastructure pour déterminer la position relative d'un nouvel élément dans la zone de liste triée du contrôle zone de liste déroulante actuel de la police.  \(Substitutions [CComboBox::CompareItem](../Topic/CComboBox::CompareItem.md).\)|  
|`CMFCFontComboBox::DrawItem`|Appelé par l'infrastructure pour dessiner un élément spécifié dans le contrôle zone de liste déroulante actuel de la police.  \(Substitutions [CComboBox::DrawItem](../Topic/CComboBox::DrawItem.md).\)|  
|[CMFCFontComboBox::GetSelFont](../Topic/CMFCFontComboBox::GetSelFont.md)|Récupère des informations sur la police sélectionnée.|  
|`CMFCFontComboBox::MeasureItem`|Appelé par l'infrastructure pour informer les fenêtres des dimensions de la zone de liste dans le contrôle zone de liste déroulante actuel de la police.  \(Substitutions [CComboBox::MeasureItem](../Topic/CComboBox::MeasureItem.md).\)|  
|`CMFCFontComboBox::PreTranslateMessage`|Traduit des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows de [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et de [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  \(Substitutions [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCFontComboBox::SelectFont](../Topic/CMFCFontComboBox::SelectFont.md)|Sélectionne la police correspondant aux critères spécifiés dans la zone de liste déroulante de la police.|  
|[CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md)|Initialise la liste d'éléments dans la zone de liste déroulante de la police.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCFontComboBox::m\_bDrawUsingFont](../Topic/CMFCFontComboBox::m_bDrawUsingFont.md)|Indique à l'infrastructure que la police à utiliser pour dessiner l'élément étiquette dans la zone de liste déroulante actuelle de la police.|  
  
## Notes  
 Pour utiliser un objet d' `CMFCFontComboBox` dans une boîte de dialogue, ajoutez une variable d' `CMFCFontComboBox` à la classe de boîte de dialogue.  Puis dans la méthode d' `OnInitDialog` de classe de boîte de dialogue, appelez la méthode de [CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md) pour initialiser la liste d'éléments du contrôle zone de liste déroulante.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## Configuration requise  
 **en\-tête :** afxfontcombobox.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)