---
title: Classe de CMFCPropertyGridToolTipCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridToolTipCtrl::PreTranslateMessage
- ~CMFCPropertyGridToolTipCtrl
- PreTranslateMessage
- CMFCPropertyGridToolTipCtrl.~CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl.PreTranslateMessage
- CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl class
- CMFCPropertyGridToolTipCtrl class, destructor
- PreTranslateMessage method
- ~CMFCPropertyGridToolTipCtrl destructor
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e5290706799dcd253205ac74dad72cd7783d19dd
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl (classe)
Implémente une info-bulle de contrôle qui le [CMFCPropertyGridCtrl classe](../../mfc/reference/cmfcpropertygridctrl-class.md) utilise pour afficher des info-bulles.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Construit un objet `CMFCPropertyGridToolTipCtrl`.|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCPropertyGridToolTipCtrl::Create](#create)|Crée une fenêtre pour le contrôle d’info-bulle.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Désactive et masque le contrôle d’info-bulle.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Retourne les coordonnées de la dernière position du contrôle d’info-bulle.|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Masque le contrôle d’info-bulle.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Utilisé par la classe [CWinApp](../../mfc/reference/cwinapp-class.md) pour convertir des messages de fenêtre avant qu’ils soient distribués à le [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) fonctions de Windows. (Substitue [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Définit l’espacement entre le texte d’info-bulle et la bordure de la fenêtre d’info-bulle.|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Affiche le contrôle d’info-bulle.|  
  
## <a name="remarks"></a>Remarques  
 Info-bulles sont affichent lorsque le pointeur se trouve sur un nom de propriété. Le [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) classe affiche une info-bulle afin qu’il soit lisible par l’utilisateur. En règle générale, la position d’une info-bulle est déterminée par la position du pointeur. À l’aide de cette classe, l’info-bulle s’affiche sur le nom de propriété et ressemble à l’extension de propriété naturelle, afin que le nom de propriété soit entièrement visible.  
  
 MFC crée ce contrôle automatiquement et l’utilise dans les [CMFCPropertyGridCtrl classe](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un objet de la `CMFCPropertyGridToolTipCtrl` classe et comment afficher le contrôle d’info-bulle.  
  
 [!code-cpp[NVC_MFC_RibbonApp n °&23;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxpropertygridtooltipctrl.h  
  
##  <a name="a-namecmfcpropertygridtooltipctrla--cmfcpropertygridtooltipctrlcmfcpropertygridtooltipctrl"></a><a name="cmfcpropertygridtooltipctrl"></a>CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 Construit un objet `CMFCPropertyGridToolTipCtrl`.  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="a-namecreatea--cmfcpropertygridtooltipctrlcreate"></a><a name="create"></a>CMFCPropertyGridToolTipCtrl::Create  
 Crée une fenêtre pour le contrôle d’info-bulle.  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndParent`  
 Pointeur vers la fenêtre parente.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la fenêtre a été créée avec succès ; Sinon, FALSE.  
  
##  <a name="a-namedeactivatea--cmfcpropertygridtooltipctrldeactivate"></a><a name="deactivate"></a>CMFCPropertyGridToolTipCtrl::Deactivate  
 Désactive et masque le contrôle d’info-bulle.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode définit la dernière position et texte des valeurs vides, afin que les futurs appels à [CMFCPropertyGridToolTipCtrl::Track](#track) l’info-bulle.  
  
##  <a name="a-namegetlastrecta--cmfcpropertygridtooltipctrlgetlastrect"></a><a name="getlastrect"></a>CMFCPropertyGridToolTipCtrl::GetLastRect  
 Retourne les coordonnées de la dernière position du contrôle d’info-bulle.  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `rect`  
 Contient la dernière position du contrôle d’info-bulle.  
  
##  <a name="a-namehidea--cmfcpropertygridtooltipctrlhide"></a><a name="hide"></a>CMFCPropertyGridToolTipCtrl::Hide  
 Masque le contrôle d’info-bulle.  
  
```  
void Hide();
```  
  
##  <a name="a-namesettextmargina--cmfcpropertygridtooltipctrlsettextmargin"></a><a name="settextmargin"></a>CMFCPropertyGridToolTipCtrl::SetTextMargin  
 Définit l’espacement entre le texte d’info-bulle et la bordure de la fenêtre d’info-bulle.  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nTextMargin`  
 Spécifie l’espacement entre le texte info-bulle du contrôle et la bordure de la fenêtre d’info-bulle. La valeur par défaut est 10 pixels.  
  
##  <a name="a-nametracka--cmfcpropertygridtooltipctrltrack"></a><a name="track"></a>CMFCPropertyGridToolTipCtrl::Track  
 Affiche le contrôle d’info-bulle.  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `rect`  
 Spécifie la position et la taille de l’info-bulle du contrôle.  
  
 [in] `strText`  
 Spécifie le texte à afficher dans l’info-bulle.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode affiche le contrôle d’info-bulle à la position et la taille spécifiée par `rect`. Si la position, la taille et le texte n’ont pas changé depuis la dernière fois que cette méthode a été appelée, cette méthode n’a aucun effet.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

