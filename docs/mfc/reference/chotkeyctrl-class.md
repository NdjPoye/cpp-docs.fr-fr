---
title: CHotKeyCtrl (classe) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 590914ac312a4f998eb759beb08ed2e7935874fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl (classe)
Fournit les fonctionnalités du contrôle commun de touche d'accès rapide Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Construit un objet `CHotKeyCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|Crée un contrôle de touche d’accès rapide et l’attache à un `CHotKeyCtrl` objet.|  
|[CHotKeyCtrl::CreateEx](#createex)|Crée un contrôle de touche d’accès rapide avec les styles étendus Windows spécifiés et l’attache à un `CHotKeyCtrl` objet.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Récupère les indicateurs clés virtuels code et le modificateur d’une touche d’accès rapide à partir d’un contrôle de touche d’accès rapide.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Récupère le nom de clé dans le jeu de caractères local, affecté à une touche d’accès rapide.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Récupère le nom de clé dans le jeu de caractères local attribué pour le code de touche virtuelle spécifié.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Définit les touches d’accès rapide pour un contrôle de touche d’accès rapide.|  
|[CHotKeyCtrl::SetRules](#setrules)|Définit les combinaisons non valides et la combinaison du modificateur par défaut pour un contrôle de touche d’accès rapide.|  
  
## <a name="remarks"></a>Notes  
 Un « contrôle de clé à chaud » est une fenêtre qui permet à l’utilisateur créer une touche d’accès rapide. Une « touche d’accès rapide » est une combinaison de clés que l’utilisateur peut sélectionner pour exécuter une action rapidement. (Par exemple, un utilisateur peut créer un raccourci clavier qui active une fenêtre donnée et la remet en vers le haut de l’ordre de plan.) Le contrôle de touche à chaud affiche les choix de l’utilisateur et garantit que l’utilisateur sélectionne une combinaison de touches valide.  
  
 Ce contrôle (et par conséquent la `CHotKeyCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT version 3.51 et ultérieures.  
  
 Lorsque l’utilisateur a choisi une combinaison de touches, l’application peut récupérer la combinaison de touches spécifiée du contrôle et utiliser le **message WM_SETHOTKEY** message pour configurer la touche d’accès rapide dans le système. Chaque fois que l’utilisateur appuie sur la touche d’accès rapide par la suite, à partir de n’importe quelle partie du système, la fenêtre spécifiée dans le **message WM_SETHOTKEY** message reçoit une `WM_SYSCOMMAND` message spécifiant **SC_HOTKEY**. Ce message Active la fenêtre qui le reçoit. Le raccourci clavier reste valid jusqu'à ce que l’application qui a appelé **message WM_SETHOTKEY** se termine.  
  
 Ce mécanisme est différent de la prise en charge clé à chaud dont dépend le **WM_HOTKEY** message et les fenêtres [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) et [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) fonctions.  
  
 Pour plus d’informations sur l’utilisation de `CHotKeyCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et [à l’aide de CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="chotkeyctrl"></a>  CHotKeyCtrl::CHotKeyCtrl  
 Construit un objet `CHotKeyCtrl`.  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="create"></a>  CHotKeyCtrl::Create  
 Crée un contrôle de touche d’accès rapide et l’attache à un `CHotKeyCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie le style du contrôle de clé à chaud. Appliquer n’importe quelle combinaison de styles de contrôle. Consultez [des Styles de contrôle courants](http://msdn.microsoft.com/library/windows/desktop/bb775498) dans le SDK Windows pour plus d’informations.  
  
 `rect`  
 Spécifie la taille et la position du contrôle de clé à chaud. Il peut être soit un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [Rect, structure](../../mfc/reference/rect-structure1.md).  
  
 `pParentWnd`  
 Spécifie l’à chaud clé fenêtre du contrôle parent, généralement un [CDialog](../../mfc/reference/cdialog-class.md). Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID. du contrôle de clé à chaud  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro, si l’initialisation a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Vous construisez un `CHotKeyCtrl` objet en deux étapes. Tout d’abord, appelez le constructeur, puis **créer**, qui crée le contrôle de touche à chaud et l’attache à le `CHotKeyCtrl` objet.  
  
 Si vous souhaitez utiliser les styles étendus windows avec votre contrôle, appelez [CreateEx](#createex) au lieu de **créer**.  
  
##  <a name="createex"></a>  CHotKeyCtrl::CreateEx  
 Appelez cette fonction pour créer un contrôle (une fenêtre enfant) et y associer la `CHotKeyCtrl` objet.  
  
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
 Spécifie le style étendu du contrôle en cours de création. Pour obtenir la liste des styles étendus de Windows, consultez le `dwExStyle` paramètre [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans le Kit de développement logiciel Windows.  
  
 `dwStyle`  
 Spécifie le style du contrôle de clé à chaud. Appliquer n’importe quelle combinaison de styles de contrôle. Pour plus d’informations, consultez [des Styles de contrôle courants](http://msdn.microsoft.com/library/windows/desktop/bb775498) dans le Kit de développement logiciel Windows.  
  
 `rect`  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure décrivant la taille et la position de la fenêtre doit être créée, en coordonnées clientes de `pParentWnd`.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre qui est le parent du contrôle.  
  
 `nID`  
 ID de fenêtre enfant. du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Utilisez `CreateEx` au lieu de [créer](#create) pour appliquer des styles étendus Windows spécifiés par la préface style étendu de Windows **WS_EX_**.  
  
##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey  
 Récupère les indicateurs clés virtuels code et le modificateur d’un raccourci clavier à partir d’un contrôle de touche d’accès rapide.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `wVirtualKeyCode`  
 Code de touche virtuelle du raccourci clavier. Pour obtenir la liste de codes de touches virtuelles, consultez Winuser.h.  
  
 [out] `wModifiers`  
 Une combinaison (OR) au niveau du bit des indicateurs qui indiquent les touches de modification dans le raccourci clavier.  
  
 Les indicateurs de modificateur sont les suivantes :  
  
|Indicateur|Clé correspondante|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|touche ALT|  
|`HOTKEYF_CONTROL`|Touche CTRL ENFONCÉE|  
|`HOTKEYF_EXT`|Clé étendue|  
|`HOTKEYF_SHIFT`|Touche MAJ enfoncée|  
  
### <a name="return-value"></a>Valeur de retour  
 Dans la première méthode surchargée, un `DWORD` qui contient les indicateurs de code et le modificateur clés virtuelles. L’octet de poids faible du mot de poids faible contient le code de touche virtuelle, l’octet de poids fort du mot de poids faible contient les indicateurs de modificateur, et le mot de poids fort est égale à zéro.  
  
### <a name="remarks"></a>Notes  
 Le code de touche virtuelle et les touches de modification ensemble définissent le raccourci clavier.  
  
##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName  
 Appelez cette fonction membre pour obtenir le nom localisé de la touche d’accès rapide.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom localisé de la touche d’accès rapide actuellement sélectionné. S’il n’existe aucune touche d’accès rapide sélectionné, `GetHotKeyName` retourne une chaîne vide.  
  
### <a name="remarks"></a>Notes  
 Le nom de cette fonction membre retourne provient le pilote du clavier. Vous pouvez installer un pilote non localisé de clavier dans une version localisée de Windows et vice versa.  
  
##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName  
 Appelez cette fonction membre pour obtenir le nom localisé de la clé attribué à un code de touche virtuelle spécifié.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>Paramètres  
 `vk`  
 Le code de touche virtuelle.  
  
 *fExtended*  
 Si le code de touche virtuelle est une clé étendue, **TRUE**; sinon **FALSE**.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom localisé de la clé spécifiée par le `vk` paramètre. Si la clé ne possède pas de nom mappé, `GetKeyName` retourne une chaîne vide.  
  
### <a name="remarks"></a>Notes  
 Cette fonction retourne le nom de clé provient le pilote du clavier, vous pouvez installer un pilote non localisé de clavier dans une version localisée de Windows et vice versa.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>  CHotKeyCtrl::SetHotKey  
 Définit le raccourci clavier pour un contrôle de touche d’accès rapide.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `wVirtualKeyCode`  
 Code de touche virtuelle du raccourci clavier. Pour obtenir la liste de codes de touches virtuelles, consultez Winuser.h.  
  
 [in] `wModifiers`  
 Une combinaison (OR) au niveau du bit des indicateurs qui indiquent les touches de modification dans le raccourci clavier.  
  
 Les indicateurs de modificateur sont les suivantes :  
  
|Indicateur|Clé correspondante|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|touche ALT|  
|`HOTKEYF_CONTROL`|Touche CTRL ENFONCÉE|  
|`HOTKEYF_EXT`|Clé étendue|  
|`HOTKEYF_SHIFT`|Touche MAJ enfoncée|  
  
### <a name="remarks"></a>Notes  
 Le code de touche virtuelle et les touches de modification ensemble définissent le raccourci clavier.  
  
##  <a name="setrules"></a>  CHotKeyCtrl::SetRules  
 Appelez cette fonction pour définir les combinaisons non valides et la combinaison du modificateur par défaut pour un contrôle de touche d’accès rapide.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Paramètres  
 `wInvalidComb`  
 Tableau d’indicateurs qui spécifie des combinaisons de clé non valides. Il peut être une combinaison des valeurs suivantes :  
  
- `HKCOMB_A` ALT  
  
- `HKCOMB_C` CTRL  
  
- `HKCOMB_CA` CTRL + ALT  
  
- `HKCOMB_NONE` Clés non modifiés  
  
- `HKCOMB_S` TOUCHE MAJ ENFONCÉE  
  
- `HKCOMB_SA` MAJ + ALT  
  
- `HKCOMB_SC` MAJ + CTRL  
  
- `HKCOMB_SCA` MAJ + CTRL + ALT  
  
 `wModifiers`  
 Tableau d’indicateurs qui spécifie la combinaison de touches à utiliser lorsque l’utilisateur entre une combinaison non valide. Pour plus d’informations sur les indicateurs de modificateur, consultez [GetHotKey](#gethotkey).  
  
### <a name="remarks"></a>Notes  
 Lorsqu’un utilisateur entre une combinaison de clé non valide, tel que défini par les indicateurs spécifiés dans `wInvalidComb`, le système utilise l’opérateur OR pour combiner les touches entrées par l’utilisateur avec les indicateurs spécifiés dans `wModifiers`. La combinaison de touches qui en résulte est convertie en une chaîne, puis affichée dans le contrôle de touche à chaud.  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)



