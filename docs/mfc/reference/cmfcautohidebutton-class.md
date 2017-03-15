---
title: Classe de CMFCAutoHideButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAutoHideButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideButton class
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
caps.latest.revision: 33
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
ms.openlocfilehash: f25072b4362b6add1682ce50fc5ee21cc065637a
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton (classe)
Un bouton qui affiche ou masque un [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) qui est configurée pour être masquée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCAutoHideButton : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCAutoHideButton::BringToTop](#bringtotop)||  
|[CMFCAutoHideButton::Create](#create)|Crée et initialise les bouton masquer automatiquement.|  
|[CMFCAutoHideButton::GetAlignment](#getalignment)|Récupère l'alignement du bouton masquer automatiquement.|  
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|Retourne le [CDockablePane](../../mfc/reference/cdockablepane-class.md) objet associé avec le bouton Masquer automatiquement.|  
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||  
|[CMFCAutoHideButton::GetRect](#getrect)||  
|[CMFCAutoHideButton::GetSize](#getsize)|Détermine la taille du bouton masquer automatiquement.|  
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|Retourne la taille de l'étiquette de texte du bouton masquer automatiquement.|  
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|Met en évidence le bouton masquer automatiquement.|  
|[CMFCAutoHideButton::IsActive](#isactive)|Indique si le bouton masquer automatiquement est actif.|  
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|Fait état de la mise en évidence du bouton masquer automatiquement.|  
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|Détermine si le bouton masquer automatiquement est horizontal ou vertical.|  
|[CMFCAutoHideButton::IsTop](#istop)||  
|[CMFCAutoHideButton::IsVisible](#isvisible)|Indique si le bouton est visible.|  
|[CMFCAutoHideButton::Move](#move)||  
|[CMFCAutoHideButton::OnDraw](#ondraw)|L'infrastructure appelle cette méthode au moment de dessiner le bouton masquer automatiquement.|  
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|L'infrastructure appelle cette méthode au moment de dessiner la bordure d'un bouton masquer automatiquement.|  
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|L'infrastructure appelle cette méthode au moment de remplir l'arrière-plan d'un bouton masquer automatiquement.|  
|[CMFCAutoHideButton::ReplacePane](#replacepane)||  
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|Affiche ou masque associé [CDockablePane Class](../../mfc/reference/cdockablepane-class.md).|  
|[CMFCAutoHideButton::ShowButton](#showbutton)|Affiche ou masque le bouton masquer automatiquement.|  
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||  
  
## <a name="remarks"></a>Remarques  
 Lors de la création, la `CMFCAutoHideButton` objet est attaché à un [CDockablePane Class](../../mfc/reference/cdockablepane-class.md). L'objet `CDockablePane` est masqué ou affiché quand l'utilisateur interagit avec l'objet `CMFCAutoHideButton`.  
  
 Par défaut, l'infrastructure crée automatiquement un `CMFCAutoHideButton` quand l'utilisateur active le bouton masquer automatiquement. L'infrastructure peut créer un élément d'une classe d'interface utilisateur personnalisée à la place de la classe `CMFCAutoHideButton`. Pour spécifier la classe d'interface utilisateur personnalisée que l'infrastructure doit utiliser, attribuez à la variable de membre statique `CMFCAutoHideBar::m_pAutoHideButtonRTS` la même valeur que la classe d'interface utilisateur personnalisée. Par défaut, cette variable a la valeur `CMFCAutoHideButton`.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment construire un objet `CMFCAutoHideButton` et utiliser différentes méthodes de la classe `CMFCAutoHideButton`. L'exemple montre comment initialiser un objet `CMFCAutoHideButton` en utilisant sa méthode `Create`, afficher la classe `CDockablePane` associée et afficher le bouton masquer automatiquement.  
  
 [!code-cpp[NVC_MFC_RibbonApp n°&32;](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAutoHideButton`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxautohidebutton.h  
  
##  <a name="a-namebringtotopa--cmfcautohidebuttonbringtotop"></a><a name="bringtotop"></a>CMFCAutoHideButton::BringToTop  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void BringToTop();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecreatea--cmfcautohidebuttoncreate"></a><a name="create"></a>CMFCAutoHideButton::Create  
 Crée et initialise un bouton Masquer automatiquement.  
  
```  
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,  
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pParentBar`  
 Pointeur vers la barre d’outils parent.  
  
 [in] `pAutoHideWnd`  
 Un pointeur vers un [CDockablePane](../../mfc/reference/cdockablepane-class.md) objet. Ce bouton Masquer masque et montre que `CDockablePane`.  
  
 [in] `dwAlignment`  
 Une valeur qui spécifie l’alignement du bouton avec la fenêtre frame principale.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Lorsque vous créez un `CMFCAutoHideButton` de l’objet, vous devez associer le bouton Masquer automatiquement son propre `CDockablePane`. L’utilisateur peut utiliser le bouton Masquer pour masquer et afficher les `CDockablePane`.  
  
 Le paramètre `dwAlignment` indique l’emplacement du bouton Masquer automatiquement dans l’application. Le paramètre peut avoir l’une des valeurs suivantes :  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="a-namegetalignmenta--cmfcautohidebuttongetalignment"></a><a name="getalignment"></a>CMFCAutoHideButton::GetAlignment  
 Récupère l'alignement du bouton masquer automatiquement.  
  
```  
DWORD GetAlignment() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `DWORD` valeur contenant l’alignement actuel du bouton Masquer automatiquement.  
  
### <a name="remarks"></a>Remarques  
 L’alignement du bouton Masquer indique où se trouve le bouton sur l’application. Il peut être l’une des valeurs suivantes :  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CRBS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="a-namegetautohidewindowa--cmfcautohidebuttongetautohidewindow"></a><a name="getautohidewindow"></a>CMFCAutoHideButton::GetAutoHideWindow  
 Retourne le [CDockablePane](../../mfc/reference/cdockablepane-class.md) objet associé avec le bouton Masquer automatiquement.  
  
```  
CDockablePane* GetAutoHideWindow() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le texte associé `CDockablePane` objet.  
  
### <a name="remarks"></a>Notes  
 Pour associer un bouton Masquer automatiquement avec un `CDockablePane`, passez le `CDockablePane` en tant que paramètre à la [CMFCAutoHideButton::Create](#create) (méthode).  
  
##  <a name="a-namegetparenttoolbara--cmfcautohidebuttongetparenttoolbar"></a><a name="getparenttoolbar"></a>CMFCAutoHideButton::GetParentToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCAutoHideBar* GetParentToolBar();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetrecta--cmfcautohidebuttongetrect"></a><a name="getrect"></a>CMFCAutoHideButton::GetRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetsizea--cmfcautohidebuttongetsize"></a><a name="getsize"></a>CMFCAutoHideButton::GetSize  
 Détermine la taille du bouton masquer automatiquement.  
  
```  
CSize GetSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CSize` objet qui contient la taille du bouton.  
  
### <a name="remarks"></a>Remarques  
 La taille calculée inclut la taille de la bordure du bouton Masquer automatiquement.  
  
##  <a name="a-namegettextsizea--cmfcautohidebuttongettextsize"></a><a name="gettextsize"></a>CMFCAutoHideButton::GetTextSize  
 Retourne la taille de l'étiquette de texte du bouton masquer automatiquement.  
  
```  
virtual CSize GetTextSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) objet qui contient la taille du texte pour le bouton Masquer automatiquement.  
  
##  <a name="a-nameisactivea--cmfcautohidebuttonisactive"></a><a name="isactive"></a>CMFCAutoHideButton::IsActive  
 Indique si le bouton masquer automatiquement est actif.  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le bouton Masquer automatiquement est actif ; `FALSE` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Un bouton Masquer automatiquement est activé lorsque associé [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) fenêtre est affichée.  
  
##  <a name="a-nameishorizontala--cmfcautohidebuttonishorizontal"></a><a name="ishorizontal"></a>CMFCAutoHideButton::IsHorizontal  
 Détermine si le bouton masquer automatiquement est horizontal ou vertical.  
  
```  
BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le bouton est horizontal ; 0 dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure définit l’orientation d’un [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) de l’objet lors de sa création.  Vous pouvez contrôler l’orientation à l’aide de la `dwAlignment` paramètre dans le [CMFCAutoHideButton::Create](#create) (méthode).  
  
##  <a name="a-nameistopa--cmfcautohidebuttonistop"></a><a name="istop"></a>CMFCAutoHideButton::IsTop  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsTop() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisvisiblea--cmfcautohidebuttonisvisible"></a><a name="isvisible"></a>CMFCAutoHideButton::IsVisible  
 Indique si le bouton Masquer automatiquement est visible.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le bouton est visible ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameondrawa--cmfcautohidebuttonondraw"></a><a name="ondraw"></a>CMFCAutoHideButton::OnDraw  
 L'infrastructure appelle cette méthode au moment de dessiner le bouton masquer automatiquement.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez personnaliser l’apparence de masquer les boutons dans votre application, créez une classe dérivée de `CMFCAutoHideButton`. Dans votre classe dérivée, substituez cette méthode.  
  
##  <a name="a-nameondrawbordera--cmfcautohidebuttonondrawborder"></a><a name="ondrawborder"></a>CMFCAutoHideButton::OnDrawBorder  
 L'infrastructure appelle cette méthode au moment de dessiner la bordure d'un bouton masquer automatiquement.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rectBounds,  
    CRect rectBorderSize);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rectBounds`  
 Le rectangle englobant du bouton Masquer automatiquement.  
  
 [in] `rectBorderSize`  
 L’épaisseur de la bordure de chaque côté du bouton Masquer automatiquement.  
  
### <a name="remarks"></a>Remarques  
 Si vous souhaitez personnaliser la bordure de chaque bouton Masquer automatiquement dans votre application, créez une classe dérivée de la `CMFCAutoHideButton`. Dans votre classe dérivée, substituez cette méthode.  
  
##  <a name="a-nameonfillbackgrounda--cmfcautohidebuttononfillbackground"></a><a name="onfillbackground"></a>CMFCAutoHideButton::OnFillBackground  
 L'infrastructure appelle cette méthode au moment de remplir l'arrière-plan d'un bouton masquer automatiquement.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rect`  
 Le rectangle englobant du bouton Masquer automatiquement.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez le personnaliser pour masquer les boutons dans votre application, créez une classe dérivée de la `CMFCAutoHideButton`. Dans votre classe dérivée, substituez cette méthode.  
  
##  <a name="a-nameshowattachedwindowa--cmfcautohidebuttonshowattachedwindow"></a><a name="showattachedwindow"></a>CMFCAutoHideButton::ShowAttachedWindow  
 Affiche ou masque associé [CDockablePane Class](../../mfc/reference/cdockablepane-class.md).  
  
```  
void ShowAttachedWindow(BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bShow`  
 Valeur booléenne qui spécifie si cette méthode affiche le fichier `CDockablePane`.  
  
##  <a name="a-nameshowbuttona--cmfcautohidebuttonshowbutton"></a><a name="showbutton"></a>CMFCAutoHideButton::ShowButton  
 Affiche ou masque le bouton masquer automatiquement.  
  
```  
virtual void ShowButton(BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bShow`  
 Valeur booléenne qui spécifie s’il faut afficher le bouton Masquer automatiquement.  
  
##  <a name="a-namemovea--cmfcautohidebuttonmove"></a><a name="move"></a>CMFCAutoHideButton::Move  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Move(int nOffset);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nOffset`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namereplacepanea--cmfcautohidebuttonreplacepane"></a><a name="replacepane"></a>CMFCAutoHideButton::ReplacePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ReplacePane(CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pNewBar`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameunsetautohidemodea--cmfcautohidebuttonunsetautohidemode"></a><a name="unsetautohidemode"></a>CMFCAutoHideButton::UnSetAutoHideMode  
 Désactivez le mode de masquage automatique.  
  
```  
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pFirstBarInGroup`  
 Pointeur vers la première barre du groupe.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namehighlightbuttona--cmfcautohidebuttonhighlightbutton"></a><a name="highlightbutton"></a>CMFCAutoHideButton::HighlightButton  
 Met en surbrillance le bouton Masquer automatiquement.  
  
```  
virtual void HighlightButton(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Paramètres  
 `bHighlight`  
 Spécifie le nouveau masquer état du bouton. `TRUE`Indique le bouton est mis en surbrillance, `FALSE` indique le bouton n’est pas mis en surbrillance.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameishighlighteda--cmfcautohidebuttonishighlighted"></a><a name="ishighlighted"></a>CMFCAutoHideButton::IsHighlighted  
 Retourne l’état de mise en surbrillance du bouton Masquer automatiquement.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` si le bouton Masquer automatiquement est mis en surbrillance ; sinon `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCAutoHideBar (classe)](../../mfc/reference/cmfcautohidebar-class.md)   
 [CAutoHideDockSite (classe)](../../mfc/reference/cautohidedocksite-class.md)

