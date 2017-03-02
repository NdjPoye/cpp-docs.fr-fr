---
title: Classe de CMFCPreviewCtrlImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPreviewCtrlImpl
- afxwin/CMFCPreviewCtrlImpl
dev_langs:
- C++
helpviewer_keywords:
- CMFCPreviewCtrlImpl class
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b3ccd0d6e03f652798b45ac35d36f8bc2f63e048
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl, classe
Cette classe implémente une fenêtre qui est placée dans une fenêtre hôte fournie par l’interpréteur de commandes pour l’aperçu riche.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl :: ~ CMFCPreviewCtrlImpl](#dtor)|Destruction d’un objet de contrôle de version préliminaire.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Construit un objet de contrôle de version préliminaire.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](#create)|Surchargé. Appelée par un gestionnaire d’aperçus de riches pour créer la fenêtre Windows.|  
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Appelée par un gestionnaire d’aperçus de riches lorsqu’il a besoin détruire ce contrôle.|  
|[CMFCPreviewCtrlImpl::Focus](#focus)|Définit le focus à ce contrôle.|  
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Retourne un document lié à ce contrôle de version préliminaire.|  
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Indique à ce contrôle à redessiner.|  
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Appelée par le Gestionnaire d’aperçus pour créer une relation entre l’implémentation de document et le contrôle de version préliminaire.|  
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Définit un nouveau parent de ce contrôle.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Appelée par un gestionnaire d’aperçus de riches lorsqu’il a besoin définir les éléments visuels de l’aperçu riche contenu.|  
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Définit un nouveau rectangle englobant pour ce contrôle.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Appelée par l’infrastructure pour afficher l’aperçu.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Couleur d’arrière-plan de la fenêtre d’aperçu.|  
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Couleur du texte de la fenêtre d’aperçu.|  
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Police utilisée pour afficher du texte dans la fenêtre d’aperçu.|  
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Pointeur vers un document dont le contenu est affiché dans le contrôle.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h    
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="a-namecmfcpreviewctrlimpla-cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a>CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
Construit un objet de contrôle de version préliminaire.

### <a name="syntax"></a>Syntaxe
CMFCPreviewCtrlImpl() ;  

## <a name="a-namecreatea-cmfcpreviewctrlimplcreate"></a><a name="create"></a>CMFCPreviewCtrlImpl::Create
Surchargé. Appelée par un gestionnaire d’aperçus de riches pour créer la fenêtre Windows.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc  
);  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc,  
   CCreateContext* pContext  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `hWndParent`  
 Handle vers la fenêtre hôte fournie par l’interpréteur de commandes pour l’aperçu riche.  
  
 `prc`  
 Spécifie la taille initiale et la position de la fenêtre.  
  
 `pContext`  
 Pointeur vers un contexte de création.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la création a réussi ; dans le cas contraire `FALSE`.  
  
## <a name="a-namedestroya-cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a>CMFCPreviewCtrlImpl::Destroy
Appelée par un gestionnaire d’aperçus de riches lorsqu’il a besoin détruire ce contrôle.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual void Destroy();  
```  
  
## <a name="a-namedopainta-cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a>CMFCPreviewCtrlImpl::DoPaint  
Appelée par l’infrastructure pour afficher l’aperçu.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual void DoPaint(  
   CPaintDC* pDC  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointeur vers un contexte de périphérique pour la peinture.  


## <a name="a-namefocusa-cmfcpreviewctrlimplfocus"></a><a name="focus"></a>CMFCPreviewCtrlImpl::Focus  
Définit le focus à ce contrôle.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual void Focus();  
```  
## <a name="a-namegetdocumenta-cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a>CMFCPreviewCtrlImpl::GetDocument
Retourne un document lié à ce contrôle de version préliminaire.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
ATL::IDocument* GetDocument();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un document dont le contenu est affiché dans le contrôle.

## <a name="a-namemclrbackcolora-cmfcpreviewctrlimplmclrbackcolor"></a><a name="m_clrbackcolor"></a>CMFCPreviewCtrlImpl::m_clrBackColor  
Couleur d’arrière-plan de la fenêtre d’aperçu.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
COLORREF m_clrBackColor;  
```  

## <a name="a-namemclrtextcolora-cmfcpreviewctrlimplmclrtextcolor"></a><a name="m_clrtextcolor"></a>CMFCPreviewCtrlImpl::m_clrTextColor
Couleur du texte de la fenêtre d’aperçu.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
COLORREF m_clrTextColor;  
```  
## <a name="a-namemfonta-cmfcpreviewctrlimplmfont--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a>CMFCPreviewCtrlImpl::m_font police utilisée pour afficher du texte dans la fenêtre d’aperçu.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
CFont m_font;  
```  
## <a name="a-namempdocumenta-cmfcpreviewctrlimplmpdocument"></a><a name="m_pdocument"></a>CMFCPreviewCtrlImpl::m_pDocument  
Pointeur vers un document dont le contenu est affiché dans le contrôle.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
ATL::IDocument* m_pDocument;  
```  

## <a name="a-nameredrawa-cmfcpreviewctrlimplredraw"></a><a name="redraw"></a>CMFCPreviewCtrlImpl::Redraw  
Indique à ce contrôle à redessiner.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual void Redraw();  
```  
## <a name="a-namesetdocumenta-cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a>CMFCPreviewCtrlImpl::SetDocument 
Appelée par le Gestionnaire d’aperçus pour créer une relation entre l’implémentation de document et le contrôle de version préliminaire.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
void SetDocument(  
   IDocument* pDocument  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `pDocument`  
 Pointeur vers l’implémentation d’un document.  

## <a name="a-namesethosta-cmfcpreviewctrlimplsethost"></a><a name="sethost"></a>CMFCPreviewCtrlImpl::SetHost  
Définit un nouveau parent de ce contrôle.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual void SetHost(  
   HWND hWndParent  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `hWndParent`  
 Handle vers la nouvelle fenêtre parent.  

## <a name="a-namesetpreviewvisualsa-cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CMFCPreviewCtrlImpl::SetPreviewVisuals  
Appelée par un gestionnaire d’aperçus de riches lorsqu’il a besoin définir les éléments visuels de l’aperçu riche contenu.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual void SetPreviewVisuals(  
   COLORREF clrBack,  
   COLORREF clrText,  
   const LOGFONTW *plf  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `clrBack`  
 Couleur d’arrière-plan de la fenêtre d’aperçu.  
  
 `clrText`  
 Couleur du texte de la fenêtre d’aperçu.  
  
 `plf`  
 Police utilisée pour afficher du texte dans la fenêtre d’aperçu. 

##  <a name="a-namesetrecta-cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a>CMFCPreviewCtrlImpl::SetRect  
Définit un nouveau rectangle englobant pour ce contrôle.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual void SetRect(  
   const RECT* prc,  
   BOOL bRedraw  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `prc`  
 Spécifie la nouvelle taille et la position du contrôle de version préliminaire.  
  
 `bRedraw`  
 Spécifie si le contrôle doit être redessiné.  
  
### <a name="remarks"></a>Remarques  
 Généralement, un rectangle englobant est défini lorsque le contrôle hôte est redimensionné.  

## <a name="a-namedtora-cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a>CMFCPreviewCtrlImpl :: ~ CMFCPreviewCtrlImpl  
Destruction d’un objet de contrôle de version préliminaire.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual ~CMFCPreviewCtrlImpl();  
```  
  

