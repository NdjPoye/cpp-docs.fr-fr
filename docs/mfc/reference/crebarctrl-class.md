---
title: CReBarCtrl (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- rebar controls, control bar
- rebar controls, CReBarCtrl class
- CReBarCtrl class
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
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
ms.openlocfilehash: c1da4de2897c74e9cb25bc060033f4bd43159174
ms.lasthandoff: 02/24/2017

---
# <a name="crebarctrl-class"></a>CReBarCtrl (classe)
Encapsule les fonctionnalités d'un contrôle rebar, qui est un conteneur de fenêtre enfant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Construit un objet `CReBarCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](#begindrag)|Place le contrôle rebar en mode de glisser-déplacer.|  
|[CReBarCtrl::Create](#create)|Crée le contrôle rebar et l’attache à le `CReBarCtrl` objet.|  
|[CReBarCtrl::CreateEx](#createex)|Crée un contrôle rebar avec les styles étendus Windows spécifiés et l’attache à une `CReBarCtrl` objet.|  
|[CReBarCtrl::DeleteBand](#deleteband)|Supprime une bande d’un contrôle rebar.|  
|[CReBarCtrl::DragMove](#dragmove)|Met à jour la position de glissement du contrôle rebar après un appel à `BeginDrag`.|  
|[CReBarCtrl::EndDrag](#enddrag)|Termine l’opération de glisser-déplacer d' un contrôle rebar.|  
|[CReBarCtrl::GetBandBorders](#getbandborders)|Récupère les bordures d’une bande.|  
|[CReBarCtrl::GetBandCount](#getbandcount)|Récupère le nombre de bandes actuellement dans le contrôle rebar.|  
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Récupère des informations sur une bande dans un contrôle rebar spécifiée.|  
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Récupère les marges d’une bande.|  
|[CReBarCtrl::GetBarHeight](#getbarheight)|Récupère la hauteur du contrôle rebar.|  
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Récupère des informations sur le contrôle rebar et il utilise la liste d’images.|  
|[CReBarCtrl::GetBkColor](#getbkcolor)|Récupère la couleur d’arrière-plan par défaut d’un contrôle rebar.|  
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Récupère le [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) structure associée au contrôle rebar.|  
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Récupère d’un contrôle rebar `IDropTarget` pointeur d’interface.|  
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Obtient le style étendu du contrôle rebar actuel.|  
|[CReBarCtrl::GetImageList](#getimagelist)|Récupère la liste d’images associée à un contrôle rebar.|  
|[CReBarCtrl::GetPalette](#getpalette)|Récupère la palette actuelle d' un contrôle rebar.|  
|[CReBarCtrl::GetRect](#getrect)|Récupère le rectangle englobant d’une bande spécifique dans un contrôle rebar.|  
|[CReBarCtrl::GetRowCount](#getrowcount)|Récupère le nombre de lignes de bandes dans un contrôle rebar.|  
|[CReBarCtrl::GetRowHeight](#getrowheight)|Récupère la hauteur d’une ligne spécifiée dans un contrôle rebar.|  
|[CReBarCtrl::GetTextColor](#gettextcolor)|Récupère la couleur du texte par défaut d’un contrôle rebar.|  
|[CReBarCtrl::GetToolTips](#gettooltips)|Récupère le handle d’un contrôle d’info-bulle associé au contrôle rebar.|  
|[CReBarCtrl::HitTest](#hittest)|Détermine quelle partie d’une bande rebar à un moment donné sur l’écran, si une bande rebar existe à ce stade.|  
|[CReBarCtrl::IDToIndex](#idtoindex)|Convertit un identificateur (ID) de la bande à un index de la bande dans un contrôle rebar.|  
|[CReBarCtrl::InsertBand](#insertband)|Insère une nouvelle bande dans un contrôle rebar.|  
|[CReBarCtrl::MaximizeBand](#maximizeband)|Redimensionne une bande dans un contrôle rebar à sa taille maximale.|  
|[CReBarCtrl::MinimizeBand](#minimizeband)|Redimensionne une bande dans un contrôle rebar à sa taille plus petite.|  
|[CReBarCtrl::MoveBand](#moveband)|Déplace une bande à partir d’un index à l’autre.|  
|[CReBarCtrl::PushChevron](#pushchevron)|Exécute un push d’un chevron par programme.|  
|[CReBarCtrl::RestoreBand](#restoreband)|Redimensionne une bande dans un contrôle rebar à sa taille idéale.|  
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Définit les caractéristiques d’une bande existante dans un contrôle rebar.|  
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Définit la largeur de la bande spécifiée ancrée dans le contrôle rebar actuel.|  
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Définit les caractéristiques d’un contrôle rebar.|  
|[CReBarCtrl::SetBkColor](#setbkcolor)|Définit la couleur d’arrière-plan par défaut d’un contrôle rebar.|  
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Définit le jeu de couleurs pour les boutons dans un contrôle rebar.|  
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Définit les styles étendus pour le contrôle rebar actuel.|  
|[CReBarCtrl::SetImageList](#setimagelist)|Définit la liste d’images d’un contrôle rebar.|  
|[CReBarCtrl::SetOwner](#setowner)|Définit la fenêtre de propriétaire d’un contrôle rebar.|  
|[CReBarCtrl::SetPalette](#setpalette)|Définit la palette actuelle d' un contrôle rebar.|  
|[CReBarCtrl::SetTextColor](#settextcolor)|Définit la couleur du texte par défaut d’un contrôle rebar.|  
|[CReBarCtrl::SetToolTips](#settooltips)|Associe un contrôle info-bulle du contrôle rebar.|  
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Définit le style visuel du contrôle rebar.|  
|[CReBarCtrl::ShowBand](#showband)|Affiche ou masque une bande spécifique dans un contrôle rebar.|  
|[CReBarCtrl::SizeToRect](#sizetorect)|Correspond à un contrôle rebar à un rectangle spécifié.|  
  
## <a name="remarks"></a>Notes  
 L’application dans laquelle réside le contrôle rebar affecte la fenêtre enfant contenue par le contrôle rebar à la bande de rebar. La fenêtre enfant est généralement un autre contrôle commun.  
  
 Rebar (contrôles) contiennent une ou plusieurs bandes. Chaque bande peut contenir une combinaison d’une barre de redimensionnement, bitmap, une étiquette de texte et fenêtre enfant. La bande peut contenir qu’un seul de ces éléments.  
  
 Le contrôle rebar peut afficher la fenêtre enfant sur un bitmap d’arrière-plan spécifiée. Toutes les bandes du contrôle rebar peuvent être redimensionnées, à l’exception de celles qui utilisent la **RBBS_FIXEDSIZE** style. Comme vous repositionnez ou redimensionnez une bande de contrôle rebar, le contrôle rebar gère la taille et la position de la fenêtre enfant affectée à cette bande. Pour redimensionner ou modifier l’ordre des bandes dans le contrôle, cliquez et faites glisser la barre de redimensionnement d’une bande.  
  
 L’illustration suivante montre un contrôle rebar qui a trois bandes :  
  
-   Bande 0 contienne un contrôle de barre d’outils plate et transparente.  
  
-   Bande 1 contient deux boutons transparent déroulante standard et transparent.  
  
-   Bande 2 contient une zone de liste déroulante et quatre boutons standards.  
  
     ![Exemple de menu Rebar](../../mfc/reference/media/vc4scc1.gif "vc4scc1")  
  
## <a name="rebar-control"></a>Contrôle rebar  
 Prise en charge des contrôles de barre :  
  
-   Listes d’images.  
  
-   Gestion des messages.  
  
-   Fonctionnalités de dessin personnalisé.  
  
-   Une variété de styles de contrôle en plus des styles de fenêtre standard. Pour obtenir la liste de ces styles, consultez [Styles de contrôle Rebar](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations, consultez [à l’aide de CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="a-namebegindraga--crebarctrlbegindrag"></a><a name="begindrag"></a>CReBarCtrl::BeginDrag  
 Implémente le comportement du message Win32 [RB_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774429), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void BeginDrag(
    UINT uBand,  
    DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro de la bande qui affecte l’opération de glisser-déplacer.  
  
 `dwPos`  
 Un `DWORD` valeur qui contient les coordonnées de la souris. Coordonnée horizontale est contenue dans le LOWORD et coordonnée verticale est contenue dans le HIWORD. Si vous transmettez `(DWORD)-1`, le contrôle rebar utilise la position de la souris sur la dernière fois que le thread du contrôle appelé **GetMessage** ou **PeekMessage**.  
  
##  <a name="a-namecreatea--crebarctrlcreate"></a><a name="create"></a>CReBarCtrl::Create  
 Crée le contrôle rebar et l’attache à le `CReBarCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie la combinaison de styles de contrôle rebar appliqué au contrôle. Consultez la page [Styles de contrôle Rebar](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour obtenir la liste des styles pris en charge.  
  
 `rect`  
 Une référence à un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure, qui représente la position et la taille du contrôle rebar.  
  
 `pParentWnd`  
 Un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet de la fenêtre parent du contrôle rebar. Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID du contrôle. d' un contrôle rebar  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet a été créé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Créer un contrôle rebar en deux étapes :  
  
1.  Appelez [CReBarCtrl](#crebarctrl) pour construire un `CReBarCtrl` objet.  
  
2.  Appelez cette fonction membre, ce qui crée le contrôle rebar de Windows et l’attache à le `CReBarCtrl` objet.  
  
 Lorsque vous appelez **créer**, les contrôles communs sont initialisés.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl n °&3;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]  
  
##  <a name="a-namecreateexa--crebarctrlcreateex"></a><a name="createex"></a>CReBarCtrl::CreateEx  
 Crée un contrôle (une fenêtre enfant) et l’associe à la `CReBarCtrl` objet.  
  
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
 Spécifie la combinaison de styles de contrôle rebar appliqué au contrôle. Pour obtenir la liste des styles pris en charge, consultez la page [Styles de contrôle Rebar](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
##  <a name="a-namecrebarctrla--crebarctrlcrebarctrl"></a><a name="crebarctrl"></a>CReBarCtrl::CReBarCtrl  
 Crée un objet `CReBarCtrl`.  
  
```  
CReBarCtrl();
```  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CReBarCtrl::Create](#create).  
  
##  <a name="a-namedeletebanda--crebarctrldeleteband"></a><a name="deleteband"></a>CReBarCtrl::DeleteBand  
 Implémente le comportement du message Win32 [RB_DELETEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774431), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL DeleteBand(UINT uBand);
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro de la bande doit être supprimé.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la bande a été supprimé avec succès ; Sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl n °&4;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]  
  
##  <a name="a-namedragmovea--crebarctrldragmove"></a><a name="dragmove"></a>CReBarCtrl::DragMove  
 Implémente le comportement du message Win32 [RB_DRAGMOVE](https://msdn.microsoft.com/library/bb774433.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void DragMove(DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwPos`  
 Un `DWORD` valeur contenant les nouvelles coordonnées de la souris. Coordonnée horizontale est contenue dans le LOWORD et coordonnée verticale est contenue dans le HIWORD. Si vous transmettez `(DWORD)-1`, le contrôle rebar utilise la position de la souris sur la dernière fois que le thread du contrôle appelé **GetMessage** ou **PeekMessage**.  
  
##  <a name="a-nameenddraga--crebarctrlenddrag"></a><a name="enddrag"></a>CReBarCtrl::EndDrag  
 Implémente le comportement du message Win32 [RB_ENDDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774435), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void EndDrag();
```  
  
##  <a name="a-namegetbandbordersa--crebarctrlgetbandborders"></a><a name="getbandborders"></a>CReBarCtrl::GetBandBorders  
 Implémente le comportement du message Win32 [RB_GETBANDBORDERS](http://msdn.microsoft.com/library/windows/desktop/bb774437), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void GetBandBorders(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro de la bande dont les bordures sont récupérées.  
  
 `prc`  
 Un pointeur vers un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure qui recevra les bordures de la bande. Si le contrôle rebar a la **RBS_BANDBORDERS** style, chaque membre de cette structure reçoit le nombre de pixels, sur le côté correspondant de la bande, qui constituent la bordure. Si le contrôle rebar n’a pas la **RBS_BANDBORDERS** de style, seul le membre gauche de cette structure reçoit des informations valides. Pour obtenir une description des styles de contrôle rebar, consultez [Styles de contrôle Rebar](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbandcounta--crebarctrlgetbandcount"></a><a name="getbandcount"></a>CReBarCtrl::GetBandCount  
 Implémente le comportement du message Win32 [RB_GETBANDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774439), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
UINT GetBandCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de bandes assigné au contrôle.  
  
##  <a name="a-namegetbandinfoa--crebarctrlgetbandinfo"></a><a name="getbandinfo"></a>CReBarCtrl::GetBandInfo  
 Implémente le comportement du message Win32 [RB_GETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774451) comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL GetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro de la bande pour lequel les informations seront récupérées.  
  
 `prbbi`  
 Un pointeur vers un [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) structure de recevoir des informations de la bande. Vous devez définir le `cbSize` membre de cette structure à `sizeof(REBARBANDINFO)` et définir le **cas** membre pour les éléments que vous souhaitez récupérer avant d’envoyer ce message.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="a-namegetbandmarginsa--crebarctrlgetbandmargins"></a><a name="getbandmargins"></a>CReBarCtrl::GetBandMargins  
 Récupère les marges de la bande.  
  
```  
void GetBandMargins(PMARGINS pMargins);
```  
  
### <a name="parameters"></a>Paramètres  
 *pMargins*  
 Un pointeur vers un [marges](http://msdn.microsoft.com/library/windows/desktop/bb773244)structure qui recevront les informations.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre émule les fonctionnalités de la [RB_GETBANDMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb774453) d’un message, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbarheighta--crebarctrlgetbarheight"></a><a name="getbarheight"></a>CReBarCtrl::GetBarHeight  
 Récupère la hauteur de la barre de contrôle rebar.  
  
```  
UINT GetBarHeight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur qui représente la hauteur, en pixels, du contrôle.  
  
##  <a name="a-namegetbarinfoa--crebarctrlgetbarinfo"></a><a name="getbarinfo"></a>CReBarCtrl::GetBarInfo  
 Implémente le comportement du message Win32 [RB_GETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774457), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL GetBarInfo(REBARINFO* prbi) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `prbi`  
 Un pointeur vers un [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) structure qui recevra les informations de contrôle rebar. Vous devez définir le `cbSize` membre de cette structure à `sizeof(REBARINFO)` avant d’envoyer ce message.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="a-namegetbkcolora--crebarctrlgetbkcolor"></a><a name="getbkcolor"></a>CReBarCtrl::GetBkColor  
 Implémente le comportement du message Win32 [RB_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774459), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **COLORREF** valeur représentant la couleur d’arrière-plan par défaut actuel.  
  
##  <a name="a-namegetcolorschemea--crebarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>CReBarCtrl::GetColorScheme  
 Récupère le [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) structure pour le contrôle rebar.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpcs`  
 Un pointeur vers un [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) de structure, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Le **COLORSCHEME** structure inclut la couleur de surbrillance du bouton et la couleur de l’ombre.  
  
##  <a name="a-namegetdroptargeta--crebarctrlgetdroptarget"></a><a name="getdroptarget"></a>CReBarCtrl::GetDropTarget  
 Implémente le comportement du message Win32 [RB_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb774463), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) interface.  
  
##  <a name="a-namegetextendedstylea--crebarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CReBarCtrl::GetExtendedStyle  
 Obtient les styles étendus du contrôle rebar actuel.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Combinaison de bits (OR) d’indicateurs qui indiquent les styles étendus. Les indicateurs possibles sont `RBS_EX_SPLITTER` et `RBS_EX_TRANSPARENT`. Pour plus d’informations, consultez la `dwMask` paramètre de la [CReBarCtrl::SetExtendedStyle](#setextendedstyle) (méthode).  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [RB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774433) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetimagelista--crebarctrlgetimagelist"></a><a name="getimagelist"></a>CReBarCtrl::GetImageList  
 Obtient le `CImageList` objet associé à un contrôle rebar.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet. Retourne **NULL** si aucune liste d’images n’est défini pour le contrôle.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre utilise la taille et masque les informations stockées dans les [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) de structure, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpalettea--crebarctrlgetpalette"></a><a name="getpalette"></a>CReBarCtrl::GetPalette  
 Récupère la palette actuelle d' un contrôle rebar.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CPalette](../../mfc/reference/cpalette-class.md) objet spécifiant la palette actuelle d' un contrôle rebar.  
  
### <a name="remarks"></a>Remarques  
 Notez que cette fonction membre utilise un `CPalette` objet comme valeur de retour, plutôt que `HPALETTE`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl n °&5;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]  
  
##  <a name="a-namegetrecta--crebarctrlgetrect"></a><a name="getrect"></a>CReBarCtrl::GetRect  
 Implémente le comportement du message Win32 [RB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb774469), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL GetRect(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro d’une bande dans le contrôle rebar.  
  
 `prc`  
 Un pointeur vers un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure qui recevra les limites de la bande de rebar.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl n °&6;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]  
  
##  <a name="a-namegetrowcounta--crebarctrlgetrowcount"></a><a name="getrowcount"></a>CReBarCtrl::GetRowCount  
 Implémente le comportement du message Win32 [RB_GETROWCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774471), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
UINT GetRowCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **UINT** valeur qui représente le nombre de lignes de bandes dans le contrôle.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl&#7;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]  
  
##  <a name="a-namegetrowheighta--crebarctrlgetrowheight"></a><a name="getrowheight"></a>CReBarCtrl::GetRowHeight  
 Implémente le comportement du message Win32 [RB_GETROWHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb774473), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
UINT GetRowHeight(UINT uRow) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *uRow*  
 Index de base zéro de la bande qui aura sa hauteur récupérée.  
  
### <a name="return-value"></a>Valeur de retour  
 A **UINT** valeur qui représente la hauteur de ligne, en pixels.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl n °&8;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]  
  
##  <a name="a-namegettextcolora--crebarctrlgettextcolor"></a><a name="gettextcolor"></a>CReBarCtrl::GetTextColor  
 Implémente le comportement du message Win32 [RB_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774475), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **COLORREF** valeur représentant la couleur du texte par défaut en cours.  
  
##  <a name="a-namegettooltipsa--crebarctrlgettooltips"></a><a name="gettooltips"></a>CReBarCtrl::GetToolTips  
 Implémente le comportement du message Win32 [RB_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb774477), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Notez que l’implémentation MFC de `GetToolTips` retourne un pointeur vers un `CToolTipCtrl`, plutôt que `HWND`.  
  
##  <a name="a-namehittesta--crebarctrlhittest"></a><a name="hittest"></a>CReBarCtrl::HitTest  
 Implémente le comportement du message Win32 [RB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb774494), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
int HitTest(RBHITTESTINFO* prbht);
```  
  
### <a name="parameters"></a>Paramètres  
 *prbht*  
 Un pointeur vers un [RBHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774391) structure. Avant d’envoyer le message, le **pt** membre de cette structure doit être initialisé sur le point à tester, en coordonnées clientes.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de la bande au point spécifié ou -1 si aucune bande rebar n’était au point.  
  
##  <a name="a-nameidtoindexa--crebarctrlidtoindex"></a><a name="idtoindex"></a>CReBarCtrl::IDToIndex  
 Implémente le comportement du message Win32 [RB_IDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774496), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
int IDToIndex(UINT uBandID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *uBandID*  
 L’identificateur défini par l’application de la bande spécifiée, est passé dans le **wID** membre de la [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) structure lorsque la bande est insérée.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index de base zéro de bande si l’opération réussit, ou sinon -1. Si l’index d’une bande en double existe, la première est renvoyée.  
  
##  <a name="a-nameinsertbanda--crebarctrlinsertband"></a><a name="insertband"></a>CReBarCtrl::InsertBand  
 Implémente le comportement du message Win32 [RB_INSERTBAND](http://msdn.microsoft.com/library/windows/desktop/bb774498), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL InsertBand(
    UINT uIndex,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Paramètres  
 *uIndex*  
 Index de base zéro de l’emplacement où la bande est insérée. Si vous définissez ce paramètre sur -1, le contrôle ajoute au dernier emplacement de la nouvelle bande.  
  
 `prbbi`  
 Un pointeur vers un [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) structure qui définit la bande à insérer. Vous devez définir le `cbSize` membre de cette structure à `sizeof(REBARBANDINFO)` avant d’appeler cette fonction.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl&#9;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]  
  
##  <a name="a-namemaximizebanda--crebarctrlmaximizeband"></a><a name="maximizeband"></a>CReBarCtrl::MaximizeBand  
 Redimensionne une bande dans un contrôle rebar à sa taille maximale.  
  
```  
void MaximizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro de la bande à être agrandi.  
  
### <a name="remarks"></a>Notes  
 Implémente le comportement du message Win32 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) avec `fIdeal` la valeur 0, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl&#10;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]  
  
##  <a name="a-nameminimizebanda--crebarctrlminimizeband"></a><a name="minimizeband"></a>CReBarCtrl::MinimizeBand  
 Redimensionne une bande dans un contrôle rebar à sa taille plus petite.  
  
```  
void MinimizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro de la bande soit réduite.  
  
### <a name="remarks"></a>Notes  
 Implémente le comportement du message Win32 [RB_MINIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774502), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl&#11;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]  
  
##  <a name="a-namemovebanda--crebarctrlmoveband"></a><a name="moveband"></a>CReBarCtrl::MoveBand  
 Implémente le comportement du message Win32 [RB_MOVEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774504), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL MoveBand(
    UINT uFrom,  
    UINT uTo);
```  
  
### <a name="parameters"></a>Paramètres  
 *uFrom*  
 Index de base zéro de la bande à déplacer.  
  
 *auto.*  
 Index de base zéro de la nouvelle position de la bande. Cette valeur de paramètre ne doit jamais être supérieure au nombre de bandes moins un. Pour obtenir le nombre de bandes, appelez [GetBandCount](#getbandcount).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="a-namepushchevrona--crebarctrlpushchevron"></a><a name="pushchevron"></a>CReBarCtrl::PushChevron  
 Implémente le comportement du message Win32 [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void PushChevron(
    UINT uBand,  
    LPARAM lAppValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro de la bande dont chevron doit être envoyée.  
  
 `lAppValue`  
 Une application définie la valeur 32 bits. Consultez la page `lAppValue` dans [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namerestorebanda--crebarctrlrestoreband"></a><a name="restoreband"></a>CReBarCtrl::RestoreBand  
 Redimensionne une bande dans un contrôle rebar à sa taille idéale.  
  
```  
void RestoreBand(UINT uBand);
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro de la bande à être agrandi.  
  
### <a name="remarks"></a>Notes  
 Implémente le comportement du message Win32 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) avec `fIdeal` définie sur 1, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl&#12;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]  
  
##  <a name="a-namesetbandinfoa--crebarctrlsetbandinfo"></a><a name="setbandinfo"></a>CReBarCtrl::SetBandInfo  
 Implémente le comportement du message Win32 [RB_SETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774508), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro de la bande de recevoir les nouveaux paramètres.  
  
 `prbbi`  
 Pointeur vers un [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) structure qui définit la bande à insérer. Vous devez définir le `cbSize` membre de cette structure à `sizeof(REBARBANDINFO)` avant d’envoyer ce message.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl&#13;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]  
  
##  <a name="a-namesetbandwidtha--crebarctrlsetbandwidth"></a><a name="setbandwidth"></a>CReBarCtrl::SetBandWidth  
 Définit la largeur de la bande spécifiée ancrée dans le contrôle rebar actuel.  
  
```  
BOOL SetBandWidth(
    UINT uBand,   
    int cxWidth);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `uBand`|Index de base zéro d’une bande rebar.|  
|[in] `cxWidth`|Nouvelle largeur de la bande de rebar, en pixels.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode réussit ; sinon, `false`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [RB_SETBANDWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb774511) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_rebar`, qui est utilisé pour accéder au contrôle rebar en cours. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1 n °&1;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit chaque bande de rebar est la même largeur.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1 n °&2;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]  
  
##  <a name="a-namesetbarinfoa--crebarctrlsetbarinfo"></a><a name="setbarinfo"></a>CReBarCtrl::SetBarInfo  
 Implémente le comportement du message Win32 [RB_SETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774513), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SetBarInfo(REBARINFO* prbi);
```  
  
### <a name="parameters"></a>Paramètres  
 `prbi`  
 Un pointeur vers un [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) structure qui contient les informations à définir. Vous devez définir le `cbSize` membre de cette structure à `sizeof(REBARINFO)` avant d’envoyer ce message  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl&#14;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]  
  
##  <a name="a-namesetbkcolora--crebarctrlsetbkcolor"></a><a name="setbkcolor"></a>CReBarCtrl::SetBkColor  
 Implémente le comportement du message Win32 [RB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774515), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Paramètres  
 `clr`  
 Le **COLORREF** valeur qui représente la nouvelle couleur d’arrière-plan par défaut.  
  
### <a name="return-value"></a>Valeur de retour  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur qui représente la couleur d’arrière-plan par défaut précédente.  
  
### <a name="remarks"></a>Remarques  
 Consultez cette rubrique pour plus d’informations sur le moment définir la couleur d’arrière-plan et comment définir la valeur par défaut.  
  
##  <a name="a-namesetcolorschemea--crebarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>CReBarCtrl::SetColorScheme  
 Définit le jeu de couleurs pour les boutons dans un contrôle rebar.  
  
```  
void SetColorScheme(const COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpcs`  
 Un pointeur vers un [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) de structure, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Le **COLORSCHEME** structure inclut la couleur de surbrillance du bouton et la couleur de l’ombre.  
  
##  <a name="a-namesetextendedstylea--crebarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CReBarCtrl::SetExtendedStyle  
 Définit les styles étendus pour le contrôle rebar actuel.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwMask,   
    DWORD dwStyleEx);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `dwMask`|Combinaison de bits (OR) d’indicateurs qui spécifient les indicateurs dans le `dwStyleEx` paramètre s’applique. Utiliser une ou plusieurs des valeurs suivantes :<br /><br /> RBS_EX_SPLITTER : Par défaut, afficher le séparateur en bas en mode horizontal et à droite en mode vertical.<br /><br /> RBS_EX_TRANSPARENT : Transférer le [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message de la fenêtre parente.|  
|[in] `dwStyleEx`|Combinaison de bits (OR) d’indicateurs qui spécifient les styles à appliquer. Pour définir un style, spécifiez le même indicateur est utilisé dans le `dwMask` paramètre. Pour réinitialiser un style, spécifiez zéro binaire.|  
  
### <a name="return-value"></a>Valeur de retour  
 Le style étendu précédent.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [RB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774519) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetimagelista--crebarctrlsetimagelist"></a><a name="setimagelist"></a>CReBarCtrl::SetImageList  
 Affecte une liste d’images à un contrôle rebar.  
  
```  
BOOL SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Paramètres  
 `pImageList`  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet contenant la liste d’images à assigner au contrôle rebar.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="a-namesetownera--crebarctrlsetowner"></a><a name="setowner"></a>CReBarCtrl::SetOwner  
 Implémente le comportement du message Win32 [RB_SETPARENT](http://msdn.microsoft.com/library/windows/desktop/bb774522), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CWnd* SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Un pointeur vers un `CWnd` objet à définir comme propriétaire du contrôle rebar.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet qui est le propriétaire actuel du contrôle rebar.  
  
### <a name="remarks"></a>Remarques  
 Notez que cette fonction membre utilise des pointeurs vers des `CWnd` des objets pour le propriétaire actuel et sélectionné du contrôle rebar, plutôt que de handles vers windows.  
  
> [!NOTE]
>  Cette fonction membre ne modifie pas le parent actuel a été défini lorsque le contrôle a été créé ; au lieu de cela, il envoie des messages de notification dans la fenêtre que vous spécifiez.  
  
##  <a name="a-namesetpalettea--crebarctrlsetpalette"></a><a name="setpalette"></a>CReBarCtrl::SetPalette  
 Implémente le comportement du message Win32 [RB_SETPALETTE](http://msdn.microsoft.com/library/windows/desktop/bb774520), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CPalette* SetPalette(HPALETTE hPal);
```  
  
### <a name="parameters"></a>Paramètres  
 *hPal*  
 Un `HPALETTE` qui spécifie la nouvelle palette qui utilise le contrôle rebar.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CPalette](../../mfc/reference/cpalette-class.md) objet spécifiant la palette précédente du contrôle rebar.  
  
### <a name="remarks"></a>Remarques  
 Notez que cette fonction membre utilise un `CPalette` objet comme valeur de retour, plutôt que `HPALETTE`.  
  
##  <a name="a-namesettextcolora--crebarctrlsettextcolor"></a><a name="settextcolor"></a>CReBarCtrl::SetTextColor  
 Implémente le comportement du message Win32 [RB_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774524), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Paramètres  
 `clr`  
 A **COLORREF** valeur qui représente le texte de couleur le `CReBarCtrl` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Le [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur représentant la couleur précédente de texte associée à la `CReBarCtrl` objet.  
  
### <a name="remarks"></a>Remarques  
 Il est fourni pour prendre en charge la flexibilité de couleur de texte dans un contrôle rebar.  
  
##  <a name="a-namesettooltipsa--crebarctrlsettooltips"></a><a name="settooltips"></a>CReBarCtrl::SetToolTips  
 Associe un contrôle info-bulle à un contrôle rebar.  
  
```  
void SetToolTips(CToolTipCtrl* pToolTip);
```  
  
### <a name="parameters"></a>Paramètres  
 *pToolTip*  
 Un pointeur vers un [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) objet  
  
### <a name="remarks"></a>Remarques  
 Vous devez détruire le `CToolTipCtrl` de l’objet lorsque vous avez terminé avec lui.  
  
##  <a name="a-namesetwindowthemea--crebarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CReBarCtrl::SetWindowTheme  
 Définit le style visuel du contrôle rebar.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszSubAppName`  
 Pointeur vers une chaîne Unicode qui contient le style visuel rebar à définir.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour n’est pas utilisée.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre émule les fonctionnalités de la [RB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb774530) d’un message, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameshowbanda--crebarctrlshowband"></a><a name="showband"></a>CReBarCtrl::ShowBand  
 Implémente le comportement du message Win32 [RB_SHOWBAND](http://msdn.microsoft.com/library/windows/desktop/bb774532), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL ShowBand(
    UINT uBand,  
    BOOL fShow = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `uBand`  
 Index de base zéro d’une bande dans le contrôle rebar.  
  
 *fShow*  
 Indique si la bande doit être affichée ou masquée. Si cette valeur est **TRUE**, la bande s’affichera. Dans le cas contraire, la bande sera masquée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="a-namesizetorecta--crebarctrlsizetorect"></a><a name="sizetorect"></a>CReBarCtrl::SizeToRect  
 Implémente le comportement du message Win32 [RB_SIZETORECT](http://msdn.microsoft.com/library/windows/desktop/bb774534), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SizeToRect(CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 Une référence à un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui spécifie le rectangle qui doit avoir des dimensions pour le contrôle rebar.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Notez que cette fonction membre utilise un `CRect` comme paramètre, plutôt qu’un `RECT` structure.  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)



