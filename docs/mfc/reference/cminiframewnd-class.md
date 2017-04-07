---
title: Classe de CMiniFrameWnd | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
dev_langs:
- C++
helpviewer_keywords:
- CMiniFrameWnd class
- mini-frame windows
- toolbars [C++]
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
caps.latest.revision: 21
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
ms.openlocfilehash: 1229f5405c9eeb90abcdc54108ed26e28d94f0e0
ms.lasthandoff: 02/24/2017

---
# <a name="cminiframewnd-class"></a>Classe de CMiniFrameWnd
Représente une fenêtre frame de demi-hauteur généralement visible autour de barres d'outils flottantes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Construit un objet `CMiniFrameWnd`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMiniFrameWnd::Create](#create)|Crée un `CMiniFrameWnd` objet après la construction.|  
|[CMiniFrameWnd::CreateEx](#createex)|Crée un `CMiniFrameWnd` objet (avec des options supplémentaires) après la construction.|  
  
## <a name="remarks"></a>Remarques  
 Ces fenêtres mini-frame se comportent comme windows normale, sauf qu’ils n’ont pas de boutons Réduire/agrandir ou menus et vous suffit de cliquer sur le menu système pour fermer les.  
  
 Pour utiliser un `CMiniFrameWnd` d’objet, tout d’abord définir l’objet. Appelez ensuite la [créer](#create) fonction membre pour afficher la fenêtre mini-frame.  
  
 Pour plus d’informations sur l’utilisation de `CMiniFrameWnd` , consultez l’article [ancrées et des barres d’outils flottantes](../../mfc/docking-and-floating-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="cminiframewnd"></a>CMiniFrameWnd::CMiniFrameWnd  
 Construit un `CMiniFrameWnd` de l’objet, mais ne crée pas de la fenêtre.  
  
```  
CMiniFrameWnd();
```  
  
### <a name="remarks"></a>Remarques  
 Pour créer la fenêtre, appelez [CMiniFrameWnd::Create](#create).  
  
##  <a name="create"></a>CMiniFrameWnd::Create  
 Crée la fenêtre mini-frame Windows et l’attache à le `CMiniFrameWnd` objet.  
  
```  
virtual BOOL Create(
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpClassName`  
 Pointe vers une chaîne de caractères se terminant par null qui nomme la classe Windows. Le nom de classe peut être n’importe quel nom inscrit avec global [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) (fonction). Si **NULL**, la classe de fenêtre sera inscrit pour vous par l’infrastructure. MFC fournit la classe par défaut, les styles et les attributs suivants :  
  
-   Définit les bits de style **CS_DBLCLKS**, qui envoie des messages à la procédure de fenêtre double lorsque l’utilisateur double-clique sur la souris.  
  
-   Définit les bits de style **CS_HREDRAW** et **CS_VREDRAW**, lequel diriger le contenu de la zone cliente est redessiné lorsque la fenêtre change de taille.  
  
-   Définit le curseur de la classe à la norme Windows **IDC_ARROW**.  
  
-   Définit le pinceau d’arrière-plan classe **NULL**, de sorte que la fenêtre n’efface pas son arrière-plan.  
  
-   Définit l’icône de classe pour l’icône du logo Windows standard, de drapeau flottant.  
  
-   Définit la fenêtre à la taille par défaut et la position, comme indiqué par Windows.  
  
 `lpWindowName`  
 Pointe vers une chaîne de caractères terminée par le caractère null qui contient le nom de la fenêtre.  
  
 `dwStyle`  
 Spécifie les attributs de style de fenêtre. Ceux-ci peuvent inclure des styles de fenêtre standard et un ou plusieurs des styles spéciaux suivants :  
  
- **MFS_MOVEFRAME** autorise à déplacer en cliquant sur le bord de la fenêtre, pas seulement la légende de la fenêtre mini-frame.  
  
- **MFS_4THICKFRAME** désactive le redimensionnement de la fenêtre mini-frame.  
  
- **MFS_SYNCACTIVE** synchronise l’activation de la fenêtre mini-frame à l’activation de la fenêtre parente.  
  
- **MFS_THICKFRAME** autorise taille petite autorise le contenu de la zone cliente de la fenêtre mini-frame.  
  
- **MFS_BLOCKSYSMENU** désactive l’accès au menu système et le menu de contrôle et les convertit en partie de la légende (barre de titre).  
  
 Consultez la page [CWnd::Create](../../mfc/reference/cwnd-class.md#create) pour obtenir une description des valeurs de style de fenêtre possible. La combinaison classique utilisée pour les fenêtres mini-frame est **WS_POPUP | WS_CAPTION | WS_SYSMENU**.  
  
 `rect`  
 Un `RECT` structure qui spécifie les dimensions de la fenêtre de votre choisies.  
  
 `pParentWnd`  
 Pointe vers la fenêtre parente. Utilisez **NULL** pour les fenêtres de niveau supérieur.  
  
 `nID`  
 Si la fenêtre mini-frame est créée en tant que fenêtre enfant, il s’agit de l’identificateur du contrôle enfant ; sinon 0.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 **Créer** initialise le nom de classe et le nom de la fenêtre de la fenêtre et enregistre les valeurs par défaut pour le style et le parent.  
  
##  <a name="createex"></a>CMiniFrameWnd::CreateEx  
 Crée un objet `CMiniFrameWnd`.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwExStyle`  
 Spécifie le style étendu de la `CMiniFrameWnd` en cours de création. Appliquer de la [les styles de fenêtre étendus](../../mfc/reference/extended-window-styles.md) à la fenêtre.  
  
 `lpClassName`  
 Pointe vers une chaîne de caractères se terminant par null qui nomme la classe Windows (un [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure). Le nom de classe peut être n’importe quel nom inscrit avec global [AfxRegisterWndClass](http://msdn.microsoft.com/library/62c7d4b1-7a29-4abb-86f7-dec541659db0) fonction ou les noms de classe de contrôle prédéfini. Il ne doit pas être **NULL**.  
  
 `lpWindowName`  
 Pointe vers une chaîne de caractères terminée par le caractère null qui contient le nom de la fenêtre.  
  
 `dwStyle`  
 Spécifie les attributs de style de fenêtre. Consultez la page [Styles de fenêtre](../../mfc/reference/window-styles.md) et [CWnd::Create](../../mfc/reference/cwnd-class.md#create) pour obtenir une description des valeurs possibles.  
  
 `rect`  
 La taille et la position de la fenêtre, en coordonnées clientes de `pParentWnd`.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parent.  
  
 `nID`  
 Identificateur de la fenêtre enfant.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Le `CreateEx` les paramètres spécifient le **WNDCLASS**, style de fenêtre et position initiale (éventuellement) et la taille de la fenêtre. `CreateEx`Spécifie également la fenêtre parent (le cas échéant) et code.  
  
 Lors de la `CreateEx` s’exécute, Windows envoie le [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), et [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) messages dans la fenêtre.  
  
 Pour étendre le traitement du message par défaut, dérivez une classe de `CMiniFrameWnd`, ajouter une table des messages à la nouvelle classe et fournissent des fonctions membres pour les messages ci-dessus. Substituer `OnCreate`, par exemple, pour effectuer l’initialisation nécessaire pour une nouvelle classe.  
  
 Remplacer plus **sur***Message* gestionnaires pour ajouter d’autres fonctionnalités à votre classe dérivée de messages.  
  
 Si le **WS_VISIBLE** style est fourni, Windows envoie la fenêtre tous les messages qui sont requises pour activer et afficher la fenêtre. Si le style de fenêtre spécifie une barre de titre, le titre de la fenêtre vers laquelle pointe le `lpszWindowName` paramètre s’affiche dans la barre de titre.  
  
 Le `dwStyle` paramètre peut être n’importe quelle combinaison de [styles de fenêtre](../../mfc/reference/window-styles.md).  
  
 Les fenêtres de boîte à outils de Palette style ancien ne sont plus pris en charge. Le style ancien, qui n’a pas un bouton de fermeture « X », a été pris en charge lors de l’exécution d’une application MFC dans les versions précédentes de Windows, mais n’est plus pris en charge dans Visual C++ .NET. La nouvelle `WS_EX_TOOLWINDOW` style est maintenant pris en charge ; pour obtenir une description de ce style, consultez [Styles de fenêtre étendus](../../mfc/reference/extended-window-styles.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CFrameWnd (classe)](../../mfc/reference/cframewnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CFrameWnd (classe)](../../mfc/reference/cframewnd-class.md)

