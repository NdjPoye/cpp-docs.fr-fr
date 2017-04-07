---
title: Classe de CDragListBox | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
dev_langs:
- C++
helpviewer_keywords:
- drag list box [C++]
- dragging list items
- CDragListBox class
- Windows [C++], list boxes
- list boxes
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: 24
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 3010fd9a363aa1ca1c946a6fe967a7ba415649d4
ms.lasthandoff: 02/24/2017

---
# <a name="cdraglistbox-class"></a>CDragListBox (classe)
En plus des fonctionnalités d’une zone de liste Windows, la `CDragListBox` classe permet à l’utilisateur de déplacer des éléments de liste, tels que des noms de fichiers, dans la zone de liste.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDragListBox : public CListBox  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](#cdraglistbox)|Construit un objet `CDragListBox`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](#begindrag)|Appelé par l’infrastructure au démarrage d’une opération de glisser-déplacer.|  
|[CDragListBox::CancelDrag](#canceldrag)|Appelé par l’infrastructure lorsqu’une opération glisser a été annulée.|  
|[CDragListBox::Dragging](#dragging)|Appelé par l’infrastructure pendant une opération glisser.|  
|[CDragListBox::DrawInsert](#drawinsert)|Dessine le guide d’insertion de la zone de liste glisser.|  
|[CDragListBox::Dropped](#dropped)|Appelé par l’infrastructure après que l’élément a été supprimé.|  
|[CDragListBox::ItemFromPt](#itemfrompt)|Retourne les coordonnées de l’élément déplacé.|  
  
## <a name="remarks"></a>Remarques  
 Zones de liste avec cette fonctionnalité permettent aux utilisateurs de classer les éléments dans une liste de quelque manière plus utile pour eux. Par défaut, la zone de liste sera déplacer l’élément vers le nouvel emplacement dans la liste. Toutefois, `CDragListBox` objets peuvent être personnalisés pour copier des éléments au lieu de les déplacer.  
  
 Le contrôle de zone de liste associée le `CDragListBox` classe ne doit pas avoir la **LBS_SORT** ou **LBS_MULTIPLESELECT** style. Pour obtenir une description des styles de zone de liste, consultez [Styles de zone de liste](../../mfc/reference/list-box-styles.md).  
  
 Pour utiliser une zone de liste glisser dans une boîte de dialogue existante de votre application, ajoutez un contrôle de zone de liste à votre modèle de boîte de dialogue à l’aide de l’éditeur de boîtes de dialogue et puis affectez une variable membre (de la catégorie `Control` et le Type de Variable `CDragListBox`) correspondant à la zone de liste dans votre modèle de boîte de dialogue.  
  
 Pour plus d’informations sur l’affectation des contrôles à des variables de membre, consultez la page [raccourci pour la définition des Variables membres pour les contrôles de boîte de dialogue](../../windows/defining-member-variables-for-dialog-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="begindrag"></a>CDragListBox::BeginDrag  
 Appelée par l’infrastructure lorsque survient un événement qui pourrait commencer une opération glisser, telles que le bouton gauche de la souris.  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Paramètres  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet qui contient les coordonnées de l’élément déplacé.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le glissement est autorisée, sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction si vous souhaitez contrôler ce qui se passe lorsqu’une opération glisser commence. L’implémentation par défaut capture la souris et reste en mode glisser jusqu'à ce que l’utilisateur clique sur le bouton gauche ou droit de la souris ou appuie sur la touche ÉCHAP, moment auquel l’opération glisser est annulée.  
  
##  <a name="canceldrag"></a>CDragListBox::CancelDrag  
 Appelé par l’infrastructure lorsqu’une opération glisser a été annulée.  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Paramètres  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet qui contient les coordonnées de l’élément déplacé.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction pour traiter tout traitement spécial pour votre contrôle de zone de liste.  
  
##  <a name="cdraglistbox"></a>CDragListBox::CDragListBox  
 Construit un objet `CDragListBox`.  
  
```  
CDragListBox();
```  
  
##  <a name="dragging"></a>CDragListBox::Dragging  
 Appelé par l’infrastructure lorsqu’un élément de zone de liste est glissé dans les `CDragListBox` objet.  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>Paramètres  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet qui contient les coordonnées x et y de l’écran coordonnées du curseur.  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de ressource du curseur à afficher. Les valeurs suivantes sont possibles :  
  
- `DL_COPYCURSOR`Indique que l’élément sera copié.  
  
- `DL_MOVECURSOR`Indique que l’élément sera déplacé.  
  
- `DL_STOPCURSOR`Indique que la cible de déplacement actuelle n’est pas acceptable.  
  
### <a name="remarks"></a>Remarques  
 Le comportement par défaut retourne `DL_MOVECURSOR`. Remplacez cette fonction si vous souhaitez fournir des fonctionnalités supplémentaires.  
  
##  <a name="drawinsert"></a>CDragListBox::DrawInsert  
 Appelé par l’infrastructure pour dessiner le guide d’insertion avant l’élément avec l’index spécifié.  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `nItem`  
 Index de base zéro du point d’insertion.  
  
### <a name="remarks"></a>Remarques  
 Une valeur de - 1 efface le guide d’insertion. Remplacez cette fonction pour modifier l’apparence ou le comportement du guide d’insertion.  
  
##  <a name="dropped"></a>CDragListBox::Dropped  
 Appelé par l’infrastructure lorsqu’un élément est supprimé dans un `CDragListBox` objet.  
  
```  
virtual void Dropped(
    int nSrcIndex,  
    CPoint pt);
```  
  
### <a name="parameters"></a>Paramètres  
 *nSrcIndex*  
 Spécifie l’index de base zéro de la chaîne supprimée.  
  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet qui contient les coordonnées du site de dépôt.  
  
### <a name="remarks"></a>Remarques  
 Le comportement par défaut copie l’élément de zone de liste et ses données vers le nouvel emplacement, puis supprime l’élément d’origine. Remplacez cette fonction pour personnaliser le comportement par défaut, telles que l’activation des copies des éléments de zone de liste à faire glisser vers d’autres emplacements au sein de la liste.  
  
##  <a name="itemfrompt"></a>CDragListBox::ItemFromPt  
 Appel de cette fonction pour récupérer l’index de base zéro de l’élément de zone de liste située à `pt`.  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet contenant les coordonnées d’un point dans la zone de liste.  
  
 *bAutoScroll*  
 Différent de zéro si le défilement est autorisé, sinon 0.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément de zone de liste de glissement.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC TSTCON](../../visual-cpp-samples.md)   
 [CListBox (classe)](../../mfc/reference/clistbox-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CListBox (classe)](../../mfc/reference/clistbox-class.md)

