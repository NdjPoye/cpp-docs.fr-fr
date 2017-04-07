---
title: Classe de CMFCRibbonStatusBarPane | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane class
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
caps.latest.revision: 31
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
ms.openlocfilehash: a101e50f55efab44e4cb66d314b2426228dbc5c0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane (classe)
La `CMFCRibbonStatusBarPane` classe implémente un élément de ruban que vous pouvez ajouter à une barre d’état du ruban.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Construit et initialise un objet `CMFCRibbonStatusBarPane`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Retourne la chaîne qui définit la plus longue chaîne de texte qui peut être affichée dans le volet sans les tronquer.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Retourne la valeur actuelle de l’alignement du texte.|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Détermine si l’animation est en cours.|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|Détermine si le volet se trouve dans la zone étendue de la barre d’état du ruban.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Substitue [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Substitue [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Définit la plus longue chaîne de texte qui peut être affichée dans le volet sans les tronquer.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Affecte une liste d’images qui peut être utilisée pour l’animation dans le volet.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Définit l’alignement du texte.|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Démarre l’animation qui est assignée au volet.|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Arrête l’animation qui est assignée au volet. .|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Appelé par l’infrastructure lorsque l’animation qui est assignée au volet s’arrête.|  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment utiliser les différentes méthodes de la classe `CMFCRibbonStatusBarPane`. L’exemple montre comment construire un `CMFCRibbonStatusBarPane` d’objet, de définir l’alignement du texte de l’étiquette du volet de barre d’état, de définir le texte de la plus longs qui peut être affiché dans le volet de barre d’état sans troncation, joindre dans le volet de barre d’état, une liste d’images qui peut être utilisée pour l’animation et démarrer l’animation.  
  
 [!code-cpp[NVC_MFC_RibbonApp n °&2;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 Construisez un objet de volet dans la barre d’état.  
  
```  
CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    BOOL bIsStatic=FALSE,  
    HICON hIcon=NULL,  
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nCmdID`  
 Spécifie l’ID de commande du volet.  
  
 [in] `lpszText`  
 Spécifie la chaîne de texte à afficher dans le volet.  
  
 [in] `bIsStatic`  
 Si `TRUE`, le volet d’état ne peut pas être mis en surbrillance ou sélectionné en cliquant dessus.  
  
 [in] `hIcon`  
 Spécifie un handle d’une icône à afficher dans le volet.  
  
 [in] `lpszAlmostLargeText`  
 Spécifie la plus longue chaîne de texte qui peut être affichée dans le volet.  
  
 [in] `hBmpAnimationList`  
 Spécifie un handle à une liste d’images qui est utilisé pour l’animation.  
  
 [in] `cxAnimation`  
 Spécifie la largeur, en pixels, de l’icône dans la liste d’images qui est utilisée pour l’animation.  
  
 [in] `clrTrnsp`  
 Spécifie la couleur transparente d’images dans la liste d’images qui sont utilisées pour l’animation.  
  
 [in] `uiAnimationListResID`  
 Spécifie un ID de ressource d’une liste d’images qui est utilisé pour l’animation.  
  
##  <a name="getalmostlargetext"></a>CMFCRibbonStatusBarPane::GetAlmostLargeText  
 Obtient la chaîne de texte plus longue que le volet de barre d’état peut afficher.  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La chaîne de texte plus longue que le volet de barre d’état peut afficher.  
  
##  <a name="gettextalign"></a>CMFCRibbonStatusBarPane::GetTextAlign  
 Obtient la valeur actuelle de l’alignement du texte de l’étiquette du volet de barre d’état.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’alignement du texte en cours qui peut être une des opérations suivantes :  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT.  
  
##  <a name="isanimation"></a>CMFCRibbonStatusBarPane::IsAnimation  
 Détermine si l’animation est en cours.  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’animation est en cours ; `FALSE` dans le cas contraire.  
  
##  <a name="isextended"></a>CMFCRibbonStatusBarPane::IsExtended  
 Déterminer si le volet se trouve dans la zone étendue de la barre d’état du ruban.  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet se trouve sur la zone étendue de la barre d’état. Sinon, `FALSE`.  
  
##  <a name="ondrawborder"></a>CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `CDC*`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onfillbackground"></a>CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="onfinishanimation"></a>CMFCRibbonStatusBarPane::OnFinishAnimation  
 Framework appelle cette méthode lors de l’animation qui est assignée au volet se termine.  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>Notes  
 `StopAnimation`appels de méthode du `OnFinishAnimation` (méthode), que vous pouvez utiliser pour nettoyer les données lors de l’animation se termine.  
  
##  <a name="setalmostlargetext"></a>CMFCRibbonStatusBarPane::SetAlmostLargeText  
 Définir le texte de la plus longs qui peut être affiché dans le volet de barre d’état sans les tronquer.  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszAlmostLargeText`  
 Spécifie la chaîne la plus longue qui peut être affichée dans le volet de barre d’état sans les tronquer.  
  
### <a name="remarks"></a>Remarques  
 La bibliothèque calcule la taille du texte qui `lpszAlmostLargeText` spécifie et redimensionne le volet en conséquence. Le texte sera tronqué si elle toujours ne tient pas dans le volet.  
  
##  <a name="setanimationlist"></a>CMFCRibbonStatusBarPane::SetAnimationList  
 Associe une liste d’images qui peut être utilisée pour l’animation dans le volet de barre d’état.  
  
```  
void SetAnimationList(
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hBmpAnimationList`  
 Spécifie un handle à une liste d’images.  
  
 [in] `cxAnimation`  
 Spécifie la largeur, en pixels, du frame dans la liste d’images.  
  
 [in] `clrTransp`  
 Spécifie la couleur transparente de la liste d’images.  
  
 [in] `uiAnimationListResID`  
 Spécifie l’ID de ressource de la liste d’images.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la liste d’images a été correctement attachée dans le volet de barre d’état ; `FALSE` dans le cas contraire.  
  
##  <a name="settextalign"></a>CMFCRibbonStatusBarPane::SetTextAlign  
 Définit l’alignement du texte de l’étiquette du volet de barre d’état.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nAlign`  
 Spécifie l’alignement du texte.  
  
### <a name="remarks"></a>Remarques  
 `nAlign`peut avoir l’une des valeurs suivantes :  
  
- `TA_LEFT`: alignement à gauche  
  
- `TA_CENTER:`alignement au centre  
  
- `TA_RIGHT:`alignement à droite  
  
##  <a name="startanimation"></a>CMFCRibbonStatusBarPane::StartAnimation  
 Démarre l’animation que vous attribuez au volet.  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nFrameDelay`  
 Spécifie la fréquence d’images de l’animation, en millisecondes.  
  
 [in] `nDuration`  
 Spécifie la durée de lecture de l’animation, en millisecondes. Utilisez -1 pour une boucle infinie.  
  
### <a name="remarks"></a>Remarques  
 Vous devez spécifier un handle vers une liste d’images avant d’appeler `StartAnimation` à l’aide de `SetAnimationList`.  
  
##  <a name="stopanimation"></a>CMFCRibbonStatusBarPane::StopAnimation  
 Arrête l’animation que vous avez affecté dans le volet de barre d’état.  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton (classe)](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar (classe)](../../mfc/reference/cmfcribbonstatusbar-class.md)

