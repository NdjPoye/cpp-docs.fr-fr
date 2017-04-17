---
title: CRichEditView (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
dev_langs:
- C++
helpviewer_keywords:
- document/view architecture, rich edit controls
- OLE containers, rich edit
- rich edit controls, OLE container
- CRichEditView class
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
caps.latest.revision: 25
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
ms.openlocfilehash: 9f54ec0c8aae58828607b01973a263e458c30ddb
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditview-class"></a>CRichEditView (classe)
Avec [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) et [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), fournit les fonctionnalités du contrôle RichEdit dans le contexte de l’architecture document/vue de MFC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CRichEditView : public CCtrlView  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditView::CRichEditView](#cricheditview)|Construit un objet `CRichEditView`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|Déplace une boîte de dialogue afin qu’il ne masquer la sélection actuelle.|  
|[CRichEditView::CanPaste](#canpaste)|Indique si le Presse-papiers contient des données qui peuvent être collées dans la vue d’édition enrichi.|  
|[CRichEditView::DoPaste](#dopaste)|Colle un élément OLE dans cette vue RichEdit.|  
|[CRichEditView::FindText](#findtext)|Recherche le texte spécifié, en appelant le curseur d’attente.|  
|[CRichEditView::FindTextSimple](#findtextsimple)|Recherche le texte spécifié.|  
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Récupère le caractère de mise en forme d’attributs pour la sélection actuelle.|  
|[CRichEditView::GetDocument](#getdocument)|Récupère un pointeur vers le [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|  
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Récupère l’élément OLE est actif actuellement en place dans la vue d’édition enrichi.|  
|[CRichEditView::GetMargins](#getmargins)|Récupère les marges pour cette vue RichEdit.|  
|[CRichEditView::GetPageRect](#getpagerect)|Récupère le rectangle de page pour cette vue RichEdit.|  
|[CRichEditView::GetPaperSize](#getpapersize)|Récupère la taille du papier pour cette vue RichEdit.|  
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Récupère les paragraphes d’attributs pour la sélection actuelle.|  
|[CRichEditView::GetPrintRect](#getprintrect)|Récupère le rectangle d’impression pour cette vue RichEdit.|  
|[CRichEditView::GetPrintWidth](#getprintwidth)|Récupère la largeur d’impression pour cette vue RichEdit.|  
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|Récupère le contrôle RichEdit.|  
|[CRichEditView::GetSelectedItem](#getselecteditem)|Récupère l’élément sélectionné dans la vue d’édition enrichi.|  
|[CRichEditView::GetTextLength](#gettextlength)|Récupère la longueur du texte dans la vue d’édition enrichi.|  
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Récupère le nombre de caractères ou d’octets dans la vue d’édition enrichi. Liste d’indicateurs de développé pour la méthode permettant de déterminer la longueur.|  
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Insère un fichier sous la forme d’un élément OLE.|  
|[CRichEditView::InsertItem](#insertitem)|Insère un nouvel élément sous la forme d’un élément OLE.|  
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Indique si le Presse-papiers contient des données dans un format texte ou RTF.|  
|[CRichEditView::OnCharEffect](#onchareffect)|Active ou désactive le caractère de mise en forme de la sélection actuelle.|  
|[CRichEditView::OnParaAlign](#onparaalign)|Modifie l’alignement des paragraphes.|  
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Met à jour l’interface utilisateur de commande pour les fonctions membres publiques de caractère.|  
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Met à jour l’interface utilisateur de commande pour les fonctions membres publiques de paragraphe.|  
|[CRichEditView::PrintInsideRect](#printinsiderect)|Met en forme le texte spécifié dans le rectangle spécifié.|  
|[CRichEditView::PrintPage](#printpage)|Met en forme le texte spécifié dans la page donnée.|  
|[CRichEditView::SetCharFormat](#setcharformat)|Définit le caractère de mise en forme d’attributs pour la sélection actuelle.|  
|[CRichEditView::SetMargins](#setmargins)|Définit les marges de cette riche modifier l’affichage.|  
|[CRichEditView::SetPaperSize](#setpapersize)|Définit le format du papier pour cette vue RichEdit.|  
|[CRichEditView::SetParaFormat](#setparaformat)|Définit les attributs pour la sélection actuelle de paragraphes.|  
|[CRichEditView::TextNotFound](#textnotfound)|Réinitialise l’état interne de recherche du contrôle.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](#getclipboarddata)|Récupère un objet Clipboard pour une plage dans cette vue RichEdit.|  
|[CRichEditView::GetContextMenu](#getcontextmenu)|Récupère un menu contextuel à utiliser sur un bouton droit de la souris vers le bas.|  
|[CRichEditView::IsSelected](#isselected)|Indique si l’élément OLE est activée ou non.|  
|[CRichEditView::OnFindNext](#onfindnext)|Recherche l’occurrence suivante d’une sous-chaîne.|  
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Actualise une vue lorsque c’est le premier joint à un document.|  
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|Récupère les données en mode natif à partir d’un élément OLE.|  
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|Définit les caractéristiques d’impression sur le périphérique donné.|  
|[CRichEditView::OnReplaceAll](#onreplaceall)|Remplace toutes les occurrences d’une chaîne donnée par une nouvelle chaîne.|  
|[CRichEditView::OnReplaceSel](#onreplacesel)|Remplace la sélection actuelle.|  
|[CRichEditView::OnTextNotFound](#ontextnotfound)|Gère la notification de l’utilisateur que le texte demandé est introuvable.|  
|[CRichEditView::QueryAcceptData](#queryacceptdata)|Requêtes à visualiser concernant les données sur le `IDataObject`.|  
|[CRichEditView::WrapChanged](#wrapchanged)|Ajuste le périphérique de sortie cible pour cette vue, selon la valeur de RichEdit `m_nWordWrap`.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Indique la quantité de retrait de listes à puces.|  
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Indique les contraintes de type wrap de word.|  
  
## <a name="remarks"></a>Notes  
 Un « contrôle rich edit » est une fenêtre dans laquelle l’utilisateur peut entrer et modifier du texte. Le texte peut être attribué caractères ou paragraphes et peut inclure des objets OLE incorporés. Les contrôles RichEdit fournissent une interface de programmation pour la mise en forme de texte. Toutefois, une application doit implémenter tous les composants d’interface utilisateur nécessaires pour rendre les opérations de mise en forme disponibles à l’utilisateur.  
  
 `CRichEditView`conserve le texte et les caractéristiques de mise en forme du texte. `CRichEditDoc`gère la liste des éléments client OLE dans la vue. `CRichEditCntrItem`fournit un accès côté conteneur à l’élément client OLE.  
  
 Ce contrôle commun de Windows (et par conséquent la [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) et les classes associées) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT versions 3.51 et ultérieures.  
  
 Pour obtenir un exemple d’utilisation d’une vue d’édition enrichi dans une application MFC, consultez la [WORDPAD](../../visual-cpp-samples.md) exemple d’application.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrich.h  
  
##  <a name="adjustdialogposition"></a>CRichEditView::AdjustDialogPosition  
 Appelez cette fonction pour déplacer la boîte de dialogue donné afin qu’il ne masque pas la sélection actuelle.  
  
```  
void AdjustDialogPosition(CDialog* pDlg);
```  
  
### <a name="parameters"></a>Paramètres  
 *pDlg*  
 Pointeur vers un `CDialog` objet.  
  
##  <a name="canpaste"></a>CRichEditView::CanPaste  
 Appelez cette fonction pour déterminer si le Presse-papiers contient des informations qui peuvent être collées dans cette vue RichEdit.  
  
```  
BOOL CanPaste() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le Presse-papiers contient des données dans un format que cette vue RichEdit peut accepter ; Sinon, 0.  
  
##  <a name="cricheditview"></a>CRichEditView::CRichEditView  
 Appelez cette fonction pour créer un `CRichEditView` objet.  
  
```  
CRichEditView();
```  
  
##  <a name="dopaste"></a>CRichEditView::DoPaste  
 Appelez cette fonction pour coller l’élément OLE dans `dataobj` dans ce RichEdit document/vue.  
  
```  
void DoPaste(
    COleDataObject& dataobj,  
    CLIPFORMAT cf,  
    HMETAFILEPICT hMetaPict);
```  
  
### <a name="parameters"></a>Paramètres  
 `dataobj`  
 Le [COleDataObject](../../mfc/reference/coledataobject-class.md) contenant les données à coller.  
  
 `cf`  
 Le format de Presse-papiers souhaité.  
  
 `hMetaPict`  
 Le métafichier qui représente l’élément à coller.  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure appelle cette fonction dans le cadre de l’implémentation par défaut de [QueryAcceptData](#queryacceptdata).  
  
 Cette fonction détermine le type de collage en fonction des résultats du Gestionnaire de collage spécial. Si `cf` est 0, le nouvel élément utilise la représentation sous forme d’icône actuelle. Si `cf` est différente de zéro et `hMetaPict` n’est pas **NULL**, utilise le nouvel élément `hMetaPict` pour sa représentation.  
  
##  <a name="findtext"></a>CRichEditView::FindText  
 Appelez cette fonction pour rechercher le texte spécifié et définissez la sélection en cours.  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFind`  
 Contient la chaîne à rechercher.  
  
 `bCase`  
 Indique si la recherche respecte la casse.  
  
 `bWord`  
 Indique si la recherche doit correspondre à des mots entiers uniquement, pas des parties de mots.  
  
 `bNext`  
 Indique la direction de la recherche. Si **TRUE**, le sens de la recherche est vers la fin de la mémoire tampon. Si **FALSE**, le sens de la recherche est vers le début de la mémoire tampon.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la `lpszFind` texte est trouvé ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction affiche le curseur d’attente pendant l’opération de recherche.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#151;](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]  
  
##  <a name="findtextsimple"></a>CRichEditView::FindTextSimple  
 Appelez cette fonction pour rechercher le texte spécifié et définissez la sélection en cours.  
  
```  
BOOL FindTextSimple(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFind`  
 Contient la chaîne à rechercher.  
  
 `bCase`  
 Indique si la recherche respecte la casse.  
  
 `bWord`  
 Indique si la recherche doit correspondre à des mots entiers uniquement, pas des parties de mots.  
  
 `bNext`  
 Indique la direction de la recherche. Si **TRUE**, le sens de la recherche est vers la fin de la mémoire tampon. Si **FALSE**, le sens de la recherche est vers le début de la mémoire tampon.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la `lpszFind` texte est trouvé ; sinon, 0.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditView::FindText](#findtext).  
  
##  <a name="getcharformatselection"></a>CRichEditView::GetCharFormatSelection  
 Appelez cette fonction pour obtenir le caractère de mise en forme des attributs de la sélection actuelle.  
  
```  
CHARFORMAT2& GetCharFormatSelection();
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure qui contient le caractère de mise en forme des attributs de la sélection actuelle.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez la [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) message et [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#152;](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="getclipboarddata"></a>CRichEditView::GetClipboardData  
 L’infrastructure appelle cette fonction dans le cadre du traitement de [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315).  
  
```  
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,  
    DWORD dwReco,  
    LPDATAOBJECT lpRichDataObj,  
    LPDATAOBJECT* lplpdataobj);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpchrg`  
 Pointeur vers le [structure CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) structure qui spécifie la plage de caractères (et les éléments OLE) pour copier l’objet de données spécifié par `lplpdataobj`.  
  
 `dwReco`  
 Indicateur d’opération Presse-papiers. Peut être une des valeurs suivantes.  
  
- **RECO_COPY** copier dans le Presse-papiers.  
  
- **RECO_CUT** coupé dans le Presse-papiers.  
  
- **RECO_DRAG** opération (glisser-déplacer) de glissement.  
  
- **RECO_DROP** déplacer (glisser-déplacer).  
  
- **RECO_PASTE** coller à partir du Presse-papiers.  
  
 `lpRichDataObj`  
 Pointeur vers un [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) objet contenant les données du Presse-papiers à partir de la riche modifiable ( [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341)).  
  
 `lplpdataobj`  
 Pointeur vers la variable pointeur qui reçoit l’adresse de la `IDataObject` objet représentant la plage spécifiée dans le `lpchrg` paramètre. La valeur de `lplpdataobj` est ignorée si une erreur est renvoyée.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `HRESULT` valeur rapport de réussite de l’opération. Pour plus d’informations sur `HRESULT`, consultez [Structure des Codes d’erreur COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Si la valeur de retour indique la réussite, **IRichEditOleCallback::GetClipboardData** retourne le `IDataObject` auxquelles `lplpdataobj`; sinon, elle retourne l’auxquelles `lpRichDataObj`. Remplacez cette fonction pour fournir vos propres données du Presse-papiers. L’implémentation par défaut de cette fonction retourne **E_NOTIMPL**.  
  
 Il s’agit d’une avancée substituable.  
  
 Pour plus d’informations, consultez [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341), [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315), et [structure CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] et [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) dans les [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
##  <a name="getcontextmenu"></a>CRichEditView::GetContextMenu  
 L’infrastructure appelle cette fonction dans le cadre du traitement de [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317).  
  
```  
virtual HMENU GetContextMenu(
    WORD seltyp,  
    LPOLEOBJECT lpoleobj,  
    CHARRANGE* lpchrg);
```  
  
### <a name="parameters"></a>Paramètres  
 *seltyp*  
 Le type de sélection. Les valeurs de type de sélection sont décrites dans la section Notes.  
  
 `lpoleobj`  
 Pointeur vers un **OLEOBJECT** structure spécifiant le premier objet OLE sélectionné si la sélection contient un ou plusieurs éléments OLE. Si la sélection ne contient aucun élément, `lpoleobj` est **NULL**. Le **OLEOBJECT** structure conserve un pointeur vers une objet OLE v-table.  
  
 `lpchrg`  
 Pointeur vers un [structure CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) structure contenant la sélection actuelle.  
  
### <a name="return-value"></a>Valeur de retour  
 Handle vers le menu contextuel.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est une partie standard du bouton droit de la souris le traitement.  
  
 Le type de sélection peut être n’importe quelle combinaison des indicateurs suivants :  
  
- `SEL_EMPTY`Indique qu’il n’existe pas de sélection.  
  
- `SEL_TEXT`Indique que la sélection actuelle contienne du texte.  
  
- `SEL_OBJECT`Indique que la sélection actuelle contienne au moins un élément OLE.  
  
- `SEL_MULTICHAR`Indique que la sélection actuelle contienne plusieurs caractères de texte.  
  
- `SEL_MULTIOBJECT`Indique que la sélection actuelle contienne plus d’un objet OLE.  
  
 L’implémentation par défaut retourne **NULL**. Il s’agit d’une avancée substituable.  
  
 Pour plus d’informations, consultez [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317) et [structure CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur la **OLEOBJECT** de type, consultez l’article de Structures de données OLE et Allocation de la Structure de la *Base de connaissances OLE*.  
  
##  <a name="getdocument"></a>CRichEditView::GetDocument  
 Appelez cette fonction pour obtenir un pointeur vers le `CRichEditDoc` associé à cette vue.  
  
```  
CRichEditDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) objet associé à votre `CRichEditView` objet.  
  
##  <a name="getinplaceactiveitem"></a>CRichEditView::GetInPlaceActiveItem  
 Appel de cette fonction pour obtenir le OLE d’élément qui est actuellement activé sur place dans cette `CRichEditView` objet.  
  
```  
CRichEditCntrItem* GetInPlaceActiveItem() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’actif unique et place [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) objet dans cette vue RichEdit ; **NULL** s’il n’existe actuellement aucun élément OLE dans l’état actif sur place.  
  
##  <a name="getmargins"></a>CRichEditView::GetMargins  
 Appelez cette fonction pour récupérer les marges actuels utilisés pour l’impression.  
  
```  
CRect GetMargins() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les marges utilisées à l’impression, mesurée en `MM_TWIPS`.  
  
##  <a name="getpagerect"></a>CRichEditView::GetPageRect  
 Appelez cette fonction pour obtenir les dimensions de la page utilisée dans l’impression.  
  
```  
CRect GetPageRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les limites de la page utilisée à l’impression, mesurée en `MM_TWIPS`.  
  
### <a name="remarks"></a>Notes  
 Cette valeur est basée sur le format du papier.  
  
##  <a name="getpapersize"></a>CRichEditView::GetPaperSize  
 Appelez cette fonction pour récupérer la taille du document en cours.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille du papier utilisé pour l’impression, mesurée en `MM_TWIPS`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#153;](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]  
  
##  <a name="getparaformatselection"></a>CRichEditView::GetParaFormatSelection  
 Appelez cette fonction pour obtenir les attributs de la sélection actuelle de paragraphes.  
  
```  
PARAFORMAT2& GetParaFormatSelection();
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) structure qui contient les attributs de la sélection actuelle de paragraphes.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) message et [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getprintrect"></a>CRichEditView::GetPrintRect  
 Appelez cette fonction pour récupérer les limites de la zone d’impression dans le rectangle de la page.  
  
```  
CRect GetPrintRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les limites de la zone d’image utilisé pour l’impression, mesurée en `MM_TWIPS`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#154;](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]  
  
##  <a name="getprintwidth"></a>CRichEditView::GetPrintWidth  
 Appelez cette fonction pour déterminer la largeur de la zone d’impression.  
  
```  
int GetPrintWidth() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La largeur de la zone d’impression, en `MM_TWIPS`.  
  
##  <a name="getricheditctrl"></a>CRichEditView::GetRichEditCtrl  
 Appelez cette fonction pour récupérer la [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) objet associé à le `CRichEditView` objet.  
  
```  
CRichEditCtrl& GetRichEditCtrl() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `CRichEditCtrl` objet pour cette vue.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditView::FindText](#findtext).  
  
##  <a name="getselecteditem"></a>CRichEditView::GetSelectedItem  
 Appelez cette fonction pour récupérer l’élément OLE (un `CRichEditCntrItem` objet) actuellement sélectionné dans ce `CRichEditView` objet.  
  
```  
CRichEditCntrItem* GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) objet sélectionné dans le `CRichEditView` de l’objet ; **NULL** si aucun élément n’est sélectionné dans cette vue.  
  
##  <a name="gettextlength"></a>CRichEditView::GetTextLength  
 Appelez cette fonction pour extraire la longueur du texte dans ce `CRichEditView` objet.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur du texte dans ce `CRichEditView` objet.  
  
##  <a name="gettextlengthex"></a>CRichEditView::GetTextLengthEx  
 Appelez cette fonction membre pour calculer la longueur du texte dans ce `CRichEditView` objet.  
  
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
 `GetTextLengthEx`Fournit des méthodes supplémentaires permettant de déterminer la longueur du texte. Il prend en charge la fonctionnalité Rich Edit 2.0. Pour plus d’informations, consultez [sur les contrôles Rich Edit](http://msdn.microsoft.com/library/windows/desktop/bb787873) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="insertfileasobject"></a>CRichEditView::InsertFileAsObject  
 Appelez cette fonction pour insérer le fichier spécifié (comme un [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) objet) dans une riche modifier l’affichage.  
  
```  
void InsertFileAsObject(LPCTSTR lpszFileName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFileName`  
 Chaîne contenant le nom du fichier à insérer.  
  
##  <a name="insertitem"></a>CRichEditView::InsertItem  
 Appelez cette fonction pour insérer un [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) objet dans une vue d’édition enrichi.  
  
```  
HRESULT InsertItem(CRichEditCntrItem* pItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointeur vers l’élément à insérer.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `HRESULT` indiquant la réussite de l’insertion.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur `HRESULT`, consultez [Structure des Codes d’erreur COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isricheditformat"></a>CRichEditView::IsRichEditFormat  
 Appelez cette fonction pour déterminer si `cf` est un format de Presse-papiers, texte, texte enrichi ou texte enrichi avec les éléments OLE.  
  
```  
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```  
  
### <a name="parameters"></a>Paramètres  
 `cf`  
 Le format de Presse-papiers dignes d’intérêt.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si `cf` est un format de Presse-papiers Édition ou de texte enrichi.  
  
##  <a name="isselected"></a>CRichEditView::IsSelected  
 Appelez cette fonction pour déterminer si l’élément OLE spécifié est actuellement sélectionné dans cette vue.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pDocItem`  
 Pointeur vers un objet dans la vue.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet est sélectionné ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction si votre classe d’affichage dérivée a une autre méthode pour gérer la sélection d’éléments OLE.  
  
##  <a name="m_nbulletindent"></a>CRichEditView::m_nBulletIndent  
 La mise en retrait pour les éléments de puce dans une liste ; par défaut, les 720 unités, c'est-à-dire 1/2 pouces.  
  
```  
int m_nBulletIndent;  
```  
  
##  <a name="m_nwordwrap"></a>CRichEditView::m_nWordWrap  
 Indique le type de retour pour cette vue RichEdit.  
  
```  
int m_nWordWrap;  
```  
  
### <a name="remarks"></a>Remarques  
 Une des valeurs suivantes :  
  
- `WrapNone`N’indique aucun retour automatique.  
  
- `WrapToWindow`Indique un retour à la fonction de la largeur de la fenêtre.  
  
- `WrapToTargetDevice`Indique un retour selon les caractéristiques de l’appareil cible.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditView::WrapChanged](#wrapchanged).  
  
##  <a name="onchareffect"></a>CRichEditView::OnCharEffect  
 Appelez cette fonction pour basculer le caractère de mise en forme des effets de la sélection en cours.  
  
```  
void OnCharEffect(
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwMask`  
 Le caractère de mise en forme des effets pour modifier la sélection en cours.  
  
 `dwEffect`  
 La liste souhaitée des effets pour activer/désactiver la mise en forme des caractères.  
  
### <a name="remarks"></a>Remarques  
 Chaque appel à cette fonction active ou désactive les effets de mise en forme spécifiées pour la sélection actuelle.  
  
 Pour plus d’informations sur la `dwMask` et `dwEffect` paramètres et leurs valeurs possibles, consultez les membres de données correspondants de [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#155;](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]  
  
##  <a name="onfindnext"></a>CRichEditView::OnFindNext  
 Appelé par l’infrastructure lors du traitement des commandes à partir de la boîte de dialogue Rechercher/Remplacer.  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFind`  
 Chaîne à rechercher.  
  
 `bNext`  
 La direction à rechercher : **TRUE** indique ; **FALSE**, up.  
  
 `bCase`  
 Indique si la recherche doit respecter la casse.  
  
 `bWord`  
 Indique si la recherche doit correspondre à des mots entiers uniquement ou non.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour rechercher du texte dans le `CRichEditView`. Remplacez cette fonction pour modifier les caractéristiques de recherche pour votre classe d’affichage dérivée.  
  
##  <a name="oninitialupdate"></a>CRichEditView::OnInitialUpdate  
 Appelée par l’infrastructure une fois que la vue est d’abord attachée au document, mais avant l’affichage initial.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut de cette fonction appelle le [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) fonction membre sans aucune information d’indicateur (autrement dit, en utilisant les valeurs par défaut de 0 pour le `lHint` paramètre et **NULL** pour la `pHint` paramètre). Remplacez cette fonction pour exécuter toute initialisation à usage unique qui requiert des informations sur le document. Par exemple, si votre application comporte des documents de taille fixe, vous pouvez utiliser cette fonction pour initialiser les limites de défilement de l’affichage en fonction de la taille du document. Si votre application prend en charge les documents de taille variable, utilisez `OnUpdate` pour mettre à jour le défilement limite chaque fois que le document est modifié.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditView::m_nWordWrap](#m_nwordwrap).  
  
##  <a name="onpastenativeobject"></a>CRichEditView::OnPasteNativeObject  
 Cette fonction permet de charger des données en mode natif à partir d’un élément incorporé.  
  
```  
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpStg*  
 Pointeur vers un [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0 ;  
  
### <a name="remarks"></a>Remarques  
 En règle générale, cette tâche est nécessaire en créant un [COleStreamFile](../../mfc/reference/colestreamfile-class.md) autour de la `IStorage`. Le `COleStreamFile` peuvent être associées à une archive et [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) appelée pour charger les données.  
  
 Il s’agit d’une avancée substituable.  
  
 Pour plus d’informations, consultez [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onparaalign"></a>CRichEditView::OnParaAlign  
 Appelez cette fonction pour modifier l’alignement de paragraphe des paragraphes sélectionnés.  
  
```  
void OnParaAlign(WORD wAlign);
```  
  
### <a name="parameters"></a>Paramètres  
 `wAlign`  
 Alignement de paragraphe souhaité. Une des valeurs suivantes :  
  
- `PFA_LEFT`Aligner les paragraphes sur la marge de gauche.  
  
- `PFA_RIGHT`Aligner les paragraphes sur la marge de droite.  
  
- `PFA_CENTER`Centre les paragraphes entre les marges.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#156;](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]  
  
##  <a name="onprinterchanged"></a>CRichEditView::OnPrinterChanged  
 Remplacez cette fonction pour changer les caractéristiques de cette vue RichEdit lors de l’imprimante.  
  
```  
virtual void OnPrinterChanged(const CDC& dcPrinter);
```  
  
### <a name="parameters"></a>Paramètres  
 `dcPrinter`  
 A [CDC](../../mfc/reference/cdc-class.md) objet de la nouvelle imprimante.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut définit le format du papier à la hauteur physique et la largeur du périphérique de sortie (imprimante). S’il existe aucun contexte de périphérique n’associé à `dcPrinter`, l’implémentation par défaut définit le format du papier à 8,5 par 11 pouces.  
  
##  <a name="onreplaceall"></a>CRichEditView::OnReplaceAll  
 Appelé par l’infrastructure lors du traitement de remplacer toutes les commandes à partir de la boîte de dialogue Remplacer.  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFind`  
 Texte à remplacer.  
  
 `lpszReplace`  
 Le texte de remplacement.  
  
 `bCase`  
 Indique si la recherche respecte la casse.  
  
 `bWord`  
 Indique si la recherche doit sélectionner des mots entiers ou non.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour remplacer toutes les occurrences d’un texte donné par une autre chaîne. Remplacez cette fonction pour modifier les caractéristiques de recherche pour cette vue.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditView::FindText](#findtext).  
  
##  <a name="onreplacesel"></a>CRichEditView::OnReplaceSel  
 Appelé par l’infrastructure lors du traitement des commandes de remplacement à partir de la boîte de dialogue Remplacer.  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFind`  
 Texte à remplacer.  
  
 `bNext`  
 Indique le sens de la recherche : **TRUE** est arrêté ; **FALSE**, up.  
  
 `bCase`  
 Indique si la recherche respecte la casse.  
  
 `bWord`  
 Indique si la recherche doit sélectionner des mots entiers ou non.  
  
 `lpszReplace`  
 Le texte de remplacement.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour remplacer une occurrence d’un texte donné par une autre chaîne. Remplacez cette fonction pour modifier les caractéristiques de recherche pour cette vue.  
  
##  <a name="ontextnotfound"></a>CRichEditView::OnTextNotFound  
 Appelée par l’infrastructure de chaque échec d’une recherche.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFind`  
 Le texte qui est introuvable.  
  
### <a name="remarks"></a>Remarques  
 Remplacer cette fonction pour modifier la notification de la sortie d’un [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356).  
  
 Pour plus d’informations, consultez [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#157;](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]  
  
##  <a name="onupdatechareffect"></a>CRichEditView::OnUpdateCharEffect  
 L’infrastructure appelle cette fonction pour mettre à jour l’interface utilisateur de commande pour les commandes d’effet de caractère.  
  
```  
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,  
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Pointeur vers un [CCmdUI](../../mfc/reference/ccmdui-class.md) objet.  
  
 `dwMask`  
 Indique le caractère de masque de mise en forme.  
  
 `dwEffect`  
 Indique le caractère de mise en forme d’effet.  
  
### <a name="remarks"></a>Remarques  
 Le masque `dwMask` Spécifie le caractère de mise en forme d’attributs à vérifier. Les indicateurs `dwEffect` le formatage des attributs à enlever ou supprimer des caractères de la liste.  
  
 Pour plus d’informations sur la `dwMask` et `dwEffect` paramètres et leurs valeurs possibles, consultez les membres de données correspondants de [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#158;](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]  
  
##  <a name="onupdateparaalign"></a>CRichEditView::OnUpdateParaAlign  
 L’infrastructure appelle cette fonction pour mettre à jour l’interface utilisateur de commande pour les commandes d’effet de paragraphe.  
  
```  
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,  
    WORD wAlign);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Pointeur vers un [CCmdUI](../../mfc/reference/ccmdui-class.md) objet.  
  
 `wAlign`  
 L’alignement de paragraphe à vérifier. Une des valeurs suivantes :  
  
- `PFA_LEFT`Aligner les paragraphes sur la marge de gauche.  
  
- `PFA_RIGHT`Aligner les paragraphes sur la marge de droite.  
  
- `PFA_CENTER`Centre les paragraphes entre les marges.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#159;](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]  
  
##  <a name="printinsiderect"></a>CRichEditView::PrintInsideRect  
 Appelez cette fonction pour mettre en forme une plage de texte dans un contrôle rich edit pour s’ajuster au *rectLayout* pour l’appareil spécifié par `pDC`.  
  
```  
long PrintInsideRect(
    CDC* pDC,  
    RECT& rectLayout,  
    long nIndexStart,  
    long nIndexStop,  
    BOOL bOutput);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointeur vers un contexte de périphérique pour la zone de sortie.  
  
 *rectLayout*  
 [RECT](../../mfc/reference/rect-structure1.md) ou [CRect](../../atl-mfc-shared/reference/crect-class.md) qui définit la zone de sortie.  
  
 `nIndexStart`  
 Index de base zéro du premier caractère à mettre en forme.  
  
 `nIndexStop`  
 Index de base zéro du dernier caractère à mettre en forme.  
  
 *bOutput*  
 Indique si le texte doit être restitué. Si **FALSE**, le texte est mesuré seulement.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index du dernier caractère qui correspond à la zone de sortie, plus un.  
  
### <a name="remarks"></a>Remarques  
 En règle générale, cet appel est suivi par un appel à [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) qui génère la sortie.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="printpage"></a>CRichEditView::PrintPage  
 Appelez cette fonction pour mettre en forme une plage de texte dans un contrôle rich edit pour le périphérique de sortie spécifié par `pDC`.  
  
```  
long PrintPage(
    CDC* pDC,  
    long nIndexStart,  
    long nIndexStop);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointeur vers un contexte de périphérique de sortie de la page.  
  
 `nIndexStart`  
 Index de base zéro du premier caractère à mettre en forme.  
  
 `nIndexStop`  
 Index de base zéro du dernier caractère à mettre en forme.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index du dernier caractère qui tienne sur la page, plus un.  
  
### <a name="remarks"></a>Remarques  
 La disposition de chaque page est contrôlée par [GetPageRect](#getpagerect) et [GetPrintRect](#getprintrect). En règle générale, cet appel est suivi par un appel à [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) qui génère la sortie.  
  
 Notez que les marges sont par rapport à la page physique, pas sur la page logique. Par conséquent, les marges de zéro découpe souvent le texte dans la mesure où de nombreuses imprimantes possèdent des zones sur la page. Pour éviter le découpage votre texte, vous devez appeler [SETMARGINS ne](#setmargins) et définissez des marges raisonnables avant l’impression.  
  
##  <a name="queryacceptdata"></a>CRichEditView::QueryAcceptData  
 Appelée par l’infrastructure pour coller un objet dans l’édition enrichi.  
  
```  
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,  
    CLIPFORMAT* lpcfFormat,  
    DWORD dwReco,  
    BOOL bReally,  
    HGLOBAL hMetaFile);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpdataobj*  
 Pointeur vers le [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) à interroger.  
  
 *lpcfFormat*  
 Pointeur vers le format de données acceptables.  
  
 `dwReco`  
 Non utilisé.  
  
 *bReally*  
 Indique si l’opération de collage doit continuer ou non.  
  
 `hMetaFile`  
 Un handle de métafichier utilisé pour dessiner l’icône de l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `HRESULT` valeur rapport de réussite de l’opération.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction pour gérer une organisation différente des éléments COM dans votre classe de document dérivée. Il s’agit d’une avancée substituable.  
  
 Pour plus d’informations sur `HRESULT` et `IDataObject`, consultez [Structure des Codes d’erreur COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) et [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421), respectivement, dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#160;](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]  
  
##  <a name="setcharformat"></a>CRichEditView::SetCharFormat  
 Appelez cette fonction pour définir le caractère de mise en forme des attributs pour le nouveau texte dans ce `CRichEditView` objet.  
  
```  
void SetCharFormat(CHARFORMAT2 cf);
```  
  
### <a name="parameters"></a>Paramètres  
 `cf`  
 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure contenant le caractère par défaut nouveaux attributs de mise en forme.  
  
### <a name="remarks"></a>Notes  
 Seuls les attributs spécifiés par le **dwMask** membre `cf` sont modifiés par cette fonction.  
  
 Pour plus d’informations, consultez [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) message et [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#152;](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="setmargins"></a>CRichEditView::SetMargins  
 Appelez cette fonction pour définir les marges d’impression de cette vue RichEdit.  
  
```  
void SetMargins(const CRect& rectMargin);
```  
  
### <a name="parameters"></a>Paramètres  
 *rectMargin*  
 Les nouvelles valeurs de marge pour l’impression, mesurée en `MM_TWIPS`.  
  
### <a name="remarks"></a>Notes  
 Si [m_nWordWrap](#m_nwordwrap) est `WrapToTargetDevice`, vous devez appeler [WrapChanged](#wrapchanged) après l’utilisation de cette fonction pour ajuster les options d’impression.  
  
 Notez que les marges utilisées par [PrintPage](#printpage) sont par rapport à la page physique, pas sur la page logique. Par conséquent, les marges de zéro découpe souvent le texte dans la mesure où de nombreuses imprimantes possèdent des zones sur la page. Pour éviter le découpage votre texte, vous devez appeler utilisez `SetMargins` pour définir les marges d’impression raisonnable avant l’impression.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="setpapersize"></a>CRichEditView::SetPaperSize  
 Appelez cette fonction pour définir le format du papier pour l’impression de cette vue RichEdit.  
  
```  
void SetPaperSize(CSize sizePaper);
```  
  
### <a name="parameters"></a>Paramètres  
 *sizePaper*  
 Les nouvelles valeurs de taille de papier pour l’impression, mesurée en `MM_TWIPS`.  
  
### <a name="remarks"></a>Remarques  
 Si [m_nWordWrap](#m_nwordwrap) est `WrapToTargetDevice`, vous devez appeler [WrapChanged](#wrapchanged) après l’utilisation de cette fonction pour ajuster les options d’impression.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#161;](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditView::SetParaFormat  
 Appelez cette fonction pour définir la mise en forme d’attributs pour la sélection actuelle dans ce paragraphe `CRichEditView` objet.  
  
```  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Paramètres  
 `pf`  
 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) structure contenant la nouvelle valeur par défaut des attributs de mise en forme de paragraphe.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Seuls les attributs spécifiés par le **dwMask** membre `pf` sont modifiés par cette fonction.  
  
 Pour plus d’informations, consultez [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) message et [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#162;](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]  
  
##  <a name="textnotfound"></a>CRichEditView::TextNotFound  
 Appelez cette fonction pour réinitialiser l’état interne de recherche de la [CRichEditView](../../mfc/reference/cricheditview-class.md) contrôle après un appel à [FindText](#findtext).  
  
```  
void TextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFind`  
 Contient la chaîne de texte qui n’a été trouvée.  
  
### <a name="remarks"></a>Notes  
 Il est recommandé que cette méthode est appelée immédiatement après les appels ayant échouées à [FindText](#findtext) afin que l’état interne de recherche du contrôle soit correctement réinitialisé.  
  
 Le `lpszFind` paramètre doit inclure le même contenu que la chaîne fournie pour [FindText](#findtext). Après la réinitialisation de l’état de recherche interne, cette méthode appelle la [OnTextNotFound](#ontextnotfound) méthode avec la chaîne de recherche fourni.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRichEditView::FindText](#findtext).  
  
##  <a name="wrapchanged"></a>CRichEditView::WrapChanged  
 Appelez cette fonction lorsque les caractéristiques d’impression ont changé ( [SETMARGINS ne](#setmargins) ou [SetPaperSize](#setpapersize)).  
  
```  
virtual void WrapChanged();
```  
  
### <a name="remarks"></a>Notes  
 Remplacement de cette fonction pour modifier la façon dont la vue RichEdit répond aux modifications des [m_nWordWrap](#m_nwordwrap) ou les caractéristiques d’impression ( [OnPrinterChanged](#onprinterchanged)).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#163;](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC WORDPAD](../../visual-cpp-samples.md)   
 [Classe de CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc (classe)](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem (classe)](../../mfc/reference/cricheditcntritem-class.md)
