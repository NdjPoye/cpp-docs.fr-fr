---
title: "CMFCPropertyGridProperty Class | Microsoft Docs"
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
  - "CMFCPropertyGridProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridProperty class"
ms.assetid: 36f3fabe-0efe-468b-8a0b-5a7956db38a2
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un objet d' `CMFCPropertyGridProperty` représente un élément de liste dans un contrôle de liste de propriétés.  
  
## Syntaxe  
  
```  
class CMFCPropertyGridProperty : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridProperty::CMFCPropertyGridProperty](../Topic/CMFCPropertyGridProperty::CMFCPropertyGridProperty.md)|Construit un objet `CMFCPropertyGridProperty`.|  
|`CMFCPropertyGridProperty::~CMFCPropertyGridProperty`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridProperty::AddOption](../Topic/CMFCPropertyGridProperty::AddOption.md)|Ajoute un nouvel élément de liste à un contrôle de liste de propriétés.|  
|[CMFCPropertyGridProperty::AddSubItem](../Topic/CMFCPropertyGridProperty::AddSubItem.md)|Ajoute un élément enfant à une propriété.|  
|[CMFCPropertyGridProperty::AdjustButtonRect](../Topic/CMFCPropertyGridProperty::AdjustButtonRect.md)|Appelé par le contrôle parent de liste de propriétés pour indiquer une propriété de redimensionner le rectangle englobant d'un bouton incorporé.|  
|[CMFCPropertyGridProperty::AdjustInPlaceEditRect](../Topic/CMFCPropertyGridProperty::AdjustInPlaceEditRect.md)|Récupère les limites de la zone de texte et du contrôle toupie facultatif qui sont utilisées pour définir une valeur de propriété.|  
|[CMFCPropertyGridProperty::AllowEdit](../Topic/CMFCPropertyGridProperty::AllowEdit.md)|Rend une propriété modifiables ou en lecture seule.|  
|[CMFCPropertyGridProperty::CreateInPlaceEdit](../Topic/CMFCPropertyGridProperty::CreateInPlaceEdit.md)|Appelé par l'infrastructure pour créer un contrôle modifiable pour une propriété.|  
|[CMFCPropertyGridProperty::CreateSpinControl](../Topic/CMFCPropertyGridProperty::CreateSpinControl.md)|Appelé par l'infrastructure pour créer un contrôle toupie modifiable.|  
|[CMFCPropertyGridProperty::Enable](../Topic/CMFCPropertyGridProperty::Enable.md)|Active ou désactive une propriété.|  
|[CMFCPropertyGridProperty::EnableSpinControl](../Topic/CMFCPropertyGridProperty::EnableSpinControl.md)|Active ou désactive un contrôle toupie utilisé pour modifier une valeur de propriété.|  
|[CMFCPropertyGridProperty::Expand](../Topic/CMFCPropertyGridProperty::Expand.md)|Augmente ou diminue une propriété qui contient des sous\-propriétés.|  
|[CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md)|Met en forme la représentation textuelle d'une valeur de propriété.|  
|[CMFCPropertyGridProperty::GetData](../Topic/CMFCPropertyGridProperty::GetData.md)|Récupère une valeur d' `DWORD` associée à une propriété.|  
|[CMFCPropertyGridProperty::GetDescription](../Topic/CMFCPropertyGridProperty::GetDescription.md)|Extrait une description de la propriété.|  
|[CMFCPropertyGridProperty::GetExpandedSubItems](../Topic/CMFCPropertyGridProperty::GetExpandedSubItems.md)|Récupère le nombre de sous\-articles développés.|  
|[CMFCPropertyGridProperty::GetHierarchyLevel](../Topic/CMFCPropertyGridProperty::GetHierarchyLevel.md)|Extrait l'index de base zéro du niveau de la hiérarchie de la propriété.|  
|[CMFCPropertyGridProperty::GetName](../Topic/CMFCPropertyGridProperty::GetName.md)|Extrait le nom de la propriété.|  
|[CMFCPropertyGridProperty::GetNameTooltip](../Topic/CMFCPropertyGridProperty::GetNameTooltip.md)|Appelé par l'infrastructure pour afficher le nom de la propriété dans une info\-bulle.|  
|[CMFCPropertyGridProperty::GetOption](../Topic/CMFCPropertyGridProperty::GetOption.md)|Extrait le texte de l'option spécifiée par un index.|  
|[CMFCPropertyGridProperty::GetOptionCount](../Topic/CMFCPropertyGridProperty::GetOptionCount.md)|Récupère le nombre d'options qui appartiennent à une propriété.|  
|[CMFCPropertyGridProperty::GetOriginalValue](../Topic/CMFCPropertyGridProperty::GetOriginalValue.md)|Extrait la valeur initiale de la propriété actuelle.|  
|[CMFCPropertyGridProperty::GetParent](../Topic/CMFCPropertyGridProperty::GetParent.md)|Extrait un pointeur vers une propriété parent.|  
|[CMFCPropertyGridProperty::GetRect](../Topic/CMFCPropertyGridProperty::GetRect.md)|Récupère le rectangle englobant d'une propriété.|  
|[CMFCPropertyGridProperty::GetSubItem](../Topic/CMFCPropertyGridProperty::GetSubItem.md)|Extrait une sous\-propriété identifiée par un index de base zéro.|  
|[CMFCPropertyGridProperty::GetSubItemsCount](../Topic/CMFCPropertyGridProperty::GetSubItemsCount.md)|Récupère le nombre de sous\-articles.|  
|`CMFCPropertyGridProperty::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCPropertyGridProperty::GetValue](../Topic/CMFCPropertyGridProperty::GetValue.md)|Récupère une valeur de propriété.|  
|[CMFCPropertyGridProperty::GetValueTooltip](../Topic/CMFCPropertyGridProperty::GetValueTooltip.md)|Appelé par l'infrastructure pour récupérer la représentation textuelle d'une valeur de propriété qui est ensuite affichée dans une info\-bulle.|  
|[CMFCPropertyGridProperty::HitTest](../Topic/CMFCPropertyGridProperty::HitTest.md)|Les points à la propriété objet qui correspond à l'élément de la liste des propriétés qui correspond à un point.|  
|[CMFCPropertyGridProperty::IsAllowEdit](../Topic/CMFCPropertyGridProperty::IsAllowEdit.md)|Indique si une propriété est modifiable.|  
|[CMFCPropertyGridProperty::IsEnabled](../Topic/CMFCPropertyGridProperty::IsEnabled.md)|Indique si une propriété est activée ou désactivée.|  
|[CMFCPropertyGridProperty::IsExpanded](../Topic/CMFCPropertyGridProperty::IsExpanded.md)|Indique si une propriété est développée ou réduite.|  
|[CMFCPropertyGridProperty::IsGroup](../Topic/CMFCPropertyGridProperty::IsGroup.md)|Indique si la propriété actuelle représente un groupe.|  
|[CMFCPropertyGridProperty::IsInPlaceEditing](../Topic/CMFCPropertyGridProperty::IsInPlaceEditing.md)|Indique si la propriété actuelle est modifiable.|  
|[CMFCPropertyGridProperty::IsModified](../Topic/CMFCPropertyGridProperty::IsModified.md)|Indique si la propriété actuelle est modifiée.|  
|[CMFCPropertyGridProperty::IsParentExpanded](../Topic/CMFCPropertyGridProperty::IsParentExpanded.md)|Indique si les parents de la propriété actuelle sont développés.|  
|[CMFCPropertyGridProperty::IsSelected](../Topic/CMFCPropertyGridProperty::IsSelected.md)|Indique si la propriété actuelle est sélectionnée.|  
|[CMFCPropertyGridProperty::IsVisible](../Topic/CMFCPropertyGridProperty::IsVisible.md)|Indique si la propriété actuelle est visible.|  
|[CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur un bouton qui est contenu dans une propriété.|  
|[CMFCPropertyGridProperty::OnClickName](../Topic/CMFCPropertyGridProperty::OnClickName.md)|Appelé par un contrôle parent de liste de propriétés lorsqu'un utilisateur clique sur le champ nom d'une propriété.|  
|[CMFCPropertyGridProperty::OnClickValue](../Topic/CMFCPropertyGridProperty::OnClickValue.md)|Appelé par un contrôle parent de liste de propriétés lorsqu'un utilisateur clique sur le champ de valeur d'une propriété.|  
|[CMFCPropertyGridProperty::OnCloseCombo](../Topic/CMFCPropertyGridProperty::OnCloseCombo.md)|Appelé par l'infrastructure lorsqu'une zone de liste déroulante contenue dans une propriété est fermée.|  
|[CMFCPropertyGridProperty::OnDblClk](../Topic/CMFCPropertyGridProperty::OnDblClk.md)|Appelé par l'infrastructure lorsque le doublon d'utilisateur clique sur une propriété.|  
|[CMFCPropertyGridProperty::OnDrawButton](../Topic/CMFCPropertyGridProperty::OnDrawButton.md)|Appelé par l'infrastructure pour dessiner un bouton qui est contenu dans une propriété.|  
|[CMFCPropertyGridProperty::OnDrawDescription](../Topic/CMFCPropertyGridProperty::OnDrawDescription.md)|Appelé par l'infrastructure pour afficher la description de la propriété.|  
|[CMFCPropertyGridProperty::OnDrawExpandBox](../Topic/CMFCPropertyGridProperty::OnDrawExpandBox.md)|Appelé par l'infrastructure pour dessiner un contrôle de zone de développement près d'une propriété qui contient des sous\-propriétés.|  
|[CMFCPropertyGridProperty::OnDrawName](../Topic/CMFCPropertyGridProperty::OnDrawName.md)|Appelé par l'infrastructure pour afficher le nom de la propriété.|  
|[CMFCPropertyGridProperty::OnDrawValue](../Topic/CMFCPropertyGridProperty::OnDrawValue.md)|Appelé par l'infrastructure pour afficher la valeur de propriété.|  
|[CMFCPropertyGridProperty::OnEdit](../Topic/CMFCPropertyGridProperty::OnEdit.md)|Appelé par l'infrastructure lorsque l'utilisateur est sur le point de modifier une valeur de propriété.|  
|[CMFCPropertyGridProperty::OnEndEdit](../Topic/CMFCPropertyGridProperty::OnEndEdit.md)|Appelé par l'infrastructure lorsque l'utilisateur a fini modifiant une valeur de propriété.|  
|[CMFCPropertyGridProperty::OnKillSelection](../Topic/CMFCPropertyGridProperty::OnKillSelection.md)||  
|[CMFCPropertyGridProperty::OnPosSizeChanged](../Topic/CMFCPropertyGridProperty::OnPosSizeChanged.md)||  
|[CMFCPropertyGridProperty::OnRClickName](../Topic/CMFCPropertyGridProperty::OnRClickName.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton droit de la souris dans la zone nom de la propriété.|  
|[CMFCPropertyGridProperty::OnRClickValue](../Topic/CMFCPropertyGridProperty::OnRClickValue.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton droit de la souris dans la zone de valeur de propriété.|  
|[CMFCPropertyGridProperty::OnSelectCombo](../Topic/CMFCPropertyGridProperty::OnSelectCombo.md)|Appelé par l'infrastructure lorsque l'utilisateur sélectionne un élément de la zone de liste déroulante modifiable.|  
|[CMFCPropertyGridProperty::OnSetCursor](../Topic/CMFCPropertyGridProperty::OnSetCursor.md)|Appelé par l'infrastructure lorsque le pointeur de la souris se déplace à un élément de propriété.|  
|[CMFCPropertyGridProperty::OnSetSelection](../Topic/CMFCPropertyGridProperty::OnSetSelection.md)||  
|[CMFCPropertyGridProperty::OnUpdateValue](../Topic/CMFCPropertyGridProperty::OnUpdateValue.md)|Appelé par l'infrastructure lorsque la valeur d'une propriété modifiable a changé.|  
|[CMFCPropertyGridProperty::PushChar](../Topic/CMFCPropertyGridProperty::PushChar.md)|Appel du contrôle de liste de propriétés lorsque la propriété est sélectionnée et de l'utilisateur entre un caractère.|  
|[CMFCPropertyGridProperty::Redraw](../Topic/CMFCPropertyGridProperty::Redraw.md)|Redessine la propriété.|  
|[CMFCPropertyGridProperty::RemoveAllOptions](../Topic/CMFCPropertyGridProperty::RemoveAllOptions.md)|Supprime toutes les options \(éléments\) d'une propriété.|  
|[CMFCPropertyGridProperty::RemoveSubItem](../Topic/CMFCPropertyGridProperty::RemoveSubItem.md)|Supprime le sous\-article spécifié.|  
|[CMFCPropertyGridProperty::ResetOriginalValue](../Topic/CMFCPropertyGridProperty::ResetOriginalValue.md)|Restaure la valeur d'origine d'une propriété modifiée.|  
|[CMFCPropertyGridProperty::SetData](../Topic/CMFCPropertyGridProperty::SetData.md)|Associe une valeur d' `DWORD` à une propriété.|  
|[CMFCPropertyGridProperty::SetDescription](../Topic/CMFCPropertyGridProperty::SetDescription.md)|Spécifie le texte qui décrit la propriété actuelle.|  
|[CMFCPropertyGridProperty::SetName](../Topic/CMFCPropertyGridProperty::SetName.md)|Définit le nom d'une propriété.|  
|[CMFCPropertyGridProperty::SetOriginalValue](../Topic/CMFCPropertyGridProperty::SetOriginalValue.md)|Définit la valeur d'origine d'une propriété modifiable.|  
|[CMFCPropertyGridProperty::SetValue](../Topic/CMFCPropertyGridProperty::SetValue.md)|Définit la valeur d'une propriété de grille des propriétés.|  
|[CMFCPropertyGridProperty::Show](../Topic/CMFCPropertyGridProperty::Show.md)|Affiche ou masque une propriété.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridProperty::CreateCombo](../Topic/CMFCPropertyGridProperty::CreateCombo.md)|Appelé par l'infrastructure pour ajouter une zone de liste déroulante à une propriété.|  
|[CMFCPropertyGridProperty::HasButton](../Topic/CMFCPropertyGridProperty::HasButton.md)|Indique si une propriété contient un bouton.|  
|[CMFCPropertyGridProperty::Init](../Topic/CMFCPropertyGridProperty::Init.md)|Appelé par l'infrastructure pour initialiser un objet de propriété.|  
|[CMFCPropertyGridProperty::IsSubItem](../Topic/CMFCPropertyGridProperty::IsSubItem.md)|Indique si la propriété spécifiée est un sous\-article de la propriété actuelle.|  
|[CMFCPropertyGridProperty::IsValueChanged](../Topic/CMFCPropertyGridProperty::IsValueChanged.md)|Indique si la valeur de la propriété actuelle a changé.|  
|[CMFCPropertyGridProperty::OnCtlColor](../Topic/CMFCPropertyGridProperty::OnCtlColor.md)|Appelé par l'infrastructure lorsqu'il doit extraire un pinceau pour remplir une couleur d'arrière\-plan d'une propriété.|  
|[CMFCPropertyGridProperty::OnDestroyWindow](../Topic/CMFCPropertyGridProperty::OnDestroyWindow.md)|Est appelé par l'infrastructure lorsqu'une propriété est perdue ou en modifiant terminé.|  
|[CMFCPropertyGridProperty::OnKillFocus](../Topic/CMFCPropertyGridProperty::OnKillFocus.md)|Appelé par l'infrastructure lorsque la propriété perd le focus d'entrée.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridProperty::m\_strFormatDouble](../Topic/CMFCPropertyGridProperty::m_strFormatDouble.md)|Chaîne de format pour une valeur de type double.|  
|[CMFCPropertyGridProperty::m\_strFormatFloat](../Topic/CMFCPropertyGridProperty::m_strFormatFloat.md)|Chaîne de format pour une valeur de type float.|  
|[CMFCPropertyGridProperty::m\_strFormatLong](../Topic/CMFCPropertyGridProperty::m_strFormatLong.md)|Chaîne de format pour une valeur de type long.|  
|[CMFCPropertyGridProperty::m\_strFormatShort](../Topic/CMFCPropertyGridProperty::m_strFormatShort.md)|Chaîne de format pour une valeur de type courte.|  
  
## Notes  
 Utilisez un objet d' `CMFCPropertyGridProperty` pour représenter une propriété, que vous ajoutez ensuite un contrôle de liste de propriétés.  Pour plus d'informations, consultez [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
 Un objet de propriété peut représenter des types de données tels que des chaînes, des dates, et booléens ou des valeurs entières.  Il peut contenir des propriétés enfants, ou il peut contenir un contrôle tel qu'une zone de liste déroulante ou un contrôle bouton.  
  
## Exemple  
 L'exemple suivant montre comment construire un objet d' `CMFCPropertyGridProperty` .  L'exemple montre également comment utiliser différentes méthodes dans la classe d' `CMFCPropertyGridProperty` pour ajouter une option, pour ajouter un sous\-article, pour permettre une propriété, et pour afficher une propriété.  Cet exemple fait partie de [Nouvel exemples de contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#27](../../mfc/reference/codesnippet/CPP/cmfcpropertygridproperty-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
## Configuration requise  
 **en\-tête :** afxpropertygridctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)