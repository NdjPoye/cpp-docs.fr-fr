---
title: CSpinButtonCtrl (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CSpinButtonCtrl
- CSpinButtonCtrl class
- CSpinButtonCtrl class, common controls
- up-down controls, spin button control
- spin button control
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
caps.latest.revision: 23
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
ms.openlocfilehash: 486a0842ed04f0e760bbb332986a97a35ce9851f
ms.lasthandoff: 02/24/2017

---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl (classe)
Fournit les fonctionnalités du contrôle commun de bouton toupie (spin) Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Construit un objet `CSpinButtonCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](#create)|Crée un contrôle de bouton toupie (spin) et l’attache à une `CSpinButtonCtrl` objet.|  
|[CSpinButtonCtrl::CreateEx](#createex)|Crée un contrôle de bouton toupie (spin) avec les styles étendus Windows spécifiés et l’attache à une `CSpinButtonCtrl` objet.|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|Récupère les informations de l’accélération d’un contrôle de bouton toupie (spin).|  
|[CSpinButtonCtrl::GetBase](#getbase)|Extrait de la base d’un contrôle de bouton toupie (spin).|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Récupère un pointeur vers la fenêtre associée en cours.|  
|[CSpinButtonCtrl::GetPos](#getpos)|Récupère la position actuelle d’un contrôle de bouton toupie (spin).|  
|[CSpinButtonCtrl::GetRange](#getrange)|Récupère les limites supérieures et inférieures (plage) d’un contrôle de bouton toupie (spin).|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|Définit l’accélération d’un contrôle de bouton toupie (spin).|  
|[CSpinButtonCtrl::SetBase](#setbase)|Définit la base d’un contrôle de bouton toupie (spin).|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Définit la fenêtre associée pour un contrôle de bouton toupie (spin).|  
|[CSpinButtonCtrl::SetPos](#setpos)|Définit la position actuelle du contrôle.|  
|[CSpinButtonCtrl::SetRange](#setrange)|Définit les limites supérieures et inférieures (plage) d’un contrôle de bouton toupie (spin).|  
  
## <a name="remarks"></a>Remarques  
 Un « contrôle toupie » (également appelé contrôle up-down) est une paire de flèches que l’utilisateur peut cliquer pour incrémenter ou décrémenter une valeur, telle qu’une position de défilement ou un numéro affiché dans un contrôle Compagnon. La valeur associée à un contrôle de bouton toupie (spin) est appelée à sa position actuelle. Un contrôle de bouton toupie (spin) est souvent utilisé avec un contrôle Compagnon, appelé « fenêtre associée ».  
  
 Ce contrôle (et par conséquent la `CSpinButtonCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT version 3.51 et ultérieures.  
  
 À l’utilisateur, un contrôle de bouton toupie (spin) et sa fenêtre associée souvent ressemblent un seul contrôle. Vous pouvez spécifier qu’un contrôle toupie automatiquement se positionne en regard de la fenêtre associée, et que la légende de la fenêtre associée automatiquement définie à sa position actuelle. Vous pouvez utiliser un contrôle de bouton toupie (spin) avec un contrôle d’édition pour inviter l’utilisateur pour entrée numérique.  
  
 En cliquant sur la flèche vers le haut déplace la position actuelle vers le maximum, et en cliquant sur la flèche vers le bas déplace la position actuelle vers le minimum. Par défaut, le minimum est 100 et la valeur maximale est 0. Chaque fois que la valeur minimale est supérieure au maximum (par exemple, lorsque les paramètres par défaut sont utilisés), en cliquant sur la baisse de flèche vers le haut la valeur de position et en cliquant sur la flèche vers le bas pour l’augmenter.  
  
 Un contrôle de bouton toupie (spin) sans fenêtre associée fonctionne comme une sorte de barre de défilement simplifiée. Par exemple, un contrôle onglet affiche parfois un contrôle de bouton toupie (spin) pour permettre aux utilisateurs de faire défiler des onglets supplémentaires dans l’affichage.  
  
 Pour plus d’informations sur l’utilisation de `CSpinButtonCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et [l’utilisation de CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="a-namecreatea--cspinbuttonctrlcreate"></a><a name="create"></a>CSpinButtonCtrl::Create  
 Crée un contrôle de bouton toupie (spin) et l’attache à une `CSpinButtonCtrl` objet...  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie le style du contrôle bouton toupie (spin). S’appliquent à n’importe quelle combinaison de styles de contrôle de bouton toupie (spin) pour le contrôle. Ces styles sont décrites dans [Styles de contrôle Up-Down](http://msdn.microsoft.com/library/windows/desktop/bb759885) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Spécifie la taille et la position du contrôle de bouton toupie (spin). Il peut être soit un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure  
  
 `pParentWnd`  
 Un pointeur vers la fenêtre de parent du contrôle de bouton toupie (spin), généralement un `CDialog`. Il ne doit pas être **NULL.**  
  
 `nID`  
 Spécifie l’ID. du contrôle de bouton spin  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Vous construisez un `CSpinButtonCtrl` tout d’abord l’objet en deux étapes, appelez le constructeur, puis appelez **créer**, qui crée le contrôle spin et l’attache à le `CSpinButtonCtrl` objet.  
  
 Pour créer un contrôle de bouton toupie (spin) avec les styles de fenêtre étendus, appelez [CSpinButtonCtrl::CreateEx](#createex) au lieu de **créer**.  
  
##  <a name="a-namecreateexa--cspinbuttonctrlcreateex"></a><a name="createex"></a>CSpinButtonCtrl::CreateEx  
 Crée un contrôle (une fenêtre enfant) et l’associe à la `CSpinButtonCtrl` objet.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwExStyle`  
 Spécifie le style étendu du contrôle en cours de création. Pour obtenir la liste de styles étendus windows, consultez le `dwExStyle` paramètre [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Spécifie le style du contrôle bouton toupie (spin). S’appliquent à n’importe quelle combinaison de styles de contrôle de bouton toupie (spin) pour le contrôle. Ces styles sont décrites dans [Styles de contrôle Up-Down](http://msdn.microsoft.com/library/windows/desktop/bb759885) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure décrivant la taille et la position de la fenêtre doit être créée, dans les coordonnées clientes de `pParentWnd`.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parent du contrôle.  
  
 `nID`  
 ID de fenêtre enfant. du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Utilisez `CreateEx` au lieu de [créer](#create) pour appliquer des styles étendus Windows, spécifiés par la préface de style étendu Windows **WS_EX_**.  
  
##  <a name="a-namecspinbuttonctrla--cspinbuttonctrlcspinbuttonctrl"></a><a name="cspinbuttonctrl"></a>CSpinButtonCtrl::CSpinButtonCtrl  
 Construit un objet `CSpinButtonCtrl`.  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="a-namegetaccela--cspinbuttonctrlgetaccel"></a><a name="getaccel"></a>CSpinButtonCtrl::GetAccel  
 Récupère les informations de l’accélération d’un contrôle de bouton toupie (spin).  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nAccel`  
 Nombre d’éléments dans le tableau spécifié par `pAccel`.  
  
 `pAccel`  
 Pointeur vers un tableau de [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) des structures qui reçoit des informations de l’accélération.  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre de structures d’accélérateur récupérés.  
  
##  <a name="a-namegetbasea--cspinbuttonctrlgetbase"></a><a name="getbase"></a>CSpinButtonCtrl::GetBase  
 Extrait de la base d’un contrôle de bouton toupie (spin).  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de base en cours.  
  
##  <a name="a-namegetbuddya--cspinbuttonctrlgetbuddy"></a><a name="getbuddy"></a>CSpinButtonCtrl::GetBuddy  
 Récupère un pointeur vers la fenêtre associée en cours.  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la fenêtre associée en cours.  
  
##  <a name="a-namegetposa--cspinbuttonctrlgetpos"></a><a name="getpos"></a>CSpinButtonCtrl::GetPos  
 Récupère la position actuelle d’un contrôle de bouton toupie (spin).  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  ```  
  
### Parameters  
 *lpbError*  
 A pointer to a boolean value that is set to zero if the value is successfully retrieved or non-zero if an error occurs. If this parameter is set to **NULL**, errors are not reported.  
  
### Return Value  
 The first version returns the 16-bit current position in the low-order word. The high-order word is nonzero if an error occurred.  
  
 The second version returns the 32-bit position.  
  
### Remarks  
 When it processes the value returned, the control updates its current position based on the caption of the buddy window. The control returns an error if there is no buddy window or if the caption specifies an invalid or out-of-range value.  
  
##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange  
 Retrieves the upper and lower limits (range) for a spin button control.  
  
```  
GetRange() DWORD const ;  
  
void GetRange (int s’inférieur,  
    int se supérieur) const ;  
  
void GetRange32 (int s’inférieurs,  
    int se supérieur) const ;  
```  
  
### Parameters  
 *lower*  
 Reference to an integer that receives the lower limit for the control.  
  
 *upper*  
 Reference to an integer that receives the upper limit for the control.  
  
### Return Value  
 The first version returns a 32-bit value containing the upper and lower limits. The low-order word is the upper limit for the control, and the high-order word is the lower limit.  
  
### Remarks  
 The member function `GetRange32` retrieves the spin button control's range as a 32-bit integer.  
  
##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel  
 Sets the acceleration for a spin button control.  
  
```  
Fonctions membres SetAccel BOOL (int nAccel,  
    UDACCEL* pAccel) ;
```  
  
### Parameters  
 `nAccel`  
 Number of [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) structures specified by `pAccel`.  
  
 `pAccel`  
 Pointer to an array of `UDACCEL` structures, which contain acceleration information. Elements should be sorted in ascending order based on the **nSec** member.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase  
 Sets the base for a spin button control.  
  
```  
int SetBase (int nBase) ;
```  
  
### Parameters  
 `nBase`  
 New base value for the control. It can be 10 for decimal or 16 for hexadecimal.  
  
### Return Value  
 The previous base value if successful, or zero if an invalid base is given.  
  
### Remarks  
 The base value determines whether the buddy window displays numbers in decimal or hexadecimal digits. Hexadecimal numbers are always unsigned; decimal numbers are signed.  
  
##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy  
 Sets the buddy window for a spin button control.  
  
```  
CWnd* SetBuddy (CWnd* pWndBuddy) ;
```  
  
### Parameters  
 `pWndBuddy`  
 Pointer to the new buddy window.  
  
### Return Value  
 A pointer to the previous buddy window.  
  
### Remarks  
 A spin control is almost always associated with another window, such as an edit control, that displays some content. This other window is called the "buddy" of the spin control.  
  
##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos  
 Sets the current position for a spin button control.  
  
```  
int, fonction membre SetPos (nPos int) ;  
int SetPos32(int nPos) ;
```  
  
### Parameters  
 `nPos`  
 New position for the control. This value must be in the range specified by the upper and lower limits for the control.  
  
### Return Value  
 The previous position (16-bit precision for `SetPos`, 32-bit precision for `SetPos32`).  
  
### Remarks  
 `SetPos32` sets the 32-bit position.  
  
##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange  
 Sets the upper and lower limits (range) for a spin button control.  
  
```  
void SetRange (short nLower,  
    short nUpper) ;

 
void SetRange32 (int nLower,  
    nUpper int) ;
```  
  
### Parameters  
 `nLower`and `nUpper`  
 Upper and lower limits for the control. For `SetRange`, neither limit can be greater than **UD_MAXVAL** or less than **UD_MINVAL**; in addition, the difference between the two limits cannot exceed **UD_MAXVAL**. `SetRange32` places no restrictions on the limits; use any integers.  
  
### Remarks  
 The member function `SetRange32` sets the 32-bit range for the spin button control.  
  
> [!NOTE]
>  The default range for the spin button has the maximum set to zero (0) and the minimum set to 100. Because the maximum value is less than the minimum value, clicking the up arrow will decrease the position and clicking the down arrow will increase it. Use `CSpinButtonCtrl::SetRange` to adjust these values.  
  
## See Also  
 [MFC Sample CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd Class](../../mfc/reference/cwnd-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Class](../../mfc/reference/csliderctrl-class.md)

