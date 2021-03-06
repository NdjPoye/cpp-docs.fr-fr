---
title: CComboBox (classe) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
dev_langs:
- C++
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90495f2eccfb31169653f6dcb09f2cf52e5a05dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="ccombobox-class"></a>CComboBox (classe)
Fournit les fonctionnalités d'une zone de liste modifiable Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CComboBox : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComboBox::CComboBox](#ccombobox)|Construit un objet `CComboBox`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComboBox::AddString](#addstring)|Ajoute une chaîne à la fin de la liste dans la zone de liste d’une zone de liste déroulante, ou à la position de tri pour les zones de liste avec la **CBS_SORT** style.|  
|[CComboBox::Clear](#clear)|Supprime (efface) la sélection actuelle, le cas échéant, dans le contrôle d’édition.|  
|[CComboBox::CompareItem](#compareitem)|Appelé par l’infrastructure pour déterminer la position relative d’un nouvel élément de liste dans une zone de liste triée d’owner-drawn.|  
|[CComboBox::Copy](#copy)|Copie la sélection actuelle, si elle existe, dans le Presse-papiers dans **CF_TEXT** format.|  
|[CComboBox::Create](#create)|Crée la zone de liste modifiable et l’attache à le `CComboBox` objet.|  
|[CComboBox::Cut](#cut)|Supprime (morceaux de) la sélection actuelle, si, en cours de la modification de contrôle et copie le texte supprimé dans le Presse-papiers dans **CF_TEXT** format.|  
|[CComboBox::DeleteItem](#deleteitem)|Appelé par l’infrastructure lorsqu’un élément de liste est supprimé d’une zone de liste déroulante owner-drawn.|  
|[CComboBox::DeleteString](#deletestring)|Supprime une chaîne de la zone de liste d’une zone de liste déroulante.|  
|[CComboBox::Dir](#dir)|Ajoute une liste de noms de fichiers à la zone de liste d’une zone de liste déroulante.|  
|[CComboBox::DrawItem](#drawitem)|Appelé par le framework lorsqu’un aspect visuel d’une modification de zone de liste déroulante owner-drawn.|  
|[CComboBox::FindString](#findstring)|Recherche la première chaîne qui contient le préfixe spécifié dans la zone de liste d’une zone de liste déroulante.|  
|[CComboBox::FindStringExact](#findstringexact)|Recherche la première chaîne de zone de liste (dans une zone de liste modifiable) qui correspond à la chaîne spécifiée.|  
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Récupère les informations sur la `CComboBox` objet.|  
|[CComboBox::GetCount](#getcount)|Récupère le nombre d’éléments dans la zone de liste d’une zone de liste déroulante.|  
|[CComboBox::GetCueBanner](#getcuebanner)|Obtient le texte d’indication qui s’affiche pour un contrôle de zone de liste déroulante.|  
|[CComboBox::GetCurSel](#getcursel)|Récupère l’index de l’élément actuellement sélectionné, le cas échéant, dans la zone de liste d’une zone de liste déroulante.|  
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Récupère les coordonnées d’écran de la zone visible liste (déposé vers le bas) d’une zone de liste déroulante modifiable.|  
|[CComboBox::GetDroppedState](#getdroppedstate)|Détermine si la zone de liste d’une zone de liste déroulante modifiable est visible (déroulée).|  
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Récupère la largeur minimale autorisée pour la partie de la zone de liste déroulante d’une zone de liste déroulante.|  
|[CComboBox::GetEditSel](#geteditsel)|Obtient les positions de caractère de début et de fin de la sélection actuelle dans le contrôle d’édition d’une zone de liste déroulante.|  
|[CComboBox::GetExtendedUI](#getextendedui)|Détermine si une zone de liste déroulante contient l’interface utilisateur par défaut ou l’interface utilisateur améliorée.|  
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Retourne la largeur en pixels que la partie de la zone de liste de la zone de liste modifiable peut défiler horizontalement.|  
|[CComboBox::GetItemData](#getitemdata)|Récupère la valeur de 32 bits fournie par l’application associée à l’élément spécifié de zone de liste déroulante.|  
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Récupère le pointeur 32 bits fournie par l’application qui est associé à l’élément spécifié de zone de liste déroulante.|  
|[CComboBox::GetItemHeight](#getitemheight)|Récupère la hauteur des éléments de liste dans une zone de liste déroulante.|  
|[CComboBox::GetLBText](#getlbtext)|Obtient une chaîne à partir de la zone de liste d’une zone de liste déroulante.|  
|[CComboBox::GetLBTextLen](#getlbtextlen)|Obtient la longueur d’une chaîne dans la zone de liste d’une zone de liste déroulante.|  
|[CComboBox::GetLocale](#getlocale)|Récupère l’identificateur de paramètres régionaux pour une zone de liste déroulante.|  
|[CComboBox::GetMinVisible](#getminvisible)|Obtient le nombre minimal d’éléments visibles dans la liste déroulante de la zone de liste déroulante.|  
|[CComboBox::GetTopIndex](#gettopindex)|Retourne l’index du premier élément visible dans la partie de la zone de liste de la zone de liste déroulante.|  
|[CComboBox::InitStorage](#initstorage)|Pré-alloue des blocs de mémoire pour les éléments et les chaînes dans la partie de la zone de liste de la zone de liste déroulante.|  
|[CComboBox::InsertString](#insertstring)|Insère une chaîne dans la zone de liste d’une zone de liste modifiable.|  
|[CComboBox::LimitText](#limittext)|Limite la longueur du texte que l’utilisateur peut entrer dans le contrôle d’édition d’une zone de liste déroulante.|  
|[CComboBox::MeasureItem](#measureitem)|Appelé par l’infrastructure pour déterminer les dimensions de zone de liste déroulante lors de la création d’une zone de liste déroulante owner-drawn.|  
|[CComboBox::Paste](#paste)|Insère les données à partir du Presse-papiers dans le contrôle d’édition à la position actuelle du curseur. Les données sont insérées que si le Presse-papiers contient des données **CF_TEXT** format.|  
|[CComboBox::ResetContent](#resetcontent)|Supprime tous les éléments de la liste de zone et de modifier le contrôle de zone de liste déroulante.|  
|[CComboBox::SelectString](#selectstring)|Recherche une chaîne dans la zone de liste d’une zone de liste déroulante et, si la chaîne est trouvée, sélectionne la chaîne dans la zone de liste et copie la chaîne dans le contrôle d’édition.|  
|[CComboBox::SetCueBanner](#setcuebanner)|Définit le texte de la file d’attente qui est affiché pour un contrôle de zone de liste déroulante.|  
|[CComboBox::SetCurSel](#setcursel)|Sélectionne une chaîne dans la zone de liste d’une zone de liste déroulante.|  
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Définit la largeur minimale autorisée pour la partie de la zone de liste déroulante d’une zone de liste déroulante.|  
|[CComboBox::SetEditSel](#seteditsel)|Sélectionne des caractères dans le contrôle d’édition d’une zone de liste déroulante.|  
|[CComboBox::SetExtendedUI](#setextendedui)|Sélectionne l’interface utilisateur par défaut ou l’interface utilisateur améliorée pour la zone de liste modifiable a la **CBS_DROPDOWN** ou **CBS_DROPDOWNLIST** style.|  
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Définit la largeur en pixels que la partie de la zone de liste de la zone de liste modifiable peut défiler horizontalement.|  
|[CComboBox::SetItemData](#setitemdata)|Définit la valeur de 32 bits associée à l’élément spécifié dans une zone de liste déroulante.|  
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Définit le pointeur 32 bits associé à l’élément spécifié dans une zone de liste déroulante.|  
|[CComboBox::SetItemHeight](#setitemheight)|Définit la hauteur des éléments de liste dans une zone de liste déroulante ou la hauteur de la partie du contrôle d’édition (ou texte statique) d’une zone de liste déroulante.|  
|[CComboBox::SetLocale](#setlocale)|Définit l’identificateur de paramètres régionaux pour une zone de liste déroulante.|  
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Définit le nombre minimal d’éléments visibles dans la liste déroulante de la zone de liste déroulante.|  
|[CComboBox::SetTopIndex](#settopindex)|Indique la partie de la zone de liste de la zone de liste déroulante pour afficher l’élément avec l’index spécifié dans la partie supérieure.|  
|[CComboBox::ShowDropDown](#showdropdown)|Affiche ou masque la zone de liste d’une zone de liste modifiable a la **CBS_DROPDOWN** ou **CBS_DROPDOWNLIST** style.|  
  
## <a name="remarks"></a>Notes  
 Une zone de liste déroulante se compose d’une zone de liste associée à un contrôle statique ou un contrôle d’édition. La partie de la zone de liste du contrôle peut être affichée en permanence ou peut-être uniquement déroulante lorsque l’utilisateur sélectionne la flèche déroulante en regard du contrôle.  
  
 L’élément actuellement sélectionné (le cas échéant) dans la zone de liste est affiché dans la méthode statique ou modifier le contrôle. En outre, si la zone de liste modifiable a le style de liste déroulante, l’utilisateur peut taper le caractère initial de l’un des éléments dans la liste et la zone de liste, si elle est visible, met en surbrillance l’élément suivant avec ce caractère initial.  
  
 Le tableau suivant compare la zone de liste déroulante trois [styles](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles).  
  
|Style|Lorsque la zone de liste est visible|Contrôle statique ou modifier|  
|-----------|-------------------------------|-----------------------------|  
|Simple|Toujours|Modifier|  
|Drop-down|Lors de la suppression vers le bas|Modifier|  
|Liste déroulante|Lors de la suppression vers le bas|Statique|  
  
 Vous pouvez créer un `CComboBox` objet à partir d’un modèle de boîte de dialogue ou directement dans votre code. Dans les deux cas, tout d’abord appeler le constructeur `CComboBox` pour construire le `CComboBox` de l’objet, puis appelez le [créer](#create) fonction membre pour créer le contrôle et l’attacher à la `CComboBox` objet.  
  
 Si vous souhaitez traiter les messages de notification Windows envoyés par une zone de liste déroulante à son parent (généralement une classe dérivée de `CDialog`), ajouter une fonction table des messages de membre des entrée et le Gestionnaire de messages à la classe parente pour chaque message.  
  
 Chaque entrée de table des messages prend la forme suivante :  
  
 **ON_** Notification **(**`id`**,**`memberFxn`**)**  
  
 où `id` Spécifie l’ID de fenêtre enfant du contrôle de zone de liste déroulante envoie la notification et `memberFxn` est le nom de la fonction de membre parent que vous avez écrit pour gérer la notification.  
  
 Prototype de fonction du parent est la suivante :  
  
 **afx_msg** `void` `memberFxn` **() ;**  
  
 L’ordre dans lequel certaines notifications seront envoyées ne peut pas être prédit. En particulier, un **CBN_SELCHANGE du** notification peut se produire avant ou après un **CBN_CLOSEUP** notification.  
  
 Les entrées de table des messages potentielles sont les suivants :  
  
- **ON_CBN_CLOSEUP** (Windows 3.1 et versions ultérieures). La zone de liste d’une zone de liste modifiable a fermé. Ce message de notification n’est pas envoyé pour la zone de liste modifiable a la [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style.  
  
- **ON_CBN_DBLCLK** l’utilisateur double-clique sur une chaîne dans la zone de liste d’une zone de liste déroulante. Ce message de notification est envoyé uniquement pour une zone de liste déroulante avec la **CBS_SIMPLE** style. Pour une zone de liste déroulante avec la [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) ou [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) de style, un double-clic ne peut pas se produire, car un seul clic masque la zone de liste.  
  
- **ON_CBN_DROPDOWN** la zone de liste d’une zone de liste déroulante est sur le point de liste déroulante (être rendus visibles). Ce message de notification peut se produire uniquement pour une zone de liste déroulante avec la **CBS_DROPDOWN** ou **CBS_DROPDOWNLIST** style.  
  
- **ON_CBN_EDITCHANGE** l’utilisateur a effectué une action qui peut avoir modifié le texte dans la partie du contrôle d’édition d’une zone de liste déroulante. Contrairement à la **CBN_EDITUPDATE** message, ce message est envoyé une fois que l’écran de mises à jour de Windows. Il n’est pas envoyé si la zone de liste modifiable a la **CBS_DROPDOWNLIST** style.  
  
- **ON_CBN_EDITUPDATE** la portion de contrôle d’édition d’une zone de liste déroulante est sur le point d’afficher le texte modifié. Ce message de notification est envoyé une fois que le contrôle a mis en forme le texte, mais avant d’afficher le texte. Il n’est pas envoyé si la zone de liste modifiable a la **CBS_DROPDOWNLIST** style.  
  
- **ON_CBN_ERRSPACE** la zone de liste déroulante ne peut pas allouer suffisamment de mémoire pour répondre à une demande spécifique.  
  
- **ON_CBN_SELENDCANCEL** (Windows 3.1 et versions ultérieures). Indique la que sélection de l’utilisateur doit être annulée. L’utilisateur clique sur un élément, puis clique sur une autre fenêtre ou un contrôle pour masquer la zone de liste d’une zone de liste déroulante. Ce message de notification est envoyé avant le **CBN_CLOSEUP** message de notification pour indiquer que la sélection de l’utilisateur doit être ignorée. Le **CBN_SELENDCANCEL** ou **CBN_SELENDOK** message de notification est envoyée même si le **CBN_CLOSEUP** message de notification n’est pas envoyé (comme dans le cas d’une zone de liste déroulante avec le **CBS_SIMPLE** style).  
  
- **ON_CBN_SELENDOK** l’utilisateur sélectionne un élément puis appuie sur la touche entrée ou clique sur la flèche vers le bas pour masquer la zone de liste d’une zone de liste déroulante. Ce message de notification est envoyé avant le **CBN_CLOSEUP** message pour indiquer que la sélection d’utilisateur doit être considéré comme valide. Le **CBN_SELENDCANCEL** ou **CBN_SELENDOK** message de notification est envoyée même si le **CBN_CLOSEUP** message de notification n’est pas envoyé (comme dans le cas d’une zone de liste déroulante avec le **CBS_SIMPLE** style).  
  
- **ON_CBN_KILLFOCUS** la zone de liste déroulante perd le focus d’entrée.  
  
- **ON_CBN_SELCHANGE** la sélection dans la zone de liste d’une zone de liste déroulante est sur le point d’être modifié à la suite de l’utilisateur, en cliquant dans la zone de liste ou la modification de la sélection en utilisant les touches de direction. Lors du traitement de ce message, le texte du contrôle d’édition de la zone de liste modifiable peut uniquement être récupéré via `GetLBText` ou une autre fonction similaire. `GetWindowText` ne peut pas être utilisé.  
  
- **ON_CBN_SETFOCUS** la zone de liste déroulante reçoit le focus d’entrée.  
  
 Si vous créez un `CComboBox` objet dans une boîte de dialogue (via une ressource de boîte de dialogue), le `CComboBox` objet est automatiquement détruit lorsque l’utilisateur ferme la boîte de dialogue.  
  
 Si vous incorporez un `CComboBox` objet dans une autre fenêtre de l’objet, vous n’avez pas besoin de le détruire. Si vous créez le `CComboBox` de l’objet sur la pile, il est supprimé automatiquement. Si vous créez le `CComboBox` objet sur le tas à l’aide de la **nouveau** (fonction), vous devez appeler **supprimer** sur l’objet de suppression de la zone de liste déroulante Windows est détruite.  
  
 **Remarque** si vous souhaitez gérer `WM_KEYDOWN` et `WM_CHAR` messages, vous devrez sous-classer la zone de liste déroulante Modifier et les contrôles de zone de liste, dériver des classes de `CEdit` et `CListBox`, et ajouter des gestionnaires pour les messages à dérivé classes. Pour plus d’informations, consultez [ http://support.microsoft.com/default.aspxscid=kb; en-us ; Q174667](http://support.microsoft.com/default.aspxscid=kb;en-us;q174667) et [CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="addstring"></a>  CComboBox::AddString  
 Ajoute une chaîne à la zone de liste d’une zone de liste déroulante.  
  
```  
int AddString(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszString`  
 Pointe vers la chaîne se terminant par null qui doit être ajouté.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la valeur de retour est supérieure ou égale à 0, c’est l’index de base zéro à la chaîne dans la zone de liste. La valeur de retour est **CB_ERR** si une erreur se produit ; la valeur de retour est **CB_ERRSPACE** si l’espace est insuffisant stocker la nouvelle chaîne.  
  
### <a name="remarks"></a>Notes  
 Si la zone de liste n’a pas été créée avec le [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style, la chaîne est ajoutée à la fin de la liste. Sinon, la chaîne est insérée dans la liste, et la liste est triée.  
  
> [!NOTE]
>  Cette fonction n’est pas prise en charge par le contrôle Windows **ComboBoxEx** . Pour plus d’informations sur ce contrôle, consultez [contrôles ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) dans le Kit de développement logiciel Windows.  
  
 Pour insérer une chaîne dans un emplacement spécifique dans la liste, utilisez la [InsertString](#insertstring) fonction membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]  
  
##  <a name="ccombobox"></a>  CComboBox::CComboBox  
 Construit un objet `CComboBox`.  
  
```  
CComboBox();
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]  
  
##  <a name="clear"></a>  CComboBox::Clear  
 Supprime (efface) la sélection actuelle, le cas échéant, dans le contrôle d’édition de la zone de liste déroulante.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Notes  
 Pour supprimer la sélection actuelle et placer le contenu supprimé dans le Presse-papiers, utilisez le [couper](#cut) fonction membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]  
  
##  <a name="compareitem"></a>  CComboBox::CompareItem  
 Appelé par l’infrastructure pour déterminer la position relative d’un nouvel élément dans la partie zone de liste d’une zone de liste déroulante triée en mode owner-draw.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpCompareItemStruct`  
 Un pointeur long désignant un [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Indique la position relative des deux éléments décrits dans le `COMPAREITEMSTRUCT` structure. Il peut être une des valeurs suivantes :  
  
|Value|Signification|  
|-----------|-------------|  
|- 1|Élément 1 est trié avant l’élément 2.|  
|0|Élément 1 et 2 de l’élément de tri identiques.|  
|1|Élément 1 trie après l’élément 2.|  
  
 Consultez [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) pour obtenir une description de `COMPAREITEMSTRUCT`.  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette fonction membre ne fait rien. Si vous créez une zone de liste déroulante owner-draw avec les **LBS_SORT** style, vous devez substituer cette fonction membre pour vous aider à l’infrastructure de tri des nouveaux éléments ajoutés à la zone de liste.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]  
  
##  <a name="copy"></a>  CComboBox::Copy  
 Copie la sélection actuelle, les cas échéant, dans le contrôle d’édition de la zone de liste déroulante dans le Presse-papiers dans **CF_TEXT** format.  
  
```  
void Copy();
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]  
  
##  <a name="create"></a>  CComboBox::Create  
 Crée la zone de liste modifiable et l’attache à le `CComboBox` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie le style de la zone de liste déroulante. Appliquer n’importe quelle combinaison de [styles de zone de liste déroulante](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) à la zone.  
  
 `rect`  
 Pointe vers la position et la taille de la zone de liste déroulante. Peut être un [Rect, structure](../../mfc/reference/rect-structure1.md) ou un `CRect` objet.  
  
 `pParentWnd`  
 Spécifie la fenêtre parente de la zone de liste modifiable (généralement un `CDialog`). Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID du contrôle. de zone de liste déroulante  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Vous construisez un `CComboBox` objet en deux étapes. Tout d’abord, appelez le constructeur, puis **créer**, ce qui crée la zone de liste déroulante Windows et l’attache à le `CComboBox` objet.  
  
 Lorsque **créer** s’exécute, Windows envoie les [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), et [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) messages à la zone de liste déroulante.  
  
 Ces messages sont gérées par défaut par le [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), et [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) fonctions membres dans la `CWnd` classe de base. Pour étendre le traitement du message par défaut, dérivez une classe de `CComboBox`, ajouter une table des messages à la nouvelle classe et substituer les fonctions membres de gestionnaire de messages précédent. Substituer `OnCreate`, par exemple, pour effectuer l’initialisation nécessaire pour une nouvelle classe.  
  
 Appliquez ce qui suit [styles de fenêtre](../../mfc/reference/styles-used-by-mfc.md#window-styles) à un contrôle de zone de liste déroulante. :  
  
- **WS_CHILD** toujours  
  
- **WS_VISIBLE** généralement  
  
- **WS_DISABLED** rarement  
  
- **WS_VSCROLL** pour ajouter un défilement vertical de la zone de liste dans la zone de liste déroulante  
  
- **WS_HSCROLL** pour ajouter un défilement horizontal pour la zone de liste dans la zone de liste déroulante  
  
- **WS_GROUP** aux contrôles de groupe  
  
- **WS_TABSTOP** pour inclure la zone de liste modifiable dans l’ordre de tabulation  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]  
  
##  <a name="cut"></a>  CComboBox::Cut  
 Supprime (morceaux) contrôle de la sélection actuelle, si une, dans la zone de liste déroulante Modifier et copie le texte supprimé dans le Presse-papiers dans **CF_TEXT** format.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Notes  
 Pour supprimer la sélection actuelle sans la placer le texte supprimé dans le Presse-papiers, appelez le [clair](#clear) fonction membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]  
  
##  <a name="deleteitem"></a>  CComboBox::DeleteItem  
 Appelé par le framework lorsque l’utilisateur supprime un élément à partir d’un mode owner-draw `CComboBox` de l’objet ou détruit la zone de liste déroulante.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpDeleteItemStruct`  
 Un pointeur long vers Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) structure qui contient des informations sur l’élément supprimé. Consultez [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) pour obtenir une description de cette structure.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut de cette fonction est sans effet. Remplacez cette fonction pour redessiner la zone de liste déroulante, en fonction des besoins.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]  
  
##  <a name="deletestring"></a>  CComboBox::DeleteString  
 Supprime l’élément dans la position `nIndex` à partir de la zone de liste déroulante.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Spécifie l’index de la chaîne doit être supprimé.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la valeur de retour est supérieure ou égale à 0, il est un nombre de chaînes restants dans la liste. La valeur de retour est **CB_ERR** si `nIndex` spécifie un index supérieur au nombre d’éléments dans la liste.  
  
### <a name="remarks"></a>Notes  
 Tous les éléments qui suivent `nIndex` se déplacent vers le bas une position. Par exemple, si une zone de liste déroulante contient deux éléments, la suppression du premier élément provoquera l’élément restant à figurer dans la première position. `nIndex`= 0 pour l’élément dans la première position.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]  
  
##  <a name="dir"></a>  CComboBox::Dir  
 Ajoute une liste de noms de fichiers ou de lecteurs à la zone de liste d’une zone de liste déroulante.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Paramètres  
 `attr`  
 Peut être n’importe quelle combinaison de la `enum` valeurs décrites dans [CFile::GetStatus](../../mfc/reference/cfile-class.md#getstatus) ou n’importe quelle combinaison des valeurs suivantes :  
  
- **DDL_READWRITE** fichier peut être lu ou écrit à.  
  
- **DDL_READONLY** fichier puisse être lues mais ne pas écrite dans.  
  
- **DDL_HIDDEN** fichier est masqué et n’apparaît pas dans une liste de répertoires.  
  
- **DDL_SYSTEM** fichier est un fichier système.  
  
- **DDL_DIRECTORY** le nom spécifié par `lpszWildCard` spécifie un répertoire.  
  
- **DDL_ARCHIVE** fichier a été archivé.  
  
- **DDL_DRIVES** incluent tous les lecteurs qui correspondent au nom spécifié par `lpszWildCard`.  
  
- **DDL_EXCLUSIVE** indicateur Exclusive. Si la valeur de l’indicateur exclusive, seuls les fichiers du type spécifié sont répertoriés. Dans le cas contraire, les fichiers du type spécifié sont répertoriés en plus des fichiers « normales ».  
  
 `lpszWildCard`  
 Pointe vers une chaîne de spécification de fichier. La chaîne peut contenir des caractères génériques (par exemple, *.\*).  
  
### <a name="return-value"></a>Valeur de retour  
 Si la valeur de retour est supérieure ou égale à 0, c’est l’index de base zéro du dernier nom de fichier ajouté à la liste. La valeur de retour est **CB_ERR** si une erreur se produit ; la valeur de retour est **CB_ERRSPACE** si l’espace est insuffisant stocker les nouvelles chaînes.  
  
### <a name="remarks"></a>Notes  
 Cette fonction n’est pas prise en charge par le contrôle Windows **ComboBoxEx** . Pour plus d’informations sur ce contrôle, consultez [contrôles ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) dans le Kit de développement logiciel Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]  
  
##  <a name="drawitem"></a>  CComboBox::DrawItem  
 Appelé par le framework lorsqu’un aspect visuel d’une modification de zone de liste déroulante owner-draw.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpDrawItemStruct`  
 Un pointeur vers un [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) structure qui contient des informations sur le type de dessin nécessaire.  
  
### <a name="remarks"></a>Notes  
 Le **itemAction** membre de la `DRAWITEMSTRUCT` structure définit l’action de dessin qui doit être effectuée. Consultez [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) pour obtenir une description de cette structure.  
  
 Par défaut, cette fonction membre ne fait rien. Remplacez cette fonction membre pour implémenter le dessin pour un mode owner-draw `CComboBox` objet. Avant l’arrêt de cette fonction membre, l’application doit restaurer tous les objets interface GDI périphérique graphique sélectionnés pour le contexte d’affichage fournie dans `lpDrawItemStruct`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]  
  
##  <a name="findstring"></a>  CComboBox::FindString  
 Recherche, mais ne sélectionne la première chaîne qui contient le préfixe spécifié dans la zone de liste d’une zone de liste déroulante.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszString) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nStartAfter`  
 Contient l’index de base zéro de l’élément précédant le premier élément à rechercher. Lorsque la recherche atteint le bas de la zone de liste, il continue à partir du haut de la zone de liste à l’élément spécifié par `nStartAfter`. Si-1, la zone de liste entière est recherchée à partir du début.  
  
 `lpszString`  
 Pointe vers la chaîne se terminant par null qui contient le préfixe à rechercher. La recherche respecte la casse est indifférente, afin de cette chaîne peut contenir toute combinaison de lettres majuscules et les minuscules.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la valeur de retour est supérieure ou égale à 0, il est l’index de base zéro de l’élément correspondant. Il s’agit de **CB_ERR** si la recherche a échoué.  
  
### <a name="remarks"></a>Notes  
 Cette fonction n’est pas prise en charge par le contrôle Windows **ComboBoxEx** . Pour plus d’informations sur ce contrôle, consultez [contrôles ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) dans le Kit de développement logiciel Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]  
  
##  <a name="findstringexact"></a>  CComboBox::FindStringExact  
 Appelez le `FindStringExact` fonction membre pour rechercher la première chaîne de zone de liste (dans une zone de liste modifiable) qui correspond à la chaîne spécifiée dans `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndexStart`  
 Spécifie l’index de base zéro de l’élément précédant le premier élément à rechercher. Lorsque la recherche atteint le bas de la zone de liste, il continue à partir du haut de la zone de liste à l’élément spécifié par `nIndexStart`. Si `nIndexStart` est -1, la zone de liste entière est recherchée à partir du début.  
  
 `lpszFind`  
 Pointe vers la chaîne se terminant par null à rechercher. Cette chaîne peut contenir un nom de fichier complet, y compris l’extension. La recherche n’est pas la casse, cette chaîne peut contenir toute combinaison de lettres majuscules et les minuscules.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément correspondant, ou **CB_ERR** si la recherche a échoué.  
  
### <a name="remarks"></a>Notes  
 Si la zone de liste modifiable a été créée avec un style de mode owner-draw, mais sans le [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style, `FindStringExact` tente de faire correspondre la valeur DWORD par rapport à la valeur de `lpszFind`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]  
  
##  <a name="getcomboboxinfo"></a>  CComboBox::GetComboBoxInfo  
 Récupère les informations de la `CComboBox` objet.  
  
```  
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *pcbi*  
 Un pointeur vers le [COMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775798) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** en cas de réussite, **FALSE** en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre émule la fonctionnalité de la [CB_GETCOMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775839) d’un message, comme décrit dans le Kit de développement logiciel Windows.  
  
##  <a name="getcount"></a>  CComboBox::GetCount  
 Appelez cette fonction membre pour récupérer le nombre d’éléments dans la partie zone de liste d’une zone de liste déroulante.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments. Le nombre retourné est supérieure à la valeur d’index du dernier élément (l’index est de base zéro). Il s’agit de **CB_ERR** si une erreur se produit.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]  
  
##  <a name="getcuebanner"></a>  CComboBox::GetCueBanner  
 Obtient le texte d’indication qui s’affiche pour un contrôle de zone de liste déroulante.  
  
```  
CString GetCueBanner() const;  
  
BOOL GetCueBanner(
    LPTSTR lpszText,   
    int cchText) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[out] `lpszText`|Pointeur vers une mémoire tampon qui reçoit le texte de bannière de signal.|  
|[in] `cchText`|Taille de la mémoire tampon qui le `lpszText` paramètre pointe vers.|  
  
### <a name="return-value"></a>Valeur de retour  
 Dans la première surcharge, une [CString](../../atl-mfc-shared/using-cstring.md) objet qui contient le texte de bannière de signal si elle existe ; sinon, un `CString` objet qui a une longueur nulle.  
  
 - ou -  
  
 Dans la seconde surcharge, `true` si cette méthode réussit ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Texte d’indication est une invite s’affiche dans la zone d’entrée du contrôle de zone de liste déroulante. Le texte de la file d’attente est affiché jusqu'à ce que l’utilisateur fournit l’entrée.  
  
 Cette méthode envoie le [CB_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775843) message, ce qui est décrit dans le Kit de développement logiciel Windows.  
  
##  <a name="getcursel"></a>  CComboBox::GetCurSel  
 Appelez cette fonction membre pour déterminer quel élément dans la zone de liste modifiable est sélectionnée.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément actuellement sélectionné dans la zone de liste d’une zone de liste déroulante, ou **CB_ERR** si aucun élément n’est sélectionné.  
  
### <a name="remarks"></a>Notes  
 `GetCurSel` Retourne un index dans la liste.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]  
  
##  <a name="getdroppedcontrolrect"></a>  CComboBox::GetDroppedControlRect  
 Appelez le `GetDroppedControlRect` fonction membre pour récupérer les coordonnées d’écran de la zone visible (supprimé) de liste déroulante d’une zone de liste déroulante modifiable.  
  
```  
void GetDroppedControlRect(LPRECT lprect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *lprect*  
 Pointe vers le [Rect, structure](../../mfc/reference/rect-structure1.md) qui doit recevoir les coordonnées.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]  
  
##  <a name="getdroppedstate"></a>  CComboBox::GetDroppedState  
 Appelez le `GetDroppedState` fonction membre pour déterminer si la zone de liste d’une zone de liste déroulante modifiable est visible (déroulée).  
  
```  
BOOL GetDroppedState() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la zone de liste est visible ; Sinon, 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]  
  
##  <a name="getdroppedwidth"></a>  CComboBox::GetDroppedWidth  
 Appelez cette fonction pour récupérer la largeur minimale autorisée, en pixels, de la zone de liste d’une zone de liste déroulante.  
  
```  
int GetDroppedWidth() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 En cas de réussite, la largeur minimale autorisée, en pixels. dans le cas contraire, **CB_ERR**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction s’applique uniquement aux zones de liste déroulante avec la [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) ou [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style.  
  
 Par défaut, la largeur minimale autorisée de la zone de liste déroulante est 0. Largeur minimale autorisée peut être définie en appelant [SetDroppedWidth](#setdroppedwidth). Lorsque la partie de la zone de liste de la zone de liste déroulante s’affiche, sa largeur est le plus grand de la largeur minimale autorisée ou la largeur de zone de liste déroulante.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [SetDroppedWidth](#setdroppedwidth).  
  
##  <a name="geteditsel"></a>  CComboBox::GetEditSel  
 Obtient les positions de caractère de début et de fin de la sélection actuelle dans le contrôle d’édition d’une zone de liste déroulante.  
  
```  
DWORD GetEditSel() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur de 32 bits qui contient la position de départ dans le mot de poids faible et de la position du premier caractère non sélectionnée après la fin de la sélection dans le mot de poids fort. Si cette fonction est utilisée sur une zone de liste déroulante sans un contrôle d’édition, **CB_ERR** est retourné.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]  
  
##  <a name="getextendedui"></a>  CComboBox::GetExtendedUI  
 Appelez le `GetExtendedUI` fonction membre pour déterminer si une zone de liste déroulante contient l’interface utilisateur par défaut ou l’interface utilisateur améliorée.  
  
```  
BOOL GetExtendedUI() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la zone de liste modifiable a l’interface utilisateur améliorée ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 L’interface utilisateur améliorée peut être identifiée comme suit :  
  
-   En cliquant sur le contrôle statique affiche la liste uniquement pour les zones de liste déroulante avec la [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style.  
  
-   Appuyez sur la touche flèche vers le bas affiche la zone de liste (F4 est désactivée).  
  
 Le défilement dans le contrôle statique est désactivé lors de la liste d’éléments n’est pas visible (flèche clés sont désactivées).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]  
  
##  <a name="gethorizontalextent"></a>  CComboBox::GetHorizontalExtent  
 Récupère la largeur en pixels, par laquelle la partie de la zone de liste de la zone de liste modifiable peut défiler horizontalement dans la zone de liste déroulante.  
  
```  
UINT GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La largeur de défilement de la partie de la zone de liste de la zone de liste déroulante, en pixels.  
  
### <a name="remarks"></a>Notes  
 Cela s’applique uniquement si la partie de la zone de liste de la zone de liste déroulante comporte une barre de défilement horizontale.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]  
  
##  <a name="getitemdata"></a>  CComboBox::GetItemData  
 Récupère la valeur de 32 bits fournie par l’application associée à l’élément spécifié de zone de liste déroulante.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Contient l’index de base zéro d’un élément dans la zone de liste de la zone de liste modifiable.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de 32 bits associée à l’élément, ou **CB_ERR** si une erreur se produit.  
  
### <a name="remarks"></a>Notes  
 La valeur de 32 bits peut être définie avec la `dwItemData` paramètre d’un [SetItemData](#setitemdata) appel de fonction membre. Utilisez le `GetItemDataPtr` fonction membre si la valeur de 32 bits doit être récupéré est un pointeur ( **void\***).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]  
  
##  <a name="getitemdataptr"></a>  CComboBox::GetItemDataPtr  
 Récupère la valeur de 32 bits fournie par l’application associée à l’élément de zone de liste déroulante spécifié en tant que pointeur ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Contient l’index de base zéro d’un élément dans la zone de liste de la zone de liste modifiable.  
  
### <a name="return-value"></a>Valeur de retour  
 Récupère un pointeur, ou -1 si une erreur se produit.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]  
  
##  <a name="getitemheight"></a>  CComboBox::GetItemHeight  
 Appelez le `GetItemHeight` fonction membre pour récupérer la hauteur des éléments de liste dans une zone de liste déroulante.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Spécifie le composant de la zone de liste déroulante dont la hauteur doit être récupéré. Si le `nIndex` paramètre est -1, la hauteur de la partie du contrôle d’édition (ou texte statique) de la zone de liste déroulante est récupérée. Si la zone de liste modifiable a la [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style, `nIndex` Spécifie l’index de base zéro de l’élément de liste dont la hauteur doit être récupéré. Dans le cas contraire, `nIndex` doit être définie sur 0.  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur, en pixels, de l’élément spécifié dans une zone de liste déroulante. La valeur de retour est **CB_ERR** si une erreur se produit.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]  
  
##  <a name="getlbtext"></a>  CComboBox::GetLBText  
 Obtient une chaîne à partir de la zone de liste d’une zone de liste déroulante.  
  
```  
int GetLBText(
    int nIndex,  
    LPTSTR lpszText) const;  
  
void GetLBText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Contient l’index de base zéro de la chaîne de la zone de liste doit être copié.  
  
 `lpszText`  
 Pointe vers une mémoire tampon pour recevoir la chaîne. La mémoire tampon d’espace disponible est suffisant pour la chaîne et un caractère null de fin.  
  
 `rString`  
 Une référence à un `CString`.  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur (en octets) de la chaîne, à l’exclusion du caractère null de fin. Si `nIndex` ne spécifie pas un index valide, la valeur de retour est **CB_ERR**.  
  
### <a name="remarks"></a>Notes  
 La deuxième forme de ce membre fonction remplit un `CString` avec le texte de l’élément.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]  
  
##  <a name="getlbtextlen"></a>  CComboBox::GetLBTextLen  
 Obtient la longueur d’une chaîne dans la zone de liste d’une zone de liste déroulante.  
  
```  
int GetLBTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Contient l’index de base zéro de la chaîne de la zone de liste.  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur de la chaîne en octets, à l’exclusion du caractère null de fin. Si `nIndex` ne spécifie pas un index valide, la valeur de retour est **CB_ERR**.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CComboBox::GetLBText](#getlbtext).  
  
##  <a name="getlocale"></a>  CComboBox::GetLocale  
 Récupère les paramètres régionaux utilisés par la zone de liste déroulante.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur d’identificateur (LCID) de paramètres régionaux pour les chaînes dans la zone de liste déroulante.  
  
### <a name="remarks"></a>Notes  
 Les paramètres régionaux sont utilisé, par exemple, pour déterminer l’ordre de tri des chaînes dans une zone de liste déroulante triée.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CComboBox::SetLocale](#setlocale).  
  
##  <a name="getminvisible"></a>  CComboBox::GetMinVisible  
 Obtient le nombre minimal d’éléments visibles dans la liste déroulante du contrôle zone de liste déroulante en cours.  
  
```  
int GetMinVisible() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre minimal d’éléments visibles dans la liste déroulante active.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [CB_GETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) message, ce qui est décrit dans le Kit de développement logiciel Windows.  
  
##  <a name="gettopindex"></a>  CComboBox::GetTopIndex  
 Récupère l’index de base zéro du premier élément visible dans la partie de la zone de liste de la zone de liste déroulante.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro du premier élément visible dans la partie de la zone de liste de la zone de liste déroulante en cas de réussite, **CB_ERR** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Au départ, l’élément 0 est en haut de la zone de liste, mais si le défilement de la zone de liste, un autre élément peut être en haut.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]  
  
##  <a name="initstorage"></a>  CComboBox::InitStorage  
 Alloue la mémoire pour le stockage des éléments de liste dans la partie de la zone de liste de la zone de liste déroulante.  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Paramètres  
 `nItems`  
 Spécifie le nombre d’éléments à ajouter.  
  
 `nBytes`  
 Spécifie la quantité de mémoire, en octets, à allouer pour les chaînes de l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Si réussie, le nombre maximal d’éléments que la partie de la zone de liste de la zone de liste modifiable peut stocker une réallocation de la mémoire est nécessaire avant de **CB_ERRSPACE**, ce qui signifie que pas assez de mémoire est disponible.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction avant d’ajouter un grand nombre d’éléments à la partie zone de liste de la `CComboBox`.  
  
 Windows 95/98 : le `wParam` paramètre est limité aux valeurs 16 bits. Cela signifie que les zones de liste ne peut pas contenir d’éléments de plus de 32 767. Bien que le nombre d’éléments est limité, la taille totale des éléments dans une zone de liste est limitée uniquement par la mémoire disponible.  
  
 Cette fonction permet d’accélérer l’initialisation des zones de liste qui ont un grand nombre d’éléments (plus de 100). Il pré-alloue la quantité spécifiée de mémoire suivante qui [AddString](#addstring), [InsertString](#insertstring), et [Dir](#dir) fonctions acceptent les plus brefs délais. Vous pouvez utiliser des estimations pour les paramètres. Si vous surestimer, la mémoire supplémentaire est allouée ; Si vous sous-estimez, l’allocation normale est utilisée pour les éléments qui dépassent le montant préalloué.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]  
  
##  <a name="insertstring"></a>  CComboBox::InsertString  
 Insère une chaîne dans la zone de liste d’une zone de liste modifiable.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Contient l’index de base zéro de la position dans la zone de liste qui doit recevoir la chaîne. Si ce paramètre est -1, la chaîne est ajoutée à la fin de la liste.  
  
 `lpszString`  
 Pointe vers la chaîne terminée par le caractère null qui doit être insérée.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de la position à laquelle la chaîne a été insérée. La valeur de retour est **CB_ERR** si une erreur se produit. La valeur de retour est **CB_ERRSPACE** si l’espace disponible est insuffisant pour stocker la nouvelle chaîne.  
  
### <a name="remarks"></a>Notes  
 Contrairement à la [AddString](#addstring) fonction membre, le `InsertString` fonction membre ne provoque pas d’une liste avec la [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style à trier.  
  
> [!NOTE]
>  Cette fonction n’est pas prise en charge par le contrôle Windows **ComboBoxEx** . Pour plus d’informations sur ce contrôle, consultez [contrôles ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) dans le Kit de développement logiciel Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]  
  
##  <a name="limittext"></a>  CComboBox::LimitText  
 Limite la longueur en octets du texte que l’utilisateur peut entrer dans le contrôle d’édition d’une zone de liste déroulante.  
  
```  
BOOL LimitText(int nMaxChars);
```  
  
### <a name="parameters"></a>Paramètres  
 `nMaxChars`  
 Spécifie la longueur (en octets) du texte que l’utilisateur peut entrer. Si ce paramètre est 0, la longueur du texte est définie à 65 535 octets.  
  
### <a name="return-value"></a>Valeur de retour  
 Non nul en cas de réussite. Si elle est appelée pour une zone de liste déroulante avec le style [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) ou d’une zone de liste déroulante sans un contrôle d’édition, la valeur de retour est **CB_ERR**.  
  
### <a name="remarks"></a>Notes  
 Si la zone de liste déroulante n’a pas le style [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles), définissant la limite supérieure à la taille du contrôle d’édition de texte n’a aucun effet.  
  
 `LimitText` limite uniquement le texte de que l’utilisateur peut entrer. Il n’a aucun effet sur n’importe quel texte déjà dans le contrôle d’édition lorsque le message est envoyé, ni n’affecte pas la longueur du texte copié dans le contrôle d’édition lorsqu’une chaîne dans la zone de liste est sélectionnée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]  
  
##  <a name="measureitem"></a>  CComboBox::MeasureItem  
 Appelé par l’infrastructure lors de la création d’une zone de liste déroulante avec un style de mode owner-draw.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpMeasureItemStruct`  
 Un pointeur long désignant un [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) structure.  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette fonction membre ne fait rien. Remplacez cette fonction membre et renseignez la `MEASUREITEMSTRUCT` structure pour informer Windows les dimensions de la liste de zone dans la zone de liste déroulante. Si la zone de liste modifiable est créée avec le [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style, l’infrastructure appelle cette fonction membre pour chaque élément dans la zone de liste. Sinon, ce membre est appelé une seule fois.  
  
 À l’aide de la **CBS_OWNERDRAWFIXED** style dans une zone de liste déroulante owner-draw créée avec le [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) fonction membre de `CWnd` implique des considérations sur la programmation supplémentaire. Consultez la discussion dans [Technical Note 14](../../mfc/tn014-custom-controls.md).  
  
 Consultez [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) pour obtenir une description de la `MEASUREITEMSTRUCT` structure.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]  
  
##  <a name="paste"></a>  CComboBox::Paste  
 Insère les données à partir du Presse-papiers dans le contrôle d’édition de la zone de liste déroulante à la position actuelle du curseur.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Notes  
 Les données sont insérées que si le Presse-papiers contient des données **CF_TEXT** format.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]  
  
##  <a name="resetcontent"></a>  CComboBox::ResetContent  
 Supprime tous les éléments de la liste de zone et de modifier le contrôle de zone de liste déroulante.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]  
  
##  <a name="selectstring"></a>  CComboBox::SelectString  
 Recherche une chaîne dans la zone de liste d’une zone de liste modifiable et si la chaîne est trouvée, sélectionne la chaîne dans la zone de liste et le copie dans le contrôle d’édition.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Paramètres  
 `nStartAfter`  
 Contient l’index de base zéro de l’élément précédant le premier élément à rechercher. Lorsque la recherche atteint le bas de la zone de liste, il continue à partir du haut de la zone de liste à l’élément spécifié par `nStartAfter`. Si-1, la zone de liste entière est recherchée à partir du début.  
  
 `lpszString`  
 Pointe vers la chaîne se terminant par null qui contient le préfixe à rechercher. La recherche respecte la casse est indifférente, afin de cette chaîne peut contenir toute combinaison de lettres majuscules et les minuscules.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément sélectionné si la chaîne a été trouvée. Si la recherche a échoué, la valeur de retour est **CB_ERR** et la sélection actuelle n’est pas modifiée.  
  
### <a name="remarks"></a>Notes  
 Une chaîne est activée uniquement si ses premiers caractères (du point de départ) correspondent aux caractères dans la chaîne de préfixe.  
  
 Notez que la `SelectString` et `FindString` fonctions membres rechercher une chaîne, mais la `SelectString` fonction membre sélectionne également la chaîne.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]  
  
##  <a name="setcuebanner"></a>  CComboBox::SetCueBanner  
 Définit le texte de la file d’attente qui est affiché pour un contrôle de zone de liste déroulante.  
  
```  
BOOL SetCueBanner(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] *lpszText*|Pointeur vers une mémoire tampon se terminant par null qui contient le texte de la file d’attente.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode réussit ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Texte d’indication est une invite s’affiche dans la zone d’entrée du contrôle de zone de liste déroulante. Le texte de la file d’attente est affiché jusqu'à ce que l’utilisateur fournit l’entrée.  
  
 Cette méthode envoie le [CB_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775897) message, ce qui est décrit dans le Kit de développement logiciel Windows.  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_combobox`, qui est utilisé pour accéder par programme le contrôle de zone de liste déroulante. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la bannière de signal pour le contrôle de zone de liste déroulante.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="setcursel"></a>  CComboBox::SetCurSel  
 Sélectionne une chaîne dans la zone de liste d’une zone de liste déroulante.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Paramètres  
 `nSelect`  
 Spécifie l’index de base zéro de la chaîne à sélectionner. Si -1, la sélection actuelle dans la zone de liste est supprimée et le contrôle d’édition est désactivé.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément sélectionné si le message a réussi. La valeur de retour est **CB_ERR** si `nSelect` est supérieur au nombre d’éléments dans la liste ou si `nSelect` a la valeur -1, ce qui efface la sélection.  
  
### <a name="remarks"></a>Notes  
 Si nécessaire, la zone de liste fait défiler la chaîne dans la vue (si la zone de liste est visible). Le texte du contrôle d’édition de la zone de liste modifiable est modifié pour refléter la nouvelle sélection. Sélection précédente dans la zone de liste est supprimée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]  
  
##  <a name="setdroppedwidth"></a>  CComboBox::SetDroppedWidth  
 Appelez cette fonction pour définir la largeur minimale autorisée, en pixels, de la zone de liste d’une zone de liste déroulante.  
  
```  
int SetDroppedWidth(UINT nWidth);
```  
  
### <a name="parameters"></a>Paramètres  
 `nWidth`  
 La largeur minimale autorisée de la partie de la zone de liste de la zone de liste déroulante, en pixels.  
  
### <a name="return-value"></a>Valeur de retour  
 Si réussie, la nouvelle largeur de la liste de zone, sinon **CB_ERR**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction s’applique uniquement aux zones de liste déroulante avec la [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) ou [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style.  
  
 Par défaut, la largeur minimale autorisée de la zone de liste déroulante est 0. Lorsque la partie de la zone de liste de la zone de liste déroulante s’affiche, sa largeur est le plus grand de la largeur minimale autorisée ou la largeur de zone de liste déroulante.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]  
  
##  <a name="seteditsel"></a>  CComboBox::SetEditSel  
 Sélectionne des caractères dans le contrôle d’édition d’une zone de liste déroulante.  
  
```  
BOOL SetEditSel(
    int nStartChar,  
    int nEndChar);
```  
  
### <a name="parameters"></a>Paramètres  
 `nStartChar`  
 Spécifie la position de départ. Si la position de départ est définie sur -1, une sélection existante est supprimée.  
  
 `nEndChar`  
 Spécifie la position de fin. Si la position de fin est définie sur -1, puis tout le texte de la position de départ au dernier caractère dans le contrôle d’édition est sélectionné.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction membre réussit ; Sinon, 0. Il s’agit de **CB_ERR** si `CComboBox` a le [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style ou ne dispose pas d’une zone de liste.  
  
### <a name="remarks"></a>Notes  
 Les positions sont de base zéro. Pour sélectionner le premier caractère du contrôle d’édition, vous spécifiez une position de départ de 0. La position de fin est le caractère juste après le dernier caractère à sélectionner. Par exemple, pour sélectionner les quatre premiers caractères du contrôle d’édition, vous utiliseriez une position de départ de 0 et une position de fin de 4.  
  
> [!NOTE]
>  Cette fonction n’est pas prise en charge par le contrôle Windows **ComboBoxEx** . Pour plus d’informations sur ce contrôle, consultez [contrôles ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775738) dans le Kit de développement logiciel Windows.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CComboBox::GetEditSel](#geteditsel).  
  
##  <a name="setextendedui"></a>  CComboBox::SetExtendedUI  
 Appelez le `SetExtendedUI` fonction membre pour sélectionner l’interface utilisateur par défaut ou l’interface utilisateur améliorée pour la zone de liste modifiable a la [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) ou [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style.  
  
```  
int SetExtendedUI(BOOL bExtended = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 *bLa*  
 Spécifie si la zone de liste modifiable doit utiliser l’interface utilisateur améliorée ou l’interface utilisateur par défaut. La valeur **TRUE** sélectionne l’étendue interface utilisateur ; la valeur **FALSE** sélectionne l’interface utilisateur standard.  
  
### <a name="return-value"></a>Valeur de retour  
 **CB_OKAY** si l’opération a réussi, ou **CB_ERR** si une erreur se produit.  
  
### <a name="remarks"></a>Notes  
 L’interface utilisateur améliorée peut être identifiée comme suit :  
  
-   En cliquant sur le contrôle statique affiche la liste uniquement pour les zones de liste déroulante avec la **CBS_DROPDOWNLIST** style.  
  
-   Appuyez sur la touche flèche vers le bas affiche la zone de liste (F4 est désactivée).  
  
 Le défilement dans le contrôle statique est désactivé lorsque la liste d’éléments n’est pas visible (les touches de direction sont désactivées).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CComboBox::GetExtendedUI](#getextendedui).  
  
##  <a name="sethorizontalextent"></a>  CComboBox::SetHorizontalExtent  
 Définit la largeur, en pixels, par laquelle la partie de la zone de liste de la zone de liste modifiable peut défiler horizontalement.  
  
```  
void SetHorizontalExtent(UINT nExtent);
```  
  
### <a name="parameters"></a>Paramètres  
 *nExtent*  
 Spécifie le nombre de pixels par lequel la partie de la zone de liste de la zone de liste modifiable peut défiler horizontalement.  
  
### <a name="remarks"></a>Notes  
 Si la largeur de la zone de liste est inférieure à cette valeur, la barre de défilement horizontale défile horizontalement les éléments dans la zone de liste. Si la largeur de la zone de liste est égale ou supérieure à cette valeur, la barre de défilement horizontale est masquée ou, si la zone de liste modifiable a la [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style, désactivé.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]  
  
##  <a name="setitemdata"></a>  CComboBox::SetItemData  
 Définit la valeur de 32 bits associée à l’élément spécifié dans une zone de liste déroulante.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Contient un index de base zéro de l’élément à définir.  
  
 `dwItemData`  
 Contient la nouvelle valeur à associer à l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 **CB_ERR** si une erreur se produit.  
  
### <a name="remarks"></a>Notes  
 Utilisez le `SetItemDataPtr` fonction membre si l’élément 32 bits doit être un pointeur.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]  
  
##  <a name="setitemdataptr"></a>  CComboBox::SetItemDataPtr  
 Définit la valeur de 32 bits associée à l’élément spécifié dans une zone de liste déroulante pour être le pointeur spécifié ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Contient un index de base zéro de l’élément.  
  
 `pData`  
 Contient le pointeur à associer à l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 **CB_ERR** si une erreur se produit.  
  
### <a name="remarks"></a>Notes  
 Ce pointeur reste valide pour la durée de vie de la zone de liste déroulante, même si la position relative de l’élément dans la zone de liste modifiable peut changer en fonction des éléments sont ajoutés ou supprimés. Par conséquent, l’index de l’élément dans la zone peut modifier, mais le pointeur reste fiable.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]  
  
##  <a name="setitemheight"></a>  CComboBox::SetItemHeight  
 Appelez le `SetItemHeight` fonction membre pour définir la hauteur des éléments de liste dans une zone de liste déroulante ou la hauteur de la partie du contrôle d’édition (ou texte statique) d’une zone de liste déroulante.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Spécifie si la hauteur des éléments de liste ou de la hauteur de la partie du contrôle d’édition (ou texte statique) de la zone de liste déroulante est définie.  
  
 Si la zone de liste modifiable a la [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style, `nIndex` Spécifie l’index de base zéro de l’élément de liste dont la hauteur doit être définie ; sinon, `nIndex` doit être 0 et la hauteur de la liste de tous les éléments définira.  
  
 Si `nIndex` est -1, la hauteur du contrôle d’édition ou la partie de texte statique de la zone de liste déroulante doit être défini.  
  
 `cyItemHeight`  
 Spécifie la hauteur, en pixels, du composant de zone de liste déroulante identifié par `nIndex`.  
  
### <a name="return-value"></a>Valeur de retour  
 **CB_ERR** si l’index ou la hauteur n’est pas valide ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La hauteur de la partie du contrôle d’édition (ou texte statique) de la zone de liste déroulante est définie indépendamment de la hauteur des éléments de liste. Une application doit garantir que la hauteur de la partie du contrôle d’édition (ou texte statique) n’est pas inférieure à la hauteur d’un élément de zone de liste particulière.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]  
  
##  <a name="setlocale"></a>  CComboBox::SetLocale  
 Définit l’identificateur de paramètres régionaux pour cette zone de liste déroulante.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Paramètres  
 `nNewLocale`  
 La nouvelle valeur de l’identificateur (LCID) de paramètres régionaux à définir pour la zone de liste déroulante.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur d’identificateur (LCID) locale précédent pour cette zone de liste déroulante.  
  
### <a name="remarks"></a>Notes  
 Si **SetLocale** n’est pas appelée, la valeur par défaut aux paramètres régionaux sont obtenue à partir du système. Ce paramètres régionaux par défaut du système peut être modifiée à l’aide du panneau application régionales (ou International).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]  
  
##  <a name="setminvisibleitems"></a>  CComboBox::SetMinVisibleItems  
 Définit le nombre minimal d’éléments visibles dans la liste déroulante de la zone de liste déroulante en cours de contrôle de zone.  
  
```  
BOOL SetMinVisibleItems(int iMinVisible);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `iMinVisible`|Spécifie le nombre minimal d’éléments visibles.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [CB_SETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) message, ce qui est décrit dans le Kit de développement logiciel Windows.  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_combobox`, qui est utilisé pour accéder par programme le contrôle de zone de liste déroulante. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant insère 20 éléments dans la liste déroulante d’un contrôle de zone de liste déroulante. Il spécifie ensuite qu’un minimum de 10 éléments affichés lorsqu’un utilisateur appuie sur la flèche déroulante.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="settopindex"></a>  CComboBox::SetTopIndex  
 Garantit qu’un élément particulier est visible dans la partie de la zone de liste de la zone de liste déroulante.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Spécifie l’index de base zéro de l’élément de zone de liste.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro en cas de réussite, ou **CB_ERR** si une erreur se produit.  
  
### <a name="remarks"></a>Notes  
 Le système fait défiler la liste jusqu'à ce que soit l’élément spécifié par `nIndex` s’affiche en haut de la liste de zone ou la plage de défilement maximal a été atteint.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]  
  
##  <a name="showdropdown"></a>  CComboBox::ShowDropDown  
 Affiche ou masque la zone de liste d’une zone de liste modifiable a la [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) ou [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style.  
  
```  
void ShowDropDown(BOOL bShowIt = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 *bShowIt*  
 Spécifie si la zone de liste déroulante doit être affichée ou masquée. La valeur **TRUE** montre la zone de liste. La valeur **FALSE** masque la zone de liste.  
  
### <a name="remarks"></a>Notes  
 Par défaut, une zone de liste modifiable de ce style affiche la zone de liste.  
  
 Cette fonction membre n’a aucun effet sur une zone de liste modifiable créée avec la [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) style.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CComboBox::GetDroppedState](#getdroppedstate).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Classe de CButton](../../mfc/reference/cbutton-class.md)   
 [Classe CEdit](../../mfc/reference/cedit-class.md)   
 [CListBox (classe)](../../mfc/reference/clistbox-class.md)   
 [Classe de CScrollBar](../../mfc/reference/cscrollbar-class.md)   
 [Classe de CStatic](../../mfc/reference/cstatic-class.md)   
 [CDialog, classe](../../mfc/reference/cdialog-class.md)
