---
title: "CMFCPropertyGridFileProperty Class | Microsoft Docs"
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
  - "CMFCPropertyGridFileProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridFileProperty class"
  - "CMFCPropertyGridFileProperty::OnClickButton method"
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridFileProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCPropertyGridFileProperty` prend en charge un élément de contrôle liste de propriétés qui ouvre une boîte de dialogue de sélection de fichier.  
  
## Syntaxe  
  
```  
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](../Topic/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty.md)|Construit un objet `CMFCPropertyGridFileProperty`.|  
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCPropertyGridFileProperty::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|`CMFCPropertyGridFileProperty::OnClickButton`|\(Substitutions [CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md).\)|  
  
### Remarques  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)  
  
## Configuration requise  
 **en\-tête :** afxpropertygridctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)