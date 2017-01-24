---
title: "CMFCPropertyGridFontProperty Class | Microsoft Docs"
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
  - "CMFCPropertyGridFontProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridFontProperty class"
  - "CMFCPropertyGridFontProperty::FormatProperty method"
  - "CMFCPropertyGridFontProperty::OnClickButton method"
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridFontProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCPropertyGridFileProperty` prend en charge un élément de contrôle liste de propriétés qui ouvre une boîte de dialogue de sélection de la police.  
  
## Syntaxe  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](../Topic/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty.md)|Construit un objet `CMFCPropertyGridFontProperty`.|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|Met en forme la représentation textuelle d'une valeur de propriété.  \(Substitutions [CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md).\)|  
|[CMFCPropertyGridFontProperty::GetColor](../Topic/CMFCPropertyGridFontProperty::GetColor.md)|Extrait la couleur de police que l'utilisateur choisit dans la boîte de dialogue Police.|  
|[CMFCPropertyGridFontProperty::GetLogFont](../Topic/CMFCPropertyGridFontProperty::GetLogFont.md)|Extrait la police que l'utilisateur choisit dans la boîte de dialogue Police.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|Appelé par l'infrastructure lorsque l'utilisateur clique sur un bouton qui est contenu dans une propriété.  \(Substitutions [CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md).\)|  
  
## Notes  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## Configuration requise  
 **en\-tête :** afxpropertygridctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)