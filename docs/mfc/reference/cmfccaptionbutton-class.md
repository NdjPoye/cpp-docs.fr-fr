---
title: Classe de CMFCCaptionButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionButton class
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: 28
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9d6342f87622c34b671ad5ea443eb78ffd8c3838
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton (classe)
La `CMFCCaptionButton` classe implémente un bouton qui s’affiche dans la barre de légende pour un volet d’ancrage ou une fenêtre mini-frame. En général, l'infrastructure crée les boutons de légende automatiquement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="constructors"></a>Constructeurs  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Construit un objet CMFCCaptionButton.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|Retourne la commande représentée par le bouton.|  
|[CMFCCaptionButton::GetIconID](#geticonid)|Retourne l’ID de l’image associée au bouton.|  
|[CMFCCaptionButton::GetRect](#getrect)|Retourne le rectangle occupé par le bouton.|  
|[CMFCCaptionButton::GetSize](#getsize)|Retourne la largeur et la hauteur du bouton.|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Indique si la hauteur de barre de titre est définie à la taille de miniature.|  
|[CMFCCaptionButton::Move](#move)|Définit l’emplacement du bouton de dessin et l’état de la fenêtre Afficher.|  
|[CMFCCaptionButton::OnDraw](#ondraw)|Dessine le bouton de légende.|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Définit la taille de miniature de la barre de titre.|  
  
## <a name="remarks"></a>Notes  
 Vous pouvez dériver une classe à partir de [CPaneFrameWnd classe](../../mfc/reference/cpaneframewnd-class.md) et utilisez la méthode protégée, `AddButton`, pour ajouter des boutons de légende dans une fenêtre frame mini.  
  
 CPaneFrameWnd.h définit l’ID de commande pour les deux types de boutons de légende :  
  
- `AFX_CAPTION_BTN_PIN`, qui affiche un bouton de code confidentiel lorsque le volet d’accueil prend en charge le mode de masquage automatique.  
  
- `AFX_CAPTION_BTN_CLOSE`, qui affiche un **fermer** bouton lorsque le volet peut être fermé ou masqué.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un `CMFCCaptionButton` de l’objet et définissez la taille de miniature de la barre de titre.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#43;](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcaptionbutton.h  
  
##  <a name="cmfccaptionbutton"></a>CMFCCaptionButton::CMFCCaptionButton  
 Construit un objet `CMFCCaptionButton`.  
  
```  
CMFCCaptionButton();

 
CMFCCaptionButton(
    UINT nHit,  
    BOOL bLeftAlign = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nHit`  
 Commande associée au bouton.  
  
 [in] `bLeftAlign`  
 Spécifie si le bouton est aligné à gauche.  
  
 Le tableau suivant répertorie les valeurs possibles pour le `nHit` paramètre.  
  
|Valeur|Commande|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Bouton Fermer.|  
|`HTMINBUTTON`|Bouton de réduction.|  
|`HTMAXBUTTON`|Bouton d’agrandissement.|  
|`AFX_HTLEFTBUTTON`|Flèche gauche.|  
|`AFX_HTRIGHTBUTTON`|Flèche droite.|  
|`AFX_HTMENU`|La flèche de menu.|  
|`HTNOWHERE`|La valeur par défaut ; ne représente un aucun commande.|  
  
### <a name="remarks"></a>Notes  
 Par défaut, les boutons de légende ne sont pas associées à une commande.  
  
 Boutons de légende sont alignés sur la droite ou la gauche.  
  
##  <a name="gethit"></a>CMFCCaptionButton::GetHit  
 Retourne la commande représentée par le bouton.  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La commande représentée par le bouton.  
  
 Le tableau suivant répertorie les valeurs de retour possibles.  
  
|Valeur|Commande|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Bouton Fermer.|  
|`HTMINBUTTON`|Bouton de réduction.|  
|`HTMAXBUTTON`|Bouton d’agrandissement.|  
|`AFX_HTLEFTBUTTON`|Flèche gauche.|  
|`AFX_HTRIGHTBUTTON`|Flèche droite.|  
|`AFX_HTMENU`|La flèche de menu.|  
|`HTNOWHERE`|La valeur par défaut ; ne représente un aucun commande.|  
  
##  <a name="geticonid"></a>CMFCCaptionButton::GetIconID  
 Retourne l’ID de l’image associée au bouton.  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bHorz`  
 `TRUE`pour les flèches gauche ou droite de l’image ID ; `FALSE` de haut ou flèche bas ID d’image.  
  
 [in] `bMaximized`  
 `TRUE`Pour agrandir l’image ID ; `FALSE` pour une réduction de l’image ID.  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de l’image.  
  
### <a name="remarks"></a>Remarques  
 Les paramètres de spécifient l’ID d’image pour réduire ou agrandir les boutons de légende.  
  
##  <a name="getrect"></a>CMFCCaptionButton::GetRect  
 Retourne le rectangle occupé par le bouton.  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le rectangle qui représente l’emplacement du bouton.  
  
### <a name="remarks"></a>Remarques  
 Si vous ne voyez pas le bouton, la valeur retournée est 0.  
  
##  <a name="getsize"></a>CMFCCaptionButton::GetSize  
 Retourne la largeur et la hauteur du bouton.  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les dimensions externes du bouton.  
  
### <a name="remarks"></a>Remarques  
 La taille retournée inclut des bordures et des marges du bouton.  
  
##  <a name="isminiframebutton"></a>CMFCCaptionButton::IsMiniFrameButton  
 Indique si la hauteur de barre de titre est définie à la taille de miniature.  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la légende est définie sur taille mini ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="move"></a>CMFCCaptionButton::Move  
 Définit l’emplacement du bouton de dessin et l’état de la fenêtre Afficher.  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `ptTo`  
 Nouvel emplacement.  
  
 [in] `bHide`  
 Si vous souhaitez afficher le bouton.  
  
##  <a name="ondraw"></a>CMFCCaptionButton::OnDraw  
 Dessine le bouton de légende.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    BOOL bActive,  
    BOOL bHorz = TRUE,  
    BOOL bMaximized = TRUE,  
    BOOL bDisabled = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique pour le bouton.  
  
 [in] `bActive`  
 Si vous souhaitez dessiner une image de bouton actif.  
  
 [in] `bHorz`  
 Réservé pour une utilisation dans une classe dérivée.  
  
 [in] `bMaximized`  
 Si vous souhaitez dessiner une image de bouton agrandi.  
  
 [in] `bDisabled`  
 Si vous souhaitez dessiner une image de bouton activé.  
  
### <a name="remarks"></a>Notes  
 Le `bMaximized` paramètre est utilisé lorsque le bouton est un agrandissement ou bouton de réduction.  
  
##  <a name="setminiframebutton"></a>CMFCCaptionButton::SetMiniFrameButton  
 Définit la taille de miniature de la barre de titre.  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
 `TRUE`pour la hauteur de barre de titre mini ; `FALSE` pour la hauteur par défaut de la barre de titre.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd (classe)](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane (classe)](../../mfc/reference/cdockablepane-class.md)

