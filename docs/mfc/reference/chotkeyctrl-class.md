---
title: CHotKeyCtrl (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- hot key controls
- CHotKeyCtrl class
- Windows common controls [C++], CHotKeyCtrl
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cbcc720d2b934cde9f8beb9bb95499d9cc569413
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

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
|[CHotKeyCtrl::Create](#create)|Crée un contrôle de touche d’accès rapide et l’attache à une `CHotKeyCtrl` objet.|  
|[CHotKeyCtrl::CreateEx](#createex)|Crée un contrôle de touche d’accès rapide avec les styles étendus Windows spécifiés et l’attache à une `CHotKeyCtrl` objet.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Récupère les indicateurs clés virtuels code et le modificateur de touche d’accès rapide à partir d’un contrôle de touche d’accès rapide.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Récupère le nom de clé dans le jeu de caractères local affecté à une touche d’accès rapide.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Récupère le nom de clé dans le jeu de caractères local attribué au code de clé virtuel spécifié.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Définit les touches d’accès rapide pour un contrôle de touche d’accès rapide.|  
|[CHotKeyCtrl::SetRules](#setrules)|Définit les combinaisons non valides et la combinaison de modificateur par défaut pour un contrôle de touche d’accès rapide.|  
  
## <a name="remarks"></a>Remarques  
 Un « contrôle de clé à chaud » est une fenêtre qui permet à l’utilisateur créer une touche d’accès rapide. Une « touche d’accès rapide » est une combinaison de touches que l’utilisateur peut sélectionner pour exécuter une action rapidement. (Par exemple, un utilisateur peut créer une touche de raccourci qui active une fenêtre donnée et le rend au début de l’ordre de plan.) Contrôle de touche d’accès rapide affiche un choix de l’utilisateur et s’assure que l’utilisateur sélectionne une combinaison de touches valide.  
  
 Ce contrôle (et par conséquent la `CHotKeyCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT version 3.51 et ultérieures.  
  
 Lorsque l’utilisateur a choisi une combinaison de touches, l’application peut récupérer la combinaison de touches spécifiée du contrôle et utiliser le **message WM_SETHOTKEY** message pour configurer la touche d’accès rapide dans le système. Chaque fois que l’utilisateur appuie sur la touche d’accès rapide par la suite, une partie du système, la fenêtre spécifiée dans le **message WM_SETHOTKEY** message reçoit une `WM_SYSCOMMAND` message spécifiant **SC_HOTKEY**. Ce message Active la fenêtre qui le reçoit. Le raccourci clavier reste valid jusqu'à ce que l’application ayant appelé **message WM_SETHOTKEY** se ferme.  
  
 Ce mécanisme est différent de la prise en charge clé à chaud dont dépend le **WM_HOTKEY** message et les fenêtres [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) et [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) fonctions.  
  
 Pour plus d’informations sur l’utilisation de `CHotKeyCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et [l’utilisation de CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="chotkeyctrl"></a>CHotKeyCtrl::CHotKeyCtrl  
 Construit un objet `CHotKeyCtrl`.  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="create"></a>CHotKeyCtrl::Create  
 Crée un contrôle de touche d’accès rapide et l’attache à une `CHotKeyCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie le style du contrôle de clé à chaud. Appliquer n’importe quelle combinaison de styles de contrôle. Consultez la page [des Styles de contrôle commun](http://msdn.microsoft.com/library/windows/desktop/bb775498) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations.  
  
 `rect`  
 Spécifie la taille et la position du contrôle de clé à chaud. Il peut être soit un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [Rect, structure](../../mfc/reference/rect-structure1.md).  
  
 `pParentWnd`  
 Spécifie les fenêtre du parent du contrôle de clé à chaud, généralement un [CDialog](../../mfc/reference/cdialog-class.md). Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID. du contrôle de clé à chaud  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro, si l’initialisation a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Vous construisez un `CHotKeyCtrl` objet en deux étapes. Tout d’abord, appelez le constructeur, puis **créer**, qui crée le contrôle de touche d’accès rapide et l’attache à le `CHotKeyCtrl` objet.  
  
 Si vous souhaitez utiliser les styles étendus windows avec votre contrôle, appelez [CreateEx](#createex) au lieu de **créer**.  
  
##  <a name="createex"></a>CHotKeyCtrl::CreateEx  
 Appelez cette fonction pour créer un contrôle (une fenêtre enfant) et y associer le `CHotKeyCtrl` objet.  
  
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
 Spécifie le style du contrôle de clé à chaud. Appliquer n’importe quelle combinaison de styles de contrôle. Pour plus d’informations, consultez [des Styles de contrôle commun](http://msdn.microsoft.com/library/windows/desktop/bb775498) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
##  <a name="gethotkey"></a>CHotKeyCtrl::GetHotKey  
 Récupère les indicateurs clés virtuels code et le modificateur d’un raccourci clavier à partir d’un contrôle de touche d’accès rapide.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `wVirtualKeyCode`  
 Code de touche virtuelle du raccourci clavier. Pour une liste des codes de touches virtuels standards, consultez Winuser.h.  
  
 [out] `wModifiers`  
 Combinaison de bits (OR) d’indicateurs qui indiquent les touches de modification dans le raccourci clavier.  
  
 Les indicateurs de modificateur sont les suivantes :  
  
|Indicateur|Clé correspondante|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|touche ALT|  
|`HOTKEYF_CONTROL`|Touche CTRL|  
|`HOTKEYF_EXT`|Clé étendue|  
|`HOTKEYF_SHIFT`|Touche MAJ.|  
  
### <a name="return-value"></a>Valeur de retour  
 Dans la première méthode surchargée, une `DWORD` qui contient les indicateurs de code et le modificateur clés virtuels. L’octet de poids faible du mot de poids faible contient le code de touche virtuel, l’octet de poids fort du mot de poids faible contient les indicateurs de modificateur et le mot de poids fort est égal à zéro.  
  
### <a name="remarks"></a>Notes  
 Le code de touche virtuelle et les touches de modification ensemble définissent le raccourci clavier.  
  
##  <a name="gethotkeyname"></a>CHotKeyCtrl::GetHotKeyName  
 Appelez cette fonction membre pour obtenir le nom localisé de la touche d’accès rapide.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom localisé de la touche de raccourci actuellement sélectionné. S’il n’existe aucune clé sélectionnée à chaud, `GetHotKeyName` renvoie une chaîne vide.  
  
### <a name="remarks"></a>Remarques  
 Le nom de cette fonction membre retourne provient le pilote du clavier. Vous pouvez installer un pilote de clavier localisée dans une version localisée de Windows et vice versa.  
  
##  <a name="getkeyname"></a>CHotKeyCtrl::GetKeyName  
 Appelez cette fonction membre pour obtenir le nom localisé de la clé attribué à un code de touche virtuel spécifié.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>Paramètres  
 `vk`  
 Le code de touche virtuelle.  
  
 *fExtended*  
 Si le code de touche virtuelle est une étendue **TRUE**; sinon **FALSE**.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom localisé de la clé spécifiée par le `vk` paramètre. Si la clé n’a aucun nom mappé, `GetKeyName` renvoie une chaîne vide.  
  
### <a name="remarks"></a>Notes  
 Le nom de la clé retournée par cette fonction provient le pilote du clavier, vous pouvez installer un pilote de clavier localisée dans une version localisée de Windows et vice versa.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#69;](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>CHotKeyCtrl::SetHotKey  
 Définit le raccourci clavier pour un contrôle de touche d’accès rapide.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `wVirtualKeyCode`  
 Code de touche virtuelle du raccourci clavier. Pour une liste des codes de touches virtuels standards, consultez Winuser.h.  
  
 [in] `wModifiers`  
 Combinaison de bits (OR) d’indicateurs qui indiquent les touches de modification dans le raccourci clavier.  
  
 Les indicateurs de modificateur sont les suivantes :  
  
|Indicateur|Clé correspondante|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|touche ALT|  
|`HOTKEYF_CONTROL`|Touche CTRL|  
|`HOTKEYF_EXT`|Clé étendue|  
|`HOTKEYF_SHIFT`|Touche MAJ.|  
  
### <a name="remarks"></a>Remarques  
 Le code de touche virtuelle et les touches de modification ensemble définissent le raccourci clavier.  
  
##  <a name="setrules"></a>CHotKeyCtrl::SetRules  
 Appelez cette fonction pour définir les combinaisons non valides et la combinaison de modificateur par défaut pour un contrôle de touche d’accès rapide.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Paramètres  
 `wInvalidComb`  
 Tableau d’indicateurs qui spécifie des combinaisons de clé non valides. Il peut être une combinaison des valeurs suivantes :  
  
- `HKCOMB_A`ALT  
  
- `HKCOMB_C`CTRL  
  
- `HKCOMB_CA`CTRL + ALT  
  
- `HKCOMB_NONE`Clés non modifiés  
  
- `HKCOMB_S`MAJ  
  
- `HKCOMB_SA`MAJ + ALT  
  
- `HKCOMB_SC`MAJ + CTRL  
  
- `HKCOMB_SCA`CTRL + MAJ + ALT  
  
 `wModifiers`  
 Tableau d’indicateurs qui spécifie la combinaison de touches à utiliser lorsque l’utilisateur entre une combinaison non valide. Pour plus d’informations sur les indicateurs de modificateur, consultez [GetHotKey](#gethotkey).  
  
### <a name="remarks"></a>Notes  
 Lorsqu’un utilisateur entre une combinaison de clé non valide, tel que défini par les indicateurs spécifiés dans `wInvalidComb`, le système utilise l’opérateur OR pour combiner les touches entrées par l’utilisateur avec les indicateurs spécifiés dans `wModifiers`. La combinaison de touches qui en résulte est convertie en chaîne, puis affichée dans le contrôle de touche d’accès rapide.  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




