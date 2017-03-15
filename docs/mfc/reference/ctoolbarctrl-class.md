---
title: CToolBarCtrl (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class
- Windows common controls [C++], CToolBarCtrl
- toolbar controls [MFC], CToolBarCtrl class
- tool tips [C++], notifications
ms.assetid: 8f2f8ad2-05d7-4975-8715-3f2eed795248
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
ms.openlocfilehash: 2d3ec23d6147299d9a615e9edb0d3f90680bbfac
ms.lasthandoff: 02/24/2017

---
# <a name="ctoolbarctrl-class"></a>CToolBarCtrl (classe)
Fournit les fonctionnalités du contrôle commun de barre d'outils Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CToolBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CToolBarCtrl::CToolBarCtrl](#ctoolbarctrl)|Construit un objet `CToolBarCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CToolBarCtrl::AddBitmap](#addbitmap)|Ajoute une ou plusieurs images de bouton bitmap à la liste des images de bouton disponibles pour un contrôle de barre d’outils.|  
|[CToolBarCtrl::AddButtons](#addbuttons)|Ajoute un ou plusieurs boutons à un contrôle de barre d’outils.|  
|[CToolBarCtrl::AddString](#addstring)|Ajoute une nouvelle chaîne, passée comme un ID de ressource à la liste interne de la barre d’outils de chaînes.|  
|[CToolBarCtrl::AddStrings](#addstrings)|Ajoute une nouvelle chaîne ou des chaînes, passés en tant que pointeur vers une mémoire tampon de chaînes séparées par null, à la liste interne de la barre d’outils de chaînes.|  
|[CToolBarCtrl::AutoSize](#autosize)|Redimensionne un contrôle de barre d’outils.|  
|[CToolBarCtrl::ChangeBitmap](#changebitmap)|Modifie la bitmap pour un bouton dans le contrôle de barre d’outils en cours.|  
|[CToolBarCtrl::CheckButton](#checkbutton)|Active ou désactive un bouton donné dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::CommandToIndex](#commandtoindex)|Récupère l’index de base zéro pour le bouton associé à l’identificateur de commande spécifié.|  
|[CToolBarCtrl::Create](#create)|Crée un contrôle de barre d’outils et l’attache à une `CToolBarCtrl` objet.|  
|[CToolBarCtrl::CreateEx](#createex)|Crée un contrôle de barre d’outils avec les styles étendus Windows spécifiés et l’attache à une `CToolBarCtrl` objet.|  
|[CToolBarCtrl::Customize](#customize)|Affiche la boîte de dialogue Personnaliser la barre d’outils.|  
|[CToolBarCtrl::DeleteButton](#deletebutton)|Supprime un bouton à partir du contrôle de barre d’outils.|  
|[CToolBarCtrl::EnableButton](#enablebutton)|Active ou désactive le bouton spécifié dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::GetAnchorHighlight](#getanchorhighlight)|Récupère la mise en surbrillance d’ancrage définition pour une barre d’outils.|  
|[CToolBarCtrl::GetBitmap](#getbitmap)|Récupère l’index de l’image bitmap associée à un bouton dans une barre d’outils.|  
|[CToolBarCtrl::GetBitmapFlags](#getbitmapflags)|Obtient les indicateurs associés le bitmap de la barre d’outils.|  
|[CToolBarCtrl::GetButton](#getbutton)|Récupère des informations sur le bouton spécifié dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::GetButtonCount](#getbuttoncount)|Récupère un nombre de boutons actuellement dans le contrôle de barre d’outils.|  
|[CToolBarCtrl::GetButtonInfo](#getbuttoninfo)|Récupère les informations d’un bouton dans une barre d’outils.|  
|[CToolBarCtrl::GetButtonSize](#getbuttonsize)|Récupère la largeur et la hauteur des boutons de barre d’outils, en pixels.|  
|[CToolBarCtrl::GetColorScheme](#getcolorscheme)|Récupère le jeu de couleurs du contrôle barre d’outils en cours.|  
|[CToolBarCtrl::GetDisabledImageList](#getdisabledimagelist)|Récupère la liste d’images par un contrôle de barre d’outils pour les boutons d’affichage désactivé.|  
|[CToolBarCtrl::GetDropTarget](#getdroptarget)|Récupère le [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) interface pour un contrôle de barre d’outils.|  
|[CToolBarCtrl::GetExtendedStyle](#getextendedstyle)|Récupère les styles étendus pour un contrôle de barre d’outils.|  
|[CToolBarCtrl::GetHotImageList](#gethotimagelist)|Récupère la liste d’images par un contrôle de barre d’outils pour afficher des boutons « chaud ». Un bouton actif apparaît en surbrillance lorsque le pointeur de la souris est au-dessus de lui.|  
|[CToolBarCtrl::GetHotItem](#gethotitem)|Récupère l’index de l’élément dans une barre d’outils Accès rapide.|  
|[CToolBarCtrl::GetImageList](#getimagelist)|Récupère la liste d’images par un contrôle de barre d’outils pour afficher les boutons dans leur état par défaut.|  
|[CToolBarCtrl::GetInsertMark](#getinsertmark)|Récupère la marque d’insertion en cours de la barre d’outils.|  
|[CToolBarCtrl::GetInsertMarkColor](#getinsertmarkcolor)|Récupère la couleur utilisée pour dessiner la marque d’insertion de la barre d’outils.|  
|[CToolBarCtrl::GetItemRect](#getitemrect)|Récupère le rectangle englobant d’un bouton dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::GetMaxSize](#getmaxsize)|Récupère la taille totale de tous les boutons visibles et les séparateurs dans la barre d’outils.|  
|[CToolBarCtrl::GetMaxTextRows](#getmaxtextrows)|Récupère le nombre maximal de lignes de texte affichées sur un bouton de barre d’outils.|  
|[CToolBarCtrl::GetMetrics](#getmetrics)|Récupère les mesures d’un contrôle de barre d’outils.|  
|[CToolBarCtrl::GetPadding](#getpadding)|Récupère la marge horizontale et verticale du contrôle barre d’outils en cours.|  
|[CToolBarCtrl::GetPressedImageList](#getpressedimagelist)|Récupère la liste d’images que le contrôle de barre d’outils actuelle utilise pour représenter les boutons à l’état enfoncé.|  
|[CToolBarCtrl::GetRect](#getrect)|Récupère le rectangle englobant d’un bouton de barre d’outils spécifiée.|  
|[CToolBarCtrl::GetRows](#getrows)|Récupère le nombre de lignes de boutons actuellement affichés dans la barre d’outils.|  
|[CToolBarCtrl::GetState](#getstate)|Récupère des informations sur l’état du bouton spécifié dans un contrôle de barre d’outils, tels que s’il est activé, activé ou activé.|  
|[CToolBarCtrl::GetString](#getstring)|Récupère une chaîne de la barre d’outils.|  
|[CToolBarCtrl::GetStyle](#getstyle)|Récupère les styles en cours d’utilisation pour un contrôle de barre d’outils.|  
|[CToolBarCtrl::GetToolTips](#gettooltips)|Récupère le handle du contrôle ToolTip, si un, associé au contrôle de barre d’outils.|  
|[CToolBarCtrl::HideButton](#hidebutton)|Masque ou affiche le bouton spécifié dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::HitTest](#hittest)|Détermine où se trouve un point dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::Indeterminate](#indeterminate)|Active ou désactive l’état indéterminé (gris) du bouton spécifié dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::InsertButton](#insertbutton)|Insère un bouton dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::InsertMarkHitTest](#insertmarkhittest)|Récupère les informations de marque d’insertion d’un point dans une barre d’outils.|  
|[CToolBarCtrl::IsButtonChecked](#isbuttonchecked)|Indique si le bouton spécifié dans un contrôle de barre d’outils est activé.|  
|[CToolBarCtrl::IsButtonEnabled](#isbuttonenabled)|Indique si le bouton spécifié dans un contrôle de barre d’outils est activé.|  
|[CToolBarCtrl::IsButtonHidden](#isbuttonhidden)|Indique si le bouton spécifié dans un contrôle de barre d’outils est masqué.|  
|[CToolBarCtrl::IsButtonHighlighted](#isbuttonhighlighted)|Vérifie l’état de mise en surbrillance du bouton de barre d’outils.|  
|[CToolBarCtrl::IsButtonIndeterminate](#isbuttonindeterminate)|Indique si l’état du bouton spécifié dans un contrôle de barre d’outils est indéterminé (gris).|  
|[CToolBarCtrl::IsButtonPressed](#isbuttonpressed)|Indique si le bouton spécifié dans un contrôle de barre d’outils est enfoncé.|  
|[CToolBarCtrl::LoadImages](#loadimages)|Charge les images bitmap dans la liste d’images d’un contrôle de barre d’outils.|  
|[CToolBarCtrl::MapAccelerator](#mapaccelerator)|Mappe un caractère accélérateur à un bouton de barre d’outils.|  
|[CToolBarCtrl::MarkButton](#markbutton)|Définit l’état de mise en surbrillance d’un bouton donné dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::MoveButton](#movebutton)|Déplace un bouton à partir d’un index à l’autre.|  
|[CToolBarCtrl::PressButton](#pressbutton)|Appuie ou relâche le bouton spécifié dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::ReplaceBitmap](#replacebitmap)|Remplace le bitmap existante dans le contrôle de barre d’outils actuelle par une nouvelle image bitmap.|  
|[CToolBarCtrl::RestoreState](#restorestate)|Restaure l’état du contrôle de barre d’outils.|  
|[CToolBarCtrl::SaveState](#savestate)|Enregistre l’état du contrôle de barre d’outils.|  
|[CToolBarCtrl::SetAnchorHighlight](#setanchorhighlight)|Définit la mise en surbrillance d’ancrage définition pour une barre d’outils.|  
|[CToolBarCtrl::SetBitmapSize](#setbitmapsize)|Définit la taille des images bitmaps à ajouter à un contrôle de barre d’outils.|  
|[CToolBarCtrl::SetButtonInfo](#setbuttoninfo)|Définit les informations d’un bouton existant dans une barre d’outils.|  
|[CToolBarCtrl::SetButtonSize](#setbuttonsize)|Définit la taille des boutons pour être ajouté à un contrôle de barre d’outils.|  
|[CToolBarCtrl::SetButtonStructSize](#setbuttonstructsize)|Spécifie la taille de la `TBBUTTON` structure.|  
|[CToolBarCtrl::SetButtonWidth](#setbuttonwidth)|Définit les largeurs minimale et maximale de bouton dans le contrôle de barre d’outils.|  
|[CToolBarCtrl::SetCmdID](#setcmdid)|Définit l’identificateur de commande à envoyer dans la fenêtre propriétaire lorsque vous appuyez sur le bouton spécifié.|  
|[CToolBarCtrl::SetColorScheme](#setcolorscheme)|Définit le jeu de couleurs du contrôle barre d’outils en cours.|  
|[CToolBarCtrl::SetDisabledImageList](#setdisabledimagelist)|Définit la liste d’images qui utilise le contrôle de barre d’outils sur les boutons d’affichage désactivé.|  
|[CToolBarCtrl::SetDrawTextFlags](#setdrawtextflags)|Définit les indicateurs de la fonction Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), qui est utilisé pour dessiner le texte dans le rectangle spécifié, mis en forme selon la façon dont les indicateurs sont définis.|  
|[CToolBarCtrl::SetExtendedStyle](#setextendedstyle)|Définit les styles étendus pour un contrôle de barre d’outils.|  
|[CToolBarCtrl::SetHotImageList](#sethotimagelist)|Définit la liste d’images qui utilise le contrôle de barre d’outils pour afficher des boutons « chaud ».|  
|[CToolBarCtrl::SetHotItem](#sethotitem)|Définit l’élément actif dans une barre d’outils.|  
|[CToolBarCtrl::SetImageList](#setimagelist)|Définit la liste d’images qui utilise la barre d’outils pour afficher des boutons qui se trouvent dans leur état par défaut.|  
|[CToolBarCtrl::SetIndent](#setindent)|Définit la mise en retrait pour le premier bouton dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::SetInsertMark](#setinsertmark)|Définit la marque d’insertion en cours de la barre d’outils.|  
|[CToolBarCtrl::SetInsertMarkColor](#setinsertmarkcolor)|Définit la couleur utilisée pour dessiner la marque d’insertion de la barre d’outils.|  
|[CToolBarCtrl::SetMaxTextRows](#setmaxtextrows)|Définit le nombre maximal de lignes de texte affichées sur un bouton de barre d’outils.|  
|[CToolBarCtrl::SetMetrics](#setmetrics)|Définit les mesures d’un contrôle de barre d’outils.|  
|[CToolBarCtrl::SetOwner](#setowner)|Définit la fenêtre de réception des messages de notification à partir du contrôle de barre d’outils.|  
|[CToolBarCtrl::SetPadding](#setpadding)|Définit le remplissage horizontal et vertical du contrôle barre d’outils en cours.|  
|[CToolBarCtrl::SetPressedImageList](#setpressedimagelist)|Définit la liste d’images que le contrôle de barre d’outils actuelle utilise pour représenter les boutons à l’état enfoncé.|  
|[CToolBarCtrl::SetRows](#setrows)|Définit le nombre de lignes de boutons affichés dans la barre d’outils.|  
|[CToolBarCtrl::SetState](#setstate)|Définit l’état du bouton spécifié dans un contrôle de barre d’outils.|  
|[CToolBarCtrl::SetStyle](#setstyle)|Définit les styles d’un contrôle de barre d’outils.|  
|[CToolBarCtrl::SetToolTips](#settooltips)|Associe un contrôle info-bulle au contrôle de barre d’outils.|  
|[CToolBarCtrl::SetWindowTheme](#setwindowtheme)|Définit le style visuel d’un contrôle de barre d’outils.|  
  
## <a name="remarks"></a>Remarques  
 Ce contrôle (et par conséquent la `CToolBarCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT version 3.51 et ultérieures.  
  
 Un contrôle commun de barre d’outils de Windows est une fenêtre enfant rectangulaire qui contient un ou plusieurs boutons. Ces boutons peuvent afficher une image bitmap, une chaîne ou des deux. Lorsque l’utilisateur choisit un bouton, il envoie un message de commande à la fenêtre propriétaire de la barre d’outils. En règle générale, les boutons dans une barre d’outils correspondent aux éléments de menu de l’application ; ils fournissent une manière plus directe de l’utilisateur accéder aux commandes de l’application.  
  
 `CToolBarCtrl`les objets contiennent plusieurs structures de données internes important : une liste d’images bitmap ou une liste d’images, une liste de chaînes d’étiquette de bouton et une liste de `TBBUTTON` structures associer une image ou de chaîne avec la position, le style, l’état et l’ID du bouton de commande. Chacun des éléments de ces structures de données est considéré par un index de base zéro. Avant de pouvoir utiliser un `CToolBarCtrl` de l’objet, vous devez définir ces structures de données. La liste de chaînes utilisable uniquement pour les étiquettes de bouton ; Impossible d’extraire des chaînes à partir de la barre d’outils.  
  
 Pour utiliser un `CToolBarCtrl` de l’objet, en général, suivez ces étapes :  
  
1.  Construire la `CToolBarCtrl` objet.  
  
2.  Appelez [créer](#create) pour créer le contrôle commun de barre d’outils Windows et l’attacher à la `CToolBarCtrl` objet. Indique le style de barre d’outils à l’aide de styles, tels que **TBSTYLE_TRANSPARENT** pour une barre d’outils transparente ou **TBSTYLE_DROPDOWN** pour une barre d’outils qui prend en charge des boutons de liste déroulante Type.  
  
3.  Identifier comment vous souhaitez que les boutons de la barre d’outils affiche :  
  
    -   Pour utiliser des images bitmap pour les boutons, ajoutez les bitmaps des boutons à la barre d’outils en appelant [AddBitmap](#addbitmap).  
  
    -   Pour utiliser des images affichées à partir d’une liste d’images pour les boutons, spécifiez la liste d’images en appelant [SetImageList](#setimagelist), [SetHotImageList](#sethotimagelist), ou [SetDisabledImageList](#setdisabledimagelist).  
  
    -   Pour utiliser des étiquettes de chaînes pour les boutons, ajoutez les chaînes à la barre d’outils en appelant [AddString](#addstring) et/ou [AddStrings](#addstrings).  
  
4.  Ajouter des structures de boutons à la barre d’outils en appelant [AddButtons](#addbuttons).  
  
5.  Si vous souhaitez que des info-bulles pour un bouton de barre d’outils dans une fenêtre de propriétaire n’est pas un `CFrameWnd`, vous devez gérer le **TTN_NEEDTEXT** des messages dans la fenêtre propriétaire de la barre d’outils comme décrit dans [la gestion des Notifications des info](../../mfc/handling-tool-tip-notifications.md). Si la fenêtre parente de la barre d’outils est dérivée de `CFrameWnd`, info-bulles sont affichent sans effort supplémentaire de votre part, car `CFrameWnd` fournit un gestionnaire par défaut.  
  
6.  Si vous souhaitez que votre utilisateur puisse personnaliser la barre d’outils, gérer les messages de notification de personnalisation dans la fenêtre propriétaire comme décrit dans [gestion des Notifications de personnalisation](../../mfc/handling-customization-notifications.md).  
  
 Vous pouvez utiliser [SaveState](#savestate) pour enregistrer l’état actuel d’un contrôle de barre d’outils dans le Registre et [RestoreState](#restorestate) pour restaurer l’état en fonction des informations précédemment stockées dans le Registre. En plus de l’enregistrement de l’état de la barre d’outils entre des utilisations de l’application, applications stockent généralement l’état avant que l’utilisateur commence à personnaliser la barre d’outils dans le cas où l’utilisateur veut ultérieurement restaurer la barre d’outils à son état d’origine.  
  
## <a name="support-for-internet-explorer-version-40-and-later"></a>Prise en charge de la Version d’Internet Explorer 4.0 et versions ultérieures  
 Pour prendre en charge les fonctionnalités introduites dans Internet Explorer version 4.0 et versions ultérieure, MFC fournit les styles transparents et plats et prise en charge de la liste des images pour les contrôles de barre d’outils.  
  
 Une barre d’outils transparente permet au client sous la barre d’outils soit visible. Pour créer une barre d’outils transparente, utilisez à la fois **TBSTYLE_FLAT** et **TBSTYLE_TRANSPARENT** styles. Barres d’outils transparentes fonctionnalité réactive ; Autrement dit, lorsque le pointeur de la souris se déplace sur un bouton actif dans la barre d’outils, l’apparence du bouton change. Barres d’outils créées avec uniquement le **TBSTYLE_FLAT** style contient des boutons qui ne sont pas transparent.  
  
 Prise en charge de la liste image un contrôle une plus grande souplesse pour le comportement par défaut, les images interactives et les images désactivés. Utilisez [GetImageList](#getimagelist), [GetHotImageList](#gethotimagelist), et [GetDisabledImageList](#getdisabledimagelist) avec la barre d’outils transparente pour manipuler une image en fonction de son état :  
  
 Pour plus d’informations sur l’utilisation de `CToolBarCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et [à l’aide de CToolBarCtrl](../../mfc/using-ctoolbarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolBarCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="a-nameaddbitmapa--ctoolbarctrladdbitmap"></a><a name="addbitmap"></a>CToolBarCtrl::AddBitmap  
 Ajoute une ou plusieurs images de bouton à la liste des images de bouton stockées dans le contrôle de barre d’outils.  
  
```  
int AddBitmap(
    int nNumButtons,  
    UINT nBitmapID);

 
int AddBitmap(
    int nNumButtons,  
    CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Paramètres  
 `nNumButtons`  
 Nombre d’images de boutons dans la bitmap.  
  
 `nBitmapID`  
 Identificateur de ressource de la bitmap qui contient l’image du bouton ou des images à ajouter.  
  
 `pBitmap`  
 Pointeur vers le `CBitmap` objet qui contient l’image du bouton ou des images à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de la nouvelle image en cas de réussite ; Sinon,-1.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez utiliser l’API Windows [CreateMappedBitmap](http://msdn.microsoft.com/library/windows/desktop/bb787467) pour mapper les couleurs avant d’ajouter l’image bitmap à la barre d’outils. Si vous passez un pointeur vers un **CBitMap** de l’objet, vous devez vous assurer que l’image bitmap n’est pas détruit tant qu’après la destruction de la barre d’outils.  
  
##  <a name="a-nameaddbuttonsa--ctoolbarctrladdbuttons"></a><a name="addbuttons"></a>CToolBarCtrl::AddButtons  
 Ajoute un ou plusieurs boutons à un contrôle de barre d’outils.  
  
```  
BOOL AddButtons(
    int nNumButtons,  
    LPTBBUTTON lpButtons);
```  
  
### <a name="parameters"></a>Paramètres  
 `nNumButtons`  
 Nombre de boutons à ajouter.  
  
 `lpButtons`  
 Adresse d’un tableau de `TBBUTTON` des structures qui contient des informations sur les boutons à ajouter. Il doit y avoir le même nombre d’éléments dans le tableau sous forme de boutons spécifiés par `nNumButtons`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Le `lpButtons` pointeur pointe vers un tableau de `TBBUTTON` des structures. Chaque `TBBUTTON` structure associe le bouton ajouté avec le style du bouton, l’état d’image et/ou une chaîne, l’ID de commande et défini par l’utilisateur :  
  
 `typedef struct _TBBUTTON {`  
  
 `int iBitmap;// zero-based index of button image`  
  
 `int idCommand;  // command to be sent when button pressed`  
  
 `BYTE fsState;   // button state--see below`  
  
 `BYTE fsStyle;   // button style--see below`  
  
 `DWORD dwData;   // application-defined value`  
  
 `int iString;// zero-based index of button label string`  
  
 `} TBBUTTON;`  
  
 Les membres sont les suivants :  
  
 **iBitmap**  
 Index de base zéro de l’image du bouton, -1 si aucune image de ce bouton.  
  
 **idCommand**  
 Identificateur de commande associé au bouton. Cet identificateur est envoyé un **WM_COMMAND** message lorsque le bouton est sélectionné. Si le **fsStyle** membre a le `TBSTYLE_SEP` valeur, ce membre doit être égal à zéro.  
  
 **fsState**  
 Indicateurs d’état du bouton. Il peut être une combinaison des valeurs répertoriées ci-dessous :  
  
- `TBSTATE_CHECKED`Le bouton a la **TBSTYLE_CHECKED** du style et est enfoncé.  
  
- `TBSTATE_ENABLED`Le bouton accepte l’entrée d’utilisateur. Un bouton qui n’a pas cet état n’accepte pas d’entrée d’utilisateur et est grisé.  
  
- `TBSTATE_HIDDEN`Le bouton n’est pas visible et ne peut pas l’entrée d’utilisateur.  
  
- `TBSTATE_INDETERMINATE`Le bouton est grisé.  
  
- `TBSTATE_PRESSED`Le bouton est enfoncé.  
  
- `TBSTATE_WRAP`Un saut de ligne suit le bouton. Le bouton doit également avoir la `TBSTATE_ENABLED` état.  
  
 **fsStyle**  
 Style de bouton. Il peut être une combinaison des valeurs répertoriées ci-dessous :  
  
- `TBSTYLE_BUTTON`Crée un bouton de commande standard.  
  
- `TBSTYLE_CHECK`Crée un bouton bascule entre les États enfoncés ou non enfoncés chaque fois que l’utilisateur clique dessus. Le bouton a une couleur d’arrière-plan lorsqu’il est dans l’état enfoncé.  
  
- `TBSTYLE_CHECKGROUP`Crée un bouton de vérification qui reste enfoncé jusqu'à ce qu’un autre bouton dans le groupe.  
  
- `TBSTYLE_GROUP`Crée un bouton qui reste enfoncé jusqu'à ce qu’un autre bouton dans le groupe.  
  
- `TBSTYLE_SEP`Crée un séparateur, en fournissant un petit intervalle entre groupes. Un bouton qui a ce style ne reçoit pas d’entrée d’utilisateur.  
  
 `dwData`  
 Données définies par l’utilisateur.  
  
 **iString**  
 Index de base zéro de la chaîne à utiliser comme bouton de l’étiquette, -1 si aucune chaîne de ce bouton.  
  
 L’image et/ou une chaîne dont vous fournissez l’index doit avoir déjà été ajoutée au contrôle de barre d’outils liste à l’aide de [AddBitmap](#addbitmap), [AddString](#addstring), et/ou [AddStrings](#addstrings).  
  
##  <a name="a-nameaddstringa--ctoolbarctrladdstring"></a><a name="addstring"></a>CToolBarCtrl::AddString  
 Ajoute une nouvelle chaîne, passée comme un ID de ressource à la liste interne de la barre d’outils de chaînes.  
  
```  
int AddString(UINT nStringID);
```  
  
### <a name="parameters"></a>Paramètres  
 *nStringID*  
 Identificateur de ressource de la ressource de chaîne à ajouter à la liste de chaîne du contrôle barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de la première chaîne de nouveau ajoutée en cas de réussite ; Sinon,-1.  
  
##  <a name="a-nameaddstringsa--ctoolbarctrladdstrings"></a><a name="addstrings"></a>CToolBarCtrl::AddStrings  
 Ajoute une nouvelle chaîne ou des chaînes à la liste des chaînes disponibles pour un contrôle de barre d’outils.  
  
```  
int AddStrings(LPCTSTR lpszStrings);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszStrings*  
 Adresse d’une mémoire tampon qui contient une ou plusieurs chaînes se terminant par null à ajouter à la liste de chaînes de la barre d’outils. La dernière chaîne doit se terminer par deux caractères null.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de la première chaîne de nouveau ajoutée en cas de réussite ; Sinon,-1.  
  
### <a name="remarks"></a>Remarques  
 Dans la mémoire tampon, les chaînes doivent être séparés par un caractère null. Vous devez vous assurer que la dernière chaîne deux indicateurs de fin null. Pour mettre correctement en forme une chaîne constante, vous pouvez écrire en tant que :  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#72;](../../mfc/codesnippet/cpp/ctoolbarctrl-class_1.cpp)]  
  
 ou :  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#73;](../../mfc/codesnippet/cpp/ctoolbarctrl-class_2.cpp)]  
  
 Vous ne devez pas passer un `CString` objet à cette fonction dans la mesure où il n’est pas possible d’avoir plus d’un caractère null dans un `CString`.  
  
##  <a name="a-nameautosizea--ctoolbarctrlautosize"></a><a name="autosize"></a>CToolBarCtrl::AutoSize  
 Redimensionne le contrôle de barre d’outils entière.  
  
```  
void AutoSize();
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler cette fonction lorsque la taille de la fenêtre parente change ou lorsque la taille de la barre d’outils change (par exemple, lorsque vous définissez la taille du bouton ou bitmap, ou ajoutez des chaînes).  
  
##  <a name="a-namechangebitmapa--ctoolbarctrlchangebitmap"></a><a name="changebitmap"></a>CToolBarCtrl::ChangeBitmap  
 Modifie la bitmap pour un bouton dans le contrôle de barre d’outils en cours.  
  
```  
BOOL ChangeBitmap(
    int idButton,   
    int iBitmap);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `idButton`|Identificateur de commande du bouton qui doit recevoir une nouvelle image bitmap.|  
|[in] `iBitmap`|Index de base zéro d’une image dans la liste d’images du contrôle de barre d’outils en cours.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Notes  
 Si cette méthode réussit, le système affiche l’image spécifiée dans le bouton spécifié.  
  
 Cette méthode envoie le [TB_CHANGEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787301) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant modifie la bitmap de la **enregistrer** bouton à l’image bitmap de la **sur** bouton.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1 n °&1;](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_3.cpp)]  
  
##  <a name="a-namecheckbuttona--ctoolbarctrlcheckbutton"></a><a name="checkbutton"></a>CToolBarCtrl::CheckButton  
 Active ou désactive un bouton donné dans un contrôle de barre d’outils.  
  
```  
BOOL CheckButton(
    int nID,  
    BOOL bCheck = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton pour activer ou désactiver.  
  
 *bvérifier*  
 **TRUE** pour vérifier le bouton, **FALSE** pour l’annuler.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Lorsqu’un bouton a été activé, il apparaît à l’utilisateur a appuyé. Si vous souhaitez modifier plusieurs États de bouton, il vaut mieux appeler [SetState](#setstate) à la place.  
  
##  <a name="a-namecommandtoindexa--ctoolbarctrlcommandtoindex"></a><a name="commandtoindex"></a>CToolBarCtrl::CommandToIndex  
 Récupère l’index de base zéro pour le bouton associé à l’identificateur de commande spécifié.  
  
```  
UINT CommandToIndex(UINT nID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 ID de commande dont bouton index que vous souhaitez rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro pour le bouton associé à l’ID de commande.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecreatea--ctoolbarctrlcreate"></a><a name="create"></a>CToolBarCtrl::Create  
 Crée un contrôle de barre d’outils et l’attache à une `CToolBarCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie le style du contrôle barre d’outils. Barres d’outils doivent toujours avoir le **WS_CHILD** style. En outre, vous pouvez spécifier n’importe quelle combinaison de styles de barre d’outils et les styles de fenêtre comme décrit sous **notes**.  
  
 `rect`  
 Spécifie éventuellement la taille et la position du contrôle barre d’outils. Il peut être soit un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure.  
  
 `pParentWnd`  
 Spécifie la fenêtre parente du contrôle de barre d’outils. Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID. du contrôle de barre d’outils  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Vous construisez un `CToolBarCtrl` en deux étapes. Tout d’abord, appelez le constructeur, puis appelez **créer**, ce qui crée le contrôle de barre d’outils et l’attache à le `CToolBarCtrl` objet. Appliquer les styles de fenêtre suivants à un contrôle de barre d’outils.  
  
- **WS_CHILD** toujours  
  
- **WS_VISIBLE** généralement  
  
- **WS_DISABLED** rarement  
  
 Consultez la page [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour obtenir une description des styles de fenêtre.  
  
 Vous pouvez également appliquer une combinaison de [des styles de contrôle commun](http://msdn.microsoft.com/library/windows/desktop/bb775498), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Appliquer une combinaison de styles de barre d’outils de contrôle ou les boutons. Les styles sont décrites dans la rubrique [contrôle de barre d’outils et les Styles de bouton](http://msdn.microsoft.com/library/windows/desktop/bb760439) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour utiliser les styles de barre d’outils étendues, appelez [SetExtendedStyle](#setextendedstyle) après avoir appelé **créer**. Pour créer une barre d’outils avec des styles de fenêtre étendus, appelez [CToolBarCtrl::CreateEx](#createex) au lieu de **créer**.  
  
 Le contrôle de barre d’outils définit automatiquement la taille et la position de la fenêtre de la barre d’outils. La hauteur est basée sur la hauteur des boutons de la barre d’outils. La largeur est identique à la largeur de la zone cliente de la fenêtre parente. Le `CCS_TOP` et `CCS_BOTTOM` déterminent si la barre d’outils se trouve en haut ou en bas de la zone cliente. Par défaut, une barre d’outils a la `CCS_TOP` style.  
  
##  <a name="a-namecreateexa--ctoolbarctrlcreateex"></a><a name="createex"></a>CToolBarCtrl::CreateEx  
 Crée un contrôle (une fenêtre enfant) et l’associe à la `CToolBarCtrl` objet.  
  
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
 Spécifie le style du contrôle barre d’outils. Barres d’outils doivent toujours avoir le **WS_CHILD** style. En outre, vous pouvez spécifier n’importe quelle combinaison de styles de barre d’outils et les styles de fenêtre comme décrit dans la **remarques** section de [créer](#create).  
  
 `rect`  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure décrivant la taille et la position de la fenêtre doit être créée, dans les coordonnées clientes de `pParentWnd`.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parent du contrôle.  
  
 `nID`  
 ID de fenêtre enfant. du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Utilisez `CreateEx` au lieu de [créer](#create) pour appliquer des styles étendus Windows, spécifiés par la préface de style étendu Windows **WS_EX_**. **CreateEx** crée le contrôle avec les styles étendus de Windows spécifiés par `dwExStyle`. Ensemble spécifique d’un contrôle à l’aide de styles étendus [SetExtendedStyle](#setextendedstyle). Par exemple, utilisez `CreateEx` pour définir ces styles en tant que **WS_EX_CONTEXTHELP**, mais utiliser `SetExtendedStyle` pour définir ces styles en tant que **TBSTYLE_EX_DRAWDDARROWS**. Pour plus d’informations, consultez les styles décrits dans [Styles étendus de barre d’outils](http://msdn.microsoft.com/library/windows/desktop/bb760430) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namectoolbarctrla--ctoolbarctrlctoolbarctrl"></a><a name="ctoolbarctrl"></a>CToolBarCtrl::CToolBarCtrl  
 Construit un objet `CToolBarCtrl`.  
  
```  
CToolBarCtrl();
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler [créer](#create) pour rendre la barre d’outils utilisable.  
  
##  <a name="a-namecustomizea--ctoolbarctrlcustomize"></a><a name="customize"></a>CToolBarCtrl::Customize  
 Affiche la boîte de dialogue Personnaliser la barre d’outils.  
  
```  
void Customize();
```  
  
### <a name="remarks"></a>Notes  
 Cette boîte de dialogue permet à l’utilisateur de personnaliser la barre d’outils en ajoutant et supprimant des boutons. Pour prendre en charge la personnalisation, votre fenêtre parente doit gérer les messages de notification de personnalisation, comme décrit dans [gestion des Notifications de personnalisation](../../mfc/handling-customization-notifications.md). La barre d’outils doit également créée avec les `CCS_ADJUSTABLE` de style, comme décrit dans [CToolBarCtrl::Create](#create).  
  
 Pour plus d’informations, consultez l’article de la Base de connaissances Q241850 : PRB : l’appel à CToolBarCtrl::Customize ne conserve pas les Visible de boîte de dialogue Personnaliser.  
  
##  <a name="a-namedeletebuttona--ctoolbarctrldeletebutton"></a><a name="deletebutton"></a>CToolBarCtrl::DeleteButton  
 Supprime un bouton à partir du contrôle de barre d’outils.  
  
```  
BOOL DeleteButton(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro du bouton Supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameenablebuttona--ctoolbarctrlenablebutton"></a><a name="enablebutton"></a>CToolBarCtrl::EnableButton  
 Active ou désactive le bouton spécifié dans un contrôle de barre d’outils.  
  
```  
BOOL EnableButton(
    int nID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton pour activer ou désactiver.  
  
 `bEnable`  
 **TRUE** pour activer le bouton ; **FALSE** pour désactiver le bouton.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Lorsqu’un bouton a été activé, il peut être enfoncée et vérifié. Si vous souhaitez modifier plusieurs États de bouton, il vaut mieux appeler [SetState](#setstate) à la place.  
  
##  <a name="a-namegetanchorhighlighta--ctoolbarctrlgetanchorhighlight"></a><a name="getanchorhighlight"></a>CToolBarCtrl::GetAnchorHighlight  
 Récupère la mise en surbrillance d’ancrage définition pour une barre d’outils.  
  
```  
BOOL GetAnchorHighlight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si elle est différente de zéro, d’ancrage est activée. Si zéro, la mise en surbrillance d’ancrage est désactivée.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787313), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbitmapa--ctoolbarctrlgetbitmap"></a><a name="getbitmap"></a>CToolBarCtrl::GetBitmap  
 Récupère l’index de l’image bitmap associée à un bouton dans une barre d’outils.  
  
```  
int GetBitmap(int nID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton dont l’index de bitmap doit être récupéré.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’index de l’image bitmap en cas de réussite, ou zéro dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Implémente les fonctionnalités de [TB_GETBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787315) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbitmapflagsa--ctoolbarctrlgetbitmapflags"></a><a name="getbitmapflags"></a>CToolBarCtrl::GetBitmapFlags  
 Récupère les indicateurs de bitmap à partir de la barre d’outils.  
  
```  
UINT GetBitmapFlags() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **UINT** dont le **TBBF_LARGE** indicateur défini si l’affichage peut prendre en charge les bitmaps de grande barre d’outils, désactivez dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Vous devez l’appeler après la création de la barre d’outils, mais avant d’ajouter des bitmaps à la barre d’outils. La valeur de retour indique si l’affichage prend en charge les images bitmaps volumineuses ou non. Si l’affichage prend en charge les images bitmaps volumineuses et si vous choisissez de les utiliser, appelez [SetBitmapSize](#setbitmapsize) et [SetButtonSize](#setbuttonsize) avant d’ajouter votre à l’aide de la grande image [AddBitmap](#addbitmap).  
  
##  <a name="a-namegetbuttona--ctoolbarctrlgetbutton"></a><a name="getbutton"></a>CToolBarCtrl::GetButton  
 Récupère des informations sur le bouton spécifié dans un contrôle de barre d’outils.  
  
```  
BOOL GetButton(
    int nIndex,  
    LPTBBUTTON lpButton) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro du bouton pour lequel récupérer les informations.  
  
 `lpButton`  
 Adresse de le `TBBUTTON` structure qui doit recevoir une copie des informations de bouton. Consultez la page [CToolBarCtrl::AddButtons](#addbuttons) pour plus d’informations sur la `TBBUTTON` structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="a-namegetbuttoncounta--ctoolbarctrlgetbuttoncount"></a><a name="getbuttoncount"></a>CToolBarCtrl::GetButtonCount  
 Récupère un nombre de boutons actuellement dans le contrôle de barre d’outils.  
  
```  
int GetButtonCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de boutons.  
  
##  <a name="a-namegetbuttoninfoa--ctoolbarctrlgetbuttoninfo"></a><a name="getbuttoninfo"></a>CToolBarCtrl::GetButtonInfo  
 Récupère les informations d’un bouton dans une barre d’outils.  
  
```  
int GetButtonInfo(
    int nID,  
    TBBUTTONINFO* ptbbi) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 L’identificateur du bouton.  
  
 `ptbbi`  
 Un pointeur vers un [TBBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb760478) structure qui reçoit les informations de bouton.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro du bouton, en cas de réussite ; sinon -1.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787321), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbuttonsizea--ctoolbarctrlgetbuttonsize"></a><a name="getbuttonsize"></a>CToolBarCtrl::GetButtonSize  
 Obtient la taille d’un bouton de barre d’outils.  
  
```  
DWORD GetButtonSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `DWORD` valeur qui contient les valeurs de largeur et la hauteur des HIWORD, LOWORD respectivement.  
  
##  <a name="a-namegetbuttontexta--ctoolbarctrlgetbuttontext"></a><a name="getbuttontext"></a>CToolBarCtrl::GetButtonText  
 Récupère le texte d’affichage d’un bouton sur le contrôle actuel de la barre d’outils spécifié.  
  
```  
CString GetButtonText(int idButton) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `idButton`|L’identificateur pour le bouton d’affichage dont le texte est récupéré.|  
  
### <a name="return-value"></a>Valeur de retour  
 A [CString](../../atl-mfc-shared/using-cstring.md) qui contient le texte d’affichage du bouton spécifié.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [TB_GETBUTTONTEXT](http://msdn.microsoft.com/library/windows/desktop/bb787325) message, qui est décrit dans le SDK Windows.  
  
##  <a name="a-namegetcolorschemea--ctoolbarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>CToolBarCtrl::GetColorScheme  
 Récupère le jeu de couleurs du contrôle barre d’outils en cours.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpColorScheme) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[out] `lpColorScheme`|Pointeur vers un [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) structure qui reçoit les informations de schéma de couleur. Lorsque cette méthode est retournée, la structure décrit la couleur de surbrillance et la couleur de l’ombre du contrôle barre d’outils.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [TB_GETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787327) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdisabledimagelista--ctoolbarctrlgetdisabledimagelist"></a><a name="getdisabledimagelist"></a>CToolBarCtrl::GetDisabledImageList  
 Récupère la liste d’images par un contrôle de barre d’outils pour les boutons d’affichage désactivé.  
  
```  
CImageList* GetDisabledImageList() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet, ou **NULL** si aucune liste d’images désactivée n’est définie.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787329), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. L’implémentation MFC de `GetDisabledImageList` utilise un `CImageList` objet contenant le bouton du contrôle de barre d’outils de l’image, au lieu d’un handle vers une liste d’images.  
  
##  <a name="a-namegetdroptargeta--ctoolbarctrlgetdroptarget"></a><a name="getdroptarget"></a>CToolBarCtrl::GetDropTarget  
 Récupère le [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) interface pour un contrôle de barre d’outils.  
  
```  
HRESULT GetDropTarget(IDropTarget** ppDropTarget) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `ppDropTarget`  
 Un pointeur vers un [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) pointeur d’interface. Si une erreur se produit, un **NULL** pointeur est placé dans cette adresse.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un `HRESULT` valeur indiquant la réussite ou l’échec de l’opération.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787343), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetextendedstylea--ctoolbarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CToolBarCtrl::GetExtendedStyle  
 Récupère les styles étendus pour un contrôle de barre d’outils.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `DWORD` qui représente les styles étendus en cours d’utilisation pour le contrôle de barre d’outils. Pour obtenir la liste des styles, consultez [Styles étendus de barre d’outils](http://msdn.microsoft.com/library/windows/desktop/bb760430), dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787331), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegethotimagelista--ctoolbarctrlgethotimagelist"></a><a name="gethotimagelist"></a>CToolBarCtrl::GetHotImageList  
 Récupère la liste d’images par un contrôle de barre d’outils pour afficher des boutons « chaud ». Un bouton actif apparaît en surbrillance lorsque le pointeur de la souris est au-dessus de lui.  
  
```  
CImageList* GetHotImageList() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet, ou **NULL** si aucune liste d’images désactivée n’est définie.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787334), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Un bouton actif apparaît en surbrillance lorsque le pointeur de la souris est au-dessus de lui.  
  
##  <a name="a-namegethotitema--ctoolbarctrlgethotitem"></a><a name="gethotitem"></a>CToolBarCtrl::GetHotItem  
 Récupère l’index de l’élément dans une barre d’outils Accès rapide.  
  
```  
int GetHotItem() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément dans une barre d’outils Accès rapide.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787336), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetimagelista--ctoolbarctrlgetimagelist"></a><a name="getimagelist"></a>CToolBarCtrl::GetImageList  
 Récupère la liste d’images par un contrôle de barre d’outils pour afficher les boutons dans leur état par défaut.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet, ou **NULL** si aucune liste d’images n’est défini.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787337), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetinsertmarka--ctoolbarctrlgetinsertmark"></a><a name="getinsertmark"></a>CToolBarCtrl::GetInsertMark  
 Récupère la marque d’insertion en cours de la barre d’outils.  
  
```  
void GetInsertMark(TBINSERTMARK* ptbim) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `ptbim`  
 Un pointeur vers un [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) structure qui reçoit la marque d’insertion.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787338), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetinsertmarkcolora--ctoolbarctrlgetinsertmarkcolor"></a><a name="getinsertmarkcolor"></a>CToolBarCtrl::GetInsertMarkColor  
 Récupère la couleur utilisée pour dessiner la marque d’insertion de la barre d’outils.  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **COLORREF** valeur qui contient la couleur de la marque d’insertion actuel.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787339), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetitemrecta--ctoolbarctrlgetitemrect"></a><a name="getitemrect"></a>CToolBarCtrl::GetItemRect  
 Récupère le rectangle englobant d’un bouton dans un contrôle de barre d’outils.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro du bouton pour lequel récupérer les informations.  
  
 `lpRect`  
 Adresse d’un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure ou un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui reçoit les coordonnées du rectangle englobant.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Cette fonction ne récupère pas le rectangle englobant pour les boutons dont l’état a la valeur `TBSTATE_HIDDEN`.  
  
##  <a name="a-namegetmaxsizea--ctoolbarctrlgetmaxsize"></a><a name="getmaxsize"></a>CToolBarCtrl::GetMaxSize  
 Récupère la taille totale de tous les boutons visibles et les séparateurs dans la barre d’outils.  
  
```  
BOOL GetMaxSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pSize`  
 Un pointeur vers un [taille](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure qui reçoit la taille des éléments.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETMAXSIZE](http://msdn.microsoft.com/library/windows/desktop/bb787341), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetmaxtextrowsa--ctoolbarctrlgetmaxtextrows"></a><a name="getmaxtextrows"></a>CToolBarCtrl::GetMaxTextRows  
 Récupère le nombre maximal de lignes de texte affichées sur un bouton de barre d’outils.  
  
```  
int GetMaxTextRows() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre maximal de lignes de texte affichées sur un bouton de barre d’outils.  
  
##  <a name="a-namegetmetricsa--ctoolbarctrlgetmetrics"></a><a name="getmetrics"></a>CToolBarCtrl::GetMetrics  
 Récupère les mesures de la `CToolBarCtrl` objet.  
  
```  
void GetMetrics(LPTBMETRICS ptbm) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `ptbm`  
 Un pointeur vers le [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482) structure de le `CToolBarCtrl` objet.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre émule les fonctionnalités de la [TB_GETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787342) d’un message, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpaddinga--ctoolbarctrlgetpadding"></a><a name="getpadding"></a>CToolBarCtrl::GetPadding  
 Récupère la marge horizontale et verticale du contrôle barre d’outils en cours.  
  
```  
BOOL GetPadding(
    int* pnHorzPadding,   
    int* pnVertPadding) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[out] `pnHorzPadding`|Entier qui reçoit la marge horizontale du contrôle de barre d’outils, en pixels.|  
|[out] `pnVertPadding`|Entier qui reçoit la marge intérieure verticale du contrôle barre d’outils, en pixels.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [TB_GETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787344) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpressedimagelista--ctoolbarctrlgetpressedimagelist"></a><a name="getpressedimagelist"></a>CToolBarCtrl::GetPressedImageList  
 Récupère la liste d’images que le contrôle de barre d’outils actuelle utilise pour représenter les boutons à l’état enfoncé.  
  
```  
CImageList* GetPressedImageList();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) qui contient la liste d’images pour le contrôle actuel, ou `NULL` si aucune liste d’images de ce type n’est défini.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [TB_GETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787345) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetrecta--ctoolbarctrlgetrect"></a><a name="getrect"></a>CToolBarCtrl::GetRect  
 Récupère le rectangle englobant d’un bouton de barre d’outils spécifiée.  
  
```  
BOOL GetRect(
    int nID,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 L’identificateur du bouton.  
  
 `lpRect`  
 Un pointeur vers un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure pour recevoir les informations de rectangle englobant.  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** cas de réussite ; sinon **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb787346), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetrowsa--ctoolbarctrlgetrows"></a><a name="getrows"></a>CToolBarCtrl::GetRows  
 Récupère le nombre de lignes de boutons actuellement affichés par le contrôle de barre d’outils.  
  
```  
int GetRows() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre de lignes de boutons actuellement affichés sur la barre d’outils.  
  
### <a name="remarks"></a>Remarques  
 Notez que le nombre de lignes sera toujours une sauf si la barre d’outils a été créé avec le `TBSTYLE_WRAPABLE` style.  
  
##  <a name="a-namegetstatea--ctoolbarctrlgetstate"></a><a name="getstate"></a>CToolBarCtrl::GetState  
 Récupère des informations sur l’état du bouton spécifié dans un contrôle de barre d’outils, tels que s’il est activé, activé ou activé.  
  
```  
int GetState(int nID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton pour lequel récupérer les informations.  
  
### <a name="return-value"></a>Valeur de retour  
 Les informations d’état du bouton en cas de réussite ou – 1 sinon. Les informations d’état de bouton peuvent être une combinaison des valeurs répertoriées dans [CToolBarCtrl::AddButtons](#addbuttons).  
  
### <a name="remarks"></a>Remarques  
 Cette fonction peut s’avérer utile si vous souhaitez récupérer plus d’un des États de bouton. Pour récupérer uniquement un état, utilisez une des fonctions membres suivantes : [IsButtonEnabled telle](#isbuttonenabled), [IsButtonChecked](#isbuttonchecked), [IsButtonPressed](#isbuttonpressed), [IsButtonHidden](#isbuttonhidden), ou [IsButtonIndeterminate](#isbuttonindeterminate). Toutefois, le `GetState` la fonction membre est le seul moyen de détecter les `TBSTATE_WRAP` bouton État.  
  
##  <a name="a-namegetstringa--ctoolbarctrlgetstring"></a><a name="getstring"></a>CToolBarCtrl::GetString  
 Récupère une chaîne de la barre d’outils.  
  
```  
int GetString(
    int nString,  
    LPTSTR lpstrString,  
    int cchMaxLen) const;  
  
int GetString(
    int nString,  
    CString& str) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *nString*  
 Index de la chaîne.  
  
 *lpstrString*  
 Pointeur vers une mémoire tampon utilisée pour retourner la chaîne.  
  
 *cchMaxLen*  
 Longueur de la mémoire tampon en octets.  
  
 `str`  
 La chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur de la chaîne en cas de réussite, -1 dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_GETSTRING](http://msdn.microsoft.com/library/windows/desktop/bb787349), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetstylea--ctoolbarctrlgetstyle"></a><a name="getstyle"></a>CToolBarCtrl::GetStyle  
 Obtient les styles actuellement appliqués à un contrôle de barre d’outils.  
  
```  
DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A `DWORD` contenant une combinaison de [les styles de contrôle de barre d’outils](http://msdn.microsoft.com/library/windows/desktop/bb760439), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettooltipsa--ctoolbarctrlgettooltips"></a><a name="gettooltips"></a>CToolBarCtrl::GetToolTips  
 Récupère le handle du contrôle ToolTip, si un, associé au contrôle de barre d’outils.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) objet associé à cette barre d’outils ou **NULL** si la barre d’outils ne possède aucun contrôle d’info-bulle associé à l’outil.  
  
### <a name="remarks"></a>Notes  
 Étant donné que le contrôle de barre d’outils normalement crée et gère son propre contrôle info-bulle, la plupart des programmes n’avez pas besoin d’appeler cette fonction.  
  
##  <a name="a-namehittesta--ctoolbarctrlhittest"></a><a name="hittest"></a>CToolBarCtrl::HitTest  
 Détermine où se trouve un point dans un contrôle de barre d’outils.  
  
```  
int HitTest(LPPOINT ppt) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `ppt`  
 Un pointeur vers un [POINT](http://msdn.microsoft.com/library/windows/desktop/dd162805) structure qui contient la coordonnée x du test d’atteinte dans le **x** membre et la coordonnée y de l’impact de test dans le **y** membre. Les coordonnées sont exprimées par rapport à la zone cliente de la barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur entière indiquant l’emplacement d’un point sur une barre d’outils. Si la valeur est zéro ou une valeur positive, cette valeur de retour est l’index de base zéro de l’élément nonseparator dans lequel se trouve le point.  
  
 Si la valeur de retour est négative, le point ne se situe pas dans un bouton. La valeur absolue de la valeur de retour est l’index d’un élément de séparateur ou l’élément nonseparator le plus proche.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787360), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehidebuttona--ctoolbarctrlhidebutton"></a><a name="hidebutton"></a>CToolBarCtrl::HideButton  
 Masque ou affiche le bouton spécifié dans un contrôle de barre d’outils.  
  
```  
BOOL HideButton(
    int nID,  
    BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton Afficher ou masquer.  
  
 `bHide`  
 **TRUE** pour masquer le bouton, **FALSE** pour l’afficher.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez modifier plusieurs États de bouton, il vaut mieux appeler [SetState](#setstate) à la place.  
  
##  <a name="a-nameindeterminatea--ctoolbarctrlindeterminate"></a><a name="indeterminate"></a>CToolBarCtrl::Indeterminate  
 Active ou désactive l’état indéterminé du bouton spécifié dans un contrôle de barre d’outils.  
  
```  
BOOL Indeterminate(
    int nID,  
    BOOL bIndeterminate = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton dont l’état indéterminé doit être configurée ou désactivée.  
  
 *bIndeterminate*  
 **TRUE** pour définir l’état indéterminé du bouton spécifié, **FALSE** pour l’annuler.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Boutons indéterminés sont affichent en grisé, telles que la méthode sur la barre d’outils, le bouton gras d’un traitement de texte apparaîtra une fois le texte sélectionné contient des caractères gras et régulières. Si vous souhaitez modifier plusieurs États de bouton, il vaut mieux appeler [SetState](#setstate) à la place.  
  
##  <a name="a-nameinsertbuttona--ctoolbarctrlinsertbutton"></a><a name="insertbutton"></a>CToolBarCtrl::InsertButton  
 Insère un bouton dans un contrôle de barre d’outils.  
  
```  
BOOL InsertButton(
    int nIndex,  
    LPTBBUTTON lpButton);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro d’un bouton. Cette fonction insère le nouveau bouton à gauche de ce bouton.  
  
 `lpButton`  
 Adresse d’un `TBBUTTON` structure contenant des informations sur le bouton à insérer. Consultez la page [CToolBarCtrl::AddButtons](#addbuttons) pour obtenir une description de le `TBBUTTON` structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 L’image et/ou une chaîne dont vous fournissez l’index doit avoir déjà été ajoutée au contrôle de barre d’outils liste à l’aide de [AddBitmap](#addbitmap), [AddString](#addstring), et/ou [AddStrings](#addstrings).  
  
##  <a name="a-nameinsertmarkhittesta--ctoolbarctrlinsertmarkhittest"></a><a name="insertmarkhittest"></a>CToolBarCtrl::InsertMarkHitTest  
 Récupère les informations de marque d’insertion d’un point dans une barre d’outils.  
  
```  
BOOL InsertMarkHitTest(
    LPPOINT ppt,  
    LPTBINSERTMARK ptbim) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `ppt`  
 Un pointeur vers un [POINT](http://msdn.microsoft.com/library/windows/desktop/dd162805) coordonnées de structure qui contient le test de positionnement, par rapport à la zone cliente de la barre d’outils.  
  
 `ptbim`  
 Un pointeur vers un [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) structure qui reçoit les informations de marque d’insertion.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_INSERTMARKHITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787367), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisbuttoncheckeda--ctoolbarctrlisbuttonchecked"></a><a name="isbuttonchecked"></a>CToolBarCtrl::IsButtonChecked  
 Détermine si le bouton spécifié dans un contrôle de barre d’outils est activé.  
  
```  
BOOL IsButtonChecked(int nID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton dans la barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le bouton est activé ; Sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Il vaut mieux appeler [GetState](#getstate) si vous souhaitez récupérer plusieurs États de bouton.  
  
##  <a name="a-nameisbuttonenableda--ctoolbarctrlisbuttonenabled"></a><a name="isbuttonenabled"></a>CToolBarCtrl::IsButtonEnabled  
 Détermine si le bouton spécifié dans un contrôle de barre d’outils est activé.  
  
```  
BOOL IsButtonEnabled(int nID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton dans la barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le bouton est activé ; Sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Il vaut mieux appeler [GetState](#getstate) si vous souhaitez récupérer plusieurs États de bouton.  
  
##  <a name="a-nameisbuttonhiddena--ctoolbarctrlisbuttonhidden"></a><a name="isbuttonhidden"></a>CToolBarCtrl::IsButtonHidden  
 Détermine si le bouton spécifié dans un contrôle de barre d’outils est masqué.  
  
```  
BOOL IsButtonHidden(int nID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton dans la barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le bouton est masqué ; Sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Il vaut mieux appeler [GetState](#getstate) si vous souhaitez récupérer plusieurs États de bouton.  
  
##  <a name="a-nameisbuttonhighlighteda--ctoolbarctrlisbuttonhighlighted"></a><a name="isbuttonhighlighted"></a>CToolBarCtrl::IsButtonHighlighted  
 Vérifie l’état de mise en surbrillance d’un bouton de barre d’outils.  
  
```  
BOOL IsButtonHighlighted(int nID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 L’ID de commande pour le bouton de barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Entier positif, si le bouton est mis en surbrillance, 0 si le bouton n’est pas mis en surbrillance, ou -1 si une erreur se produit.  
  
##  <a name="a-nameisbuttonindeterminatea--ctoolbarctrlisbuttonindeterminate"></a><a name="isbuttonindeterminate"></a>CToolBarCtrl::IsButtonIndeterminate  
 Détermine si le bouton spécifié dans un contrôle de barre d’outils est indéterminé.  
  
```  
BOOL IsButtonIndeterminate(int nID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 Identificateur de commande du bouton dans la barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Entier positif si le bouton est indéterminé, zéro si le bouton n’est pas indéterminé, ou -1 si une erreur se produit.  
  
### <a name="remarks"></a>Remarques  
 Indéterminé boutons apparaissent estompés, telles que la méthode sur la barre d’outils, le bouton gras d’un traitement de texte se présente lorsque le texte sélectionné contient des caractères gras et régulières. Il vaut mieux appeler [GetState](#getstate) si vous souhaitez récupérer plusieurs États de bouton.  
  
##  <a name="a-nameisbuttonpresseda--ctoolbarctrlisbuttonpressed"></a><a name="isbuttonpressed"></a>CToolBarCtrl::IsButtonPressed  
 Détermine si le bouton spécifié dans un contrôle de barre d’outils est enfoncé.  
  
```  
BOOL IsButtonPressed(int nID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton dans la barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le bouton est activé, sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Il vaut mieux appeler [GetState](#getstate) si vous souhaitez récupérer plusieurs États de bouton.  
  
##  <a name="a-nameloadimagesa--ctoolbarctrlloadimages"></a><a name="loadimages"></a>CToolBarCtrl::LoadImages  
 Charge les images bitmap dans la liste d’images d’un contrôle de barre d’outils.  
  
```  
void LoadImages(
    int iBitmapID,  
    HINSTANCE hinst);
```  
  
### <a name="parameters"></a>Paramètres  
 *iBitmapID*  
 ID de la bitmap qui contient les images à charger. Pour spécifier votre propre ressource de bitmap, définissez ce paramètre sur l’ID d’une ressource bitmap et définissez `hInst` à **NULL**. Votre ressource bitmap sera ajoutée à la liste d’images comme une seule image. Vous pouvez ajouter des bitmaps standards, défini par le système en définissant *hinst* à **HINST_COMMCTRL** et en définissant ce paramètre sur un des ID suivants :  
  
|ID de bitmap|Description|  
|---------------|-----------------|  
|IDB_HIST_LARGE_COLOR|Explorer les bitmaps de grande taille|  
|IDB_HIST_SMALL_COLOR|Explorer les bitmaps de petite taille|  
|IDB_STD_LARGE_COLOR|Standards bitmaps de grande taille|  
|IDB_STD_SMALL_COLOR|Bitmaps standards de petite taille|  
|IDB_VIEW_LARGE_COLOR|Affichage des bitmaps de grande taille|  
|IDB_VIEW_SMALL_COLOR|Affichage des bitmaps de petite taille|  
  
 *HINST*  
 Handle d’instance de programme à l’application appelante. Ce paramètre peut être **HINST_COMMCTRL** pour charger une liste d’images standard.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_LOADIMAGES](http://msdn.microsoft.com/library/windows/desktop/bb787381), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemapacceleratora--ctoolbarctrlmapaccelerator"></a><a name="mapaccelerator"></a>CToolBarCtrl::MapAccelerator  
 Mappe un caractère accélérateur à un bouton de barre d’outils.  
  
```  
BOOL MapAccelerator(
    TCHAR chAccel,  
    UINT* pIDBtn);
```  
  
### <a name="parameters"></a>Paramètres  
 `chAccel`  
 Caractère d’accélérateur doit être mappé. Ce caractère est le même caractère souligné dans le texte du bouton.  
  
 *pIDBtn*  
 Un pointeur vers un **UINT** qui reçoit l’identificateur de commande du bouton qui correspond à l’accélérateur spécifié dans `chAccel`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_MAPACCELERATOR](http://msdn.microsoft.com/library/windows/desktop/bb787383), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemarkbuttona--ctoolbarctrlmarkbutton"></a><a name="markbutton"></a>CToolBarCtrl::MarkButton  
 Définit l’état de mise en surbrillance d’un bouton donné dans un contrôle de barre d’outils.  
  
```  
BOOL MarkButton(
    int nID,  
    BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 L’identificateur du bouton.  
  
 `fHighlight`  
 Spécifie l’état de mise en surbrillance à définir. Par défaut, **TRUE**. Si la valeur **FALSE**, le bouton est défini à son état par défaut.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_MARKBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787385), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemovebuttona--ctoolbarctrlmovebutton"></a><a name="movebutton"></a>CToolBarCtrl::MoveButton  
 Déplace un bouton à partir d’un index à l’autre.  
  
```  
BOOL MoveButton(
    UINT nOldPos,  
    UINT nNewPos);
```  
  
### <a name="parameters"></a>Paramètres  
 *nOldPos*  
 Index de base zéro du bouton à déplacer.  
  
 *nNewPos*  
 Index de base zéro de la destination du bouton.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TB_MOVEBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787387), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namepressbuttona--ctoolbarctrlpressbutton"></a><a name="pressbutton"></a>CToolBarCtrl::PressButton  
 Appuie ou relâche le bouton spécifié dans un contrôle de barre d’outils.  
  
```  
BOOL PressButton(int nID, BOOL bPress = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 Identificateur de commande du bouton à appuyer sur ou release.  
  
 [in] `bPress`  
 `true`Appuyez sur le bouton spécifié. `false` pour libérer le bouton spécifié. La valeur par défaut est `true`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode réussit ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez modifier plusieurs États de bouton, il vaut mieux appeler [SetState](#setstate) à la place.  
  
 Cette méthode envoie le [TB_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787389) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namereplacebitmapa--ctoolbarctrlreplacebitmap"></a><a name="replacebitmap"></a>CToolBarCtrl::ReplaceBitmap  
 Remplace le bitmap existante dans le contrôle de barre d’outils actuelle par une nouvelle image bitmap.  
  
```  
BOOL ReplaceBitmap(LPTBREPLACEBITMAP pReplaceBitmap);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `pReplaceBitmap`|Pointeur vers un [TBREPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb760484) structure qui décrit la bitmap à remplacer et la nouvelle bitmap.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [TB_REPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787391) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant remplace l’image bitmap de la barre d’outils standard avec une bitmap différents.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1 n °&2;](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_4.cpp)]  
  
##  <a name="a-namerestorestatea--ctoolbarctrlrestorestate"></a><a name="restorestate"></a>CToolBarCtrl::RestoreState  
 Restaure l’état du contrôle de barre d’outils à partir de l’emplacement dans le Registre spécifié par les paramètres.  
  
```  
void RestoreState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>Paramètres  
 `hKeyRoot`  
 Identifie une clé ouverte dans le Registre ou une des valeurs de handle réservés prédéfinis suivants :  
  
- **HKEY_CLASSES_ROOT**  
  
- **HKEY_CURRENT_USER**  
  
- **HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 Pointe vers une chaîne terminée par le caractère null qui contient le nom de la sous-clé auquel est associée une valeur. Ce paramètre peut être null ou un pointeur vers une chaîne vide. Si le paramètre est **NULL**, la valeur sera ajoutée à la clé identifiée par le `hKeyRoot` paramètre.  
  
 `lpszValueName`  
 Pointe vers une chaîne contenant le nom de la valeur à récupérer. Si une valeur portant ce nom n’est pas déjà présente dans la clé, la fonction ajoute à la clé.  
  
##  <a name="a-namesavestatea--ctoolbarctrlsavestate"></a><a name="savestate"></a>CToolBarCtrl::SaveState  
 Enregistre l’état du contrôle de barre d’outils à l’emplacement dans le Registre spécifié par les paramètres.  
  
```  
void SaveState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>Paramètres  
 `hKeyRoot`  
 Identifie une clé ouverte dans le Registre ou une des valeurs de handle réservés prédéfinis suivants :  
  
- **HKEY_CLASSES_ROOT**  
  
- **HKEY_CURRENT_USER**  
  
- **HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 Pointe vers une chaîne terminée par le caractère null qui contient le nom de la sous-clé auquel est associée une valeur. Ce paramètre peut être null ou un pointeur vers une chaîne vide. Si le paramètre est **NULL**, la valeur sera ajoutée à la clé identifiée par le `hKeyRoot` paramètre.  
  
 `lpszValueName`  
 Pointe vers une chaîne contenant le nom de la valeur à définir. Si une valeur portant ce nom n’est pas déjà présente dans la clé, la fonction ajoute à la clé.  
  
##  <a name="a-namesetanchorhighlighta--ctoolbarctrlsetanchorhighlight"></a><a name="setanchorhighlight"></a>CToolBarCtrl::SetAnchorHighlight  
 Définit la mise en surbrillance d’ancrage définition pour une barre d’outils.  
  
```  
BOOL SetAnchorHighlight(BOOL fAnchor = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `fAnchor`  
 Spécifie si la mise en surbrillance d’ancrage est activée ou désactivée. Si cette valeur est différente de zéro, la mise en surbrillance d’ancrage sera activée. Si cette valeur est nulle, la mise en surbrillance d’ancrage sera désactivée.  
  
### <a name="return-value"></a>Valeur de retour  
 Le paramètre d’ancrage précédent. Si la mise en surbrillance a été activée, cette valeur est différente de zéro. Si la mise en surbrillance n’était pas activé, cette valeur est zéro.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode implémente le comportement du message Win32 [TB_SETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787396), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbitmapsizea--ctoolbarctrlsetbitmapsize"></a><a name="setbitmapsize"></a>CToolBarCtrl::SetBitmapSize  
 Définit la taille des images bitmaps réelles à ajouter à un contrôle de barre d’outils.  
  
```  
BOOL SetBitmapSize(CSize size);
```  
  
### <a name="parameters"></a>Paramètres  
 `size`  
 Largeur et hauteur, en pixels, des images bitmaps.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction doit être appelée uniquement avant d’ajouter toutes les images bitmap dans la barre d’outils. Si l’application ne définit pas explicitement la taille de la bitmap, la valeur par défaut est 16 par 15 pixels.  
  
##  <a name="a-namesetbuttoninfoa--ctoolbarctrlsetbuttoninfo"></a><a name="setbuttoninfo"></a>CToolBarCtrl::SetButtonInfo  
 Définit les informations d’un bouton existant dans une barre d’outils.  
  
```  
BOOL SetButtonInfo(
    int nID,  
    TBBUTTONINFO* ptbbi);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 L’identificateur du bouton.  
  
 `ptbbi`  
 Un pointeur vers un [TBBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb760478) structure qui reçoit les informations de bouton.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 La fonction membre implémente le comportement du message Win32 [TB_SETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787413), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbuttonsizea--ctoolbarctrlsetbuttonsize"></a><a name="setbuttonsize"></a>CToolBarCtrl::SetButtonSize  
 Définit la taille des boutons dans le contrôle de barre d’outils.  
  
```  
BOOL SetButtonSize(CSize size);
```  
  
### <a name="parameters"></a>Paramètres  
 `size`  
 Largeur et hauteur, en pixels, des boutons.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 La taille du bouton doit toujours être au moins aussi grande que la taille de bitmap qu'elle englobe. Cette fonction doit être appelée uniquement avant d’ajouter toutes les images bitmap dans la barre d’outils. Si l’application ne définit pas explicitement la taille du bouton, la valeur par défaut est 24 par 22 pixels.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CToolBar::GetToolBarCtrl](../../mfc/reference/ctoolbar-class.md#gettoolbarctrl).  
  
##  <a name="a-namesetbuttonstructsizea--ctoolbarctrlsetbuttonstructsize"></a><a name="setbuttonstructsize"></a>CToolBarCtrl::SetButtonStructSize  
 Spécifie la taille de la `TBBUTTON` structure.  
  
```  
void SetButtonStructSize(int nSize);
```  
  
### <a name="parameters"></a>Paramètres  
 `nSize`  
 Taille, en octets, de la `TBBUTTON` structure.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez stocker des données supplémentaires dans les `TBBUTTON` structure, vous pouvez soit dériver une nouvelle structure de `TBBUTTON`, ajout de membres vous nécessaires ou créer une structure qui contient un `TBBUTTON` structure en tant que premier membre. Vous devez ensuite appeler cette fonction pour indiquer le contrôle de barre d’outils à la taille de la nouvelle structure.  
  
 Consultez la page [CToolBarCtrl::AddButtons](#addbuttons) pour plus d’informations sur la `TBBUTTON` structure.  
  
##  <a name="a-namesetbuttonwidtha--ctoolbarctrlsetbuttonwidth"></a><a name="setbuttonwidth"></a>CToolBarCtrl::SetButtonWidth  
 Définit les largeurs minimale et maximale de bouton dans le contrôle de barre d’outils.  
  
```  
BOOL SetButtonWidth(
    int cxMin,  
    int cxMax);
```  
  
### <a name="parameters"></a>Paramètres  
 `cxMin`  
 Largeur du bouton minimale, en pixels. Boutons de barre d’outils ne seront jamais plus étroites que cette valeur.  
  
 *cxMax*  
 Largeur du bouton maximale, en pixels. Si le texte du bouton est trop grand, le contrôle affiche avec des points de suspension.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_SETBUTTONWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb787417), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcmdida--ctoolbarctrlsetcmdid"></a><a name="setcmdid"></a>CToolBarCtrl::SetCmdID  
 Définit l’identificateur de commande qui sera envoyé à la fenêtre propriétaire lorsque vous appuyez sur le bouton spécifié.  
  
```  
BOOL SetCmdID(
    int nIndex,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro du bouton dont l’ID de commande doit être définie.  
  
 `nID`  
 L’ID de commande à la valeur du bouton sélectionné.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne zéro si l’opération a réussi ; Sinon, zéro.  
  
##  <a name="a-namesetcolorschemea--ctoolbarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>CToolBarCtrl::SetColorScheme  
 Définit le jeu de couleurs du contrôle barre d’outils en cours.  
  
```  
void SetColorScheme(const COLORSCHEME* lpColorScheme);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `lpColorScheme`|Pointeur vers un [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) structure qui décrit la couleur de surbrillance et la couleur de l’ombre du contrôle barre d’outils.|  
  
### <a name="remarks"></a>Remarques  
 Cette méthode n’a aucun effet si un [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] thème visuel est défini.  
  
 Cette méthode envoie le [TB_SETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787421) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit le jeu de couleurs pour le contrôle de barre d’outils en cours. L’exemple de code rend les bords gauche et supérieur de chaque bouton outil rouge et les bords droit et inférieur bleu. Lorsque l’utilisateur appuie sur le bouton, bords rouge du bouton deviennent bleus et ses bords bleus en rouges.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1 n °&3;](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_5.cpp)]  
  
##  <a name="a-namesetdisabledimagelista--ctoolbarctrlsetdisabledimagelist"></a><a name="setdisabledimagelist"></a>CToolBarCtrl::SetDisabledImageList  
 Définit la liste d’images qui utilise le contrôle de barre d’outils sur les boutons d’affichage désactivé.  
  
```  
CImageList* SetDisabledImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Paramètres  
 `pImageList`  
 Un pointeur vers un `CImageList` objet contenant les images à utiliser par le contrôle de barre d’outils pour les images de bouton Affichage désactivé.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet qui a été précédemment utilisé par le contrôle de barre d’outils pour les images de bouton Affichage désactivé.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_SETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787423), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. L’implémentation MFC de `SetDisabledImageList` utilise un `CImageList` objet contenant le bouton désactivé du contrôle barre d’outils de l’image, au lieu d’un handle vers une liste d’images.  
  
##  <a name="a-namesetdrawtextflagsa--ctoolbarctrlsetdrawtextflags"></a><a name="setdrawtextflags"></a>CToolBarCtrl::SetDrawTextFlags  
 Définit les indicateurs de la fonction Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), qui est utilisé pour dessiner le texte dans le rectangle spécifié, mis en forme selon la façon dont les indicateurs sont définis.  
  
```  
DWORD SetDrawTextFlags(
    DWORD dwMask,  
    DWORD dwDTFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwMask`  
 Une combinaison d’un ou plusieurs des indicateurs du préfixeDT_, spécifiés dans la fonction Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), qui indique les bits qui dans `dwDTFlags` sera utilisé lors du dessin du texte.  
  
 `dwDTFlags`  
 Une combinaison d’une ou plusieurs des indicateurs du préfixeDT_, spécifiés dans la fonction Win32 `DrawText`, qui indiquent comment le texte du bouton sera dessiné. Cette valeur est passée à `DrawText` lorsque le texte du bouton est dessiné.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `DWORD` contenant le texte précédent indicateurs de dessin.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_SETDRAWTEXTFLAGS](http://msdn.microsoft.com/library/windows/desktop/bb787425), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Cette fonction membre définit les indicateurs de la fonction Win32 `DrawText`, qui dessine le texte dans le rectangle spécifié, mis en forme selon la façon dont les indicateurs sont définis.  
  
##  <a name="a-namesetextendedstylea--ctoolbarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CToolBarCtrl::SetExtendedStyle  
 Définit les styles étendus pour un contrôle de barre d’outils.  
  
```  
DWORD SetExtendedStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwExStyle`  
 Valeur spécifiant les nouveaux styles prolongés. Ce paramètre peut être une combinaison de la barre d’outils de styles étendus.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `DWORD` qui représente le précédent styles étendus. Pour obtenir la liste des styles, consultez [Styles étendus de barre d’outils](http://msdn.microsoft.com/library/windows/desktop/bb760430), dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787427), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesethotimagelista--ctoolbarctrlsethotimagelist"></a><a name="sethotimagelist"></a>CToolBarCtrl::SetHotImageList  
 Définit la liste d’images qui utilise le contrôle de barre d’outils pour afficher des boutons « chaud ».  
  
```  
CImageList* SetHotImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Paramètres  
 `pImageList`  
 Un pointeur vers un `CImageList` objet contenant les images à utiliser par le contrôle de barre d’outils pour afficher des images de bouton actif.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet qui a été précédemment utilisé par le contrôle de barre d’outils pour afficher des images de bouton actif.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_SETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787429), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 L’implémentation MFC de `SetHotImageList` utilise un `CImageList` objet contenant le bouton d’actif du contrôle de barre d’outils de l’image, au lieu d’un handle vers une liste d’images. Un bouton actif apparaît en surbrillance lorsque le pointeur se trouve au-dessus d’elle.  
  
##  <a name="a-namesethotitema--ctoolbarctrlsethotitem"></a><a name="sethotitem"></a>CToolBarCtrl::SetHotItem  
 Définit l’élément actif dans une barre d’outils.  
  
```  
int SetHotItem(int nHot);
```  
  
### <a name="parameters"></a>Paramètres  
 *nHot*  
 Numéro d’index de base zéro de l’élément qui est apportée à chaud. Si cette valeur est -1, aucun des éléments ne sera actif.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de l’élément précédent à chaud, ou -1 s’il y a aucun élément à chaud.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_SETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787431), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetimagelista--ctoolbarctrlsetimagelist"></a><a name="setimagelist"></a>CToolBarCtrl::SetImageList  
 Définit la liste d’images qui utilise la barre d’outils pour afficher des boutons qui se trouvent dans leur état par défaut.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Paramètres  
 `pImageList`  
 Un pointeur vers un `CImageList` objet contenant les images à utiliser par le contrôle de barre d’outils pour afficher des images de bouton dans leur état par défaut.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet qui a été précédemment utilisé par le contrôle de barre d’outils pour afficher des images de bouton dans leur état par défaut.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TB_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787433), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 L’implémentation MFC de `SetImageList` utilise un `CImageList` objet contenant le bouton du contrôle de barre d’outils de l’image, au lieu d’un handle vers une liste d’images.  
  
##  <a name="a-namesetindenta--ctoolbarctrlsetindent"></a><a name="setindent"></a>CToolBarCtrl::SetIndent  
 Définit la mise en retrait pour le premier bouton dans un contrôle de barre d’outils.  
  
```  
BOOL SetIndent(int iIndent);
```  
  
### <a name="parameters"></a>Paramètres  
 *iIndent*  
 Valeur spécifiant la mise en retrait, en pixels.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="a-namesetinsertmarka--ctoolbarctrlsetinsertmark"></a><a name="setinsertmark"></a>CToolBarCtrl::SetInsertMark  
 Définit la marque d’insertion en cours de la barre d’outils.  
  
```  
void SetInsertMark(TBINSERTMARK* ptbim);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptbim`  
 Un pointeur vers le [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) structure qui contient la marque d’insertion.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787437), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetinsertmarkcolora--ctoolbarctrlsetinsertmarkcolor"></a><a name="setinsertmarkcolor"></a>CToolBarCtrl::SetInsertMarkColor  
 Définit la couleur utilisée pour dessiner la marque d’insertion de la barre d’outils.  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Paramètres  
 `clrNew`  
 A **COLORREF** valeur qui contient la nouvelle couleur de marque d’insertion.  
  
### <a name="return-value"></a>Valeur de retour  
 A **COLORREF** valeur qui contient la couleur précédente de la marque d’insertion.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [TB_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787439), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetmaxtextrowsa--ctoolbarctrlsetmaxtextrows"></a><a name="setmaxtextrows"></a>CToolBarCtrl::SetMaxTextRows  
 Définit le nombre maximal de lignes de texte affichées sur un bouton de barre d’outils.  
  
```  
BOOL SetMaxTextRows(int iMaxRows);
```  
  
### <a name="parameters"></a>Paramètres  
 *iMaxRows*  
 Nombre maximal de lignes à définir.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="a-namesetmetricsa--ctoolbarctrlsetmetrics"></a><a name="setmetrics"></a>CToolBarCtrl::SetMetrics  
 Définit les mesures de la `CToolBarCtrl` objet.  
  
```  
void SetMetrics(LPTBMETRICS ptbm);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptbm`  
 Un pointeur vers le [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482) structure de le `CToolBarCtrl` objet.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre émule les fonctionnalités de la [TB_SETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787446) d’un message, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetownera--ctoolbarctrlsetowner"></a><a name="setowner"></a>CToolBarCtrl::SetOwner  
 Définit la fenêtre propriétaire pour le contrôle de barre d’outils.  
  
```  
void SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Pointeur vers le `CWnd` ou `CWnd`-dérivés d’objet qui sera la nouvelle fenêtre propriétaire pour le contrôle de barre d’outils.  
  
### <a name="remarks"></a>Remarques  
 La fenêtre propriétaire est la fenêtre qui reçoit des notifications à partir de la barre d’outils.  
  
##  <a name="a-namesetpaddinga--ctoolbarctrlsetpadding"></a><a name="setpadding"></a>CToolBarCtrl::SetPadding  
 Définit le remplissage horizontal et vertical du contrôle barre d’outils en cours.  
  
```  
DWORD SetPadding(
    int nHorzPadding,   
    int nVertPadding);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `nHorzPadding`|Spécifie la marge horizontale du contrôle de barre d’outils, en pixels.|  
|[in] `nVertPadding`|Spécifie la marge verticale du contrôle barre d’outils, en pixels.|  
  
### <a name="return-value"></a>Valeur de retour  
 Un `DWORD` dont word faible contient la valeur précédente de la marge intérieure horizontale et dont le mot haute contient la valeur précédente de la marge intérieure verticale. Les valeurs de remplissage sont mesurées en pixels.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [TB_SETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787448) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la marge horizontale et verticale du contrôle barre d’outils en cours à 20 pixels.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1 n °&4;](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_6.cpp)]  
  
##  <a name="a-namesetpressedimagelista--ctoolbarctrlsetpressedimagelist"></a><a name="setpressedimagelist"></a>CToolBarCtrl::SetPressedImageList  
 Définit la liste d’images que le contrôle de barre d’outils actuelle utilise pour représenter les boutons à l’état enfoncé.  
  
```  
CImagelist* SetPressedImageList(
    int iImageID,   
    CImageList* pImageList);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `iImageID`|Index de base zéro de la liste d’images. Définissez ce paramètre sur zéro si vous utilisez uniquement une liste d’images.|  
|[in] `pImageList`|Pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) qui contient la liste d’images.|  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) qui contient la liste d’images précédent pour le contrôle actuel, ou `NULL` si aucune liste d’images de ce type a été défini.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [TB_SETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787453) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la liste d’images enfoncé pour être le même que la liste d’images par défaut.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1 n °&5;](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_7.cpp)]  
  
##  <a name="a-namesetrowsa--ctoolbarctrlsetrows"></a><a name="setrows"></a>CToolBarCtrl::SetRows  
 Demande le contrôle de barre d’outils doit se redimensionner pour le nombre de lignes demandé.  
  
```  
void SetRows(
    int nRows,  
    BOOL bLarger,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `nRows`  
 Nombre de lignes demandé.  
  
 `bLarger`  
 Indique s’il faut utiliser des lignes plus ou moins de lignes si la barre d’outils ne peut pas être modifiée et le nombre de lignes demandé.  
  
 `lpRect`  
 Pointe vers le [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure qui recevront le nouveau rectangle englobant de la barre d’outils.  
  
### <a name="remarks"></a>Remarques  
 Si la barre d’outils ne peut pas se redimensionne pour le nombre demandé de lignes, il est redimensionné automatiquement soit la suivante supérieure ou suivante plus petite taille valide, selon la valeur de `bLarger`. Si `bLarger` est **TRUE**, le nouveau nombre de lignes sera supérieur au nombre demandé. Si `bLarger` est **FALSE**, le nouveau nombre de lignes sera inférieur au nombre demandé.  
  
 Un certain nombre de lignes est valide pour la barre d’outils si les boutons peuvent être organisés de telle sorte que toutes les lignes ont le même nombre de boutons (sauf peut-être la dernière ligne). Par exemple, une barre d’outils qui contient quatre boutons ne peut pas être une taille trois lignes, car les deux dernières lignes devrait être plus courte. Si vous avez tenté de dimensionner sur trois lignes, vous obtenez quatre lignes si `bLarger` a **TRUE** et deux lignes si `bLarger` a **FALSE**.  
  
 S’il existe des séparateurs dans la barre d’outils, les règles lorsqu’un nombre donné de lignes est valid sont plus complexes. La disposition est calculée telles que les groupes de boutons (boutons avec un séparateur avant le premier) et le dernier bouton dans le groupe sont jamais réparties sur plusieurs lignes, sauf si le groupe ne peut pas tenir sur une seule ligne.  
  
 Si un groupe ne tient pas sur une ligne, le groupe suivant démarre sur la ligne suivante, même si elle tenait sur la ligne où le groupe s’est terminé. L’objectif de cette règle consiste à rendre la séparation entre la plus notable de grands groupes. Les séparateurs verticaux qui en résulte sont comptés comme des lignes.  
  
 Notez également que le `SetRows` fonction membre toujours choisir la disposition de la plus petite taille de la barre d’outils. Création d’une barre d’outils avec le `TBSTYLE_WRAPABLE` style et le redimensionnement du contrôle seront applique simplement la méthode décrite ci-dessus, compte tenu de la largeur du contrôle.  
  
 Cette fonction peut uniquement être appelée pour les barres d’outils qui ont été créés avec le `TBSTYLE_WRAPABLE` style.  
  
##  <a name="a-namesetstatea--ctoolbarctrlsetstate"></a><a name="setstate"></a>CToolBarCtrl::SetState  
 Définit l’état du bouton spécifié dans un contrôle de barre d’outils.  
  
```  
BOOL SetState(
    int nID,  
    UINT nState);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur de commande du bouton.  
  
 `nState`  
 Indicateurs d’état. Il peut être une combinaison des valeurs répertoriées pour les États de bouton dans [CToolBarCtrl::AddButtons](#addbuttons).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction peut s’avérer utile si vous souhaitez définir plusieurs des États de bouton. Pour simplement définir un état, utilisez une des fonctions membres suivantes : [EnableButton](#enablebutton), [CheckButton](#checkbutton), [HideButton](#hidebutton), [Indeterminate](#indeterminate), ou [PressButton](#pressbutton).  
  
##  <a name="a-namesetstylea--ctoolbarctrlsetstyle"></a><a name="setstyle"></a>CToolBarCtrl::SetStyle  
 Définit les styles d’un contrôle de barre d’outils.  
  
```  
void SetStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 A `DWORD` contenant une combinaison de [les styles de contrôle de barre d’outils](http://msdn.microsoft.com/library/windows/desktop/bb760439), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesettooltipsa--ctoolbarctrlsettooltips"></a><a name="settooltips"></a>CToolBarCtrl::SetToolTips  
 Associe un contrôle info-bulle à un contrôle de barre d’outils.  
  
```  
void SetToolTips(CToolTipCtrl* pTip);
```  
  
### <a name="parameters"></a>Paramètres  
 *pTip*  
 Pointeur vers le [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) objet.  
  
##  <a name="a-namesetwindowthemea--ctoolbarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CToolBarCtrl::SetWindowTheme  
 Définit le style visuel de le `CToolBarCtrl` objet.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszSubAppName`  
 Pointeur vers une chaîne Unicode qui contient le style visuel de la barre d’outils à définir.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour n’est pas utilisée.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre émule les fonctionnalités de la [TB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb787465) d’un message, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [MFC exemple CMNCTRL1](../../visual-cpp-samples.md)   
 [Exemple MFC MFCIE](../../visual-cpp-samples.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CToolBar (classe)](../../mfc/reference/ctoolbar-class.md)

