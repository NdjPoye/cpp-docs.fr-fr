---
title: CSliderCtrl (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CSliderCtrl
- slider controls, CSliderCtrl class
- CSliderCtrl class, common controls
- CSliderCtrl class
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0d024c7d6670ff3b7a94b9657151e7bf1958d5f1
ms.lasthandoff: 02/24/2017

---
# <a name="csliderctrl-class"></a>CSliderCtrl (classe)
Fournit les fonctionnalités du contrôle commun de curseur Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Construit un objet `CSliderCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|Efface la sélection actuelle dans un contrôle de curseur.|  
|[CSliderCtrl::ClearTics](#cleartics)|Supprime les marques de graduation actuelle à partir d’un contrôle slider.|  
|[CSliderCtrl::Create](#create)|Crée un contrôle slider et l’attache à une `CSliderCtrl` objet.|  
|[CSliderCtrl::CreateEx](#createex)|Crée un contrôle slider avec les styles étendus Windows spécifiés et l’attache à une `CSliderCtrl` objet.|  
|[CSliderCtrl::GetBuddy](#getbuddy)|Récupère le handle de fenêtre associée contrôle slider à un emplacement donné.|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Récupère la taille de canal du contrôle de curseur.|  
|[CSliderCtrl::GetLineSize](#getlinesize)|Récupère la taille de ligne d’un contrôle slider.|  
|[CSliderCtrl::GetNumTics](#getnumtics)|Récupère le nombre de graduations dans un contrôle de curseur.|  
|[CSliderCtrl::GetPageSize](#getpagesize)|Récupère la taille de page d’un contrôle slider.|  
|[CSliderCtrl::GetPos](#getpos)|Récupère la position actuelle du curseur.|  
|[CSliderCtrl::GetRange](#getrange)|Récupère les positions minimales et maximales pour un curseur.|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|Récupère la position maximale pour un curseur.|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|Récupère la position minimale pour un curseur.|  
|[CSliderCtrl::GetSelection](#getselection)|Récupère la plage de la sélection actuelle.|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|Récupère la longueur du curseur dans le contrôle de barre de suivi actuel.|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Récupère la taille du curseur de défilement du contrôle slider.|  
|[CSliderCtrl::GetTic](#gettic)|Récupère la position de la graduation spécifié.|  
|[CSliderCtrl::GetTicArray](#getticarray)|Récupère le tableau marque de positions de graduations pour un contrôle slider.|  
|[CSliderCtrl::GetTicPos](#getticpos)|Récupère la position de la graduation spécifié, en coordonnées clientes.|  
|[CSliderCtrl::GetToolTips](#gettooltips)|Récupère le handle du contrôle d’info-bulle assigné au contrôle slider, le cas échéant.|  
|[CSliderCtrl::SetBuddy](#setbuddy)|Affecte une fenêtre en tant que la fenêtre associée pour un curseur.|  
|[CSliderCtrl::SetLineSize](#setlinesize)|Définit la taille de ligne d’un contrôle slider.|  
|[CSliderCtrl::SetPageSize](#setpagesize)|Définit la taille de page d’un contrôle slider.|  
|[CSliderCtrl::SetPos](#setpos)|Définit la position actuelle du curseur.|  
|[CSliderCtrl::SetRange](#setrange)|Définit les positions minimales et maximales pour un curseur.|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|Définit la position maximale pour un curseur.|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|Définit la position minimale pour un curseur.|  
|[CSliderCtrl::SetSelection](#setselection)|Définit la plage de la sélection actuelle.|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|Définit la longueur du curseur dans le contrôle de barre de suivi actuel.|  
|[CSliderCtrl::SetTic](#settic)|Définit la position de la graduation spécifié.|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|Définit la fréquence des graduations par incrément de contrôle slider.|  
|[CSliderCtrl::SetTipSide](#settipside)|Positions un contrôle d’info-bulle utilisée par un contrôle de barre de suivi.|  
|[CSliderCtrl::SetToolTips](#settooltips)|Affecte un contrôle d’info-bulle à un contrôle de curseur.|  
  
## <a name="remarks"></a>Remarques  
 Un « contrôle slider » (également appelé barre de suivi) est une fenêtre qui contient un curseur et les coches facultatives. Lorsque l’utilisateur déplace le curseur, à l’aide de la souris ou les touches de direction, le contrôle envoie des messages de notification pour indiquer le changement.  
  
 Contrôles Slider sont utiles lorsque vous souhaitez que l’utilisateur de sélectionner une valeur discrète ou une série de valeurs consécutives dans une plage. Par exemple, vous pouvez utiliser un contrôle slider pour permettre à l’utilisateur de définir la fréquence de répétition du clavier en déplaçant le curseur jusqu'à une graduation donnée.  
  
 Ce contrôle (et par conséquent la `CSliderCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT version 3.51 et ultérieures.  
  
 Le curseur se déplace dans les incréments que vous spécifiez lors de sa création. Par exemple, si vous spécifiez que le curseur doit avoir une plage de cinq, le curseur peut occuper seulement six positions : une position située à gauche du contrôle slider et une position pour chaque incrément dans la plage. En règle générale, chacune de ces positions est identifiée par une graduation.  
  
 Création d’un curseur en utilisant le constructeur et le **créer** fonction membre de `CSliderCtrl`. Une fois que vous avez créé un contrôle slider, vous pouvez utiliser les fonctions membres dans `CSliderCtrl` pour modifier plusieurs de ses propriétés. Les modifications que vous pouvez effectuer incluent définissant les positions minimales et maximales pour le curseur, dessin des graduations, en définissant une plage de sélection et repositionnement du curseur.  
  
 Pour plus d’informations sur l’utilisation de `CSliderCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et [l’utilisation de CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="clearsel"></a>CSliderCtrl::ClearSel  
 Efface la sélection actuelle dans un contrôle de curseur.  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bRedraw`  
 Indicateur de renouvellement. Si ce paramètre est **TRUE**, le curseur est redessiné après l’effacement de la sélection ; sinon, le curseur n’est pas redessiné.  
  
##  <a name="cleartics"></a>CSliderCtrl::ClearTics  
 Supprime les marques de graduation actuelle à partir d’un contrôle slider.  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bRedraw`  
 Indicateur de renouvellement. Si ce paramètre est **TRUE**, le curseur est redessiné après les graduations sont désactivées ; sinon, le curseur n’est pas redessiné.  
  
##  <a name="create"></a>CSliderCtrl::Create  
 Crée un contrôle slider et l’attache à une `CSliderCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie le style du contrôle slider. Appliquer n’importe quelle combinaison de [styles du contrôle slider](http://msdn.microsoft.com/library/windows/desktop/bb760147), décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], au contrôle.  
  
 `rect`  
 Spécifie la taille et la position du curseur. Il peut être soit un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure.  
  
 `pParentWnd`  
 Spécifie les fenêtre du parent du contrôle slider, généralement un `CDialog`. Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID. du contrôle de curseur  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation a réussi ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Vous construisez un `CSliderCtrl` en deux étapes. Tout d’abord, appelez le constructeur, puis appelez **créer**, ce qui crée le contrôle slider et l’attache à le `CSliderCtrl` objet.  
  
 Selon les valeurs définies pour `dwStyle`, le contrôle slider peut avoir une orientation verticale ou horizontale. Il peut avoir des graduations d’un côté, les deux côtés, ou aucune des deux. Il peut également être utilisé pour spécifier une plage de valeurs consécutives.  
  
 Pour appliquer des styles de fenêtre étendus au contrôle de curseur, appelez [CreateEx](#createex) au lieu de **créer**.  
  
##  <a name="createex"></a>CSliderCtrl::CreateEx  
 Crée un contrôle (une fenêtre enfant) et l’associe à la `CSliderCtrl` objet.  
  
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
 Spécifie le style étendu du contrôle en cours de création. Pour obtenir la liste des styles étendus de Windows, consultez le `dwExStyle` paramètre [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Spécifie le style du contrôle slider. Appliquer n’importe quelle combinaison de [styles du contrôle slider](http://msdn.microsoft.com/library/windows/desktop/bb760147), décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], au contrôle.  
  
 `rect`  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure décrivant la taille et la position de la fenêtre doit être créée, dans les coordonnées clientes de `pParentWnd`.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parent du contrôle.  
  
 `nID`  
 ID de fenêtre enfant. du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Utilisez `CreateEx` au lieu de [créer](#create) pour appliquer des styles étendus Windows, spécifiés par la préface de style étendu Windows **WS_EX_**.  
  
##  <a name="csliderctrl"></a>CSliderCtrl::CSliderCtrl  
 Construit un objet `CSliderCtrl`.  
  
```  
CSliderCtrl();
```  
  
##  <a name="getbuddy"></a>CSliderCtrl::GetBuddy  
 Récupère le handle de fenêtre associée contrôle slider à un emplacement donné.  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `fLocation`  
 Valeur booléenne qui indique deux handles de fenêtre associée à récupérer. Peut avoir l'une des valeurs suivantes :  
  
- **TRUE** récupère le handle de l’ami à gauche du curseur. Si le contrôle slider utilise le `TBS_VERT` style, récupère le message l’ami au-dessus du curseur.  
  
- **FALSE** récupère le handle de l’ami à droite du curseur. Si le contrôle slider utilise le `TBS_VERT` style, récupère le message l’ami sous le curseur.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet de la fenêtre associée à l’emplacement spécifié par `fLocation`, ou **NULL** si aucune fenêtre associée n’existe à cet emplacement.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TBM_GETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760178), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Pour obtenir une description des styles de contrôle slider, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getchannelrect"></a>CSliderCtrl::GetChannelRect  
 Récupère la taille et la position du rectangle englobant pour les canaux d’un contrôle slider.  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lprc`  
 Un pointeur vers un [CRect](../../atl-mfc-shared/reference/crect-class.md) qui contient la taille et la position de la couche objet rectangle englobant lorsque la fonction retourne une valeur.  
  
### <a name="remarks"></a>Remarques  
 Le canal est la zone sur lequel le curseur se déplace et qui contient la mise en surbrillance lorsqu’une plage est sélectionnée.  
  
##  <a name="getlinesize"></a>CSliderCtrl::GetLineSize  
 Récupère la taille de la ligne d’un contrôle slider.  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille d’une ligne pour le contrôle de curseur.  
  
### <a name="remarks"></a>Remarques  
 La taille de ligne affecte la quantité le curseur se déplace pour la **TB_LINEUP** et **quel** des notifications. Le paramètre par défaut pour la taille de ligne est 1.  
  
##  <a name="getnumtics"></a>CSliderCtrl::GetNumTics  
 Récupère le nombre de graduations dans un contrôle de curseur.  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de graduations dans le contrôle de curseur.  
  
##  <a name="getpagesize"></a>CSliderCtrl::GetPageSize  
 Récupère la taille de la page d’un contrôle slider.  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille d’une page pour le contrôle de curseur.  
  
### <a name="remarks"></a>Notes  
 La taille de page affecte la quantité le curseur se déplace pour la **TB_PAGEUP** et **TB_PAGEDOWN** des notifications.  
  
##  <a name="getpos"></a>CSliderCtrl::GetPos  
 Récupère la position actuelle du curseur dans un contrôle de curseur.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Position actuelle.  
  
##  <a name="getrange"></a>CSliderCtrl::GetRange  
 Récupère les positions minimum et maximum pour le curseur dans un contrôle de curseur.  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nMin`  
 Référence à un entier qui reçoit la position minimale.  
  
 `nMax`  
 Référence à un entier qui reçoit la position maximale.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction copie les valeurs dans les nombres entiers référencés par `nMin` et `nMax`.  
  
##  <a name="getrangemax"></a>CSliderCtrl::GetRangeMax  
 Récupère la position maximale du curseur dans un contrôle de curseur.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Position maximale du contrôle.  
  
##  <a name="getrangemin"></a>CSliderCtrl::GetRangeMin  
 Récupère la position minimale du curseur dans un contrôle de curseur.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Position minimale du contrôle.  
  
##  <a name="getselection"></a>CSliderCtrl::GetSelection  
 Récupère les positions de début et de fin de la sélection actuelle dans un contrôle de curseur.  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nMin`  
 Référence à un entier qui reçoit la position de départ de la sélection actuelle.  
  
 `nMax`  
 Référence à un entier qui reçoit la position de fin de la sélection actuelle.  
  
##  <a name="getthumblength"></a>CSliderCtrl::GetThumbLength  
 Récupère la longueur du curseur dans le contrôle de barre de suivi actuel.  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur du curseur, en pixels.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [TBM_GETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760201) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getthumbrect"></a>CSliderCtrl::GetThumbRect  
 Récupère la taille et la position du rectangle englobant pour le slider (curseur) dans un contrôle de curseur.  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lprc`  
 Un pointeur vers un `CRect` objet qui contient le rectangle englobant du curseur lorsque la fonction retourne une valeur.  
  
##  <a name="gettic"></a>CSliderCtrl::GetTic  
 Récupère la position d’une graduation dans un contrôle de curseur.  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nTic`  
 Index de base zéro identifiant une graduation.  
  
### <a name="return-value"></a>Valeur de retour  
 La position de la graduation spécifié ou -1 si `nTic` ne spécifie pas un index valide.  
  
##  <a name="getticarray"></a>CSliderCtrl::GetTicArray  
 Récupère l’adresse du tableau qui contient les positions des graduations pour un contrôle slider.  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’adresse du tableau qui contient les positions de marque de graduation pour le contrôle de curseur.  
  
##  <a name="getticpos"></a>CSliderCtrl::GetTicPos  
 Récupère la position physique actuelle d’une graduation dans un contrôle de curseur.  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nTic`  
 Index de base zéro identifiant une graduation.  
  
### <a name="return-value"></a>Valeur de retour  
 La position physique, en coordonnées clientes, de la graduation spécifié ou -1 si `nTic` ne spécifie pas un index valide.  
  
##  <a name="gettooltips"></a>CSliderCtrl::GetToolTips  
 Récupère le handle du contrôle d’info-bulle assigné au contrôle slider, le cas échéant.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) objet, ou **NULL** si les info-bulles ne sont pas en cours d’utilisation. Si le contrôle slider n’utilise pas le **TBS_TOOLTIPS** style, la valeur de retour est **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TBM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760209), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Notez que cette fonction membre retourne un `CToolTipCtrl` objet au lieu d’un handle à un contrôle.  
  
 Pour obtenir une description des styles de contrôle slider, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setbuddy"></a>CSliderCtrl::SetBuddy  
 Affecte une fenêtre en tant que la fenêtre associée pour un curseur.  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWndBuddy`  
 Un pointeur vers un `CWnd` objet est défini comme les contacts du contrôle slider.  
  
 `fLocation`  
 Valeur qui spécifie l’emplacement d’affichage de la fenêtre associée. Cette valeur peut être une des opérations suivantes :  
  
- **TRUE** l’ami apparaît à gauche de la barre de suivi si le contrôle de barre de suivi utilise le `TBS_HORZ` style. Si la barre de suivi utilise le `TBS_VERT` de style, les contacts s’affiche au-dessus du contrôle trackbar.  
  
- **FALSE** l’ami s’affiche à droite de la barre de suivi si le contrôle de barre de suivi utilise le `TBS_HORZ` style. Si la barre de suivi utilise le `TBS_VERT` de style, les contacts s’affiche au-dessous du contrôle trackbar.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet qui a été précédemment affecté au contrôle de curseur à cet emplacement.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TBM_SETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760213), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Notez que cette fonction membre utilise des pointeurs vers `CWnd` objets, plutôt que les handles de fenêtre pour sa valeur de retour et le paramètre.  
  
 Pour obtenir une description des styles de contrôle slider, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setlinesize"></a>CSliderCtrl::SetLineSize  
 Définit la taille de la ligne d’un contrôle slider.  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>Paramètres  
 `nSize`  
 La nouvelle taille de ligne du curseur.  
  
### <a name="return-value"></a>Valeur de retour  
 La taille de la ligne précédente.  
  
### <a name="remarks"></a>Remarques  
 La taille de ligne affecte la quantité le curseur se déplace pour la **TB_LINEUP** et **quel** des notifications.  
  
##  <a name="setpagesize"></a>CSliderCtrl::SetPageSize  
 Définit la taille de la page d’un contrôle slider.  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>Paramètres  
 `nSize`  
 La nouvelle taille de page du contrôle slider.  
  
### <a name="return-value"></a>Valeur de retour  
 La taille de page précédente.  
  
### <a name="remarks"></a>Notes  
 La taille de page affecte la quantité le curseur se déplace pour la **TB_PAGEUP** et **TB_PAGEDOWN** des notifications.  
  
##  <a name="setpos"></a>CSliderCtrl::SetPos  
 Définit la position actuelle du curseur dans un contrôle de curseur.  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>Paramètres  
 `nPos`  
 Spécifie la nouvelle position du curseur.  
  
##  <a name="setrange"></a>CSliderCtrl::SetRange  
 Définit la plage (positions minimum et maximum) pour le curseur dans un contrôle de curseur.  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nMin`  
 Position minimale du curseur.  
  
 `nMax`  
 Position maximale du curseur.  
  
 `bRedraw`  
 L’indicateur de renouvellement. Si ce paramètre est **TRUE**, le curseur est redessiné après la plage définie ; sinon, le curseur n’est pas redessiné.  
  
##  <a name="setrangemax"></a>CSliderCtrl::SetRangeMax  
 Définit la durée maximale pour le curseur dans un contrôle de curseur.  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nMax`  
 Position maximale du curseur.  
  
 `bRedraw`  
 L’indicateur de renouvellement. Si ce paramètre est **TRUE**, le curseur est redessiné après la plage définie ; sinon, le curseur n’est pas redessiné.  
  
##  <a name="setrangemin"></a>CSliderCtrl::SetRangeMin  
 Définit la plage minimale pour le curseur dans un contrôle de curseur.  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nMin`  
 Position minimale du curseur.  
  
 `bRedraw`  
 L’indicateur de renouvellement. Si ce paramètre est **TRUE**, le curseur est redessiné après la plage définie ; sinon, le curseur n’est pas redessiné.  
  
##  <a name="setselection"></a>CSliderCtrl::SetSelection  
 Définit les positions de début et de fin pour la sélection actuelle dans un contrôle de curseur.  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Paramètres  
 `nMin`  
 Position de départ pour le curseur.  
  
 `nMax`  
 Position de fin du curseur.  
  
##  <a name="setthumblength"></a>CSliderCtrl::SetThumbLength  
 Définit la longueur du curseur dans le contrôle de barre de suivi actuel.  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `nLength`|Longueur du curseur, en pixels.|  
  
### <a name="remarks"></a>Remarques  
 Cette méthode requiert que le contrôle trackbar valeur [TBS_FIXEDLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760147) style.  
  
 Cette méthode envoie le [TBM_SETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760234) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_sliderCtrl`, qui est utilisé pour accéder au contrôle de barre de suivi actuel. L’exemple définit également une variable, `thumbLength`, qui est utilisé pour stocker la longueur par défaut du composant de curseur de défilement du contrôle trackbar. Ces variables sont utilisées dans l’exemple suivant.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1 n °&1;](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit le composant de curseur de défilement du contrôle trackbar à deux fois sa longueur par défaut.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1 n °&2;](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="settic"></a>CSliderCtrl::SetTic  
 Définit la position d’une graduation dans un contrôle de curseur.  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>Paramètres  
 `nTic`  
 Position de la graduation. Ce paramètre doit spécifier une valeur positive.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la graduation est définie ; sinon 0.  
  
##  <a name="setticfreq"></a>CSliderCtrl::SetTicFreq  
 Définit la fréquence avec les graduations marques sont affichés dans un curseur.  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>Paramètres  
 *nFreq*  
 Fréquence des graduations.  
  
### <a name="remarks"></a>Remarques  
 Par exemple, si la fréquence est définie sur 2, une graduation s’affiche pour chaque autre référence de plage du composant. Le paramètre par défaut pour la fréquence est 1 (autrement dit, chaque incrément dans la plage est associé à une graduation).  
  
 Vous devez créer le contrôle avec la `TBS_AUTOTICKS` style à utiliser cette fonction. Pour plus d’informations, consultez [CSliderCtrl::Create](#create).  
  
##  <a name="settipside"></a>CSliderCtrl::SetTipSide  
 Positions un contrôle d’info-bulle utilisée par un contrôle de barre de suivi.  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>Paramètres  
 `nLocation`  
 Valeur qui représente l’emplacement d’affichage du contrôle d’info-bulle. Pour obtenir la liste des valeurs possibles, consultez le message Win32 [TBM_SETTIPSIDE](http://msdn.microsoft.com/library/windows/desktop/bb760240), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur qui représente l’emplacement précédent du contrôle d’info-bulle. La valeur de retour correspond à l’une des valeurs possibles pour `nLocation`.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 **TBM_SETTIPSIDE**, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Curseur de contrôles qui utilisent la **TBS_TOOLTIPS** style d’affichage des info-bulles. Pour obtenir une description des styles de contrôle slider, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans les [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
##  <a name="settooltips"></a>CSliderCtrl::SetToolTips  
 Affecte un contrôle d’info-bulle à un contrôle de curseur.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWndTip`  
 Un pointeur vers un [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) objet contenant les info-bulles à utiliser avec le contrôle slider.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TBM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760242), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Lorsqu’un contrôle slider est créé avec le **TBS_TOOLTIPS** style, il crée un contrôle d’info-bulle par défaut qui s’affiche à côté du curseur, affichage de la position du curseur en cours. Pour obtenir une description des styles de contrôle slider, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans les [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [MFC exemple CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl (classe)](../../mfc/reference/cprogressctrl-class.md)

