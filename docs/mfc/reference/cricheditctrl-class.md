---
title: CRichEditCtrl (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditCtrl
- AFXCMN/CRichEditCtrl
- AFXCMN/CRichEditCtrl::CRichEditCtrl
- AFXCMN/CRichEditCtrl::CanPaste
- AFXCMN/CRichEditCtrl::CanRedo
- AFXCMN/CRichEditCtrl::CanUndo
- AFXCMN/CRichEditCtrl::CharFromPos
- AFXCMN/CRichEditCtrl::Clear
- AFXCMN/CRichEditCtrl::Copy
- AFXCMN/CRichEditCtrl::Create
- AFXCMN/CRichEditCtrl::CreateEx
- AFXCMN/CRichEditCtrl::Cut
- AFXCMN/CRichEditCtrl::DisplayBand
- AFXCMN/CRichEditCtrl::EmptyUndoBuffer
- AFXCMN/CRichEditCtrl::FindText
- AFXCMN/CRichEditCtrl::FindWordBreak
- AFXCMN/CRichEditCtrl::FormatRange
- AFXCMN/CRichEditCtrl::GetCharPos
- AFXCMN/CRichEditCtrl::GetDefaultCharFormat
- AFXCMN/CRichEditCtrl::GetEventMask
- AFXCMN/CRichEditCtrl::GetFirstVisibleLine
- AFXCMN/CRichEditCtrl::GetIRichEditOle
- AFXCMN/CRichEditCtrl::GetLimitText
- AFXCMN/CRichEditCtrl::GetLine
- AFXCMN/CRichEditCtrl::GetLineCount
- AFXCMN/CRichEditCtrl::GetModify
- AFXCMN/CRichEditCtrl::GetOptions
- AFXCMN/CRichEditCtrl::GetParaFormat
- AFXCMN/CRichEditCtrl::GetPunctuation
- AFXCMN/CRichEditCtrl::GetRect
- AFXCMN/CRichEditCtrl::GetRedoName
- AFXCMN/CRichEditCtrl::GetSel
- AFXCMN/CRichEditCtrl::GetSelectionCharFormat
- AFXCMN/CRichEditCtrl::GetSelectionType
- AFXCMN/CRichEditCtrl::GetSelText
- AFXCMN/CRichEditCtrl::GetTextLength
- AFXCMN/CRichEditCtrl::GetTextLengthEx
- AFXCMN/CRichEditCtrl::GetTextMode
- AFXCMN/CRichEditCtrl::GetTextRange
- AFXCMN/CRichEditCtrl::GetUndoName
- AFXCMN/CRichEditCtrl::GetWordWrapMode
- AFXCMN/CRichEditCtrl::HideSelection
- AFXCMN/CRichEditCtrl::LimitText
- AFXCMN/CRichEditCtrl::LineFromChar
- AFXCMN/CRichEditCtrl::LineIndex
- AFXCMN/CRichEditCtrl::LineLength
- AFXCMN/CRichEditCtrl::LineScroll
- AFXCMN/CRichEditCtrl::Paste
- AFXCMN/CRichEditCtrl::PasteSpecial
- AFXCMN/CRichEditCtrl::PosFromChar
- AFXCMN/CRichEditCtrl::Redo
- AFXCMN/CRichEditCtrl::ReplaceSel
- AFXCMN/CRichEditCtrl::RequestResize
- AFXCMN/CRichEditCtrl::SetAutoURLDetect
- AFXCMN/CRichEditCtrl::SetBackgroundColor
- AFXCMN/CRichEditCtrl::SetDefaultCharFormat
- AFXCMN/CRichEditCtrl::SetEventMask
- AFXCMN/CRichEditCtrl::SetModify
- AFXCMN/CRichEditCtrl::SetOLECallback
- AFXCMN/CRichEditCtrl::SetOptions
- AFXCMN/CRichEditCtrl::SetParaFormat
- AFXCMN/CRichEditCtrl::SetPunctuation
- AFXCMN/CRichEditCtrl::SetReadOnly
- AFXCMN/CRichEditCtrl::SetRect
- AFXCMN/CRichEditCtrl::SetSel
- AFXCMN/CRichEditCtrl::SetSelectionCharFormat
- AFXCMN/CRichEditCtrl::SetTargetDevice
- AFXCMN/CRichEditCtrl::SetTextMode
- AFXCMN/CRichEditCtrl::SetUndoLimit
- AFXCMN/CRichEditCtrl::SetWordCharFormat
- AFXCMN/CRichEditCtrl::SetWordWrapMode
- AFXCMN/CRichEditCtrl::StopGroupTyping
- AFXCMN/CRichEditCtrl::StreamIn
- AFXCMN/CRichEditCtrl::StreamOut
- AFXCMN/CRichEditCtrl::Undo
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class, common controls
- CRichEditCtrl class
- formatted text [C++]
ms.assetid: 2be52788-822c-4c27-aafd-2471231e74eb
caps.latest.revision: 26
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
ms.openlocfilehash: 77b8dfb6011831f4e4300096a127f70b26bcc603
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditctrl-class"></a>CRichEditCtrl (classe)
Fournit les fonctionnalités du contrôle d'édition enrichi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CRichEditCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditCtrl::CRichEditCtrl](#cricheditctrl)|Construit un objet `CRichEditCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditCtrl::CanPaste](#canpaste)|Détermine si le contenu du Presse-papiers peut être collé dans ce contrôle d’édition enrichi.|  
|[CRichEditCtrl::CanRedo](#canredo)|Détermine s’il existe des actions en file d’attente de restauration par progression du contrôle.|  
|[CRichEditCtrl::CanUndo](#canundo)|Détermine si une opération de modification peut être annulée.|  
|[CRichEditCtrl::CharFromPos](#charfrompos)|Récupère des informations sur le caractère le plus proche à un point spécifié dans la zone cliente du contrôle d’édition.|  
|[CRichEditCtrl::Clear](#clear)|Efface la sélection actuelle.|  
|[CRichEditCtrl::Copy](#copy)|Copie la sélection actuelle dans le Presse-papiers.|  
|[CRichEditCtrl::Create](#create)|Crée le contrôle d’édition enrichi de Windows et l’associe à cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::CreateEx](#createex)|Crée le contrôle d’édition enrichi Windows utilisant Windows styles étendus et l’associe à cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::Cut](#cut)|Coupe la sélection actuelle dans le Presse-papiers.|  
|[CRichEditCtrl::DisplayBand](#displayband)|Affiche une partie du contenu de ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::EmptyUndoBuffer](#emptyundobuffer)|Réinitialise (efface), l’indicateur d’annulation de cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::FindText](#findtext)|Recherche de texte dans cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::FindWordBreak](#findwordbreak)|Recherche le prochain saut word avant ou après la position de caractère spécifiée, ou récupère des informations sur le caractère à cette position.|  
|[CRichEditCtrl::FormatRange](#formatrange)|Met en forme une plage de texte pour le périphérique de sortie cible.|  
|[CRichEditCtrl::GetCharPos](#getcharpos)|Détermine l’emplacement d’un caractère donné dans cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetDefaultCharFormat](#getdefaultcharformat)|Récupère le caractère par défaut actuelle mise en forme d’attributs dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetEventMask](#geteventmask)|Récupère le masque d’événement de ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetFirstVisibleLine](#getfirstvisibleline)|Détermine la ligne supérieure visible dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetIRichEditOle](#getiricheditole)|Récupère un pointeur vers le `IRichEditOle` de l’interface pour ce contrôle RichEdit.|  
|[CRichEditCtrl::GetLimitText](#getlimittext)|Obtient la limite de la quantité de texte, un utilisateur peut entrer dans cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetLine](#getline)|Récupère une ligne de texte à partir de ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetLineCount](#getlinecount)|Récupère le nombre de lignes dans cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetModify](#getmodify)|Détermine si le contenu de ce `CRichEditCtrl` objet ont été modifiés depuis le dernier enregistrement.|  
|[CRichEditCtrl::GetOptions](#getoptions)|Récupère les options de contrôle RichEdit.|  
|[CRichEditCtrl::GetParaFormat](#getparaformat)|Récupère les paragraphes d’attributs de la sélection actuelle dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetPunctuation](#getpunctuation)|Extrait les caractères de ponctuation actuelle pour le contrôle d’édition enrichi. Ce message est disponible uniquement dans les versions asiatiques du système d’exploitation.|  
|[CRichEditCtrl::GetRect](#getrect)|Récupère le rectangle de mise en forme de ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetRedoName](#getredoname)|Récupère le type de l’action suivante, si un dans du contrôle file d’attente de restauration par progression.|  
|[CRichEditCtrl::GetSel](#getsel)|Obtient le début et fin des positions de la sélection actuelle dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetSelectionCharFormat](#getselectioncharformat)|Récupère le caractère de mise en forme des attributs de la sélection actuelle dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetSelectionType](#getselectiontype)|Récupère le type de contenu de la sélection actuelle dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::GetSelText](#getseltext)|Obtient le texte de la sélection actuelle dans ce `CRichEditCtrl` objet|  
|[CRichEditCtrl::GetTextLength](#gettextlength)|Récupère la longueur du texte, en caractères, dans ce `CRichEditCtrl` objet. N’inclut pas le caractère null de fin.|  
|[CRichEditCtrl::GetTextLengthEx](#gettextlengthex)|Récupère le nombre de caractères ou d’octets dans la vue d’édition enrichi. Accepte une liste d’indicateurs pour indiquer la méthode de détermination de la longueur du texte dans un contrôle RichEdit|  
|[CRichEditCtrl::GetTextMode](#gettextmode)|Récupère le niveau de mode et annulation d’opérations de texte actuel d’un contrôle RichEdit.|  
|[CRichEditCtrl::GetTextRange](#gettextrange)|Récupère la plage de texte spécifiée.|  
|[CRichEditCtrl::GetUndoName](#getundoname)|Récupère le type de l’action d’annulation suivant, le cas échéant.|  
|[CRichEditCtrl::GetWordWrapMode](#getwordwrapmode)|Récupère le retour actuel et les options de dernières word du contrôle RichEdit. Ce message est disponible uniquement dans les versions asiatiques du système d’exploitation.|  
|[CRichEditCtrl::HideSelection](#hideselection)|Affiche ou masque la sélection actuelle.|  
|[CRichEditCtrl::LimitText](#limittext)|Limite la quantité de texte, un utilisateur peut entrer dans le `CRichEditCtrl` objet.|  
|[CRichEditCtrl::LineFromChar](#linefromchar)|Détermine quelle ligne contient le caractère donné.|  
|[CRichEditCtrl::LineIndex](#lineindex)|Récupère l’index de caractère d’une ligne donnée dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::LineLength](#linelength)|Récupère la longueur d’une ligne donnée dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::LineScroll](#linescroll)|Fait défiler le texte dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::Paste](#paste)|Insère le contenu du Presse-papiers dans ce contrôle d’édition enrichi.|  
|[CRichEditCtrl::PasteSpecial](#pastespecial)|Insère le contenu du Presse-papiers dans ce contrôle d’édition enrichi dans le format de données spécifié.|  
|[CRichEditCtrl::PosFromChar](#posfromchar)|Récupère les coordonnées de la zone client d’un caractère spécifié dans un contrôle d’édition.|  
|[CRichEditCtrl::Redo](#redo)|Rétablit l’action suivante dans la file d’attente de restauration par progression du contrôle.|  
|[CRichEditCtrl::ReplaceSel](#replacesel)|Remplace la sélection actuelle dans ce `CRichEditCtrl` avec le texte spécifié.|  
|[CRichEditCtrl::RequestResize](#requestresize)|Cela force `CRichEditCtrl` objet pour envoyer des notifications de requête redimensionnement.|  
|[CRichEditCtrl::SetAutoURLDetect](#setautourldetect)|Indique si la détection automatique des URL est active dans un contrôle rich edit.|  
|[CRichEditCtrl::SetBackgroundColor](#setbackgroundcolor)|Définit la couleur d’arrière-plan dans cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetDefaultCharFormat](#setdefaultcharformat)|Définit le caractère par défaut actuelle mise en forme d’attributs dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetEventMask](#seteventmask)|Définit le masque d’événement de ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetModify](#setmodify)|Active ou désactive l’indicateur de modification pour ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetOLECallback](#setolecallback)|Définit le `IRichEditOleCallback` objet COM pour ce contrôle d’édition enrichi.|  
|[CRichEditCtrl::SetOptions](#setoptions)|Définit les options pour ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetParaFormat](#setparaformat)|Définit la mise en forme des attributs de la sélection actuelle dans ce paragraphe `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetPunctuation](#setpunctuation)|Définit les caractères de ponctuation pour un contrôle rich edit. Ce message est disponible uniquement dans les versions asiatiques du système d’exploitation.|  
|[CRichEditCtrl::SetReadOnly](#setreadonly)|Définit l’option lecture seule pour ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetRect](#setrect)|Définit le rectangle de mise en forme de ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetSel](#setsel)|Définit la sélection dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetSelectionCharFormat](#setselectioncharformat)|Définit le caractère de mise en forme des attributs de la sélection actuelle dans ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetTargetDevice](#settargetdevice)|Définit le périphérique de sortie cible de ce `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetTextMode](#settextmode)|Définit le niveau de texte en mode ou annulation d’un contrôle RichEdit. Le message échoue si le contrôle contient du texte.|  
|[CRichEditCtrl::SetUndoLimit](#setundolimit)|Définit le nombre maximal d’actions pouvant être stockés dans la file d’attente.|  
|[CRichEditCtrl::SetWordCharFormat](#setwordcharformat)|Définit le caractère de mise en forme des attributs dans le mot actuel dans cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::SetWordWrapMode](#setwordwrapmode)|Définit les options de saut de ligne et de césure de mots pour la riche contrôle d’édition. Ce message est disponible uniquement dans les versions asiatiques du système d’exploitation.|  
|[CRichEditCtrl::StopGroupTyping](#stopgrouptyping)|Arrête le contrôle de la collecte supplémentaire en tapant des actions dans l’action en cours d’annulation. Le contrôle stocke l’action suivante de frappe, éventuellement dans une action dans la file d’attente.|  
|[CRichEditCtrl::StreamIn](#streamin)|Insère le texte à partir d’un flux d’entrée dans cette `CRichEditCtrl` objet.|  
|[CRichEditCtrl::StreamOut](#streamout)|Stocke le texte à partir de ce `CRichEditCtrl` un objet en un flux de sortie.|  
|[CRichEditCtrl::Undo](#undo)|Annule la dernière opération de modification.|  
  
## <a name="remarks"></a>Remarques  
 Un « contrôle rich edit » est une fenêtre dans laquelle l’utilisateur peut entrer et modifier du texte. Le texte peut être attribué caractères ou paragraphes et peut inclure des objets OLE incorporés. Les contrôles RichEdit fournissent une interface de programmation pour la mise en forme de texte. Toutefois, une application doit implémenter tous les composants d’interface utilisateur nécessaires pour rendre les opérations de mise en forme disponibles à l’utilisateur.  
  
 Ce contrôle commun de Windows (et par conséquent la `CRichEditCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT versions 3.51 et ultérieures. Le `CRichEditCtrl` classe prend en charge les versions 2.0 et 3.0 de la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] contrôle RichEdit.  
  
> [!CAUTION]
>  Si vous utilisez un contrôle RichEdit dans une boîte de dialogue (quel que soit votre application soit SDI, MDI ou basée sur une boîte de dialogue), vous devez appeler [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit) une fois avant de la boîte de dialogue zone s’affiche. Un emplacement standard pour appeler cette fonction est de votre programme `InitInstance` fonction membre. Il est inutile de l’appeler à chaque fois que vous affichez la boîte de dialogue uniquement la première fois. Vous n’avez pas à appeler `AfxInitRichEdit` si vous travaillez avec `CRichEditView`.  
  
 Pour plus d’informations sur l’utilisation de `CRichEditCtrl`, voir :  
  
- [Contrôles](../../mfc/controls-mfc.md)  
  
- [Utilisation de CRichEditCtrl](../../mfc/using-cricheditctrl.md)  
  
-   L’article Q259949 de la Base de connaissances : INFO : SetCaretPos() n’est pas appropriée avec CEdit ou contrôles de CRichEditCtrl  
  
 Pour obtenir un exemple de l’utilisation d’un contrôle rich edit dans une application MFC, consultez la [WORDPAD](../../visual-cpp-samples.md) exemple d’application.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CRichEditCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="canpaste"></a>CRichEditCtrl::CanPaste  
 Détermine si le contrôle rich edit peut coller le format de Presse-papiers spécifié.  
  
```  
BOOL CanPaste(UINT nFormat = 0) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nFormat`  
 Le format de données de Presse-papiers à la requête. Ce paramètre peut être un des formats de Presse-papiers prédéfinis ou la valeur retournée par [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le format de Presse-papiers peut être collé ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Si `nFormat` est 0, `CanPaste` va essayer de n’importe quel format actuellement dans le Presse-papiers.  
  
 Pour plus d’informations, consultez [EM_CANPASTE](http://msdn.microsoft.com/library/windows/desktop/bb787993) message et [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) de fonction dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&1;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_1.cpp)]  
  
##  <a name="canredo"></a>CRichEditCtrl::CanRedo  
 Détermine si la file d’attente de restauration par progression contient toutes les actions.  
  
```  
BOOL CanRedo() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la file d’attente de restauration par progression contient des actions, sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Pour découvrir le nom de l’opération dans la file d’attente de restauration par progression, appelez [CRichEditCtrl::GetRedoName](#getredoname). Pour rétablir la dernière opération d’annulation, appelez [de restauration par progression](#redo).  
  
 Pour plus d’informations, consultez [EM_CANREDO](http://msdn.microsoft.com/library/windows/desktop/bb787995) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="canundo"></a>CRichEditCtrl::CanUndo  
 Détermine si la dernière opération de modification peut être annulée.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la dernière opération de modification peut être annulée par un appel à la [Annuler](#undo) fonction membre ; 0 si elle ne peut pas être annulée.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&2;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_2.cpp)]  
  
##  <a name="charfrompos"></a>CRichEditCtrl::CharFromPos  
 Récupère des informations sur le caractère au point spécifié par le paramètre `pt`.  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet contenant les coordonnées du point spécifié.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index de caractère de base zéro du caractère le plus proche du point spécifié. Si le point spécifié se trouve au-delà du dernier caractère dans le contrôle, la valeur de retour indique le dernier caractère dans le contrôle.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre fonctionne avec un contrôle rich edit. Pour obtenir les informations d’un contrôle d’édition, appelez [CEdit::CharFromPos](../../mfc/reference/cedit-class.md#charfrompos).  
  
 Pour plus d’informations, consultez [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="clear"></a>CRichEditCtrl::Clear  
 Supprime (efface) contrôle la sélection actuelle (le cas échéant) de la riche d’édition.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarques  
 La suppression effectuée par **clair** puissent être annulées en appelant le [Annuler](#undo) fonction membre.  
  
 Pour supprimer la sélection actuelle et placez le contenu supprimé dans le Presse-papiers, appelez le [couper](#cut) fonction membre.  
  
 Pour plus d’informations, consultez [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&3;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_3.cpp)]  
  
##  <a name="copy"></a>CRichEditCtrl::Copy  
 Copie la sélection actuelle (le cas échéant) dans le contrôle RichEdit dans le Presse-papiers.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&4;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_4.cpp)]  
  
##  <a name="create"></a>CRichEditCtrl::Create  
 Crée le contrôle d’édition enrichi de Windows et l’associe à cette `CRichEditCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie le style du contrôle d’édition. Appliquer une combinaison des styles de fenêtre répertoriées dans le **remarques** ci-dessous, et [modifier les styles de contrôle](http://msdn.microsoft.com/library/windows/desktop/bb775464), décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Spécifie la taille et la position du contrôle d’édition. Peut être un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou [RECT](../../mfc/reference/rect-structure1.md) structure.  
  
 `pParentWnd`  
 Spécifie la fenêtre du parent du contrôle d’édition (souvent un [CDialog](../../mfc/reference/cdialog-class.md)). Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID. du contrôle de la modifier  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation aboutit ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Vous construisez un `CRichEditCtrl` objet en deux étapes. Tout d’abord, appelez le [CRichEditCtrl](#cricheditctrl) constructeur, puis appelez **créer**, qui crée le contrôle d’édition Windows et l’attache à le `CRichEditCtrl` objet.  
  
 Lorsque vous créez un contrôle rich edit avec cette fonction, vous devez tout d’abord charger la bibliothèque de contrôles communs nécessaires. Pour charger la bibliothèque, appelez la fonction globale [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit), ce qui initialise ensuite la bibliothèque de contrôles. Vous devez appeler `AfxInitRichEdit` qu’une seule fois dans votre processus.  
  
 Lors de la **créer** s’exécute, Windows envoie le [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), et [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) messages au contrôle d’édition.  
  
 Ces messages sont gérées par défaut par le [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), et [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) les fonctions membres dans la `CWnd` classe de base. Pour étendre le traitement du message par défaut, dérivez une classe de `CRichEditCtrl`, ajouter une table des messages à la nouvelle classe et substituer les fonctions membres de gestionnaire de messages ci-dessus. Substituer `OnCreate`, par exemple, pour effectuer l’initialisation nécessaire pour la nouvelle classe.  
  
 Appliquez ce qui suit [styles de fenêtre](../../mfc/reference/window-styles.md) à un contrôle d’édition.  
  
- **WS_CHILD** toujours.  
  
- **WS_VISIBLE** généralement.  
  
- **WS_DISABLED** rarement.  
  
- **WS_GROUP** pour regrouper des contrôles.  
  
- **WS_TABSTOP** pour inclure le contrôle d’édition dans l’ordre de tabulation.  
  
 Pour plus d’informations sur les styles de fenêtre, consultez la page [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&5;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_5.cpp)]  
  
##  <a name="createex"></a>CRichEditCtrl::CreateEx  
 Crée un contrôle (une fenêtre enfant) et l’associe à la `CRichEditCtrl` objet.  
  
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
 Spécifie le style du contrôle d’édition. Appliquer une combinaison des styles de fenêtre répertoriées dans le **remarques** section de [créer](#create) et [modifier les styles de contrôle](http://msdn.microsoft.com/library/windows/desktop/bb775464), décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure décrivant la taille et la position de la fenêtre doit être créée, dans les coordonnées clientes de `pParentWnd`.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parent du contrôle.  
  
 `nID`  
 ID de fenêtre enfant. du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Utilisez `CreateEx` au lieu de **créer** pour appliquer des styles étendus Windows, spécifiés par la préface de style étendu Windows **WS_EX_**.  
  
##  <a name="cricheditctrl"></a>CRichEditCtrl::CRichEditCtrl  
 Construit un objet `CRichEditCtrl`.  
  
```  
CRichEditCtrl();
```  
  
### <a name="remarks"></a>Notes  
 Utilisez [créer](#create) pour construire les fenêtres de contrôle RichEdit.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&6;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_6.cpp)]  
  
##  <a name="cut"></a>CRichEditCtrl::Cut  
 Supprimer (réduit) contrôle d’édition de la sélection actuelle (le cas échéant) de la riche et copie le texte supprimé dans le Presse-papiers.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Remarques  
 La suppression effectuée par **couper** puissent être annulées en appelant le [Annuler](#undo) fonction membre.  
  
 Pour supprimer la sélection en cours sans placer le texte supprimé dans le Presse-papiers, appelez le [clair](#clear) fonction membre.  
  
 Pour plus d’informations, consultez [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#7;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_7.cpp)]  
  
##  <a name="displayband"></a>CRichEditCtrl::DisplayBand  
 Affiche une partie du contenu du contrôle RichEdit (texte et les éléments OLE), précédemment mis en forme en [FormatRange](#formatrange).  
  
```  
BOOL DisplayBand(LPRECT pDisplayRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDisplayRect`  
 Pointeur vers un [RECT](../../mfc/reference/rect-structure1.md) ou [CRect](../../atl-mfc-shared/reference/crect-class.md) objet spécifiant la zone du périphérique pour afficher le texte.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’affichage du texte mis en forme réussit, sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le texte et les éléments OLE sont réduits à la zone spécifiée par le pointeur `pDisplayRect`.  
  
 Pour plus d’informations, consultez [EM_DISPLAYBAND](http://msdn.microsoft.com/library/windows/desktop/bb787997) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditCtrl::FormatRange](#formatrange).  
  
##  <a name="emptyundobuffer"></a>CRichEditCtrl::EmptyUndoBuffer  
 Réinitialise (clear) l’indicateur d’annulation de ce contrôle d’édition enrichi.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Notes  
 Le contrôle sera désormais impossible d’annuler la dernière opération de modification. L’indicateur d’annulation est défini chaque fois qu’une opération dans le contrôle rich edit peut être annulée.  
  
 L’indicateur d’annulation est automatiquement effacé lorsque vous appelez le [CWnd](../../mfc/reference/cwnd-class.md) fonction membre [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
 Pour plus d’informations, consultez [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&8;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_8.cpp)]  
  
##  <a name="findtext"></a>CRichEditCtrl::FindText  
 Recherche du texte dans le contrôle RichEdit.  
  
```  
long FindText(
    DWORD dwFlags,  
    FINDTEXTEX* pFindText) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Pour obtenir la liste des valeurs possibles, consultez la page `wParam` dans [EM_FINDTEXTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788011) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *pFindText*  
 Pointeur vers le [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) structure donnant aux paramètres de recherche et de retourner la plage où la correspondance a été trouvée.  
  
### <a name="return-value"></a>Valeur de retour  
 Position de base zéro du caractère de la correspondance suivante ; – 1 si aucune correspondance.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez rechercher soit vers le haut ou vers le bas en définissant les paramètres de plage appropriée le [structure CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) au sein de la structure la **FINDTEXTEX** structure.  
  
 Pour plus d’informations, consultez [EM_FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb788011) message et [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#9;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_9.cpp)]  
  
##  <a name="findwordbreak"></a>CRichEditCtrl::FindWordBreak  
 Recherche le prochain saut word avant ou après la position spécifiée par `nStart`.  
  
```  
DWORD FindWordBreak(
    UINT nCode,  
    DWORD nStart) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nCode`  
 Indique l’action à entreprendre. Pour obtenir la liste des valeurs possibles, consultez la description pour le paramètre `code` dans **EM_FINDWORDBREAK** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nStart`  
 Position du caractère de base zéro à partir duquel commencer.  
  
### <a name="return-value"></a>Valeur de retour  
 En fonction du paramètre `nCode`. Pour plus d’informations, consultez [EM_FINDWORDBREAK](http://msdn.microsoft.com/library/windows/desktop/bb788018) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez utiliser cette fonction membre pour récupérer des informations sur un caractère à une position donnée.  
  
##  <a name="formatrange"></a>CRichEditCtrl::FormatRange  
 Met en forme une plage de texte dans un contrôle rich edit pour un périphérique spécifique.  
  
```  
long FormatRange(
    FORMATRANGE* pfr,  
    BOOL bDisplay = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 *PFR*  
 Pointeur vers le [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) structure qui contient des informations sur le périphérique de sortie. **NULL** indique que les informations mises en cache dans le contrôle rich edit peuvent être libérées.  
  
 *bDisplay*  
 Indique si le texte doit être restitué. Si **FALSE**, le texte est mesuré seulement.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index du dernier caractère qui correspond à la région, plus un.  
  
### <a name="remarks"></a>Remarques  
 En règle générale, cet appel est suivi par un appel à [DisplayBand](#displayband).  
  
 Pour plus d’informations, consultez [EM_FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb788020) message et [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#10;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_10.cpp)]  
  
##  <a name="getcharpos"></a>CRichEditCtrl::GetCharPos  
 Obtient la position (coin supérieur gauche) d’un caractère donné dans cette `CRichEditCtrl` objet.  
  
```  
CPoint GetCharPos(long lChar) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lChar`  
 Index de base zéro du caractère.  
  
### <a name="return-value"></a>Valeur de retour  
 L’emplacement de l’angle supérieur gauche du caractère spécifié par `lChar`.  
  
### <a name="remarks"></a>Remarques  
 Le caractère est spécifié en donnant sa valeur d’index de base zéro. Si `lChar` est supérieur à l’index du dernier caractère dans ce `CRichEditCtrl` de l’objet, la valeur de retour spécifie les coordonnées de la position de caractère juste après le dernier caractère dans ce `CRichEditCtrl` objet.  
  
 Pour plus d’informations, consultez [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdefaultcharformat"></a>CRichEditCtrl::GetDefaultCharFormat  
 Obtient le caractère par défaut mise en forme des attributs du `CRichEditCtrl` objet.  
  
```  
DWORD GetDefaultCharFormat(CHARFORMAT& cf) const;  DWORD GetDefaultCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a **CHARFORMAT** structure holding the default character formatting attributes.  
  
 In the second version, a pointer to a **CHARFORMAT2** structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure, holding the default character formatting attributes.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specified the default character formatting attributes.  
  
### Remarks  
 For more information, see the **EM_GETCHARFORMAT** message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetDefaultCharFormat](#setdefaultcharformat).  
  
##  <a name="geteventmask"></a>  CRichEditCtrl::GetEventMask  
 Gets the event mask for this `CRichEditCtrl` object.  
  
```  
GetEventMask() long const ;  
```  
  
### Return Value  
 The event mask for this `CRichEditCtrl` object.  
  
### Remarks  
 The event mask specifies which notification messages the `CRichEditCtrl` object sends to its parent window.  
  
 For more information, see [EM_GETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb788032) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [CRichEditCtrl::SetEventMask](#seteventmask).  
  
##  <a name="getfirstvisibleline"></a>  CRichEditCtrl::GetFirstVisibleLine  
 Determines the topmost visible line in this `CRichEditCtrl` object.  
  
```  
int GetFirstVisibleLine() const ;  
```  
  
### Return Value  
 Zero-based index of the uppermost visible line in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#11](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_11.cpp)]  
  
##  <a name="getiricheditole"></a>  CRichEditCtrl::GetIRichEditOle  
 Accesses the **IRichEditOle** interface for this `CRichEditCtrl` object.  
  
```  
IRichEditOle * GetIRichEditOle() const ;  
```  
  
### Return Value  
 Pointer to the [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface that can be used to access this `CRichEditCtrl` object's OLE functionality; **NULL** if the interface is not accessible.  
  
### Remarks  
 Use this interface to access this `CRichEditCtrl` object's OLE functionality.  
  
 For more information, see [EM_GETOLEINTERFACE](http://msdn.microsoft.com/library/windows/desktop/bb788041) message and [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlimittext"></a>  CRichEditCtrl::GetLimitText  
 Gets the text limit for this `CRichEditCtrl` object.  
  
```  
GetLimitText() long const ;  
```  
  
### Return Value  
 The current text limit, in bytes, for this `CRichEditCtrl` object.  
  
### Remarks  
 The text limit is the maximum amount of text, in bytes, the rich edit control can accept.  
  
 For more information, see [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#12](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_12.cpp)]  
  
##  <a name="getline"></a>  CRichEditCtrl::GetLine  
 Retrieves a line of text from this `CRichEditCtrl` object.  
  
```  
int GetLine (int nIndex,  
    LPTSTR lpszBuffer) const ;  
  
int GetLine (int nIndex,  
    LPTSTR lpszBuffer,  
    int nMaxLength) const ;  
```  
  
### Parameters  
 `nIndex`  
 Zero-based index of the line to retrieve.  
  
 `lpszBuffer`  
 Points to the buffer to receive the text. The first word of the buffer must specify the maximum number of bytes that can be copied into the buffer.  
  
 `nMaxLength`  
 Maximum number of characters that can be copied into `lpszBuffer`. The second form of `GetLine` places this value into the first word of the buffer specified by `lpszBuffer`.  
  
### Return Value  
 The number of characters copied into `lpszBuffer`.  
  
### Remarks  
 The copied line does not contain a terminating null character.  
  
> [!NOTE]
>  Because the first word of the buffer stores the number of characters to be copied, make sure that your buffer is at least 4 bytes long.  
  
 For more information, see [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>  CRichEditCtrl::GetLineCount  
 Retrieves the number of lines in the `CRichEditCtrl` object.  
  
```  
int GetLineCount() const ;  
```  
  
### Return Value  
 The number of lines in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#13](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_13.cpp)]  
  
##  <a name="getmodify"></a>  CRichEditCtrl::GetModify  
 Determines if the contents of this `CRichEditCtrl` object have been modified.  
  
```  
BOOL GetModify() const ;  
```  
  
### Return Value  
 Nonzero if the text in this `CRichEditCtrl` object has been modified; otherwise 0.  
  
### Remarks  
 Windows maintains an internal flag indicating whether the contents of the rich edit control have been changed. This flag is cleared when the edit control is first created and can also be cleared by calling the [SetModify](#setmodify) member function.  
  
 For more information, see [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#14](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_14.cpp)]  
  
##  <a name="getoptions"></a>  CRichEditCtrl::GetOptions  
 Retrieves the options currently set for the rich edit control.  
  
```  
UINT GetOptions() const ;  
```  
  
### Return Value  
 A combination of the current option flag values. For a list of these values, see the *fOptions* parameter in the [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getparaformat"></a>  CRichEditCtrl::GetParaFormat  
 Gets the paragraph formatting attributes of the current selection.  
  
```  
GetParaFormat(PARAFORMAT& pf) DWORD const ;  GetParaFormat(PARAFORMAT2& pf) DWORD const ;  ```  
  
### <a name="parameters"></a>Paramètres  
 `pf`  
 Dans la première version, un pointeur vers un [RAJOUTER](http://msdn.microsoft.com/library/windows/desktop/bb787940) structure contenant les attributs de la sélection actuelle de paragraphes.  
  
 Dans la deuxième version, un pointeur vers un [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) structure, qui est une extension Rich Edit 2.0 à la **RAJOUTER** structure, contenant le caractère par défaut les attributs de mise en forme.  
  
### <a name="return-value"></a>Valeur de retour  
 Le **dwMask** membre de données de `pf`. Il spécifie le paragraphe mise en forme des attributs qui sont cohérentes dans la sélection actuelle.  
  
### <a name="remarks"></a>Remarques  
 Si plusieurs paragraphes sont sélectionnés, `pf` reçoit les attributs du premier paragraphe sélectionné. La valeur de retour spécifie quels attributs sont cohérentes dans la sélection.  
  
 Pour plus d’informations, consultez la [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) message et **RAJOUTER** et **PARAFORMAT2** structures dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditCtrl::SetParaFormat](#setparaformat).  
  
##  <a name="getpunctuation"></a>CRichEditCtrl::GetPunctuation  
 Obtient les caractères de ponctuation en cours dans un contrôle rich edit.  
  
```  
BOOL GetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `fType`  
 L’indicateur de type de ponctuation, comme décrit dans la `fType` paramètre de [EM_GETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774184) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpPunc`  
 Un pointeur vers un [ponctuation](http://msdn.microsoft.com/library/windows/desktop/bb787944) de structure, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi, sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est disponible avec uniquement les versions asiatiques du système d’exploitation.  
  
##  <a name="getrect"></a>CRichEditCtrl::GetRect  
 Récupère le rectangle de mise en forme de ce `CRichEditCtrl` objet.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md) ou pointeur vers un [RECT](../../mfc/reference/rect-structure1.md) pour recevoir le rectangle de mise en forme de ce `CRichEditCtrl` objet.  
  
### <a name="remarks"></a>Remarques  
 Le rectangle de mise en forme est le rectangle englobant pour le texte. Cette valeur est indépendante de la taille de la `CRichEditCtrl` objet.  
  
 Pour plus d’informations, consultez [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [LimitText](#limittext).  
  
##  <a name="getredoname"></a>CRichEditCtrl::GetRedoName  
 Récupère le type de l’action suivante disponible dans la file d’attente de restauration par progression, le cas échéant.  
  
```  
UNDONAMEID GetRedoName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 En cas de réussite, `GetRedoName` retourne le [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) type d’énumération indiquant le type de l’action suivante dans la file d’attente de restauration par progression du contrôle. Si la file d’attente de restauration par progression est vide, ou si l’action de restauration par progression dans la file d’attente est de type inconnu, `GetRedoName` renvoie la valeur 0.  
  
### <a name="remarks"></a>Notes  
 Les types d’actions qui peuvent être annulées ou rétablies incluent en tapant delete, glisser-déplacer, couper et coller. Cette information peut être utile pour les applications qui fournissent une interface utilisateur améliorée pour les opérations Annuler et rétablir, par exemple une zone de liste déroulante des actions redoable.  
  
##  <a name="getsel"></a>CRichEditCtrl::GetSel  
 Récupère les limites de la sélection actuelle dans ce `CRichEditCtrl` objet.  
  
```  
void GetSel(CHARRANGE& cr) const;  
  
void GetSel(
    long& nStartChar,  
    long& nEndChar) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `cr`  
 Référence à un [structure CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) structure pour recevoir les limites de la sélection actuelle.  
  
 `nStartChar`  
 Index de base zéro du premier caractère de la sélection actuelle.  
  
 `nEndChar`  
 Index de base zéro du dernier caractère de la sélection actuelle.  
  
### <a name="remarks"></a>Remarques  
 Les deux formes de cette fonction fournissent d’autres méthodes permettant d’obtenir les limites de la sélection. Suivent de brèves descriptions de ces formes :  
  
- **Fonction membre GetSel (** `cr` **)** ce formulaire utilise le **structure CHARRANGE** structure avec son **cpMin** et **cpMax** membres pour retourner les limites.  
  
- **Fonction membre GetSel (** `nStartChar` **,** `nEndChar` **)** ce formulaire retourne les limites dans les paramètres `nStartChar` et `nEndChar`.  
  
 La sélection contient tous les éléments, si le début ( **cpMin** ou `nStartChar`) est 0 et la fin ( **cpMax** ou `nEndChar`) est – 1.  
  
 Pour plus d’informations, consultez [EM_EXGETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788001) message et [structure CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#15;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_15.cpp)]  
  
##  <a name="getselectioncharformat"></a>CRichEditCtrl::GetSelectionCharFormat  
 Obtient le caractère de mise en forme les attributs de la sélection actuelle.  
  
```  
DWORD GetSelectionCharFormat(CHARFORMAT& cf) const;  DWORD GetSelectionCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) structure to receive the character formatting attributes of the current selection.  
  
 In the second version, a pointer to a [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure to receive the character formatting attributes of the current selection.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specifies the character formatting attributes that are consistent throughout the current selection.  
  
### Remarks  
 The `cf` parameter receives the attributes of the first character in the current selection. The return value specifies which attributes are consistent throughout the selection.  
  
 For more information, see the [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetSelectionCharFormat](#setselectioncharformat).  
  
##  <a name="getselectiontype"></a>  CRichEditCtrl::GetSelectionType  
 Determines the selection type in this `CRichEditCtrl` object.  
  
```  
GetSelectionType() WORD const ;  
```  
  
### Return Value  
 Flags indicating the contents of the current selection. A combination of the following flags:  
  
- `SEL_EMPTY` Indicates that there is no current selection.  
  
- `SEL_TEXT` Indicates that the current selection contains text.  
  
- `SEL_OBJECT` Indicates that the current selection contains at least one OLE item.  
  
- `SEL_MULTICHAR` Indicates that the current selection contains more than one character of text.  
  
- `SEL_MULTIOBJECT` Indicates that the current selection contains more than one OLE object.  
  
### Remarks  
 For more information, see [EM_SELECTIONTYPE](http://msdn.microsoft.com/library/windows/desktop/bb774223) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#16](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_16.cpp)]  
  
##  <a name="getseltext"></a>  CRichEditCtrl::GetSelText  
 Retrieves the text from the current selection in this `CRichEditCtrl` object.  
  
```  
GetSelText(LPSTR lpBuf) long const ;  CString GetSelText() const ;  ```  
  
### <a name="parameters"></a>Paramètres  
 `lpBuf`  
 Pointeur vers la mémoire tampon qui recevra le texte de la sélection actuelle.  
  
### <a name="return-value"></a>Valeur de retour  
 Dépend de la forme :  
  
- **Fonction membre GetSelText (** `lpBuf` **)** le nombre de caractères copiés dans `lpBuf`, sans le caractère null de fin.  
  
- **() Fonction membre GetSelText** chaîne contenant la sélection actuelle.  
  
### <a name="remarks"></a>Remarques  
 Si vous utilisez la première forme, **fonction membre GetSelText (** `lpBuf` **)**, vous devez vous assurer que la mémoire tampon est assez grande pour le texte qu’il reçoit. Appelez [fonction membre GetSel](#getsel) pour déterminer le nombre de caractères dans la sélection actuelle.  
  
 Pour plus d’informations, consultez [EM_GETSELTEXT](http://msdn.microsoft.com/library/windows/desktop/bb774190) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditCtrl::GetSelectionType](#getselectiontype).  
  
##  <a name="gettextlength"></a>CRichEditCtrl::GetTextLength  
 Récupère la longueur du texte, en caractères, dans ce `CRichEditCtrl` objet, non compris le caractère null de fin.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur du texte dans ce `CRichEditCtrl` objet.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#17;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_17.cpp)]  
  
##  <a name="gettextlengthex"></a>CRichEditCtrl::GetTextLengthEx  
 Calcule la longueur du texte dans le contrôle d’édition enrichi.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Valeur spécifiant la méthode à utiliser pour déterminer la longueur du texte. Ce membre peut être une ou plusieurs des valeurs répertoriées dans le membre d’indicateurs de [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) décrits dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `uCodePage`  
 Page de codes pour la traduction (CP_ACP pour la Page de codes ANSI, 1200 pour Unicode).  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de caractères ou d’octets dans le contrôle d’édition. Si les indicateurs incompatibles ont été définis `dwFlags`, cette fonction membre retourne `E_INVALIDARG`.  
  
### <a name="remarks"></a>Remarques  
 `GetTextLengthEx`Fournit des méthodes supplémentaires permettant de déterminer la longueur du texte. Il prend en charge la fonctionnalité Rich Edit 2.0. Consultez la page [sur les contrôles Rich Edit](http://msdn.microsoft.com/library/windows/desktop/bb787873) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]pour plus d’informations.  
  
##  <a name="gettextmode"></a>CRichEditCtrl::GetTextMode  
 Récupère le niveau de mode et annulation d’opérations de texte actuel d’un contrôle RichEdit.  
  
```  
UINT GetTextMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un ensemble de bits indicateurs de la [TEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774364) type énumération, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Les indicateurs indiquent le mode texte actuel et annuler au niveau du contrôle.  
  
##  <a name="gettextrange"></a>CRichEditCtrl::GetTextRange  
 Obtient la plage de caractères spécifiée.  
  
```  
int GetTextRange(
    int nFirst,  
    int nLast,  
    CString& refString) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nFirst`  
 L’index de position de caractère précédant le premier caractère de la plage.  
  
 `nLast`  
 Position du caractère qui suit immédiatement le dernier caractère de la plage.  
  
 `refString`  
 Une référence à un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet qui recevra le texte.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de caractères copiés, non compris le caractère null de fin.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [EM_GETTEXTRANGE](http://msdn.microsoft.com/library/windows/desktop/bb774199) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `GetTextRange`prend en charge la fonctionnalité Rich Edit 2.0. Consultez la page [sur les contrôles Rich Edit](http://msdn.microsoft.com/library/windows/desktop/bb787873) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]pour plus d’informations.  
  
##  <a name="getundoname"></a>CRichEditCtrl::GetUndoName  
 Récupère le type de l’action suivante disponible dans la file d’attente, le cas échéant.  
  
```  
UNDONAMEID GetUndoName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si une opération d’annulation est dans la file d’attente du contrôle, `GetUndoName` retourne le [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) type d’énumération indiquant le type de l’action suivante dans la file d’attente. Si la file d’attente est vide ou si l’opération d’annulation dans la file d’attente est de type inconnu, `GetUndoName` renvoie la valeur 0.  
  
### <a name="remarks"></a>Remarques  
 Les types d’actions qui peuvent être annulées ou rétablies incluent en tapant delete, glisser-déplacer, couper et coller. Ces informations peuvent être utiles pour les applications qui fournissent une interface utilisateur améliorée pour les opérations Annuler et rétablir, par exemple une zone de liste déroulante des actions qui peuvent être annulées.  
  
##  <a name="getwordwrapmode"></a>CRichEditCtrl::GetWordWrapMode  
 Récupère le retour actuel et les options de dernières word du contrôle RichEdit.  
  
```  
UINT GetWordWrapMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le retour en cours et lexicale options. Ces options sont décrites dans [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est disponible uniquement pour les versions asiatiques du système d’exploitation.  
  
##  <a name="hideselection"></a>CRichEditCtrl::HideSelection  
 Modifie la visibilité de la sélection.  
  
```  
void HideSelection(
    BOOL bHide,  
    BOOL bPerm);
```  
  
### <a name="parameters"></a>Paramètres  
 `bHide`  
 Indique si la sélection doit être affichée ou masquée, **TRUE** pour masquer la sélection.  
  
 `bPerm`  
 Indique si cette modification de la visibilité de la sélection doit être permanente.  
  
### <a name="remarks"></a>Remarques  
 Lors de la `bPerm` est **TRUE**, il modifie le `ECO_NOHIDESEL` option pour ce `CRichEditCtrl` objet. Pour obtenir une brève description de cette option, consultez la page [SetOptions](#setoptions). Vous pouvez utiliser cette fonction pour définir toutes les options de cet `CRichEditCtrl` objet.  
  
 Pour plus d’informations, consultez [EM_HIDESELECTION](http://msdn.microsoft.com/library/windows/desktop/bb774210) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#18;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_18.cpp)]  
  
##  <a name="limittext"></a>CRichEditCtrl::LimitText  
 Limite la longueur du texte que l’utilisateur peut entrer dans un contrôle d’édition.  
  
```  
void LimitText(long nChars = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `nChars`  
 Spécifie la longueur (en octets) du texte que l’utilisateur peut entrer. Si ce paramètre est 0 (valeur par défaut), la longueur du texte est définie à 64 Ko.  
  
### <a name="remarks"></a>Remarques  
 Modification de la limite de texte restreint uniquement le texte que l’utilisateur peut entrer. Il n’a aucun effet sur le texte déjà dans le contrôle d’édition, ni n’affecte la longueur du texte copié dans le contrôle d’édition par le [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) fonction membre dans `CWnd`. Si une application utilise le `SetWindowText` à placer plus de texte dans un contrôle d’édition que celle spécifiée dans l’appel de fonction `LimitText`, l’utilisateur peut supprimer du texte dans le contrôle d’édition. Toutefois, la limite de texte empêche l’utilisateur de remplacer le texte existant par un nouveau texte, à moins que la suppression de la sélection actuelle provoque le texte passe en dessous de la limite de texte.  
  
> [!NOTE]
>  Pour la limite de texte, chaque élément OLE est considérée comme un caractère unique.  
  
 Pour plus d’informations, consultez [EM_EXLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788003) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&19;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_19.cpp)]  
  
##  <a name="linefromchar"></a>CRichEditCtrl::LineFromChar  
 Récupère le numéro de la ligne qui contient l’index de caractère spécifié.  
  
```  
long LineFromChar(long nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Contient la valeur d’index de base zéro du caractère souhaité dans le texte du contrôle d’édition, ou -1. Si `nIndex` est –&1;, il spécifie la ligne actuelle, autrement dit, la ligne qui contient le point d’insertion.  
  
### <a name="return-value"></a>Valeur de retour  
 Le numéro de ligne de base zéro de la ligne contenant l’index de caractère spécifié par `nIndex`. Si `nIndex` est –&1;, le numéro de la ligne qui contient le premier caractère de la sélection est retourné. S’il n’existe aucune sélection, le numéro de ligne actuel est retourné.  
  
### <a name="remarks"></a>Notes  
 Un index de caractère est le nombre de caractères à partir du début du contrôle RichEdit. Pour le comptage des caractères, un élément OLE est compté comme un caractère unique.  
  
 Pour plus d’informations, consultez [EM_EXLINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb788005) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#20;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_20.cpp)]  
  
##  <a name="lineindex"></a>CRichEditCtrl::LineIndex  
 Récupère l’index de caractère d’une ligne dans cette `CRichEditCtrl` objet.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nLine`  
 Contient la valeur d’index de la ligne dans le texte du contrôle d’édition, ou -1. Si `nLine` est –&1;, il spécifie la ligne actuelle, autrement dit, la ligne qui contient le point d’insertion.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index de caractère de la ligne spécifiée dans `nLine` ou -1 si le numéro de ligne spécifié est supérieur, puis le nombre de lignes dans le contrôle d’édition.  
  
### <a name="remarks"></a>Notes  
 L’index de caractère est le nombre de caractères à partir du début du contrôle rich edit de la ligne spécifiée.  
  
 Pour plus d’informations, consultez [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&21;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_21.cpp)]  
  
##  <a name="linelength"></a>CRichEditCtrl::LineLength  
 Extrait la longueur d’une ligne dans un contrôle rich edit.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nLine`  
 Spécifie l’index de caractère d’un caractère dans la ligne dont la longueur doit être récupéré. Si ce paramètre est –&1;, la longueur de la ligne actuelle (la ligne contenant le signe insertion) est retournée, non compris la longueur d’un sélectionné du texte dans la ligne. Lorsque `LineLength` est appelée pour un contrôle d’édition sur une ligne, ce paramètre est ignoré.  
  
### <a name="return-value"></a>Valeur de retour  
 Lors de la `LineLength` est appelée pour un contrôle d’édition de plusieurs lignes, la valeur de retour est la longueur (en octets) de la ligne spécifiée par `nLine`. Lorsque `LineLength` est appelée pour un contrôle d’édition sur une ligne, la valeur de retour est la longueur (en octets) du texte dans le contrôle d’édition.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le [LineIndex](#lineindex) fonction membre pour récupérer l’index de caractère pour un numéro de ligne donné dans cette `CRichEditCtrl` objet.  
  
 Pour plus d’informations, consultez [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [LineIndex](#lineindex).  
  
##  <a name="linescroll"></a>CRichEditCtrl::LineScroll  
 Fait défiler le texte d’un contrôle d’édition de plusieurs lignes.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `nLines`  
 Spécifie le nombre de lignes à faire défiler verticalement.  
  
 `nChars`  
 Spécifie le nombre de positions de caractère pour faire défiler horizontalement. Cette valeur est ignorée si le contrôle rich edit est la **ES_RIGHT** ou **ES_CENTER** style. [Modifier les styles](../../mfc/reference/edit-styles.md) sont spécifiées dans [créer](#create).  
  
### <a name="remarks"></a>Remarques  
 Le contrôle d’édition ne défile pas verticalement au-delà de la dernière ligne de texte dans le contrôle d’édition. Si la ligne en cours ainsi que le nombre de lignes spécifié par `nLines` dépasse le nombre total de lignes dans le contrôle d’édition, la valeur est ajustée afin que la dernière ligne du contrôle d’édition faites défiler vers le haut de la fenêtre de contrôle d’édition.  
  
 `LineScroll`peut être utilisé pour faire défiler horizontalement au-delà du dernier caractère de n’importe quelle ligne.  
  
 Pour plus d’informations, consultez [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="paste"></a>CRichEditCtrl::Paste  
 Insère les données du Presse-papiers dans le `CRichEditCtrl` au point d’insertion, l’emplacement du signe insertion.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Remarques  
 Données sont insérées que si le Presse-papiers contient des données dans un format reconnu.  
  
 Pour plus d’informations, consultez [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#22;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_22.cpp)]  
  
##  <a name="pastespecial"></a>CRichEditCtrl::PasteSpecial  
 Colle les données dans un format de Presse-papiers spécifique dans ce `CRichEditCtrl` objet.  
  
```  
void PasteSpecial(
    UINT nClipFormat,  
    DWORD dvAspect = 0,  
    HMETAFILE hMF = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 *nClipFormat*  
 Format de Presse-papiers pour coller dans ce `CRichEditCtrl` objet.  
  
 *dvAspect*  
 Aspect de périphérique pour les données à récupérer à partir du Presse-papiers.  
  
 *hMF*  
 Handle du métafichier contenant la vue sous forme d’icône de l’objet à coller.  
  
### <a name="remarks"></a>Notes  
 Le nouveau matériel est inséré au point d’insertion, l’emplacement du signe insertion.  
  
 Pour plus d’informations, consultez [EM_PASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/bb774214) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&23;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_23.cpp)]  
  
##  <a name="posfromchar"></a>CRichEditCtrl::PosFromChar  
 Récupère les coordonnées de la zone client d’un caractère spécifié dans un contrôle d’édition.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nChar`  
 Index de base zéro du caractère.  
  
### <a name="return-value"></a>Valeur de retour  
 Position de caractère, (x, y). Pour un contrôle d’édition sur une ligne, la coordonnée y est toujours zéro.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="redo"></a>CRichEditCtrl::Redo  
 Rétablit l’action suivante dans la file d’attente de restauration par progression du contrôle.  
  
```  
BOOL Redo();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [EM_REDO](http://msdn.microsoft.com/library/windows/desktop/bb774218) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="replacesel"></a>CRichEditCtrl::ReplaceSel  
 Remplace la sélection actuelle dans ce `CRichEditCtrl` objet avec le texte spécifié.  
  
```  
void ReplaceSel(
    LPCTSTR lpszNewText,  
    BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszNewText`  
 Pointeur vers une chaîne terminée par le caractère null qui contient le texte de remplacement.  
  
 `bCanUndo`  
 Pour spécifier que cette fonction peut être annulée, définissez la valeur de ce paramètre pour **TRUE**. La valeur par défaut est **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Remplacez tout le texte dans ce `CRichEditCtrl` de l’objet, utilisez [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
 S’il n’existe pas de sélection, le texte de remplacement est inséré au point d’insertion, autrement dit, l’emplacement du signe insertion actuel.  
  
 Cette fonction mettra en forme le texte inséré avec la mise en forme de caractères existant. Lors du remplacement de l’ensemble du texte (en appelant `SetSel`(0, -1) avant d’appeler `ReplaceSel`), il existe un caractère de fin de paragraphe qui conserve la mise en forme le paragraphe précédent, qui en est hérité par le texte qui vient d’être inséré.  
  
 Pour plus d’informations, consultez [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [LineIndex](#lineindex).  
  
##  <a name="requestresize"></a>CRichEditCtrl::RequestResize  
 Cela force `CRichEditCtrl` objet vers lequel envoyer **EN_REQUESTRESIZE** des messages de notification à sa fenêtre parente.  
  
```  
void RequestResize();
```  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utile lors de la [CWnd::OnSize](../../mfc/reference/cwnd-class.md#onsize) de traitement pour un sans marge inférieure `CRichEditCtrl` objet.  
  
 Pour plus d’informations, consultez le [EM_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb774220) message et **contrôles Rich Edit sans fin** section de [sur les contrôles Rich Edit](http://msdn.microsoft.com/library/windows/desktop/bb787873) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setautourldetect"></a>CRichEditCtrl::SetAutoURLDetect  
 Définit le contrôle d’édition enrichi pour détecter automatiquement une URL.  
  
```  
BOOL SetAutoURLDetect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bEnable`  
 Spécifie si le contrôle est configuré pour détecter automatiquement les URL. Si **TRUE**, il est activé. Si **FALSE**, elle est désactivée.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro en cas de réussite, sinon différente de zéro. Par exemple, le message peut échouer en raison d’une insuffisance de mémoire.  
  
### <a name="remarks"></a>Remarques  
 S’il est activé, le contrôle rich edit analyse le texte pour déterminer si elle correspond à un format d’URL standard. Pour obtenir la liste de ces formats d’URL, consultez [EM_AUTOURLDETECT](http://msdn.microsoft.com/library/windows/desktop/bb787991) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Ne définissez pas `SetAutoURLDetect` à **TRUE** si votre contrôle d’édition utilise le **CFE_LINK** effet de texte autour des URL. `SetAutoURLDetect`permet à cet effet pour les URL et la désactive pour tous les autres types de texte. Consultez la page [EN_LINK](http://msdn.microsoft.com/library/windows/desktop/bb787970) pour plus d’informations sur la **CFE_LINK** effet.  
  
##  <a name="setbackgroundcolor"></a>CRichEditCtrl::SetBackgroundColor  
 Définit la couleur d’arrière-plan de ce `CRichEditCtrl` objet.  
  
```  
COLORREF SetBackgroundColor(
    BOOL bSysColor,  
    COLORREF cr);
```  
  
### <a name="parameters"></a>Paramètres  
 `bSysColor`  
 Indique si la couleur d’arrière-plan doit être définie sur la valeur du système. Si cette valeur est **TRUE**, `cr` est ignoré.  
  
 `cr`  
 La couleur d’arrière-plan demandé. Utilisé uniquement si `bSysColor` est **FALSE**.  
  
### <a name="return-value"></a>Valeur de retour  
 La couleur d’arrière-plan précédente pour ce `CRichEditCtrl` objet.  
  
### <a name="remarks"></a>Remarques  
 La couleur d’arrière-plan peut être définie à la valeur système ou à une certaine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur.  
  
 Pour plus d’informations, consultez [EM_SETBKGNDCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774228) message et [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#24;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_24.cpp)]  
  
##  <a name="setdefaultcharformat"></a>CRichEditCtrl::SetDefaultCharFormat  
 Définit le caractère de mise en forme des attributs pour le nouveau texte dans ce `CRichEditCtrl` objet.  
  
```  
BOOL SetDefaultCharFormat(CHARFORMAT& cf);  
BOOL SetDefaultCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Paramètres  
 `cf`  
 Dans la première version, un pointeur vers un [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) structure contenant le caractère par défaut nouveaux attributs de mise en forme.  
  
 Dans la deuxième version, un pointeur vers un [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure, qui est une extension Rich Edit 2.0 à la **CHARFORMAT** structure, qui contient le caractère par défaut les attributs de mise en forme.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Seuls les attributs spécifiés par le **dwMask** membre `cf` sont modifiés par cette fonction.  
  
 Pour plus d’informations, consultez la [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) message et **CHARFORMAT** et **CHARFORMAT2** structures dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#25;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_25.cpp)]  
  
##  <a name="seteventmask"></a>CRichEditCtrl::SetEventMask  
 Définit le masque d’événement de ce `CRichEditCtrl` objet.  
  
```  
DWORD SetEventMask(DWORD dwEventMask);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwEventMask*  
 Le nouveau masque d’événements pour cet `CRichEditCtrl` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Le masque d’événement précédent.  
  
### <a name="remarks"></a>Remarques  
 Le masque d’événement indique que les messages de notification du `CRichEditCtrl` objet envoie à sa fenêtre parente.  
  
 Pour plus d’informations, consultez [EM_SETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb774238) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#26;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_26.cpp)]  
  
##  <a name="setmodify"></a>CRichEditCtrl::SetModify  
 Active ou désactive l’indicateur modifié pour un contrôle d’édition.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bModified`  
 Une valeur de **TRUE** indique que le texte a été modifié et la valeur **FALSE** indique qu’il est modifié. Par défaut, l’indicateur modifié est défini.  
  
### <a name="remarks"></a>Remarques  
 L’indicateur modifié indique si le texte dans le contrôle d’édition a été modifié. Elle est définie automatiquement lorsque l’utilisateur modifie le texte. Sa valeur peut être récupérée avec la [GetModify](#getmodify) fonction membre.  
  
 Pour plus d’informations, consultez [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [GetModify](#getmodify).  
  
##  <a name="setolecallback"></a>CRichEditCtrl::SetOLECallback  
 Cela donne `CRichEditCtrl` objet une **IRichEditOleCallback** objet à utiliser pour accéder aux informations et ressources liées à OLE.  
  
```  
BOOL SetOLECallback(IRichEditOleCallback* pCallback);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCallback`  
 Pointeur vers un [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) objet que cet `CRichEditCtrl` objet utilisera pour obtenir des informations et des ressources liées à OLE.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cela `CRichEditCtrl` objet appellera [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) pour incrémenter le décompte d’utilisation de l’objet COM spécifié par `pCallback`.  
  
 Pour plus d’informations, consultez [EM_SETOLECALLBACK](http://msdn.microsoft.com/library/windows/desktop/bb774252) message et [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) de l’interface dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setoptions"></a>CRichEditCtrl::SetOptions  
 Définit les options pour ce `CRichEditCtrl` objet.  
  
```  
void SetOptions(
    WORD wOp,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 *wOp*  
 Indique le type d’opération. Une des valeurs suivantes :  
  
- `ECOOP_SET`Définir les options à ceux spécifiés par `dwFlags`.  
  
- `ECOOP_OR`Combiner les options actuelles avec celles spécifiées par `dwFlags`.  
  
- `ECOOP_AND`Conserver uniquement les options en cours sont également spécifiées par `dwFlags`.  
  
- `ECOOP_XOR`Conserver uniquement les options actuelles sont *pas* spécifié par `dwFlags`.  
  
 `dwFlags`  
 Options de modification riches. Les valeurs d’indicateur sont répertoriées dans la section Notes.  
  
### <a name="remarks"></a>Remarques  
 Les options peuvent être une combinaison des valeurs suivantes :  
  
- `ECO_AUTOWORDSELECTION`Sélection automatique des mots sur double-cliquez sur.  
  
- `ECO_AUTOVSCROLL`Défile automatiquement le texte à droite de 10 caractères lorsque l’utilisateur tape un caractère à la fin de la ligne. Lorsque l’utilisateur appuie sur la touche entrée, le contrôle défile tout le texte à la position zéro.  
  
- `ECO_AUTOHSCROLL`Fait défiler automatiquement le texte d’une page lorsque l’utilisateur appuie sur la touche entrée sur la dernière ligne.  
  
- `ECO_NOHIDESEL`Inverse le comportement par défaut pour un contrôle d’édition. Le comportement par défaut masque la sélection lorsque le contrôle perd le focus d’entrée et affiche la sélection lorsque le contrôle reçoit le focus d’entrée. Si vous spécifiez `ECO_NOHIDESEL`, le texte sélectionné est inversé, même si le contrôle n’a pas le focus.  
  
- `ECO_READONLY`Empêche l’utilisateur de taper ou de modifier du texte dans le contrôle d’édition.  
  
- `ECO_WANTRETURN`Spécifie qu’un retour chariot est insérée lorsque l’utilisateur appuie sur la touche entrée lors de la saisie de texte dans un contrôle multiligne RichEdit dans une boîte de dialogue. Si vous ne spécifiez pas ce style, en appuyant sur la touche entrée envoie une commande à la fenêtre parente du contrôle RichEdit qui reproduit en cliquant sur le bouton par défaut de la fenêtre parente (par exemple, le bouton OK dans une boîte de dialogue). Ce style n’a aucun effet sur une seule ligne contrôle d’édition.  
  
- `ECO_SAVESEL`Conserve la sélection lorsque le contrôle perd le focus. Par défaut, tout le contenu du contrôle est sélectionné lorsqu’elle reprend le focus.  
  
- `ECO_VERTICAL`Dessine le texte et les objets dans le sens vertical. Disponible pour les langues asiatiques uniquement.  
  
 Pour plus d’informations, consultez [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[27 NVC_MFC_CRichEditCtrl](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_27.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditCtrl::SetParaFormat  
 Définit la mise en forme d’attributs pour la sélection actuelle dans ce paragraphe `CRichEditCtrl` objet.  
  
```  
BOOL SetParaFormat(PARAFORMAT& pf);  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Paramètres  
 `pf`  
 Dans la première version, un pointeur vers un [RAJOUTER](http://msdn.microsoft.com/library/windows/desktop/bb787940) structure contenant la nouvelle valeur par défaut des attributs de mise en forme de paragraphe.  
  
 Dans la deuxième version, un pointeur vers un [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) structure, qui est une extension Rich Edit 2.0 à la **RAJOUTER** structure, contenant le caractère par défaut les attributs de mise en forme.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Seuls les attributs spécifiés par le **dwMask** membre `pf` sont modifiés par cette fonction.  
  
 Pour plus d’informations, consultez la [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) message et **RAJOUTER** et **PARAFORMAT2** structures dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#28;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_28.cpp)]  
  
##  <a name="setpunctuation"></a>CRichEditCtrl::SetPunctuation  
 Définit la ponctuation dans un contrôle rich edit.  
  
```  
BOOL SetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc);
```  
  
### <a name="parameters"></a>Paramètres  
 `fType`  
 L’indicateur de signes de ponctuation. Pour obtenir la liste des valeurs possibles, consultez la `fType` paramètre [EM_SETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774278) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpPunc`  
 Un pointeur vers un [ponctuation](http://msdn.microsoft.com/library/windows/desktop/bb787944) de structure, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération réussit, sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est disponible pour les langues asiatiques uniquement des versions du système d’exploitation.  
  
##  <a name="setreadonly"></a>CRichEditCtrl::SetReadOnly  
 Modifications de la `ECO_READONLY` option pour ce `CRichEditCtrl` objet.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bReadOnly`  
 Indique si cette `CRichEditCtrl` objet doit être en lecture seule.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Pour obtenir une brève description de cette option, consultez la page [SetOptions](#setoptions). Vous pouvez utiliser cette fonction pour définir toutes les options de cet `CRichEditCtrl` objet.  
  
 Pour plus d’informations, consultez [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#29;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_29.cpp)]  
  
##  <a name="setrect"></a>CRichEditCtrl::SetRect  
 Définit le rectangle de mise en forme de ce `CRichEditCtrl` objet.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md) ou pointeur vers un [RECT](../../mfc/reference/rect-structure1.md) qui indique les nouvelles limites du rectangle de mise en forme.  
  
### <a name="remarks"></a>Remarques  
 Le rectangle de mise en forme est le rectangle de limitation pour le texte. Le rectangle de limitation est indépendant de la taille de la fenêtre du contrôle RichEdit. Lorsque cette `CRichEditCtrl` objet est créé, le rectangle de mise en forme est la même taille que la zone cliente de la fenêtre. Utilisez `SetRect` pour rendre le rectangle de mise en forme est supérieure ou inférieure de la fenêtre d’édition enrichi.  
  
 Pour plus d’informations, consultez [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[30 NVC_MFC_CRichEditCtrl](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_30.cpp)]  
  
##  <a name="setsel"></a>CRichEditCtrl::SetSel  
 Définit la sélection dans cette `CRichEditCtrl` objet.  
  
```  
void SetSel(
    long nStartChar,  
    long nEndChar);  
  
void SetSel(CHARRANGE& cr);
```  
  
### <a name="parameters"></a>Paramètres  
 `nStartChar`  
 Index de base zéro du premier caractère de la sélection.  
  
 `nEndChar`  
 Index de base zéro du dernier caractère de la sélection.  
  
 `cr`  
 [Structure CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) structure qui contient les limites de la sélection actuelle.  
  
### <a name="remarks"></a>Remarques  
 Les deux formes de cette fonction fournissent différents moyens de définir les limites de la sélection. Suivent de brèves descriptions de ces formes :  
  
- **Fonction membre SetSel (** `cr` **)** ce formulaire utilise le **structure CHARRANGE** structure avec son **cpMin** et **cpMax** membres pour définir les limites.  
  
- **Fonction membre SetSel (** `nStartChar` **,** `nEndChar` **)** cet écran utilisent les paramètres `nStartChar` et `nEndChar` pour définir les limites.  
  
 Le point d’insertion est placé à la fin de la sélection indiquée par la plus grande de début ( **cpMin** ou `nStartChar`) et de fin ( **cpMax** ou `nEndChar`) indices. Cette fonction fait défiler le contenu de la `CRichEditCtrl` pour que le point d’insertion soit visible.  
  
 Pour sélectionner tout le texte dans ce `CRichEditCtrl` de l’objet, appelez `SetSel` avec un index de départ de 0 et un index de fin de – 1.  
  
 Pour plus d’informations, consultez [EM_EXSETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788007) message et [structure CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [fonction membre GetSel](#getsel).  
  
##  <a name="setselectioncharformat"></a>CRichEditCtrl::SetSelectionCharFormat  
 Définit le caractère de mise en forme des attributs pour le texte de la sélection actuelle dans ce `CRichEditCtrl` objet.  
  
```  
BOOL SetSelectionCharFormat(CHARFORMAT& cf);  
BOOL SetSelectionCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Paramètres  
 `cf`  
 Dans la première version, un pointeur vers un [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) les attributs de structure qui contient le caractère de nouvelle mise en forme de la sélection actuelle.  
  
 Dans la deuxième version, un pointeur vers un [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure, qui est une extension Rich Edit 2.0 à la **CHARFORMAT** structure, qui contient le caractère de nouvelle mise en forme d’attributs pour la sélection actuelle.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Seuls les attributs spécifiés par le **dwMask** membre `cf` sont modifiés par cette fonction.  
  
 Pour plus d’informations, consultez la [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) et **CHARFORMAT** et **CHARFORMAT2** structures dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#31;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_31.cpp)]  
  
##  <a name="settargetdevice"></a>CRichEditCtrl::SetTargetDevice  
 Définit la largeur de périphérique et la ligne cible utilisée pour WYSIWYG (ce que vous voyez est ce que vous obtenez) mise en forme dans ce `CRichEditCtrl` objet.  
  
```  
BOOL SetTargetDevice(
    HDC hDC,  
    long lLineWidth);

 
BOOL SetTargetDevice(
    CDC& dc,  
    long lLineWidth);
```  
  
### <a name="parameters"></a>Paramètres  
 `hDC`  
 Handle vers le contexte de périphérique pour le nouveau périphérique cible.  
  
 *lLineWidth*  
 Largeur de ligne à utiliser pour la mise en forme.  
  
 `dc`  
 [Capture de données modifiées](../../mfc/reference/cdc-class.md) pour le nouveau périphérique cible.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Si cette fonction est réussie, le contrôle rich edit est propriétaire du périphérique contexte passé en tant que paramètre. Dans ce cas, la fonction d’appel ne doit pas détruire le contexte de périphérique.  
  
 Pour plus d’informations, consultez [EM_SETTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/bb774282) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n°&32;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_32.cpp)]  
  
##  <a name="settextmode"></a>CRichEditCtrl::SetTextMode  
 Définit le niveau de mode ou annuler et rétablir de texte d’un contrôle rich edit.  
  
```  
BOOL SetTextMode(UINT fMode);
```  
  
### <a name="parameters"></a>Paramètres  
 *fMode*  
 Spécifie les nouveaux paramètres texte mode et annulation au niveau paramètres du contrôle. Pour obtenir la liste des valeurs possibles, consultez le paramètre de mode de [EM_SETTEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774286) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro en cas de réussite, sinon différente de zéro.  
  
### <a name="remarks"></a>Remarques  
 Pour obtenir une description des modes de texte, consultez **EM_SETTEXTMODE** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Cette fonction membre échoue si le contrôle contient du texte. Pour vous assurer que le contrôle est vide, envoyez un [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) message avec une chaîne vide.  
  
##  <a name="setundolimit"></a>CRichEditCtrl::SetUndoLimit  
 Définit le nombre maximal d’actions pouvant être stockés dans la file d’attente.  
  
```  
UINT SetUndoLimit(UINT nLimit);
```  
  
### <a name="parameters"></a>Paramètres  
 *nLimit*  
 Spécifie le nombre maximal d’actions pouvant être stockés dans la file d’attente. La valeur zéro pour désactiver l’annulation.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nouveau nombre maximal d’actions d’annulation de la riche contrôle d’édition.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, le nombre maximal d’actions dans la file d’attente est 100. Si vous augmentez ce nombre, il doit être suffisamment de mémoire pour prendre en charge le nouveau numéro. Pour optimiser les performances, définir la limite la plus petite valeur possible.  
  
##  <a name="setwordcharformat"></a>CRichEditCtrl::SetWordCharFormat  
 Définit le caractère de mise en forme des attributs pour le mot actuellement sélectionné dans ce `CRichEditCtrl` objet.  
  
```  
BOOL SetWordCharFormat(CHARFORMAT& cf);  
BOOL SetWordCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Paramètres  
 `cf`  
 Dans la première version, un pointeur vers un [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) structure contenant la nouvelle mise en forme des caractères d’attributs pour le mot actuellement sélectionné.  
  
 Dans la deuxième version, un pointeur vers un [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure, qui est une extension Rich Edit 2.0 à la **CHARFORMAT** structure, qui contient le caractère de nouvelle mise en forme des attributs pour le mot actuellement sélectionné.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Seuls les attributs spécifiés par le **dwMask** membre `cf` sont modifiés par cette fonction.  
  
 Pour plus d’informations, consultez la [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) message et **CHARFORMAT** et **CHARFORMAT2** structures dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#33;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_33.cpp)]  
  
##  <a name="setwordwrapmode"></a>CRichEditCtrl::SetWordWrapMode  
 Définit les options de saut de ligne et de césure de mots pour la riche contrôle d’édition.  
  
```  
UINT SetWordWrapMode(UINT uFlags) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `uFlags`  
 Les options à définir pour effectuer l’analyse lexicale et de retour. Pour obtenir la liste des options possibles, consultez [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Le retour en cours et césure options.  
  
### <a name="remarks"></a>Remarques  
 Ce message est disponible uniquement dans les versions asiatiques du système d’exploitation.  
  
##  <a name="stopgrouptyping"></a>CRichEditCtrl::StopGroupTyping  
 Arrête le contrôle de la collecte supplémentaire en tapant des actions dans l’action en cours d’annulation.  
  
```  
void StopGroupTyping();
```  
  
### <a name="remarks"></a>Notes  
 Le contrôle stocke l’action suivante de frappe, éventuellement dans une action dans la file d’attente.  
  
 Pour plus d’informations, consultez [EM_STOPGROUPTYPING](http://msdn.microsoft.com/library/windows/desktop/bb774300) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="streamin"></a>CRichEditCtrl::StreamIn  
 Remplace le texte dans ce `CRichEditCtrl` avec le texte à partir du flux d’entrée spécifié.  
  
```  
long StreamIn(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>Paramètres  
 `nFormat`  
 Indicateurs qui spécifient les formats de données d’entrée. Pour plus d'informations, consultez la section Notes.  
  
 `es`  
 [Structure EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) structure spécifiant le flux d’entrée. Pour plus d'informations, consultez la section Notes.  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre de caractères lus à partir du flux d’entrée.  
  
### <a name="remarks"></a>Notes  
 La valeur de `nFormat` doit être une des opérations suivantes :  
  
- `SF_TEXT`Indique le texte de lecture uniquement.  
  
- `SF_RTF`Indique le texte de la lecture et la mise en forme.  
  
 Ces valeurs peuvent être combinées avec `SFF_SELECTION`. Si `SFF_SELECTION` est spécifié, `StreamIn` remplace la sélection actuelle par le contenu du flux d’entrée. S’il n’est pas spécifié, `StreamIn` remplace tout le contenu de ce `CRichEditCtrl` objet.  
  
 Dans le **structure EDITSTREAM** paramètre `es`, vous spécifiez une fonction de rappel qui remplit une mémoire tampon de texte. Cette fonction de rappel est appelée plusieurs fois, jusqu'à ce que le flux d’entrée est épuisé.  
  
 Pour plus d’informations, consultez [EM_STREAMIN](http://msdn.microsoft.com/library/windows/desktop/bb774302) message et [structure EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#34;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_34.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#35;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_35.cpp)]  
  
##  <a name="streamout"></a>CRichEditCtrl::StreamOut  
 Écrit le contenu de ce `CRichEditCtrl` objet dans le flux de sortie spécifié.  
  
```  
long StreamOut(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>Paramètres  
 `nFormat`  
 Indicateurs qui spécifient les formats de données de sortie. Pour plus d'informations, consultez la section Notes.  
  
 `es`  
 [Structure EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) structure qui spécifie le flux de sortie. Pour plus d'informations, consultez la section Notes.  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre de caractères écrits dans le flux de sortie.  
  
### <a name="remarks"></a>Remarques  
 La valeur de `nFormat` doit être une des opérations suivantes :  
  
- `SF_TEXT`Indique l’écriture du texte uniquement.  
  
- `SF_RTF`Indique le texte de l’écriture et la mise en forme.  
  
- `SF_RTFNOOBJS`Indique de texte et la mise en forme, en remplaçant les éléments OLE par des espaces.  
  
- `SF_TEXTIZED`Indique le texte de l’écriture et la mise en forme avec des représentations textuelles des éléments OLE.  
  
 Ces valeurs peuvent être combinées avec `SFF_SELECTION`. Si `SFF_SELECTION` est spécifié, `StreamOut` écrit la sélection actuelle dans le flux de sortie. S’il n’est pas spécifié, `StreamOut` écrit tout le contenu de ce `CRichEditCtrl` objet.  
  
 Dans le **structure EDITSTREAM** paramètre `es`, vous spécifiez une fonction de rappel qui remplit une mémoire tampon de texte. Cette fonction de rappel est appelée plusieurs fois, jusqu'à ce que le flux de sortie est épuisé.  
  
 Pour plus d’informations, consultez [EM_STREAMOUT](http://msdn.microsoft.com/library/windows/desktop/bb774304) message et [structure EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CRichEditCtrl n °&36;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_36.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#37;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_37.cpp)]  
  
##  <a name="undo"></a>CRichEditCtrl::Undo  
 Annule la dernière opération de contrôle d’édition enrichi.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération d’annulation a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Une opération d’annulation peut également être annulée. Par exemple, vous pouvez restaurer le texte supprimé avec le premier appel à **Annuler**. Tant qu’il n’existe aucune opération de modification intermédiaire, vous pouvez supprimer le texte avec un deuxième appel à **Annuler**.  
  
 Pour plus d’informations, consultez [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CanUndo](#canundo).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC WORDPAD](../../visual-cpp-samples.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe CEdit](../../mfc/reference/cedit-class.md)   
 [CRichEditView (classe)](../../mfc/reference/cricheditview-class.md)

