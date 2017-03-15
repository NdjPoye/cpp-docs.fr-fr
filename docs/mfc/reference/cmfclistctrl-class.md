---
title: Classe de CMFCListCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCListCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCListCtrl class
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
caps.latest.revision: 29
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3a4c67b2d7ea2a5356f7c053403edf414319a928
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl (classe)
Le `CMFCListCtrl` classe étend les fonctionnalités de [CListCtrl (classe)](../../mfc/reference/clistctrl-class.md) classe prend en charge les fonctionnalités de contrôle d’en-tête avancées de la [CMFCHeaderCtrl classe](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Permet de marquer une colonne triée avec une couleur d’arrière-plan.|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Active le mode de tri multiples.|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Retourne une référence au contrôle header soulignée.|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Vérifie si le contrôle de liste est en mode de tri multiple.|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|Appelé par l’infrastructure lorsqu’elle doit comparer deux éléments de liste de contrôle.|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Appelé par l’infrastructure lorsqu’il doit déterminer la couleur d’arrière-plan d’une cellule.|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Appelé par l’infrastructure lorsqu’elle doit obtenir la police pour la cellule qui est dessinée.|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Appelé par l’infrastructure lorsqu’il doit déterminer la couleur du texte d’une cellule.|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Supprime une colonne de tri de la liste des colonnes triées.|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Définit la colonne triée actuelle et l’ordre de tri.|  
|[CMFCListCtrl::Sort](#sort)|Trie le contrôle de liste.|  
  
## <a name="remarks"></a>Remarques  
 `CMFCListCtrl`propose deux améliorations à [CListCtrl (classe)](../../mfc/reference/clistctrl-class.md) (classe). Tout d’abord, il indique que le tri de colonne est une option disponible en dessinant automatiquement une flèche de tri de l’en-tête. Deuxièmement, il prend en charge les données de tri sur plusieurs colonnes en même temps.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans la `CMFCListCtrl` classe. L’exemple montre comment créer un contrôle de liste, insérer des colonnes, insérer des éléments, définir le texte d’un élément et définir la police du contrôle de liste. Cet extrait de code fait partie de la [exemple de Visual Studio démonstration](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#25;](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#26;](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxlistctrl.h  
  
##  <a name="a-nameenablemarksortedcolumna--cmfclistctrlenablemarksortedcolumn"></a><a name="enablemarksortedcolumn"></a>CMFCListCtrl::EnableMarkSortedColumn  
 Marque les colonnes triées avec une couleur d’arrière-plan.  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bMark`  
 Un paramètre booléen qui détermine s’il faut activer une couleur d’arrière-plan.  
  
 [in] `bRedraw`  
 Un paramètre booléen qui détermine s’il faut redessiner le contrôle immédiatement.  
  
### <a name="remarks"></a>Notes  
 `EnableMarkSortedColumn`utilise la méthode `CDrawingManager::PixelAlpha` pour calculer quelle couleur pour utiliser pour triée colonnes. La couleur sélectionnée est basée sur la couleur d’arrière-plan normale.  
  
##  <a name="a-nameenablemultiplesorta--cmfclistctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFCListCtrl::EnableMultipleSort  
 Permet de trier les lignes de données dans le contrôle de liste en plusieurs colonnes.  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 Valeur booléenne qui spécifie s’il faut activer le mode de trier plusieurs colonnes.  
  
### <a name="remarks"></a>Remarques  
 Lorsque vous activez le tri en fonction de plusieurs colonnes, les colonnes ont une hiérarchie. Les lignes de données seront tout d’abord triés par la colonne principale. Les valeurs équivalentes sont triés en fonction de chaque colonne suivante selon la priorité.  
  
##  <a name="a-namegetheaderctrla--cmfclistctrlgetheaderctrl"></a><a name="getheaderctrl"></a>CMFCListCtrl::GetHeaderCtrl  
 Retourne une référence au contrôle header.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à l’objet sous-jacent [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Le contrôle header pour un contrôle de liste est la fenêtre qui contient les titres des colonnes. Il est généralement placé directement au-dessus des colonnes.  
  
##  <a name="a-nameismultiplesorta--cmfclistctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFCListCtrl::IsMultipleSort  
 Vérifie si le contrôle de liste prend actuellement en charge le tri sur plusieurs colonnes.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le contrôle de liste prend en charge le tri sur plusieurs ; `FALSE` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Lorsqu’un [CMFCListCtrl classe](../../mfc/reference/cmfclistctrl-class.md) prend en charge le tri multiples, l’utilisateur peut trier les données dans le contrôle de liste à plusieurs colonnes. Pour activer le tri de plusieurs, appelez [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).  
  
##  <a name="a-nameoncompareitemsa--cmfclistctrloncompareitems"></a><a name="oncompareitems"></a>CMFCListCtrl::OnCompareItems  
 L’infrastructure appelle cette méthode lorsqu’il compare deux éléments.  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lParam1`  
 Premier élément à comparer.  
  
 [in] `lParam2`  
 Deuxième élément à comparer.  
  
 [in] `iColumn`  
 Index de la colonne de tri de cette méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 Entier qui indique la position relative de deux éléments. Une valeur négative indique que le premier élément doit précéder la seconde, valeur positive indique que le premier élément doit suivre la seconde, et zéro signifie que les deux éléments sont équivalents.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut toujours retourne 0. Vous devez substituer cette fonction pour fournir un algorithme de tri.  
  
##  <a name="a-nameongetcellbkcolora--cmfclistctrlongetcellbkcolor"></a><a name="ongetcellbkcolor"></a>CMFCListCtrl::OnGetCellBkColor  
 L’infrastructure appelle cette méthode lorsqu’il doit déterminer la couleur d’arrière-plan d’une cellule.  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nRow`  
 La ligne de la cellule en question.  
  
 [in] `nColumn`  
 La colonne de la cellule en question.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `COLOREF` valeur qui spécifie la couleur d’arrière-plan de la cellule.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de `OnGetCellBkColor` n’utilise pas les paramètres d’entrée fournis et à la place simplement à appeler `GetBkColor`. Par conséquent, par défaut, le contrôle de liste a la même couleur d’arrière-plan. Vous pouvez remplacer `OnGetCellBkColor` dans une classe dérivée pour marquer des cellules avec une couleur d’arrière-plan.  
  
##  <a name="a-nameongetcellfonta--cmfclistctrlongetcellfont"></a><a name="ongetcellfont"></a>CMFCListCtrl::OnGetCellFont  
 L’infrastructure appelle cette méthode lorsqu’il obtient la police pour une cellule individuelle.  
  
```  
virtual HFONT OnGetCellFont(
    int nRow,  
    int nColumn,  
    DWORD dwData = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nRow`  
 La ligne de la cellule en question.  
  
 [in] `nColumn`  
 La colonne de la cellule en question.  
  
 [in] `dwData`  
 Données définies par l’utilisateur. L’implémentation par défaut n’utilise pas ce paramètre.  
  
### <a name="return-value"></a>Valeur de retour  
 Handle de la police utilisée pour la cellule active.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, cette méthode retourne `NULL`. Toutes les cellules dans un contrôle de liste ont la même police. Substituez cette méthode pour fournir des polices pour différentes cellules.  
  
##  <a name="a-nameongetcelltextcolora--cmfclistctrlongetcelltextcolor"></a><a name="ongetcelltextcolor"></a>CMFCListCtrl::OnGetCellTextColor  
 L’infrastructure appelle cette méthode lorsqu’il doit déterminer la couleur du texte d’une cellule.  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nRow`  
 La ligne de la cellule en question.  
  
 [in] `nColumn`  
 La colonne de la cellule en question.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `COLOREF` valeur qui spécifie la couleur du texte de la cellule.  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette méthode appelle `GetTextColor` indépendamment des paramètres d’entrée. Le contrôle de liste a la même couleur. Vous pouvez remplacer `OnGetCellTextColor` dans une classe dérivée pour marquer des cellules avec une couleur de texte.  
  
##  <a name="a-nameremovesortcolumna--cmfclistctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFCListCtrl::RemoveSortColumn  
 Supprime une colonne de tri de la liste des colonnes triées.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iColumn`  
 La colonne à supprimer.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode supprime une colonne de tri du contrôle d’en-tête. Il appelle [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).  
  
##  <a name="a-namesetsortcolumna--cmfclistctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFCListCtrl::SetSortColumn  
 Définit la colonne triée actuelle et l’ordre de tri.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iColumn`  
 La colonne à trier.  
  
 [in] `bAscending`  
 Valeur booléenne qui spécifie l’ordre de tri.  
  
 [in] `bAdd`  
 Valeur booléenne qui spécifie si la méthode ajoute la colonne indiquée par `iColumn` à la liste des colonnes de tri.  
  
### <a name="remarks"></a>Notes  
 Cette méthode passe les paramètres d’entrée au contrôle d’en-tête à l’aide de la méthode [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).  
  
##  <a name="a-namesorta--cmfclistctrlsort"></a><a name="sort"></a>CMFCListCtrl::Sort  
 Trie le contrôle de liste.  
  
```  
virtual void Sort(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iColumn`  
 La colonne à trier.  
  
 [in] `bAscending`  
 Valeur booléenne qui spécifie l’ordre de tri.  
  
 [in] `bAdd`  
 Valeur booléenne qui spécifie si cette méthode ajoute la colonne indiquée par `iColumn` à la liste des colonnes de tri.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CListCtrl (classe)](../../mfc/reference/clistctrl-class.md)

