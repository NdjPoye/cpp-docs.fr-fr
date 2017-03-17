---
title: Classe de CMFCRibbonUndoButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonUndoButton class
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
caps.latest.revision: 35
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
ms.openlocfilehash: d4406e21a7e2a945965020d85a748b93d66b5682
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton (classe)
La `CMFCRibbonUndoButton` classe implémente un bouton de liste déroulante qui contient les commandes utilisateur les plus récentes. Les utilisateurs peuvent sélectionner un ou plusieurs des dernières commandes dans la liste déroulante pour les annuler ou rétablir.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Construit un nouveau `CMFCRibbonUndoButton` à l’aide de l’ID de commande que vous spécifiez, étiquette de texte et les images à partir de la liste d’images de l’objet parent.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Ajoute une nouvelle action à la liste d’actions.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Efface la liste des actions, qui est la liste déroulante.|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Détermine le nombre d’éléments qu’un utilisateur a sélectionnés dans la liste déroulante.|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Indique si l’objet contienne un menu.|  
  
## <a name="remarks"></a>Remarques  
 La `CMFCRibbonUndoButton` classe utilise une pile pour représenter la liste déroulante.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un objet de la `CMFCRibbonUndoButton` classe et ajoutez une nouvelle action à la liste des actions. Cet extrait de code fait partie de la [exemples de Gadgets du ruban](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RibbonGadgets n °&2;](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxribbonundobutton.h  
  
##  <a name="addundoaction"></a>CMFCRibbonUndoButton::AddUndoAction  
 Ajoute une nouvelle action à la liste d’actions.  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszLabel`  
 L’étiquette d’action qui sera affiché dans la liste déroulante.  
  
##  <a name="cleanupundolist"></a>CMFCRibbonUndoButton::CleanUpUndoList  
 Efface la liste des actions, qui est la liste déroulante.  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="cmfcribbonundobutton"></a>CMFCRibbonUndoButton::CMFCRibbonUndoButton  
 Construit un nouveau `CMFCRibbonUndoButton` à l’aide de l’ID de commande que vous spécifiez, étiquette de texte et les images à partir de la liste d’images de l’objet parent.  
  
```  
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1);

 
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 Spécifie l’identificateur de commande.  
  
 [in] `lpszText`  
 Spécifie l’étiquette de texte du bouton.  
  
 [in] `nSmallImageIndex`  
 Index de base zéro dans la liste d’images de l’objet parent de l’image du bouton petit.  
  
 [in] `nLargeImageIndex`  
 Index de base zéro dans la liste d’images de l’objet parent pour le d’image de grande taille du bouton.  
  
 [in] `hIcon`  
 Un handle d’une icône que vous pouvez utiliser comme image d’un bouton.  
  
##  <a name="getactionnumber"></a>CMFCRibbonUndoButton::GetActionNumber  
 Détermine le nombre d’éléments qu’un utilisateur a sélectionnés dans la liste déroulante.  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments qu’un utilisateur sélectionnés.  
  
##  <a name="hasmenu"></a>CMFCRibbonUndoButton::HasMenu  
 Indique si l’objet contienne un menu.  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `TRUE`.  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery (classe)](../../mfc/reference/cmfcribbongallery-class.md)   
 [CMFCRibbonButton (classe)](../../mfc/reference/cmfcribbonbutton-class.md)

