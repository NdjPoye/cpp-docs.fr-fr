---
title: CReBar (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- rebar controls, control bar
- CReBar class
- Internet Explorer 4.0 common controls
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
caps.latest.revision: 22
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
ms.openlocfilehash: 38ac4611503bec70ea9f809a4d4f9d4b5133e30e
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="crebar-class"></a>CReBar (classe)
Barre de contrôles qui fournit des informations de disposition, de persistance et d'état pour les contrôles rebar.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CReBar : public CControlBar  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CReBar::AddBar](#addbar)|Ajoute une bande à un contrôle rebar.|  
|[CReBar::Create](#create)|Crée le contrôle rebar et l’attache à le `CReBar` objet.|  
|[CReBar::GetReBarCtrl](#getrebarctrl)|Permet d’accéder directement au contrôle commun sous-jacent.|  
  
## <a name="remarks"></a>Remarques  
 Un objet rebar peut contenir plusieurs fenêtres enfants, généralement d'autres contrôles, notamment des zones d'édition, des barres d'outils et des zones de liste. Un objet rebar peut afficher les fenêtres enfants sur une image bitmap spécifiée. Votre application peut redimensionner automatiquement le rebar, ou l’utilisateur peut redimensionner manuellement le rebar en cliquant ou en faisant glisser sa barre de redimensionnement.  
  
 ![Exemple de RebarMenu](../../mfc/reference/media/vc4sc61.gif "vc4sc61")  
  
## <a name="rebar-control"></a>Contrôle rebar  
 Un objet rebar se comporte comme un objet de barre d’outils. Un contrôle rebar utilise le mécanisme de cliquez et faites glisser pour redimensionner les bandes. Un contrôle rebar peut contenir une ou plusieurs bandes, chaque bande disposant de n’importe quelle combinaison d’une barre de redimensionnement, bitmap, une étiquette de texte et fenêtre enfant. Toutefois, les bandes ne peut pas contenir plusieurs fenêtres enfants.  
  
 **CReBar** utilise le [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) classe pour fournir son implémentation. Vous pouvez accéder au contrôle de rebar via [GetReBarCtrl](#getrebarctrl) pour tirer parti des options de personnalisation du contrôle. Pour plus d’informations sur les contrôles rebar, consultez `CReBarCtrl`. Pour plus d’informations sur les contrôles rebar, consultez [à l’aide de CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
> [!CAUTION]
>  Rebar et objets de contrôle rebar ne gèrent pas la barre d’ancrage de contrôles MFC. Si **CRebar::EnableDocking** est appelée, votre application sera évaluée.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxext.h  
  
##  <a name="addbar"></a>CReBar::AddBar  
 Appelez cette fonction membre pour ajouter une bande rebar.  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

 
BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>Paramètres  
 `pBar`  
 Un pointeur vers un `CWnd` objet de la fenêtre enfant sera inséré dans le contrôle rebar. L’objet référencé doit avoir un **WS_CHILD**.  
  
 `lpszText`  
 Pointeur vers une chaîne contenant le texte à afficher sur le contrôle rebar. **NULL** par défaut. Le texte contenu dans `lpszText` ne fait pas partie de la fenêtre enfant ; il se trouve sur le rebar lui-même.  
  
 `pbmp`  
 Un pointeur vers un `CBitmap` objet à afficher sur l’arrière-plan du contrôle rebar. **NULL** par défaut.  
  
 `dwStyle`  
 Un `DWORD` contenant le style à appliquer au rebar. Consultez le **fStyle** description de la structure Win32 de fonction [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) pour une liste complète des styles de bande.  
  
 *clrFore*  
 A **COLORREF** valeur qui représente la couleur de premier plan du rebar.  
  
 *clrBack*  
 A **COLORREF** valeur qui représente la couleur d’arrière-plan du rebar.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl n °&1;](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]  
  
##  <a name="create"></a>CReBar::Create  
 Appelez cette fonction membre pour créer un contrôle rebar.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointeur vers le `CWnd` objet dont la fenêtre Windows est le parent de la barre d’état. Normalement votre fenêtre frame.  
  
 `dwCtrlStyle`  
 Le style du contrôle rebar. Par défaut, **RBS_BANDBORDERS**, qui affiche limiter les lignes entre les bandes contiguës dans le contrôle rebar. Consultez la page [Styles de contrôle Rebar](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour obtenir la liste des styles.  
  
 `dwStyle`  
 Les styles de fenêtre rebar.  
  
 `nID`  
 ID de fenêtre enfant. du rebar  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CReBar::AddBar](#addbar).  
  
##  <a name="getrebarctrl"></a>CReBar::GetReBarCtrl  
 Cette fonction membre permet d’accéder directement au contrôle commun sous-jacent.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à un [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction membre pour tirer parti des fonctionnalités du contrôle commun rebar de Windows dans la personnalisation de votre contrôle rebar. Lorsque vous appelez `GetReBarCtrl`, elle retourne un objet de référence pour le `CReBarCtrl` afin de pouvoir utiliser l’ensemble des fonctions membres de l’objet.  
  
 Pour plus d’informations sur l’utilisation de `CReBarCtrl` pour personnaliser votre rebar, consultez [à l’aide de CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl n °&2;](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC MFCIE](../../visual-cpp-samples.md)   
 [CControlBar (classe)](../../mfc/reference/ccontrolbar-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




