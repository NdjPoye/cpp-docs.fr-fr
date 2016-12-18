---
title: "CMFCPropertyGridColorProperty Class | Microsoft Docs"
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
  - "CMFCPropertyGridColorProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridColorProperty class"
  - "CMFCPropertyGridColorProperty::FormatProperty method"
  - "CMFCPropertyGridColorProperty::OnClickButton method"
  - "CMFCPropertyGridColorProperty::OnDrawValue method"
  - "CMFCPropertyGridColorProperty::OnEdit method"
  - "CMFCPropertyGridColorProperty::OnUpdateValue method"
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridColorProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe `CMFCPropertyGridColorProperty` prend en charge un élément de contrôle de liste de propriétés qui ouvre une boîte de dialogue de sélection de couleur.  
  
## Syntaxe  
  
```  
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](../Topic/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty.md)|Construit un objet `CMFCPropertyGridColorProperty`.|  
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Destructeur.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](../Topic/CMFCPropertyGridColorProperty::EnableAutomaticButton.md)|Active le bouton  *automatique* dans la boîte de dialogue de sélection de couleur.  \(Le bouton automatique standard s'intitule **Automatique**.\)|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](../Topic/CMFCPropertyGridColorProperty::EnableOtherButton.md)|Active le bouton *autre* dans la boîte de dialogue de sélection de couleur.  \(Le bouton autre standard s'intitule **Autres couleurs...**.\)|  
|`CMFCPropertyGridColorProperty::FormatProperty`|Met en forme la représentation textuelle d'une valeur de propriété.  \(Substitue [CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md).\)|  
|[CMFCPropertyGridColorProperty::GetColor](../Topic/CMFCPropertyGridColorProperty::GetColor.md)|Obtient la couleur actuelle de la propriété.|  
|`CMFCPropertyGridColorProperty::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|`CMFCPropertyGridColorProperty::OnClickButton`|Appelé par l'infrastructure quand l'utilisateur clique sur un bouton contenu dans une propriété.  \(Substitue [CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md).\)|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|Appelé par l'infrastructure pour afficher la valeur de propriété.  \(Substitue [CMFCPropertyGridProperty::OnDrawValue](../Topic/CMFCPropertyGridProperty::OnDrawValue.md).\)|  
|`CMFCPropertyGridColorProperty::OnEdit`|Appelé par l'infrastructure quand l'utilisateur s'apprête à modifier une valeur de propriété.  \(Substitue [CMFCPropertyGridProperty::OnEdit](../Topic/CMFCPropertyGridProperty::OnEdit.md).\)|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Appelé par l'infrastructure quand la valeur d'une propriété modifiable a changé.  \(Substitue [CMFCPropertyGridProperty::OnUpdateValue](../Topic/CMFCPropertyGridProperty::OnUpdateValue.md).\)|  
|[CMFCPropertyGridColorProperty::SetColor](../Topic/CMFCPropertyGridColorProperty::SetColor.md)|Définit une nouvelle couleur pour la propriété.|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](../Topic/CMFCPropertyGridColorProperty::SetColumnsNumber.md)|Spécifie le nombre de colonnes de la grille de propriétés de couleur actuelle.|  
|[CMFCPropertyGridColorProperty::SetOriginalValue](../Topic/CMFCPropertyGridColorProperty::SetOriginalValue.md)|Définit la valeur d'origine d'une propriété modifiable.|  
  
## Notes  
 La classe `CMFCPropertyGridColorProperty` prend en charge une propriété de couleur qui peut être ajoutée à un contrôle de liste de propriétés.  Pour plus d'informations, consultez [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## Exemple  
 L'exemple suivant montre comment construire un objet de la classe `CMFCPropertyGridColorProperty` et configurer cet objet à l'aide de différentes méthodes de la classe `CMFCPropertyGridColorProperty`.  Le code explique comment activer les boutons automatique et autre et comment définir la couleur et le nombre de colonnes.  Cet exemple fait partie de l'[exemple Nouveaux contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/CPP/cmfcpropertygridcolorproperty-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)  
  
## Configuration requise  
 **En\-tête :** afxpropertygridctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)