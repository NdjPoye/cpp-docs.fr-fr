---
title: Classe de CCtrlView | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
dev_langs:
- C++
helpviewer_keywords:
- views, and common controls
- controls [MFC], common
- CCtrlView class
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: 20
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
ms.openlocfilehash: 569044de59dc3ccd73157abc86855beef57cb558
ms.lasthandoff: 02/24/2017

---
# <a name="cctrlview-class"></a>Classe de CCtrlView
Adapte l'architecture document/vue aux contrôles communs pris en charge par Windows 98 et Windows NT versions 3.51 et ultérieures.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CCtrlView : public CView  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](#cctrlview)|Construit un objet `CCtrlView`.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CCtrlView::OnDraw](#ondraw)|Appelé par l’infrastructure pour dessiner en utilisant le contexte de périphérique spécifié.|  
|[CCtrlView::PreCreateWindow](#precreatewindow)|Appelé avant la création de la fenêtre Windows attachée à cet objet `CCtrlView`.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Contient le style par défaut pour la classe d’affichage.|  
|[CCtrlView::m_strClass](#m_strclass)|Contient le nom de classe Windows pour la classe d’affichage.|  
  
## <a name="remarks"></a>Remarques  
 La classe `CCtrlView` et ses dérivés, [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), et [CRichEditView](../../mfc/reference/cricheditview-class.md), adapter l’architecture document / vue pour les nouveaux contrôles communs pris en charge par Windows 95/98 et Windows NT versions 3.51 et ultérieures. Pour plus d’informations sur l’architecture document / vue, consultez [Architecture Document/vue](../../mfc/document-view-architecture.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="cctrlview"></a>CCtrlView::CCtrlView  
 Construit un objet `CCtrlView`.  
  
```  
CCtrlView(
    LPCTSTR lpszClass,  
    DWORD dwStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszClass`  
 Nom de classe Windows de la classe d’affichage.  
  
 `dwStyle`  
 Style de la classe d’affichage.  
  
### <a name="remarks"></a>Notes  
 Le framework appelle le constructeur lors de la création d’une fenêtre frame ou une fenêtre est fractionnée. Substituer [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) pour initialiser la vue une fois que le document est lié. Appelez [CWnd::Create](../../mfc/reference/cwnd-class.md#create) ou [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) pour créer l’objet Windows.  
  
##  <a name="m_strclass"></a>CCtrlView::m_strClass  
 Contient le nom de classe Windows pour la classe d’affichage.  
  
```  
CString m_strClass;  
```  
  
##  <a name="m_dwdefaultstyle"></a>CCtrlView::m_dwDefaultStyle  
 Contient le style par défaut pour la classe d’affichage.  
  
```  
DWORD m_dwDefaultStyle;  
```  
  
### <a name="remarks"></a>Remarques  
 Ce style est appliqué lorsqu’une fenêtre est créée.  
  
##  <a name="ondraw"></a>CCtrlView::OnDraw  
 Appelée par l’infrastructure pour dessiner le contenu de la `CCtrlView` de l’objet en utilisant le contexte de périphérique spécifié.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointeur vers le contexte de périphérique dans lequel le dessin se produit.  
  
### <a name="remarks"></a>Remarques  
 `OnDraw`est généralement appelée pour afficher l’écran, en passant un contexte de périphérique spécifié par `pDC`.  
  
##  <a name="precreatewindow"></a>CCtrlView::PreCreateWindow  
 Appelé avant la création de la fenêtre Windows attachée à cet objet `CWnd`.  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Paramètres  
 *cs*  
 A [CREATESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632603) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la création de la fenêtre doit continuer ; 0 pour indiquer l’échec de la création.  
  
### <a name="remarks"></a>Notes  
 Ne jamais appeler directement cette fonction.  
  
 L’implémentation par défaut de cette fonction vérifie un **NULL** nom de classe de fenêtre et les remplace par une valeur par défaut appropriée. Remplacez cette fonction membre pour modifier la `CREATESTRUCT` avant la création de la fenêtre de la structure.  
  
 Chaque classe dérivée de `CCtrlView` ajoute ses propres fonctionnalités à sa substitution de `PreCreateWindow`. Par défaut, ces dérivations de `PreCreateWindow` ne sont pas documentées. Pour déterminer les styles appropriés pour chaque classe et les interdépendances entre les styles, vous pouvez examiner le code source MFC pour la classe de base de votre application. Si vous choisissez de remplacer `PreCreateWindow`, vous pouvez déterminer si les styles utilisés dans la classe de base de votre application fournissent les fonctionnalités que vous avez besoin en utilisant les informations collectées à partir du code source MFC.  
  
 Pour plus d’informations sur la modification des styles de fenêtre, consultez la [modification des Styles d’une fenêtre créée par MFC](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CView (classe)](../../mfc/reference/cview-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CTreeView (classe)](../../mfc/reference/ctreeview-class.md)   
 [CListView (classe)](../../mfc/reference/clistview-class.md)   
 [CRichEditView (classe)](../../mfc/reference/cricheditview-class.md)

