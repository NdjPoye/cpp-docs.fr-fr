---
title: Classe de CAtlPreviewCtrlImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlpreviewctrlimpl/ATL::CAtlPreviewCtrlImpl
- CAtlPreviewCtrlImpl
dev_langs:
- C++
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
caps.latest.revision: 26
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
ms.openlocfilehash: 979dc23eabc2ba2362f7301fc34ca89016d58f37
ms.lasthandoff: 02/24/2017

---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl (classe)
Cette classe est une implémentation d’une fenêtre qui est placée dans une fenêtre hôte fournie par l’interpréteur de commandes pour l’aperçu riche d’ATL.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl :: ~ CAtlPreviewCtrlImpl](#dtor)|Destruction d’un objet de contrôle de version préliminaire.|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Construit un objet de contrôle de version préliminaire.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::Create](#create)|Appelée par un gestionnaire d’aperçus de riches pour créer la fenêtre Windows.|  
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Appelée par un gestionnaire d’aperçus de riches lorsqu’il a besoin détruire ce contrôle.|  
|[CAtlPreviewCtrlImpl::Focus](#focus)|Définit le focus à ce contrôle.|  
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|Gère le message WM_PAINT.|  
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Indique à ce contrôle à redessiner.|  
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Définit un nouveau parent de ce contrôle.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Appelée par un gestionnaire d’aperçus de riches lorsqu’il a besoin définir les éléments visuels de l’aperçu riche contenu.|  
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Définit un nouveau rectangle englobant pour ce contrôle.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Appelée par l’infrastructure pour afficher l’aperçu.|  
  
### <a name="protected-constants"></a>Constantes protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Police utilisée pour afficher du texte dans la fenêtre d’aperçu.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Couleur d’arrière-plan de la fenêtre d’aperçu.|  
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Couleur du texte de la fenêtre d’aperçu.|  

  
## <a name="remarks"></a>Remarques  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `TBase`  
  
 `ATL::CMessageMap`  
  
 `ATL::CWindowImplRoot<TBase>`  
  
 `ATL::CWindowImplBaseT<TBase,TWinTraits>`  
  
 [ATL::CWindowImpl\<CAtlPreviewCtrlImpl >](../../atl/reference/cwindowimpl-class.md)  
  
 `IPreviewCtrl`  
  
 `ATL::CAtlPreviewCtrlImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlpreviewctrlimpl.h  
  
##  <a name="a-namecatlpreviewctrlimpla--catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a>CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl  
 Construit un objet de contrôle de version préliminaire.  
  
```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namedtora--catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a>CAtlPreviewCtrlImpl :: ~ CAtlPreviewCtrlImpl  
 Destruction d’un objet de contrôle de version préliminaire.  
  
```
virtual ~CAtlPreviewCtrlImpl(void);
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecreatea--catlpreviewctrlimplcreate"></a><a name="create"></a>CAtlPreviewCtrlImpl::Create  
 Appelée par un gestionnaire d’aperçus de riches pour créer la fenêtre Windows.  
  
```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWndParent`  
 Handle vers la fenêtre hôte fournie par l’interpréteur de commandes pour l’aperçu riche.  
  
 `prc`  
 Spécifie la taille initiale et la position de la fenêtre.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` en cas de réussite ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namedestroya--catlpreviewctrlimpldestroy"></a><a name="destroy"></a>CAtlPreviewCtrlImpl::Destroy  
 Appelée par un gestionnaire d’aperçus de riches lorsqu’il a besoin détruire ce contrôle.  
  
```
virtual void Destroy();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namedopainta--catlpreviewctrlimpldopaint"></a><a name="dopaint"></a>CAtlPreviewCtrlImpl::DoPaint  
 Appelée par l’infrastructure pour afficher l’aperçu.  
  
```
virtual void DoPaint(HDC hdc);
```  
  
### <a name="parameters"></a>Paramètres  
 `hdc`  
 Handle vers un contexte de périphérique pour la peinture.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namefocusa--catlpreviewctrlimplfocus"></a><a name="focus"></a>CAtlPreviewCtrlImpl::Focus  
 Définit le focus à ce contrôle.  
  
```
virtual void Focus();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemclrbacka--catlpreviewctrlimplmclrback"></a><a name="m_clrback"></a>CAtlPreviewCtrlImpl::m_clrBack  
 Couleur d’arrière-plan de la fenêtre d’aperçu.  
  
```
COLORREF m_clrBack;
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemclrtexta--catlpreviewctrlimplmclrtext"></a><a name="m_clrtext"></a>CAtlPreviewCtrlImpl::m_clrText  
 Couleur du texte de la fenêtre d’aperçu.  
  
```
COLORREF m_clrText;
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namemplfa--catlpreviewctrlimplmplf"></a><a name="m_plf"></a>CAtlPreviewCtrlImpl::m_plf  
 Police utilisée pour afficher du texte dans la fenêtre d’aperçu.  
  
```
const LOGFONTW* m_plf;
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonpainta--catlpreviewctrlimplonpaint"></a><a name="onpaint"></a>CAtlPreviewCtrlImpl::OnPaint  
 Gère le message WM_PAINT.  
  
```
LRESULT OnPaint(  
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Paramètres  
 `nMsg`  
 La valeur WM_PAINT.  
  
 `wParam`  
 Ce paramètre n'est pas utilisé.  
  
 `lParam`  
 Ce paramètre n'est pas utilisé.  
  
 `bHandled`  
 Lorsque cette fonction est retournée, elle contient `TRUE`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours 0.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameredrawa--catlpreviewctrlimplredraw"></a><a name="redraw"></a>CAtlPreviewCtrlImpl::Redraw  
 Indique à ce contrôle à redessiner.  
  
```
virtual void Redraw();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesethosta--catlpreviewctrlimplsethost"></a><a name="sethost"></a>CAtlPreviewCtrlImpl::SetHost  
 Définit un nouveau parent de ce contrôle.  
  
```
virtual void SetHost(HWND hWndParent);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWndParent`  
 Handle vers la nouvelle fenêtre parent.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetpreviewvisualsa--catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CAtlPreviewCtrlImpl::SetPreviewVisuals  
 Appelée par un gestionnaire d’aperçus de riches lorsqu’il a besoin définir les éléments visuels de l’aperçu riche contenu.  
  
```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```  
  
### <a name="parameters"></a>Paramètres  
 `clrBack`  
 Couleur d’arrière-plan de la fenêtre d’aperçu.  
  
 `clrText`  
 Couleur du texte de la fenêtre d’aperçu.  
  
 `plf`  
 Police utilisée pour afficher du texte dans la fenêtre d’aperçu.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetrecta--catlpreviewctrlimplsetrect"></a><a name="setrect"></a>CAtlPreviewCtrlImpl::SetRect  
 Définit un nouveau rectangle englobant pour ce contrôle.  
  
```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```  
  
### <a name="parameters"></a>Paramètres  
 `prc`  
 Spécifie la nouvelle taille et la position du contrôle de version préliminaire.  
  
 `bRedraw`  
 Spécifie si le contrôle doit être redessiné.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Composants COM bureau ATL](../../atl/atl-com-desktop-components.md)

