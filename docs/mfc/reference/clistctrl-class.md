---
title: "CListCtrl Class | Microsoft Docs"
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
  - "CListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListCtrl (classe)"
  - "list view controls"
  - "list view controls, CListCtrl (classe)"
  - "LVS_ICON"
  - "LVS_LIST"
  - "LVS_REPORT"
  - "LVS_SMALLICON"
  - "Windows common controls [C++], CListCtrl"
ms.assetid: fe08a1ca-4b05-4ff7-a12a-ee4c765a2197
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule les fonctionnalités d'un contrôle liste view « , » qui affiche une collection d'éléments chacune qui se compose d'une icône \(d'une liste d'images\) et d'une étiquette.  
  
## Syntaxe  
  
```  
class CListCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CListCtrl::CListCtrl](../Topic/CListCtrl::CListCtrl.md)|Construit un objet `CListCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CListCtrl::ApproximateViewRect](../Topic/CListCtrl::ApproximateViewRect.md)|Détermine la largeur et la hauteur requise pour afficher les éléments d'un contrôle liste view.|  
|[CListCtrl::Arrange](../Topic/CListCtrl::Arrange.md)|Aligne les éléments sur une grille.|  
|[CListCtrl::CancelEditLabel](../Topic/CListCtrl::CancelEditLabel.md)|Annule l'opération d'édition de texte de l'élément.|  
|[CListCtrl::Create](../Topic/CListCtrl::Create.md)|Crée un contrôle de liste et l'attache à un objet d' `CListCtrl` .|  
|[CListCtrl::CreateDragImage](../Topic/CListCtrl::CreateDragImage.md)|Crée une liste d'images pour faire glisser un élément spécifié.|  
|[CListCtrl::CreateEx](../Topic/CListCtrl::CreateEx.md)|Crée un contrôle de liste avec les styles étendus par windows spécifiées et l'attache à un objet d' `CListCtrl` .|  
|[CListCtrl::DeleteAllItems](../Topic/CListCtrl::DeleteAllItems.md)|Supprime tous les éléments du contrôle.|  
|[CListCtrl::DeleteColumn](../Topic/CListCtrl::DeleteColumn.md)|Supprime une colonne du contrôle liste view.|  
|[CListCtrl::DeleteItem](../Topic/CListCtrl::DeleteItem.md)|Supprime un élément du contrôle.|  
|[CListCtrl::DrawItem](../Topic/CListCtrl::DrawItem.md)|Appelé lorsqu'un aspect visuel s'aligne d'un contrôle owner draw.|  
|[CListCtrl::EditLabel](../Topic/CListCtrl::EditLabel.md)|Démarre la modification sur place du texte d'un élément.|  
|[CListCtrl::EnableGroupView](../Topic/CListCtrl::EnableGroupView.md)|Active ou désactive si les éléments dans une vue Liste affichage en tant que groupe.|  
|[CListCtrl::EnsureVisible](../Topic/CListCtrl::EnsureVisible.md)|Garantit qu'un élément est visible.|  
|[CListCtrl::FindItem](../Topic/CListCtrl::FindItem.md)|Recherche un élément de l'affichage de liste ayant spécifié des caractéristiques.|  
|[CListCtrl::GetBkColor](../Topic/CListCtrl::GetBkColor.md)|Extrait la couleur d'arrière\-plan d'un contrôle liste view.|  
|[CListCtrl::GetBkImage](../Topic/CListCtrl::GetBkImage.md)|Récupère l'image d'arrière\-plan actuelle d'un contrôle liste view.|  
|[CListCtrl::GetCallbackMask](../Topic/CListCtrl::GetCallbackMask.md)|Récupère le masque de rappel pour un contrôle liste view.|  
|[CListCtrl::GetCheck](../Topic/CListCtrl::GetCheck.md)|Extrait l'état actuel d'affichage de l'image d'état associée à un élément.|  
|[CListCtrl::GetColumn](../Topic/CListCtrl::GetColumn.md)|Récupère les attributs d'une colonne du contrôle.|  
|[CListCtrl::GetColumnOrderArray](../Topic/CListCtrl::GetColumnOrderArray.md)|Récupère l'ordre des colonnes \(de gauche à droite\) d'un contrôle liste view.|  
|[CListCtrl::GetColumnWidth](../Topic/CListCtrl::GetColumnWidth.md)|Extrait la largeur d'une colonne en mode Rapport ou la vue Liste.|  
|[CListCtrl::GetCountPerPage](../Topic/CListCtrl::GetCountPerPage.md)|Calcule le nombre d'éléments qui peuvent être intégrées verticalement dans un contrôle liste view.|  
|[CListCtrl::GetEditControl](../Topic/CListCtrl::GetEditControl.md)|Récupère le handle du contrôle d'édition utilisé pour modifier le texte d'un élément.|  
|[CListCtrl::GetEmptyText](../Topic/CListCtrl::GetEmptyText.md)|Extrait la chaîne à afficher si le contrôle liste view actuel est vide.|  
|[CListCtrl::GetExtendedStyle](../Topic/CListCtrl::GetExtendedStyle.md)|Récupère les styles étendus actuels d'un contrôle liste view.|  
|[CListCtrl::GetFirstSelectedItemPosition](../Topic/CListCtrl::GetFirstSelectedItemPosition.md)|Extrait la position du premier élément de l'affichage de liste sélectionné dans un contrôle liste view.|  
|[CListCtrl::GetFocusedGroup](../Topic/CListCtrl::GetFocusedGroup.md)|Récupère le groupe qui a le focus clavier dans le contrôle liste view actuel.|  
|[CListCtrl::GetGroupCount](../Topic/CListCtrl::GetGroupCount.md)|Récupère le nombre de groupes dans le contrôle liste view actuel.|  
|[CListCtrl::GetGroupInfo](../Topic/CListCtrl::GetGroupInfo.md)|Obtient les informations relatives à un groupe spécifié du contrôle liste view.|  
|[CListCtrl::GetGroupInfoByIndex](../Topic/CListCtrl::GetGroupInfoByIndex.md)|Récupère des informations sur un groupe spécifié dans le contrôle liste view actuel.|  
|[CListCtrl::GetGroupMetrics](../Topic/CListCtrl::GetGroupMetrics.md)|Extrait la métrique d'un groupe.|  
|[CListCtrl::GetGroupRect](../Topic/CListCtrl::GetGroupRect.md)|Récupère le rectangle englobant d'un groupe spécifié dans le contrôle liste view actuel.|  
|[CListCtrl::GetGroupState](../Topic/CListCtrl::GetGroupState.md)|Récupère l'état d'un groupe spécifié dans le contrôle liste view actuel.|  
|[CListCtrl::GetHeaderCtrl](../Topic/CListCtrl::GetHeaderCtrl.md)|Récupère le contrôle header d'un contrôle liste view.|  
|[CListCtrl::GetHotCursor](../Topic/CListCtrl::GetHotCursor.md)|Récupère le curseur utilisé lorsque la sélection réactive est activée pour un contrôle liste view.|  
|[CListCtrl::GetHotItem](../Topic/CListCtrl::GetHotItem.md)|Récupère l'élément de l'affichage de liste actuelle sous le curseur.|  
|[CListCtrl::GetHoverTime](../Topic/CListCtrl::GetHoverTime.md)|Extrait l'heure actuelle de pointage d'un contrôle liste view.|  
|[CListCtrl::GetImageList](../Topic/CListCtrl::GetImageList.md)|Récupère le handle d'une liste d'images utilisée pour dessiner des éléments de l'affichage de liste.|  
|[CListCtrl::GetInsertMark](../Topic/CListCtrl::GetInsertMark.md)|Extrait la position actuelle de la marque d'insertion.|  
|[CListCtrl::GetInsertMarkColor](../Topic/CListCtrl::GetInsertMarkColor.md)|Extrait la couleur actuelle de la marque d'insertion.|  
|[CListCtrl::GetInsertMarkRect](../Topic/CListCtrl::GetInsertMarkRect.md)|Récupère le rectangle limites que le point d'insertion.|  
|[CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md)|Récupère les attributs d'un élément de l'affichage de liste.|  
|[CListCtrl::GetItemCount](../Topic/CListCtrl::GetItemCount.md)|Récupère le nombre d'éléments dans un contrôle liste view.|  
|[CListCtrl::GetItemData](../Topic/CListCtrl::GetItemData.md)|Extrait la valeur spécifique à l'application associée à un élément.|  
|[CListCtrl::GetItemIndexRect](../Topic/CListCtrl::GetItemIndexRect.md)|Récupère le rectangle englobant de l'ensemble ou une partie d'un sous\-élément dans le contrôle liste view actuel.|  
|[CListCtrl::GetItemPosition](../Topic/CListCtrl::GetItemPosition.md)|Extrait la position d'un élément de l'affichage de liste.|  
|[CListCtrl::GetItemRect](../Topic/CListCtrl::GetItemRect.md)|Récupère le rectangle englobant d'un élément.|  
|[CListCtrl::GetItemSpacing](../Topic/CListCtrl::GetItemSpacing.md)|Calcule l'espacement entre les éléments du contrôle liste view actuel.|  
|[CListCtrl::GetItemState](../Topic/CListCtrl::GetItemState.md)|Récupère l'état d'un élément de l'affichage de liste.|  
|[CListCtrl::GetItemText](../Topic/CListCtrl::GetItemText.md)|Extrait le texte d'un élément de l'affichage de liste ou d'un sous\-élément.|  
|[CListCtrl::GetNextItem](../Topic/CListCtrl::GetNextItem.md)|Recherche un élément de l'affichage de liste avec les propriétés spécifiées et avec la relation spécifiée à un élément donné.|  
|[CListCtrl::GetNextItemIndex](../Topic/CListCtrl::GetNextItemIndex.md)|Extrait l'index de l'élément du contrôle liste view actuel qui a un jeu spécifié de propriétés.|  
|[CListCtrl::GetNextSelectedItem](../Topic/CListCtrl::GetNextSelectedItem.md)|Récupère l'index d'une position d'élément de l'affichage de liste, et la position de l'élément de l'affichage de liste sélectionné pour itérer.|  
|[CListCtrl::GetNumberOfWorkAreas](../Topic/CListCtrl::GetNumberOfWorkAreas.md)|Récupère le nombre actuel d'emplacements de travail pour un contrôle liste view.|  
|[CListCtrl::GetOrigin](../Topic/CListCtrl::GetOrigin.md)|Récupère l'origine de l'affichage actuel pour un contrôle liste view.|  
|[CListCtrl::GetOutlineColor](../Topic/CListCtrl::GetOutlineColor.md)|Extrait la couleur de la bordure d'un contrôle liste view.|  
|[CListCtrl::GetSelectedColumn](../Topic/CListCtrl::GetSelectedColumn.md)|Extrait l'index de la colonne sélectionnée dans le contrôle de liste.|  
|[CListCtrl::GetSelectedCount](../Topic/CListCtrl::GetSelectedCount.md)|Récupère le nombre d'éléments sélectionnés dans le contrôle liste view.|  
|[CListCtrl::GetSelectionMark](../Topic/CListCtrl::GetSelectionMark.md)|Récupère le jeton de sélection d'un contrôle liste view.|  
|[CListCtrl::GetStringWidth](../Topic/CListCtrl::GetStringWidth.md)|Détermine la largeur de colonne minimale requise pour afficher toute la chaîne donnée.|  
|[CListCtrl::GetSubItemRect](../Topic/CListCtrl::GetSubItemRect.md)|Récupère le rectangle englobant d'un élément dans un contrôle liste view.|  
|[CListCtrl::GetTextBkColor](../Topic/CListCtrl::GetTextBkColor.md)|Extrait la couleur d'arrière\-plan du texte d'un contrôle liste view.|  
|[CListCtrl::GetTextColor](../Topic/CListCtrl::GetTextColor.md)|Extrait la couleur du texte d'un contrôle liste view.|  
|[CListCtrl::GetTileInfo](../Topic/CListCtrl::GetTileInfo.md)|Récupère des informations sur une mosaïque dans un contrôle liste view.|  
|[CListCtrl::GetTileViewInfo](../Topic/CListCtrl::GetTileViewInfo.md)|Récupère des informations sur un contrôle liste view dans l'affichage en mosaïque.|  
|[CListCtrl::GetToolTips](../Topic/CListCtrl::GetToolTips.md)|Récupère le contrôle d'info\-bulle que le contrôle liste view utilise pour afficher des info\-bulles.|  
|[CListCtrl::GetTopIndex](../Topic/CListCtrl::GetTopIndex.md)|Extrait l'index de l'élément visible le plus élevé.|  
|[CListCtrl::GetView](../Topic/CListCtrl::GetView.md)|Obtient la vue du contrôle liste view.|  
|[CListCtrl::GetViewRect](../Topic/CListCtrl::GetViewRect.md)|Récupère le rectangle englobant de tous les éléments du contrôle liste view.|  
|[CListCtrl::GetWorkAreas](../Topic/CListCtrl::GetWorkAreas.md)|Récupère les emplacements de travail actuels d'un contrôle liste view.|  
|[CListCtrl::HasGroup](../Topic/CListCtrl::HasGroup.md)|Détermine si le contrôle liste view a le groupe spécifié.|  
|[CListCtrl::HitTest](../Topic/CListCtrl::HitTest.md)|Détermine quel élément de l'affichage de liste est à une position spécifiée.|  
|[CListCtrl::InsertColumn](../Topic/CListCtrl::InsertColumn.md)|Insère une nouvelle colonne dans un contrôle liste view.|  
|[CListCtrl::InsertGroup](../Topic/CListCtrl::InsertGroup.md)|Insère un groupe dans le contrôle liste view.|  
|[CListCtrl::InsertGroupSorted](../Topic/CListCtrl::InsertGroupSorted.md)|Insère le groupe spécifié dans une liste triée de groupes.|  
|[CListCtrl::InsertItem](../Topic/CListCtrl::InsertItem.md)|Insère un nouvel élément dans un contrôle liste view.|  
|[CListCtrl::InsertMarkHitTest](../Topic/CListCtrl::InsertMarkHitTest.md)|Récupère le point d'insertion le plus proche d'un point spécifié.|  
|[CListCtrl::IsGroupViewEnabled](../Topic/CListCtrl::IsGroupViewEnabled.md)|Détermine si la vue de groupe est activée pour un contrôle liste view.|  
|[CListCtrl::IsItemVisible](../Topic/CListCtrl::IsItemVisible.md)|Indique si un élément spécifié dans le contrôle liste view actuellement visible.|  
|[CListCtrl::MapIDToIndex](../Topic/CListCtrl::MapIDToIndex.md)|Mappe l'identificateur unique d'un élément du contrôle liste view actuel à un index.|  
|[CListCtrl::MapIndexToID](../Topic/CListCtrl::MapIndexToID.md)|Mappe l'index d'un élément du contrôle liste view actuel à un ID|  
|[CListCtrl::MoveGroup](../Topic/CListCtrl::MoveGroup.md)|Déplace le groupe spécifié.|  
|[CListCtrl::MoveItemToGroup](../Topic/CListCtrl::MoveItemToGroup.md)|Déplace le groupe spécifié à l'index spécifié de base zéro du contrôle liste view.|  
|[CListCtrl::RedrawItems](../Topic/CListCtrl::RedrawItems.md)|Force un contrôle liste view pour redessiner une plage d'éléments.|  
|[CListCtrl::RemoveAllGroups](../Topic/CListCtrl::RemoveAllGroups.md)|Supprime tous les groupes d'un contrôle liste view.|  
|[CListCtrl::RemoveGroup](../Topic/CListCtrl::RemoveGroup.md)|Supprime le groupe spécifié du contrôle liste view.|  
|[CListCtrl::Scroll](../Topic/CListCtrl::Scroll.md)|Fait défiler le contenu d'un contrôle liste view.|  
|[CListCtrl::SetBkColor](../Topic/CListCtrl::SetBkColor.md)|Définit la couleur d'arrière\-plan du contrôle liste view.|  
|[CListCtrl::SetBkImage](../Topic/CListCtrl::SetBkImage.md)|Définit l'image d'arrière\-plan actuelle d'un contrôle liste view.|  
|[CListCtrl::SetCallbackMask](../Topic/CListCtrl::SetCallbackMask.md)|Définit le masque de rappel pour un contrôle liste view.|  
|[CListCtrl::SetCheck](../Topic/CListCtrl::SetCheck.md)|Définit l'état actuel d'affichage de l'image d'état associée à un élément.|  
|[CListCtrl::SetColumn](../Topic/CListCtrl::SetColumn.md)|Définit les attributs d'une colonne de vue Liste.|  
|[CListCtrl::SetColumnOrderArray](../Topic/CListCtrl::SetColumnOrderArray.md)|Définit l'ordre des colonnes \(de gauche à droite\) d'un contrôle liste view.|  
|[CListCtrl::SetColumnWidth](../Topic/CListCtrl::SetColumnWidth.md)|Modifie la largeur d'une colonne en mode Rapport ou la vue Liste.|  
|[CListCtrl::SetExtendedStyle](../Topic/CListCtrl::SetExtendedStyle.md)|Définit les styles étendus actuels d'un contrôle liste view.|  
|[CListCtrl::SetGroupInfo](../Topic/CListCtrl::SetGroupInfo.md)|Définit les informations du groupe spécifié d'un contrôle liste view.|  
|[CListCtrl::SetGroupMetrics](../Topic/CListCtrl::SetGroupMetrics.md)|Définit la métrique du groupe d'un contrôle liste view.|  
|[CListCtrl::SetHotCursor](../Topic/CListCtrl::SetHotCursor.md)|Place le curseur utilisé lorsque la sélection réactive est activée pour un contrôle liste view.|  
|[CListCtrl::SetHotItem](../Topic/CListCtrl::SetHotItem.md)|Définit l'élément réactif actuel d'un contrôle liste view.|  
|[CListCtrl::SetHoverTime](../Topic/CListCtrl::SetHoverTime.md)|Définit l'heure actuelle de pointage d'un contrôle liste view.|  
|[CListCtrl::SetIconSpacing](../Topic/CListCtrl::SetIconSpacing.md)|Définit l'espacement entre les icônes dans un contrôle liste view.|  
|[CListCtrl::SetImageList](../Topic/CListCtrl::SetImageList.md)|Assigne une liste d'images à un contrôle liste view.|  
|[CListCtrl::SetInfoTip](../Topic/CListCtrl::SetInfoTip.md)|Définit le texte d'info\-bulle.|  
|[CListCtrl::SetInsertMark](../Topic/CListCtrl::SetInsertMark.md)|Définit le point d'insertion à la position définie.|  
|[CListCtrl::SetInsertMarkColor](../Topic/CListCtrl::SetInsertMarkColor.md)|Définit la couleur du point d'insertion.|  
|[CListCtrl::SetItem](../Topic/CListCtrl::SetItem.md)|Définit une partie ou l'ensemble des attributs d'un élément de l'affichage de liste.|  
|[CListCtrl::SetItemCount](../Topic/CListCtrl::SetItemCount.md)|Prépare un contrôle liste view pour ajouter un grand nombre d'éléments.|  
|[CListCtrl::SetItemCountEx](../Topic/CListCtrl::SetItemCountEx.md)|Définit le nombre d'éléments pour un contrôle liste view virtuel.|  
|[CListCtrl::SetItemData](../Topic/CListCtrl::SetItemData.md)|Définit la valeur spécifique à l'application de l'élément.|  
|[CListCtrl::SetItemIndexState](../Topic/CListCtrl::SetItemIndexState.md)|Définit l'état d'un élément du contrôle liste view actuel.|  
|[CListCtrl::SetItemPosition](../Topic/CListCtrl::SetItemPosition.md)|Déplace un élément à une position spécifiée dans un contrôle liste view.|  
|[CListCtrl::SetItemState](../Topic/CListCtrl::SetItemState.md)|Change l'état d'un élément dans un contrôle liste view.|  
|[CListCtrl::SetItemText](../Topic/CListCtrl::SetItemText.md)|Modifie le texte d'un élément de l'affichage de liste ou d'un sous\-élément.|  
|[CListCtrl::SetOutlineColor](../Topic/CListCtrl::SetOutlineColor.md)|Définit la couleur de la bordure d'un contrôle liste view.|  
|[CListCtrl::SetSelectedColumn](../Topic/CListCtrl::SetSelectedColumn.md)|Définit la colonne sélectionnée du contrôle liste view.|  
|[CListCtrl::SetSelectionMark](../Topic/CListCtrl::SetSelectionMark.md)|Définit le jeton de sélection d'un contrôle liste view.|  
|[CListCtrl::SetTextBkColor](../Topic/CListCtrl::SetTextBkColor.md)|Définit la couleur d'arrière\-plan du texte dans un contrôle liste view.|  
|[CListCtrl::SetTextColor](../Topic/CListCtrl::SetTextColor.md)|Définit la couleur du texte d'un contrôle liste view.|  
|[CListCtrl::SetTileInfo](../Topic/CListCtrl::SetTileInfo.md)|Définit les informations pour une mosaïque du contrôle liste view.|  
|[CListCtrl::SetTileViewInfo](../Topic/CListCtrl::SetTileViewInfo.md)|Définit les informations qu'un contrôle liste view utilise dans l'affichage en mosaïque.|  
|[CListCtrl::SetToolTips](../Topic/CListCtrl::SetToolTips.md)|Définit le contrôle d'info\-bulle que le contrôle liste view utilisera pour afficher des info\-bulles.|  
|[CListCtrl::SetView](../Topic/CListCtrl::SetView.md)|Définit la vue du contrôle liste view.|  
|[CListCtrl::SetWorkAreas](../Topic/CListCtrl::SetWorkAreas.md)|Définit la zone où les icônes peuvent être affichées dans un contrôle liste view.|  
|[CListCtrl::SortGroups](../Topic/CListCtrl::SortGroups.md)|Trie les groupes d'un contrôle liste view avec une fonction définie par l'utilisateur.|  
|[CListCtrl::SortItems](../Topic/CListCtrl::SortItems.md)|Trie les éléments d'affichage de liste à l'aide d'une fonction de comparaison définie par l'application.|  
|[CListCtrl::SortItemsEx](../Topic/CListCtrl::SortItemsEx.md)|Trie les éléments d'affichage de liste à l'aide d'une fonction de comparaison définie par l'application.|  
|[CListCtrl::SubItemHitTest](../Topic/CListCtrl::SubItemHitTest.md)|Détermine que l'élément de l'affichage de liste, le cas échéant, est à une position donnée.|  
|[CListCtrl::Update](../Topic/CListCtrl::Update.md)|Force le contrôle pour redessiner un élément spécifié.|  
  
## Notes  
 En plus d'une icône et une étiquette, chaque élément peut contenir les informations affichées dans les colonnes à droite de l'icône et de l'étiquette.  Ce contrôle \(et par conséquent la classe d' `CListCtrl` \) est disponible uniquement aux programmes s'exécutant sous la version 3,51 de Windows 95\/98 et Windows NT et versions ultérieures.  
  
 Voici une vue d'ensemble de la classe d' `CListCtrl` .  Pour une description détaillée et conceptuelle, consultez [Utilisation CListCtrl](../../mfc/using-clistctrl.md) et le [contrôles](../../mfc/controls-mfc.md).  
  
## Vues  
 Les contrôles liste view peuvent afficher leur contenu de quatre manières différentes, appelées « vues. »  
  
-   Vue icône  
  
     Chaque élément apparaît en pixels de l'icône de taille normale \(32 x 32\) avec une étiquette au\-dessous de lui.  L'utilisateur peut faire glisser les éléments à tout emplacement dans la fenêtre vue Liste.  
  
-   Vue de petite icône  
  
     Chaque élément apparaît en pixels de la petite icône \(16 x 16\) avec l'étiquette située à droite de lui.  L'utilisateur peut faire glisser les éléments à tout emplacement dans la fenêtre vue Liste.  
  
-   Vue Liste  
  
     Chaque élément apparaît comme une petite icône à une étiquette à droite de lui.  Les éléments sont disposés dans les colonnes et ne peuvent pas être glissés vers n'importe où dans la fenêtre vue Liste.  
  
-   Mode Rapport  
  
     Chaque élément apparaît sur sa propre ligne, avec les informations supplémentaires réorganisées dans les colonnes à droite.  La colonne la plus à gauche contient la petite icône et l'étiquette, et les colonnes suivantes contiennent des sous\-éléments comme spécifié par l'application.  Un contrôle header incorporés \(classe\) [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)implémente ces colonnes.  Pour plus d'informations sur le contrôle header et les colonnes dans un mode Rapport, consultez l' [Utilisation CListCtrl : Ajout de colonnes au contrôle \(mode Rapport\)](../../mfc/adding-columns-to-the-control-report-view.md).  
  
 Voir aussi :  
  
-   Article de la Base de connaissances Q250614 : HOWTO : Éléments de tri dans un CListCtrl en mode Rapport  
  
-   Article de la Base de connaissances Q200054 : PRB : OnTimer\(\) n'est pas appelée à plusieurs reprises pour un contrôle de liste  
  
 Le style de la vue Liste actuelle du contrôle détermine l'affichage actuel.  Pour plus d'informations sur ces styles et leur utilisation, consultez l' [Utilisation CListCtrl : Modification des styles de contrôle liste](../../mfc/changing-list-control-styles.md).  
  
## Styles étendus  
 Outre les styles standard de liste, classez `CListCtrl` prend en charge un grand ensemble de styles étendus, en fournissant les fonctionnalités enrichie.  Quelques exemples de ces fonctionnalités incluent :  
  
-   Sélection de pointage  
  
     Une fois activé, autorise la sélection automatique d'un élément lorsque le curseur reste sur l'élément pendant un certain temps.  
  
-   Vues Liste virtuelles  
  
     Une fois activé, permet au contrôle prenne en charge jusqu'à `DWORD` des éléments.  Ceci est possible en définissant la charge mémoire de gérer des données d'élément dans l'application.  À l'exception de la sélection d'élément et de focus, toutes les informations d'élément doivent être gérées par l'application.  Pour plus d'informations, consultez l' [Utilisation CListCtrl : contrôles de liste virtuels](../../mfc/virtual-list-controls.md).  
  
-   Activation d'un et deux clics  
  
     Une fois activé, autorise la sélection réactive \(mettre en surbrillance automatique du texte de l'élément\) et le lancement d'un ou deux clics de l'élément en surbrillance.  
  
-   Le classement de la colonne de glisser\-déplacer  
  
     Une fois activé, permet de réorganiser glisser\-déplacer des colonnes dans un contrôle liste view.  Disponible uniquement en mode Rapport.  
  
 Pour plus d'informations sur l'utilisation de ces nouveaux styles étendus, consultez l' [Utilisation CListCtrl : Modification des styles de contrôle liste](../../mfc/changing-list-control-styles.md).  
  
## Éléments et sous\-éléments  
 Chaque élément dans un contrôle liste view se compose d'une icône \(d'une liste d'images\), d'une étiquette, d'un état actuel, et une valeur définie par l'application \(appelée sous le nom de « données d'élément »\).  Un ou plusieurs des sous\-éléments peuvent également être associés à chaque élément.  Un « sous\-élément » est une chaîne qui, en mode Rapport, peut être affichée dans une colonne à droite de l'icône et de l'étiquette d'un élément.  Tous les éléments dans un contrôle liste view doivent avoir le même nombre de sous\-éléments.  
  
 La classe **CListCtrl** fournit plusieurs fonctions pour insérer, supprimer, rechercher, et modifier ces éléments.  Pour plus d'informations, consultez [CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md), [CListCtrl::InsertItem](../Topic/CListCtrl::InsertItem.md), et [CListCtrl::FindItem](../Topic/CListCtrl::FindItem.md), [Utilisation CListCtrl : ajouter des éléments au contrôle](../../mfc/adding-items-to-the-control.md), et [Utilisation CListCtrl : Défilement, réorganiser, trier, et rechercher dans les contrôles de liste](../../mfc/scrolling-arranging-sorting-and-finding-in-list-controls.md).  
  
 Par défaut, le contrôle liste view est chargé d'enregistrer l'icône et les attributs du texte d'un élément.  Toutefois, en plus de ces types d'éléments, la classe `CListCtrl` « prend en charge les éléments de rappel. » « Un élément de rappel » est un élément de l'affichage de liste pour lequel l'application \(plutôt que le contrôle — les magasins le texte, l'icône, ou les deux.  Un masque de rappel est utilisé pour spécifier les attributs de l'élément \(texte et\/ou icône\) sont fournies par l'application.  Si une application utilise des éléments de rappel, il doit pouvoir fournir du texte et\/ou l'icône l'attribut à la demande.  Les éléments de rappel sont utiles lorsque votre application met à jour déjà certaines de ces informations.  Pour plus d'informations, consultez l' [Utilisation CListCtrl : éléments de rappel et le masque de rappel](../../mfc/callback-items-and-the-callback-mask.md).  
  
## Listes d'images  
 Les icônes, les images d'élément d'en\-tête, et les rapports définis par l'application pour les éléments de l'affichage de liste sont contenus dans plusieurs listes d'images \(implémentées par la classe [CImageList](../../mfc/reference/cimagelist-class.md)\), que vous créez et assignez au contrôle liste view.  Chaque contrôle liste view peut contenir jusqu'à quatre types de listes d'images :  
  
-   Grande icône  
  
     Utilisé dans la vue icône pour les icônes de taille normale.  
  
-   Petite icône  
  
     Utilisé dans la petite icône, la liste, et les vues de Rapport pour les petites versions des icônes utilisées dans la vue icône.  
  
-   État défini par l'application  
  
     Contient les images d'état, qui sont affichées en regard de l'icône d'un élément pour indiquer un état défini par l'application.  
  
-   Header Item  
  
     Utilisé en mode Rapport pour les petites icônes qui apparaissent dans chaque élément de contrôle header.  
  
 Par défaut, un contrôle liste view détruit les listes d'images assignées à lui lorsqu'il est détruit ; toutefois, le développeur peut personnaliser ce comportement en détruisant chaque liste d'images lorsqu'il n'est plus utilisé, tel que déterminé par l'application.  Pour plus d'informations, consultez l' [Utilisation CListCtrl : éléments de liste et listes d'images](../../mfc/list-items-and-image-lists.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [exemple MFC ROWLIST](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CImageList Class](../../mfc/reference/cimagelist-class.md)