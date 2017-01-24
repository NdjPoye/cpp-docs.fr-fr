---
title: "CMFCPropertyGridCtrl Class | Microsoft Docs"
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
  - "CMFCPropertyGridCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridCtrl class"
  - "CMFCPropertyGridCtrl::accHitTest method"
  - "CMFCPropertyGridCtrl::accLocation method"
  - "CMFCPropertyGridCtrl::get_accChild method"
  - "CMFCPropertyGridCtrl::get_accDefaultAction method"
  - "CMFCPropertyGridCtrl::get_accDescription method"
  - "CMFCPropertyGridCtrl::get_accName method"
  - "CMFCPropertyGridCtrl::get_accRole method"
  - "CMFCPropertyGridCtrl::get_accState method"
  - "CMFCPropertyGridCtrl::get_accValue method"
  - "CMFCPropertyGridCtrl::PreTranslateMessage method"
ms.assetid: 95877cae-2311-4a2a-9031-0c8c3cf0a5f9
caps.latest.revision: 35
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Prend en charge un contrôle de grille des propriétés modifiables qui peut afficher des propriétés dans l'ordre alphabétique ou hiérarchique.  
  
## Syntaxe  
  
```  
class CMFCPropertyGridCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](../Topic/CMFCPropertyGridCtrl::CMFCPropertyGridCtrl.md)|Construit un objet `CMFCPropertyGridCtrl`.|  
|`CMFCPropertyGridCtrl::~CMFCPropertyGridCtrl`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCPropertyGridCtrl::accHitTest`|Appelé par l'infrastructure pour récupérer l'élément enfant ou l'objet enfant à un point donné sur l'écran.  \(Substitutions [CWnd::accHitTest](../Topic/CWnd::accHitTest.md).\)|  
|`CMFCPropertyGridCtrl::accLocation`|Appelé par l'infrastructure pour récupérer l'emplacement actuel de l'écran de l'objet spécifié.  \(Substitutions [CWnd::accLocation](../Topic/CWnd::accLocation.md).\)|  
|[CMFCPropertyGridCtrl::accSelect](../Topic/CMFCPropertyGridCtrl::accSelect.md)|Appelé par l'infrastructure pour modifier la sélection ou pour déplacer le focus clavier de l'objet spécifié.  \(Substitutions [CWnd::accSelect](../Topic/CWnd::accSelect.md).\)|  
|[CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md)|Ajoute une nouvelle propriété à un contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::AlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::AlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::CloseColorPopup](../Topic/CMFCPropertyGridCtrl::CloseColorPopup.md)|Ferme la boîte de dialogue de sélection de couleurs.|  
|[CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md)|Crée un contrôle de grille des propriétés et l'attache à l'objet contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::DeleteProperty](../Topic/CMFCPropertyGridCtrl::DeleteProperty.md)|Supprime la propriété spécifiée du contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::DrawControlBarColors](../Topic/CMFCPropertyGridCtrl::DrawControlBarColors.md)||  
|[CMFCPropertyGridCtrl::EnableDescriptionArea](../Topic/CMFCPropertyGridCtrl::EnableDescriptionArea.md)|Active ou désactive la zone de description qui s'affiche sous la liste de propriétés.|  
|[CMFCPropertyGridCtrl::EnableHeaderCtrl](../Topic/CMFCPropertyGridCtrl::EnableHeaderCtrl.md)|Active ou désactive le contrôle header en haut du contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::EnsureVisible](../Topic/CMFCPropertyGridCtrl::EnsureVisible.md)|Fait défiler un contrôle de grille des propriétés et développe des éléments de propriété jusqu'à ce que la propriété spécifiée est visible.|  
|[CMFCPropertyGridCtrl::ExpandAll](../Topic/CMFCPropertyGridCtrl::ExpandAll.md)|Augmente ou diminue tous les nœuds de contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::FindItemByData](../Topic/CMFCPropertyGridCtrl::FindItemByData.md)|Récupère la propriété associée à une valeur définie par l'utilisateur d' `DWORD` .|  
|`CMFCPropertyGridCtrl::get_accChild`|Appelé par l'infrastructure pour récupérer l'adresse d'une interface d' `IDispatch` pour l'enfant spécifié.  \(Substitutions [CWnd::get\_accChild](../Topic/CWnd::get_accChild.md).\)|  
|[CMFCPropertyGridCtrl::get\_accChildCount](../Topic/CMFCPropertyGridCtrl::get_accChildCount.md)|Appelé par l'infrastructure pour récupérer le nombre d'enfants appartenant à cet objet.  \(Substitutions [CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md).\)|  
|`CMFCPropertyGridCtrl::get_accDefaultAction`|Appelé par l'infrastructure pour récupérer une chaîne qui décrit l'action par défaut de l'objet.  \(Substitutions [CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md).\)|  
|`CMFCPropertyGridCtrl::get_accDescription`|Appelé par l'infrastructure pour récupérer une chaîne qui décrit l'apparence visuelle de l'objet spécifié.  \(Substitutions [CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md).\)|  
|[CMFCPropertyGridCtrl::get\_accFocus](../Topic/CMFCPropertyGridCtrl::get_accFocus.md)|Appelé par l'infrastructure pour récupérer l'objet qui a le focus clavier.  \(Substitutions [CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md).\)|  
|[CMFCPropertyGridCtrl::get\_accHelp](../Topic/CMFCPropertyGridCtrl::get_accHelp.md)|Appelé par l'infrastructure pour récupérer la chaîne de propriété d' `Help` d'un objet.  \(Substitutions [CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md).\)|  
|[CMFCPropertyGridCtrl::get\_accHelpTopic](../Topic/CMFCPropertyGridCtrl::get_accHelpTopic.md)|Appelé par l'infrastructure pour récupérer le chemin d'accès complet du fichier d' `WinHelp`associé à l'objet spécifié et l'identificateur de la rubrique appropriée dans ce fichier.  \(Substitutions [CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md).\)|  
|[CMFCPropertyGridCtrl::get\_accKeyboardShortcut](../Topic/CMFCPropertyGridCtrl::get_accKeyboardShortcut.md)|Appelé par l'infrastructure pour récupérer la touche de raccourci spécifiée ou le raccourci de l'objet.  \(Substitutions [CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md).\)|  
|`CMFCPropertyGridCtrl::get_accName`|Appelé par l'infrastructure pour extraire le nom de l'objet spécifié.  \(Substitutions [CWnd::get\_accName](../Topic/CWnd::get_accName.md).\)|  
|`CMFCPropertyGridCtrl::get_accRole`|Appelé par l'infrastructure pour récupérer des informations qui décrivent le rôle de l'objet spécifié.  \(Substitutions [CWnd::get\_accRole](../Topic/CWnd::get_accRole.md).\)|  
|[CMFCPropertyGridCtrl::get\_accSelection](../Topic/CMFCPropertyGridCtrl::get_accSelection.md)|Appelé par l'infrastructure pour récupérer les enfants sélectionnés de faire objet.  \(Substitutions [CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md).\)|  
|`CMFCPropertyGridCtrl::get_accState`|Appelé par l'infrastructure pour récupérer l'état actuel de l'objet spécifié.  \(Substitutions [CWnd::get\_accState](../Topic/CWnd::get_accState.md).\)|  
|`CMFCPropertyGridCtrl::get_accValue`|Appelé par l'infrastructure pour récupérer la valeur de l'objet spécifié.  \(Substitutions [CWnd::get\_accValue](../Topic/CWnd::get_accValue.md).\)|  
|[CMFCPropertyGridCtrl::GetBkColor](../Topic/CMFCPropertyGridCtrl::GetBkColor.md)|Extrait la couleur d'arrière\-plan du contrôle de grille des propriétés actuel.|  
|[CMFCPropertyGridCtrl::GetBoldFont](../Topic/CMFCPropertyGridCtrl::GetBoldFont.md)|Extrait la police windows qui du texte dans le contrôle de grille des propriétés actuel dans le style gras.|  
|[CMFCPropertyGridCtrl::GetCurSel](../Topic/CMFCPropertyGridCtrl::GetCurSel.md)|Récupère la propriété sélectionnée.|  
|[CMFCPropertyGridCtrl::GetCustomColors](../Topic/CMFCPropertyGridCtrl::GetCustomColors.md)|Récupère les couleurs personnalisées qui sont actuellement définies pour les éléments de contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::GetDescriptionHeight](../Topic/CMFCPropertyGridCtrl::GetDescriptionHeight.md)|Extrait la hauteur de la zone de description située en bas du contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::GetDescriptionRows](../Topic/CMFCPropertyGridCtrl::GetDescriptionRows.md)|Récupère le nombre de lignes dans le champ de description du contrôle de grille des propriétés actuel.|  
|[CMFCPropertyGridCtrl::GetHeaderCtrl](../Topic/CMFCPropertyGridCtrl::GetHeaderCtrl.md)|Récupère l'objet interne de [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) que l'infrastructure utilise pour afficher le contrôle de grille des propriétés actuel.|  
|[CMFCPropertyGridCtrl::GetHeaderHeight](../Topic/CMFCPropertyGridCtrl::GetHeaderHeight.md)|Extrait la hauteur de l'en\-tête de contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::GetLeftColumnWidth](../Topic/CMFCPropertyGridCtrl::GetLeftColumnWidth.md)|Extrait la largeur de la colonne de gauche du contrôle de grille des propriétés actuellement, qui contient le nom de chaque propriété.|  
|[CMFCPropertyGridCtrl::GetListRect](../Topic/CMFCPropertyGridCtrl::GetListRect.md)|Récupère le rectangle englobant du contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::GetProperty](../Topic/CMFCPropertyGridCtrl::GetProperty.md)|Extrait un pointeur vers l'objet de propriété correspondant à l'index spécifié d'un élément de contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::GetPropertyColumnWidth](../Topic/CMFCPropertyGridCtrl::GetPropertyColumnWidth.md)|Extrait la largeur actuelle de la colonne qui contient les valeurs de propriété.|  
|[CMFCPropertyGridCtrl::GetPropertyCount](../Topic/CMFCPropertyGridCtrl::GetPropertyCount.md)|Récupère le nombre de propriétés dans un contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::GetRowHeight](../Topic/CMFCPropertyGridCtrl::GetRowHeight.md)|Extrait la hauteur d'une ligne dans le contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::GetScrollBarCtrl](../Topic/CMFCPropertyGridCtrl::GetScrollBarCtrl.md)|Extrait un pointeur vers le contrôle de barre de défilement dans le contrôle de grille des propriétés.  \(Substitutions [CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md).\)|  
|[CMFCPropertyGridCtrl::GetTextColor](../Topic/CMFCPropertyGridCtrl::GetTextColor.md)|Extrait la couleur du texte des éléments de propriété dans le contrôle de grille des propriétés actuel.|  
|`CMFCPropertyGridCtrl::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCPropertyGridCtrl::HitTest](../Topic/CMFCPropertyGridCtrl::HitTest.md)|Extrait un pointeur vers l'objet de propriété qui correspond à un élément de contrôle de grille des propriétés si un point spécifié dans l'élément.  Cette méthode indique également la zone dans le contrôle de grille des propriétés qui contient le point.|  
|[CMFCPropertyGridCtrl::InitHeader](../Topic/CMFCPropertyGridCtrl::InitHeader.md)|Initialise l'objet interne de [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) que l'infrastructure utilise pour afficher le contrôle de grille des propriétés actuel.|  
|[CMFCPropertyGridCtrl::IsAlphabeticMode](../Topic/CMFCPropertyGridCtrl::IsAlphabeticMode.md)|Indique si un contrôle de grille des propriétés est en mode alphabétique.|  
|[CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::IsDescriptionArea](../Topic/CMFCPropertyGridCtrl::IsDescriptionArea.md)|Indique si le champ de description du contrôle de grille de propriétés s'affiche.|  
|[CMFCPropertyGridCtrl::IsGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::IsGroupNameFullWidth.md)|Indique si chaque nom de groupe de propriétés est affiché entre la largeur du contrôle de grille des propriétés actuel.|  
|[CMFCPropertyGridCtrl::IsHeaderCtrl](../Topic/CMFCPropertyGridCtrl::IsHeaderCtrl.md)|Indique si le contrôle header est affiché.|  
|[CMFCPropertyGridCtrl::IsMarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::IsMarkModifiedProperties.md)|Indique comment le contrôle de grille des propriétés affiche les propriétés modifiées.|  
|[CMFCPropertyGridCtrl::IsShowDragContext](../Topic/CMFCPropertyGridCtrl::IsShowDragContext.md)|Indique si l'infrastructure redessine les colonnes de nom et valeur du contrôle de grille des propriétés actuel lorsqu'un utilisateur redimensionne les colonnes.|  
|[CMFCPropertyGridCtrl::IsVSDotNetLook](../Topic/CMFCPropertyGridCtrl::IsVSDotNetLook.md)|Indique si l'apparence du contrôle de grille de propriétés est dans le style utilisé par VS .NET.|  
|[CMFCPropertyGridCtrl::MarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::MarkModifiedProperties.md)|Indique comment afficher les propriétés modifiées.|  
|`CMFCPropertyGridCtrl::PreTranslateMessage`|Utilisé par la classe [CWinApp](../../mfc/reference/cwinapp-class.md) pour convertir des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows de [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et de [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  \(Substitutions [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCPropertyGridCtrl::RemoveAll](../Topic/CMFCPropertyGridCtrl::RemoveAll.md)|Supprime tous les objets de propriété d'un contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::ResetOriginalValues](../Topic/CMFCPropertyGridCtrl::ResetOriginalValues.md)|Restaure la valeur d'origine de toutes les propriétés.|  
|[CMFCPropertyGridCtrl::SetAlphabeticMode](../Topic/CMFCPropertyGridCtrl::SetAlphabeticMode.md)|Définit ou mode alphabétique de réinitialise.|  
|[CMFCPropertyGridCtrl::SetBoolLabels](../Topic/CMFCPropertyGridCtrl::SetBoolLabels.md)|Spécifie le texte des étiquettes booléennes.|  
|[CMFCPropertyGridCtrl::SetCurSel](../Topic/CMFCPropertyGridCtrl::SetCurSel.md)|Sélectionne une propriété dans un contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::SetCustomColors](../Topic/CMFCPropertyGridCtrl::SetCustomColors.md)|Spécifie des couleurs personnalisées pour différents éléments de contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::SetDescriptionRows](../Topic/CMFCPropertyGridCtrl::SetDescriptionRows.md)|Spécifie le nombre de lignes à afficher dans la section de description du contrôle de grille des propriétés actuel.|  
|[CMFCPropertyGridCtrl::SetGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::SetGroupNameFullWidth.md)|Spécifie s'il faut afficher la largeur du nom de catégorie pour un groupe de propriétés dans le contrôle de grille des propriétés actuel.|  
|[CMFCPropertyGridCtrl::SetListDelimiter](../Topic/CMFCPropertyGridCtrl::SetListDelimiter.md)|Définit un caractère qui sera utilisé comme séparateur dans une liste de valeurs de propriété.|  
|[CMFCPropertyGridCtrl::SetShowDragContext](../Topic/CMFCPropertyGridCtrl::SetShowDragContext.md)|Spécifie si l'infrastructure redessine les colonnes de nom et valeur du contrôle de grille des propriétés actuel lorsqu'un utilisateur redimensionne les colonnes.|  
|[CMFCPropertyGridCtrl::SetVSDotNetLook](../Topic/CMFCPropertyGridCtrl::SetVSDotNetLook.md)|Définit l'apparence du contrôle de grille des propriétés du style utilisé dans VS .NET.|  
|[CMFCPropertyGridCtrl::UpdateColor](../Topic/CMFCPropertyGridCtrl::UpdateColor.md)|Définit la valeur de couleur de la propriété de couleur sélectionnée.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyGridCtrl::AdjustLayout](../Topic/CMFCPropertyGridCtrl::AdjustLayout.md)|Redessine le contrôle de grille des propriétés et ses propriétés.|  
|[CMFCPropertyGridCtrl::CompareProps](../Topic/CMFCPropertyGridCtrl::CompareProps.md)|Appelé par le contrôle de grille de propriétés pour trier les propriétés.|  
|[CMFCPropertyGridCtrl::EditItem](../Topic/CMFCPropertyGridCtrl::EditItem.md)|Appelé par l'infrastructure lorsque l'utilisateur commence à modifier une propriété.|  
|[CMFCPropertyGridCtrl::EndEditItem](../Topic/CMFCPropertyGridCtrl::EndEditItem.md)|Appelé par l'infrastructure lorsque l'utilisateur arrête de modifier une propriété.|  
|[CMFCPropertyGridCtrl::Init](../Topic/CMFCPropertyGridCtrl::Init.md)|Appelé par l'infrastructure pour initialiser un contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::OnChangeSelection](../Topic/CMFCPropertyGridCtrl::OnChangeSelection.md)|Appelé par l'infrastructure lorsque la sélection actuelle est modifiée.|  
|[CMFCPropertyGridCtrl::OnClickButton](../Topic/CMFCPropertyGridCtrl::OnClickButton.md)|Appelé par l'infrastructure lorsqu'un bouton de propriété est effectué sur.|  
|[CMFCPropertyGridCtrl::OnDrawBorder](../Topic/CMFCPropertyGridCtrl::OnDrawBorder.md)|Appelé par l'infrastructure pour dessiner une bordure autour d'un contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::OnDrawDescription](../Topic/CMFCPropertyGridCtrl::OnDrawDescription.md)|Appelé par l'infrastructure pour dessiner la zone de description et afficher le texte de description.|  
|[CMFCPropertyGridCtrl::OnDrawList](../Topic/CMFCPropertyGridCtrl::OnDrawList.md)|Appelé par l'infrastructure pour afficher la liste des propriétés dans le contrôle de grille des propriétés.|  
|[CMFCPropertyGridCtrl::OnDrawProperty](../Topic/CMFCPropertyGridCtrl::OnDrawProperty.md)|Appelé par l'infrastructure pour afficher une propriété.|  
|[CMFCPropertyGridCtrl::OnPropertyChanged](../Topic/CMFCPropertyGridCtrl::OnPropertyChanged.md)|Appelé par l'infrastructure lorsque la valeur d'une propriété est modifiée.|  
|[CMFCPropertyGridCtrl::OnSelectCombo](../Topic/CMFCPropertyGridCtrl::OnSelectCombo.md)|Appelé par l'infrastructure lorsqu'une propriété qui contient un contrôle zone de liste déroulante est sélectionnée.|  
|[CMFCPropertyGridCtrl::ValidateItemData](../Topic/CMFCPropertyGridCtrl::ValidateItemData.md)|Appelé par l'infrastructure pour valider les données de propriété.|  
  
## Notes  
 Les affichages de classe d' `CMFCPropertyGridCtrl` qu'un contrôle de grille des propriétés qui contient des propriétés modifiables a dérivés de la classe de [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md) .  Chaque propriété peut représenter un type et peut contenir des sous\-éléments.  Le contrôle de grille des propriétés prend en charge une zone redimensionnable au bas qui peut consulter la description d'une propriété sélectionnée.  
  
 Pour utiliser un contrôle de grille des propriétés, construisez un objet d' `CMFCPropertyGridCtrl` puis appelez la méthode de [CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md) .  Utilisez la méthode de [CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md) pour ajouter des propriétés à la liste.  
  
## Propriétés de sélection  
 Au lieu de représenter une valeur, un élément de propriété peut démarrer une boîte de dialogue qui permet à l'utilisateur de sélectionner une couleur, un fichier, ou une police.  
  
 Le tableau suivant répertorie quatre types de propriété de sélection :  
  
|Classe|Description|  
|------------|-----------------|  
|[CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)|Une propriété à usage général qui est utilisée pour spécifier la valeur des chaînes, valeur booléenne, dates et ainsi de suite.|  
|[CMFCPropertyGridColorProperty Class](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)|Une propriété utilisée pour sélectionner une valeur de couleur.|  
|[CMFCPropertyGridFileProperty Class](../../mfc/reference/cmfcpropertygridfileproperty-class.md)|Une propriété utilisée pour sélectionner un fichier.|  
|[CMFCPropertyGridFontProperty Class](../../mfc/reference/cmfcpropertygridfontproperty-class.md)|Une propriété utilisée pour sélectionner une police.|  
  
## Illustrations  
 Les illustrations suivantes représentent un contrôle de grille des propriétés qui affiche les propriétés de deux façons.  La première illustration affiche les propriétés de façon hiérarchique et la deuxième affiche les propriétés par ordre alphabétique.  
  
 ![Liste de propriétés &#45; PropertySheet](../../mfc/reference/media/proplist.png "PropList")  
  
## Exemple  
 L'exemple suivant montre comment configurer un objet contrôle de grille des propriétés en utilisant différentes méthodes dans la classe d' `CMFCPropertyGridCtrl` .  L'exemple montre comment activer le contrôle header, activer la zone de description, et définir l'apparence du contrôle de grille des propriétés.  L'exemple montre également comment définir le mode alphabétique pour le contrôle par lequel le contrôle trie toutes les propriétés qu'il contient par leur nom de la propriété, et comment définir des couleurs personnalisées pour des éléments du contrôle de grille des propriétés.  Cet exemple fait partie de [Nouvel exemples de contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#14](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#16](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls#20](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls#21](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_4.cpp)]  
[!code-cpp[NVC_MFC_NewControls#24](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_5.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)  
  
## Configuration requise  
 **en\-tête :** afxpropertygridctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)