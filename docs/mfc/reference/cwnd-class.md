---
title: CWnd (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWnd
dev_langs:
- C++
helpviewer_keywords:
- windows [C++]
- window objects [C++]
- CWnd class
ms.assetid: 49a832ee-bc34-4126-88b3-bc1d9974f6c4
caps.latest.revision: 27
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
ms.openlocfilehash: ab9007e512f5af43bdace06796fb8487ffebc8e6
ms.lasthandoff: 02/24/2017

---
# <a name="cwnd-class"></a>CWnd, classe
Fournit les fonctionnalités de base de toutes les classes de fenêtres de la bibliothèque MFC (Microsoft Foundation Class).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CWnd : public CCmdTarget  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWnd::CWnd](#cwnd)|Construit un objet `CWnd`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWnd::accDoDefaultAction](#accdodefaultaction)|Appelé par l'infrastructure pour effectuer l'action par défaut de l'objet.|  
|[CWnd::accHitTest](#acchittest)|Appelé par l'infrastructure pour récupérer l'élément enfant ou l'objet enfant à un point déterminé de l'écran.|  
|[CWnd::accLocation](#acclocation)|Appelé par l'infrastructure pour récupérer l'emplacement d'affichage actuel de l'objet spécifié.|  
|[CWnd::accNavigate](#accnavigate)|Appelé par l'infrastructure pour accéder à un autre élément d'interface utilisateur au sein d'un conteneur et, dans la mesure du possible, récupérer l'objet.|  
|[CWnd::accSelect](#accselect)|Appelé par l'infrastructure pour modifier la sélection ou déplacer le focus clavier de l'objet spécifié.|  
|[CWnd::AnimateWindow](#animatewindow)|Anime l'objet fenêtre associé.|  
|[CWnd::ArrangeIconicWindows](#arrangeiconicwindows)|Réorganise toutes les fenêtres enfants réduites (sous forme d'icônes).|  
|[CWnd::Attach](#attach)|Attache un handle Windows à un objet `CWnd`.|  
|[CWnd::BeginModalState](#beginmodalstate)|Appelez cette fonction membre pour rendre modale une fenêtre frame.|  
|[CWnd::BeginPaint](#beginpaint)|Prépare `CWnd` pour la peinture.|  
|[CWnd::BindDefaultProperty](#binddefaultproperty)|Lie la propriété liée simple par défaut de l'objet appelant, comme indiqué dans la bibliothèque de types, à un curseur associé à un contrôle de source de données.|  
|[CWnd::BindProperty](#bindproperty)|Lie une propriété liée au curseur d’un contrôle lié aux données à un contrôle de source de données et inscrit cette relation auprès du gestionnaire de liaisons MFC.|  
|[CWnd::BringWindowToTop](#bringwindowtotop)|Place `CWnd` en haut d'une pile de fenêtres superposées.|  
|[CWnd::CalcWindowRect](#calcwindowrect)|Appelé pour calculer le rectangle de la fenêtre à partir du rectangle client.|  
|[CWnd::CancelToolTips](#canceltooltips)|Désactive le contrôle d'info-bulle.|  
|[CWnd::CenterWindow](#centerwindow)|Centre une fenêtre par rapport à son parent.|  
|[CWnd::ChangeClipboardChain](#changeclipboardchain)|Supprime `CWnd` de la chaîne de visionneuses de Presse-papiers.|  
|[CWnd::CheckDlgButton](#checkdlgbutton)|Place une coche à côté d'un contrôle bouton ou la supprime.|  
|[CWnd::CheckRadioButton](#checkradiobutton)|Vérifie la case d'option spécifiée et supprime la coche de toutes les autres cases d'option contenues dans le groupe de boutons spécifié.|  
|[CWnd::ChildWindowFromPoint](#childwindowfrompoint)|Parmi les fenêtres enfants existantes, détermine celles qui contiennent le point spécifié, le cas échéant.|  
|[CWnd::ClientToScreen](#clienttoscreen)|Convertit les coordonnées clientes d'un point ou rectangle donné affiché en coordonnées d'écran.|  
|[CWnd::CloseWindow](#closewindow)|Réduit la fenêtre.|  
|[CWnd::ContinueModal](#continuemodal)|Conserve l'état modal d'une fenêtre.|  
|[CWnd::Create](#create)|Crée et initialise la fenêtre enfant associée à l'objet `CWnd`.|  
|[CWnd::CreateAccessibleProxy](#createaccessibleproxy)|Crée un proxy Active Accessibility pour l'objet spécifié.|  
|[CWnd::CreateCaret](#createcaret)|Crée une forme pour le signe insertion et obtient la propriété du caret.|  
|[CWnd::CreateControl](#createcontrol)|Crée un contrôle ActiveX qui sera représenté dans un programme MFC par un objet `CWnd`.|  
|[CWnd::CreateEx](#createex)|Crée une fenêtre Windows superposée, indépendante ou enfant et l'attache à un objet `CWnd`.|  
|[CWnd::CreateGrayCaret](#creategraycaret)|Crée un bloc gris pour le signe insertion et obtient la propriété du caret.|  
|[CWnd::CreateSolidCaret](#createsolidcaret)|Crée un bloc uni pour le signe insertion et obtient la propriété du caret.|  
|[CWnd::DeleteTempMap](#deletetempmap)|Appelé automatiquement par le gestionnaire de durée d'inactivité `CWinApp` et supprime les objets `CWnd` temporaires créés par `FromHandle`.|  
|[CWnd::DestroyWindow](#destroywindow)|Détruit la fenêtre Windows attachée.|  
|[CWnd::Detach](#detach)|Détache un handle Windows d'un objet `CWnd` et retourne le handle.|  
|[CWnd::DlgDirList](#dlgdirlist)|Remplit une zone de liste avec une liste de fichiers ou de répertoires.|  
|[CWnd::DlgDirListComboBox](#dlgdirlistcombobox)|Remplit la zone de liste d'une zone de liste modifiable avec une liste de fichiers ou de répertoires.|  
|[CWnd::DlgDirSelect](#dlgdirselect)|Récupère la sélection actuelle d'une zone de liste.|  
|[CWnd::DlgDirSelectComboBox](#dlgdirselectcombobox)|Récupère la sélection actuelle de la zone de liste d'une zone de liste modifiable.|  
|[CWnd::DragAcceptFiles](#dragacceptfiles)|Indique que la fenêtre acceptera les fichiers déplacés.|  
|[CWnd::DragDetect](#dragdetect)|Capture la souris et suit ses déplacements jusqu’à ce que l’utilisateur relâche le bouton gauche, appuie sur la touche Échap ou déplace la souris en dehors du rectangle de glissement entourant le point spécifié.|  
|[CWnd::DrawAnimatedRects](#drawanimatedrects)|Dessine un rectangle en mode filaire et l'anime pour indiquer l'ouverture d'une icône ou la réduction ou agrandissement d'une fenêtre.|  
|[CWnd::DrawCaption](#drawcaption)|Dessine une légende.|  
|[CWnd::DrawMenuBar](#drawmenubar)|Redessine la barre de menus.|  
|[CWnd::EnableActiveAccessibility](#enableactiveaccessibility)|Active les fonctions `Active Accessibility` définies par l'utilisateur.|  
|[CWnd::EnableDynamicLayout](#enabledynamiclayout)|Active la position et la taille des fenêtres enfants pour qu'elles s'ajustent dynamiquement quand l'utilisateur redimensionne la fenêtre.|  
|[CWnd::EnableD2DSupport](#enabled2dsupport)|Active ou désactive la prise en charge `D2D` de la fenêtre. Appelez cette méthode avant que la fenêtre principale soit initialisée.|  
|[CWnd::EnableScrollBar](#enablescrollbar)|Active ou désactive une flèche (ou les deux) d'une barre de défilement.|  
|[CWnd::EnableScrollBarCtrl](#enablescrollbarctrl)|Active ou désactive un contrôle de barre de défilement frère.|  
|[CWnd::EnableToolTips](#enabletooltips)|Active le contrôle d'info-bulle.|  
|[CWnd::EnableTrackingToolTips](#enabletrackingtooltips)|Active le contrôle d'info-bulle en mode de suivi.|  
|[CWnd::EnableWindow](#enablewindow)|Active ou désactive les entrées de souris et de clavier.|  
|[CWnd::EndModalLoop](#endmodalloop)|Met fin à l'état modal d'une fenêtre.|  
|[CWnd::EndModalState](#endmodalstate)|Appelez cette fonction membre pour changer une fenêtre frame modale en fenêtre frame non modale.|  
|[CWnd::EndPaint](#endpaint)|Marque la fin de la peinture.|  
|[CWnd::ExecuteDlgInit](#executedlginit)|Initie une ressource de boîte de dialogue|  
|[CWnd::FilterToolTipMessage](#filtertooltipmessage)|Récupère le titre ou le texte associé à un contrôle de boîte de dialogue.|  
|[CWnd::FindWindow](#findwindow)|Retourne le handle de la fenêtre, qui est identifiée par ses nom et classe de fenêtre.|  
|[CWnd::FindWindowEx](#findwindowex)|Retourne le handle de la fenêtre, qui est identifiée par ses nom et classe de fenêtre.|  
|[CWnd::FlashWindow](#flashwindow)|Fait clignoter la fenêtre une fois.|  
|[CWnd::FlashWindowEx](#flashwindowex)|Fait clignoter la fenêtre avec des fonctionnalités supplémentaires.|  
|[CWnd::FromHandle](#fromhandle)|Retourne un pointeur vers un objet `CWnd` quand un handle de fenêtre lui est fourni. Si aucun objet `CWnd` n'est attaché au handle, un objet `CWnd` temporaire est créé et attaché.|  
|[CWnd::FromHandlePermanent](#fromhandlepermanent)|Retourne un pointeur vers un objet `CWnd` quand un handle de fenêtre lui est fourni. Si aucun objet `CWnd` n'est attaché au handle, un objet `CWnd` temporaire est créé et attaché.|  
|[CWnd::get_accChild](#get_accchild)|Appelé par l'infrastructure pour récupérer l'adresse d'une interface `IDispatch` pour l'enfant spécifié.|  
|[CWnd::get_accChildCount](#get_accchildcount)|Appelé par l'infrastructure pour récupérer le nombre d'enfants appartenant à cet objet.|  
|[CWnd::get_accDefaultAction](#get_accdefaultaction)|Appelé par l'infrastructure pour récupérer une chaîne qui décrit l'action par défaut de l'objet.|  
|[CWnd::get_accDescription](#get_accdescription)|Appelé par l'infrastructure pour récupérer une chaîne qui décrit l'aspect visuel de l'objet spécifié.|  
|[CWnd::get_accFocus](#get_accfocus)|Appelé par l'infrastructure pour récupérer l'objet qui a le focus clavier.|  
|[CWnd::get_accHelp](#get_acchelp)|Appelé par l’infrastructure pour récupérer un objet **aide** chaîne de la propriété.|  
|[CWnd::get_accHelpTopic](#get_acchelptopic)|Appelé par l'infrastructure pour récupérer le chemin d'accès complet du fichier `WinHelp` associé à l'objet spécifié, ainsi que l'identificateur de la rubrique appropriée au sein de ce fichier.|  
|[CWnd::get_accKeyboardShortcut](#get_acckeyboardshortcut)|Appelé par l'infrastructure pour récupérer la touche de raccourci ou la touche d'accès rapide de l'objet spécifié.|  
|[CWnd::get_accName](#get_accname)|Appelé par l'infrastructure pour récupérer le nom de l'objet spécifié.|  
|[CWnd::get_accParent](#get_accparent)|Appelé par l'infrastructure pour récupérer l'interface `IDispatch` du parent de l'objet.|  
|[CWnd::get_accRole](#get_accrole)|Appelé par l'infrastructure pour récupérer les informations qui décrivent le rôle de l'objet spécifié.|  
|[CWnd::get_accSelection](#get_accselection)|Appelé par l'infrastructure pour récupérer les enfants sélectionnés de cet objet.|  
|[CWnd::get_accState](#get_accstate)|Appelé par l'infrastructure pour récupérer l'état actuel de l'objet spécifié.|  
|[CWnd::get_accValue](#get_accvalue)|Appelé par l'infrastructure pour récupérer la valeur de l'objet spécifié.|  
|[CWnd::GetActiveWindow](#getactivewindow)|Récupère la fenêtre active.|  
|[CWnd::GetAncestor](#getancestor)|Récupère l'objet fenêtre ancêtre de la fenêtre spécifiée.|  
|[CWnd::GetCapture](#getcapture)|Récupère le `CWnd` qui détient la capture de souris.|  
|[CWnd::GetCaretPos](#getcaretpos)|Récupère les coordonnées clientes de la position actuelle du caret.|  
|[CWnd::GetCheckedRadioButton](#getcheckedradiobutton)|Retourne l'ID de la case d'option actuellement activée dans un groupe de boutons.|  
|[CWnd::GetClientRect](#getclientrect)|Obtient les dimensions de la zone cliente `CWnd`.|  
|[CWnd::GetClipboardOwner](#getclipboardowner)|Récupère un pointeur désignant le propriétaire actuel du Presse-papiers.|  
|[CWnd::GetClipboardViewer](#getclipboardviewer)|Récupère un pointeur désignant la première fenêtre de la chaîne de visionneuses de Presse-papiers.|  
|[CWnd::GetControlUnknown](#getcontrolunknown)|Récupère un pointeur vers un contrôle ActiveX inconnu.|  
|[CWnd::GetDC](#getdc)|Récupère un contexte d'affichage pour la zone cliente.|  
|[CWnd::GetDCEx](#getdcex)|Récupère un contexte d'affichage pour la zone cliente et active le détourage pendant le traçage du dessin.|  
|[CWnd::GetDCRenderTarget](#getdcrendertarget)|Récupère la cible de rendu du contexte de périphérique pour la fenêtre `CWnd`.|  
|[CWnd::GetDescendantWindow](#getdescendantwindow)|Recherche dans toutes les fenêtres descendantes et retourne la fenêtre ayant l'ID spécifié.|  
|[CWnd::GetDesktopWindow](#getdesktopwindow)|Récupère la fenêtre du bureau Windows.|  
|[CWnd::GetDlgCtrlID](#getdlgctrlid)|Si `CWnd` est une fenêtre enfant, l'appel de cette fonction retourne sa valeur d'ID.|  
|[CWnd::GetDlgItem](#getdlgitem)|Récupère le contrôle ayant l'ID spécifié dans la boîte de dialogue spécifiée.|  
|[CWnd::GetDlgItemInt](#getdlgitemint)|Traduit le texte d'un contrôle de la boîte de dialogue spécifiée en valeur entière.|  
|[CWnd::GetDlgItemText](#getdlgitemtext)|Récupère la légende ou le texte associé à un contrôle.|  
|[CWnd::GetDSCCursor](#getdsccursor)|Récupère un pointeur désignant le curseur sous-jacent défini par les propriétés DataSource, UserName, Password et SQL d'un contrôle de source de données.|  
|[CWnd::GetDynamicLayout](#getdynamiclayout)|Récupère un pointeur désignant l'objet gestionnaire de disposition dynamique.|  
|[CWnd::GetExStyle](#getexstyle)|Retourne le style étendu de la fenêtre.|  
|[CWnd::GetFocus](#getfocus)|Récupère le `CWnd` qui a actuellement le focus d'entrée.|  
|[CWnd::GetFont](#getfont)|Récupère la police actuelle.|  
|[CWnd::GetForegroundWindow](#getforegroundwindow)|Retourne un pointeur désignant la fenêtre de premier plan (fenêtre de niveau supérieur dans laquelle l'utilisateur travaille actuellement).|  
|[CWnd::GetIcon](#geticon)|Récupère le handle d'une icône.|  
|[CWnd::GetLastActivePopup](#getlastactivepopup)|Identifie la dernière fenêtre contextuelle détenue par `CWnd` à avoir été active.|  
|[CWnd::GetLayeredWindowAttributes](#getlayeredwindowattributes)|Récupère la clé de couleur d'opacité et de transparence d'une fenêtre superposée.|  
|[CWnd::GetMenu](#getmenu)|Récupère un pointeur vers le menu spécifié.|  
|[CWnd::GetNextDlgGroupItem](#getnextdlggroupitem)|Recherche le contrôle suivant (ou précédent) au sein d'un groupe de contrôles.|  
|[CWnd::GetNextDlgTabItem](#getnextdlgtabitem)|Récupère le premier contrôle avec la [WS_TABSTOP](window-styles.md) style qui suit (ou précède) du contrôle spécifié.|  
|[CWnd::GetNextWindow](#getnextwindow)|Retourne la fenêtre suivante (ou précédente) dans la liste du gestionnaire de fenêtrage.|  
|[CWnd::GetOleControlSite](#getolecontrolsite)|Récupère le site personnalisé pour le contrôle ActiveX spécifié.|  
|[CWnd::GetOpenClipboardWindow](#getopenclipboardwindow)|Récupère un pointeur vers la fenêtre pour laquelle le Presse-papiers est actuellement ouvert.|  
|[CWnd::GetOwner](#getowner)|Récupère un pointeur vers le propriétaire d'un `CWnd`.|  
|[CWnd::GetParent](#getparent)|Récupère la fenêtre parente de `CWnd` (le cas échéant).|  
|[CWnd::GetParentFrame](#getparentframe)|Récupère la fenêtre frame parente de l'objet `CWnd`.|  
|[CWnd::GetParentOwner](#getparentowner)|Retourne un pointeur vers la fenêtre parente d'une fenêtre enfant.|  
|[CWnd::GetProperty](#getproperty)|Récupère une propriété de contrôle ActiveX.|  
|[CWnd::GetRenderTarget](#getrendertarget)|Obtient une cible de rendu associée à cette fenêtre.|  
|[CWnd::GetSafeHwnd](#getsafehwnd)|Retourne `m_hWnd` ou `NULL` si le pointeur `this` a la valeur `NULL`.|  
|[CWnd::GetSafeOwner](#getsafeowner)|Récupère le propriétaire sécurisé pour la fenêtre spécifiée.|  
|[CWnd::GetScrollBarCtrl](#getscrollbarctrl)|Retourne un contrôle de barre de défilement frère.|  
|[CWnd::GetScrollBarInfo](#getscrollbarinfo)|Récupère les informations sur la barre de défilement spécifiée.|  
|[CWnd::GetScrollInfo](#getscrollinfo)|Récupère les informations que la structure `SCROLLINFO` conserve à propos d'une barre de défilement.|  
|[CWnd::GetScrollLimit](#getscrolllimit)|Récupère la limite de la barre de défilement.|  
|[CWnd::GetScrollPos](#getscrollpos)|Récupère la position actuelle d'une case de défilement.|  
|[CWnd::GetScrollRange](#getscrollrange)|Copie les positions minimale et maximale actuelles de la barre de défilement spécifiée.|  
|[CWnd::GetStyle](#getstyle)|Retourne le style de fenêtre actif.|  
|[CWnd::GetSystemMenu](#getsystemmenu)|Permet à l'application d'accéder au menu Système pour copie et modification.|  
|[CWnd::GetTitleBarInfo](#gettitlebarinfo)|Récupère les informations sur la barre de titre spécifiée.|  
|[CWnd::GetTopLevelFrame](#gettoplevelframe)|Récupère la fenêtre frame de niveau supérieur de la fenêtre.|  
|[CWnd::GetTopLevelOwner](#gettoplevelowner)|Récupère la fenêtre de niveau supérieur.|  
|[Plus élevé](#gettoplevelparent)|Récupère le parent de niveau supérieur de la fenêtre.|  
|[CWnd::GetTopWindow](#gettopwindow)|Retourne la première fenêtre enfant qui appartient à `CWnd`.|  
|[CWnd::GetUpdateRect](#getupdaterect)|Récupère les coordonnées du plus petit rectangle qui englobe entièrement la région de mise à jour `CWnd`.|  
|[CWnd::GetUpdateRgn](#getupdatergn)|Récupère la région de mise à jour `CWnd`.|  
|[CWnd::GetWindow](#getwindow)|Retourne la fenêtre avec la relation spécifiée de cette fenêtre.|  
|[CWnd::GetWindowContextHelpId](#getwindowcontexthelpid)|Récupère l'identificateur de contexte d'aide.|  
|[CWnd::GetWindowDC](#getwindowdc)|Récupère le contexte d'affichage de la fenêtre entière, y compris la barre de légende, les menus et les barres de défilement.|  
|[CWnd::GetWindowedChildCount](#getwindowedchildcount)|Retourne le nombre de fenêtres enfants associées.|  
|[CWnd::GetWindowInfo](#getwindowinfo)|Retourne les informations sur la fenêtre.|  
|[CWnd::GetWindowlessChildCount](#getwindowlesschildcount)|Retourne le nombre de fenêtres enfants sans fenêtre associées.|  
|[CWnd::GetWindowPlacement](#getwindowplacement)|Récupère l'état d'affichage et les positions normale (restaurée), réduite et agrandie d'une fenêtre.|  
|[CWnd::GetWindowRect](#getwindowrect)|Obtient les coordonnées d'écran de `CWnd`.|  
|[CWnd::GetWindowRgn](#getwindowrgn)|Récupère une copie de la région de fenêtre d'une fenêtre.|  
|[CWnd::GetWindowText](#getwindowtext)|Retourne le texte de la fenêtre ou le titre de la légende (le cas échéant).|  
|[CWnd::GetWindowTextLength](#getwindowtextlength)|Retourne la longueur du texte de la fenêtre ou du titre de légende.|  
|[CWnd::HideCaret](#hidecaret)|Masque le caret en le supprimant de l'écran.|  
|[CWnd::HiliteMenuItem](#hilitemenuitem)|Met en surbrillance ou supprime la mise en surbrillance d'un élément de menu (barre de menus) de niveau supérieur.|  
|[CWnd::HtmlHelp](#htmlhelp)|Appelé pour lancer l'application HTMLHelp.|  
|[CWnd::Invalidate](#invalidate)|Invalide la zone cliente dans son intégralité.|  
|[CWnd::InvalidateRect](#invalidaterect)|Invalide la zone cliente dans le rectangle donné en ajoutant ce rectangle à la région de mise à jour actuelle.|  
|[CWnd::InvalidateRgn](#invalidatergn)|Invalide la zone cliente dans la région en question donnée en ajoutant cette région à la région de mise à jour actuelle.|  
|[CWnd::InvokeHelper](#invokehelper)|Appelle une méthode ou une propriété de contrôle ActiveX.|  
|[CWnd::IsChild](#ischild)|Indique si `CWnd` est une fenêtre enfant ou un autre descendant direct de la fenêtre spécifiée.|  
|[CWnd::IsD2DSupportEnabled](#isd2dsupportenabled)|Détermine si la prise en charge `D2D` est activée.|  
|[CWnd::IsDialogMessage](#isdialogmessage)|Détermine si le message donné est destiné à la boîte de dialogue non modale et, si tel est le cas, le traite.|  
|[CWnd::IsDlgButtonChecked](#isdlgbuttonchecked)|Détermine si un contrôle bouton est activé.|  
|[CWnd::IsDynamicLayoutEnabled](#isdynamiclayoutenabled)|Détermine si la disposition dynamique est activée dans cette fenêtre. Si la disposition dynamique est activée, la position et la taille des fenêtres enfants peuvent changer quand l'utilisateur redimensionne la fenêtre parente.|  
|[CWnd::IsIconic](#isiconic)|Détermine si `CWnd` est réduit (sous forme d'icône).|  
|[CWnd::IsTouchWindow](#istouchwindow)|Spécifie si `CWnd` intègre une prise en charge de l'interface tactile.|  
|[CWnd::IsWindowEnabled](#iswindowenabled)|Détermine si la fenêtre est activée pour les entrées de souris et de clavier.|  
|[CWnd::IsWindowVisible](#iswindowvisible)|Détermine si la fenêtre est visible.|  
|[CWnd::IsZoomed](#iszoomed)|Détermine si `CWnd` est agrandi.|  
|[CWnd::KillTimer](#killtimer)|Tue une horloge système.|  
|[CWnd::LockWindowUpdate](#lockwindowupdate)|Désactive ou réactive un dessin dans la fenêtre donnée.|  
|[CWnd::MapWindowPoints](#mapwindowpoints)|Convertit (mappe) un ensemble de points de l'espace de coordonnées de `CWnd` dans celui d'une autre fenêtre.|  
|[CWnd::MessageBox](#messagebox)|Crée et affiche une fenêtre qui contient un message et une légende fournis par l'application.|  
|[CWnd::ModifyStyle](#modifystyle)|Modifie le style de fenêtre actif.|  
|[CWnd::ModifyStyleEx](#modifystyleex)|Modifie le style étendu de la fenêtre.|  
|[CWnd::MoveWindow](#movewindow)|Modifie la position et les dimensions de `CWnd`.|  
|[CWnd::NotifyWinEvent](#notifywinevent)|Signale au système qu'un événement prédéfini s'est produit.|  
|[CWnd::OnAmbientProperty](#onambientproperty)|Implémente les valeurs de propriété ambiante.|  
|[CWnd::OnDrawIconicThumbnailOrLivePreview](#ondrawiconicthumbnailorlivepreview)|Appelé par l'infrastructure quand elle a besoin d'obtenir une image bitmap à afficher sur une miniature d'onglet Windows 7 ou sur le client pour l'aperçu de l'application.|  
|[CWnd::OnHelp](#onhelp)|Gère l'aide F1 dans l'application (en utilisant le contexte actuel).|  
|[CWnd::OnHelpFinder](#onhelpfinder)|Gère les commandes `ID_HELP_FINDER` et `ID_DEFAULT_HELP`.|  
|[CWnd::OnHelpIndex](#onhelpindex)|Gère la commande `ID_HELP_INDEX` et fournit une rubrique d'aide par défaut.|  
|[CWnd::OnHelpUsing](#onhelpusing)|Gère la commande `ID_HELP_USING`.|  
|[CWnd::OnToolHitTest](#ontoolhittest)|Détermine si un point se trouve dans le rectangle englobant de l'outil spécifié et récupère les informations sur l'outil.|  
|[CWnd::OpenClipboard](#openclipboard)|Ouvre le Presse-papiers. Autres applications ne seront pas en mesure de modifier le Presse-papiers jusqu'à ce que Windows [la fermeture du Presse-papiers](http://msdn.microsoft.com/library/windows/desktop/ms649035) fonction est appelée.|  
|[CWnd::PaintWindowlessControls](#paintwindowlesscontrols)|Dessine des contrôles sans fenêtre sur le conteneur de contrôle.|  
|[CWnd::PostMessage](#postmessage)|Place un message dans la file d'attente d'application, puis retourne une valeur sans attendre que la fenêtre ait traité le message.|  
|[CWnd::PreCreateWindow](#precreatewindow)|Appelé avant la création de la fenêtre Windows attachée à cet objet `CWnd`.|  
|[CWnd::PreSubclassWindow](#presubclasswindow)|Permet d’autres sous-classement nécessaire avant de [SubclassWindow](#subclasswindow) est appelée.|  
|[CWnd::PreTranslateMessage](#pretranslatemessage)|Utilisé par `CWinApp` pour filtrer les messages de fenêtre avant d'être distribués aux fonctions Windows `TranslateMessage` et `DispatchMessage`.|  
|[CWnd::Print](#print)|Dessine la fenêtre active dans le contexte de périphérique spécifié.|  
|[CWnd::PrintClient](#printclient)|Dessine une fenêtre dans le contexte de périphérique spécifié (généralement un contexte de périphérique d'impression).|  
|[CWnd::PrintWindow](#printwindow)|Copie une fenêtre visuelle dans le contexte de périphérique spécifié, en général un contexte de périphérique d'impression.|  
|[CWnd::RedrawWindow](#redrawwindow)|Met à jour la région ou le rectangle spécifié dans la zone cliente.|  
|[CWnd::RegisterTouchWindow](#registertouchwindow)|Inscrit/annule l'inscription de la prise en charge de l'interface tactile Windows de fenêtre.|  
|[CWnd::ReleaseDC](#releasedc)|Libère les contextes de périphérique client et fenêtre, ce qui les libère en vue d’une utilisation par d’autres applications.|  
|[CWnd::RepositionBars](#repositionbars)|Repositionne les barres de contrôle dans la zone cliente.|  
|[CWnd::RunModalLoop](#runmodalloop)|Récupère, traduit ou distribue les messages pour une fenêtre qui est à l'état modal.|  
|[CWnd::ScreenToClient](#screentoclient)|Convertit les coordonnées d'écran d'un point ou rectangle donné sur l'affichage en coordonnées clientes.|  
|[CWnd::ScrollWindow](#scrollwindow)|Fait défiler le contenu de la zone cliente.|  
|[CWnd::ScrollWindowEx](#scrollwindowex)|Fait défiler le contenu de la zone cliente. Semblable à `ScrollWindow` avec des fonctionnalités supplémentaires.|  
|[CWnd::SendChildNotifyLastMsg](#sendchildnotifylastmsg)|Fournit un message de notification à une fenêtre enfant, à partir de la fenêtre parente, pour que la fenêtre enfant puisse gérer une tâche.|  
|[CWnd::SendDlgItemMessage](#senddlgitemmessage)|Envoie un message au contrôle spécifié.|  
|[CWnd::SendMessage](#sendmessage)|Envoie un message à l'objet `CWnd` et ne retourne pas de valeur tant qu'il n'a pas traité le message.|  
|[CWnd::SendMessageToDescendants](#sendmessagetodescendants)|Envoie un message à toutes les fenêtres descendantes de la fenêtre.|  
|[CWnd::SendNotifyMessage](#sendnotifymessage)|Envoie le message spécifié à la fenêtre et retourne une valeur dès que possible, selon que le thread appelant a créé ou non la fenêtre.|  
|[CWnd::SetActiveWindow](#setactivewindow)|Active la fenêtre.|  
|[CWnd::SetCapture](#setcapture)|Provoque l'envoi de toutes les entrées de souris ultérieures à `CWnd`.|  
|[CWnd::SetCaretPos](#setcaretpos)|Déplace le caret vers une position spécifiée.|  
|[CWnd::SetClipboardViewer](#setclipboardviewer)|Ajoute `CWnd` à la chaîne de fenêtres qui sont notifiées chaque fois que le contenu du Presse-papiers est modifié.|  
|[CWnd::SetDlgCtrlID](#setdlgctrlid)|Définit l'ID de fenêtre ou l'ID de contrôle de la fenêtre (qui peut être une fenêtre enfant, et pas seulement un contrôle de boîte de dialogue).|  
|[CWnd::SetDlgItemInt](#setdlgitemint)|Définit le texte d'un contrôle avec la chaîne qui représente une valeur entière.|  
|[CWnd::SetDlgItemText](#setdlgitemtext)|Définit la légende ou le texte d'un contrôle dans la boîte de dialogue spécifiée.|  
|[CWnd::SetFocus](#setfocus)|Revendique le focus d'entrée.|  
|[CWnd::SetFont](#setfont)|Définit la police actuelle.|  
|[CWnd::SetForegroundWindow](#setforegroundwindow)|Place le thread créé par la fenêtre au premier plan et active la fenêtre.|  
|[CWnd::SetIcon](#seticon)|Définit le handle avec une icône spécifique.|  
|[CWnd::SetLayeredWindowAttributes](#setlayeredwindowattributes)|Définit la clé de couleur d'opacité et de transparence d'une fenêtre superposée.|  
|[CWnd::SetMenu](#setmenu)|Définit le menu avec le menu spécifié.|  
|[CWnd::SetOwner](#setowner)|Modifie le propriétaire d'un `CWnd`.|  
|[CWnd::SetParent](#setparent)|Modifie la fenêtre parente.|  
|[CWnd::SetProperty](#setproperty)|Définit une propriété de contrôle ActiveX.|  
|[CWnd::SetRedraw](#setredraw)|Autorise ou empêche le redessinage des modifications dans `CWnd`.|  
|[CWnd::SetScrollInfo](#setscrollinfo)|Définit les informations sur la barre de défilement.|  
|[CWnd::SetScrollPos](#setscrollpos)|Définit la position actuelle d'une case de défilement et, si elle est spécifiée, redessine la barre de défilement en fonction de la nouvelle position.|  
|[CWnd::SetScrollRange](#setscrollrange)|Définit les valeurs de position minimale et maximale de la barre de défilement donnée.|  
|[CWnd::SetTimer](#settimer)|Installe une horloge système qui envoie un [WM_TIMER](#ontimer) au déclenchement de message.|  
|[CWnd::SetWindowContextHelpId](#setwindowcontexthelpid)|Définit l'identificateur de contexte d'aide.|  
|[CWnd::SetWindowPlacement](#setwindowplacement)|Définit l'état d'affichage et les positions normale (restaurée), réduite et agrandie d'une fenêtre.|  
|[CWnd::SetWindowPos](#setwindowpos)|Modifie la taille, la position et l'agencement des fenêtres enfants, indépendantes et de niveau supérieur.|  
|[CWnd::SetWindowRgn](#setwindowrgn)|Définit la région d'une fenêtre.|  
|[CWnd::SetWindowText](#setwindowtext)|Définit le texte de la fenêtre ou le titre de la légende (le cas échéant) avec le texte spécifié.|  
|[CWnd::ShowCaret](#showcaret)|Affiche le caret à l'écran à sa position actuelle. Une fois affiché, le caret se met à clignoter automatiquement.|  
|[CWnd::ShowOwnedPopups](#showownedpopups)|Affiche ou masque toutes les fenêtres indépendantes qui appartiennent à la fenêtre.|  
|[CWnd::ShowScrollBar](#showscrollbar)|Affiche ou masque une barre de défilement.|  
|[CWnd::ShowWindow](#showwindow)|Affiche ou masque la fenêtre.|  
|[CWnd::SubclassDlgItem](#subclassdlgitem)|Attache un contrôle Windows à un objet `CWnd` et fait acheminer les messages via la table des messages de `CWnd`.|  
|[CWnd::SubclassWindow](#subclasswindow)|Attache un fenêtre à un objet `CWnd` et fait acheminer les messages via la table des messages de `CWnd`.|  
|[CWnd::UnlockWindowUpdate](#unlockwindowupdate)|Déverrouille une fenêtre qui était verrouillée avec `CWnd::LockWindowUpdate`.|  
|[CWnd::UnsubclassWindow](#unsubclasswindow)|Détache une fenêtre à partir d’un `CWnd` objet|  
|[CWnd::UpdateData](#updatedata)|Initialise ou récupère les données d'une boîte de dialogue.|  
|[CWnd::UpdateDialogControls](#updatedialogcontrols)|Appelle à mettre à jour l'état de boutons et autres contrôles de boîte de dialogue.|  
|[CWnd::UpdateLayeredWindow](#updatelayeredwindow)|Met à jour la position, la taille, la forme, le contenu et la transparence d'une fenêtre superposée.|  
|[CWnd::UpdateWindow](#updatewindow)|Met à jour la zone cliente.|  
|[CWnd::ValidateRect](#validaterect)|Valide la zone cliente dans le rectangle donné en supprimant le rectangle de la région de mise à jour actuelle.|  
|[CWnd::ValidateRgn](#validatergn)|Valide la zone cliente dans la région donnée en supprimant la région de la région de mise à jour actuelle.|  
|[CWnd::WindowFromPoint](#windowfrompoint)|Identifie la fenêtre qui contient le point donné.|  
|[CWnd::WinHelp](#winhelp)|Appelé pour lancer l'application WinHelp.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CWnd::Default](#default)|Appelle la procédure de fenêtre par défaut, qui assure le traitement par défaut des messages de fenêtre qu'une application ne traite pas.|  
|[CWnd::DefWindowProc](#defwindowproc)|Appelle la procédure de fenêtre par défaut, qui assure le traitement par défaut des messages de fenêtre qu'une application ne traite pas.|  
|[CWnd::DoDataExchange](#dodataexchange)|Pour l’échange et la validation de données de boîte de dialogue. Appelée par `UpdateData`.|  
|[CWnd::GetCurrentMessage](#getcurrentmessage)|Retourne un pointeur vers le message actuellement traité par cette fenêtre. Doit être appelée uniquement lorsque une `On` *Message* fonction membre de gestionnaire de messages.|  
|[CWnd::InitDynamicLayout](#initdynamiclayout)|Appelé par l'infrastructure pour initialiser la disposition dynamique pour la fenêtre.|  
|[CWnd::LoadDynamicLayoutResource](#loaddynamiclayoutresource)|Charge les informations de disposition dynamique à partir du fichier de ressources.|  
|[CWnd::OnActivate](#onactivate)|Appelé pendant l'activation ou la désactivation de `CWnd`.|  
|[CWnd::OnActivateApp](#onactivateapp)|Appelé quand l'application est sur le point d'être activée ou désactivée.|  
|[CWnd::OnAppCommand](#onappcommand)|Appelé quand l'utilisateur génère un événement de commande d'application.|  
|[CWnd::OnAskCbFormatName](#onaskcbformatname)|Appelé par une application de visualisation de Presse-papiers quand un propriétaire de Presse-papiers affiche le contenu du Presse-papiers.|  
|[CWnd::OnCancelMode](#oncancelmode)|Appelé pour permettre à `CWnd` d'annuler les modes internes, tels que la capture de la souris.|  
|[CWnd::OnCaptureChanged](#oncapturechanged)|Envoie un message à la fenêtre qui perd la capture de la souris.|  
|[CWnd::OnChangeCbChain](#onchangecbchain)|Signale qu'une fenêtre spécifiée va être supprimée de la chaîne.|  
|[CWnd::OnChangeUIState](#onchangeuistate)|Appelé quand l'état de l'interface utilisateur (IU) doit être modifié.|  
|[CWnd::OnChar](#onchar)|Appelé quand une séquence de touches est traduite en caractère non système.|  
|[CWnd::OnCharToItem](#onchartoitem)|Appelée par une zone de liste enfant avec la [LBS_WANTKEYBOARDINPUT](list-box-styles.md) style en réponse à une [WM_CHAR](#onchar) message.|  
|[CWnd::OnChildActivate](#onchildactivate)|Appelé pour des fenêtres enfants d'interface multidocument (MDI) chaque fois que la taille ou la position de `CWnd` change ou que `CWnd` est activé.|  
|[CWnd::OnChildNotify](#onchildnotify)|Appelé par une fenêtre parente pour offrir à un contrôle de notification la possibilité de répondre à une notification de contrôle.|  
|[CWnd::OnClipboardUpdate](#onclipboardupdate)|Envoyé quand le contenu du Presse-papiers a changé.|  
|[CWnd::OnClose](#onclose)|Appelé pour signaler que `CWnd` doit être fermé.|  
|[CWnd::OnColorizationColorChanged](#oncolorizationcolorchanged)|Appelé quand la stratégie de rendu de la zone non cliente a changé.|  
|[Fonction membre CWnd::OnCommand](#oncommand)|Appelé quand l'utilisateur sélectionne une commande.|  
|[CWnd::OnCompacting](#oncompacting)|Appelé quand Windows détecte que la mémoire système est insuffisante.|  
|[CWnd::OnCompareItem](#oncompareitem)|Appelé pour déterminer la position relative d'un nouvel élément dans une zone de liste modifiable ou une zone de liste enfant triée en mode owner-draw.|  
|[CWnd::OnCompositionChanged](#oncompositionchanged)|Appelé pour toutes les fenêtres de niveau supérieur quand la composition du Gestionnaire de fenêtrage est activée ou désactivée.|  
|[CWnd::OnContextMenu](#oncontextmenu)|Appelé quand l'utilisateur clique dans la fenêtre avec le bouton droit de la souris.|  
|[CWnd::OnCopyData](#oncopydata)|Copie les données d'une application vers une autre.|  
|[CWnd::OnCreate](#oncreate)|Appelé dans le cadre de la création d'une fenêtre.|  
|[CWnd::OnCtlColor](#onctlcolor)|Appelé si `CWnd` est le parent d'un contrôle qui est sur le point d'être dessiné.|  
|[CWnd::OnDeadChar](#ondeadchar)|Appelé quand une séquence de touches est traduite en caractère de modificateur non système (tel qu'un accent).|  
|[CWnd::OnDeleteItem](#ondeleteitem)|Appelé quand une zone de liste ou une zone de liste modifiable enfant en mode owner-draw est détruite ou que des éléments sont supprimés du contrôle.|  
|[CWnd::OnDestroy](#ondestroy)|Appelé quand `CWnd` va être détruit.|  
|[CWnd::OnDestroyClipboard](#ondestroyclipboard)|Appelé lorsque le Presse-papiers est vidé via un appel à Windows [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) (fonction).|  
|[CWnd::OnDeviceChange](#ondevicechange)|Avertit une application ou un pilote de périphérique que la configuration matérielle d'un périphérique ou de l'ordinateur a été modifiée.|  
|[CWnd::OnDevModeChange](#ondevmodechange)|Appelé pour toutes les fenêtres de niveau supérieur quand l'utilisateur modifie les paramètres de mode de périphérique.|  
|[CWnd::OnDrawClipboard](#ondrawclipboard)|Appelé quand le contenu du Presse-papiers change.|  
|[CWnd::OnDrawItem](#ondrawitem)|Appelé quand un aspect visuel d'un contrôle enfant de bouton, zone de liste modifiable, zone de liste ou menu en mode owner-draw doit être dessiné.|  
|[CWnd::OnDropFiles](#ondropfiles)|Appelé quand l’utilisateur relâche le bouton gauche de la souris dans une fenêtre qui s’est inscrite en tant que destinataire des fichiers déposés.|  
|[CWnd::OnEnable](#onenable)|Appelé quand `CWnd` est activé ou désactivé.|  
|[CWnd::OnEndSession](#onendsession)|Appelé quand la session prend fin.|  
|[CWnd::OnEnterIdle](#onenteridle)|Appelé pour informer la procédure de fenêtre principale d'une application qu'une boîte de dialogue modale ou un menu entre dans un état inactif.|  
|[CWnd::OnEnterMenuLoop](#onentermenuloop)|Appelé lors de l'entrée dans une boucle modale de menu.|  
|[CWnd::OnEnterSizeMove](#onentersizemove)|Appelé après l'entrée de la fenêtre affectée dans une boucle modale de déplacement ou de dimensionnement.|  
|[CWnd::OnEraseBkgnd](#onerasebkgnd)|Appelé quand l'arrière-plan de la fenêtre doit être effacé.|  
|[CWnd::OnExitMenuLoop](#onexitmenuloop)|Appelé lors de la sortie d'une boucle modale de menu.|  
|[CWnd::OnExitSizeMove](#onexitsizemove)|Appelé après la sortie de la fenêtre affectée d'une boucle modale de déplacement ou de dimensionnement.|  
|[CWnd::OnFontChange](#onfontchange)|Appelé quand le pool de ressources de police change.|  
|[CWnd::OnGetDlgCode](#ongetdlgcode)|Appelé pour un contrôle afin de lui permettre de traiter lui-même une entrée de touche de direction et de touche TAB.|  
|[CWnd::OnGetMinMaxInfo](#ongetminmaxinfo)|Appelé chaque fois que Windows a besoin de connaître la position ou les dimensions agrandies ou la taille de suivi minimale ou maximale.|  
|[CWnd::OnHelpInfo](#onhelpinfo)|Appelé par l'infrastructure quand l'utilisateur appuie sur la touche F1.|  
|[CWnd::OnHotKey](#onhotkey)|Appelé quand l'utilisateur appuie sur une touche d'accès rapide à l'échelle du système.|  
|[CWnd::OnHScroll](#onhscroll)|Appelé quand l'utilisateur clique sur la barre de défilement horizontale de `CWnd`.|  
|[CWnd::OnHScrollClipboard](#onhscrollclipboard)|Appelé quand un propriétaire de Presse-papiers doit faire défiler l'image du Presse-papiers, invalider la section appropriée et mettre à jour les valeurs de la barre de défilement.|  
|[CWnd::OnIconEraseBkgnd](#oniconerasebkgnd)|Appelé quand `CWnd` est réduit (sous forme d'icône) et que l'arrière-plan de l'icône doit être rempli avant de peindre l'icône.|  
|[CWnd::OnInitMenu](#oninitmenu)|Appelé quand un menu va devenir actif.|  
|[CWnd::OnInitMenuPopup](#oninitmenupopup)|Appelé quand un menu contextuel va devenir actif.|  
|[CWnd::OnInputDeviceChange](#oninputdevicechange)|Appelé quand un périphérique d'E/S est ajouté ou supprimé du système.|  
|[CWnd::OnInputLangChange](#oninputlangchange)|Appelé après la modification du langage d'entrée d'une application.|  
|[CWnd::OnInputLangChangeRequest](#oninputlangchangerequest)|Appelé quand l'utilisateur choisit un nouveau langage d'entrée.|  
|[CWnd::OnKeyDown](#onkeydown)|Appelé quand l'utilisateur appuie sur une touche non système.|  
|[CWnd::OnKeyUp](#onkeyup)|Appelé quand l’utilisateur relâche une touche non système.|  
|[CWnd::OnKillFocus](#onkillfocus)|Appelé juste avant que `CWnd` perde le focus d'entrée.|  
|[CWnd::OnLButtonDblClk](#onlbuttondblclk)|Appelé quand l'utilisateur double-clique avec le bouton gauche de la souris.|  
|[CWnd::OnLButtonDown](#onlbuttondown)|Appelé quand l'utilisateur appuie sur le bouton gauche de la souris.|  
|[CWnd::OnLButtonUp](#onlbuttonup)|Appelé quand l’utilisateur relâche le bouton gauche de la souris.|  
|[CWnd::OnMButtonDblClk](#onmbuttondblclk)|Appelé quand l'utilisateur double-clique avec le bouton central de la souris.|  
|[CWnd::OnMButtonDown](#onmbuttondown)|Appelé quand l'utilisateur appuie sur le bouton central de la souris.|  
|[CWnd::OnMButtonUp](#onmbuttonup)|Appelé quand l’utilisateur relâche le bouton central de la souris.|  
|[CWnd::OnMDIActivate](#onmdiactivate)|Appelé quand une fenêtre enfant MDI est activée ou désactivée.|  
|[CWnd::OnMeasureItem](#onmeasureitem)|Appelé pour une zone de liste modifiable, une zone de liste ou un élément de menu enfant en mode owner-draw quand le contrôle est créé. `CWnd` communique à Windows les dimensions du contrôle.|  
|[CWnd::OnMenuChar](#onmenuchar)|Appelé quand l'utilisateur appuie sur un caractère mnémonique de menu qui ne correspond à aucun des mnémoniques prédéfinis dans le menu actif.|  
|[CWnd::OnMenuDrag](#onmenudrag)|Appelé quand l'utilisateur commence à faire glisser un élément de menu.|  
|[CWnd::OnMenuGetObject](#onmenugetobject)|Appelé quand le curseur de la souris entre dans un élément de menu ou se déplace du centre de l'élément vers le haut ou le bas de l'élément.|  
|[CWnd::OnMenuRButtonUp](#onmenurbuttonup)|Appelé quand l’utilisateur relâche le bouton droit de la souris et que le curseur se trouve sur un élément de menu.|  
|[CWnd::OnMenuSelect](#onmenuselect)|Appelé quand l'utilisateur sélectionne un élément de menu.|  
|[CWnd::OnMouseActivate](#onmouseactivate)|Appelé quand le curseur se trouve dans une fenêtre inactive et que l'utilisateur appuie sur un bouton de la souris.|  
|[CWnd::OnMouseHover](#onmousehover)|Appelé lorsque le curseur pointe sur la zone cliente de la fenêtre pour la période de temps spécifiée dans un appel antérieur à [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnMouseHWheel](#onmousehwheel)|Appelé quand la fenêtre active est composée par le Gestionnaire de fenêtrage et que cette fenêtre est agrandie.|  
|[CWnd::OnMouseLeave](#onmouseleave)|Appelé lorsque le curseur quitte la zone cliente de la fenêtre spécifiée dans un appel antérieur à [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnMouseMove](#onmousemove)|Appelé quand le curseur de la souris se déplace.|  
|[CWnd::OnMouseWheel](#onmousewheel)|Appelé quand un utilisateur fait tourner la roulette de la souris. Utilise la gestion des messages de Windows NT 4.0.|  
|[CWnd::OnMove](#onmove)|Appelé après un changement de position de `CWnd`.|  
|[CWnd::OnMoving](#onmoving)|Indique qu'un utilisateur déplace un objet `CWnd`.|  
|[CWnd::OnNcActivate](#onncactivate)|Appelé quand la zone non cliente doit être modifiée pour indiquer un état actif ou inactif.|  
|[CWnd::OnNcCalcSize](#onnccalcsize)|Appelé quand la taille et la position de la zone client doivent être calculées.|  
|[CWnd::OnNcCreate](#onnccreate)|Appelé avant [OnCreate](#oncreate) lorsque la zone non cliente est créée.|  
|[CWnd::OnNcDestroy](#onncdestroy)|Appelé quand la zone non cliente va être détruite.|  
|[CWnd::OnNcHitTest](#onnchittest)|Appelé par Windows chaque fois que la souris est déplacée si `CWnd` contient le curseur ou a capturé l'entrée de souris avec `SetCapture`.|  
|[CWnd::OnNcLButtonDblClk](#onnclbuttondblclk)|Appelé quand l'utilisateur double-clique avec le bouton gauche de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcLButtonDown](#onnclbuttondown)|Appelé quand l'utilisateur appuie sur le bouton gauche de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcLButtonUp](#onnclbuttonup)|Appelé quand l'utilisateur relâche le bouton gauche de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcMButtonDblClk](#onncmbuttondblclk)|Appelé quand l'utilisateur double-clique avec le bouton central de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcMButtonDown](#onncmbuttondown)|Appelé quand l'utilisateur appuie sur le bouton central de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcMButtonUp](#onncmbuttonup)|Appelé quand l'utilisateur relâche le bouton central de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcMouseHover](#onncmousehover)|Appelé lorsque le curseur est placé sur la zone non cliente de la fenêtre pour la période de temps spécifiée dans un appel antérieur à [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnNcMouseLeave](#onncmouseleave)|L’infrastructure appelle cette fonction membre lorsque le curseur quitte la zone non cliente de la fenêtre spécifiée dans un appel antérieur à [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnNcMouseMove](#onncmousemove)|Appelé quand le curseur est déplacé dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcPaint](#onncpaint)|Appelé quand la zone non cliente doit être peinte.|  
|[CWnd::OnNcRButtonDblClk](#onncrbuttondblclk)|Appelé quand l'utilisateur double-clique avec le bouton droit de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcRButtonDown](#onncrbuttondown)|Appelé quand l'utilisateur appuie sur le bouton droit de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcRButtonUp](#onncrbuttonup)|Appelé quand l'utilisateur relâche le bouton droit de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcRenderingChanged](#onncrenderingchanged)|Appelé quand la stratégie de rendu de la zone non cliente a changé.|  
|[CWnd::OnNcXButtonDblClk](#onncxbuttondblclk)|Appelé quand l'utilisateur double-clique sur le bouton XBUTTON1 ou XBUTTON2 pendant que le curseur se trouve dans la zone non cliente d'une fenêtre.|  
|[CWnd::OnNcXButtonDown](#onncxbuttondown)|Appelé quand l'utilisateur appuie sur le bouton XBUTTON1 ou XBUTTON2 de la souris pendant que le curseur se trouve dans la zone non cliente d'une fenêtre.|  
|[CWnd::OnNcXButtonUp](#onncxbuttonup)|Appelé quand l’utilisateur relâche le bouton XBUTTON1 ou XBUTTON2 de la souris pendant que le curseur se trouve dans la zone non cliente d’une fenêtre.|  
|[CWnd::OnNextMenu](#onnextmenu)|Appelé quand la touche de direction droite ou gauche est utilisée pour basculer entre la barre de menus et le menu système.|  
|[CWnd::OnNotify](#onnotify)|Appelé par l'infrastructure pour informer une fenêtre parente qu'un événement s'est produit dans l'un de ses contrôles ou que le contrôle a besoin d'informations.|  
|[CWnd::OnNotifyFormat](#onnotifyformat)|Appelé pour déterminer si la fenêtre active accepte les structures ANSI ou Unicode dans le message de notification WM_NOTIFY.|  
|[CWnd::OnPaint](#onpaint)|Appelé pour repeindre une partie de la fenêtre.|  
|[CWnd::OnPaintClipboard](#onpaintclipboard)|Appelé quand la zone cliente de la visionneuse de Presse-papiers doit être repeinte.|  
|[CWnd::OnPaletteChanged](#onpalettechanged)|Appelé pour permettre aux fenêtres qui utilisent une palette de couleurs de réaliser leurs palettes logiques et de mettre à jour leurs zones clientes.|  
|[CWnd::OnPaletteIsChanging](#onpaletteischanging)|Informe les autres applications qu'une application va réaliser sa palette logique.|  
|[Fonction membre CWnd::OnParentNotify](#onparentnotify)|Appelé quand une fenêtre enfant est créée ou détruite ou quand l’utilisateur clique avec un bouton de la souris pendant que le curseur se trouve dans la fenêtre enfant.|  
|[CWnd::OnPowerBroadcast](#onpowerbroadcast)|Appelé quand un événement de gestion de l'alimentation se produit.|  
|[CWnd::OnQueryDragIcon](#onquerydragicon)|Appelé quand un `CWnd` réduit (sous forme d'icône) est sur le point d'être déplacé par l'utilisateur.|  
|[CWnd::OnQueryEndSession](#onqueryendsession)|Appelé quand l'utilisateur choisit de mettre fin à la session Windows.|  
|[CWnd::OnQueryNewPalette](#onquerynewpalette)|Informe `CWnd` qu'il va recevoir le focus d'entrée.|  
|[CWnd::OnQueryOpen](#onqueryopen)|Appelé quand `CWnd` est une icône et que l'utilisateur demande à ce qu'elle soit ouverte.|  
|[CWnd::OnQueryUIState](#onqueryuistate)|Appelé pour récupérer l'état de l'interface utilisateur (IU) pour une fenêtre.|  
|[CWnd::OnRawInput](#onrawinput)|Appelé quand la fenêtre active obtient une entrée brute.|  
|[CWnd::OnRButtonDblClk](#onrbuttondblclk)|Appelé quand l'utilisateur double-clique avec le bouton droit de la souris.|  
|[CWnd::OnRButtonDown](#onrbuttondown)|Appelé quand l'utilisateur appuie sur le bouton droit de la souris.|  
|[CWnd::OnRButtonUp](#onrbuttonup)|Appelé quand l’utilisateur relâche le bouton droit de la souris.|  
|[CWnd::OnRenderAllFormats](#onrenderallformats)|Appelé quand l’application propriétaire va être détruite et qu’elle doit restituer tous ses formats.|  
|[CWnd::OnRenderFormat](#onrenderformat)|Appelé pour le propriétaire du Presse-papiers quand un format particulier avec rendu retardé doit être restitué.|  
|[CWnd::OnSessionChange](#onsessionchange)|Appelé pour avertir une application d'un changement d'état de session.|  
|[CWnd::OnSetCursor](#onsetcursor)|Appelé si l'entrée de la souris n'est pas capturée et que la souris entraîne le déplacement du curseur dans une fenêtre.|  
|[CWnd::OnSetFocus](#onsetfocus)|Appelé après que `CWnd` a obtenu le focus d'entrée.|  
|[CWnd::OnSettingChange](#onsettingchange)|Appelé quand la fonction Win32 `SystemParametersInfo` modifie un paramètre à l'échelle du système.|  
|[CWnd::OnShowWindow](#onshowwindow)|Appelé quand `CWnd` doit être masqué ou affiché.|  
|[CWnd::OnSize](#onsize)|Appelé après que la taille de `CWnd` a changé.|  
|[CWnd::OnSizeClipboard](#onsizeclipboard)|Appelé quand la taille de la zone cliente de la fenêtre de visualisation de Presse-papiers a changé.|  
|[CWnd::OnSizing](#onsizing)|Indique que l'utilisateur redimensionne le rectangle.|  
|[CWnd::OnSpoolerStatus](#onspoolerstatus)|Appelé depuis le Gestionnaire d'impression chaque fois qu'un travail est ajouté ou supprimé dans la fille d'attente du Gestionnaire d'impression.|  
|[CWnd::OnStyleChanged](#onstylechanged)|Indique que le [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) fonction Windows a modifié une ou plusieurs des styles de la fenêtre.|  
|[CWnd::OnStyleChanging](#onstylechanging)|Indique que le [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) fonction Windows est sur le point de changer un ou plusieurs styles de la fenêtre.|  
|[CWnd::OnSysChar](#onsyschar)|Appelé quand une séquence de touches est traduite en caractère système.|  
|[CWnd::OnSysColorChange](#onsyscolorchange)|Appelé pour toutes les fenêtres de niveau supérieur quand une modification est apportée au paramètre de couleur système.|  
|[CWnd::OnSysCommand](#onsyscommand)|Appelé quand l'utilisateur sélectionne une commande dans le menu Système ou qu'il sélectionne le bouton Agrandir ou Réduire.|  
|[CWnd::OnSysDeadChar](#onsysdeadchar)|Appelé quand une séquence de touches est traduite en caractère de modificateur système (tel qu'un accent).|  
|[CWnd::OnSysKeyDown](#onsyskeydown)|Appelé quand l'utilisateur maintient la touche ALT enfoncée, puis qu'il appuie sur une autre touche.|  
|[CWnd::OnSysKeyUp](#onsyskeyup)|Appelé quand l’utilisateur relâche une touche sur laquelle il avait appuyé tout en ayant maintenu la touche ALT enfoncée.|  
|[CWnd::OnTCard](#ontcard)|Appelé quand l'utilisateur clique sur un bouton autorisé.|  
|[CWnd::OnTimeChange](#ontimechange)|Appelé pour toutes les fenêtres de niveau supérieur après un changement d'heure système.|  
|[CWnd::OnTimer](#ontimer)|Appelée après chaque intervalle spécifié dans [SetTimer](#settimer).|  
|[CWnd::OnTouchInput](#ontouchinput)|Traite une entrée unique de l'interface tactile Windows.|  
|[CWnd::OnTouchInputs](#ontouchinputs)|Traite les entrées de l'interface tactile Windows.|  
|[CWnd::OnUniChar](#onunichar)|Appelé quand un utilisateur appuie sur une touche. Autrement dit, la fenêtre en cours a le focus clavier et un [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) message est traduit par le [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) (fonction).|  
|[CWnd::OnUnInitMenuPopup](#onuninitmenupopup)|Appelé quand un menu ou sous-menu déroulant a été détruit.|  
|[CWnd::OnUpdateUIState](#onupdateuistate)|Appelé pour modifier l'état de l'interface utilisateur pour la fenêtre spécifiée et toutes ses fenêtres enfants.|  
|[CWnd::OnUserChanged](#onuserchanged)|Appelé après la connexion ou la déconnexion de l'utilisateur.|  
|[CWnd::OnVKeyToItem](#onvkeytoitem)|Appelée par une zone de liste appartienne `CWnd` en réponse à une [WM_KEYDOWN](#onkeydown) message.|  
|[CWnd::OnVScroll](#onvscroll)|Appelé quand l'utilisateur clique sur la barre de défilement verticale de la fenêtre.|  
|[CWnd::OnVScrollClipboard](#onvscrollclipboard)|Appelé quand le propriétaire doit faire défiler l'image du Presse-papiers, invalider la section appropriée et mettre à jour les valeurs de la barre de défilement.|  
|[CWnd::OnWindowPosChanged](#onwindowposchanged)|Appelé lorsque la taille, position ou ordre de plan est modifiée à la suite d’un appel à [SetWindowPos](#setwindowpos) ou une autre fonction de gestion de fenêtre.|  
|[CWnd::OnWindowPosChanging](#onwindowposchanging)|Appelé lorsque la taille, position ou ordre de plan est sur le point de changer suite à un appel à [SetWindowPos](#setwindowpos) ou une autre fonction de gestion de fenêtre.|  
|[CWnd::OnWinIniChange](#onwininichange)|Appelé pour toutes les fenêtres de niveau supérieur après que le fichier d'initialisation de Windows, WIN. INI, a été modifié.|  
|[CWnd::OnWndMsg](#onwndmsg)|Indique si un message Windows a été traité.|  
|[CWnd::OnXButtonDblClk](#onxbuttondblclk)|Appelé quand l'utilisateur double-clique sur le bouton XBUTTON1 ou XBUTTON2 pendant que le curseur se trouve dans la zone cliente d'une fenêtre.|  
|[CWnd::OnXButtonDown](#onxbuttondown)|Appelé quand l'utilisateur appuie sur le bouton XBUTTON1 ou XBUTTON2 pendant que le curseur se trouve dans la zone cliente d'une fenêtre.|  
|[CWnd::OnXButtonUp](#onxbuttonup)|Appelé quand l’utilisateur relâche le bouton XBUTTON1 ou XBUTTON2 pendant que le curseur se trouve dans la zone cliente d’une fenêtre.|  
|[CWnd::PostNcDestroy](#postncdestroy)|Cette fonction virtuelle est appelée par la valeur par défaut [OnNcDestroy](#onncdestroy) fonction une fois que la fenêtre a été détruite.|  
|[CWnd::ReflectChildNotify](#reflectchildnotify)|Fonction d'assistance qui reflète un message à sa source.|  
|[CWnd::ReflectLastMsg](#reflectlastmsg)|Reflète le dernier message à la fenêtre enfant.|  
|[CWnd::ResizeDynamicLayout](#resizedynamiclayout)|Appelé par l'infrastructure quand la taille de fenêtre change pour ajuster la disposition des fenêtres enfants, si la disposition dynamique est activée pour la fenêtre.|  
|[CWnd::WindowProc](#windowproc)|Fournit une procédure de fenêtre pour un `CWnd`. Par défaut, les messages sont distribués via la table des messages|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWnd::operator HWND](#operator_hwnd)|Appelé pour obtenir un handle de fenêtre.|  
|[CWnd::operator ! =](#operator_neq)|Détermine si une fenêtre n’est pas identique à la fenêtre dont le handle est [m_hWnd](#m_hwnd).|  
|[CWnd::operator ==](#operator_eq_eq)|Détermine si une fenêtre est identique à la fenêtre dont le handle est [m_hWnd](#m_hwnd).|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWnd::m_hWnd](#m_hwnd)|Indique le `HWND` attaché à ce `CWnd`.|  
  
## <a name="remarks"></a>Remarques  
 Un objet `CWnd` est distinct d'une fenêtre Windows, mais les deux sont étroitement liés. Un objet `CWnd` est créé ou détruit par le constructeur et destructeur `CWnd`. La fenêtre Windows, est en revanche, une structure de données interne Windows qui est créé par un **créer** fonction membre et détruit par le `CWnd` destructeur virtuel. Le [DestroyWindow](#destroywindow) fonction détruit la fenêtre Windows sans détruire l’objet.  
  
 Le `CWnd` classe et le mécanisme masquer la **WndProc** (fonction). Les messages entrants de notification de Windows sont automatiquement acheminées via la table des messages pour correct **sur***Message* `CWnd` les fonctions membres. Vous substituez un **sur***Message* fonction membre pour traiter le message particulier d’un membre dans vos classes dérivées.  
  
 La classe `CWnd` vous permet aussi de créer une fenêtre enfant Windows pour votre application. Faites dériver une classe de `CWnd`, puis ajoutez des variables membres à la classe dérivée pour stocker les données propres à votre application. Implémentez des fonctions membres de gestionnaire de messages et une table des messages dans la classe dérivée pour préciser ce qu'il advient quand des messages sont dirigés vers la fenêtre.  
  
 Une fenêtre enfant se crée en deux étapes. Tout d’abord, appelez le constructeur `CWnd` pour construire le `CWnd` de l’objet, puis appelez le [créer](#create) fonction membre pour créer la fenêtre enfant et l’attacher à la `CWnd` objet.  
  
 Quand l'utilisateur ferme votre fenêtre enfant, détruisez l'objet `CWnd` ou appelez la fonction membre `DestroyWindow` pour supprimer la fenêtre et détruire ses structures de données.  
  
 Dans la bibliothèque MFC (Microsoft Foundation Class), d'autres classes sont dérivées de `CWnd` pour fournir des types de fenêtres spécifiques. Nombre de ces classes, y compris [CFrameWnd](../../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md), [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md), [CView](../../mfc/reference/cview-class.md), et [CDialog](../../mfc/reference/cdialog-class.md), sont conçus pour une dérivation supplémentaire. Les classes de contrôle dérivé `CWnd`, tel que [CButton](../../mfc/reference/cbutton-class.md), peut être utilisée directement ou peut être utilisé pour la dérivation de davantage de classes.  
  
 Pour plus d’informations sur l’utilisation de `CWnd`, consultez [fenêtres Frame](../../mfc/frame-windows.md) et [objets fenêtres](../../mfc/window-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWnd`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-nameaccdodefaultactiona--cwndaccdodefaultaction"></a><a name="accdodefaultaction"></a>CWnd::accDoDefaultAction  
 Appelé par l'infrastructure pour effectuer l'action par défaut de l'objet.  
  
```  
virtual HRESULT accDoDefaultAction(VARIANT varChild);
```  
  
### <a name="parameters"></a>Paramètres  
 `varChild`  
 Spécifie si l’action par défaut à appeler est celle de l’objet ou un des éléments enfants de l’objet. Ce paramètre peut être CHILDID_SELF (pour effectuer l’action par défaut de l’objet) ou un ID enfant (pour effectuer l’action par défaut d’un des éléments enfants de l’objet).  
  
### <a name="return-value"></a>Valeur de retour  
 En cas de réussite, un code d’erreur COM en cas d’échec, retourne S_OK. Consultez la page **valeurs de retour** dans [IAccessible::accDoDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318470) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est la partie de MFC [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) prennent en charge.  
  
 Remplacez cette fonction dans votre `CWnd`-dérivée de la classe pour effectuer l’action par défaut de l’objet. Pour plus d’informations, consultez [IAccessible::accDoDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318470) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameacchittesta--cwndacchittest"></a><a name="acchittest"></a>CWnd::accHitTest  
 Appelé par l'infrastructure pour récupérer l'élément enfant ou l'objet enfant à un point déterminé de l'écran.  
  
```  
virtual HRESULT accHitTest(
    long xLeft,  
    long yTop,  
    VARIANT* pvarChild);
```  
  
### <a name="parameters"></a>Paramètres  
 `xLeft`  
 Coordonnée X du point à tester (en unités de l’écran).  
  
 `yTop`  
 Coordonnée Y du point à tester (en unités de l’écran).  
  
 `pvarChild`  
 Reçoit des informations d’identification de l’objet au point spécifié par `xLeft` et `yTop`. Consultez la page *pvarID* dans [IAccessible::accHitTest](http://msdn.microsoft.com/library/windows/desktop/dd318471) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 En cas de réussite, un code d’erreur COM en cas d’échec, retourne S_OK. Consultez la page **valeurs de retour** dans **IAccessible::accHitTest** dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est la partie de MFC [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) prennent en charge.  
  
 Remplacez cette fonction dans votre `CWnd`-classe dérivée si vous disposez des éléments d’interface utilisateur nonwindowed (autres que les contrôles ActiveX sans fenêtre, que MFC gère).  
  
 Pour plus d’informations, consultez [IAccessible::accHitTest](http://msdn.microsoft.com/library/windows/desktop/dd318471) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameacclocationa--cwndacclocation"></a><a name="acclocation"></a>CWnd::accLocation  
 Appelé par l'infrastructure pour récupérer l'emplacement d'affichage actuel de l'objet spécifié.  
  
```  
virtual HRESULT accLocation(
    long* pxLeft,  
    long* pyTop,  
    long* pcxWidth,  
    long* pcyHeight,  
    VARIANT varChild);
```  
  
### <a name="parameters"></a>Paramètres  
 *pxLeft*  
 Reçoit la coordonnée x du coin supérieur gauche de l’objet (en unités de l’écran).  
  
 *pyTop*  
 Reçoit la coordonnée y du coin supérieur gauche de l’objet (en unités de l’écran).  
  
 *pcxWidth*  
 Reçoit la largeur de l’objet (en unités de l’écran).  
  
 *pcyHeight*  
 Reçoit la hauteur de l’objet (en unités de l’écran).  
  
 `varChild`  
 Spécifie si l’emplacement doit être récupéré est celui de l’objet ou un des éléments enfants de l’objet. Ce paramètre peut être CHILDID_SELF (pour obtenir des informations sur l’objet) ou un ID enfant (pour obtenir des informations sur l’élément enfant de l’objet).  
  
### <a name="return-value"></a>Valeur de retour  
 En cas de réussite, un code d’erreur COM en cas d’échec, retourne S_OK. Consultez la page **valeurs de retour** dans **IAccessible::accLocation** dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction dans votre `CWnd`-classe dérivée si vous disposez des éléments d’interface utilisateur nonwindowed (autres que les contrôles ActiveX sans fenêtre, que MFC gère).  
  
 Pour plus d’informations, consultez **IAccessible::accLocation** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameaccnavigatea--cwndaccnavigate"></a><a name="accnavigate"></a>CWnd::accNavigate  
 Appelé par l'infrastructure pour accéder à un autre élément d'interface utilisateur au sein d'un conteneur et, dans la mesure du possible, récupérer l'objet.  
  
```  
virtual HRESULT accNavigate(
    long navDir,  
    VARIANT varStart,  
    VARIANT* pvarEndUpAt);
```  
  
### <a name="parameters"></a>Paramètres  
 `navDir`  
 Spécifie la direction vers laquelle naviguer. Consultez la page `navDir` dans [IAccessible::accNavigate](http://msdn.microsoft.com/library/windows/desktop/dd318473) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `varStart`  
 Spécifie l’objet de départ. Consultez la page `varStart` dans **IAccessible::accNavigate** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *pvarEndUpAt*  
 Reçoit des informations sur l’objet d’interface utilisateur destination. Consultez la page *pvarEnd* dans **IAccessible::accNavigate** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 En cas de réussite, un code d’erreur COM en cas d’échec, retourne S_OK. Consultez la page **valeurs de retour** dans **IAccessible::accNavigate** dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est la partie de MFC [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) prennent en charge.  
  
 Remplacez cette fonction dans votre `CWnd`-classe dérivée si vous disposez des éléments d’interface utilisateur nonwindowed (autres que les contrôles ActiveX sans fenêtre, que MFC gère).  
  
 Pour plus d’informations, consultez [IAccessible::accNavigate](http://msdn.microsoft.com/library/windows/desktop/dd318473) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameaccselecta--cwndaccselect"></a><a name="accselect"></a>CWnd::accSelect  
 Appelé par l'infrastructure pour modifier la sélection ou déplacer le focus clavier de l'objet spécifié.  
  
```  
virtual HRESULT accSelect(
    long flagsSelect,  
    VARIANT varChild);
```  
  
### <a name="parameters"></a>Paramètres  
 `flagsSelect`  
 Indique comment modifier la sélection actuelle ou le focus. Consultez la page `flagsSelect` dans [IAccessible::accSelect](http://msdn.microsoft.com/library/windows/desktop/dd318474) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `varChild`  
 Spécifie l’objet à sélectionner. Ce paramètre peut être CHILDID_SELF (pour sélectionner l’objet lui-même) ou un ID enfant (pour sélectionner un des enfants de l’objet).  
  
### <a name="return-value"></a>Valeur de retour  
 En cas de réussite, un code d’erreur COM en cas d’échec, retourne S_OK. Consultez la page **valeurs de retour** dans **IAccessible::accSelect** dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est la partie de MFC [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) prennent en charge.  
  
 Remplacez cette fonction dans votre `CWnd`-classe dérivée si vous disposez des éléments d’interface utilisateur nonwindowed (autres que les contrôles ActiveX sans fenêtre, que MFC gère).  
  
 Pour plus d’informations, consultez [IAccessible::accSelect](http://msdn.microsoft.com/library/windows/desktop/dd318474) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameanimatewindowa--cwndanimatewindow"></a><a name="animatewindow"></a>CWnd::AnimateWindow  
 Produit des effets spéciaux lors de l’affichage ou masquage de windows.  
  
```  
BOOL AnimateWindow(
    DWORD dwTime,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwTime*  
 Spécifie la durée de lecture de l’animation, en millisecondes. En règle générale, une animation prend 200 millisecondes à lire.  
  
 `dwFlags`  
 Spécifie le type d’animation. Pour obtenir une liste complète des valeurs possibles, consultez la page [AnimateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632669).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre émule les fonctionnalités de la fonction [AnimateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632669), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namearrangeiconicwindowsa--cwndarrangeiconicwindows"></a><a name="arrangeiconicwindows"></a>CWnd::ArrangeIconicWindows  
 Réorganise toutes les fenêtres enfants réduites (sous forme d'icônes).  
  
```  
UINT ArrangeIconicWindows();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur d’une ligne d’icônes si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre organise également les icônes dans la fenêtre du bureau, ce qui occupe tout l’écran. Le [GetDesktopWindow](#getdesktopwindow) fonction membre récupère un pointeur vers l’objet de la fenêtre du bureau.  
  
 Pour réorganiser les fenêtres MDI enfants sous forme d’icône dans une fenêtre du client MDI, appelez [CMDIFrameWnd::MDIIconArrange](../../mfc/reference/cmdiframewnd-class.md#mdiiconarrange).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#66;](../../mfc/reference/codesnippet/cpp/cwnd-class_1.cpp)]  
  
##  <a name="a-nameattacha--cwndattach"></a><a name="attach"></a>CWnd::Attach  
 Attache une fenêtre Windows à un `CWnd` objet.  
  
```  
BOOL Attach(HWND hWndNew);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWndNew`  
 Spécifie un handle à une fenêtre Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
 Cet exemple montre comment utiliser attacher et détacher pour mapper à la fenêtre du client MDI.  
  
 [!code-cpp[NVC_MFCWindowing&#67;](../../mfc/reference/codesnippet/cpp/cwnd-class_2.h)]  
  
 [!code-cpp[NVC_MFCWindowing&#68;](../../mfc/reference/codesnippet/cpp/cwnd-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#69;](../../mfc/reference/codesnippet/cpp/cwnd-class_4.cpp)]  
  
##  <a name="a-namebeginmodalstatea--cwndbeginmodalstate"></a><a name="beginmodalstate"></a>CWnd::BeginModalState  
 Appelez cette fonction membre pour rendre modale une fenêtre frame.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="a-namebeginpainta--cwndbeginpaint"></a><a name="beginpaint"></a>CWnd::BeginPaint  
 Prépare `CWnd` pour la peinture et remplit une `PAINTSTRUCT` structure de données avec des informations sur la peinture.  
  
```  
CDC* BeginPaint(LPPAINTSTRUCT lpPaint);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpPaint`  
 Pointe vers le [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) structure qui doit recevoir les informations de peinture.  
  
### <a name="return-value"></a>Valeur de retour  
 Identifie le contexte de périphérique pour `CWnd`. Le pointeur peut être temporaire et ne doivent pas être stocké dépasse le cadre de [EndPaint](#endpaint).  
  
### <a name="remarks"></a>Remarques  
 La structure de peinture contient une structure de données RECT qui a le plus petit rectangle qui englobe complètement la zone de mise à jour et un indicateur qui spécifie si l’arrière-plan a été effacé.  
  
 La région de mise à jour est définie par le [Invalidate](#invalidate), [InvalidateRect](#invalidaterect), ou [InvalidateRgn](#invalidatergn) les fonctions membres et par le système après sa taille, se déplace, crée, fait défiler ou effectue toute autre opération qui a une incidence sur la zone cliente. Si la région de mise à jour est marquée pour suppression, `BeginPaint` envoie un [WM_ONERASEBKGND](#onerasebkgnd) message.  
  
 N’appelez pas la `BeginPaint` fonction membre sauf en réponse à une [WM_PAINT](#onpaint) message. Chaque appel à la `BeginPaint` fonction membre doit avoir un appel correspondant à la [EndPaint](#endpaint) fonction membre. Si le point d’insertion se trouve dans la zone à peindre, le `BeginPaint` fonction membre masque automatiquement le signe insertion pour l’empêcher d’être effacé.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#70;](../../mfc/reference/codesnippet/cpp/cwnd-class_5.cpp)]  
  
##  <a name="a-namebinddefaultpropertya--cwndbinddefaultproperty"></a><a name="binddefaultproperty"></a>CWnd::BindDefaultProperty  
 Lie par défaut simple propriété liée l’objet appelant (par exemple, un contrôle d’édition), sélectionnée dans la bibliothèque de types, le curseur sous-jacent qui est défini par les propriétés de la source de données, nom d’utilisateur, mot de passe et SQL du contrôle de source de données.  
  
```  
void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwDispID`  
 Spécifie le DISPID d’une propriété sur un contrôle lié aux données qui doit être lié à un contrôle de source de données.  
  
 `vtProp`  
 Spécifie le type de la propriété à lier, par exemple, `VT_BSTR`, **VT_VARIANT**, et ainsi de suite.  
  
 `szFieldName`  
 Spécifie le nom de la colonne du curseur fournie par le contrôle de source de données auquel la propriété va être liée.  
  
 `pDSCWnd`  
 Pointe vers la fenêtre contrôle héberge la source de données auquel la propriété va être liée. Appelez `GetDlgItem` avec l’ID de ressource de la fenêtre de l’hôte de contrôleurs de domaine pour récupérer ce pointeur.  
  
### <a name="remarks"></a>Notes  
 Le `CWnd` objet sur lequel vous appelez cette fonction doit être un contrôle lié aux données.  
  
### <a name="example"></a>Exemple  
 `BindDefaultProperty`peut être utilisé dans le contexte suivant :  
  
 [!code-cpp[NVC_MFC_AxDataBinding n °&1;](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding n °&2;](../../mfc/reference/codesnippet/cpp/cwnd-class_7.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding n °&3;](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="a-namebindpropertya--cwndbindproperty"></a><a name="bindproperty"></a>CWnd::BindProperty  
 Lie une propriété liée à du curseur sur un contrôle lié aux données (par exemple, un contrôle de grille) à un contrôle de source de données et enregistre cette relation avec le Gestionnaire de liaisons de MFC.  
  
```  
void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwDispId*  
 Spécifie le DISPID d’une propriété sur un contrôle lié aux données qui doit être lié à un contrôle de source de données.  
  
 `pWndDSC`  
 Pointe vers la fenêtre contrôle héberge la source de données auquel la propriété va être liée. Appelez `GetDlgItem` avec l’ID de ressource de la fenêtre de l’hôte de contrôleurs de domaine pour récupérer ce pointeur.  
  
### <a name="remarks"></a>Notes  
 Le `CWnd` objet sur lequel vous appelez cette fonction doit être un contrôle lié aux données.  
  
### <a name="example"></a>Exemple  
 `BindProperty`peut être utilisé dans le contexte suivant :  
  
 [!code-cpp[NVC_MFC_AxDataBinding n °&1;](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding n °&4;](../../mfc/reference/codesnippet/cpp/cwnd-class_9.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding n °&3;](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="a-namebringwindowtotopa--cwndbringwindowtotop"></a><a name="bringwindowtotop"></a>CWnd::BringWindowToTop  
 Place `CWnd` en haut d'une pile de fenêtres superposées.  
  
```  
void BringWindowToTop();
```  
  
### <a name="remarks"></a>Remarques  
 En outre, `BringWindowToTop` active les fenêtres contextuelles, les fenêtres de niveau supérieur et les fenêtres enfants MDI. La fonction membre `BringWindowToTop` doit être utilisée pour déterminer les fenêtres qui sont partiellement ou totalement masquées par d'autres fenêtres.  
  
 Cette fonction appelle simplement Win32 [BringWindowToTop](http://msdn.microsoft.com/library/windows/desktop/ms632673\(v=vs.85\).aspx) (fonction). Appelez le [SetWindowPos](#setwindowpos) (fonction) pour modifier la position d’une fenêtre dans l’ordre de plan. La fonction `BringWindowToTop` ne modifie pas le style de la fenêtre pour en faire une fenêtre de niveau supérieur. Pour plus d’informations, consultez [quelle est la différence entre HWND_TOP and HWND_TOPMOST](http://blogs.msdn.com/b/oldnewthing/archive/2005/11/21/495246.aspx)  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#71;](../../mfc/reference/codesnippet/cpp/cwnd-class_10.cpp)]  
  
##  <a name="a-namecalcwindowrecta--cwndcalcwindowrect"></a><a name="calcwindowrect"></a>CWnd::CalcWindowRect  
 Calcule le rectangle de la fenêtre contenant le rectangle client spécifié.  
  
```  
virtual void CalcWindowRect(
    LPRECT lpClientRect,  
    UINT nAdjustType = adjustBorder);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `lpClientRect`  
 Pointeur vers une structure de rectangle. En entrée, cette structure contient le rectangle client. Une fois la méthode terminée, cette structure contient le rectangle de la fenêtre contenant le rectangle client spécifié.  
  
 [in] `nAdjustType`  
 Utilisez `CWnd::adjustBorder` pour calculer les coordonnées de fenêtre sans la `WS_EX_CLIENTEDGE` de style ; sinon, utilisez `CWnd::adjustOutside`.  
  
### <a name="remarks"></a>Remarques  
 La taille du rectangle de la fenêtre calculé n’inclut pas d’espace pour une barre de menus.  
  
 Pour plus de restrictions d’utilisation, consultez la page [AdjustWindowRectEx](http://msdn.microsoft.com/library/windows/desktop/ms632667).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#72;](../../mfc/reference/codesnippet/cpp/cwnd-class_11.cpp)]  
  
##  <a name="a-namecanceltooltipsa--cwndcanceltooltips"></a><a name="canceltooltips"></a>CWnd::CancelToolTips  
 Appelez cette fonction membre pour supprimer une info-bulle de l’écran si une info-bulle est affichée.  
  
```  
static void PASCAL CancelToolTips(BOOL bKeys = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 *bKeys*  
 **TRUE** annuler des info-bulles lorsqu’une touche est enfoncée et le texte de la barre d’état la valeur par défaut ; sinon **FALSE**.  
  
### <a name="remarks"></a>Notes  
  
> [!NOTE]
>  À l’aide de cette fonction membre n’a aucun effet sur les info-bulles gérés par votre code. Elle n’affecte que le contrôle d’info-bulle géré par [CWnd::EnableToolTips](#enabletooltips).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#73;](../../mfc/reference/codesnippet/cpp/cwnd-class_12.cpp)]  
  
##  <a name="a-namecenterwindowa--cwndcenterwindow"></a><a name="centerwindow"></a>CWnd::CenterWindow  
 Centre une fenêtre par rapport à son parent.  
  
```  
void CenterWindow(CWnd* pAlternateOwner = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pAlternateOwner`  
 Pointeur vers une autre fenêtre par rapport à laquelle il sera centré (autres que la fenêtre parente).  
  
### <a name="remarks"></a>Remarques  
 Généralement appelées à partir de [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) aux boîtes de dialogue Centre par rapport à la fenêtre principale de l’application. Par défaut, la fonction centres de fenêtres enfants par rapport à leur fenêtre parente et des fenêtres publicitaires intempestives par rapport à leur propriétaire. Si la fenêtre contextuelle n’est pas détenue, il est centré par rapport à l’écran. Pour centrer une fenêtre par rapport à une fenêtre spécifique qui n’est pas le propriétaire ou un parent, le `pAlternateOwner` paramètre peut être défini sur une fenêtre valide. Pour forcer le centrage par rapport à l’écran, passez la valeur retournée par [CWnd::GetDesktopWindow](#getdesktopwindow) comme `pAlternateOwner`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#74;](../../mfc/reference/codesnippet/cpp/cwnd-class_13.cpp)]  
  
##  <a name="a-namechangeclipboardchaina--cwndchangeclipboardchain"></a><a name="changeclipboardchain"></a>CWnd::ChangeClipboardChain  
 Supprime `CWnd` à partir de la chaîne de visionneuses de Presse-papiers et rend la fenêtre spécifiée par `hWndNext` le descendant du `CWnd` ancêtre dans la chaîne.  
  
```  
BOOL ChangeClipboardChain(HWND hWndNext);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWndNext`  
 Identifie la fenêtre suit `CWnd` dans la chaîne de gestionnaire de l’album.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
##  <a name="a-namecheckdlgbuttona--cwndcheckdlgbutton"></a><a name="checkdlgbutton"></a>CWnd::CheckDlgButton  
 (Place une coche à côté) ou désactive (supprime une case à cocher à partir de) un bouton, ou il modifie l’état d’un bouton à trois états.  
  
```  
void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDButton`  
 Spécifie le bouton à modifier.  
  
 `nCheck`  
 Spécifie l’action à entreprendre. Si `nCheck` est différent de zéro, le `CheckDlgButton` fonction membre place une coche en regard du bouton, la valeur 0, la case à cocher est supprimée. Pour les boutons de trois états, si `nCheck` est 2, l’état est indéterminé.  
  
### <a name="remarks"></a>Remarques  
 Le `CheckDlgButton` fonction envoie une [BM_SETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775989) message pour le bouton spécifié.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#75;](../../mfc/reference/codesnippet/cpp/cwnd-class_14.cpp)]  
  
##  <a name="a-namecheckradiobuttona--cwndcheckradiobutton"></a><a name="checkradiobutton"></a>CWnd::CheckRadioButton  
 Sélectionne (ajoute une coche à) une case d’option donné dans un groupe et efface (supprime une coche) toutes les autres cases d’option dans le groupe.  
  
```  
void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDFirstButton`  
 Spécifie l’identificateur entier de la première case dans le groupe.  
  
 `nIDLastButton`  
 Spécifie l’identificateur entier de la dernière case dans le groupe.  
  
 `nIDCheckButton`  
 Spécifie l’identificateur entier de la case d’option à vérifier.  
  
### <a name="remarks"></a>Remarques  
 Le `CheckRadioButton` fonction envoie une [BM_SETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775989) message vers le bouton radio spécifié.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#76;](../../mfc/reference/codesnippet/cpp/cwnd-class_15.cpp)]  
  
##  <a name="a-namechildwindowfrompointa--cwndchildwindowfrompoint"></a><a name="childwindowfrompoint"></a>CWnd::ChildWindowFromPoint  
 Détermine le cas échéant, des fenêtres enfants qui appartiennent à `CWnd` contient le point spécifié.  
  
```  
CWnd* ChildWindowFromPoint(POINT point) const;  
  
CWnd* ChildWindowFromPoint(
    POINT point,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Spécifie les coordonnées du client du point à tester.  
  
 *nIndicateurs*  
 Spécifie les fenêtres enfants à ignorer. Ce paramètre peut être une combinaison des valeurs suivantes :  
  
|Valeur|Signification|  
|-----------|-------------|  
|**CWP_ALL**|N’ignorez pas toutes les fenêtres enfants|  
|**CWP_SKIPINVISIBLE**|Ignorer les fenêtres enfants invisibles|  
|**CWP_SKIPDISABLED**|Ignorer les fenêtres enfants désactivées|  
|**CWP_SKIPTRANSPARENT**|Ignorer les fenêtres enfants transparentes|  
  
### <a name="return-value"></a>Valeur de retour  
 Identifie la fenêtre enfant qui contient le point. Il est **NULL** si le point donné se trouve en dehors de la zone cliente. Si le point se trouve dans la zone cliente, mais n’est pas contenu dans n’importe quelle fenêtre enfant, `CWnd` est retourné.  
  
 Cette fonction membre retourne une fenêtre enfant masqués ou désactivés qui contient le point spécifié.  
  
 Plus d’une fenêtre peut contenir du point donné. Toutefois, cette fonction retourne uniquement le `CWnd`* de la première fenêtre rencontrée qui contient le point.  
  
 Le `CWnd`* qui est retourné peut être temporaire et ne doivent pas être stockées pour une utilisation ultérieure.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#77;](../../mfc/reference/codesnippet/cpp/cwnd-class_16.cpp)]  
  
##  <a name="a-nameclienttoscreena--cwndclienttoscreen"></a><a name="clienttoscreen"></a>CWnd::ClientToScreen  
 Convertit les coordonnées clientes d'un point ou rectangle donné affiché en coordonnées d'écran.  
  
```  
void ClientToScreen(LPPOINT lpPoint) const;  void ClientToScreen(LPRECT lpRect) const;  ```  
  
### Parameters  
 `lpPoint`  
 Points to a [POINT structure](../../mfc/reference/point-structure1.md) or `CPoint` object that contains the client coordinates to be converted.  
  
 `lpRect`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) or `CRect` object that contains the client coordinates to be converted.  
  
### Remarks  
 The `ClientToScreen` member function uses the client coordinates in the **POINT** or `RECT` structure or the `CPoint` or `CRect` object pointed to by `lpPoint` or `lpRect` to compute new screen coordinates; it then replaces the coordinates in the structure with the new coordinates. The new screen coordinates are relative to the upper-left corner of the system display.  
  
 The `ClientToScreen` member function assumes that the given point or rectangle is in client coordinates.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#78](../../mfc/reference/codesnippet/cpp/cwnd-class_17.cpp)]  
  
##  <a name="closewindow"></a>  CWnd::CloseWindow  
 Minimizes the window.  
  
```  
void CloseWindow() ;
```  
  
### Remarks  
 This member function emulates the functionality of the function [CloseWindow](http://msdn.microsoft.com/library/windows/desktop/ms632678), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="continuemodal"></a>  CWnd::ContinueModal  
 This member function is called by [RunModalLoop](#runmodalloop) to determine when the modal state should be exited.  
  
```  
virtuel BOOL ContinueModal() ;
```  
  
### Return Value  
 Nonzero if modal loop is to be continued; 0 when [EndModalLoop](#endmodalloop) is called.  
  
### Remarks  
 By default, it returns non-zero until `EndModalLoop` is called.  
  
##  <a name="create"></a>  CWnd::Create  
 Creates the specified child window and attaches it to the [CWnd](../../mfc/reference/cwnd-class.md) object.  
  
```  
virtuel BOOL créer (lpszClassName LPCTSTR,  
    LpszWindowName LPCTSTR,  
    DWORD dwStyle,  
    RECT const se rect,  
    CWnd* pParentWnd, nID UINT, CCreateContext* pContext = NULL) ;
```  
  
### Parameters  
 [in] `lpszClassName`  
 Pointer to a null-terminated string that contains the name of a registered system window class; or the name of a predefined system window class.  
  
 [in] `lpszWindowName`  
 Pointer to a null-terminated string that contains the window display name; otherwise `NULL` for no window display name.  
  
 [in] `dwStyle`  
 Bitwise combination (OR) of [window styles](../../mfc/reference/window-styles.md). The `WS_POPUP` option is not a valid style.  
  
 [in] `rect`  
 The size and location of the window relative to the top-left corner of the parent window.  
  
 [in] `pParentWnd`  
 Pointer to the parent window.  
  
 [in] `nID`  
 ID of the window.  
  
 [in] `pContext`  
 Pointer to a [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) structure that is used to customize the document-view architecture for the application.  
  
### Return Value  
 `TRUE` if the method was successful; otherwise `FALSE`.  
  
### Remarks  
  
> [!WARNING]
> `CWnd::PreCreateWindow` now assigns the hMenu member of its `CREATESTRUCT` parameter to the `this` pointer if the menu is `NULL` and the style contains `WS_CHILD`. For proper functionality, ensure that your dialog control has an ID that is not `NULL`.  
>   
>  This change fixes a crash in managed/native interop scenarios. A `TRACE` statement in `CWnd::Create` alerts the developer of the problem.  
  
 Use the [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) function to register window classes. User defined window classes are available in the module where they are registered.  
  
 The [CWnd::OnCreate](#oncreate) method is called before the `Create` method returns, and before the window becomes visible.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#79](../../mfc/reference/codesnippet/cpp/cwnd-class_18.cpp)]  
  
##  <a name="createaccessibleproxy"></a>  CWnd::CreateAccessibleProxy  
 Creates an Active Accessibility proxy for the specified object.  
  
```  
virtuel HRESULT CreateAccessibleProxy (WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult) ;
```  
  
### Parameters  
 `wParam`  
 Identifies the object accessed by the Active Accessibility proxy. Can be one of the following values  
  
|Value|Meaning|  
|-----------|-------------|  
|**OBJID_CLIENT**|Refers to the window's client area.|  
  
 `lParam`  
 Provides additional message-dependent information.  
  
 `pResult`  
 A pointer to an **LRESULT** that stores the result code.  
  
### Remarks  
 Creates an Active Accessibility proxy for the specified object.  
  
##  <a name="createcaret"></a>  CWnd::CreateCaret  
 Creates a new shape for the system caret and claims ownership of the caret.  
  
```  
void CreateCaret (CBitmap * pBitmap) ;
```  
  
### Parameters  
 `pBitmap`  
 Identifies the bitmap that defines the caret shape.  
  
### Remarks  
 The bitmap must have previously been created by the [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap) member function, the [CreateDIBitmap](http://msdn.microsoft.com/library/windows/desktop/dd183491) Windows function, or the [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap) member function.  
  
 `CreateCaret` automatically destroys the previous caret shape, if any, regardless of which window owns the caret. Once created, the caret is initially hidden. To show the caret, the [ShowCaret](#showcaret) member function must be called.  
  
 The system caret is a shared resource. `CWnd` should create a caret only when it has the input focus or is active. It should destroy the caret before it loses the input focus or becomes inactive.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#80](../../mfc/reference/codesnippet/cpp/cwnd-class_19.cpp)]  
  
##  <a name="createcontrol"></a>  CWnd::CreateControl  
 Use this member function to create an ActiveX control that will be represented in the MFC program by a `CWnd` object.  
  
```  
CreateControl BOOL (LPCTSTR pszClass,  
    LPCTSTR pszWindowName,  
    DWORD dwStyle,  
    RECT const se rect,  
    CWnd* pParentWnd, nID UINT, CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL) ;

 
CreateControl BOOL (clsid REFCLSID,  
    LPCTSTR pszWindowName,  
    DWORD dwStyle,  
    RECT const se rect,  
    CWnd* pParentWnd, nID UINT, CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL) ;

 
CreateControl BOOL (clsid REFCLSID,  
    LPCTSTR pszWindowName,  
    DWORD dwStyle,  
    POINT const* ppt, taille const* psize,  
    CWnd* pParentWnd, nID UINT, CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL) ;
```  
  
### Parameters  
 *pszClass*  
 This string may contain the OLE "short name" (ProgID) for the class, e.g., "CIRC3.Circ3Ctrl.1". The name needs to match the same name registered by the control. Alternatively, the string may contain the string form of a **CLSID**, contained in braces, e.g., "{9DBAFCCF-592F-101B-85CE-00608CEC297B}". In either case, `CreateControl` converts the string to the corresponding class ID.  
  
 *pszWindowName*  
 A pointer to the text to be displayed in the control. Sets the value of the control's Caption or Text property (if any). If **NULL**, the control's Caption or Text property is not changed.  
  
 `dwStyle`  
 Windows styles. The available styles are listed under Remarks.  
  
 `rect`  
 Specifies the control's size and position. It can be either a [CRect](../../atl-mfc-shared/reference/crect-class.md) object or a [RECT structure](../../mfc/reference/rect-structure1.md).  
  
 `ppt`  
 Points to a [POINT structure](../../mfc/reference/point-structure1.md) or `CPoint` object that contains the upper left corner of the control.  
  
 `pSize`  
 Points to a [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure or `CSize` object that contains the control's size  
  
 `pParentWnd`  
 Specifies the control's parent window. It must not be **NULL**.  
  
 `nID`  
 Specifies the control's ID.  
  
 `pPersist`  
 A pointer to a [CFile](../../mfc/reference/cfile-class.md) containing the persistent state for the control. The default value is **NULL**, indicating that the control initializes itself without restoring its state from any persistent storage. If not **NULL**, it should be a pointer to a `CFile`-derived object which contains the control's persistent data, in the form of either a stream or a storage. This data could have been saved in a previous activation of the client. The `CFile` can contain other data, but must have its read-write pointer set to the first byte of persistent data at the time of the call to `CreateControl`.  
  
 `bStorage`  
 Indicates whether the data in `pPersist` should be interpreted as IStorage or IStream data. If the data in `pPersist` is a storage, `bStorage` should be **TRUE**. If the data in `pPersist` is a stream, `bStorage` should be **FALSE**. The default value is **FALSE**.  
  
 *bstrLicKe*y  
 Optional license key data. This data is needed only for creating controls that require a run-time license key. If the control supports licensing, you must provide a license key for the creation of the control to succeed. The default value is **NULL**.  
  
 `clsid`  
 The unique class ID of the control.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 `CreateControl` is a direct analog of the [CWnd::Create](#create) function, which creates the window for a `CWnd`. `CreateControl` creates an ActiveX control instead of an ordinary window.  
  
 Only a subset of the Windows `dwStyle` flags are supported for `CreateControl`:  
  
- **WS_VISIBLE** Creates a window that is initially visible. Required if you want the control to be visible immediately, like ordinary windows.  
  
- **WS_DISABLED** Creates a window that is initially disabled. A disabled window cannot receive input from the user. Can be set if the control has an Enabled property.  
  
- `WS_BORDER` Creates a window with a thin-line border. Can be set if control has a BorderStyle property.  
  
- **WS_GROUP** Specifies the first control of a group of controls. The user can change the keyboard focus from one control in the group to the next by using the direction keys. All controls defined with the **WS_GROUP** style after the first control belong to the same group. The next control with the **WS_GROUP** style ends the group and starts the next group.  
  
- **WS_TABSTOP** Specifies a control that can receive the keyboard focus when the user presses the TAB key. Pressing the TAB key changes the keyboard focus to the next control of the **WS_TABSTOP** style.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#81](../../mfc/reference/codesnippet/cpp/cwnd-class_20.h)]  
  
##  <a name="createex"></a>  CWnd::CreateEx  
 Creates the specified window and attaches it to the `CWnd` object.  
  
```  
virtuel BOOL CreateEx (DWORD dwExStyle,  
    LpszClassName LPCTSTR,  
    LpszWindowName LPCTSTR,  
    DWORD dwStyle,  
    int x,  
    int y,  
    int nWidth,  
    nHeight int,  
    HWndParent HWND,  
    HMENU nIDorHMenu,  
    LPVOID lpParam = NULL) ;

 
virtuel BOOL CreateEx (DWORD dwExStyle,  
    LpszClassName LPCTSTR,  
    LpszWindowName LPCTSTR,  
    DWORD dwStyle,  
    RECT const se rect,  
    CWnd * pParentWnd,  
    UINT nID,  
    LPVOID lpParam = NULL) ;
```  
  
### Parameters  
 `dwExStyle`  
 Bitwise combination (OR) of [extended window styles](../../mfc/reference/extended-window-styles.md); otherwise `NULL` for the default extended window style.  
  
 `lpszClassName`  
 Pointer to a null-terminated string that contains the name of a registered system window class; or the name of a predefined system window class.  
  
 `lpszWindowName`  
 Pointer to a null-terminated string that contains the window display name; otherwise `NULL` for no window display name.  
  
 `dwStyle`  
 Bitwise combination (OR) of [window styles](../../mfc/reference/window-styles.md); otherwise `NULL` for the default window style.  
  
 `x`  
 The initial horizontal distance of the window from the left side of the screen or the parent window.  
  
 `y`  
 The initial vertical distance of the window from the top of the screen or the parent window.  
  
 `nWidth`  
 The width, in pixels, of the window.  
  
 `nHeight`  
 The height, in pixels, of the window.  
  
 `hwndParent`  
 For a child window, the handle to the parent window; otherwise, the handle of the owner window if the window has an owner.  
  
 `nIDorHMenu`  
 For a child window, the window ID; otherwise, the ID of a menu for the window.  
  
 `lpParam`  
 Pointer to user data that is passed to the [CWnd::OnCreate](#oncreate) method in the `lpCreateParams` field.  
  
 `rect`  
 The size and location of the window relative to the screen or the parent window.  
  
 `pParentWnd`  
 For a child window, pointer to the parent window; otherwise, pointer to the owner window if the window has an owner.  
  
 `nID`  
 For a child window, the window ID; otherwise, the ID of a menu for the window.  
  
### Return Value  
 `TRUE` if the method was successful; otherwise `FALSE`.  
  
### Remarks  
  
> [!WARNING]
> `CWnd::PreCreateWindow` now assigns the hMenu member of its `CREATESTRUCT` parameter to the `this` pointer if the menu is `NULL` and the style contains `WS_CHILD`. For proper functionality, ensure that your dialog control has an ID that is not `NULL`.  
>   
>  This change fixes a crash in managed/native interop scenarios. A `TRACE` statement in `CWnd::Create` alerts the developer of the problem.  
  
 The default extended window style is `WS_EX_LEFT`. The default window style is `WS_OVERLAPPED`.  
  
 Use the [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) function to register window classes. User defined window classes are available in the module where they are registered.  
  
 Dimensions for child windows are relative to the top-left corner of the client area of the parent window. Dimensions for top-level windows are relative to the top-left corner of the screen.  
  
 The [CWnd::OnCreate](#oncreate) method is called before the `CreateEx` method returns, and before the window becomes visible.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#82](../../mfc/reference/codesnippet/cpp/cwnd-class_21.cpp)]  
  
##  <a name="creategraycaret"></a>  CWnd::CreateGrayCaret  
 Creates a gray rectangle for the system caret and claims ownership of the caret.  
  
```  
void CreateGrayCaret (int nWidth,  
    nHeight int) ;
```  
  
### Parameters  
 `nWidth`  
 Specifies the width of the caret (in logical units). If this parameter is 0, the width is set to the system-defined window-border width.  
  
 `nHeight`  
 Specifies the height of the caret (in logical units). If this parameter is 0, the height is set to the system-defined window-border height.  
  
### Remarks  
 The caret shape can be a line or a block.  
  
 The parameters `nWidth` and `nHeight` specify the caret's width and height (in logical units); the exact width and height (in pixels) depend on the mapping mode.  
  
 The system's window-border width or height can be retrieved by the [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) Windows function with the **SM_CXBORDER** and **SM_CYBORDER** indexes. Using the window-border width or height ensures that the caret will be visible on a high-resolution display.  
  
 The `CreateGrayCaret` member function automatically destroys the previous caret shape, if any, regardless of which window owns the caret. Once created, the caret is initially hidden. To show the caret, the [ShowCaret](#showcaret) member function must be called.  
  
 The system caret is a shared resource. `CWnd` should create a caret only when it has the input focus or is active. It should destroy the caret before it loses the input focus or becomes inactive.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#83](../../mfc/reference/codesnippet/cpp/cwnd-class_22.cpp)]  
  
##  <a name="createsolidcaret"></a>  CWnd::CreateSolidCaret  
 Creates a solid rectangle for the system caret and claims ownership of the caret.  
  
```  
void CreateSolidCaret (int nWidth,  
    nHeight int) ;
```  
  
### Parameters  
 `nWidth`  
 Specifies the width of the caret (in logical units). If this parameter is 0, the width is set to the system-defined window-border width.  
  
 `nHeight`  
 Specifies the height of the caret (in logical units). If this parameter is 0, the height is set to the system-defined window-border height.  
  
### Remarks  
 The caret shape can be a line or block.  
  
 The parameters `nWidth` and `nHeight` specify the caret's width and height (in logical units); the exact width and height (in pixels) depend on the mapping mode.  
  
 The system's window-border width or height can be retrieved by the [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) Windows function with the **SM_CXBORDER** and **SM_CYBORDER** indexes. Using the window-border width or height ensures that the caret will be visible on a high-resolution display.  
  
 The `CreateSolidCaret` member function automatically destroys the previous caret shape, if any, regardless of which window owns the caret. Once created, the caret is initially hidden. To show the caret, the [ShowCaret](#showcaret) member function must be called.  
  
 The system caret is a shared resource. `CWnd` should create a caret only when it has the input focus or is active. It should destroy the caret before it loses the input focus or becomes inactive.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#84](../../mfc/reference/codesnippet/cpp/cwnd-class_23.cpp)]  
  
##  <a name="cwnd"></a>  CWnd::CWnd  
 Constructs a `CWnd` object.  
  
```  
CWnd() ;
```  
  
### Remarks  
 The Windows window is not created and attached until the [CreateEx](#createex) or [Create](#create) member function is called.  
  
##  <a name="default"></a>  CWnd::Default  
 Calls the default window procedure.  
  
```  
() Par défaut LRESULT ;
```  
  
### Return Value  
 Depends on the message sent.  
  
### Remarks  
 The default window procedure provides default processing for any window message that an application does not process. This member function ensures that every message is processed.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#85](../../mfc/reference/codesnippet/cpp/cwnd-class_24.cpp)]  
  
##  <a name="defwindowproc"></a>  CWnd::DefWindowProc  
 Calls the default window procedure, which provides default processing for any window message that an application does not process.  
  
```  
virtuel LRESULT DefWindowProc (UINT message,  
    WPARAM wParam,  
    LPARAM lParam) ;
```  
  
### Parameters  
 `message`  
 Specifies the Windows message to be processed.  
  
 `wParam`  
 Specifies additional message-dependent information.  
  
 `lParam`  
 Specifies additional message-dependent information.  
  
### Return Value  
 Depends on the message sent.  
  
### Remarks  
 This member function ensures that every message is processed. It should be called with the same parameters as those received by the window procedure.  
  
##  <a name="deletetempmap"></a>  CWnd::DeleteTempMap  
 Called automatically by the idle time handler of the `CWinApp` object.  
  
```  
statique DeleteTempMap() PASCAL void ;
```  
  
### Remarks  
 Deletes any temporary `CWnd` objects created by the `FromHandle` member function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#86](../../mfc/reference/codesnippet/cpp/cwnd-class_25.cpp)]  
  
##  <a name="destroywindow"></a>  CWnd::DestroyWindow  
 Destroys the Windows window attached to the `CWnd` object.  
  
```  
virtuel BOOL DestroyWindow() ;
```  
  
### Return Value  
 Nonzero if the window is destroyed; otherwise 0.  
  
### Remarks  
 The `DestroyWindow` member function sends appropriate messages to the window to deactivate it and remove the input focus. It also destroys the window's menu, flushes the application queue, destroys outstanding timers, removes Clipboard ownership, and breaks the Clipboard-viewer chain if `CWnd` is at the top of the viewer chain. It sends [WM_DESTROY](#ondestroy) and [WM_NCDESTROY](#onncdestroy) messages to the window. It does not destroy the `CWnd` object.  
  
 `DestroyWindow` is a place holder for performing cleanup. Because `DestroyWindow` is a virtual function, it is shown in any `CWnd`-derived class in Class View. But even if you override this function in your `CWnd`-derived class, `DestroyWindow` is not necessarily called. If `DestroyWindow` is not called in the MFC code, then you have to explicitly call it in your own code if you want it to be called.  
  
 Assume, for example, you have overridden `DestroyWindow` in a `CView`-derived class. Since MFC source code does not call `DestroyWindow` in any of its `CFrameWnd`-derived classes, your overridden `DestroyWindow` will not be called unless you call it explicitly.  
  
 If the window is the parent of any windows, these child windows are automatically destroyed when the parent window is destroyed. The `DestroyWindow` member function destroys child windows first and then the window itself.  
  
 The `DestroyWindow` member function also destroys modeless dialog boxes created by [CDialog::Create](../../mfc/reference/cdialog-class.md#create).  
  
 If the `CWnd` being destroyed is a child window and does not have the [WS_EX_NOPARENTNOTIFY](../../mfc/reference/extended-window-styles.md) style set, then the [WM_PARENTNOTIFY ](https://msdn.microsoft.com/library/ms632638.aspx)       message is sent to the parent.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#87](../../mfc/reference/codesnippet/cpp/cwnd-class_26.cpp)]  
  
##  <a name="detach"></a>  CWnd::Detach  
 Detaches a Windows handle from a `CWnd` object and returns the handle.  
  
```  
HWND Detach() ;
```  
  
### Return Value  
 A `HWND` to the Windows object.  
  
### Example  
  See the example for [CWnd::Attach](#attach).  
  
##  <a name="dlgdirlist"></a>  CWnd::DlgDirList  
 Fills a list box with a file or directory listing.  
  
```  
int DlgDirList (LPTSTR lpPathSpec,  
    int nIDListBox,  
    int nIDStaticPath,  
    UINT nFileType) ;
```  
  
### Parameters  
 `lpPathSpec`  
 Points to a null-terminated string that contains the path or filename. `DlgDirList` modifies this string, which should be long enough to contain the modifications. For more information, see the following "Remarks" section.  
  
 `nIDListBox`  
 Specifies the identifier of a list box. If `nIDListBox` is 0, `DlgDirList` assumes that no list box exists and does not attempt to fill one.  
  
 `nIDStaticPath`  
 Specifies the identifier of the static-text control used to display the current drive and directory. If `nIDStaticPath` is 0, `DlgDirList` assumes that no such text control is present.  
  
 `nFileType`  
 Specifies the attributes of the files to be displayed. It can be any combination of the following values:  
  
- **DDL_READWRITE** Read-write data files with no additional attributes.  
  
- **DDL_READONLY** Read-only files.  
  
- **DDL_HIDDEN** Hidden files.  
  
- **DDL_SYSTEM** System files.  
  
- **DDL_DIRECTORY** Directories.  
  
- **DDL_ARCHIVE** Archives.  
  
- **DDL_POSTMSGS LB_DIR** flag. If the **LB_DIR** flag is set, Windows places the messages generated by `DlgDirList` in the application's queue; otherwise, they are sent directly to the dialog-box procedure.  
  
- **DDL_DRIVES** Drives. If the **DDL_DRIVES** flag is set, the **DDL_EXCLUSIVE** flag is set automatically. Therefore, to create a directory listing that includes drives and files, you must call `DlgDirList` twice: once with the **DDL_DRIVES** flag set and once with the flags for the rest of the list.  
  
- **DDL_EXCLUSIVE** Exclusive bit. If the exclusive bit is set, only files of the specified type are listed; otherwise normal files and files of the specified type are listed.  
  
### Return Value  
 Nonzero if the function is successful; otherwise 0.  
  
### Remarks  
 `DlgDirList` sends [LB_RESETCONTENT](http://msdn.microsoft.com/library/windows/desktop/bb761325) and [LB_DIR](http://msdn.microsoft.com/library/windows/desktop/bb775185) messages to the list box. It fills the list box specified by `nIDListBox` with the names of all files that match the path given by `lpPathSpec`.  
  
 The `lpPathSpec` parameter has the following form:  
  
 `[drive:] [ [\u]directory[\idirectory]...\u] [filename]`  
  
 In this example, `drive` is a drive letter, `directory` is a valid directory name, and *filename* is a valid filename that must contain at least one wildcard. The wildcards are a question mark ( ****), which means match any character, and an asterisk ( **\***), meaning match any number of characters.  
  
 If you specify a 0-length string for `lpPathSpec`, or if you specify only a directory name but do not include any file specification, the string will be changed to "*.\*".  
  
 If `lpPathSpec` includes a drive and/or directory name, the current drive and directory are changed to the designated drive and directory before the list box is filled. The text control identified by `nIDStaticPath` is also updated with the new drive and/or directory name.  
  
 After the list box is filled, `lpPathSpec` is updated by removing the drive and/or directory portion of the path.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#88](../../mfc/reference/codesnippet/cpp/cwnd-class_27.cpp)]  
  
##  <a name="dlgdirlistcombobox"></a>  CWnd::DlgDirListComboBox  
 Fills the list box of a combo box with a file or directory listing.  
  
```  
int DlgDirListComboBox (LPTSTR lpPathSpec,  
    int nIDComboBox,  
    int nIDStaticPath,  
    UINT nFileType) ;
```  
  
### Parameters  
 `lpPathSpec`  
 Points to a null-terminated string that contains the path or filename. `DlgDirListComboBox` modifies this string, so this data should not be in the form of a string literal. See the following "Remarks" section.  
  
 `nIDComboBox`  
 Specifies the identifier of a combo box in a dialog box. If `nIDComboBox` is 0, `DlgDirListComboBox` assumes that no combo box exists and does not attempt to fill one.  
  
 `nIDStaticPath`  
 Specifies the identifier of the static-text control used to display the current drive and directory. If `nIDStaticPath` is 0, `DlgDirListComboBox` assumes that no such text control is present.  
  
 `nFileType`  
 Specifies DOS file attributes of the files to be displayed. It can be any combination of the following values:  
  
- **DDL_READWRITE** Read-write data files with no additional attributes.  
  
- **DDL_READONLY** Read-only files.  
  
- **DDL_HIDDEN** Hidden files.  
  
- **DDL_SYSTEM** System files.  
  
- **DDL_DIRECTORY** Directories.  
  
- **DDL_ARCHIVE** Archives.  
  
- **DDL_POSTMSGS CB_DIR** flag. If the **CB_DIR** flag is set, Windows places the messages generated by `DlgDirListComboBox` in the application's queue; otherwise, they are sent directly to the dialog-box procedure.  
  
- **DDL_DRIVES** Drives. If the **DDL_DRIVES** flag is set, the **DDL_EXCLUSIVE** flag is set automatically. Therefore, to create a directory listing that includes drives and files, you must call `DlgDirListComboBox` twice: once with the **DDL_DRIVES** flag set and once with the flags for the rest of the list.  
  
- **DDL_EXCLUSIVE** Exclusive bit. If the exclusive bit is set, only files of the specified type are listed; otherwise normal files and files of the specified type are listed.  
  
### Return Value  
 Specifies the outcome of the function. It is nonzero if a listing was made, even an empty listing. A 0 return value implies that the input string did not contain a valid search path.  
  
### Remarks  
 `DlgDirListComboBox` sends [CB_RESETCONTENT](http://msdn.microsoft.com/library/windows/desktop/bb775878) and [CB_DIR](http://msdn.microsoft.com/library/windows/desktop/bb775832) messages to the combo box. It fills the list box of the combo box specified by `nIDComboBox` with the names of all files that match the path given by `lpPathSpec`.  
  
 The `lpPathSpec` parameter has the following form:  
  
 `[drive:] [ [\u]directory[\idirectory]...\u] [filename]`  
  
 In this example, `drive` is a drive letter, `directory` is a valid directory name, and *filename* is a valid filename that must contain at least one wildcard. The wildcards are a question mark ( ****), which means match any character, and an asterisk ( **\***), which means match any number of characters.  
  
 If you specify a zero-length string for `lpPathSpec`, the current directory will be used and `lpPathSpec` will not be modified. If you specify only a directory name but do not include any file specification, the string will be changed to "*".  
  
 If `lpPathSpec` includes a drive and/or directory name, the current drive and directory are changed to the designated drive and directory before the list box is filled. The text control identified by `nIDStaticPath` is also updated with the new drive and/or directory name.  
  
 After the combo-box list box is filled, `lpPathSpec` is updated by removing the drive and/or directory portion of the path.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#89](../../mfc/reference/codesnippet/cpp/cwnd-class_28.cpp)]  
  
##  <a name="dlgdirselect"></a>  CWnd::DlgDirSelect  
 Retrieves the current selection from a list box.  
  
```  
BOOL DlgDirSelect (LPTSTR lpString,  
    nIDListBox int) ;
```  
  
### Parameters  
 `lpString`  
 Points to a buffer that is to receive the current selection in the list box.  
  
 `nIDListBox`  
 Specifies the integer ID of a list box in the dialog box.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 It assumes that the list box has been filled by the [DlgDirList](#dlgdirlist) member function and that the selection is a drive letter, a file, or a directory name.  
  
 The `DlgDirSelect` member function copies the selection to the buffer given by `lpString`. If there is no selection, `lpString` does not change.  
  
 `DlgDirSelect` sends [LB_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb775197) and [LB_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761313) messages to the list box.  
  
 It does not allow more than one filename to be returned from a list box. The list box must not be a multiple-selection list box.  
  
##  <a name="dlgdirselectcombobox"></a>  CWnd::DlgDirSelectComboBox  
 Retrieves the current selection from the list box of a combo box.  
  
```  
BOOL DlgDirSelectComboBox (LPTSTR lpString,  
    nIDComboBox int) ;
```  
  
### Parameters  
 `lpString`  
 Points to a buffer that is to receive the selected path.  
  
 `nIDComboBox`  
 Specifies the integer ID of the combo box in the dialog box.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 It assumes that the list box has been filled by the [DlgDirListComboBox](#dlgdirlistcombobox) member function and that the selection is a drive letter, a file, or a directory name.  
  
 The `DlgDirSelectComboBox` member function copies the selection to the specified buffer. If there is no selection, the contents of the buffer are not changed.  
  
 `DlgDirSelectComboBox` sends [CB_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb775845) and [CB_GETLBTEXT](http://msdn.microsoft.com/library/windows/desktop/bb775862) messages to the combo box.  
  
 It does not allow more than one filename to be returned from a combo box.  
  
##  <a name="dodataexchange"></a>  CWnd::DoDataExchange  
 Called by the framework to exchange and validate dialog data.  
  
```  
DoDataExchange void virtuelle (CDataExchange * pDX) ;
```  
  
### Parameters  
 `pDX`  
 A pointer to a `CDataExchange` object.  
  
### Remarks  
 Never call this function directly. It is called by the [UpdateData](#updatedata) member function. Call `UpdateData` to initialize a dialog box's controls or retrieve data from a dialog box.  
  
 When you derive an application-specific dialog class from [CDialog](../../mfc/reference/cdialog-class.md), you need to override this member function if you wish to utilize the framework's automatic data exchange and validation. The Add Variable wizard will write an overridden version of this member function for you containing the desired "data map" of dialog data exchange (DDX) and validation (DDV) global function calls.  
  
 To automatically generate an overridden version of this member function, first create a dialog resource with the dialog editor, then derive an application-specific dialog class. Then use the Add Variable wizard to associate variables, data, and validation ranges with various controls in the new dialog box. The wizard then writes the overridden `DoDataExchange`, which contains a data map. The following is an example DDX/DDV code block generated by the Add Variable wizard:  
  
 [!code-cpp[NVC_MFCWindowing#90](../../mfc/reference/codesnippet/cpp/cwnd-class_29.cpp)]  
  
 The `DoDataExchange` overridden member function must precede the macro statements in your source file.  
  
 For more information on dialog data exchange and validation, see [Displaying and Manipulating Data in a Form](../../data/odbc/displaying-and-manipulating-data-in-a-form.md) and [Dialog Data Exchange and Validation](../../mfc/dialog-data-exchange-and-validation.md). For a description of the DDX_ and DDV_ macros generated by the Add Variable wizard, see [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md).  
  
##  <a name="dragacceptfiles"></a>  CWnd::DragAcceptFiles  
 Call this member function from within a window, using a `CWnd` pointer, in your application's [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) function to indicate that the window accepts dropped files from the Windows File Manager or File Explorer.  
  
```  
void DragAcceptFiles (BOOL bAccept = TRUE) ;
```  
  
### Parameters  
 *BAccept*  
 Flag that indicates whether dragged files are accepted.  
  
### Remarks  
 Only the window that calls `DragAcceptFiles` with the `bAccept` parameter set to **TRUE** has identified itself as able to process the Windows message `WM_DROPFILES`. For example, in an MDI application, if the `CMDIFrameWnd` window pointer is used in the `DragAcceptFiles` function call, only the `CMDIFrameWnd` window gets the `WM_DROPFILES` message. This message is not sent to all open `CMDIChildWnd` windows. For a `CMDIChildWnd` window to receive this message, you must call `DragAcceptFiles` with the `CMDIChildWnd` window pointer.  
  
 To discontinue receiving dragged files, call the member function with `bAccept` set to **FALSE**.  
  
##  <a name="dragdetect"></a>  CWnd::DragDetect  
 Captures the mouse and tracks its movement until the user releases the left button, presses the ESC key, or moves the mouse outside the drag rectangle around the specified point.  
  
```  
BOOL DragDetect(POINT pt) const ;  
```  
  
### Parameters  
 `pt`  
 Initial position of the mouse, in screen coordinates. The function determines the coordinates of the drag rectangle by using this point.  
  
### Return Value  
 If the user moved the mouse outside of the drag rectangle while holding down the left button , the return value is nonzero.  
  
 If the user did not move the mouse outside of the drag rectangle while holding down the left button , the return value is zero.  
  
### Remarks  
 This member function emulates the functionality of the function [DragDetect](http://msdn.microsoft.com/library/windows/desktop/ms646256), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawanimatedrects"></a>  CWnd::DrawAnimatedRects  
 Draws a wire-frame rectangle and animates it to indicate the opening of an icon or the minimizing or maximizing of a window.  
  
```  
BOOL DrawAnimatedRects (int idAni,  
    CONST RECT* lprcFrom, CONST RECT* lprcTo) ;
```  
  
### Parameters  
 *idAni*  
 Specifies the type of animation. If you specify **IDANI_CAPTION**, the window caption will animate from the position specified by `lprcFrom` to the position specified by `lprcTo`. The effect is similar to minimizing or maximizing a window.  
  
 `lprcFrom`  
 Pointer to a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure specifying the location and size of the icon or minimized window.  
  
 `lprcTo`  
 Pointer to a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure specifying the location and size of the restored window  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [DrawAnimatedRects](http://msdn.microsoft.com/library/windows/desktop/dd162475), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawcaption"></a>  CWnd::DrawCaption  
 Draws a window caption.  
  
```  
BOOL DrawCaption (CDC * pDC,  
    LPCRECT lprc,  
    UINT uFlags) ;
```  
  
### Parameters  
 `pDC`  
 A pointer to a device context. The function draws the window caption into this device context.  
  
 `lprc`  
 A pointer to a RECT structure that specifies the bounding rectangle for the window caption.  
  
 `uFlags`  
 Specifies drawing options. For a complete list of values, see [DrawCaption](http://msdn.microsoft.com/library/windows/desktop/dd162476).  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [DrawCaption](http://msdn.microsoft.com/library/windows/desktop/dd162476), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawmenubar"></a>  CWnd::DrawMenuBar  
 Redraws the menu bar.  
  
```  
void DrawMenuBar() ;
```  
  
### Remarks  
 If a menu bar is changed after Windows has created the window, call this function to draw the changed menu bar.  
  
### Example  
  See the example for [CWnd::GetMenu](#getmenu).  
  
##  <a name="enableactiveaccessibility"></a>  CWnd::EnableActiveAccessibility  
 Enables user-defined Active Accessibility functions.  
  
```  
void EnableActiveAccessibility() ;
```  
  
### Remarks  
 MFC's default Active Accessibility support is sufficient for standard windows and controls, including ActiveX controls; however, if your `CWnd`-derived class contains nonwindowed user interface elements, MFC has no way of knowing about them. In that case, you must override the appropriate [Active Accessibility member functions](http://msdn.microsoft.com/en-us/68af04ac-4eb9-4b7d-b33f-c45512097a74) in your class, and you must call **EnableActiveAccessibility** in the class's constructor.  
  
##  <a name="enabledynamiclayout"></a>  CWnd::EnableDynamicLayout  
 Enables or disables the dynamic layout manager. When dynamic layout is enabled, the position and size of child windows can adjust dynamically when the user resizes the window.  
  
```  
void EnableDynamicLayout (BOOL bActivez = TRUE) ;
```  
  
### Parameters  
 `bEnable`  
 TRUE to enable dynamic layout; FALSE to disable dynamic layout.  
  
### Remarks  
 If you want to enable dynamic layout, you have to do more than just call this method. You also have to provide dynamic layout information which species how the controls in the window respond to size changes. You can specify this information in the resource editor, or programmatically, for each control. See [Dynamic Layout](../../mfc/dynamic-layout.md).  
  
##  <a name="enabled2dsupport"></a>  CWnd::EnableD2DSupport  
 Enables or disables window D2D support. Call this method before the main window is initialized.  
  
```  
void EnableD2DSupport (BOOL bActivez = TRUE,  
    BOOL bUseDCRenderTarget = FALSE) ;
```  
  
### Parameters  
 `bEnable`  
 Specifies whether to turn on, or off D2D support.  
  
 `bUseDCRenderTarget`  
 Species whether to use the Device Context (DC) render target, CDCRenderTarget. If FALSE, CHwndRenderTarget is used.  
  
##  <a name="enablescrollbar"></a>  CWnd::EnableScrollBar  
 Enables or disables one or both arrows of a scroll bar.  
  
```  
BOOL EnableScrollBar (int nSBFlags,  
    UINT nArrowFlags = ESB_ENABLE_BOTH) ;
```  
  
### Parameters  
 *nSBFlags*  
 Specifies the scroll-bar type. Can have one of the following values:  
  
- **SB_BOTH** Enables or disables the arrows of the horizontal and vertical scroll bars associated with the window.  
  
- **SB_HORZ** Enables or disables the arrows of the horizontal scroll bar associated with the window.  
  
- **SB_VERT** Enables or disables the arrows of the vertical scroll bar associated with the window.  
  
 `nArrowFlags`  
 Specifies whether the scroll-bar arrows are enabled or disabled and which arrows are enabled or disabled. Can have one of the following values:  
  
- **ESB_ENABLE_BOTH** Enables both arrows of a scroll bar (default).  
  
- **ESB_DISABLE_LTUP** Disables the left arrow of a horizontal scroll bar or the up arrow of a vertical scroll bar.  
  
- **ESB_DISABLE_RTDN** Disables the right arrow of a horizontal scroll bar or the down arrow of a vertical scroll bar.  
  
- **ESB_DISABLE_BOTH** Disables both arrows of a scroll bar.  
  
### Return Value  
 Nonzero if the arrows are enabled or disabled as specified. Otherwise it is 0, which indicates that the arrows are already in the requested state or that an error occurred.  
  
##  <a name="enablescrollbarctrl"></a>  CWnd::EnableScrollBarCtrl  
 Enables or disables the scroll bar for this window.  
  
```  
void EnableScrollBarCtrl (int nBar,  
    BOOL bActivez = TRUE) ;
```  
  
### Parameters  
 `nBar`  
 The scroll-bar identifier.  
  
 `bEnable`  
 Specifies whether the scroll bar is to be enabled or disabled.  
  
### Remarks  
 If the window has a sibling scroll-bar control, that scroll bar is used; otherwise the window's own scroll bar is used.  
  
##  <a name="enabletooltips"></a>  CWnd::EnableToolTips  
 Enables tool tips for the given window.  
  
```  
BOOL EnableToolTips(BOOL bEnable = TRUE) ;
```  
  
### Parameters  
 `bEnable`  
 Specifies whether the tool tip control is enabled or disabled. **TRUE** enables the control; **FALSE** disables the control.  
  
### Return Value  
 **TRUE** if tool tips are enabled; otherwise **FALSE**.  
  
### Remarks  
 Override [OnToolHitTest](#ontoolhittest) to provide the [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) struct or structs for the window.  
  
> [!NOTE]
>  Some windows, such as [CToolBar](../../mfc/reference/ctoolbar-class.md), provide a built-in implementation of [OnToolHitTest](#ontoolhittest).  
  
 See [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information on this structure.  
  
 Simply calling `EnableToolTips` is not enough to display tool tips for your child controls unless the parent window is derived from `CFrameWnd`. This is because `CFrameWnd` provides a default handler for the **TTN_NEEDTEXT** notification. If your parent window is not derived from `CFrameWnd`, that is, if it is a dialog box or a form view, tool tips for your child controls will not display correctly unless you provide a handler for the **TTN_NEEDTEXT** tool tip notification. See [Tool Tips](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 The default tool tips provided for your windows by `EnableToolTips` do not have text associated with them. To retrieve text for the tool tip to display, the **TTN_NEEDTEXT** notification is sent to the tool tip control's parent window just before the tool tip window is displayed. If there is no handler for this message to assign some value to the `pszText` member of the **TOOLTIPTEXT** structure, there will be no text displayed for the tool tip.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#91](../../mfc/reference/codesnippet/cpp/cwnd-class_30.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#92](../../mfc/reference/codesnippet/cpp/cwnd-class_31.cpp)]  
  
##  <a name="enabletrackingtooltips"></a>  CWnd::EnableTrackingToolTips  
 Enables or disables tracking tooltips.  
  
```  
BOOL EnableTrackingToolTips(BOOL bEnable = TRUE) ;
```  
  
### Parameters  
 `bEnable`  
 Specifies whether tracking tool tips are enabled or disabled. If this parameter is **TRUE**, the tracking tool tips will be enabled. If this parameter is **FALSE**, the tracking tool tips will be disabled.  
  
### Return Value  
 Indicates the state before the `EnableWindow` member function was called. The return value is nonzero if the window was previously disabled. The return value is 0 if the window was previously enabled or an error occurred.  
  
### Remarks  
 Tracking tool tips are tool tip windows that you can dynamically position on the screen. By rapidly updating the position, the tool tip window appears to move smoothly, or "track." This functionality can be useful if you need tool tip text to follow the position of the pointer as it moves.  
  
##  <a name="enablewindow"></a>  CWnd::EnableWindow  
 Enables or disables mouse and keyboard input.  
  
```  
BOOL EnableWindow(BOOL bEnable = TRUE) ;
```  
  
### Parameters  
 `bEnable`  
 Specifies whether the given window is to be enabled or disabled. If this parameter is **TRUE**, the window will be enabled. If this parameter is **FALSE**, the window will be disabled.  
  
### Return Value  
 Indicates the state before the `EnableWindow` member function was called. The return value is nonzero if the window was previously disabled. The return value is 0 if the window was previously enabled or an error occurred.  
  
### Remarks  
 When input is disabled, input such as mouse clicks and keystrokes is ignored. When input is enabled, the window processes all input.  
  
 If the enabled state is changing, the [WM_ENABLE](#onenable) message is sent before this function returns.  
  
 If disabled, all child windows are implicitly disabled, although they are not sent `WM_ENABLE` messages.  
  
 A window must be enabled before it can be activated. For example, if an application is displaying a modeless dialog box and has disabled its main window, the main window must be enabled before the dialog box is destroyed. Otherwise, another window will get the input focus and be activated. If a child window is disabled, it is ignored when Windows tries to determine which window should get mouse messages.  
  
 By default, a window is enabled when it is created. An application can specify the **WS_DISABLED** style in the [Create](#create) or [CreateEx](#createex) member function to create a window that is initially disabled. After a window has been created, an application can also use the `EnableWindow` member function to enable or disable the window.  
  
 An application can use this function to enable or disable a control in a dialog box. A disabled control cannot receive the input focus, nor can a user access it.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#93](../../mfc/reference/codesnippet/cpp/cwnd-class_32.cpp)]  
  
##  <a name="endmodalloop"></a>  CWnd::EndModalLoop  
 Terminates a call to `RunModalLoop`.  
  
```  
EndModalLoop void virtuel (%nrésultat int) ;
```  
  
### Parameters  
 `nResult`  
 Contains the value to be returned to the caller of [RunModalLoop](#runmodalloop).  
  
### Remarks  
 The `nResult` parameter is propagated to the return value from `RunModalLoop`.  
  
##  <a name="endmodalstate"></a>  CWnd::EndModalState  
 Call this member function to change a frame window from modal to modeless.  
  
```  
EndModalState() void virtuel ;
```  
  
##  <a name="endpaint"></a>  CWnd::EndPaint  
 Marks the end of painting in the given window.  
  
```  
void EndPaint (LPPAINTSTRUCT lpPaint) ;
```  
  
### Parameters  
 `lpPaint`  
 Points to a [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) structure that contains the painting information retrieved by the [BeginPaint](#beginpaint) member function.  
  
### Remarks  
 The `EndPaint` member function is required for each call to the `BeginPaint` member function, but only after painting is complete.  
  
 If the caret was hidden by the `BeginPaint` member function, `EndPaint` restores the caret to the screen.  
  
### Example  
  See the example for [CWnd::BeginPaint](#beginpaint).  
  
##  <a name="executedlginit"></a>  CWnd::ExecuteDlgInit  
 Initiates a dialog resource.  
  
```  
BOOL ExecuteDlgInit(LPCTSTR lpszResourceName) ;  
BOOL ExecuteDlgInit(LPVOID lpResource) ;
```  
  
### Parameters  
 `lpszResourceName`  
 A pointer to a null-terminated string specifying the name of the resource.  
  
 `lpResource`  
 A pointer to a resource.  
  
### Return Value  
 **TRUE** if a dialog resource is executed; otherwise **FALSE**.  
  
### Remarks  
 `ExecuteDlgInit` will use resources bound to the executing module, or resources from other sources. To accomplish this, `ExecuteDlgInit` finds a resource handle by calling `AfxFindResourceHandle`. If your MFC application does not use the shared DLL (MFCx0[U][D].DLL), **AfxFindResourceHandle** calls [AfxGetResourceHandle](http://msdn.microsoft.com/library/d0eff6c4-f566-471a-96b7-a5a70a751a92), which returns the current resource handle for the executable. If your MFC application that uses MFCx0[U][D].DLL, `AfxFindResourceHandle` traverses the **CDynLinkLibrary** object list of shared and extension DLLs looking for the correct resource handle.  
  
##  <a name="filtertooltipmessage"></a>  CWnd::FilterToolTipMessage  
 Called by the framework to display tool tip messages.  
  
```  
void FilterToolTipMessage (MSG * pMsg) ;
```  
  
### Parameters  
 `pMsg`  
 A pointer to the tool tip message.  
  
### Remarks  
 In most MFC applications this method is called by the framework from [PreTranslateMessage](#pretranslatemessage) and [EnableToolTips](#enabletooltips), and you do not need to call it yourself.  
  
 However, in certain applications, for example some ActiveX controls, these methods might not be invoked by the framework, and you will need to call FilterToolTipMessage yourself. For more information, see [Methods of Creating Tool Tips](../../mfc/methods-of-creating-tool-tips.md).  
  
##  <a name="findwindow"></a>  CWnd::FindWindow  
 Returns the top-level `CWnd` whose window class is given by `lpszClassName` and whose window name, or title, is given by `lpszWindowName`.  
  
```  
statique CWnd * PASCAL FindWindow (lpszClassName LPCTSTR,  
    LPCTSTR lpszWindowName) ;
```  
  
### Parameters  
 `lpszClassName`  
 Points to a null-terminated string that specifies the window's class name (a **WNDCLASS** structure). If `lpClassName` is **NULL**, all class names match.  
  
 `lpszWindowName`  
 Points to a null-terminated string that specifies the window name (the window's title). If `lpWindowName` is **NULL**, all window names match.  
  
### Return Value  
 Identifies the window that has the specified class name and window name. It is **NULL** if no such window is found.  
  
 The `CWnd`* may be temporary and should not be stored for later use.  
  
### Remarks  
 This function does not search child windows.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#94](../../mfc/reference/codesnippet/cpp/cwnd-class_33.cpp)]  
  
##  <a name="findwindowex"></a>  CWnd::FindWindowEx  
 Retrieves the window object whose class name and window name match the specified strings.  
  
```  
CWnd * FindWindowEx statique (HWND hwndParent,  
    HWND hwndChildAfter,  
    LPCTSTR lpszClass,  
    LPCTSTR lpszWindow) ;
```  
  
### Parameters  
 *hwndParent*  
 Handle to the parent window whose child windows are to be searched.  
  
 *hwndChildAfter*  
 Handle to a child window. The search begins with the next child window in the Z order. The child window must be a direct child window of *hwndParent*, not just a descendant window.  
  
 `lpszClass`  
 Pointer to a null-terminated string that specifies the class name or a class atom created by a previous call to the [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586) or [RegisterClassEx](http://msdn.microsoft.com/library/windows/desktop/ms633587).  
  
 *lpszWindow*  
 Pointer to a null-terminated string that specifies the window name (the window's title). If this parameter is **NULL**, all window names match.  
  
### Return Value  
 If the function succeeds, the return value is a pointer to the window object having the specified class and window names. If the function fails, the return value is **NULL**.  
  
### Remarks  
 This member function emulates the functionality of the function [FindWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms633500), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="flashwindow"></a>  CWnd::FlashWindow  
 Flashes the given window once.  
  
```  
BOOL FlashWindow(BOOL bInvert) ;
```  
  
### Parameters  
 `bInvert`  
 Specifies whether the `CWnd` is to be flashed or returned to its original state. The `CWnd` is flashed from one state to the other if `bInvert` is **TRUE**. If `bInvert` is **FALSE**, the window is returned to its original state (either active or inactive).  
  
### Return Value  
 Nonzero if the window was active before the call to the `FlashWindow` member function; otherwise 0.  
  
### Remarks  
 For successive flashing, create a system timer and repeatedly call `FlashWindow`. Flashing the `CWnd` means changing the appearance of its title bar as if the `CWnd` were changing from inactive to active status, or vice versa. (An inactive title bar changes to an active title bar; an active title bar changes to an inactive title bar.)  
  
 Typically, a window is flashed to inform the user that it requires attention but that it does not currently have the input focus.  
  
 The `bInvert` parameter should be **FALSE** only when the window is getting the input focus and will no longer be flashing; it should be **TRUE** on successive calls while waiting to get the input focus.  
  
 This function always returns nonzero for minimized windows. If the window is minimized, `FlashWindow` will simply flash the window's icon; `bInvert` is ignored for minimized windows.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#95](../../mfc/reference/codesnippet/cpp/cwnd-class_34.cpp)]  
  
##  <a name="flashwindowex"></a>  CWnd::FlashWindowEx  
 Flashes the given window.  
  
```  
BOOL FlashWindowEx (DWORD dwFlags,  
    UINT uCount,  
    DwTimeout DWORD) ;
```  
  
### Parameters  
 `dwFlags`  
 Specifies the flash status. For a complete list of values, see the [FLASHWINFO](http://msdn.microsoft.com/library/windows/desktop/ms679348) structure.  
  
 `uCount`  
 Specifies the number of times to flash the window.  
  
 `dwTimeout`  
 Specifies the rate, in milliseconds, at which the window will be flashed. If `dwTimeout` is zero, the function uses the default cursor blink rate.  
  
### Return Value  
 The return value specifies the window's state before the call to the `FlashWindowEx` function. If the window caption was drawn as active before the call, the return value is nonzero. Otherwise, the return value is zero.  
  
### Remarks  
 This method emulates the functionality of the function [FlashWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms679347), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="fromhandle"></a>  CWnd::FromHandle  
 Returns a pointer to a `CWnd` object when given a handle to a window. If a `CWnd` object is not attached to the handle, a temporary `CWnd` object is created and attached.  
  
```  
statique CWnd * PASCAL FromHandle(HWND hWnd) ;
```  
  
### Parameters  
 `hWnd`  
 An `HWND` of a Windows window.  
  
### Return Value  
 Returns a pointer to a `CWnd` object when given a handle to a window. If a `CWnd` object is not attached to the handle, a temporary `CWnd` object is created and attached.  
  
 The pointer may be temporary and should not be stored for later use.  
  
##  <a name="fromhandlepermanent"></a>  CWnd::FromHandlePermanent  
 Returns a pointer to a `CWnd` object when given a handle to a window.  
  
```  
statique CWnd * PASCAL FromHandlePermanent(HWND hWnd) ;
```  
  
### Parameters  
 `hWnd`  
 An `HWND` of a Windows window.  
  
### Return Value  
 A pointer to a `CWnd` object.  
  
### Remarks  
 If a `CWnd` object is not attached to the handle, **NULL** is returned.  
  
 This function, unlike [FromHandle](#fromhandle), does not create temporary objects.  
  
##  <a name="get_accchild"></a>  CWnd::get_accChild  
 Called by the framework to retrieve the address of an `IDispatch` interface for the specified child.  
  
```  
virtuel HRESULT get_accChild (variante varChild,  
    IDispatch** ppdispChild) ;
```  
  
### Parameters  
 `varChild`  
 Identifies the child whose `IDispatch` interface is to be retrieved.  
  
 *ppdispChild*  
 Receives the address of the child object's `IDispatch` interface.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accChild](http://msdn.microsoft.com/library/windows/desktop/dd318475) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accChild](http://msdn.microsoft.com/library/windows/desktop/dd318475) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accchildcount"></a>  CWnd::get_accChildCount  
 Called by the framework to retrieve the number of children belonging to this object.  
  
```  
virtuel HRESULT get_accChildCount (long * pcountChildren) ;
```  
  
### Parameters  
 *pcountChildren*  
 Receives the number of children.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accChildCount](http://msdn.microsoft.com/library/windows/desktop/dd318476) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles). Call the base class version and then add the nonwindowed child elements.  
  
 For more information, see [IAccessible::get_accChildCount](http://msdn.microsoft.com/library/windows/desktop/dd318476) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accdefaultaction"></a>  CWnd::get_accDefaultAction  
 Called by the framework to retrieve a string that describes the object's default action.  
  
```  
virtuel HRESULT get_accDefaultAction (variante varChild,  
    BSTR* pszDefaultAction) ;
```  
  
### Parameters  
 `varChild`  
 Specifies whether the default action to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 *pszDefaultAction*  
 Address of a `BSTR` that receives a localized string describing the default action for the specified object, or NULL if this object has no default action.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318477) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to describe your object's default action.  
  
 For more information, see [IAccessible::get_accDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318477) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accdescription"></a>  CWnd::get_accDescription  
 Called by framework to retrieve a string that describes the visual appearance of the specified object.  
  
```  
virtuel HRESULT get_accDescription (variante varChild,  
    BSTR* pszDescription) ;
```  
  
### Parameters  
 `varChild`  
 Specifies whether the description to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pszDescription`  
 Address of a `BSTR` that receives a localized string describing the specified object, or NULL if no description is available for this object.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accDescription](http://msdn.microsoft.com/library/windows/desktop/dd318478) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to describe your object. Call the base class version and add your description.  
  
 For more information, see [IAccessible::get_accDescription](http://msdn.microsoft.com/library/windows/desktop/dd318478) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accfocus"></a>  CWnd::get_accFocus  
 Called by the framework to retrieve the object that has the keyboard focus.  
  
```  
virtuel HRESULT get_accFocus (VARIANT * pvarChild) ;
```  
  
### Parameters  
 `pvarChild`  
 Receives information about the object that has the focus. See *pvarID* in [IAccessible::get_accFocus](http://msdn.microsoft.com/library/windows/desktop/dd318479) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accFocus** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accFocus](http://msdn.microsoft.com/library/windows/desktop/dd318479) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_acchelp"></a>  CWnd::get_accHelp  
 Called by the framework to retrieve an object's **Help** property string.  
  
```  
virtuel HRESULT get_accHelp (variante varChild,  
    BSTR* pszHelp) ;
```  
  
### Parameters  
 `varChild`  
 Specifies whether the help information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 *pszHelp*  
 Address of a `BSTR` that receives the localized string containing the help information for the specified object, or NULL if no help information is available.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accHelp](http://msdn.microsoft.com/library/windows/desktop/dd318480) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to provide help text for your object.  
  
 For more information, see [IAccessible::get_accHelp](http://msdn.microsoft.com/library/windows/desktop/dd318480) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_acchelptopic"></a>  CWnd::get_accHelpTopic  
 Called by the framework to retrieve the full path of the **WinHelp** file associated with the specified object and the identifier of the appropriate topic within that file.  
  
```  
virtuel HRESULT get_accHelpTopic (BSTR* pszHelpFile, variante varChild, long* pidTopic) ;
```  
  
### Parameters  
 `pszHelpFile`  
 Address of a `BSTR` that receives the full path of the `WinHelp` file associated with the specified object, if any.  
  
 `varChild`  
 Specifies whether the Help topic to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain a Help topic for the object) or a child ID (to obtain a Help topic for one of the object's child elements).  
  
 `pidTopic`  
 Identifies the Help file topic associated with the specified object. See `pidTopic` in [IAccessible::get_accHelpTopic](http://msdn.microsoft.com/library/windows/desktop/dd318481) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accHelpTopic** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to provide help information about your object.  
  
 For more information, see [IAccessible::get_accHelpTopic](http://msdn.microsoft.com/library/windows/desktop/dd318481) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_acckeyboardshortcut"></a>  CWnd::get_accKeyboardShortcut  
 Called by the framework to retrieve the specified object's shortcut key or access key.  
  
```  
virtuel HRESULT get_accKeyboardShortcut (variante varChild,  
    BSTR* pszKeyboardShortcut) ;
```  
  
### Parameters  
 `varChild`  
 Specifies whether the keyboard shortcut to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 *pszKeyboardShortcut*  
 Address of a `BSTR` that receives a localized string identifying the keyboard shortcut, or NULL if no keyboard shortcut is associated with the specified object.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accKeyboardShortcut](http://msdn.microsoft.com/library/windows/desktop/dd318482) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to identify the keyboard shortcut for your object.  
  
 For more information, see [IAccessible::get_accKeyboardShortcut](http://msdn.microsoft.com/library/windows/desktop/dd318482) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accname"></a>  CWnd::get_accName  
 Called by the framework to retrieve the name of the specified object.  
  
```  
virtuel HRESULT get_accName (variante varChild,  
    BSTR* pszName) ;
```  
  
### Parameters  
 `varChild`  
 Specifies whether the name to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pszName`  
 Address of a `BSTR` that receives a string containing the specified object's name.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accName](http://msdn.microsoft.com/library/windows/desktop/dd318483) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class to return the name of your object.  
  
 For more information, see [IAccessible::get_accName](http://msdn.microsoft.com/library/windows/desktop/dd318483) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accparent"></a>  CWnd::get_accParent  
 Called by the framework to retrieve the `IDispatch` interface of the object's parent.  
  
```  
virtuel HRESULT get_accParent (IDispatch ** ppdispParent) ;
```  
  
### Parameters  
 *ppdispParent*  
 Receives the address of the parent object's `IDispatch` interface. The variable is set to NULL if no parent exists, or if the child cannot access its parent.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accParent](http://msdn.microsoft.com/library/windows/desktop/dd318484) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 In most cases you don't have to override this function.  
  
 For more information, see [IAccessible::get_accParent](http://msdn.microsoft.com/library/windows/desktop/dd318484) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accrole"></a>  CWnd::get_accRole  
 Called by the framework to retrieve information that describes the role of the specified object.  
  
```  
virtuel HRESULT get_accRole (variante varChild,  
    Variant* pvarRole) ;
```  
  
### Parameters  
 `varChild`  
 Specifies whether the role information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pvarRole`  
 Receives the role information. See `pvarRole` in [IAccessible::get_accRole](http://msdn.microsoft.com/library/windows/desktop/dd318485) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accRole** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accRole](http://msdn.microsoft.com/library/windows/desktop/dd318485) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accselection"></a>  CWnd::get_accSelection  
 Called by the framework to retrieve the selected children of this object.  
  
```  
virtuel HRESULT get_accSelection (VARIANT * pvarChildren) ;
```  
  
### Parameters  
 `pvarChildren`  
 Receives information about which children are selected. See `pvarChildren` in [IAccessible::get_accSelection](http://msdn.microsoft.com/library/windows/desktop/dd318486) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accSelection** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accSelection](http://msdn.microsoft.com/library/windows/desktop/dd318486) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accstate"></a>  CWnd::get_accState  
 Called by the framework to retrieve the current state of the specified object.  
  
```  
virtuel HRESULT get_accState (variante varChild,  
    Variant* pvarState) ;
```  
  
### Parameters  
 `varChild`  
 Specifies whether the state information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pvarState`  
 Receives information about the object's state. See `pvarState` in [IAccessible::get_accState](http://msdn.microsoft.com/library/windows/desktop/dd318487) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in **IAccessible::get_accState** in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accState](http://msdn.microsoft.com/library/windows/desktop/dd318487) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="get_accvalue"></a>  CWnd::get_accValue  
 Called by the framework to retrieve the value of the specified object.  
  
```  
virtuel HRESULT get_accValue (variante varChild,  
    BSTR* pszValue) ;
```  
  
### Parameters  
 `varChild`  
 Specifies whether the value information to be retrieved is that of the object or one of the object's child elements. This parameter can be either CHILDID_SELF (to obtain information about the object) or a child ID (to obtain information about the object's child element).  
  
 `pszValue`  
 Address of the `BSTR` that receives a localized string containing the object's current value.  
  
### Return Value  
 Returns S_OK on success, a COM error code on failure. See **Return Values** in [IAccessible::get_accValue](http://msdn.microsoft.com/library/windows/desktop/dd318488) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 This function is part of MFC's [Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592) support.  
  
 Override this function in your `CWnd`-derived class if you have nonwindowed user interface elements (other than windowless ActiveX controls, which MFC handles).  
  
 For more information, see [IAccessible::get_accValue](http://msdn.microsoft.com/library/windows/desktop/dd318488) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getactivewindow"></a>  CWnd::GetActiveWindow  
 Retrieves a pointer to the active window.  
  
```  
statique CWnd * PASCAL GetActiveWindow() ;
```  
  
### Return Value  
 The active window or **NULL** if no window was active at the time of the call. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The active window is either the window that has the current input focus or the window explicitly made active by the [SetActiveWindow](#setactivewindow) member function.  
  
##  <a name="getancestor"></a>  CWnd::GetAncestor  
 Retrieves the ancestor window object of the specified window.  
  
```  
CWnd * GetAncestor(UINT gaFlags) const ;  
```  
  
### Parameters  
 *gaFlags*  
 Specifies the ancestor to be retrieved. For a complete list of possible values, see [GetAncestor](http://msdn.microsoft.com/library/windows/desktop/ms633502).  
  
### Return Value  
 If the function succeeds, the return value is a pointer to the ancestor window object. If the function fails, the return value is **NULL**.  
  
### Remarks  
 This member function emulates the functionality of the function [GetAncestor](http://msdn.microsoft.com/library/windows/desktop/ms633502), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcapture"></a>  CWnd::GetCapture  
 Retrieves the window that has the mouse capture.  
  
```  
statique CWnd * PASCAL GetCapture() ;
```  
  
### Return Value  
 Identifies the window that has the mouse capture. It is **NULL** if no window has the mouse capture.  
  
 The return value may be temporary and should not be stored for later use.  
  
### Remarks  
 Only one window has the mouse capture at any given time. A window receives the mouse capture when the [SetCapture](#setcapture) member function is called. This window receives mouse input whether or not the cursor is within its borders.  
  
##  <a name="getcaretpos"></a>  CWnd::GetCaretPos  
 Retrieves the client coordinates of the caret's current position and returns them as a `CPoint`.  
  
```  
GetCaretPos() de casse PASCAL CPoint statique ;
```  
  
### Return Value  
 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object containing the coordinates of the caret's position.  
  
### Remarks  
 The caret position is given in the client coordinates of the `CWnd` window.  
  
##  <a name="getcheckedradiobutton"></a>  CWnd::GetCheckedRadioButton  
 Retrieves the ID of the currently checked radio button in the specified group.  
  
```  
int GetCheckedRadioButton (int nIDFirstButton,  
    nIDLastButton int) ;
```  
  
### Parameters  
 `nIDFirstButton`  
 Specifies the integer identifier of the first radio button in the group.  
  
 `nIDLastButton`  
 Specifies the integer identifier of the last radio button in the group.  
  
### Return Value  
 ID of the checked radio button, or 0 if none is selected.  
  
##  <a name="getclientrect"></a>  CWnd::GetClientRect  
 Copies the client coordinates of the `CWnd` client area into the structure pointed to by `lpRect`.  
  
```  
void GetClientRect (LPRECT lpRect) const ;  
```  
  
### Parameters  
 `lpRect`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) or a `CRect` object to receive the client coordinates. The **left** and **top** members will be 0. The **right** and **bottom** members will contain the width and height of the window.  
  
### Remarks  
 The client coordinates specify the upper-left and lower-right corners of the client area. Since client coordinates are relative to the upper-left corners of the `CWnd` client area, the coordinates of the upper-left corner are (0,0).  
  
### Example  
  See the example for [CWnd::IsIconic](#isiconic).  
  
##  <a name="getclipboardowner"></a>  CWnd::GetClipboardOwner  
 Retrieves the current owner of the Clipboard.  
  
```  
statique CWnd * PASCAL GetClipboardOwner() ;
```  
  
### Return Value  
 Identifies the window that owns the Clipboard if the function is successful. Otherwise, it is **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The Clipboard can still contain data even if it is not currently owned.  
  
##  <a name="getclipboardviewer"></a>  CWnd::GetClipboardViewer  
 Retrieves the first window in the Clipboard-viewer chain.  
  
```  
statique CWnd * PASCAL GetClipboardViewer() ;
```  
  
### Return Value  
 Identifies the window currently responsible for displaying the Clipboard if successful; otherwise **NULL** (for example, if there is no viewer).  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
##  <a name="getcontrolunknown"></a>  CWnd::GetControlUnknown  
 Call this member function to retrieve a pointer to an unknown OLE control.  
  
```  
GetControlUnknown() LPUNKNOWN ;
```  
  
### Return Value  
 A pointer to the [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) interface of the OLE control represented by this `CWnd` object. If this object does not represent an OLE control, the return value is **NULL**.  
  
### Remarks  
 You should not release this **IUnknown** pointer. Typically, you would use to obtain a specific interface of the control.  
  
 The interface pointer returned by **GetControlUnknown** is not reference-counted. Do not call [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) on the pointer unless you have previously called [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) on it.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#96](../../mfc/reference/codesnippet/cpp/cwnd-class_35.cpp)]  
  
##  <a name="getcurrentmessage"></a>  CWnd::GetCurrentMessage  
 Returns a pointer to the message this window is currently processing. Should only be called when in an **On***Message* message-handler member function.  
  
```  
static const MSG * PASCAL GetCurrentMessage() ;
```  
  
### Return Value  
 Returns a pointer to the [MSG](../../mfc/reference/msg-structure1.md) structure that contains the message the window is currently processing. Should only be called when in an **On***Message* handler.  
  
### Example  
  See the example for [CMDIFrameWnd::MDICascade](../../mfc/reference/cmdiframewnd-class.md#mdicascade).  
  
##  <a name="getdc"></a>  CWnd::GetDC  
 Retrieves a pointer to a common, class, or private device context for the client area depending on the class style specified for the `CWnd`.  
  
```  
CDC * GetDC() ;
```  
  
### Return Value  
 Identifies the device context for the `CWnd` client area if successful; otherwise, the return value is **NULL**. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 For common device contexts, `GetDC` assigns default attributes to the context each time it is retrieved. For class and private contexts, `GetDC` leaves the previously assigned attributes unchanged. The device context can be used in subsequent graphics device interface (GDI) functions to draw in the client area.  
  
 Unless the device context belongs to a window class, the [ReleaseDC](#releasedc) member function must be called to release the context after painting.  
  
 A device context belonging to the `CWnd` class is returned by the `GetDC` member function if **CS_CLASSDC**, **CS_OWNDC**, or **CS_PARENTDC** was specified as a style in the **WNDCLASS** structure when the class was registered.  
  
##  <a name="getdcex"></a>  CWnd::GetDCEx  
 Retrieves the handle of a device context for the `CWnd` window.  
  
```  
Capture de données modifiées* GetDCEx (CRgn* prgnClip,  
    Indicateurs DWORD) ;
```  
  
### Parameters  
 `prgnClip`  
 Identifies a clipping region that may be combined with the visible region of the client window.  
  
 `flags`  
 Can have one of the following preset values:  
  
- **DCX_CACHE** Returns a device context from the cache rather than the **OWNDC** or **CLASSDC** window. Overrides **CS_OWNDC** and **CS_CLASSDC**.  
  
- **DCX_CLIPCHILDREN** Excludes the visible regions of all child windows below the `CWnd` window.  
  
- **DCX_CLIPSIBLINGS** Excludes the visible regions of all sibling windows above the `CWnd` window.  
  
- **DCX_EXCLUDERGN** Excludes the clipping region identified by `prgnClip` from the visible region of the returned device context.  
  
- **DCX_INTERSECTRGN** Intersects the clipping region identified by `prgnClip` within the visible region of the returned device context.  
  
- **DCX_LOCKWINDOWUPDATE** Allows drawing even if there is a `LockWindowUpdate` call in effect that would otherwise exclude this window. This value is used for drawing during tracking.  
  
- **DCX_PARENTCLIP** Uses the visible region of the parent window and ignores the parent window's **WS_CLIPCHILDREN** and **WS_PARENTDC** style bits. This value sets the device context's origin to the upper-left corner of the `CWnd` window.  
  
- **DCX_WINDOW** Returns a device context that corresponds to the window rectangle rather than the client rectangle.  
  
### Return Value  
 The device context for the specified window if the function is successful; otherwise **NULL**.  
  
### Remarks  
 The device context can be used in subsequent GDI functions to draw in the client area.  
  
 This function, which is an extension to the [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) function, gives an application more control over how and whether a device context for a window is clipped.  
  
 Unless the device context belongs to a window class, the [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) function must be called to release the context after drawing. Since only five common device contexts are available at any given time, failure to release a device context can prevent other applications from gaining access to a device context.  
  
 To obtain a cached device context, an application must specify [DCX_CACHE](http://msdn.microsoft.com/library/windows/desktop/dd144873). If **DCX_CACHE** is not specified and the window is neither **CS_OWNDC** nor [CS_CLASSDC](http://msdn.microsoft.com/library/windows/desktop/ms633576), this function returns **NULL**.  
  
 A device context with special characteristics is returned by the [GetDCEx](http://msdn.microsoft.com/library/windows/desktop/dd144873) function if the **CS_CLASSDC**, [CS_OWNDC](http://msdn.microsoft.com/library/windows/desktop/ms633576), or [CS_PARENTDC](http://msdn.microsoft.com/library/windows/desktop/ms633576) style was specified in the [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure when the class was registered.  
  
 For more information about these characteristics, see the description of the **WNDCLASS** structure in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdcrendertarget"></a>  CWnd::GetDCRenderTarget  
 Retrieves the device context (DC) render target for the `CWnd` window.  
  
```  
CDCRenderTarget * GetDCRenderTarget() ;
```  
  
### Return Value  
 The device context render target for the specified window if the function is successful; otherwise **NULL**.  
  
### Remarks  
  
##  <a name="getdescendantwindow"></a>  CWnd::GetDescendantWindow  
 Call this member function to find the descendant window specified by the given ID.  
  
```  
CWnd * GetDescendantWindow (int nID,  
    BOOL bOnlyPerm = FALSE) const ;  
```  
  
### Parameters  
 `nID`  
 Specifies the identifier of the control or child window to be retrieved.  
  
 `bOnlyPerm`  
 Specifies whether the window to be returned can be temporary. If **TRUE**, only a permanent window can be returned; if **FALSE,** the function can return a temporary window. For more information on temporary windows see [Technical Note 3](../../mfc/tn003-mapping-of-windows-handles-to-objects.md).  
  
### Return Value  
 A pointer to a `CWnd` object, or **NULL** if no child window is found.  
  
### Remarks  
 This member function searches the entire tree of child windows, not only the windows that are immediate children.  
  
##  <a name="getdesktopwindow"></a>  CWnd::GetDesktopWindow  
 Returns the Windows desktop window.  
  
```  
statique CWnd * PASCAL GetDesktopWindow() ;
```  
  
### Return Value  
 Identifies the Windows desktop window. This pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The desktop window covers the entire screen and is the area on top of which all icons and other windows are painted.  
  
##  <a name="getdlgctrlid"></a>  CWnd::GetDlgCtrlID  
 Returns the window or control ID value for any child window, not only that of a control in a dialog box.  
  
```  
int GetDlgCtrlID() const ;  
```  
  
### Return Value  
 The numeric identifier of the `CWnd` child window if the function is successful; otherwise 0.  
  
### Remarks  
 Since top-level windows do not have an ID value, the return value of this function is invalid if the `CWnd` is a top-level window.  
  
### Example  
  See the example for [CWnd::OnCtlColor](#onctlcolor).  
  
##  <a name="getdlgitem"></a>  CWnd::GetDlgItem  
 Retrieves a pointer to the specified control or child window in a dialog box or other window.  
  
```  
CWnd * GetDlgItem(int nID) const ;  
  
void GetDlgItem (int nID,  
    HWND* phWnd) const ;  
```  
  
### Parameters  
 `nID`  
 Specifies the identifier of the control or child window to be retrieved.  
  
 `phWnd`  
 A pointer to a child window.  
  
### Return Value  
 A pointer to the given control or child window. If no control with the integer ID given by the `nID` parameter exists, the value is **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The pointer returned is usually cast to the type of control identified by `nID`.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#97](../../mfc/reference/codesnippet/cpp/cwnd-class_36.cpp)]  
  
##  <a name="getdlgitemint"></a>  CWnd::GetDlgItemInt  
 Retrieves the text of the control identified by `nID`.  
  
```  
UINT GetDlgItemInt (int nID,  
    BOOL * lpTrans = NULL,  
    BOOL bSigned = TRUE) const ;  
```  
  
### Parameters  
 `nID`  
 Specifies the integer identifier of the dialog-box control to be translated.  
  
 `lpTrans`  
 Points to the Boolean variable that is to receive the translated flag.  
  
 `bSigned`  
 Specifies whether the value to be retrieved is signed.  
  
### Return Value  
 Specifies the translated value of the dialog-box item text. Since 0 is a valid return value, `lpTrans` must be used to detect errors. If a signed return value is desired, cast it as an `int` type.  
  
 The function returns 0 if the translated number is greater than INT_MAX (for signed numbers) or UINT_MAX (for unsigned).  
  
 When errors occur, such as encountering nonnumeric characters and exceeding the above maximum, `GetDlgItemInt` copies 0 to the location pointed to by `lpTrans`. If there are no errors, `lpTrans` receives a nonzero value. If `lpTrans` is **NULL**, `GetDlgItemInt` does not warn about errors.  
  
### Remarks  
 It translates the text of the specified control in the given dialog box into an integer value by stripping any extra spaces at the beginning of the text and converting decimal digits. It stops the translation when it reaches the end of the text or encounters any nonnumeric character.  
  
 If `bSigned` is **TRUE**, `GetDlgItemInt` checks for a minus sign (–) at the beginning of the text and translates the text into a signed number. Otherwise, it creates an unsigned value.  
  
 It sends a [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627) message to the control.  
  
##  <a name="getdlgitemtext"></a>  CWnd::GetDlgItemText  
 Call this member function to retrieve the title or text associated with a control in a dialog box.  
  
```  
GetDlgItemText (int nID, de type int  
    LPTSTR lpStr,  
    int nMaxCount) const ;  
  
GetDlgItemText (int nID, de type int  
    CString se rString) const ;  
```  
  
### Parameters  
 `nID`  
 Specifies the integer identifier of the control whose title is to be retrieved.  
  
 `lpStr`  
 Points to the buffer to receive the control's title or text.  
  
 `nMaxCount`  
 Specifies the maximum length (in characters) of the string to be copied to `lpStr`. If the string is longer than `nMaxCount`, it is truncated.  
  
 `rString`  
 A reference to a [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### Return Value  
 Specifies the actual number of characters copied to the buffer, not including the terminating null character. The value is 0 if no text is copied.  
  
### Remarks  
 The `GetDlgItemText` member function copies the text to the location pointed to by `lpStr` and returns a count of the number of bytes it copies.  
  
##  <a name="getdsccursor"></a>  CWnd::GetDSCCursor  
 Call this member function to retrieve a pointer to the underlying cursor that is defined by the DataSource, UserName, Password, and SQL properties of the data-source control.  
  
```  
IUnknown * GetDSCCursor() ;
```  
  
### Return Value  
 A pointer to a cursor that is defined by a data-source control. MFC takes care of calling `AddRef` for the pointer.  
  
### Remarks  
 Use the returned pointer to set the ICursor property of a complex data-bound control, such as the data-bound grid control. A data-source control will not become active until the first bound control requests its cursor. This can happen either explicitly by a call to `GetDSCCursor` or implicitly by the MFC binding manager. In either case, you can force a data-source control to become active by calling `GetDSCCursor` and then calling **Release** on the returned pointer to **IUnknown**. Activation will cause the data-source control to attempt to connect to the underlying data source. The returned pointer might be used in the following context:  
  
### Example  
 [!code-cpp[NVC_MFC_AxDataBinding#1](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#5](../../mfc/reference/codesnippet/cpp/cwnd-class_37.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#3](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="getdynamiclayout"></a>  CWnd::GetDynamicLayout  
 Retrieves a pointer to the dynamic layout manager object.  
  
```  
CMFCDynamicLayout * GetDynamicLayout() ;
```  
  
### Return Value  
 A pointer to the dynamic layout manager object, or NULL if dynamic layout is not enabled.  
  
### Remarks  
 The window object owns and manages the lifetime of the returned pointer, so it should only be used to access the object; do not delete the pointer or store the pointer permanently.  
  
##  <a name="getexstyle"></a>  CWnd::GetExStyle  
 Returns the window's extended style.  
  
```  
GetExStyle() DWORD const ;  
```  
  
### Return Value  
 The window's extended style. For more information about the extended window styles used in MFC, see [Extended Window Styles](../../mfc/reference/extended-window-styles.md).  
  
##  <a name="getfocus"></a>  CWnd::GetFocus  
 Retrieves a pointer to the `CWnd` that currently has the input focus.  
  
```  
statique CWnd * PASCAL GetFocus() ;
```  
  
### Return Value  
 A pointer to the window that has the current focus, or **NULL** if there is no focus window.  
  
 The pointer may be temporary and should not be stored for later use.  
  
##  <a name="getfont"></a>  CWnd::GetFont  
 Sends the `WM_GETFONT` message to the window to retrieve the current font.  
  
```  
CFont * GetFont() const ;  
```  
  
### Return Value  
 Pointer to a [CFont](../../mfc/reference/cfont-class.md) object that is attached to the current font for the window.  
  
### Remarks  
 This method has no effect unless the window processes the `WM_GETFONT` message. Many MFC classes that derive from `CWnd` process this message because they are attached to a predefined window class that includes a message handler for the `WM_GETFONT` message. To use this method, classes that you derive from `CWnd` must define a method handler for the `WM_GETFONT` message.  
  
##  <a name="getforegroundwindow"></a>  CWnd::GetForegroundWindow  
 Returns a pointer to the foreground window (the window with which the user is currently working).  
  
```  
statique CWnd * PASCAL GetForegroundWindow() ;
```  
  
### Return Value  
 A pointer to the foreground window. This may be a temporary `CWnd` object.  
  
### Remarks  
 The foreground window applies only to top-level windows (frame windows or dialog boxes).  
  
##  <a name="geticon"></a>  CWnd::GetIcon  
 Call this member function to get the handle to either a big (32x32) or the handle to a small (16x16) icon, as indicated by `bBigIcon`.  
  
```  
GetIcon(BOOL bBigIcon) HICON const ;  
```  
  
### Parameters  
 `bBigIcon`  
 Specifies a 32 pixel by 32 pixel icon if **TRUE**; specifies a 16 pixel by 16 pixel icon if **FALSE**.  
  
### Return Value  
 A handle to an icon. If unsuccessful, returns **NULL**.  
  
##  <a name="getlastactivepopup"></a>  CWnd::GetLastActivePopup  
 Determines which pop-up window owned by `CWnd` was most recently active.  
  
```  
CWnd * GetLastActivePopup() const ;  
```  
  
### Return Value  
 Identifies the most recently active pop-up window. The return value will be the window itself if any of the following conditions are met:  
  
-   The window itself was most recently active.  
  
-   The window does not own any pop-up windows.  
  
-   The window is not a top-level window or is owned by another window.  
  
 The pointer may be temporary and should not be stored for later use.  
  
### Example  
  See the example for [CWnd::FindWindow](#findwindow).  
  
##  <a name="getlayeredwindowattributes"></a>  CWnd::GetLayeredWindowAttributes  
 Retrieves the opacity and transparency color key of a layered window.  
  
```  
BOOL GetLayeredWindowAttributes (COLORREF* pcrKey, octet* pbAlpha,  
    DWORD* pdwFlags) const ;  
```  
  
### Parameters  
 *pcrKey*  
 Pointer to a **COLORREF** value that receives the transparency color key to be used when composing the layered window. All pixels painted by the window in this color will be transparent. This can be **NULL** if the argument is not needed.  
  
 `pbAlpha`  
 Pointer to a **BYTE** that receives the Alpha value used to describe the opacity of the layered window. When the variable referred to by `pbAlpha` is 0, the window is completely transparent. When the variable referred to by `pbAlpha` is 255, the window is opaque. This can be **NULL** if the argument is not needed.  
  
 *pdwFlags*  
 Pointer to a `DWORD` that receives a layering flag. This can be **NULL** if the argument is not needed. For a complete list of possible values, see [GetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633508).  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [GetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633508), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getmenu"></a>  CWnd::GetMenu  
 Retrieves a pointer to the menu for this window.  
  
```  
CMenu * GetMenu() const ;  
```  
  
### Return Value  
 Identifies the menu. The value is **NULL** if `CWnd` has no menu. The return value is undefined if `CWnd` is a child window.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 This function should not be used for child windows because they do not have a menu.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#98](../../mfc/reference/codesnippet/cpp/cwnd-class_38.cpp)]  
  
##  <a name="getmenubarinfo"></a>  CWnd::GetMenuBarInfo  
 Retrieves information about the specified menu bar.  
  
```  
BOOL GetMenuBarInfo (LONG idObject,  
    LONG idItem,  
    PMENUBARINFO pmbi) const ;  
```  
  
### Parameters  
 `idObject`  
 Specifies the menu object. For a list of possible values, see [GetMenuBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms647833).  
  
 `idItem`  
 Specifies the item for which to retrieve information. If this parameter is zero, the function retrieves information about the menu itself. If this parameter is 1, the function retrieves information about the first item on the menu, and so on.  
  
 *pmbi*  
 Pointer to a [MENUBARINFO](http://msdn.microsoft.com/library/windows/desktop/ms647564) structure that receives the information.  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [GetMenuBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms647833), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnextdlggroupitem"></a>  CWnd::GetNextDlgGroupItem  
 Searches for the previous or next control within a group of controls in a dialog box.  
  
```  
CWnd* GetNextDlgGroupItem (CWnd* pWndCtl,  
    BOOL bPrevious = FALSE) const ;  
  
COleControlSiteOrWnd* GetNextDlgGroupItem (COleControlSiteOrWnd* pCurSiteOrWnd = NULL) const ;  
```  
  
### Parameters  
 `pWndCtl`  
 Identifies the control to be used as the starting point for the search.  
  
 `bPrevious`  
 Specifies how the function is to search the group of controls in the dialog box. If **TRUE**, the function searches for the previous control in the group; if **FALSE**, it searches for the next control in the group.  
  
 `pCurSiteOrWnd`  
 Identifies the **COleControlSiteOrWnd** control. For more information about `COleControlSiteOrWnd`, see **Remarks**.  
  
### Return Value  
 Pointer to the previous or next control in the group if the member function is successful.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 A group of controls begins with a control that was created with the [WS_GROUP](../../mfc/reference/window-styles.md) style and ends with the last control that was not created with the **WS_GROUP** style.  
  
 By default, the `GetNextDlgGroupItem` member function returns a pointer to the next control in the group. If `pWndCtl` identifies the first control in the group and `bPrevious` is **TRUE**, `GetNextDlgGroupItem` returns a pointer to the last control in the group.  
  
> [!NOTE]
>  Because MFC supports windowless ActiveX controls, standard ActiveX controls, and windows, referring to a control by only an HWND no longer suffices. The `COleControlSiteOrWnd` object includes information that identifies the object as a windowed ActiveX control, a windowless ActiveX control, or a window, as follows:  
  
|Control or window type|Identifying information|  
|----------------------------|-----------------------------|  
|Windowed ActiveX control|Contains an HWND and associates a [COleControlSite](../../mfc/reference/colecontrolsite-class.md) object with it. The `m_hWnd` member of `COleControlSiteOrWnd` is set to the HWND of the control, and the **m_pSite** member points to the control's `COleControlSite`.|  
|Windowless ActiveX control|Contains no `HWND`. The **m_pSite** member of `COleControlSiteOrWnd` points to the control's `COleControlSite`, and the **m_hWnd** member is **NULL**.|  
|Standard window|Contains just an `HWND`. The `m_hWnd` member of `COleControlSiteOrWnd` is set to the `HWND` of the window, and the **m_pSite** member is **NULL**.|  
  
##  <a name="getnextdlgtabitem"></a>  CWnd::GetNextDlgTabItem  
 Retrieves a pointer to the first control that was created with the [WS_TABSTOP](window-styles.md) style and that precedes or follows the specified control.  
  
```  
CWnd* GetNextDlgTabItem (CWnd* pWndCtl,  
    BOOL bPrevious = FALSE) const ;  
  
COleControlSiteOrWnd* GetNextDlgTabItem (COleControlSiteOrWnd* pCurSiteOrWnd,  
    BOOL bPrevious) const ;  
```  
  
### Parameters  
 `pWndCtl`  
 Identifies the control to be used as the starting point for the search.  
  
 `pCurSiteOrWnd`  
 Identifies the **COleControlSiteOrWnd** control. For more information about `COleControlSiteOrWnd`, see [CWnd::GetNextDlgGroupItem](#getnextdlggroupitem).  
  
 `bPrevious`  
 Specifies how the function is to search the dialog box. If **TRUE**, the function searches for the previous control in the dialog box; if **FALSE**, it searches for the next control.  
  
### Return Value  
 Pointer to the previous or next control that has the **WS_TABSTOP** style, if the member function is successful.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
 For more information about `COleControlSiteOrWnd`, see [CWnd::GetNextDlgGroupItem](#getnextdlggroupitem).  
  
##  <a name="getnextwindow"></a>  CWnd::GetNextWindow  
 Searches for the next (or previous) window in the window manager's list.  
  
```  
CWnd * GetNextWindow(UINT nFlag = GW_HWNDNEXT) const ;  
```  
  
### Parameters  
 `nFlag`  
 Specifies whether the function returns a pointer to the next window or the previous window. It can be either **GW_HWNDNEXT**, which returns the window that follows the `CWnd` object on the window manager's list, or **GW_HWNDPREV**, which returns the previous window on the window manager's list.  
  
### Return Value  
 Identifies the next (or the previous) window in the window manager's list if the member function is successful.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The window manager's list contains entries for all top-level windows, their associated child windows, and the child windows of any child windows.  
  
 If `CWnd` is a top-level window, the function searches for the next (or previous) top-level window; if `CWnd` is a child window, the function searches for the next (or previous) child window.  
  
##  <a name="getolecontrolsite"></a>  CWnd::GetOleControlSite  
 Retrieves the custom site for the specified ActiveX control.  
  
```  
GetOleControlSite(UINT idControl) COleControlSite * const ;  
```  
  
### Parameters  
 `idControl`  
 The ID of the ActiveX control.  
  
##  <a name="getopenclipboardwindow"></a>  CWnd::GetOpenClipboardWindow  
 Retrieves the handle of the window that currently has the Clipboard open.  
  
```  
statique CWnd * PASCAL GetOpenClipboardWindow() ;
```  
  
### Return Value  
 The handle of the window that currently has the Clipboard open if the function is successful; otherwise **NULL**.  
  
##  <a name="getowner"></a>  CWnd::GetOwner  
 Retrieves a pointer to the owner of the window.  
  
```  
CWnd * GetOwner() const ;  
```  
  
### Return Value  
 A pointer to a `CWnd` object.  
  
### Remarks  
 If the window has no owner, then a pointer to the parent window object is returned by default. Note that the relationship between the owner and the owned differs from the parent-child aspect in several important aspects. For example, a window with a parent is confined to its parent window's client area. Owned windows can be drawn at any location on the desktop.  
  
 The ownership concept of this function is different from the ownership concept of [GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms633515).  
  
##  <a name="getparent"></a>  CWnd::GetParent  
 Call this function to get a pointer to a child window's parent window (if any).  
  
```  
CWnd * GetParent() const ;  
```  
  
### Return Value  
 See the Return Values section in [GetParent](http://msdn.microsoft.com/library/windows/desktop/ms633510) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 The `GetParent` function returns a pointer to the immediate parent (if it exists). In contrast, the [GetParentOwner](#getparentowner) function returns a pointer to the most immediate parent or owner window that is not a child window (does not have the **WS_CHILD** style). If you have a child window within a child window `GetParent` and `GetParentOwner` return different results.  
  
##  <a name="getparentframe"></a>  CWnd::GetParentFrame  
 Call this member function to retrieve the parent frame window.  
  
```  
CFrameWnd * GetParentFrame() const ;  
```  
  
### Return Value  
 A pointer to a frame window if successful; otherwise **NULL**.  
  
### Remarks  
 The member function searches up the parent chain until a [CFrameWnd](../../mfc/reference/cframewnd-class.md) (or derived class) object is found.  
  
##  <a name="getparentowner"></a>  CWnd::GetParentOwner  
 Call this member function to get a pointer to a child window's parent window or owner window.  
  
```  
CWnd * GetParentOwner() const ;  
```  
  
### Return Value  
 A pointer to a `CWnd` object. If a `CWnd` object is not attached to the handle, a temporary `CWnd` object is created and attached. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 `GetParentOwner` returns a pointer to the most immediate parent or owner window that is not a child window (does not have the **WS_CHILD** style). The current owner window can be set with [SetOwner](#setowner). By default, the parent of a window is its owner.  
  
 In contrast, the [GetParent](#getparent) function returns a pointer to the immediate parent, whether it is a child window or not. If you have a child window within a child window `GetParent` and `GetParentOwner` return different results.  
  
##  <a name="getproperty"></a>  CWnd::GetProperty  
 Call this member function to get the ActiveX control property specified by `dwDispID`.  
  
```  
void GetProperty (DISPID dwDispID,  
    VARTYPE vtProp,  
    void * pvProp) const ;  
```  
  
### Parameters  
 `dwDispID`  
 Identifies the property to be retrieved.  
  
 `vtProp`  
 Specifies the type of the property to be retrieved. For possible values, see the Remarks section for [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvProp`  
 Address of the variable that will that will receive the property value. It must match the type specified by `vtProp`.  
  
### Remarks  
 **GetProperty** returns the value through `pvProp`.  
  
> [!NOTE]
>  This function should be called only on a `CWnd` object that represents an ActiveX control.  
  
 For more information about using this member function with ActiveX Control Containers, see the article [ActiveX Control Containers: Programming ActiveX Controls in an ActiveX Control Container](../../mfc/programming-activex-controls-in-a-activex-control-container.md).  
  
##  <a name="getrendertarget"></a>  CWnd::GetRenderTarget  
 Gets a render target that is associated with this window.  
  
```  
CHwndRenderTarget * GetRenderTarget() ;
```  
  
### Return Value  
 Pointer to the render target or NULL.  
  
##  <a name="getsafehwnd"></a>  CWnd::GetSafeHwnd  
 Returns `m_hWnd`, or **NULL** if the **this** pointer is **NULL**.  
  
```  
HWND GetSafeHwnd() const ;  
```  
  
### Return Value  
 Returns the window handle for a window. Returns **NULL** if the `CWnd` is not attached to a window or if it is used with a **NULL CWnd** pointer.  
  
### Example  
  See the example for [CWnd::SubclassWindow](#subclasswindow).  
  
##  <a name="getsafeowner"></a>  CWnd::GetSafeOwner  
 Call this member function to retrieve the owner window that should be used for dialog boxes or other modal windows.  
  
```  
CWnd statique* GetSafeOwner (CWnd* pParent = NULL,  
    HWND* pWndTop = NULL) ;
```  
  
### Parameters  
 `pParent`  
 A pointer to a parent `CWnd` window. May be **NULL**.  
  
 *pWndTop*  
 A pointer to the window that is currently on top. May be **NULL**.  
  
### Return Value  
 A pointer to the safe owner for the given window.  
  
### Remarks  
 The safe owner is the first non-child parent window of `pParent`. If `pParent` is **NULL**, the thread's main window (retrieved via [AfxGetMainWnd](../../mfc/reference/application-information-and-management.md#afxgetmainwnd)) is used to find an owner.  
  
> [!NOTE]
>  The framework itself uses this function to determine the correct owner window for dialog boxes and property sheets where the owner is not specified.  
  
##  <a name="getscrollbarctrl"></a>  CWnd::GetScrollBarCtrl  
 Call this member function to obtain a pointer to the specified sibling scroll bar or splitter window.  
  
```  
virtuel CScrollBar * GetScrollBarCtrl(int nBar) const ;  
```  
  
### Parameters  
 `nBar`  
 Specifies the type of scroll bar. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the position of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the position of the vertical scroll bar.  
  
### Return Value  
 A sibling scroll-bar control, or **NULL** if none.  
  
### Remarks  
 This member function does not operate on scroll bars created when the **WS_HSCROLL** or **WS_VSCROLL** bits are set during the creation of a window. The `CWnd` implementation of this function simply returns **NULL**. Derived classes, such as `CView`, implement the described functionality.  
  
##  <a name="getscrollbarinfo"></a>  CWnd::GetScrollBarInfo  
 Retrieves information about the specified scroll bar.  
  
```  
BOOL GetScrollBarInfo (LONG idObject,  
    PSCROLLBARINFO psbi) const ;  
```  
  
### Parameters  
 `idObject`  
 Specifies the menu object. For a list of possible values, see [GetScrollBarInfo](http://msdn.microsoft.com/library/windows/desktop/bb787581).  
  
 *psbi*  
 Pointer to a [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535) structure that receives the information.  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [GetScrollBarInfo](http://msdn.microsoft.com/library/windows/desktop/bb787581), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getscrollinfo"></a>  CWnd::GetScrollInfo  
 Call this member function to retrieve the information that the `SCROLLINFO` structure maintains about a scroll bar.  
  
```  
BOOL GetScrollInfo (int nBar,  
    LPSCROLLINFO lpScrollInfo,  
    UINT nMask = SIF_ALL) ;
```  
  
### Parameters  
 `nBar`  
 Specifies whether the scroll bar is a control or part of a window's nonclient area. If it is part of the nonclient area, `nBar` also indicates whether the scroll bar is positioned horizontally, vertically, or both. It must be one of the following:  
  
- **SB_CTL** Retrieves the parameters for a scroll bar control. The `m_hWnd` data member must be the handle of the scroll bar control.  
  
- **SB_HORZ** Retrieves the parameters for the window's standard horizontal scroll bar.  
  
- **SB_VERT** Retrieves the parameters for the window's standard vertical scroll bar.  
  
 `lpScrollInfo`  
 A pointer to a [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) structure. See the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information about this structure.  
  
 `nMask`  
 Specifies the scroll bar parameters to retrieve. The default specifies a combination of **SIF_PAGE**, **SIF_POS**, **SIF_TRACKPOS**, and **SIF_RANGE**. See `SCROLLINFO` for more information on the *nMask* values.  
  
### Return Value  
 If the message retrieved any values, the return is **TRUE**. Otherwise, it is **FALSE**.  
  
### Remarks  
 `GetScrollInfo` enables applications to use 32-bit scroll positions.  
  
 The [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) structure contains information about a scroll bar, including the minimum and maximum scrolling positions, the page size, and the position of the scroll box (the thumb). See the `SCROLLINFO` structure topic in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information about changing the structure defaults.  
  
 The MFC Windows message handlers that indicate scroll-bar position, [CWnd::OnHScroll](#onhscroll) and [CWnd::OnVScroll](#onvscroll), provide only 16 bits of position data. `GetScrollInfo` and `SetScrollInfo` provide 32 bits of scroll-bar position data. Thus, an application can call `GetScrollInfo` while processing either `CWnd::OnHScroll` or `CWnd::OnVScroll` to obtain 32-bit scroll-bar position data.  
  
##  <a name="getscrolllimit"></a>  CWnd::GetScrollLimit  
 Call this member function to retrieve the maximum scrolling position of the scroll bar.  
  
```  
int GetScrollLimit (int nBar) ;
```  
  
### Parameters  
 `nBar`  
 Specifies the type of scroll bar. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the scroll limit of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the scroll limit of the vertical scroll bar.  
  
### Return Value  
 Specifies the maximum position of a scroll bar if successful; otherwise 0.  
  
##  <a name="getscrollpos"></a>  CWnd::GetScrollPos  
 Retrieves the current position of the scroll box of a scroll bar.  
  
```  
int GetScrollPos (int nBar) const ;  
```  
  
### Parameters  
 `nBar`  
 Specifies the scroll bar to examine. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the position of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the position of the vertical scroll bar.  
  
### Return Value  
 Specifies the current position of the scroll box in the scroll bar if successful; otherwise 0.  
  
### Remarks  
 The current position is a relative value that depends on the current scrolling range. For example, if the scrolling range is 50 to 100 and the scroll box is in the middle of the bar, the current position is 75.  
  
##  <a name="getscrollrange"></a>  CWnd::GetScrollRange  
 Copies the current minimum and maximum scroll-bar positions for the given scroll bar to the locations specified by `lpMinPos` and `lpMaxPos`.  
  
```  
void GetScrollRange (int nBar,  
    LPINT lpMinPos,  
    LPINT lpMaxPos) const ;  
```  
  
### Parameters  
 `nBar`  
 Specifies the scroll bar to examine. The parameter can take one of the following values:  
  
- **SB_HORZ** Retrieves the position of the horizontal scroll bar.  
  
- **SB_VERT** Retrieves the position of the vertical scroll bar.  
  
 `lpMinPos`  
 Points to the integer variable that is to receive the minimum position.  
  
 `lpMaxPos`  
 Points to the integer variable that is to receive the maximum position.  
  
### Remarks  
 If `CWnd` does not have a scroll bar, then the `GetScrollRange` member function copies 0 to `lpMinPos` and `lpMaxPos`.  
  
 The default range for a standard scroll bar is 0 to 100. The default range for a scroll-bar control is empty (both values are 0).  
  
##  <a name="getstyle"></a>  CWnd::GetStyle  
 Returns the current window style.  
  
```  
DWORD GetStyle() const ;  
```  
  
### Return Value  
 The window's style. For more information about the window styles used in MFC, see [Window Styles](../../mfc/reference/window-styles.md).  
  
##  <a name="getsystemmenu"></a>  CWnd::GetSystemMenu  
 Allows the application to access the Control menu for copying and modification.  
  
```  
CMenu * GetSystemMenu(BOOL bRevert) const ;  
```  
  
### Parameters  
 `bRevert`  
 Specifies the action to be taken. If `bRevert` is **FALSE**, `GetSystemMenu` returns a handle to a copy of the Control menu currently in use. This copy is initially identical to the Control menu but can be modified. If `bRevert` is **TRUE**, `GetSystemMenu` resets the Control menu back to the default state. The previous, possibly modified, Control menu, if any, is destroyed. The return value is undefined in this case.  
  
### Return Value  
 Identifies a copy of the Control menu if `bRevert` is **FALSE**. If `bRevert` is **TRUE**, the return value is undefined.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 Any window that does not use `GetSystemMenu` to make its own copy of the Control menu receives the standard Control menu.  
  
 The pointer returned by the `GetSystemMenu` member function can be used with the [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu), or [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu) functions to change the Control menu.  
  
 The Control menu initially contains items identified with various ID values such as **SC_CLOSE**, **SC_MOVE**, and **SC_SIZE**. Items on the Control menu generate [WM_SYSCOMMAND](#onsyscommand) messages. All predefined Control-menu items have ID numbers greater than 0xF000. If an application adds items to the Control menu, it should use ID numbers less than F000.  
  
 Windows may automatically make items unavailable on the standard Control menu. `CWnd` can carry out its own selection or unavailability by responding to the [WM_INITMENU](#oninitmenu) messages, which are sent before any menu is displayed.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#99](../../mfc/reference/codesnippet/cpp/cwnd-class_39.cpp)]  
  
##  <a name="gettitlebarinfo"></a>  CWnd::GetTitleBarInfo  
 Retrieves information about the specified title bar.  
  
```  
BOOL GetTitleBarInfo(PTITLEBARINFO pti) const ;  
```  
  
### Parameters  
 *pti*  
 Pointer to a [TITLEBARINFO](http://msdn.microsoft.com/library/windows/desktop/ms632608) structure that receives the information.  
  
### Remarks  
 This member function emulates the functionality of the function [GetTitleBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms633513), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettoplevelframe"></a>  CWnd::GetTopLevelFrame  
 Call this member function to retrieve the window's top level frame window, if any.  
  
```  
CFrameWnd * GetTopLevelFrame() const ;  
```  
  
### Return Value  
 Identifies the top-level frame window of the window.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 If `CWnd` has no attached window, or its top-level parent is not a [CFrameWnd](../../mfc/reference/cframewnd-class.md)-derived object, this function returns **NULL**.  
  
##  <a name="gettoplevelowner"></a>  CWnd::GetTopLevelOwner  
 Call this member function to retrieve the top-level window.  
  
```  
CWnd * GetTopLevelOwner() const ;  
```  
  
### Return Value  
 Identifies the top-level window. The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The top-level window is the window that is a child of the desktop. If `CWnd` has no attached window, this function returns **NULL**.  
  
##  <a name="gettoplevelparent"></a>  CWnd::GetTopLevelParent  
 Call this member function to retrieve the window's top-level parent.  
  
```  
CWnd * GetTopLevelParent() const ;  
```  
  
### Return Value  
 Identifies the top-level parent window of the window.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 `GetTopLevelParent` is similar to [GetTopLevelFrame](#gettoplevelframe) and [GetTopLevelOwner](#gettoplevelowner); however, it ignores the value set as the current owner window.  
  
##  <a name="gettopwindow"></a>  CWnd::GetTopWindow  
 Searches for the top-level child window that belongs to `CWnd`.  
  
```  
CWnd * GetTopWindow() const ;  
```  
  
### Return Value  
 Identifies the top-level child window in a `CWnd` linked list of child windows. If no child windows exist, the value is **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 If `CWnd` has no children, this function returns **NULL**.  
  
##  <a name="getupdaterect"></a>  CWnd::GetUpdateRect  
 Retrieves the coordinates of the smallest rectangle that completely encloses the update region.  
  
```  
BOOL GetUpdateRect (LPRECT lpRect,  
    BOOL bErase = FALSE) ;
```  
  
### Parameters  
 `lpRect`  
 Points to a `CRect` object or [RECT structure](../../mfc/reference/rect-structure1.md) that is to receive the client coordinates of the update that encloses the update region.  
  
 Set this parameter to **NULL** to determine whether an update region exists within the `CWnd`. If `lpRect` is **NULL**, the `GetUpdateRect` member function returns nonzero if an update region exists and 0 if one does not. This provides a way to determine whether a `WM_PAINT` message resulted from an invalid area. Do not set this parameter to **NULL** in Windows version 3.0 and earlier.  
  
 `bErase`  
 Specifies whether the background in the update region is to be erased.  
  
### Return Value  
 Specifies the status of the update region. The value is nonzero if the update region is not empty; otherwise 0.  
  
 If the `lpRect` parameter is set to **NULL**, the return value is nonzero if an update region exists; otherwise 0.  
  
### Remarks  
 If `CWnd` was created with the **CS_OWNDC** style and the mapping mode is not `MM_TEXT`, the `GetUpdateRect` member function gives the rectangle in logical coordinates. Otherwise, `GetUpdateRect` gives the rectangle in client coordinates. If there is no update region, `GetUpdateRect` sets the rectangle to be empty (sets all coordinates to 0).  
  
 The `bErase` parameter specifies whether `GetUpdateRect` should erase the background of the update region. If `bErase` is **TRUE** and the update region is not empty, the background is erased. To erase the background, `GetUpdateRect` sends the [WM_ERASEBKGND](#onerasebkgnd) message.  
  
 The update rectangle retrieved by the [BeginPaint](#beginpaint) member function is identical to that retrieved by the `GetUpdateRect` member function.  
  
 The `BeginPaint` member function automatically validates the update region, so any call to `GetUpdateRect` made immediately after a call to `BeginPaint` retrieves an empty update region.  
  
##  <a name="getupdatergn"></a>  CWnd::GetUpdateRgn  
 Retrieves the update region into a region identified by `pRgn`.  
  
```  
int GetUpdateRgn (CRgn * pRgn,  
    BOOL bErase = FALSE) ;
```  
  
### Parameters  
 `pRgn`  
 Identifies the update region.  
  
 `bErase`  
 Specifies whether the background will be erased and nonclient areas of child windows will be drawn. If the value is **FALSE**, no drawing is done.  
  
### Return Value  
 Specifies a short-integer flag that indicates the type of resulting region. The value can take any one of the following:  
  
- **SIMPLEREGION** The region has no overlapping borders.  
  
- **COMPLEXREGION** The region has overlapping borders.  
  
- **NULLREGION** The region is empty.  
  
- **ERROR** No region was created.  
  
### Remarks  
 The coordinates of this region are relative to the upper-left corner (client coordinates).  
  
 The [BeginPaint](#beginpaint) member function automatically validates the update region, so any call to `GetUpdateRgn` made immediately after a call to `BeginPaint` retrieves an empty update region.  
  
##  <a name="getwindow"></a>  CWnd::GetWindow  
 Returns a pointer to the window requested, or **NULL** if none.  
  
```  
CWnd * GetWindow(UINT nCmd) const ;  
```  
  
### Parameters  
 `nCmd`  
 Specifies the relationship between `CWnd` and the returned window. It can take one of the following values:  
  
- **GW_CHILD** Identifies the `CWnd` first child window.  
  
- **GW_HWNDFIRST** If `CWnd` is a child window, returns the first sibling window. Otherwise, it returns the first top-level window in the list.  
  
- **GW_HWNDLAST** If `CWnd` is a child window, returns the last sibling window. Otherwise, it returns the last top-level window in the list.  
  
- **GW_HWNDNEXT** Returns the next window on the window manager's list.  
  
- **GW_HWNDPREV** Returns the previous window on the window manager's list.  
  
- **GW_OWNER** Identifies the `CWnd` owner.  
  
### Return Value  
 The returned pointer may be temporary and should not be stored for later use.  
  
##  <a name="getwindowcontexthelpid"></a>  CWnd::GetWindowContextHelpId  
 Call this member function to retrieve the help context identifier, if any, associated with the window.  
  
```  
GetWindowContextHelpId() DWORD const ;  
```  
  
### Return Value  
 The help context identifier. Returns 0 if the window has none.  
  
##  <a name="getwindowedchildcount"></a>  CWnd::GetWindowedChildCount  
 Call this member function to retrieve the number of associated child windows.  
  
```  
long GetWindowedChildCount() ;
```  
  
### Return Value  
 The number of child windows associated with the `CWnd` object.  
  
##  <a name="getwindowdc"></a>  CWnd::GetWindowDC  
 Retrieves the display context for the entire window, including caption bar, menus, and scroll bars.  
  
```  
CDC * GetWindowDC() ;
```  
  
### Return Value  
 Identifies the display context for the given window if the function is successful; otherwise **NULL**.  
  
 The returned pointer may be temporary and should not be stored for later use. [ReleaseDC](#releasedc) should be called once for each successful call to `GetWindowDC`.  
  
### Remarks  
 A window display context permits painting anywhere in `CWnd`, since the origin of the context is the upper-left corner of `CWnd` instead of the client area.  
  
 Default attributes are assigned to the display context each time it retrieves the context. Previous attributes are lost.  
  
 `GetWindowDC` is intended to be used for special painting effects within the `CWnd` nonclient area. Painting in nonclient areas of any window is not recommended.  
  
 The [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) Windows function can be used to retrieve the dimensions of various parts of the nonclient area, such as the caption bar, menu, and scroll bars.  
  
 After painting is complete, the [ReleaseDC](#releasedc) member function must be called to release the display context. Failure to release the display context will seriously affect painting requested by applications due to limitations on the number of device contexts that can be open at the same time.  
  
##  <a name="getwindowinfo"></a>  CWnd::GetWindowInfo  
 Retrieves information about the window.  
  
```  
BOOL GetWindowInfo(PWINDOWINFO pwi) const ;  
```  
  
### Parameters  
 *pwi*  
 A pointer to a [WINDOWINFO](http://msdn.microsoft.com/library/windows/desktop/ms632610) structure.  
  
### Remarks  
 This member function emulates the functionality of the function [GetWindowInfo](http://msdn.microsoft.com/library/windows/desktop/ms633516), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getwindowlesschildcount"></a>  CWnd::GetWindowlessChildCount  
 Retrieves the number of associated windowless child windows.  
  
```  
long GetWindowlessChildCount() ;
```  
  
### Return Value  
 The number of windowless child windows associated with the `CWnd` object.  
  
##  <a name="getwindowplacement"></a>  CWnd::GetWindowPlacement  
 Retrieves the show state and the normal (restored), minimized, and maximized positions of a window.  
  
```  
BOOL GetWindowPlacement(WINDOWPLACEMENT* lpwndpl) const ;  
```  
  
### Parameters  
 `lpwndpl`  
 Points to the `WINDOWPLACEMENT` structure that receives the show state and position information.  
  
### Return Value  
 Nonzero if the function is successful; otherwise 0.  
  
### Remarks  
 The **flags** member of the [WINDOWPLACEMENT](../../mfc/reference/windowplacement-structure.md) structure retrieved by this function is always 0. If `CWnd` is maximized, the **showCmd** member of `WINDOWPLACEMENT` is **SW_SHOWMAXIMIZED**. If the window is minimized, it is **SW_SHOWMINIMIZED.** It is **SW_SHOWNORMAL** otherwise.  
  
##  <a name="getwindowrect"></a>  CWnd::GetWindowRect  
 Copies the dimensions of the bounding rectangle of the `CWnd` object to the structure pointed to by `lpRect`.  
  
```  
void GetWindowRect (LPRECT lpRect) const ;  
```  
  
### Parameters  
 `lpRect`  
 Points to a `CRect` object or a [RECT structure](../../mfc/reference/rect-structure1.md) that will receive the screen coordinates of the upper-left and lower-right corners.  
  
### Remarks  
 The dimensions are given in screen coordinates relative to the upper-left corner of the display screen. The dimensions of the caption, border, and scroll bars, if present, are included.  
  
##  <a name="getwindowrgn"></a>  CWnd::GetWindowRgn  
 Call this member function to get the window region of a window.  
  
```  
int GetWindowRgn (HRGN hRgn) const ;  
```  
  
### Parameters  
 `hRgn`  
 A handle to a window region.  
  
### Return Value  
 The return value specifies the type of the region that the function obtains. It can be one of the following values:  
  
- **NULLREGION** The region is empty.  
  
- **SIMPLEREGION** The region is a single rectangle.  
  
- **COMPLEXREGION** The region is more than one rectangle.  
  
- **ERROR** An error occurred; the region is unaffected.  
  
### Remarks  
 The window region determines the area within the window where the operating system permits drawing. The operating system does not display any portion of a window that lies outside of the window region.  
  
 The coordinates of a window's window region are relative to the upper-left corner of the window, not the client area of the window.  
  
 To set the window region of a window, call [CWnd::SetWindowRgn](#setwindowrgn).  
  
##  <a name="getwindowtext"></a>  CWnd::GetWindowText  
 Copies the `CWnd` caption title (if it has one) into the buffer pointed to by `lpszStringBuf` or into the destination string `rString`.  
  
```  
int GetWindowText (LPTSTR lpszStringBuf,  
    int nMaxCount) const ;  
  
void GetWindowText (CString se rString) const ;  
```  
  
### Parameters  
 `lpszStringBuf`  
 Points to the buffer that is to receive the copied string of the window's title.  
  
 `nMaxCount`  
 Specifies the maximum number of characters to be copied to the buffer, including the terminating null character. If the string is longer than the number of characters specified in `nMaxCount`, it is truncated.  
  
 `rString`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) object that is to receive the copied string of the window's title.  
  
### Return Value  
 Specifies the length, in characters, of the copied string, not including the terminating null character. It is 0 if `CWnd` has no caption or if the caption is empty.  
  
### Remarks  
 If the `CWnd` object is a control, the `GetWindowText` member function copies the text within the control instead of copying the caption.  
  
 This member function causes the [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627) message to be sent to the `CWnd` object.  
  
### Example  
  See the example for [CWnd::SetWindowText](#setwindowtext).  
  
##  <a name="getwindowtextlength"></a>  CWnd::GetWindowTextLength  
 Returns the length of the `CWnd` object caption title.  
  
```  
int GetWindowTextLength() const ;  
```  
  
### Return Value  
 Specifies the text length in characters, not including any null-termination character. The value is 0 if no such text exists.  
  
### Remarks  
 If `CWnd` is a control, the `GetWindowTextLength` member function returns the length of the text within the control instead of the caption.  
  
 This member function causes the [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628) message to be sent to the `CWnd` object.  
  
### Example  
  See the example for [CWnd::SetWindowText](#setwindowtext).  
  
##  <a name="hidecaret"></a>  CWnd::HideCaret  
 Hides the caret by removing it from the display screen.  
  
```  
void HideCaret() ;
```  
  
### Remarks  
 Although the caret is no longer visible, it can be displayed again by using the [ShowCaret](#showcaret) member function. Hiding the caret does not destroy its current shape.  
  
 Hiding is cumulative. If `HideCaret` has been called five times in a row, the `ShowCaret` member function must be called five times before the caret will be shown.  
  
##  <a name="hilitemenuitem"></a>  CWnd::HiliteMenuItem  
 Highlights or removes the highlight from a top-level (menu-bar) menu item.  
  
```  
BOOL HiliteMenuItem (CMenu * pMenu,  
    UINT nIDHiliteItem,  
    UINT nHilite) ;
```  
  
### Parameters  
 `pMenu`  
 Identifies the top-level menu that contains the item to be highlighted.  
  
 `nIDHiliteItem`  
 Specifies the menu item to be highlighted, depending on the value of the `nHilite` parameter.  
  
 `nHilite`  
 Specifies whether the menu item is highlighted or the highlight is removed. It can be a combination of **MF_HILITE** or **MF_UNHILITE** with **MF_BYCOMMAND** or **MF_BYPOSITION**. The values can be combined using the bitwise OR operator. These values have the following meanings:  
  
- **MF_BYCOMMAND** Interprets `nIDHiliteItem` as the menu-item ID (the default interpretation).  
  
- **MF_BYPOSITION** Interprets `nIDHiliteItem` as the zero-based offset of the menu item.  
  
- **MF_HILITE** Highlights the item. If this value is not given, the highlight is removed from the item.  
  
- **MF_UNHILITE** Removes the highlight from the item.  
  
### Return Value  
 Specifies whether the menu item was highlighted. Nonzero if the item was highlighted; otherwise 0.  
  
### Remarks  
 The **MF_HILITE** and **MF_UNHILITE** flags can be used only with this member function; they cannot be used with the [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu) member function.  
  
##  <a name="htmlhelp"></a>  CWnd::HtmlHelp  
 Call this member function to invoke the HTMLHelp application.  
  
```  
HtmlHelp void virtuel (dwData DWORD_PTR,  
    UINT nCmd = 0x000F) ;
```  
  
### Parameters  
 `dwData`  
 Specifies additional data. The value used depends on the value of the `nCmd` parameter.  
  
 `nCmd`  
 Specifies the type of help requested. For a list of possible values and how they affect the `dwData` parameter, see the `uCommand` parameter described in the HTML Help API Reference in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Remarks  
 See [CWinApp::HtmlHelp](../../mfc/reference/cwinapp-class.md#htmlhelp) for more information.  
  
##  <a name="initdynamiclayout"></a>  CWnd::InitDynamicLayout  
 Called by the framework to initialize dynamic layout for a window.  
  
```  
void InitDynamicLayout() ;
```  
  
### Remarks  
 Do not call this method directly.  
  
##  <a name="invalidate"></a>  CWnd::Invalidate  
 Invalidates the entire client area of `CWnd`.  
  
```  
void Invalidate (BOOL bErase = TRUE) ;
```  
  
### Parameters  
 `bErase`  
 Specifies whether the background within the update region is to be erased.  
  
### Remarks  
 The client area is marked for painting when the next [WM_PAINT](#onpaint) message occurs. The region can also be validated before a `WM_PAINT` message occurs by the [ValidateRect](#validaterect) or [ValidateRgn](#validatergn) member function.  
  
 The `bErase` parameter specifies whether the background within the update area is to be erased when the update region is processed. If `bErase` is **TRUE**, the background is erased when the [BeginPaint](#beginpaint) member function is called; if `bErase` is **FALSE**, the background remains unchanged. If `bErase` is **TRUE** for any part of the update region, the background in the entire region, not just in the given part, is erased.  
  
 Windows sends a [WM_PAINT](#onpaint) message whenever the `CWnd` update region is not empty and there are no other messages in the application queue for that window.  
  
### Example  
  See the example for [CWnd::UpdateWindow](#updatewindow).  
  
##  <a name="invalidaterect"></a>  CWnd::InvalidateRect  
 Invalidates the client area within the given rectangle by adding that rectangle to the `CWnd` update region.  
  
```  
void InvalidateRect (LPCRECT lpRect,  
    BOOL bErase = TRUE) ;
```  
  
### Parameters  
 `lpRect`  
 Points to a `CRect` object or a [RECT structure](../../mfc/reference/rect-structure1.md) that contains the rectangle (in client coordinates) to be added to the update region. If `lpRect` is **NULL**, the entire client area is added to the region.  
  
 `bErase`  
 Specifies whether the background within the update region is to be erased.  
  
### Remarks  
 The invalidated rectangle, along with all other areas in the update region, is marked for painting when the next [WM_PAINT](#onpaint) message is sent. The invalidated areas accumulate in the update region until the region is processed when the next `WM_PAINT` call occurs, or until the region is validated by the [ValidateRect](#validaterect) or [ValidateRgn](#validatergn) member function.  
  
 The `bErase` parameter specifies whether the background within the update area is to be erased when the update region is processed. If `bErase` is **TRUE**, the background is erased when the [BeginPaint](#beginpaint) member function is called; if `bErase` is **FALSE**, the background remains unchanged. If `bErase` is **TRUE** for any part of the update region, the background in the entire region is erased, not just in the given part.  
  
 Windows sends a [WM_PAINT](#onpaint) message whenever the `CWnd` update region is not empty and there are no other messages in the application queue for that window.  
  
##  <a name="invalidatergn"></a>  CWnd::InvalidateRgn  
 Invalidates the client area within the given region by adding it to the current update region of `CWnd`.  
  
```  
void InvalidateRgn (CRgn * pRgn,  
    BOOL bErase = TRUE) ;
```  
  
### Parameters  
 `pRgn`  
 A pointer to a [CRgn](../../mfc/reference/crgn-class.md) object that identifies the region to be added to the update region. The region is assumed to have client coordinates. If this parameter is **NULL**, the entire client area is added to the update region.  
  
 `bErase`  
 Specifies whether the background within the update region is to be erased.  
  
### Remarks  
 The invalidated region, along with all other areas in the update region, is marked for painting when the [WM_PAINT](#onpaint) message is next sent. The invalidated areas accumulate in the update region until the region is processed when a `WM_PAINT` message is next sent, or until the region is validated by the [ValidateRect](#validaterect) or [ValidateRgn](#validatergn) member function.  
  
 The `bErase` parameter specifies whether the background within the update area is to be erased when the update region is processed. If `bErase` is **TRUE**, the background is erased when the [BeginPaint](#beginpaint) member function is called; if `bErase` is **FALSE**, the background remains unchanged. If `bErase` is **TRUE** for any part of the update region, the background in the entire region, not just in the given part, is erased.  
  
 Windows sends a [WM_PAINT](#onpaint) message whenever the `CWnd` update region is not empty and there are no other messages in the application queue for that window.  
  
 The given region must have been previously created by one of the region functions.  
  
##  <a name="invokehelper"></a>  CWnd::InvokeHelper  
 Call this member function to invoke the ActiveX Control method or property specified by `dwDispID`, in the context specified by `wFlags`.  
  
```  
void AFX_CDECL InvokeHelper (DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet, octet const* pbParamInfo,  
 ...);
```  
  
### Parameters  
 `dwDispID`  
 Identifies the method or property to be invoked.  
  
 `wFlags`  
 Flags describing the context of the call to **IDispatch::Invoke**.  
  
 `vtRet`  
 Specifies the type of the return value. For possible values, see the Remarks section for [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvRet`  
 Address of the variable that will that will receive the property value or return value. It must match the type specified by `vtRet`.  
  
 `pbParamInfo`  
 Pointer to a null-terminated string of bytes specifying the types of the parameters following `pbParamInfo`. For possible values, see the Remarks section for `COleDispatchDriver::InvokeHelper`.  
  
 *...*  
 Variable List of parameters, of types specified in `pbParamInfo`.  
  
### Remarks  
 The `pbParamInfo` parameter specifies the types of the parameters passed to the method or property. The variable list of arguments is represented by *...* in the syntax declaration.  
  
 This function converts the parameters to **VARIANTARG** values, then invokes the **IDispatch::Invoke** method on the ActiveX control. If the call to **IDispatch::Invoke** fails, this function will throw an exception. If the `SCODE` (status code) returned by **IDispatch::Invoke** is `DISP_E_EXCEPTION`, this function throws a [COleException](../../mfc/reference/coleexception-class.md) object, otherwise it throws a [COleDispatchException](../../mfc/reference/coledispatchexception-class.md).  
  
> [!NOTE]
>  This function should be called only on a `CWnd` object that represents an ActiveX control.  
  
 For more information about using this member function with ActiveX Control Containers, see the article [ActiveX Control Containers: Programming ActiveX Controls in an ActiveX Control Container](../../mfc/programming-activex-controls-in-a-activex-control-container.md).  
  
##  <a name="ischild"></a>  CWnd::IsChild  
 Indicates whether the window specified by `pWnd` is a child window or other direct descendant of `CWnd`.  
  
```  
BOOL IsChild(const CWnd* pWnd) const ;  
```  
  
### Parameters  
 `pWnd`  
 Identifies the window to be tested.  
  
### Return Value  
 Specifies the outcome of the function. The value is nonzero if the window identified by `pWnd` is a child window of `CWnd`; otherwise 0.  
  
### Remarks  
 A child window is the direct descendant of `CWnd` if the `CWnd` object is in the chain of parent windows that leads from the original pop-up window to the child window.  
  
##  <a name="isd2dsupportenabled"></a>  CWnd::IsD2DSupportEnabled  
 Determines whether D2D support is enabled.  
  
```  
BOOL IsD2DSupportEnabled() ;
```  
  
### Return Value  
 TRUE if the feature is enabled; otherwise FALSE.  
  
##  <a name="isdialogmessage"></a>  CWnd::IsDialogMessage  
 Call this member function to determine whether the given message is intended for a modeless dialog box; if it is, this function processes the message.  
  
```  
BOOL IsDialogMessage(LPMSG lpMsg) ;
```  
  
### Parameters  
 `lpMsg`  
 Points to an [MSG](../../mfc/reference/msg-structure1.md) structure that contains the message to be checked.  
  
### Return Value  
 Specifies whether the member function has processed the given message. It is nonzero if the message has been processed; otherwise 0. If the return is 0, call the [CWnd::PreTranslateMessage](#pretranslatemessage) member function of the base class to process the message. In an override of the `CWnd::PreTranslateMessage` member function the code looks like this :  
  
 [!code-cpp[NVC_MFCWindowing#100](../../mfc/reference/codesnippet/cpp/cwnd-class_40.cpp)]  
  
### Remarks  
 When the `IsDialogMessage` function processes a message, it checks for keyboard messages and converts them to selection commands for the corresponding dialog box. For example, the TAB key selects the next control or group of controls, and the DOWN ARROW key selects the next control in a group.  
  
 You must not pass a message processed by `IsDialogMessage` to the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) or [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows functions, because it has already been processed.  
  
##  <a name="isdlgbuttonchecked"></a>  CWnd::IsDlgButtonChecked  
 Determines whether a button control has a check mark next to it.  
  
```  
UINT IsDlgButtonChecked(int nIDButton) const ;  
```  
  
### Parameters  
 `nIDButton`  
 Specifies the integer identifier of the button control.  
  
### Return Value  
 Nonzero if the given control is checked, and 0 if it is not checked. Only radio buttons and check boxes can be checked. For three-state buttons, the return value can be 2 if the button is indeterminate. This member function returns 0 for a pushbutton.  
  
### Remarks  
 If the button is a three-state control, the member function determines whether it is dimmed, checked, or neither.  
  
##  <a name="isdynamiclayoutenabled"></a>  CWnd::IsDynamicLayoutEnabled  
 Determines whether dynamic layout is enabled on this window. If dynamic layout is enabled, the position and size of child windows can change when the user resizes the parent window.  
  
```  
BOOL IsDynamicLayoutEnabled() const ;  
```  
  
### Return Value  
 TRUE if dynamic layout is enabled; otherwise FALSE.  
  
### Remarks  
  
##  <a name="isiconic"></a>  CWnd::IsIconic  
 Specifies whether `CWnd` is minimized (iconic).  
  
```  
BOOL IsIconic() const ;  
```  
  
### Return Value  
 Nonzero if `CWnd` is minimized; otherwise 0.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#101](../../mfc/reference/codesnippet/cpp/cwnd-class_41.cpp)]  
  
##  <a name="istouchwindow"></a>  CWnd::IsTouchWindow  
 Specifies whether `CWnd` has touch support.  
  
```  
BOOL IsTouchWindow() const ;  
```  
  
### Return Value  
 `TRUE` if `CWnd` has touch support; otherwise `FALSE`.  
  
### Remarks  
  
##  <a name="iswindowenabled"></a>  CWnd::IsWindowEnabled  
 Specifies whether `CWnd` is enabled for mouse and keyboard input.  
  
```  
BOOL IsWindowEnabled() const ;  
```  
  
### Return Value  
 Nonzero if `CWnd` is enabled; otherwise 0.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#102](../../mfc/reference/codesnippet/cpp/cwnd-class_42.cpp)]  
  
##  <a name="iswindowvisible"></a>  CWnd::IsWindowVisible  
 Determines the visibility state of the given window.  
  
```  
BOOL IsWindowVisible() const ;  
```  
  
### Return Value  
 Nonzero if `CWnd` is visible (has the [WS_VISIBLE](../../mfc/reference/window-styles.md) style bit set, and parent window is visible). Because the return value reflects the state of the **WS_VISIBLE** style bit, the return value may be nonzero even though `CWnd` is totally obscured by other windows.  
  
### Remarks  
 A window possesses a visibility state indicated by the **WS_VISIBLE** style bit. When this style bit is set with a call to the [ShowWindow](#showwindow) member function, the window is displayed and subsequent drawing to the window is displayed as long as the window has the style bit set.  
  
 Any drawing to a window that has the **WS_VISIBLE** style will not be displayed if the window is covered by other windows or is clipped by its parent window.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#103](../../mfc/reference/codesnippet/cpp/cwnd-class_43.cpp)]  
  
##  <a name="iszoomed"></a>  CWnd::IsZoomed  
 Determines whether `CWnd` has been maximized.  
  
```  
BOOL IsZoomed() const ;  
```  
  
### Return Value  
 Nonzero if `CWnd` is maximized; otherwise 0.  
  
##  <a name="killtimer"></a>  CWnd::KillTimer  
 Kills the timer event identified by `nIDEvent` from the earlier call to `SetTimer`.  
  
```  
BOOL KillTimer(UINT_PTR nIDEvent) ;
```  
  
### Parameters  
 `nIDEvent`  
 The value of the timer event passed to [SetTimer](#settimer).  
  
### Return Value  
 Specifies the outcome of the function. The value is nonzero if the event was killed. It is 0 if the `KillTimer` member function could not find the specified timer event.  
  
### Remarks  
 Pending [WM_TIMER](#ontimer) messages associated with the timer are not removed from the message queue.  
  
### Example  
  See the example for [CWnd::SetTimer](#settimer).  
  
##  <a name="loaddynamiclayoutresource"></a>  CWnd::LoadDynamicLayoutResource  
 Called by the framework to load dynamic layout information from the resource file.  
  
```  
BOOL LoadDynamicLayoutResource(LPCTSTR lpszResourceName) ;
```  
  
### Parameters  
 `lpszResourceName`  
 The name of the resource that contains the desired dynamic layout information for this window.  
  
### Return Value  
 Nonzero if the function is successful. It is 0 if a failure occurs.  
  
### Remarks  
 Do not call this method directly.  
  
##  <a name="lockwindowupdate"></a>  CWnd::LockWindowUpdate  
 Disables drawing in the given window.  
  
```  
BOOL LockWindowUpdate() ;
```  
  
### Return Value  
 Nonzero if the function is successful. It is 0 if a failure occurs or if the `LockWindowUpdate` function has been used to lock another window.  
  
### Remarks  
 A locked window cannot be moved. Only one window can be locked at a time. To unlock a window locked with `LockWindowUpdate`, call [UnlockWindowUpdate](#unlockwindowupdate).  
  
 If an application with a locked window (or any locked child windows) calls the [GetDC,](http://msdn.microsoft.com/library/windows/desktop/dd144871) [GetDCEx,](http://msdn.microsoft.com/library/windows/desktop/dd144873) or [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362) Windows function, the called function returns a device context whose visible region is empty. This will occur until the application unlocks the window by calling the `UnlockWindowUpdate` member function.  
  
 While window updates are locked, the system keeps track of the bounding rectangle of any drawing operations to device contexts associated with a locked window. When drawing is reenabled, this bounding rectangle is invalidated in the locked window and its child windows to force an eventual [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message to update the screen. If no drawing has occurred while the window updates were locked, no area is invalidated.  
  
 The `LockWindowUpdate` member function does not make the given window invisible and does not clear the [WS_VISIBLE](../../mfc/reference/window-styles.md) style bit.  
  
##  <a name="m_hwnd"></a>  CWnd::m_hWnd  
 The handle of the Windows window attached to this `CWnd`.  
  
```  
HWND m_hWnd ;  
```  
  
### Remarks  
 The `m_hWnd` data member is a public variable of type `HWND`.  
  
##  <a name="mapwindowpoints"></a>  CWnd::MapWindowPoints  
 Converts (maps) a set of points from the coordinate space of the `CWnd` to the coordinate space of another window.  
  
```  
void MapWindowPoints (CWnd * pwndTo,  
    LPRECT lpRect) const ;  
  
void MapWindowPoints (CWnd * pwndTo,  
    LPPOINT lpPoint,  
    UINT nCount) const ;  
```  
  
### Parameters  
 *pwndTo*  
 Identifies the window to which points are converted. If this parameter is **NULL**, the points are converted to screen coordinates.  
  
 `lpRect`  
 Specifies the rectangle whose points are to be converted. The first version of this function is available only for Windows 3.1 and later.  
  
 `lpPoint`  
 A pointer to an array of [POINT structure](../../mfc/reference/point-structure1.md) that contain the set of points to be converted.  
  
 `nCount`  
 Specifies the number of **POINT** structures in the array pointed to by `lpPoint`.  
  
##  <a name="messagebox"></a>  CWnd::MessageBox  
 Creates and displays a window that contains an application-supplied message and caption, plus a combination of the predefined icons and pushbuttons described in the [Message-Box Styles](../../mfc/reference/message-box-styles.md) list.  
  
```  
int MessageBox (lpszText LPCTSTR,  
    LPCTSTR lpszCaption = NULL,  
    UINT %nLes = MB_OK) ;
```  
  
### Parameters  
 `lpszText`  
 Points to a `CString` object or null-terminated string containing the message to be displayed.  
  
 `lpszCaption`  
 Points to a `CString` object or null-terminated string to be used for the message-box caption. If `lpszCaption` is **NULL**, the default caption "Error" is used.  
  
 `nType`  
 Specifies the contents and behavior of the message box.  
  
### Return Value  
 This method utilizes the [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) function as defined in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This method returns the result of calling this function.  
  
### Remarks  
 Use the global function [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) instead of this member function to implement a message box in your application.  
  
 The following shows the various system icons that can be used in a message box:  
  
|||  
|-|-|  
|![Stop &#40;x&#41; icon](../../mfc/reference/media/vc364f1.gif "vc364f1")|**MB_ICONHAND**, **MB_ICONSTOP**, and **MB_ICONERROR**|  
|![Help &#40;&#41; icon](../../mfc/reference/media/vc364f2.gif "vc364f2")|**MB_ICONQUESTION**|  
|![Important &#40;&#33;&#41; icon](../../mfc/reference/media/vc364f3.gif "vc364f3")|**MB_ICONEXCLAMATION** and **MB_ICONWARNING**|  
|![Information &#40;i&#41; icon](../../mfc/reference/media/vc364f4.gif "vc364f4")|**MB_ICONASTERISK** and **MB_ICONINFORMATION**|  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#104](../../mfc/reference/codesnippet/cpp/cwnd-class_44.cpp)]  
  
##  <a name="modifystyle"></a>  CWnd::ModifyStyle  
 Call this member function to modify a window's style.  
  
```  
BOOL ModifyStyle (DWORD dwRemove,  
    DwAdd DWORD,  
    UINT nIndicateurs = 0) ;
```  
  
### Parameters  
 `dwRemove`  
 Specifies window styles to be removed during style modification.  
  
 `dwAdd`  
 Specifies window styles to be added during style modification.  
  
 `nFlags`  
 Flags to be passed to [SetWindowPos](#setwindowpos), or zero if `SetWindowPos` should not be called. The default is zero. See the Remarks section for a list of preset flags.  
  
### Return Value  
 Nonzero if style was successfully modified; otherwise, 0.  
  
### Remarks  
 Styles to be added or removed can be combined by using the bitwise OR (&#124;) operator. See the topics [Window Styles](http://msdn.microsoft.com/library/windows/desktop/ms632600) and [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for information about the available window styles.  
  
 If `nFlags` is nonzero, `ModifyStyle` calls the Windows API function [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) and redraws the window by combining `nFlags` with the following four preset flags:  
  
- `SWP_NOSIZE` Retains the current size.  
  
- `SWP_NOMOVE` Retains the current position.  
  
- `SWP_NOZORDER` Retains the current Z order.  
  
- `SWP_NOACTIVATE` Does not activate the window.  
  
 To modify a window's extended styles, see [ModifyStyleEx](#modifystyleex).  
  
> [!NOTE]
>  For some styles in certain controls (the **ES_READONLY** style in the edit control, for example), **ModifyStyle** may not properly change the style because the control may need to perform special internal processing. In these cases, a corresponding message to change the style will be available ( **EM_SETREADONLY** in the example mentioned).  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#105](../../mfc/reference/codesnippet/cpp/cwnd-class_45.cpp)]  
  
##  <a name="modifystyleex"></a>  CWnd::ModifyStyleEx  
 Call this member function to modify a window's extended style.  
  
```  
BOOL ModifyStyleEx (DWORD dwRemove,  
    DwAdd DWORD,  
    UINT nIndicateurs = 0) ;
```  
  
### Parameters  
 `dwRemove`  
 Specifies extended styles to be removed during style modification.  
  
 `dwAdd`  
 Specifies extended styles to be added during style modification.  
  
 `nFlags`  
 Flags to be passed to [SetWindowPos](#setwindowpos), or zero if `SetWindowPos` should not be called. The default is zero. See the Remarks section for a list of preset flags.  
  
### Return Value  
 Nonzero if style was successfully modified; otherwise, 0.  
  
### Remarks  
 Styles to be added or removed can be combined by using the bitwise OR (&#124;) operator. See the topics [Extended Window Styles](../../mfc/reference/extended-window-styles.md) in this book and [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for information about the available extended styles  
  
 If `nFlags` is nonzero, `ModifyStyleEx` calls the Windows API function [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) and redraws the window by combining `nFlags` with the following four preset flags:  
  
- `SWP_NOSIZE` Retains the current size.  
  
- `SWP_NOMOVE` Retains the current position.  
  
- `SWP_NOZORDER` Retains the current Z order.  
  
- `SWP_NOACTIVATE` Does not activate the window.  
  
 To modify windows using regular window styles, see [ModifyStyle](#modifystyle).  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#106](../../mfc/reference/codesnippet/cpp/cwnd-class_46.cpp)]  
  
##  <a name="movewindow"></a>  CWnd::MoveWindow  
 Changes the position and dimensions.  
  
```  
void MoveWindow (int x,  
    int y,  
    int nWidth,  
    nHeight int,  
    BOOL bRepaint = TRUE) ;

 
void MoveWindow (LPCRECT lpRect, BOOL bRepaint = TRUE) ;
```  
  
### Parameters  
 *x*  
 Specifies the new position of the left side of the `CWnd`.  
  
 *y*  
 Specifies the new position of the top of the `CWnd`.  
  
 `nWidth`  
 Specifies the new width of the `CWnd`.  
  
 `nHeight`  
 Specifies the new height of the `CWnd`.  
  
 `bRepaint`  
 Specifies whether `CWnd` is to be repainted. If **TRUE**, `CWnd` receives a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message in its [OnPaint](#onpaint) message handler as usual. If this parameter is **FALSE**, no repainting of any kind occurs. This applies to the client area, to the nonclient area (including the title and scroll bars), and to any part of the parent window uncovered as a result of `CWnd`'s move. When this parameter is **FALSE**, the application must explicitly invalidate or redraw any parts of `CWnd` and parent window that must be redrawn.  
  
 `lpRect`  
 The [CRect](../../atl-mfc-shared/reference/crect-class.md) object or [RECT structure](../../mfc/reference/rect-structure1.md) that specifies the new size and position.  
  
### Remarks  
 For a top-level `CWnd` object, the *x* and *y* parameters are relative to the upper-left corner of the screen. For a child `CWnd` object, they are relative to the upper-left corner of the parent window's client area.  
  
 The `MoveWindow` function sends the [WM_GETMINMAXINFO](#ongetminmaxinfo) message. Handling this message gives `CWnd` the opportunity to modify the default values for the largest and smallest possible windows. If the parameters to the `MoveWindow` member function exceed these values, the values can be replaced by the minimum or maximum values in the `WM_GETMINMAXINFO` handler.  
  
### Example  
  See the example for [CWnd::ClientToScreen](#clienttoscreen).  
  
##  <a name="notifywinevent"></a>  CWnd::NotifyWinEvent  
 Signals the system that a predefined event occurred. If any client applications have registered a hook function for the event, the system calls the client's hook function.  
  
```  
void NotifyWinEvent (événement DWORD,  
    LONG idObjectType,  
    IdObject LONG) ;
```  
  
### Parameters  
 `event`  
 Specifies the event that occurred. This value must be one of the [event constants](http://msdn.microsoft.com/library/windows/desktop/dd318066).  
  
 *idObjectType*  
 Identifies the kind of object that generated the event. This value is one of the predefined [object identifiers](http://msdn.microsoft.com/library/windows/desktop/dd373606) or a custom object ID value.  
  
 `idObject`  
 Identifies whether the event was generated by an object or a child element of the object. If this value is **CHILDID_SELF**, the event was generated by the object itself. If not, this value is the child ID of the element that generated the event.  
  
### Remarks  
 This member function emulates the functionality of the function [NotifyWinEvent](http://msdn.microsoft.com/library/windows/desktop/dd373603), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onactivate"></a>  CWnd::OnActivate  
 The framework calls this member function when a `CWnd` object is being activated or deactivated.  
  
```  
afx_msg void OnActivate (UINT nState,  
    CWnd * pWndOther,  
    BOOL bMinimized) ;
```  
  
### Parameters  
 `nState`  
 Specifies whether the `CWnd` is being activated or deactivated. It can be one of the following values:  
  
- **WA_INACTIVE** The window is being deactivated.  
  
- **WA_ACTIVE** The window is being activated through some method other than a mouse click (for example, by use of the keyboard interface to select the window).  
  
- **WA_CLICKACTIVE** The window is being activated by a mouse click.  
  
 *pWndOther*  
 Pointer to the `CWnd` being activated or deactivated. The pointer can be **NULL**, and it may be temporary.  
  
 *bMinimized*  
 Specifies the minimized state of the `CWnd` being activated or deactivated. A value of **TRUE** indicates the window is minimized.  
  
 If **TRUE**, the `CWnd` is being activated; otherwise deactivated.  
  
### Remarks  
 If the `CWnd` object is activated with a mouse click, it will also receive an [OnMouseActivate](#onmouseactivate) member function call.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onactivateapp"></a>  CWnd::OnActivateApp  
 The framework calls this member function to all top-level windows of the task being activated and for all top-level windows of the task being deactivated.  
  
```  
afx_msg void OnActivateApp (BOOL bActive,  
    DwThreadID DWORD) ;
```  
  
### Parameters  
 `bActive`  
 Specifies whether the `CWnd` is being activated or deactivated. **TRUE** means the `CWnd` is being activated. **FALSE** means the `CWnd` is being deactivated.  
  
 *dwThreadID*  
 Specifies the value of the thread ID. If `bActive` is **TRUE**, *dwThreadID* identifies the thread that owns the `CWnd` being deactivated. If `bActive` is **FALSE**, *dwThreadID* identifies the thread that owns the `CWnd` being activated.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onambientproperty"></a>  CWnd::OnAmbientProperty  
 The framework calls this member function to obtain ambient property values from a window that contains OLE controls.  
  
```  
virtuel BOOL OnAmbientProperty (COleControlSite* pSite, DISPID dispid, variante* pvar) ;
```  
  
### Parameters  
 `pSite`  
 Pointer to the site of the control that requested the ambient property.  
  
 `dispid`  
 The dispatch ID of the requested ambient property.  
  
 `pvar`  
 Pointer to a caller-allocated `VARIANT` structure, through which the ambient property's value will be returned.  
  
### Return Value  
 **TRUE** if the ambient property is supported; **FALSE** if not.  
  
### Remarks  
 Override this function to alter the default ambient property values returned by an OLE control container to its controls. Any ambient property requests not handled by an overriding function should be forwarded to the base class implementation.  
  
##  <a name="onappcommand"></a>  CWnd::OnAppCommand  
 The framework calls this member function when the user generates an application command event. Such an event occurs when the user clicks an application command button or types an application command key.  
  
```  
afx_msg void OnAppCommand (CWnd * pWnd,  
    UINT nCmd,  
    UINT nDevice,  
    UINT nKey) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pWnd`|Pointer to a `CWnd` object that represents the window where the user clicked the comman button or pressed the command key. This window can be a child window of the window receiving the message.|  
|[in] `nCmd`|Indicates the application command. For a list of possible values, see the commands under the *cmd* section of the `lParam` parameter of [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275).|  
|[in] `nDevice`|The input device that generated the input event. For a list of possible values, see the devices under the *uDevice* section of the `lParam` parameter of [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275).|  
|[in] `nKey`|Indicates any virtual keys that are down, such as the CTRL key or the left mouse button. For a list of possible values, see the keys under the *dwKeys* section of the `lParam` parameter of [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275). For more information, see the "Message Parameters" subheading in [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).|  
  
### Remarks  
 This method receives the [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onaskcbformatname"></a>  CWnd::OnAskCbFormatName  
 The framework calls this member function when the Clipboard contains a data handle for the `CF_OWNERDISPLAY` format (that is, when the Clipboard owner will display the Clipboard contents).  
  
```  
afx_msg void OnAskCbFormatName (UINT nMaxCount,  
    LPTSTR lpszString) ;
```  
  
### Parameters  
 `nMaxCount`  
 Specifies the maximum number of bytes to copy.  
  
 `lpszString`  
 Points to the buffer where the copy of the format name is to be stored.  
  
### Remarks  
 The Clipboard owner should provide a name for its format.  
  
 Override this member function and copy the name of the `CF_OWNERDISPLAY` format into the specified buffer, not exceeding the maximum number of bytes specified.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncancelmode"></a>  CWnd::OnCancelMode  
 The framework calls this member function to inform `CWnd` to cancel any internal mode.  
  
```  
afx_msg void OnCancelMode() ;
```  
  
### Remarks  
 If the `CWnd` object has the focus, its `OnCancelMode` member function is called when a dialog box or message box is displayed. This gives the `CWnd` the opportunity to cancel modes such as mouse capture.  
  
 The default implementation responds by calling the [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261) Windows function. Override this member function in your derived class to handle other modes.  
  
##  <a name="oncapturechanged"></a>  CWnd::OnCaptureChanged  
 The framework calls this member function to notify the window that is losing the mouse capture.  
  
```  
afx_msg void OnCaptureChanged (CWnd * pWnd) ;
```  
  
### Parameters  
 `pWnd`  
 A pointer to the window to gain mouse capture  
  
### Remarks  
 A window receives this message even if it calls [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261) itself. An application should not attempt to set the mouse capture in response to this message. When it receives this message, a window should redraw itself, if necessary, to reflect the new mouse-capture state.  
  
 See the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for information on the `ReleaseCapture` Windows function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchangecbchain"></a>  CWnd::OnChangeCbChain  
 The framework calls this member function for each window in the Clipboard-viewer chain to notify it that a window is being removed from the chain.  
  
```  
afx_msg void OnChangeCbChain (HWND hWndRemove,  
    HWND hWndAfter) ;
```  
  
### Parameters  
 `hWndRemove`  
 Specifies the window handle that is being removed from the Clipboard-viewer chain.  
  
 `hWndAfter`  
 Specifies the window handle that follows the window being removed from the Clipboard-viewer chain.  
  
### Remarks  
 Each `CWnd` object that receives an `OnChangeCbChain` call should use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function to send the [WM_CHANGECBCHAIN](http://msdn.microsoft.com/library/windows/desktop/ms649019) message to the next window in the Clipboard-viewer chain (the handle returned by `SetClipboardViewer`). If `hWndRemove` is the next window in the chain, the window specified by `hWndAfter` becomes the next window, and Clipboard messages are passed on to it.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchangeuistate"></a>  CWnd::OnChangeUIState  
 Called when the user interface (UI) state should be changed.  
  
```  
afx_msg void OnChangeUIState (UINT %4%nsortie de l’action,  
    UINT nUIElement) ;
```  
  
### Parameters  
 `nAction`  
 Specifies the action to be taken. Can be one of the following values:  
  
- **UIS_CLEAR** The UI state element (specified by `nUIElement`) should be hidden.  
  
- **UIS_INITIALIZE** The UI state element (specified by `nUIElement`) should be changed based on the last input event. For more information, see the **Remarks** section of [WM_CHANGEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646342).  
  
- **UIS_SET** The UI state element (specified by `nUIElement`) should be visible.  
  
 `nUIElement`  
 Specifies which UI state elements are affected or the style of the control. Can be one of the following values:  
  
- **UISF_HIDEACCEL** Keyboard accelerators.  
  
- **UISF_HIDEFOCUS** Focus indicators.  
  
- **UISF_ACTIVE Windows XP:** A control should be drawn in the style used for active controls.  
  
### Remarks  
 This member function emulates the functionality of the [WM_CHANGEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646342) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onchar"></a>  CWnd::OnChar  
 The framework calls this member function when a keystroke translates to a nonsystem character.  
  
```  
afx_msg void OnChar (UINT nChar,  
    UINT nRepCnt,  
    UINT nIndicateurs) ;
```  
  
### Parameters  
 `nChar`  
 Contains the character code value of the key.  
  
 `nRepCnt`  
 Contains the repeat count, the number of times the keystroke is repeated when user holds down the key.  
  
 `nFlags`  
 Contains the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0-15|Specifies the repeat count. The value is the number of times the keystroke is repeated as a result of the user holding down the key.|  
|16-23|Specifies the scan code. The value depends on the original equipment manufacturer (OEM)|  
|24|Specifies whether the key is an extended key, such as the right-hand ALT and CTRL keys that appear on an enhanced 101- or 102-key keyboard. The value is 1 if it is an extended key; otherwise, it is 0.|  
|25-28|Used internally by Windows.|  
|29|Specifies the context code. The value is 1 if the ALT key is held down while the key is pressed; otherwise, the value is 0.|  
|30|Specifies the previous key state. The value is 1 if the key is down before the message is sent, or it is 0 if the key is up.|  
|31|Specifies the transition state. The value is 1 if the key is being released, or it is 0 if the key is being pressed.|  
  
### Remarks  
 This function is called before the [OnKeyUp](#onkeyup) member function and after the [OnKeyDown](#onkeydown) member function are called. `OnChar` contains the value of the keyboard key being pressed or released.  
  
 Because there is not necessarily a one-to-one correspondence between keys pressed and `OnChar` calls generated, the information in `nFlags` is generally not useful to applications. The information in `nFlags` applies only to the most recent call to the `OnKeyUp` member function or the `OnKeyDown` member function that precedes the call to `OnChar`.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchartoitem"></a>  CWnd::OnCharToItem  
 Called when a list box with the [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) style sends its owner a [WM_CHARTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761358) message in response to a [WM_CHAR](#onchar) message.  
  
```  
int afx_msg OnCharToItem (UINT nChar,  
    CListBox * pListBox,  
    UINT nIndex) ;
```  
  
### Parameters  
 `nChar`  
 Specifies the value of the key pressed by the user.  
  
 `pListBox`  
 Specifies a pointer to the list box. It may be temporary.  
  
 `nIndex`  
 Specifies the current caret position.  
  
### Return Value  
 The framework calls this member function to specify the action that the application performed in response to the call. A return value of –2 indicates that the application handled all aspects of selecting the item and wants no further action by the list box. A return value of –1 indicates that the list box should perform the default action in response to the keystroke. A return value of 0 or greater specifies the zero-based index of an item in the list box and indicates that the list box should perform the default action for the keystroke on the given item.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onchildactivate"></a>  CWnd::OnChildActivate  
 If the `CWnd` object is a multiple document interface (MDI) child window, `OnChildActivate` is called by the framework when the user clicks the window's title bar or when the window is activated, moved, or sized.  
  
```  
afx_msg void OnChildActivate() ;
```  
  
##  <a name="onchildnotify"></a>  CWnd::OnChildNotify  
 This member function is called by this window's parent window when it receives a notification message that applies to this window.  
  
```  
virtuel OnChildNotify BOOL (UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult) ;
```  
  
### Parameters  
 `message`  
 A Windows message number sent to a parent window.  
  
 `wParam`  
 The **wparam** associated with the message.  
  
 `lParam`  
 The **lparam** associated with the message.  
  
 `pLResult`  
 A pointer to a value to be returned from the parent's window procedure. This pointer will be **NULL** if no return value is expected.  
  
### Return Value  
 Nonzero if this window is responsible for handling the message sent to its parent; otherwise 0.  
  
### Remarks  
 Never call this member function directly.  
  
 The default implementation of this member function returns 0, which means that the parent should handle the message.  
  
 Override this member function to extend the manner in which a control responds to notification messages.  
  
##  <a name="onclipboardupdate"></a>  CWnd::OnClipboardUpdate  
 The framework calls this member function when the contents of the clipboard have changed.  
  
```  
afx_msg void OnClipboardUpdate() ;
```  
  
##  <a name="onclose"></a>  CWnd::OnClose  
 The framework calls this member function as a signal that the `CWnd` or an application is to terminate.  
  
```  
afx_msg void OnClose() ;
```  
  
### Remarks  
 The default implementation calls `DestroyWindow`.  
  
##  <a name="oncolorizationcolorchanged"></a>  CWnd::OnColorizationColorChanged  
 The framework calls this member when the rendering policy for the nonclient area has changed.  
  
```  
afx_msg void OnColorizationColorChanged (DWORD dwColorizationColor,   
    BOOL bOpacity) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `dwColorizationColor`|Specifies the new colorization color.<br /><br /> The color format is a hexadecimal number of the form 0xAARRGGBB, where each of the four components ranges from 0x00 through 0xFF. The AA component is the alpha value, RR is the color red, GG is green, and BB is blue.|  
|[in] `bOpacity`|`true` if the new color is blended with opacity; `false` if it is not.|  
  
### Remarks  
 This method receives the [WM_DWMNCRENDERINGCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388198) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncommand"></a>  CWnd::OnCommand  
 The framework calls this member function when the user selects an item from a menu, when a child control sends a notification message, or when an accelerator keystroke is translated.  
  
```  
virtuel OnCommand BOOL (WPARAM wParam,  
    LPARAM lParam) ;
```  
  
### Parameters  
 `wParam`  
 The low-order word of `wParam` identifies the command ID of the menu item, control, or accelerator. The high-order word of `wParam` specifies the notification message if the message is from a control. If the message is from an accelerator, the high-order word is 1. If the message is from a menu, the high-order word is 0.  
  
 `lParam`  
 Identifies the control that sends the message if the message is from a control. Otherwise, `lParam` is 0.  
  
### Return Value  
 An application returns nonzero if it processes this message; otherwise 0.  
  
### Remarks  
 `OnCommand` processes the message map for control notification and `ON_COMMAND` entries, and calls the appropriate member function.  
  
 Override this member function in your derived class to handle the [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) message. An override will not process the message map unless the base class `OnCommand` is called.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncompacting"></a>  CWnd::OnCompacting  
 The framework calls this member function for all top-level windows when Windows detects that more than 12.5 percent of system time over a 30- to 60-second interval is being spent compacting memory.  
  
```  
afx_msg void OnCompacting (UINT nCpuTime) ;
```  
  
### Parameters  
 *nCpuTime*  
 Specifies the ratio of CPU time currently spent by Windows compacting memory to CPU time spent performing other operations. For example, 8000h represents 50 percent of CPU time spent compacting memory.  
  
### Remarks  
 This indicates that system memory is low.  
  
 When a `CWnd` object receives this call, it should free as much memory as possible, taking into account the current level of activity of the application and the total number of applications running in Windows. The application can call the Windows function to determine how many applications are running.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncompareitem"></a>  CWnd::OnCompareItem  
 The framework calls this member function to specify the relative position of a new item in a child sorted owner-draw combo or list box.  
  
```  
afx_msg int OnCompareItem (int nIDCtl,  
    LpCompareItemStruct LPCOMPAREITEMSTRUCT) ;
```  
  
### Parameters  
 `nIDCtl`  
 The identifier of the control that sent the `WM_COMPAREITEM` message.  
  
 `lpCompareItemStruct`  
 Contains a long pointer to a [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) data structure that contains the identifiers and application-supplied data for two items in the combo or list box.  
  
### Return Value  
 Indicates the relative position of the two items. It may be any of the following values:  
  
|Value|Meaning|  
|-----------|-------------|  
|–1|Item 1 sorts before item 2.|  
|0|Item 1 and item 2 sort the same.|  
|1|Item 1 sorts after item 2.|  
  
### Remarks  
 If a combo or list box is created with the [CBS_SORT](../../mfc/reference/combo-box-styles.md) or [LBS_SORT](../../mfc/reference/list-box-styles.md) style, Windows sends the combo-box or list-box owner a `WM_COMPAREITEM` message whenever the application adds a new item.  
  
 Two items in the combo or list box are reformed in a `COMPAREITEMSTRUCT` structure pointed to by `lpCompareItemStruct`. `OnCompareItem` should return a value that indicates which of the items should appear before the other. Typically, Windows makes this call several times until it determines the exact position for the new item.  
  
 If the **hwndItem** member of the `COMPAREITEMSTRUCT` structure belongs to a [CListBox](../../mfc/reference/clistbox-class.md) or [CComboBox](../../mfc/reference/ccombobox-class.md) object, then the `CompareItem` virtual function of the appropriate class is called. Override `CComboBox::CompareItem` or `CListBox::CompareItem` in your derived `CListBox` or `CComboBox` class to do the item comparison.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncompositionchanged"></a>  CWnd::OnCompositionChanged  
 The framework calls this member function for all top-level windows when the Desktop Window Manager (DWM) composition is enabled or disabled.  
  
```  
afx_msg void OnCompositionChanged() ;
```  
  
### Remarks  
 This method receives the [WM_DWMCOMPOSITIONCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388199) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncontextmenu"></a>  CWnd::OnContextMenu  
 Called by the framework when the user has clicked the right mouse button (right clicked) in the window.  
  
```  
afx_msg void OnContextMenu (CWnd * pWnd,  
    CPoint pos) ;
```  
  
### Parameters  
 `pWnd`  
 Handle to the window in which the user right clicked the mouse. This can be a child window of the window receiving the message. For more information about processing this message, see the Remarks section.  
  
 `pos`  
 Position of the cursor, in screen coordinates, at the time of the mouse click.  
  
### Remarks  
 You can process this message by displaying a context menu using the [TrackPopupMenu](../../mfc/reference/cmenu-class.md#trackpopupmenu).  
  
 If you do not display a context menu you should pass this message onto the [DefWindowProc](#defwindowproc) function. If your window is a child window, `DefWindowProc` sends the message to the parent. Otherwise, `DefWindowProc` displays a default context menu if the specified position is in the window's caption.  
  
##  <a name="oncopydata"></a>  CWnd::OnCopyData  
 This member function is called by the framework to copy data from one application to another.  
  
```  
afx_msg BOOL OnCopyData (CWnd* pWnd, COPYDATASTRUCT* pCopyDataStruct) ;
```  
  
### Parameters  
 `pWnd`  
 A pointer to a `CWnd` object that is sending the data.  
  
 `pCopyDataStruct`  
 A pointer to a [COPYDATASTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms649010) structure that contains the data being sent.  
  
### Return Value  
 Returns **TRUE** if the receiving application successfully accepts the data. Otherwise, returns **FALSE**.  
  
### Remarks  
 The data being passed must not contain pointers or other references to objects not accessible to the application receiving the data.  
  
 While the data is being copied, it must not be changed by another thread of the sending process.  
  
 The receiving application should consider the data read-only. The structure pointed to by the parameter `pCopyDataStruct` is valid only during the transfer of data; however, the receiving application should not free the memory associated with the structure.  
  
 If the receiving application needs access to the data after this function returns, it must copy the data received to a local buffer.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oncreate"></a>  CWnd::OnCreate  
 The framework calls this member function when an application requests that the Windows window be created by calling the [Create](#create) or [CreateEx](#createex) member function.  
  
```  
int afx_msg OnCreate (LPCREATESTRUCT lpCreateStruct) ;
```  
  
### Parameters  
 `lpCreateStruct`  
 Points to a [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) structure that contains information about the `CWnd` object being created.  
  
### Return Value  
 `OnCreate` must return 0 to continue the creation of the `CWnd` object. If the application returns –1, the window will be destroyed.  
  
### Remarks  
 The `CWnd` object receives this call after the window is created but before it becomes visible. `OnCreate` is called before the **Create** or `CreateEx` member function returns.  
  
 Override this member function to perform any needed initialization of a derived class.  
  
 The `CREATESTRUCT` structure contains copies of the parameters used to create the window.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onctlcolor"></a>  CWnd::OnCtlColor  
 The framework calls this member function when a child control is about to be drawn.  
  
```  
afx_msg HBRUSH OnCtlColor (CDC* pDC, CWnd* pWnd,  
    UINT nCtlColor) ;
```  
  
### Parameters  
 `pDC`  
 Contains a pointer to the display context for the child window. May be temporary.  
  
 `pWnd`  
 Contains a pointer to the control asking for the color. May be temporary.  
  
 `nCtlColor`  
 Contains one of the following values, specifying the type of control:  
  
- **CTLCOLOR_BTN** Button control  
  
- **CTLCOLOR_DLG** Dialog box  
  
- **CTLCOLOR_EDIT** Edit control  
  
- **CTLCOLOR_LISTBOX** List-box control  
  
- **CTLCOLOR_MSGBOX** Message box  
  
- **CTLCOLOR_SCROLLBAR** Scroll-bar control  
  
- **CTLCOLOR_STATIC** Static control  
  
### Return Value  
 `OnCtlColor` must return a handle to the brush that is to be used for painting the control background.  
  
### Remarks  
 Most controls send this message to their parent (usually a dialog box) to prepare the `pDC` for drawing the control using the correct colors.  
  
 To change the text color, call the `SetTextColor` member function with the desired red, green, and blue (RGB) values.  
  
 To change the background color of a single-line edit control, set the brush handle in both the **CTLCOLOR_EDIT** and **CTLCOLOR_MSGBOX** message codes, and call the [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) function in response to the **CTLCOLOR_EDIT** code.  
  
 `OnCtlColor` will not be called for the list box of a drop-down combo box because the drop-down list box is actually a child of the combo box and not a child of the window. To change the color of the drop-down list box, create a `CComboBox` with an override of `OnCtlColor` that checks for **CTLCOLOR_LISTBOX** in the `nCtlColor` parameter. In this handler, the `SetBkColor` member function must be used to set the background color for the text.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function. To add the following method to your dialog class, use the Visual Studio properties pane to add a message handler for WM_CTLCOLOR. Alternatively, you can manually add an ON_WM_CTLCOLOR() entry to the message map.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#107](../../mfc/reference/codesnippet/cpp/cwnd-class_47.cpp)]  
  
##  <a name="ondeadchar"></a>  CWnd::OnDeadChar  
 The framework calls this member function when the [OnKeyUp](#onkeyup) member function and the [OnKeyDown](#onkeydown) member functions are called.  
  
```  
afx_msg void OnDeadChar (UINT nChar,  
    UINT nRepCnt,  
    UINT nIndicateurs) ;
```  
  
### Parameters  
 `nChar`  
 Specifies the dead-key character value.  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Description|  
|-----------|-----------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
### Remarks  
 This member function can be used to specify the character value of a dead key. A dead key is a key, such as the umlaut (double-dot) character, that is combined with other characters to form a composite character. For example, the umlaut-O character consists of the dead key, umlaut, and the O key.  
  
 An application typically uses `OnDeadChar` to give the user feedback about each key pressed. For example, an application can display the accent in the current character position without moving the caret.  
  
 Since there is not necessarily a one-to-one correspondence between keys pressed and `OnDeadChar` calls, the information in `nFlags` is generally not useful to applications. The information in `nFlags` applies only to the most recent call to the [OnKeyUp](#onkeyup) member function or the [OnKeyDown](#onkeydown) member function that precedes the `OnDeadChar` call.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondeleteitem"></a>  CWnd::OnDeleteItem  
 The framework calls this member function to inform the owner of an owner-draw list box or combo box that the list box or combo box is destroyed or that items have been removed by [CComboBox::DeleteString](../../mfc/reference/ccombobox-class.md#deletestring), [CListBox::DeleteString](../../mfc/reference/clistbox-class.md#deletestring), [CComboBox::ResetContent](../../mfc/reference/ccombobox-class.md#resetcontent), or [CListBox::ResetContent](../../mfc/reference/clistbox-class.md#resetcontent).  
  
```  
afx_msg void OnDeleteItem (int nIDCtl,  
    LpDeleteItemStruct LPDELETEITEMSTRUCT) ;
```  
  
### Parameters  
 `nIDCtl`  
 The identifier of the control that sent the `WM_DELETEITEM` message.  
  
 `lpDeleteItemStruct`  
 Specifies a long pointer to a [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) data structure that contains information about the deleted list box item.  
  
### Remarks  
 If the **hwndItem** member of the `DELETEITEMSTRUCT` structure belongs to a combo box or list box, then the `DeleteItem` virtual function of the appropriate class is called. Override the `DeleteItem` member function of the appropriate control's class to delete item-specific data.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondestroy"></a>  CWnd::OnDestroy  
 The framework calls this member function to inform the `CWnd` object that it is being destroyed.  
  
```  
afx_msg void OnDestroy() ;
```  
  
### Remarks  
 `OnDestroy` is called after the `CWnd` object is removed from the screen.  
  
 `OnDestroy` is called first for the `CWnd` being destroyed, then for the child windows of `CWnd` as they are destroyed. It can be assumed that all child windows still exist while `OnDestroy` runs.  
  
 If the `CWnd` object being destroyed is part of the Clipboard-viewer chain (set by calling the [SetClipboardViewer](#setclipboardviewer) member function), the `CWnd` must remove itself from the Clipboard-viewer chain by calling the [ChangeClipboardChain](#changeclipboardchain) member function before returning from the `OnDestroy` function.  
  
##  <a name="ondestroyclipboard"></a>  CWnd::OnDestroyClipboard  
 The framework calls this member function for the Clipboard owner when the Clipboard is emptied through a call to the [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) Windows function.  
  
```  
afx_msg void OnDestroyClipboard() ;
```  
  
##  <a name="ondevicechange"></a>  CWnd::OnDeviceChange  
 The framework calls this member function to notify an application or device driver of a change to the hardware configuration of a device or the computer.  
  
```  
afx_msg BOOL OnDeviceChange (UINT nEventType,  
    DwData DWORD_PTR) ;
```  
  
### Parameters  
 *nEventType*  
 An event type. See the Remarks section for a description of the available values  
  
 `dwData`  
 The address of a structure that contains event-specific data. Its meaning depends on the given event.  
  
### Remarks  
 For devices that offer software-controllable features, such as ejection and locking, the operating system typically sends a **DBT_DEVICEREMOVEPENDING** message to let applications and device drivers end their use of the device gracefully.  
  
 If the operating system forcefully removes of a device, it may not send a **DBT_DEVICEQUERYREMOVE** message before doing so.  
  
 The *nEvent* parameter can be one of these values:  
  
- [DBT_DEVICEARRIVAL](http://msdn.microsoft.com/library/windows/desktop/aa363205) A device has been inserted and is now available.  
  
- [DBT_DEVICEQUERYREMOVE](http://msdn.microsoft.com/library/windows/desktop/aa363206) Permission to remove a device is requested. Any application can deny this request and cancel the removal.  
  
- [DBT_DEVICEQUERYREMOVEFAILED](http://msdn.microsoft.com/library/windows/desktop/aa363207) Request to remove a device has been canceled.  
  
- [DBT_DEVICEREMOVEPENDING](http://msdn.microsoft.com/library/windows/desktop/aa363209) Device is about to be removed. Cannot be denied.  
  
- [DBT_DEVICEREMOVECOMPLETE](http://msdn.microsoft.com/library/windows/desktop/aa363208) Device has been removed.  
  
- [DBT_DEVICETYPESPECIFIC](http://msdn.microsoft.com/library/windows/desktop/aa363210) Device-specific event.  
  
- [DBT_CONFIGCHANGED](http://msdn.microsoft.com/library/windows/desktop/aa363203) Current configuration has changed.  
  
- **DBT_DEVNODES_CHANGED** Device node has changed.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondevmodechange"></a>  CWnd::OnDevModeChange  
 The framework calls this member function for all top-level `CWnd` objects when the user changes device-mode settings.  
  
```  
afx_msg void OnDevModeChange (LPTSTR lpDeviceName) ;
```  
  
### Parameters  
 *lpDeviceName*  
 Points to the device name specified in the Windows initialization file, WIN.INI.  
  
### Remarks  
 Applications that handle the `WM_DEVMODECHANGE` message may reinitialize their device-mode settings. Applications that use the Windows **ExtDeviceMode** function to save and restore device settings typically do not process this function.  
  
 This function is not called when the user changes the default printer from Control Panel. In this case, the `OnWinIniChange` function is called.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondrawclipboard"></a>  CWnd::OnDrawClipboard  
 The framework calls this member function for each window in the Clipboard-viewer chain when the contents of the Clipboard change.  
  
```  
afx_msg void OnDrawClipboard() ;
```  
  
### Remarks  
 Only applications that have joined the Clipboard-viewer chain by calling the [SetClipboardViewer](#setclipboardviewer) member function need to respond to this call.  
  
 Each window that receives an `OnDrawClipboard` call should call the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function to pass a [WM_DRAWCLIPBOARD](http://msdn.microsoft.com/library/windows/desktop/ms649025) message on to the next window in the Clipboard-viewer chain. The handle of the next window is returned by the [SetClipboardViewer](#setclipboardviewer) member function; it may be modified in response to an [OnChangeCbChain](#onchangecbchain) member function call.  
  
##  <a name="ondrawiconicthumbnailorlivepreview"></a>  CWnd::OnDrawIconicThumbnailOrLivePreview  
 Called by the framework when it needs to obtain a bitmap to be displayed on Windows 7 tab thumbnail, or on the client for application peek.  
  
```  
virtuel OnDrawIconicThumbnailOrLivePreview void (CDC se du contrôleur de domaine,  
    CRect rect,  
    CSize szRequiredThumbnailSize,  
    BOOL bIsThumbnail,  
    BOOL se bAlphaChannelSet) ;
```  
  
### Parameters  
 `dc`  
 Specifies the device context.  
  
 `rect`  
 Specifies the bounding rectangle of the area to render.  
  
 `szRequiredThumbnailSize`  
 Specifies the size of the target thumbnail. Should be ignored if `bIsThumbnail` is `FALSE`.  
  
 `bIsThumbnail`  
 Specifies whether this method is called for iconic thumbnail or live preview (peek).  
  
 `bAlphaChannelSet`  
 [out] Set it to `TRUE` if your implementation initializes the alpha channel of a bitmap selected in `dc`.  
  
### Remarks  
 Override this method in a derived class and draw on the specified device context in order to customize thumbnail and peek. If `bThumbnail` is `TRUE`, `szRequiredThumbnailSize` can be ignored. In this case you should be aware that you draw full sized bitmap (that is, a bitmap that covers the whole client area). The device context ( `dc`) comes with selected 32 bits bitmap. The default implementation sends WM_PRINT to this window with PRF_CLIENT, PRF_CHILDREN, and PRF_NONCLIENT flags.  
  
##  <a name="ondrawitem"></a>  CWnd::OnDrawItem  
 The framework calls this member function for the owner of an owner-draw button control, combo-box control, list-box control, or menu when a visual aspect of the control or menu has changed.  
  
```  
afx_msg void OnDrawItem (int nIDCtl,  
    LpDrawItemStruct LPDRAWITEMSTRUCT) ;
```  
  
### Parameters  
 `nIDCtl`  
 Contains the identifier of the control that sent the `WM_DRAWITEM` message. If a menu sent the message, `nIDCtl` contains 0.  
  
 `lpDrawItemStruct`  
 Specifies a long pointer to a `DRAWITEMSTRUCT` data structure that contains information about the item to be drawn and the type of drawing required.  
  
### Remarks  
 The **itemAction** member of the [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) structure defines the drawing operation that is to be performed. The data in this member allows the owner of the control to determine what drawing action is required.  
  
 Before returning from processing this message, an application should ensure that the device context identified by the `hDC` member of the `DRAWITEMSTRUCT` structure is restored to the default state.  
  
 If the **hwndItem** member belongs to a [CButton](../../mfc/reference/cbutton-class.md), [CMenu](../../mfc/reference/cmenu-class.md), [CListBox](../../mfc/reference/clistbox-class.md), or [CComboBox](../../mfc/reference/ccombobox-class.md) object, then the `DrawItem` virtual function of the appropriate class is called. Override the `DrawItem` member function of the appropriate control's class to draw the item.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ondropfiles"></a>  CWnd::OnDropFiles  
 The framework calls this member function when the user releases the left mouse button over a window that has registered itself as the recipient of dropped files.  
  
```  
afx_msg void OnDropFiles (HDROP hDropInfo) ;
```  
  
### Parameters  
 *hDropInfo*  
 A pointer to an internal data structure that describes the dropped files. This handle is used by the **DragFinish**, **DragQueryFile**, and **DragQueryPoint** Windows functions to retrieve information about the dropped files.  
  
### Remarks  
 Typically, a derived class will be designed to support dropped files and it will register itself during window construction.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onenable"></a>  CWnd::OnEnable  
 The framework calls this member function when an application changes the enabled state of the `CWnd` object.  
  
```  
afx_msg void OnEnable (BOOL bActivez) ;
```  
  
### Parameters  
 `bEnable`  
 Specifies whether the `CWnd` object has been enabled or disabled. This parameter is **TRUE** if the `CWnd` has been enabled; it is **FALSE** if the `CWnd` has been disabled.  
  
### Remarks  
 `OnEnable` is called before the [EnableWindow](#enablewindow) member function returns, but after the window enabled state ( [WS_DISABLED](../../mfc/reference/window-styles.md) style bit) has changed.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onendsession"></a>  CWnd::OnEndSession  
 The framework calls this member function after the `CWnd` object has returned a nonzero value from a [OnQueryEndSession](#onqueryendsession) member function call.  
  
```  
afx_msg void OnEndSession(BOOL bEnding) ;
```  
  
### Parameters  
 `bEnding`  
 Specifies whether or not the session is being ended. It is **TRUE** if the session is being ended; otherwise **FALSE**.  
  
### Remarks  
 The `OnEndSession` call informs the `CWnd` object whether the session is actually ending.  
  
 If `bEnding` is **TRUE**, Windows can terminate any time after all applications have returned from processing this call. Consequently, have an application perform all tasks required for termination within `OnEndSession`.  
  
 You do not need to call the [DestroyWindow](#destroywindow) member function or [PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) Windows function when the session is ending.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onenteridle"></a>  CWnd::OnEnterIdle  
 The framework calls this member function to inform an application's main window procedure that a modal dialog box or a menu is entering an idle state.  
  
```  
afx_msg void OnEnterIdle (UINT nWhy,  
    CWnd* pWho) ;
```  
  
### Parameters  
 `nWhy`  
 Specifies whether the message is the result of a dialog box or a menu being displayed. This parameter can be one of the following values:  
  
- **MSGF_DIALOGBOX** The system is idle because a dialog box is being displayed.  
  
- **MSGF_MENU** The system is idle because a menu is being displayed.  
  
 *pWho*  
 Specifies a pointer to the dialog box (if `nWhy` is **MSGF_DIALOGBOX**), or the window that contains the displayed menu (if `nWhy` is **MSGF_MENU**). This pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 A modal dialog box or menu enters an idle state when no messages are waiting in its queue after it has processed one or more previous messages.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onentermenuloop"></a>  CWnd::OnEnterMenuLoop  
 The framework calls this member function when a menu modal loop has been entered.  
  
```  
afx_msg void OnEnterMenuLoop (BOOL bIsTrackPopupMenu) ;
```  
  
### Parameters  
 `bIsTrackPopupMenu`  
 Specifies whether the menu involved is a popup menu. Has a nonzero value if the function is successful; otherwise 0.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onentersizemove"></a>  CWnd::OnEnterSizeMove  
 The framework calls this member function one time after the affected window enters a moving or sizing modal loop.  
  
```  
afx_msg void OnEnterSizeMove() ;
```  
  
### Remarks  
 This method receives the [WM_ENTERSIZEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms632622) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 A window enters a moving or sizing modal loop when the user clicks the window's title bar or sizing border, or when the window passes the [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) message to the [CWnd::DefWindowProc](#defwindowproc) function and the `wParam` parameter of that message specifies `SC_MOVE` or `SC_SIZE`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onerasebkgnd"></a>  CWnd::OnEraseBkgnd  
 The framework calls this member function when the `CWnd` object background needs erasing (for example, when resized).  
  
```  
afx_msg BOOL OnEraseBkgnd(CDC* pDC) ;
```  
  
### Parameters  
 `pDC`  
 Specifies the device-context object.  
  
### Return Value  
 Nonzero if it erases the background; otherwise 0.  
  
### Remarks  
 It is called to prepare an invalidated region for painting.  
  
 The default implementation erases the background using the window class background brush specified by the **hbrBackground** member of the window class structure.  
  
 If the **hbrBackground** member is **NULL**, your overridden version of `OnEraseBkgnd` should erase the background color. Your version should also align the origin of the intended brush with the `CWnd` coordinates by first calling [UnrealizeObject](http://msdn.microsoft.com/library/windows/desktop/dd145164) for the brush, and then selecting the brush.  
  
 An overridden `OnEraseBkgnd` should return nonzero in response to `WM_ERASEBKGND` if it processes the message and erases the background; this indicates that no further erasing is required. If it returns 0, the window will remain marked as needing to be erased. (Typically, this means that the **fErase** member of the `PAINTSTRUCT` structure will be **TRUE**.)  
  
 Windows assumes the background is computed with the `MM_TEXT` mapping mode. If the device context is using any other mapping mode, the area erased may not be within the visible part of the client area.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onexitmenuloop"></a>  CWnd::OnExitMenuLoop  
 The framework calls this member function when a menu modal loop has been exited.  
  
```  
afx_msg void OnExitMenuLoop (BOOL bIsTrackPopupMenu) ;
```  
  
### Parameters  
 `bIsTrackPopupMenu`  
 Specifies whether the menu involved is a pop-up menu. Has a nonzero value if the function is successful; otherwise 0.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onexitsizemove"></a>  CWnd::OnExitSizeMove  
 The framework calls this member function one time after the affected window exits a moving or sizing modal loop.  
  
```  
afx_msg void OnExitSizeMove() ;
```  
  
### Remarks  
 This method receives the [WM_EXITSIZEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms632623) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 A window enters a moving or sizing modal loop when the user clicks the window's title bar or sizing border, or when the window passes the [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) message to the [CWnd::DefWindowProc](#defwindowproc) function and the `wParam` parameter of that message specifies `SC_MOVE` or `SC_SIZE`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onfontchange"></a>  CWnd::OnFontChange  
 All top-level windows in the system receive an `OnFontChange` call from the framework after the application changes the pool of font resources.  
  
```  
afx_msg void OnFontChange() ;
```  
  
### Remarks  
 An application that adds or removes fonts from the system (for example, through the [AddFontResource](http://msdn.microsoft.com/library/windows/desktop/dd183326) or [RemoveFontResource](http://msdn.microsoft.com/library/windows/desktop/dd162922) Windows function) should send the [WM_FONTCHANGE](http://msdn.microsoft.com/library/windows/desktop/dd145211) message to all top-level windows.  
  
 To send this message, use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function with the `hWnd` parameter set to **HWND_BROADCAST**.  
  
##  <a name="ongetdlgcode"></a>  CWnd::OnGetDlgCode  
 Called for a control so the control can process arrow-key and TAB-key input itself.  
  
```  
afx_msg UINT OnGetDlgCode() ;
```  
  
### Return Value  
 One or more of the following values, indicating which type of input the application processes:  
  
- **DLGC_BUTTON** Button (generic).  
  
- **DLGC_DEFPUSHBUTTON** Default pushbutton.  
  
- **DLGC_HASSETSEL EM_SETSEL** messages.  
  
- **DLGC_UNDEFPUSHBUTTON** No default pushbutton processing. (An application can use this flag with **DLGC_BUTTON** to indicate that it processes button input but relies on the system for default pushbutton processing.)  
  
- **DLGC_RADIOBUTTON** Radio button.  
  
- **DLGC_STATIC** Static control.  
  
- **DLGC_WANTALLKEYS** All keyboard input.  
  
- **DLGC_WANTARROWS** Arrow keys.  
  
- **DLGC_WANTCHARS** `WM_CHAR` messages.  
  
- **DLGC_WANTMESSAGE** All keyboard input. The application passes this message on to the control.  
  
- **DLGC_WANTTAB** TAB key.  
  
### Remarks  
 Normally, Windows handles all arrow-key and TAB-key input to a `CWnd` control. By overriding `OnGetDlgCode`, a `CWnd` control can choose a particular type of input to process itself.  
  
 The default `OnGetDlgCode` functions for the predefined control classes return a code appropriate for each class.  
  
##  <a name="ongetminmaxinfo"></a>  CWnd::OnGetMinMaxInfo  
 The framework calls this member function whenever Windows needs to know the maximized position or dimensions, or the minimum or maximum tracking size.  
  
```  
afx_msg void OnGetMinMaxInfo (MINMAXINFO * lpMMI) ;
```  
  
### Parameters  
 *lpMMI*  
 Points to a `MINMAXINFO` structure that contains information about a window's maximized size and position and its minimum and maximum tracking size. For more about this structure, see the [MINMAXINFO](../../mfc/reference/minmaxinfo-structure.md) structure.  
  
### Remarks  
 The maximized size is the size of the window when its borders are fully extended. The maximum tracking size of the window is the largest window size that can be achieved by using the borders to size the window. The minimum tracking size of the window is the smallest window size that can be achieved by using the borders to size the window.  
  
 Windows fills in an array of points specifying default values for the various positions and dimensions. The application may change these values in `OnGetMinMaxInfo`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onhelp"></a>  CWnd::OnHelp  
 Handles F1 Help within the application (using the current context).  
  
```  
afx_msg void OnHelp() ;
```  
  
### Remarks  
 See [CWinApp::OnHelp](../../mfc/reference/cwinapp-class.md#onhelp) for more information.  
  
##  <a name="onhelpfinder"></a>  CWnd::OnHelpFinder  
 Handles the **ID_HELP_FINDER** and **ID_DEFAULT_HELP** commands.  
  
```  
afx_msg void OnHelpFinder() ;
```  
  
### Remarks  
 See [CWinApp::OnHelpFinder](../../mfc/reference/cwinapp-class.md#onhelpfinder) for more information.  
  
##  <a name="onhelpindex"></a>  CWnd::OnHelpIndex  
 Handles the **ID_HELP_INDEX** command and provides a default Help topic.  
  
```  
afx_msg void OnHelpIndex() ;
```  
  
### Remarks  
 See [CWinApp::OnHelpIndex](../../mfc/reference/cwinapp-class.md#onhelpindex) for more information.  
  
##  <a name="onhelpinfo"></a>  CWnd::OnHelpInfo  
 Called by the framework when the user presses the F1 key.  
  
```  
afx_msg BOOL OnHelpInfo(HELPINFO* lpHelpInfo) ;
```  
  
### Parameters  
 *lpHelpInfo*  
 Pointer to a [HELPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773313) structure that contains information about the menu item, control, dialog box, or window for which help is requested.  
  
### Return Value  
 Returns TRUE if a window has the keyboard focus or if a menu is active within a window. If no window has the keyboard focus, returns FALSE.  
  
### Remarks  
 If a menu is active when F1 is pressed, **WM_HELP** is sent to the window associated with the menu; otherwise, **WM_HELP** is sent to the window that has the keyboard focus. If no window has the keyboard focus, **WM_HELP** is sent to the currently active window.  
  
##  <a name="onhelpusing"></a>  CWnd::OnHelpUsing  
 Handles the **ID_HELP_USING** command.  
  
```  
afx_msg void OnHelpUsing() ;
```  
  
### Remarks  
 See [CWinApp::OnHelpUsing](../../mfc/reference/cwinapp-class.md#onhelpusing) for more information.  
  
##  <a name="onhotkey"></a>  CWnd::OnHotKey  
 The framework calls this member function when the user presses a system-wide hot key.  
  
```  
afx_msg void OnHotKey (UINT nHotKeyId,   
    UINT nKey1,   
    UINT nKey2) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHotKeyId`|Identifier for the hot key that generated the message. If the message was generated by a system-defined hot key, this parameter will be one of the following values:<br /><br /> - `IDHOT_SNAPDESKTOP` - The snap desktop hot key was pressed.<br />- `IDHOT_SNAPWINDOW` - The snap window hot key was pressed.|  
|[in] `nKey1`|A bitwise combination (OR) of flags that indicate the keys that were pressed in combination with the key specified by the `nKey2` parameter. The possible values are:<br /><br /> - `MOD_ALT` - Either ALT key was held down.<br />- `MOD_CONTROL` - Either CTRL key was held down.<br />- `MOD_SHIFT` - Either SHIFT key was held down.<br />- `MOD_WIN` - Either WINDOWS key was held down. These keys are labeled with the Microsoft Windows logo.|  
|[in] `nKey2`|The virtual key code of the hot key.|  
  
### Remarks  
 This method receives the [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is placed at the top of the message queue associated with the thread that registered the hot key. Use the [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) function to register a system-wide hot key.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onhscroll"></a>  CWnd::OnHScroll  
 The framework calls this member function when the user clicks a window's horizontal scroll bar.  
  
```  
afx_msg void OnHScroll (UINT nSBCode,  
    NPos UINT,  
    CScrollBar* pScrollBar) ;
```  
  
### Parameters  
 `nSBCode`  
 Specifies a scroll-bar code that indicates the user's scrolling request. This parameter can be one of the following:  
  
- **SB_LEFT** Scroll to far left.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINELEFT** Scroll left.  
  
- **SB_LINERIGHT** Scroll right.  
  
- **SB_PAGELEFT** Scroll one page left.  
  
- **SB_PAGERIGHT** Scroll one page right.  
  
- **SB_RIGHT** Scroll to far right.  
  
- **SB_THUMBPOSITION** Scroll to absolute position. The current position is specified by the `nPos` parameter.  
  
- **SB_THUMBTRACK** Drag scroll box to specified position. The current position is specified by the `nPos` parameter.  
  
 `nPos`  
 Specifies the scroll-box position if the scroll-bar code is **SB_THUMBPOSITION** or **SB_THUMBTRACK**; otherwise, not used. Depending on the initial scroll range, `nPos` may be negative and should be cast to an `int` if necessary.  
  
 `pScrollBar`  
 If the scroll message came from a scroll-bar control, contains a pointer to the control. If the user clicked a window's scroll bar, this parameter is **NULL**. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 The **SB_THUMBTRACK** scroll-bar code typically is used by applications that give some feedback while the scroll box is being dragged.  
  
 If an application scrolls the contents controlled by the scroll bar, it must also reset the position of the scroll box with the [SetScrollPos](#setscrollpos) member function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#108](../../mfc/reference/codesnippet/cpp/cwnd-class_48.cpp)]  
  
##  <a name="onhscrollclipboard"></a>  CWnd::OnHScrollClipboard  
 The Clipboard owner's `OnHScrollClipboard` member function is called by the Clipboard viewer when the Clipboard data has the `CF_OWNERDISPLAY` format and there is an event in the Clipboard viewer's horizontal scroll bar.  
  
```  
afx_msg void OnHScrollClipboard (CWnd * pClipAppWnd,  
    UINT nSBCode,  
    NPos UINT) ;
```  
  
### Parameters  
 `pClipAppWnd`  
 Specifies a pointer to a Clipboard-viewer window. The pointer may be temporary and should not be stored for later use.  
  
 `nSBCode`  
 Specifies one of the following scroll-bar codes in the low-order word:  
  
- **SB_BOTTOM** Scroll to lower right.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINEDOWN** Scroll one line down.  
  
- **SB_LINEUP** Scroll one line up.  
  
- **SB_PAGEDOWN** Scroll one page down.  
  
- **SB_PAGEUP** Scroll one page up.  
  
- **SB_THUMBPOSITION** Scroll to the absolute position. The current position is provided in `nPos`.  
  
- **SB_TOP** Scroll to upper left.  
  
 `nPos`  
 Contains the scroll-box position if the scroll-bar code is **SB_THUMBPOSITION**; otherwise not used.  
  
### Remarks  
 The owner should scroll the Clipboard image, invalidate the appropriate section, and update the scroll-bar values.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oniconerasebkgnd"></a>  CWnd::OnIconEraseBkgnd  
 The framework calls this member function for a minimized (iconic) `CWnd` object when the background of the icon must be filled before painting the icon.  
  
```  
afx_msg void OnIconEraseBkgnd (CDC * pDC) ;
```  
  
### Parameters  
 `pDC`  
 Specifies the device-context object of the icon. May be temporary and should not be stored for later use.  
  
### Remarks  
 `CWnd` receives this call only if a class icon is defined for the window default implementation; otherwise [OnEraseBkgnd](#onerasebkgnd) is called.  
  
 The [DefWindowProc](#defwindowproc) member function fills the icon background with the background brush of the parent window.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninitmenu"></a>  CWnd::OnInitMenu  
 The framework calls this member function when a menu is about to become active.  
  
```  
afx_msg void OnInitMenu (CMenu * pMenu) ;
```  
  
### Parameters  
 `pMenu`  
 Specifies the menu to be initialized. May be temporary and should not be stored for later use.  
  
### Remarks  
 `OnInitMenu` is called when the user clicks an item on the menu bar or presses a menu key. Override this member function to modify the menu before it is displayed.  
  
 `OnInitMenu` is only called once, when a menu is first accessed (for example, when a user clicks an item on the menu bar). This method does not provide information about menu items. As the user moves to items within the menu (for example, by moving the mouse across several menu items) the function is not called again. Once the user exits from the menu (for example, by clicking on the application client area) and later clicks an item on the menu bar, the function will be called again.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninitmenupopup"></a>  CWnd::OnInitMenuPopup  
 The framework calls this member function when a pop-up menu is about to become active.  
  
```  
afx_msg void OnInitMenuPopup (CMenu * pPopupMenu,  
    UINT nIndex,  
    BOOL bSysMenu) ;
```  
  
### Parameters  
 *pPopupMenu*  
 Specifies the menu object of the pop-up menu. May be temporary and should not be stored for later use.  
  
 `nIndex`  
 Specifies the index of the pop-up menu in the main menu.  
  
 *bSysMenu*  
 **TRUE** if the pop-up menu is the Control menu; otherwise **FALSE**.  
  
### Remarks  
 This allows an application to modify the pop-up menu before it is displayed without changing the entire menu.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninputdevicechange"></a>  CWnd::OnInputDeviceChange  
 The framework calls this member function when an I/O device is added or removed from the system.  
  
```  
afx_msg void OnInputDeviceChange (unsigned short uFlag) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `uFlag`|This flag can contain the following values:<br /><br /> - `GIDC_ARRIVAL` - A new device has been added to the system.<br />- `GIDC_REMOVAL` - A device has been removed from the system.|  
  
### Remarks  
 This method receives the [WM_INPUT_DEVICE_CHANGE](http://msdn.microsoft.com/library/windows/desktop/ms645591) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. The is a generic input device message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninputlangchange"></a>  CWnd::OnInputLangChange  
 The framework calls this member for the topmost affected window after an application's input language has been changed.  
  
```  
afx_msg void OnInputLangChange (UINT nCharSet,   
    UINT nLocaleId) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nCharSet`|The character set of the new locale. For more information, see the `lfCharSet` parameter of the [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure.|  
|[in] `nLocaleId`|The input locale identifier. For more information, see [Language Identifier Constants and Strings](http://msdn.microsoft.com/library/windows/desktop/dd318693).|  
  
### Remarks  
 This method receives the [WM_INPUTLANGCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms632629) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="oninputlangchangerequest"></a>  CWnd::OnInputLangChangeRequest  
 The framework calls this member for window with the focus when the user chooses a new input language.  
  
```  
afx_msg void OnInputLangChangeRequest (UINT nIndicateurs,   
    UINT nLocaleId) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise (OR) combination of flags that indicate the new locale was selected from the previous or next locale in the installed list of locales, or that the new input locale's keyboard layout can be used with the system character set.<br /><br /> The possible values are `INPUTLANGCHANGE_BACKWARD`, `INPUTLANGCHANGE_FORWARD`, and `INPUTLANGCHANGE_SYSCHARSET`.|  
|[in] `nLocaleId`|The input locale identifier. For more information, see [Language Identifier Constants and Strings](http://msdn.microsoft.com/library/windows/desktop/dd318693).|  
  
### Remarks  
 This method receives the [WM_INPUTLANGCHANGEREQUEST](http://msdn.microsoft.com/library/windows/desktop/ms632630) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted when the user chooses a new input language with either a hotkey that is specified in the keyboard control panel application, or from the indicator on the system taskbar.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onkeydown"></a>  CWnd::OnKeyDown  
 The framework calls this member function when a nonsystem key is pressed.  
  
```  
afx_msg void OnKeyDown (UINT nChar,  
    UINT nRepCnt,  
    UINT nIndicateurs) ;
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the given key. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Repeat count (the number of times the keystroke is repeated as a result of the user holding down the key).  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Description|  
|-----------|-----------------|  
|0–7|Scan code (OEM-dependent value).|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For a `WM_KEYDOWN` message, the key-transition bit (bit 15) is 0 and the context-code bit (bit 13) is 0.  
  
### Remarks  
 A nonsystem key is a keyboard key that is pressed when the ALT key is not pressed or a keyboard key that is pressed when `CWnd` has the input focus.  
  
 Because of auto-repeat, more than one `OnKeyDown` call may occur before an [OnKeyUp](#onkeyup) member function call is made. The bit that indicates the previous key state can be used to determine whether the `OnKeyDown` call is the first down transition or a repeated down transition.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onkeyup"></a>  CWnd::OnKeyUp  
 The framework calls this member function when a nonsystem key is released.  
  
```  
afx_msg void OnKeyUp (UINT nChar,  
    UINT nRepCnt,  
    UINT nIndicateurs) ;
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the given key. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Repeat count (the number of times the keystroke is repeated as a result of the user holding down the key).  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Description|  
|-----------|-----------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For a `WM_KEYUP` message, the key-transition bit (bit 15) is 1 and the context-code bit (bit 13) is 0.  
  
### Remarks  
 A nonsystem key is a keyboard key that is pressed when the ALT key is not pressed or a keyboard key that is pressed when the `CWnd` has the input focus.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onkillfocus"></a>  CWnd::OnKillFocus  
 The framework calls this member function immediately before losing the input focus.  
  
```  
afx_msg void OnKillFocus (CWnd * pNewWnd) ;
```  
  
### Parameters  
 *pNewWnd*  
 Specifies a pointer to the window that receives the input focus (may be **NULL** or may be temporary).  
  
### Remarks  
 If the `CWnd` object is displaying a caret, the caret should be destroyed at this point.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onlbuttondblclk"></a>  CWnd::OnLButtonDblClk  
 The framework calls this member function when the user double-clicks the left mouse button.  
  
```  
afx_msg void OnLButtonDblClk (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 Only windows that have the **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) style will receive `OnLButtonDblClk` calls. This is the default for Microsoft Foundation Class windows. Windows calls `OnLButtonDblClk` when the user presses, releases, and then presses the left mouse button again within the system's double-click time limit. Double-clicking the left mouse button actually generates four events: [WM_LBUTTONDOWN](#onlbuttondown), [WM_LBUTTONUP](#onlbuttonup) messages, the `WM_LBUTTONDBLCLK` call, and another `WM_LBUTTONUP` message when the button is released.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onlbuttondown"></a>  CWnd::OnLButtonDown  
 The framework calls this member function when the user presses the left mouse button.  
  
```  
afx_msg void OnLButtonDown (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onlbuttonup"></a>  CWnd::OnLButtonUp  
 The framework calls this member function when the user releases the left mouse button.  
  
```  
afx_msg void OnLButtonUp (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmbuttondblclk"></a>  CWnd::OnMButtonDblClk  
 The framework calls this member function when the user double-clicks the middle mouse button.  
  
```  
afx_msg void OnMButtonDblClk (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 Only windows that have the **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) style will receive `OnMButtonDblClk` calls. This is the default for all Microsoft Foundation Class windows. Windows generates an `OnMButtonDblClk` call when the user presses, releases, and then presses the middle mouse button again within the system's double-click time limit. Double-clicking the middle mouse button actually generates four events: [WM_MBUTTONDOWN](#onmbuttondown) and [WM_MBUTTONUP](#onmbuttonup) messages, the `WM_MBUTTONDBLCLK` call, and another `WM_MBUTTONUP` message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmbuttondown"></a>  CWnd::OnMButtonDown  
 The framework calls this member function when the user presses the middle mouse button.  
  
```  
afx_msg void OnMButtonDown (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmbuttonup"></a>  CWnd::OnMButtonUp  
 The framework calls this member function when the user releases the middle mouse button.  
  
```  
afx_msg void OnMButtonUp (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmdiactivate"></a>  CWnd::OnMDIActivate  
 The framework calls this member function for the child window being deactivated and the child window being activated.  
  
```  
afx_msg void OnMDIActivate (BOOL bActivate,  
    CWnd* pActivateWnd, CWnd* pDeactivateWnd) ;
```  
  
### Parameters  
 `bActivate`  
 **TRUE** if the child is being activated and **FALSE** if it is being deactivated.  
  
 `pActivateWnd`  
 Contains a pointer to the MDI child window to be activated. When received by an MDI child window, `pActivateWnd` contains a pointer to the child window being activated. This pointer may be temporary and should not be stored for later use.  
  
 *pDeactivateWnd*  
 Contains a pointer to the MDI child window being deactivated. This pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 An MDI child window is activated independently of the MDI frame window. When the frame becomes active, the child window that was last activated with a `OnMDIActivate` call receives an [WM_NCACTIVATE](#onncactivate) message to draw an active window frame and caption bar, but it does not receive another `OnMDIActivate` call.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmeasureitem"></a>  CWnd::OnMeasureItem  
 The framework calls this member function by the framework for the owner of an owner-draw button, combo box, list box, or menu item when the control is created.  
  
```  
afx_msg void OnMeasureItem (int nIDCtl, LPMEASUREITEMSTRUCT lpMeasureItemStruct) ;
```  
  
### Parameters  
 `nIDCtl`  
 The ID of the control.  
  
 `lpMeasureItemStruct`  
 Points to a [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) data structure that contains the dimensions of the owner-draw control.  
  
### Remarks  
 Override this member function and fill in the `MEASUREITEMSTRUCT` data structure pointed to by `lpMeasureItemStruct` and return; this informs Windows of the dimensions of the control and allows Windows to process user interaction with the control correctly.  
  
 If a list box or combo box is created with the [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) or [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) style, the framework calls this function for the owner for each item in the control; otherwise this function is called once.  
  
 Windows initiates the call to `OnMeasureItem` for the owner of combo boxes and list boxes created with the **OWNERDRAWFIXED** style before sending the [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) message. As a result, when the owner receives this call, Windows has not yet determined the height and width of the font used in the control; function calls and calculations that require these values should occur in the main function of the application or library.  
  
 If the item being measured is a `CMenu`, `CListBox` or `CComboBox` object, then the `MeasureItem` virtual function of the appropriate class is called. Override the `MeasureItem` member function of the appropriate control's class to calculate and set the size of each item.  
  
 `OnMeasureItem` will be called only if the control's class is created at run time, or it is created with the **LBS_OWNERDRAWVARIABLE** or **CBS_OWNERDRAWVARIABLE** style. If the control is created by the dialog editor, `OnMeasureItem` will not be called. This is because the [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) message is sent early in the creation process of the control. If you subclass by using `DDX_Control`, `SubclassDlgItem`, or `SubclassWindow`, the subclassing usually occurs after the creation process. Therefore, there is no way to handle the [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) message in the control's `OnChildNotify` function, which is the mechanism MFC uses to implement **ON_WM_MEASUREITEM_REFLECT**.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenuchar"></a>  CWnd::OnMenuChar  
 The framework calls this member function when the user presses a menu mnemonic character that doesn't match any of the predefined mnemonics in the current menu.  
  
```  
afx_msg LRESULT OnMenuChar (UINT nChar,  
    UINT nIndicateurs,  
    CMenu* pMenu) ;
```  
  
### Parameters  
 `nChar`  
 Depending on the build settings, specifies the ANSI or Unicode character that the user pressed.  
  
 `nFlags`  
 Contains the **MF_POPUP** flag if the menu is a pop-up menu. It contains the **MF_SYSMENU** flag if the menu is a Control menu.  
  
 `pMenu`  
 Contains a pointer to the selected `CMenu`. The pointer may be temporary and should not be stored.  
  
### Return Value  
 The high-order word of the return value should contain one of the following command codes:  
  
|Value|Description|  
|-----------|-----------------|  
|0|Tells Windows to discard the character that the user pressed and creates a short beep on the system speaker.|  
|1|Tells Windows to close the current menu.|  
|2|Informs Windows that the low-order word of the return value contains the item number for a specific item. This item is selected by Windows.|  
  
 The low-order word is ignored if the high-order word contains 0 or 1. Applications should process this message when accelerator (shortcut) keys are used to select bitmaps placed in a menu.  
  
### Remarks  
 It is sent to the `CWnd` that owns the menu. `OnMenuChar` is also called when the user presses ALT and any other key, even if the key does not correspond to a mnemonic character. In this case, `pMenu` points to the menu owned by the `CWnd`, and `nFlags` is 0.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenudrag"></a>  CWnd::OnMenuDrag  
 The framework calls this member function of the current drag-and-drop menu when the user begins to drag a menu item.  
  
```  
afx_msg UINT OnMenuDrag (UINT nPos,   
    CMenu* pMenu) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nPos`|The index position of the menu item when the drag operation begins.|  
|[in] `pMenu`|Pointer to the [CMenu](../../mfc/reference/cmenu-class.md) object that contains the menu item.|  
  
### Return Value  
  
|Return Value|Meaning|  
|------------------|-------------|  
|`MND_CONTINUE`|The menu should remain active. If the mouse is released, it should be ignored.|  
|`MND_ENDMENU`|The menu should be ended.|  
  
### Remarks  
 This method receives the [WM_MENUDRAG](http://msdn.microsoft.com/library/windows/desktop/ms647606) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenugetobject"></a>  CWnd::OnMenuGetObject  
 The framework calls this member function of the current drag-and-drop menu when the mouse cursor enters a menu item or moves from the center of the item to the top or bottom of the item.  
  
```  
afx_msg UINT OnMenuGetObject(MENUGETOBJECTINFO* pMenuGetObjectInfo) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pMenu`|Pointer to a [MENUGETOBJECTINFO](http://msdn.microsoft.com/library/windows/desktop/ms647572) structure that contains information about the drag-and-drop menu the mouse cursor is on.|  
  
### Return Value  
  
|Return Value|Meaning|  
|------------------|-------------|  
|`MNGO_NOERROR`|An interface pointer that supports drop-and-drag operations is returned in the `pvObj` member of the [MENUGETOBJECTINFO](http://msdn.microsoft.com/library/windows/desktop/ms647572) structure. Currently, only the [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) interface is supported.|  
|`MNGO_NOINTERFACE`|No drop-and-drag interface is supported.|  
  
### Remarks  
 This method receives the [WM_MENUGETOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms647607) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenurbuttonup"></a>  CWnd::OnMenuRButtonUp  
 The framework calls this member function when the user releases the right mouse button while the cursor is on a menu item.  
  
```  
afx_msg void OnMenuRButtonUp (UINT nPos,  
    CMenu* pMenu) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nPos`|The index position of the menu item when the right mouse button was released.|  
|[in] `pMenu`|Pointer to the [CMenu](../../mfc/reference/cmenu-class.md) object that contains the menu item.|  
  
### Remarks  
 This method receives the [WM_MENURBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms647610) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. The [WM_MENURBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms647610) message enables an application to provide a context-sensitive menu for the menu item specified in the message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmenuselect"></a>  CWnd::OnMenuSelect  
 If the `CWnd` object is associated with a menu, `OnMenuSelect` is called by the framework when the user selects a menu item.  
  
```  
afx_msg void OnMenuSelect (UINT nItemID,  
    UINT nIndicateurs,  
    HSysMenu HMENU) ;
```  
  
### Parameters  
 `nItemID`  
 Identifies the item selected. If the selected item is a menu item, `nItemID` contains the menu-item ID. If the selected item contains a pop-up menu, `nItemID` contains the pop-up menu index, and *hSysMenu* contains the handle of the main (clicked-on) menu.  
  
 `nFlags`  
 Contains a combination of the following menu flags:  
  
- **MF_BITMAP** Item is a bitmap.  
  
- **MF_CHECKED** Item is checked.  
  
- **MF_DISABLED** Item is disabled.  
  
- **MF_GRAYED** Item is dimmed.  
  
- **MF_MOUSESELECT** Item was selected with a mouse.  
  
- `MF_OWNERDRAW` Item is an owner-draw item.  
  
- **MF_POPUP** Item contains a pop-up menu.  
  
- **MF_SEPARATOR** Item is a menu-item separator.  
  
- **MF_SYSMENU** Item is contained in the Control menu.  
  
 `hSysMenu`  
 If `nFlags` contains **MF_SYSMENU**, identifies the menu associated with the message. If `nFlags` contains **MF_POPUP**, identifies the handle of the main menu. If `nFlags` contains neither **MF_SYSMENU** nor **MF_POPUP**, it is unused.  
  
### Remarks  
 If `nFlags` contains 0xFFFF and `hSysMenu` contains 0, Windows has closed the menu because the user pressed the ESC key or clicked outside the menu.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmouseactivate"></a>  CWnd::OnMouseActivate  
 The framework calls this member function when the cursor is in an inactive window and the user presses a mouse button.  
  
```  
int afx_msg OnMouseActivate (CWnd * pDesktopWnd,  
    UINT nHitTest,  
    UINT message) ;
```  
  
### Parameters  
 *pDesktopWnd*  
 Specifies a pointer to the top-level parent window of the window being activated. The pointer may be temporary and should not be stored.  
  
 `nHitTest`  
 Specifies the [hit-test](#onnchittest) area code. A hit test is a test that determines the location of the cursor.  
  
 `message`  
 Specifies the mouse message number.  
  
### Return Value  
 Specifies whether to activate the `CWnd` and whether to discard the mouse event. It must be one of the following values:  
  
- **MA_ACTIVATE** Activate `CWnd` object.  
  
- **MA_NOACTIVATE** Do not activate `CWnd` object.  
  
- **MA_ACTIVATEANDEAT** Activate `CWnd` object and discard the mouse event.  
  
- **MA_NOACTIVATEANDEAT** Do not activate `CWnd` object and discard the mouse event.  
  
### Remarks  
 The default implementation passes this message to the parent window before any processing occurs. If the parent window returns **TRUE**, processing is halted.  
  
 For a description of the individual hit-test area codes, see the [OnNcHitTest](#onnchittest) member function  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCAxCtl#9](../../mfc/reference/codesnippet/cpp/cwnd-class_49.cpp)]  
  
##  <a name="onmousehover"></a>  CWnd::OnMouseHover  
 The framework calls this member function when the cursor hovers over the client area of the window for the period of time specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
afx_msg void OnMouseHover (UINT nIndicateurs,   
    Point CPoint) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_MOUSEHOVER](http://msdn.microsoft.com/library/windows/desktop/ms645613) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmousehwheel"></a>  CWnd::OnMouseHWheel  
 The framework calls this member when the current window is composed by the Desktop Window Manager (DWM), and that window is maximized.  
  
```  
afx_msg void OnMouseHWheel (UINT nIndicateurs,   
    short zDelta,   
    CPoint pt) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.<br /><br /> For a list of flags, see the "Message Parameters" subheading in [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).|  
|[in] `zDelta`|Indicates the distance the wheel is rotated, expressed in multiples or divisions of `WHEEL_DELTA`, which is 120. A positive value indicates that the wheel was rotated to the right; a negative value indicates that the wheel was rotated to the left.|  
|[in] `pt`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_MOUSEHWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645614) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is sent to the window that has the focus when the mouse's horizontal scroll wheel is tilted or rotated.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmouseleave"></a>  CWnd::OnMouseLeave  
 The framework calls this member function when the cursor leaves the client area of the window specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
afx_msg void OnMouseLeave() ;
```  
  
### Remarks  
 This method receives the [WM_MOUSELEAVE](http://msdn.microsoft.com/library/windows/desktop/ms645615) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmousemove"></a>  CWnd::OnMouseMove  
 The framework calls this member function when the mouse cursor moves.  
  
```  
afx_msg void OnMouseMove (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 If the mouse is not captured, the `WM_MOUSEMOVE` message is received by the `CWnd` object beneath the mouse cursor; otherwise, the message goes to the window that has captured the mouse.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmousewheel"></a>  CWnd::OnMouseWheel  
 The framework calls this member function as a user rotates the mouse wheel and encounters the wheel's next notch.  
  
```  
afx_msg BOOL OnMouseWheel (UINT nIndicateurs,  
    short zDelta,  
    CPoint pt) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if the CTRL key is down.  
  
- **MK_LBUTTON** Set if the left mouse button is down.  
  
- **MK_MBUTTON** Set if the middle mouse button is down.  
  
- **MK_RBUTTON** Set if the right mouse button is down.  
  
- **MK_SHIFT** Set if the SHIFT key is down.  
  
 `zDelta`  
 Indicates distance rotated. The `zDelta` value is expressed in multiples or divisions of **WHEEL_DELTA**, which is 120. A value less than zero indicates rotating back (toward the user) while a value greater than zero indicates rotating forward (away from the user). The user can reverse this response by changing the Wheel setting in the mouse software. See the Remarks for more information about this parameter.  
  
 `pt`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the screen.  
  
### Return Value  
 Nonzero if mouse wheel scrolling is enabled; otherwise 0.  
  
### Remarks  
 Unless overridden, `OnMouseWheel` calls the default of [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617). Windows automatically routes the message to the control or child window that has the focus. The Win32 function [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) propagates the message up the parent chain to the window that processes it.  
  
 The `zDelta` parameter is a multiple of **WHEEL_DELTA**, which is set at 120. This value is the threshold for an action to be taken, and one such action (for example, scrolling forward one notch) should occur for each delta.  
  
 **WHEEL_DELTA** was set to 120 to allow for finer-resolution wheels, such as a freely-rotating wheel with no notches. A finer-resolution wheel sends more messages per rotation, but each message has a smaller delta value. To use such a wheel, either add the incoming `zDelta` values until **WHEEL_DELTA** is reached (so that you get the same response for a given delta-rotation), or scroll partial lines in response to the more frequent messages. You can also choose a scroll granularity and accumulate deltas until **WHEEL_DELTA** is reached.  
  
 Override this member function to provide your own mouse-wheel scrolling behavior.  
  
> [!NOTE]
> `OnMouseWheel` handles messages for Windows NT 4.0 and later versions. For Windows 95/98 or Windows NT 3.51 message handling, use [OnRegisteredMouseWheel](#onregisteredmousewheel).  
  
##  <a name="onmove"></a>  CWnd::OnMove  
 The framework calls this member function after the `CWnd` object has been moved.  
  
```  
afx_msg void OnMove (int x,  
    int y) ;
```  
  
### Parameters  
 *x*  
 Specifies the new x-coordinate location of the upper-left corner of the client area. This new location is given in screen coordinates for overlapped and pop-up windows, and parent-client coordinates for child windows.  
  
 *y*  
 Specifies the new y-coordinate location of the upper-left corner of the client area. This new location is given in screen coordinates for overlapped and pop-up windows, and parent-client coordinates for child windows.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onmoving"></a>  CWnd::OnMoving  
 The framework calls this member function while a user is moving a `CWnd` object.  
  
```  
afx_msg void OnMoving (UINT nSide,  
    LpRect LPRECT) ;
```  
  
### Parameters  
 `nSide`  
 The edge of window to be moved.  
  
 `lpRect`  
 Address of the [CRect](../../atl-mfc-shared/reference/crect-class.md) or [RECT structure](../../mfc/reference/rect-structure1.md) that will contain the item's coordinates.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncactivate"></a>  CWnd::OnNcActivate  
 The framework calls this member function when the nonclient area needs to be changed to indicate an active or inactive state.  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive) ;
```  
  
### Parameters  
 `bActive`  
 Specifies when a caption bar or icon needs to be changed to indicate an active or inactive state. The `bActive` parameter is **TRUE** if an active caption or icon is to be drawn. It is **FALSE** for an inactive caption or icon.  
  
### Return Value  
 Nonzero if Windows should proceed with default processing; 0 to prevent the caption bar or icon from being deactivated.  
  
### Remarks  
 The default implementation draws the title bar and title-bar text in their active colors if `bActive` is **TRUE** and in their inactive colors if `bActive` is **FALSE**.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnccalcsize"></a>  CWnd::OnNcCalcSize  
 The framework calls this member function when the size and position of the client area needs to be calculated.  
  
```  
afx_msg void OnNcCalcSize (BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS* lpncsp) ;
```  
  
### Parameters  
 `bCalcValidRects`  
 Specifies whether the application should specify which part of the client area contains valid information. Windows will copy the valid information to the specified area within the new client area. If this parameter is **TRUE**, the application should specify which part of the client area is valid.  
  
 `lpncsp`  
 Points to a [NCCALCSIZE_PARAMS](../../mfc/reference/nccalcsize-params-structure.md) data structure that contains information an application can use to calculate the new size and position of the `CWnd` rectangle (including client area, borders, caption, scroll bars, and so on).  
  
### Remarks  
 By processing this message, an application can control the contents of the window's client area when the size or position of the window changes.  
  
 Regardless of the value of `bCalcValidRects`, the first rectangle in the array specified by the **rgrc** structure member of the `NCCALCSIZE_PARAMS` structure contains the coordinates of the window. For a child window, the coordinates are relative to the parent window's client area. For top-level windows, the coordinates are screen coordinates. An application should modify the **rgrc[0]** rectangle to reflect the size and position of the client area.  
  
 The **rgrc[1]** and **rgrc[2]** rectangles are valid only if `bCalcValidRects` is **TRUE**. In this case, the **rgrc[1]** rectangle contains the coordinates of the window before it was moved or resized. The **rgrc[2]** rectangle contains the coordinates of the window's client area before the window was moved. All coordinates are relative to the parent window or screen.  
  
 The default implementation calculates the size of the client area based on the window characteristics (presence of scroll bars, menu, and so on), and places the result in `lpncsp`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnccreate"></a>  CWnd::OnNcCreate  
 The framework calls this member function prior to the [WM_CREATE](#oncreate) message when the `CWnd` object is first created.  
  
```  
afx_msg BOOL OnNcCreate(LPCREATESTRUCT lpCreateStruct) ;
```  
  
### Parameters  
 `lpCreateStruct`  
 Points to the [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) data structure for `CWnd`.  
  
### Return Value  
 Nonzero if the nonclient area is created. It is 0 if an error occurs; the **Create** function will return **failure** in this case.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncdestroy"></a>  CWnd::OnNcDestroy  
 Called by the framework when the nonclient area is being destroyed, and is the last member function called when the Windows window is destroyed.  
  
```  
afx_msg void OnNcDestroy() ;
```  
  
### Remarks  
 The default implementation performs some cleanup, then calls the virtual member function [PostNcDestroy](#postncdestroy).  
  
 Override `PostNcDestroy` if you want to perform your own cleanup, such as a **delete this** operation. If you override `OnNcDestroy`, you must call `OnNcDestroy` in your base class to ensure that any memory internally allocated for the window is freed.  
  
##  <a name="onnchittest"></a>  CWnd::OnNcHitTest  
 The framework calls this member function for the `CWnd` object that contains the cursor (or the `CWnd` object that used the [SetCapture](#setcapture) member function to capture the mouse input) every time the mouse is moved.  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point) ;
```  
  
### Parameters  
 `point`  
 Contains the x- and y-coordinates of the cursor. These coordinates are always screen coordinates.  
  
### Return Value  
 One of the mouse hit-test enumerated values listed below.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnclbuttondblclk"></a>  CWnd::OnNcLButtonDblClk  
 The framework calls this member function when the user double-clicks the left mouse button while the cursor is within a nonclient area of `CWnd`.  
  
```  
afx_msg void OnNcLButtonDblClk (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, the [WM_SYSCOMMAND](#onsyscommand) message is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnclbuttondown"></a>  CWnd::OnNcLButtonDown  
 The framework calls this member function when the user presses the left mouse button while the cursor is within a nonclient area of the `CWnd` object.  
  
```  
afx_msg void OnNcLButtonDown (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, the [WM_SYSCOMMAND](#onsyscommand) is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received.If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnclbuttonup"></a>  CWnd::OnNcLButtonUp  
 The framework calls this member function when the user releases the left mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg void OnNcLButtonUp (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, [WM_SYSCOMMAND](#onsyscommand) is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmbuttondblclk"></a>  CWnd::OnNcMButtonDblClk  
 The framework calls this member function when the user double-clicks the middle mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg void OnNcMButtonDblClk (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmbuttondown"></a>  CWnd::OnNcMButtonDown  
 The framework calls this member function when the user presses the middle mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg void OnNcMButtonDown (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmbuttonup"></a>  CWnd::OnNcMButtonUp  
 The framework calls this member function when the user releases the middle mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg void OnNcMButtonUp (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmousehover"></a>  CWnd::OnNcMouseHover  
 The framework calls this member function when the cursor hovers over the nonclient area of the window for the period of time specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
afx_msg void OnNcMouseHover (UINT nHitTest,   
    Point CPoint) ;  
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the screen.|  
  
### Remarks  
 This method receives the [WM_NCMOUSEHOVER](http://msdn.microsoft.com/library/windows/desktop/ms645625) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmouseleave"></a>  CWnd::OnNcMouseLeave  
 The framework calls this member function when the cursor leaves the nonclient area of the window specified in a prior call to [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).  
  
```  
afx_msg void OnNcMouseLeave() ;
```  
  
### Remarks  
 This method receives the [WM_NCMOUSELEAVE](http://msdn.microsoft.com/library/windows/desktop/ms645626) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncmousemove"></a>  CWnd::OnNcMouseMove  
 The framework calls this member function when the cursor is moved within a nonclient area.  
  
```  
afx_msg void OnNcMouseMove (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
 If appropriate, the [WM_SYSCOMMAND](#onsyscommand) message is sent.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncpaint"></a>  CWnd::OnNcPaint  
 The framework calls this member function when the nonclient area needs to be painted.  
  
```  
afx_msg void OnNcPaint() ;
```  
  
### Remarks  
 The default implementation paints the window frame.  
  
 An application can override this call and paint its own custom window frame. The clipping region is always rectangular, even if the shape of the frame is altered.  
  
##  <a name="onncrbuttondblclk"></a>  CWnd::OnNcRButtonDblClk  
 The framework calls this member function when the user double-clicks the right mouse button while the cursor is within a nonclient area of `CWnd`.  
  
```  
afx_msg void OnNcRButtonDblClk (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncrbuttondown"></a>  CWnd::OnNcRButtonDown  
 The framework calls this member function when the user presses the right mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg void OnNcRButtonDown (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncrbuttonup"></a>  CWnd::OnNcRButtonUp  
 The framework calls this member function when the user releases the right mouse button while the cursor is within a nonclient area.  
  
```  
afx_msg void OnNcRButtonUp (UINT nHitTest,  
    Point CPoint) ;
```  
  
### Parameters  
 `nHitTest`  
 Specifies the [hit-test code](#onnchittest). A hit test is a test that determines the location of the cursor.  
  
 `point`  
 Specifies a `CPoint` object that contains the x and y screen coordinates of the cursor position. These coordinates are always relative to the upper-left corner of the screen.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncrenderingchanged"></a>  CWnd::OnNcRenderingChanged  
 The framework calls this member when the rendering policy for the nonclient area has changed.  
  
```  
afx_msg void OnNcRenderingChanged (BOOL bIsRendering) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `bIsRendering`|`true` if Desktop Window Manager (DWM) rendering is enabled for the nonclient area of the window; `false` if rendering is disabled.|  
  
### Remarks  
 This method receives the [WM_DWMNCRENDERINGCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388200) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncxbuttondblclk"></a>  CWnd::OnNcXButtonDblClk  
 The framework calls this member function when the user double-clicks XBUTTON1 or XBUTTON2 while the cursor is in the nonclient area of a window.  
  
```  
void OnNcXButtonDblClk (short nHitTest,   
    UINT nButton,   
    Point CPoint) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button is double-clicked, or `XBUTTON2` if the second X button is double-clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms646244) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted to the window that contains the cursor. If a window has captured the mouse, this message is not posted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncxbuttondown"></a>  CWnd::OnNcXButtonDown  
 The framework calls this member function when the user presses XBUTTON1 or XBUTTON2 of the mouse while the cursor is in the nonclient area of a window.  
  
```  
afx_msg void OnNcXButtonDown (short nHitTest,   
    UINT nButton,   
    Point CPoint) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `nButton`|A value of `XBUTTON1` if the first mouse X button is pressed, or `XBUTTON2` if the second X button is pressed.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the screen.|  
  
### Remarks  
 This method receives the [WM_NCXBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645632) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted to the window that contains the cursor. If a window has captured the mouse, this message is not posted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onncxbuttonup"></a>  CWnd::OnNcXButtonUp  
 The framework calls this member function when the user releases XBUTTON1 or XBUTTON2 of the mouse while the cursor is in the nonclient area of a window.  
  
```  
afx_msg void OnNcXButtonUp (short nHitTest,   
    UINT nButton,   
    Point CPoint) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nHitTest`|The hit-test value returned by the [CWnd::DefWindowProc](#defwindowproc) function as a result of processing the [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618) message.|  
|[in] `nButton`|A value of `XBUTTON1` if the first mouse X button is released, or `XBUTTON2` if the second X button is released.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the screen.|  
  
### Remarks  
 This method receives the [WM_NCXBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646240) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. This message is posted to the window that contains the cursor. If a window has captured the mouse, this message is not posted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnextmenu"></a>  CWnd::OnNextMenu  
 The framework calls this member function when when the right or left arrow key is used to switch between the menu bar and the system menu.  
  
```  
afx_msg void OnNextMenu (UINT nKey,  
    LpMdiNextMenu LPMDINEXTMENU) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nKey`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.<br /><br /> For a list of flags, see the "Message Parameters" subheading in [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).|  
|[in] `lpMdiNextMenu`|Pointer to a [MDINEXTMENU](http://msdn.microsoft.com/library/windows/desktop/ms647561) structure that contains information about the menu to be activated.|  
  
### Remarks  
 This method receives the [WM_UNINITMENUPOPUP](http://msdn.microsoft.com/library/windows/desktop/ms647614) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In response to this message, your application can set the `hmenuNext` member of the [MDINEXTMENU](http://msdn.microsoft.com/library/windows/desktop/ms647561) structure to specify the menu to switch to, and the `hwndNext` member to specify the window to receive menu notification messages.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onnotify"></a>  CWnd::OnNotify  
 The framework calls this member function to inform the parent window of a control that an event has occurred in the control or that the control requires some kind of information.  
  
```  
OnNotify BOOL virtuel (WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult) ;
```  
  
### Parameters  
 `wParam`  
 Identifies the control that sends the message if the message is from a control. Otherwise, `wParam` is 0.  
  
 `lParam`  
 Pointer to a notification message ( **NMHDR**) structure that contains the notification code and additional information. For some notification messages, this parameter points to a larger structure that has the **NMHDR** structure as its first member.  
  
 `pResult`  
 Pointer to an **LRESULT** variable in which to store the result code if the message is handled.  
  
### Return Value  
 An application returns nonzero if it processes this message; otherwise 0.  
  
### Remarks  
 `OnNotify` processes the message map for control notification.  
  
 Override this member function in your derived class to handle the **WM_NOTIFY** message. An override will not process the message map unless the base class `OnNotify` is called.  
  
 For more information on the WM_NOTIFY message, see Technical Note 61 (TN061), [ON_NOTIFY and WM_NOTIFY messages](../../mfc/tn061-on-notify-and-wm-notify-messages.md). You may also be interested the related topics described in [Control Topics](../../mfc/controls-mfc.md), and TN062, [Message Reflection for Windows Controls](../../mfc/tn062-message-reflection-for-windows-controls.md).  
  
##  <a name="onnotifyformat"></a>  CWnd::OnNotifyFormat  
 The framework calls this member function to determine if the current window accepts ANSI or Unicode structures in the WM_NOTIFY notification message.  
  
```  
afx_msg UINT OnNotifyFormat (CWnd * pWnd,   
    UINT %n%ncommande) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pWnd`|A pointer to a `CWnd` object that represents the window sending the [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) message.<br /><br /> This parameter is the pointer to a control if the `nCommand` parameter is `NF_QUERY`, or the pointer to the parent window of a control if `nCommand` is `NF_REQUERY`.|  
|[in] `nCommand`|A command value that specializes the **WM_NOTIFY** message. The possible values are:<br /><br /> - `NF_QUERY` -<br />     The message is a query to determine whether ANSI or Unicode structures should be used in **WM_NOTIFY** messages. This message is sent from a control to its parent window during the creation of a control, and in response to the `NF_REQUERY` form of this message.<br />- `NF_REQUERY` -<br />     The message is a request for a control to send the `NF_QUERY` form of this message to its parent window. This request is sent from the parent window, and asks the control to requery the parent about the type of structure to use in **WM_NOTIFY** messages. If the `nCommand` parameter is `NF_REQUERY`, the return value is the result of the requery operation.|  
  
### Return Value  
  
|Return value|Meaning|  
|------------------|-------------|  
|`NFR_ANSI`|ANSI structures should be used in **WM_NOTIFY** messages sent by the control.|  
|`NFR_UNICODE`|Unicode structures should be used in **WM_NOTIFY** messages sent by the control.|  
|0|An error occurred.|  
  
### Remarks  
 This method receives the [WM_NOTIFYFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb775584) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. **WM_NOTIFY** messages are sent from a common control to its parent window, and from the parent window to the common control.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpaint"></a>  CWnd::OnPaint  
 The framework calls this member function when Windows or an application makes a request to repaint a portion of an application's window.  
  
```  
afx_msg void OnPaint() ;
```  
  
### Remarks  
 The [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145137) message is sent when the [UpdateWindow](#updatewindow) or [RedrawWindow](#redrawwindow) member function is called.  
  
 A window may receive internal paint messages as a result of calling the `RedrawWindow` member function with the **RDW_INTERNALPAINT** flag set. In this case, the window may not have an update region. An application should call the [GetUpdateRect](#getupdaterect) member function to determine whether the window has an update region. If `GetUpdateRect` returns 0, the application should not call the [BeginPaint](#beginpaint) and [EndPaint](#endpaint) member functions.  
  
 It is an application's responsibility to check for any necessary internal repainting or updating by looking at its internal data structures for each `WM_PAINT` message because a `WM_PAINT` message may have been caused by both an invalid area and a call to the `RedrawWindow` member function with the **RDW_INTERNALPAINT** flag set.  
  
 An internal `WM_PAINT` message is sent only once by Windows. After an internal `WM_PAINT` message is sent to a window by the `UpdateWindow` member function, no further `WM_PAINT` messages will be sent or posted until the window is invalidated or until the `RedrawWindow` member function is called again with the **RDW_INTERNALPAINT** flag set.  
  
 For information on rendering an image in document/view applications, see [CView::OnDraw](../../mfc/reference/cview-class.md#ondraw).  
  
 For more information about using **WM_Paint**, see the following topics in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]:  
  
- [The WM_PAINT Message](http://msdn.microsoft.com/library/windows/desktop/dd145137)  
  
- [Using the WM_PAINT Message](http://msdn.microsoft.com/library/windows/desktop/dd145193)  
  
##  <a name="onpaintclipboard"></a>  CWnd::OnPaintClipboard  
 A Clipboard owner's `OnPaintClipboard` member function is called by a Clipboard viewer when the Clipboard owner has placed data on the Clipboard in the `CF_OWNERDISPLAY` format and the Clipboard viewer's client area needs repainting.  
  
```  
afx_msg void OnPaintClipboard (CWnd * pClipAppWnd,  
    HPaintStruct HGLOBAL) ;
```  
  
### Parameters  
 `pClipAppWnd`  
 Specifies a pointer to the Clipboard-application window. The pointer may be temporary and should not be stored for later use.  
  
 *hPaintStruct*  
 Identifies a [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) data structure that defines what part of the client area to paint.  
  
### Remarks  
 To determine whether the entire client area or just a portion of it needs repainting, the Clipboard owner must compare the dimensions of the drawing area given in the **rcpaint** member of the `PAINTSTRUCT` structure to the dimensions given in the most recent [OnSizeClipboard](#onsizeclipboard) member function call.  
  
 `OnPaintClipboard` should use the [GlobalLock](http://msdn.microsoft.com/library/windows/desktop/aa366584) Windows function to lock the memory that contains the `PAINTSTRUCT` data structure and unlock that memory with the [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows function before it exits.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpalettechanged"></a>  CWnd::OnPaletteChanged  
 The framework calls this member function for all top-level windows after the window with input focus has realized its logical palette, thereby changing the system palette.  
  
```  
afx_msg void OnPaletteChanged (CWnd * pFocusWnd) ;
```  
  
### Parameters  
 `pFocusWnd`  
 Specifies a pointer to the window that caused the system palette to change. The pointer may be temporary and should not be stored.  
  
### Remarks  
 This call allows a window without the input focus that uses a color palette to realize its logical palettes and update its client area.  
  
 The `OnPaletteChanged` member function is called for all top-level and overlapped windows, including the one that changed the system palette and caused the `WM_PALETTECHANGED` message to be sent. If any child window uses a color palette, this message must be passed on to it.  
  
 To avoid an infinite loop, the window shouldn't realize its palette unless it determines that `pFocusWnd` does not contain a pointer to itself.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpaletteischanging"></a>  CWnd::OnPaletteIsChanging  
 The framework calls this member function to inform applications that an application is going to realize its logical palette.  
  
```  
afx_msg void OnPaletteIsChanging (CWnd * pRealizeWnd) ;
```  
  
### Parameters  
 *pRealizeWnd*  
 Specifies the window that is about to realize its logical palette.  
  
### Remarks  
 This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onparentnotify"></a>  CWnd::OnParentNotify  
 A parent's `OnParentNotify` member function is called by the framework when its child window is created or destroyed, or when the user clicks a mouse button while the cursor is over the child window.  
  
```  
afx_msg void OnParentNotify (UINT message,  
    LPARAM lParam) ;
```  
  
### Parameters  
 `message`  
 Specifies the event for which the parent is being notified and the identifier of the child window. The event is the low-order word of `message`. If the event is `WM_CREATE` or `WM_DESTROY`, the high-order word of `message` is the identifier of the child window; otherwise, the high-order word is undefined. The event (low-order word of `message`) can be any of these values:  
  
- `WM_CREATE` The child window is being created.  
  
- `WM_DESTROY` The child window is being destroyed.  
  
- `WM_LBUTTONDOWN` The user has placed the mouse cursor over the child window and clicked the left mouse button.  
  
- `WM_MBUTTONDOWN` The user has placed the mouse cursor over the child window and clicked the middle mouse button.  
  
- `WM_RBUTTONDOWN` The user has placed the mouse cursor over the child window and clicked the right mouse button.  
  
 `lParam`  
 If the event (low-order word) of `message` is `WM_CREATE` or `WM_DESTROY`, `lParam` specifies the window handle of the child window; otherwise `lParam` contains the x and y coordinates of the cursor. The x coordinate is in the low-order word and the y coordinate is in the high-order word.  
  
### Remarks  
 When the child window is being created, the system calls `OnParentNotify` just before the [Create](#create) member function that creates the window returns. When the child window is being destroyed, the system calls `OnParentNotify` before any processing takes place to destroy the window.  
  
 `OnParentNotify` is called for all ancestor windows of the child window, including the top-level window.  
  
 All child windows except those that have the [WS_EX_NOPARENTNOTIFY](../../mfc/reference/extended-window-styles.md) style send this message to their parent windows. By default, child windows in a dialog box have the **WS_EX_NOPARENTNOTIFY** style unless the child window was created without this style by calling the [CreateEx](#createex) member function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onpowerbroadcast"></a>  CWnd::OnPowerBroadcast  
 The framework calls this member function when a power-management event occurs.  
  
```  
afx_msg UINT OnPowerBroadcast (UINT nPowerEvent,   
    UINT nEventData) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nPowerEvent`|The power-management event.|  
|[in] `nEventData`|Event-specific data.|  
  
### Return Value  
 If the event is a request, return `true` to grant the request, or `BROADCAST_QUERY_DENY` to deny the request.  
  
### Remarks  
 This method receives the [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 The `nPowerEvent` parameter specifies events such as battery power is low, the power status has changed, permission to suspend operation is requested or denied, an operation is resuming automatically after an event, the system is suspending operation, or an operation is resuming after suspension. The `nEventData` parameter is typically not used. For more information, see the `wParam` and `lParam` parameters of the [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onquerydragicon"></a>  CWnd::OnQueryDragIcon  
 The framework calls this member function by a minimized (iconic) window that does not have an icon defined for its class.  
  
```  
afx_msg HCURSOR OnQueryDragIcon() ;
```  
  
### Return Value  
 A doubleword value that contains a cursor or icon handle in the low-order word. The cursor or icon must be compatible with the display driver's resolution. If the application returns **NULL**, the system displays the default cursor. The default return value is **NULL**.  
  
### Remarks  
 The system makes this call to obtain the cursor to display while the user drags the minimized window. If an application returns the handle of an icon or cursor, the system converts it to black-and-white. If an application returns a handle, the handle must identify a monochrome cursor or icon compatible with the display driver's resolution. The application can call the [CWinApp::LoadCursor](../../mfc/reference/cwinapp-class.md#loadcursor) or [CWinApp::LoadIcon](../../mfc/reference/cwinapp-class.md#loadicon) member functions to load a cursor or icon from the resources in its executable file and to obtain this handle.  
  
##  <a name="onqueryendsession"></a>  CWnd::OnQueryEndSession  
 The framework calls this member function when the user chooses to end the Windows session or when an application calls the [ExitWindows](http://msdn.microsoft.com/library/windows/desktop/aa376867) Windows function.  
  
```  
afx_msg BOOL OnQueryEndSession() ;
```  
  
### Return Value  
 Nonzero if an application can be conveniently shut down; otherwise 0.  
  
### Remarks  
 If any application returns 0, the Windows session is not ended. Windows stops calling `OnQueryEndSession` as soon as one application returns 0 and sends the [WM_ENDSESSION](#onendsession) message with a parameter value of **FALSE** for any application that has already returned nonzero.  
  
##  <a name="onquerynewpalette"></a>  CWnd::OnQueryNewPalette  
 The framework calls this member function when the `CWnd` object is about to receive the input focus, giving the `CWnd` an opportunity to realize its logical palette when it receives the focus.  
  
```  
afx_msg BOOL OnQueryNewPalette() ;
```  
  
### Return Value  
 Nonzero if the `CWnd` realizes its logical palette; otherwise 0.  
  
##  <a name="onqueryopen"></a>  CWnd::OnQueryOpen  
 The framework calls this member function when the `CWnd` object is minimized and the user requests that the `CWnd` be restored to its preminimized size and position.  
  
```  
afx_msg BOOL OnQueryOpen() ;
```  
  
### Return Value  
 Nonzero if the icon can be opened, or 0 to prevent the icon from being opened.  
  
### Remarks  
 While in `OnQueryOpen`, `CWnd` should not perform any action that would cause an activation or focus change (for example, creating a dialog box).  
  
##  <a name="onqueryuistate"></a>  CWnd::OnQueryUIState  
 Called to retrieve the user interface (UI) state for a window.  
  
```  
afx_msg UINT OnQueryUIState() ;
```  
  
### Return Value  
 The return value is **NULL** if the focus indicators and the keyboard accelerators are visible. Otherwise, the return value can be one or more of the following values:  
  
- **UISF_HIDEFOCUS** Focus indicators are hidden.  
  
- **UISF_HIDEACCEL** Keyboard accelerators are hidden.  
  
- **UISF_ACTIVE Windows XP:** A control should be drawn in the style used for active controls.  
  
### Remarks  
 This member function emulates the functionality of the [WM_QUERYUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646355) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onrawinput"></a>  CWnd::OnRawInput  
 The framework calls this member function when the current window gets raw input.  
  
```  
afx_msg void OnRawInput (UINT nInputCode,  
    HRawInput HRAWINPUT) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nInputCode`|Input code that indicates whether the input occurred while the application was in the foreground or not. In either case, the application must call [CWnd::DefWindowProc](#defwindowproc) so the system can perform cleanup.<br /><br /> This parameter can be one of the following values:<br /><br /> - `RIM_INPUT` - Input occurred while the application was in the foreground.<br />- `RIM_INPUTSINK` - Input occurred while the application was not in the foreground.|  
|[in] `hRawInput`|Handle to a [RAWINPUT](http://msdn.microsoft.com/library/windows/desktop/ms645562) structure that contains the raw input from the device.|  
  
### Remarks  
 This method receives the [WM_INPUT](http://msdn.microsoft.com/library/windows/desktop/ms646275) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onrbuttondblclk"></a>  CWnd::OnRButtonDblClk  
 The framework calls this member function when the user double-clicks the right mouse button.  
  
```  
afx_msg void OnRButtonDblClk (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if CTRL key is down.  
  
- **MK_LBUTTON** Set if left mouse button is down.  
  
- **MK_MBUTTON** Set if middle mouse button is down.  
  
- **MK_RBUTTON** Set if right mouse button is down.  
  
- **MK_SHIFT** Set if SHIFT key is down.  
  
 `point`  
 Specifies the x and y coordinates of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 Only windows that have the **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) style can receive `OnRButtonDblClk` calls. This is the default for windows within the Microsoft Foundation Class Library. Windows calls `OnRButtonDblClk` when the user presses, releases, and then again presses the right mouse button within the system's double-click time limit. Double-clicking the right mouse button actually generates four events: [WM_RBUTTONDOWN](#onrbuttondown) and [WM_RBUTTONUP](#onrbuttonup) messages, the `OnRButtonDblClk` call, and another `WM_RBUTTONUP` message when the button is released.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onrbuttondown"></a>  CWnd::OnRButtonDown  
 The framework calls this member function when the user presses the right mouse button.  
  
```  
afx_msg void OnRButtonDown (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if CTRL key is down.  
  
- **MK_LBUTTON** Set if left mouse button is down.  
  
- **MK_MBUTTON** Set if middle mouse button is down.  
  
- **MK_RBUTTON** Set if right mouse button is down.  
  
- **MK_SHIFT** Set if SHIFT key is down.  
  
 `point`  
 Specifies the x and y coordinates of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onrbuttonup"></a>  CWnd::OnRButtonUp  
 The framework calls this member function when the user releases the right mouse button.  
  
```  
afx_msg void OnRButtonUp (UINT nIndicateurs,  
    Point CPoint) ;
```  
  
### Parameters  
 `nFlags`  
 Indicates whether various virtual keys are down. This parameter can be any combination of the following values:  
  
- **MK_CONTROL** Set if CTRL key is down.  
  
- **MK_LBUTTON** Set if left mouse button is down.  
  
- **MK_MBUTTON** Set if middle mouse button is down.  
  
- **MK_SHIFT** Set if SHIFT key is down.  
  
 `point`  
 Specifies the x and y coordinates of the cursor. These coordinates are always relative to the upper-left corner of the window.  
  
### Remarks  
 This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onregisteredmousewheel"></a>  CWnd::OnRegisteredMouseWheel  
 The framework calls this member function as a user rotates the mouse wheel and encounters the wheel's next notch.  
  
```  
afx_msg LRESULT OnRegisteredMouseWheel (WPARAM wParam,  
    LPARAM lParam) ;
```  
  
### Parameters  
 `wParam`  
 Horizontal position of the pointer.  
  
 `lParam`  
 Vertical position of the pointer.  
  
### Return Value  
 Insignificant at this time. Always zero.  
  
### Remarks  
 Unless overridden, `OnRegisteredMouseWheel` routes the message to the appropriate window (the parent window with focus), and calls the [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617) handler for that window.  
  
 Override this member function to provide your own message routing or to alter the mouse-wheel scrolling behavior.  
  
> [!NOTE]
> `OnRegisteredMouseWheel` handles messages for Windows 95/98 and Windows NT 3.51. For Windows NT 4.0 message handling, use [OnMouseWheel](#onmousewheel).  
  
##  <a name="onrenderallformats"></a>  CWnd::OnRenderAllFormats  
 The Clipboard owner's `OnRenderAllFormats` member function is called by the framework when the owner application is being destroyed.  
  
```  
afx_msg void OnRenderAllFormats() ;
```  
  
### Remarks  
 The Clipboard owner should render the data in all the formats it is capable of generating and pass a data handle for each format to the Clipboard by calling the [SetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms649051) Windows function. This ensures that the Clipboard contains valid data even though the application that rendered the data is destroyed. The application should call the [OpenClipboard](#openclipboard) member function before calling the [SetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms649051) Windows function and call the [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Windows function afterward.  
  
##  <a name="onrenderformat"></a>  CWnd::OnRenderFormat  
 The Clipboard owner's `OnRenderFormat` member function is called by the framework when a particular format with delayed rendering needs to be rendered.  
  
```  
afx_msg void OnRenderFormat (UINT nFormat) ;
```  
  
### Parameters  
 `nFormat`  
 Specifies the Clipboard format.  
  
### Remarks  
 The receiver should render the data in that format and pass it to the Clipboard by calling the [SetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms649051) Windows function.  
  
 Do not call the `OpenClipboard` member function or the **CloseClipboard** Windows function from within `OnRenderFormat`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsessionchange"></a>  CWnd::OnSessionChange  
 The framework calls this member function to notify an application of a change in session state.  
  
```  
afx_msg void OnSessionChange (UINT nSessionState,   
    UINT nId) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nSessionState`|A status code describes the session state change.|  
|[in] `nId`|A session identifier.|  
  
### Remarks  
 This method receives the [WM_WTSSESSION_CHANGE](http://msdn.microsoft.com/library/aa383828) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 The `nSessionState` parameter specifies that a session is connected or disconnected from the console or a remote terminal, a user logged on or off, a session is locked or unlocked, or a session has changed to remote-controlled status. For more information, see the `wParam` parameter of the the [WM_WTSSESSION_CHANGE](http://msdn.microsoft.com/library/aa383828) message.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsetcursor"></a>  CWnd::OnSetCursor  
 The framework calls this member function if mouse input is not captured and the mouse causes cursor movement within the `CWnd` object.  
  
```  
afx_msg BOOL OnSetCursor (CWnd * pWnd,  
    UINT nHitTest,  
    UINT message) ;
```  
  
### Parameters  
 `pWnd`  
 Specifies a pointer to the window that contains the cursor. The pointer may be temporary and should not be stored for later use.  
  
 `nHitTest`  
 Specifies the [hit-test](#onnchittest) area code. The hit test determines the cursor's location.  
  
 `message`  
 Specifies the mouse message number.  
  
### Return Value  
 Nonzero to halt further processing, or 0 to continue.  
  
### Remarks  
 The default implementation calls the parent window's `OnSetCursor` before processing. If the parent window returns **TRUE**, further processing is halted. Calling the parent window gives the parent window control over the cursor's setting in a child window.  
  
 The default implementation sets the cursor to an arrow if it is not in the client area or to the registered-class cursor if it is.  
  
 If `nHitTest` is **HTERROR** and `message` is a mouse button-down message, the **MessageBeep** member function is called.  
  
 The `message` parameter is 0 when `CWnd` enters menu mode.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsetfocus"></a>  CWnd::OnSetFocus  
 The framework calls this member function after gaining the input focus.  
  
```  
afx_msg void OnSetFocus (CWnd * pOldWnd) ;
```  
  
### Parameters  
 *pOldWnd*  
 Contains the `CWnd` object that loses the input focus (may be **NULL**). The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 To display a caret, `CWnd` should call the appropriate caret functions at this point.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsettingchange"></a>  CWnd::OnSettingChange  
 The framework calls `OnSettingChange` for all top-level windows when the Win32 SystemParametersInfo function changes a system-wide setting.  
  
```  
afx_msg void OnSettingChange (UINT uFlags,  
    LPCTSTR lpszSection) ;
```  
  
### Parameters  
 `uFlags`  
 When the system sends the message as a result of a **SystemParametersInfo** call, this parameter is a flag that indicates the system parameter that was changed. For a list of values, see [SystemParametersInfo](http://msdn.microsoft.com/library/windows/desktop/ms724947) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. When an application sends the message, this parameter must be 0.  
  
 `lpszSection`  
 Points to a string that specifies the name of the section that has changed. (The string does not include the square brackets that enclose the section name.)  
  
### Remarks  
 An application should send the message to all top-level windows when it makes changes to system parameters, and Windows will send the message if the user changes settings via the Control Panel.  
  
 The **ON_WM_SETTINGCHANGE** message is similar to the **ON_WM_WININICHANGE** message, with the following difference:  
  
-   Use **ON_WM_SETTINGCHANGE** when running Windows NT 4.0 or newer, or under Windows 95/98.  
  
-   Use **ON_WININICHANGE** when running Windows NT 3.51 or older. This message is now obsolete.  
  
 You should have only one of these macros in your message map. To write a program that works for both Windows 95/98 and Windows NT 4.0, write a handler for **ON_WM_SETTINGCHANGE**. Under Windows NT 3.51, your handler will be called by `OnSettingChange` and `uFlags` and will always be zero.  
  
##  <a name="onshowwindow"></a>  CWnd::OnShowWindow  
 The framework calls this member function when the `CWnd` object is about to be hidden or shown.  
  
```  
afx_msg void OnShowWindow (BOOL bShow,  
    État UINT) ;
```  
  
### Parameters  
 `bShow`  
 Specifies whether a window is being shown. It is **TRUE** if the window is being shown; it is **FALSE** if the window is being hidden.  
  
 `nStatus`  
 Specifies the status of the window being shown. It is 0 if the message is sent because of a `ShowWindow` member function call; otherwise `nStatus` is one of the following:  
  
- **SW_PARENTCLOSING** Parent window is closing (being made iconic) or a pop-up window is being hidden.  
  
- **SW_PARENTOPENING** Parent window is opening (being displayed) or a pop-up window is being shown.  
  
### Remarks  
 A window is hidden or shown when the `ShowWindow` member function is called, when an overlapped window is maximized or restored, or when an overlapped or pop-up window is closed (made iconic) or opened (displayed on the screen). When an overlapped window is closed, all pop-up windows associated with that window are hidden.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsize"></a>  CWnd::OnSize  
 The framework calls this member function after the window's size has changed.  
  
```  
afx_msg void OnSize (UINT %nLes,  
    int cx,  
    int cy) ;
```  
  
### Parameters  
 `nType`  
 Specifies the type of resizing requested. This parameter can be one of the following values:  
  
- **SIZE_MAXIMIZED** Window has been maximized.  
  
- **SIZE_MINIMIZED** Window has been minimized.  
  
- **SIZE_RESTORED** Window has been resized, but neither **SIZE_MINIMIZED** nor **SIZE_MAXIMIZED** applies.  
  
- **SIZE_MAXHIDE** Message is sent to all pop-up windows when some other window is maximized.  
  
- **SIZE_MAXSHOW** Message is sent to all pop-up windows when some other window has been restored to its former size.  
  
 `cx`  
 Specifies the new width of the client area.  
  
 `cy`  
 Specifies the new height of the client area.  
  
### Remarks  
 If the [SetScrollPos](#setscrollpos) or [MoveWindow](#movewindow) member function is called for a child window from `OnSize`, the `bRedraw` parameter of `SetScrollPos` or `MoveWindow` should be nonzero to cause the `CWnd` to be repainted.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#109](../../mfc/reference/codesnippet/cpp/cwnd-class_50.cpp)]  
  
##  <a name="onsizeclipboard"></a>  CWnd::OnSizeClipboard  
 The Clipboard owner's `OnSizeClipboard` member function is called by the Clipboard viewer when the Clipboard contains data with the `CF_OWNERDISPLAY` attribute and the size of the client area of the Clipboard-viewer window has changed.  
  
```  
afx_msg void OnSizeClipboard (CWnd * pClipAppWnd,  
    HRect HGLOBAL) ;
```  
  
### Parameters  
 `pClipAppWnd`  
 Identifies the Clipboard-application window. The pointer may be temporary and should not be stored.  
  
 *hRect*  
 Identifies a global memory object. The memory object contains a RECT data structure that specifies the area for the Clipboard owner to paint.  
  
### Remarks  
 The `OnSizeClipboard` member function is called with a null rectangle (0,0,0,0) as the new size when the Clipboard application is about to be destroyed or minimized. This permits the Clipboard owner to free its display resources.  
  
 Within `OnSizeClipboard`, an application must use the [GlobalLock](http://msdn.microsoft.com/library/windows/desktop/aa366584) Windows function to lock the memory that contains the RECT data structure. Have the application unlock that memory with the [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows function before it yields or returns control.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsizing"></a>  CWnd::OnSizing  
 The framework calls this member function to indicate that the user is resizing the rectangle.  
  
```  
afx_msg void OnSizing (UINT nSide,  
    LpRect LPRECT) ;
```  
  
### Parameters  
 `nSide`  
 The edge of window to be moved.  
  
 `lpRect`  
 Address of the [CRect](../../atl-mfc-shared/reference/crect-class.md) or [RECT structure](../../mfc/reference/rect-structure1.md) that will contain the item's coordinates.  
  
### Remarks  
 By processing this message, an application can monitor the size and position of the drag rectangle and, if needed, change its size or position.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#110](../../mfc/reference/codesnippet/cpp/cwnd-class_51.cpp)]  
  
##  <a name="onspoolerstatus"></a>  CWnd::OnSpoolerStatus  
 The framework calls this member function from Print Manager whenever a job is added to or removed from the Print Manager queue.  
  
```  
afx_msg void OnSpoolerStatus (état UINT,  
    UINT nJobs) ;
```  
  
### Parameters  
 `nStatus`  
 Specifies the **SP_JOBSTATUS** flag.  
  
 *nJobs*  
 Specifies the number of jobs remaining in the Print Manager queue.  
  
### Remarks  
 This call is for informational purposes only.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onstylechanged"></a>  CWnd::OnStyleChanged  
 The framework calls this member function after the [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) function has changed one or more of the window's styles.  
  
```  
afx_msg void OnStyleChanged (int nStyleType,  
    LpStyleStruct LPSTYLESTRUCT) ;
```  
  
### Parameters  
 `nStyleType`  
 Specifies whether the window's extended or nonextended styles have changed. This parameter can be a combination of the following values:  
  
- **GWL_EXSTYLE** The window's extended styles have changed.  
  
- **GWL_STYLE** The window's nonextended styles have changed.  
  
 `lpStyleStruct`  
 Points to a [STYLESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632607) structure that contains the new styles for the window. An application can examine the styles, but it can not change them.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onstylechanging"></a>  CWnd::OnStyleChanging  
 The framework calls this member function when the [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) function is about to change one or more of the window's styles.  
  
```  
afx_msg void OnStyleChanging (int nStyleType,  
    LpStyleStruct LPSTYLESTRUCT) ;
```  
  
### Parameters  
 `nStyleType`  
 Specifies whether the window's extended or nonextended styles have changed. This parameter can be a combination of the following values:  
  
- **GWL_EXSTYLE** The window's extended styles have changed.  
  
- **GWL_STYLE** The window's nonextended styles have changed.  
  
 `lpStyleStruct`  
 Points to a [STYLESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632607) structure that contains the new styles for the window. An application can examine the styles and change them.  
  
### Remarks  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyschar"></a>  CWnd::OnSysChar  
 The framework calls this member function if `CWnd` has the input focus and the [WM_SYSKEYUP](#onsyskeyup) and [WM_SYSKEYDOWN](#onsyskeydown) messages are translated.  
  
```  
afx_msg void OnSysChar (UINT nChar,  
    UINT nRepCnt,  
    UINT nIndicateurs) ;
```  
  
### Parameters  
 `nChar`  
 Specifies the ASCII-character key code of a Control-menu key.  
  
 `nRepCnt`  
 Specifies the repeat count (the number of times the keystroke is repeated as a result of the user holding down the key).  
  
 `nFlags`  
 The `nFlags` parameter can have these values:  
  
|Value|Meaning|  
|-----------|-------------|  
|0-15|Specifies the repeat count. The value is the number of times the keystroke is repeated as a result of the user holding down the key..|  
|16-23|Specifies the scan code. The value depends on the original equipment manufacturer (OEM)|  
|24|Specifies whether the key is an extended key, such as the right-hand ALT and CTRL keys that appear on an enhanced 101- or 102-key keyboard. The value is 1 if it is an extended key; otherwise, it is 0.|  
|25-28|Used internally by Windows.|  
|29|Specifies the context code. The value is 1 if the ALT key is held down while the key is pressed; otherwise, the value is 0.|  
|30|Specifies the previous key state. The value is 1 if the key is down before the message is sent, or it is 0 if the key is up.|  
|31|Specifies the transition state. The value is 1 if the key is being released, or it is 0 if the key is being pressed.|  
  
### Remarks  
 It specifies the virtual key code of the Control-menu key. (For a list of of standard virtual key codes, see Winuser.h)  
  
 When the context code is 0, `WM_SYSCHAR` can pass the [WM_SYSCHAR](http://msdn.microsoft.com/library/windows/desktop/ms646357) message to the [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows function, which will handle it as though it were a normal key message instead of a system character-key. This allows accelerator keys to be used with the active window even if the active window does not have the input focus.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyscolorchange"></a>  CWnd::OnSysColorChange  
 The framework calls this member function for all top-level windows when a change is made in the system color setting.  
  
```  
afx_msg void OnSysColorChange() ;
```  
  
### Remarks  
 Windows calls `OnSysColorChange` for any window that is affected by a system color change.  
  
 Applications that have brushes that use the existing system colors should delete those brushes and re-create them with the new system colors.  
  
##  <a name="onsyscommand"></a>  CWnd::OnSysCommand  
 The framework calls this member function when the user selects a command from the Control menu, or when the user selects the Maximize or the Minimize button.  
  
```  
afx_msg void OnSysCommand (UINT nID,  
    LPARAM lParam) ;
```  
  
### Parameters  
 `nID`  
 Specifies the type of system command requested. This parameter can be any one of the following values:  
  
- **SC_CLOSE** Close the `CWnd` object.  
  
- **SC_HOTKEY** Activate the `CWnd` object associated with the application-specified hot key. The low-order word of `lParam` identifies the `HWND` of the window to activate.  
  
- **SC_HSCROLL** Scroll horizontally.  
  
- **SC_KEYMENU** Retrieve a menu through a keystroke.  
  
- **SC_MAXIMIZE** (or **SC_ZOOM**)   Maximize the `CWnd` object.  
  
- **SC_MINIMIZE** (or **SC_ICON**)   Minimize the `CWnd` object.  
  
- **SC_MOUSEMENU** Retrieve a menu through a mouse click.  
  
- **SC_MOVE** Move the `CWnd` object.  
  
- **SC_NEXTWINDOW** Move to the next window.  
  
- **SC_PREVWINDOW** Move to the previous window.  
  
- **SC_RESTORE** Restore window to normal position and size.  
  
- **SC_SCREENSAVE** Executes the screen-saver application specified in the [boot] section of the SYSTEM.INI file.  
  
- **SC_SIZE** Size the `CWnd` object.  
  
- **SC_TASKLIST** Execute or activate the Windows Task Manager application.  
  
- **SC_VSCROLL** Scroll vertically.  
  
 `lParam`  
 If a Control-menu command is chosen with the mouse, `lParam` contains the cursor coordinates. The low-order word contains the x coordinate, and the high-order word contains the y coordinate. Otherwise this parameter is not used.  
  
- **SC_HOTKEY** Activate the window associated with the application-specified hot key. The low-order word of `lParam` identifies the window to activate.  
  
- **SC_SCREENSAVE** Execute the screen-save application specified in the Desktop section of Control Panel.  
  
### Remarks  
 By default, `OnSysCommand` carries out the Control-menu request for the predefined actions specified in the preceding table.  
  
 In `WM_SYSCOMMAND` messages, the four low-order bits of the `nID` parameter are used internally by Windows. When an application tests the value of `nID`, it must combine the value 0xFFF0 with the `nID` value by using the bitwise-AND operator to obtain the correct result.  
  
 The menu items in a Control menu can be modified with the `GetSystemMenu`, `AppendMenu`, `InsertMenu`, and `ModifyMenu` member functions. Applications that modify the Control menu must process `WM_SYSCOMMAND` messages, and any `WM_SYSCOMMAND` messages not handled by the application must be passed on to `OnSysCommand`. Any command values added by an application must be processed by the application and cannot be passed to `OnSysCommand`.  
  
 An application can carry out any system command at any time by passing a `WM_SYSCOMMAND` message to `OnSysCommand`.  
  
 Accelerator (shortcut) keystrokes that are defined to select items from the Control menu are translated into `OnSysCommand` calls; all other accelerator keystrokes are translated into [WM_COMMAND](#oncommand) messages.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsysdeadchar"></a>  CWnd::OnSysDeadChar  
 The framework calls this member function if the `CWnd` object has the input focus when the [OnSysKeyUp](#onsyskeyup) or [OnSysKeyDown](#onsyskeydown) member function is called.  
  
```  
afx_msg void OnSysDeadChar (UINT nChar,  
    UINT nRepCnt,  
    UINT nIndicateurs) ;
```  
  
### Parameters  
 `nChar`  
 Specifies the dead-key character value.  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed; otherwise 0).|  
|14|Previous key state (1 if the key is down before the call, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
### Remarks  
 It specifies the character value of a dead key.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyskeydown"></a>  CWnd::OnSysKeyDown  
 If the `CWnd` object has the input focus, the `OnSysKeyDown` member function is called by the framework when the user holds down the ALT key and then presses another key.  
  
```  
afx_msg void OnSysKeyDown (UINT nChar,  
    UINT nRepCnt,  
    UINT nIndicateurs) ;
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the key being pressed. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed, 0 otherwise).|  
|14|Previous key state (1 if the key is down before the message is sent, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For `OnSysKeyDown` calls, the key-transition bit (bit 15) is 0. The context-code bit (bit 13) is 1 if the ALT key is down while the key is pressed; it is 0 if the message is sent to the active window because no window has the input focus.  
  
### Remarks  
 If no window currently has the input focus, the active window's `OnSysKeyDown` member function is called. The `CWnd` object that receives the message can distinguish between these two contexts by checking the context code in `nFlags`.  
  
 When the context code is 0, the `WM_SYSKEYDOWN` message received by `OnSysKeyDown` can be passed to the [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows function, which will handle it as though it were a normal key message instead of a system-key message. This allows accelerator keys to be used with the active window even if the active window does not have the input focus.  
  
 Because of auto-repeat, more than one `OnSysKeyDown` call may occur before the [WM_SYSKEYUP](#onsyskeyup) message is received. The previous key state (bit 14) can be used to determine whether the `OnSysKeyDown` call indicates the first down transition or a repeated down transition.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onsyskeyup"></a>  CWnd::OnSysKeyUp  
 If the `CWnd` object has the focus, the `OnSysKeyUp` member function is called by the framework when the user releases a key that was pressed while the ALT key was held down.  
  
```  
afx_msg void OnSysKeyUp (UINT nChar,  
    UINT nRepCnt,  
    UINT nIndicateurs) ;
```  
  
### Parameters  
 `nChar`  
 Specifies the virtual key code of the key being pressed. For a list of of standard virtual key codes, see Winuser.h  
  
 `nRepCnt`  
 Specifies the repeat count.  
  
 `nFlags`  
 Specifies the scan code, key-transition code, previous key state, and context code, as shown in the following list:  
  
|Value|Meaning|  
|-----------|-------------|  
|0–7|Scan code (OEM-dependent value). Low byte of high-order word.|  
|8|Extended key, such as a function key or a key on the numeric keypad (1 if it is an extended key; otherwise 0).|  
|9–10|Not used.|  
|11–12|Used internally by Windows.|  
|13|Context code (1 if the ALT key is held down while the key is pressed, 0 otherwise).|  
|14|Previous key state (1 if the key is down before the message is sent, 0 if the key is up).|  
|15|Transition state (1 if the key is being released, 0 if the key is being pressed).|  
  
 For `OnSysKeyUp` calls, the key-transition bit (bit 15) is 1. The context-code bit (bit 13) is 1 if the ALT key is down while the key is pressed; it is 0 if the message is sent to the active window because no window has the input focus.  
  
### Remarks  
 If no window currently has the input focus, the active window's `OnSysKeyUp` member function is called. The `CWnd` object that receives the call can distinguish between these two contexts by checking the context code in `nFlags`.  
  
 When the context code is 0, the `WM_SYSKEYUP` message received by `OnSysKeyUp` can be passed to the [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows function, which will handle it as though it were a normal key message instead of a system-key message. This allows accelerator (shortcut) keys to be used with the active window even if the active window does not have the input focus.  
  
 For IBM Enhanced 101- and 102-key keyboards, enhanced keys are the right ALT and the right CTRL keys on the main section of the keyboard; the INS, DEL, HOME, END, PAGE UP, PAGE DOWN, and arrow keys in the clusters to the left of the numeric keypad; and the slash (/) and ENTER keys in the numeric keypad. Some other keyboards may support the extended-key bit in `nFlags`.  
  
 For non-U.S. Enhanced 102-key keyboards, the right ALT key is handled as the CTRL+ALT key combination. The following shows the sequence of messages and calls that result when the user presses and releases this key:  
  
|Sequence|Function Accessed|Message Passed|  
|--------------|-----------------------|--------------------|  
|1.|[WM_KEYDOWN](#onkeydown)|**VK_CONTROL**|  
|2.|[WM_KEYDOWN](#onkeydown)|**VK_MENU**|  
|3.|[WM_KEYUP](#onkeyup)|**VK_CONTROL**|  
|4.|[WM_SYSKEYUP](http://msdn.microsoft.com/library/windows/desktop/ms646287)|**VK_MENU**|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="ontcard"></a>  CWnd::OnTCard  
 The framework calls this member function when the user clicks an authorable button.  
  
```  
afx_msg void OnTCard (UINT idAction,  
    DwActionData DWORD) ;
```  
  
### Parameters  
 `idAction`  
 Indicates the action the user has taken. This parameter can be one of these values:  
  
- **IDABORT** The user clicked an authorable Abort button.  
  
- **IDCANCEL** The user clicked an authorable Cancel button.  
  
- **IDCLOSE** The user closed the training card.  
  
- **IDHELP** The user clicked an authorable Windows Help button.  
  
- **IDIGNORE** The user clicked an authorable Ignore button.  
  
- **IDOK** The user clicked an authorable OK button.  
  
- **IDNO** The user clicked an authorable No button.  
  
- **IDRETRY** The user clicked an authorable Retry button.  
  
- **HELP_TCARD_DATA** The user clicked an authorable button. The `dwActionData` parameter contains a long integer specified by the help author.  
  
- **HELP_TCARD_NEXT** The user clicked an authorable Next button.  
  
- **HELP_TCARD_OTHER_CALLER** Another application has requested training cards.  
  
- **IDYES** The user clicked an authorable Yes button.  
  
 `dwActionData`  
 If `idAction` specifies **HELP_TCARD_DATA**, this parameter is a long integer specified by the help author. Otherwise, this parameter is zero.  
  
### Remarks  
 This function is called only when an application has initiated a training card with Windows Help. An application initiates a training card by specifying the **HELP_TCARD** command in a call to the [WinHelp](../../mfc/reference/cwinapp-class.md#winhelp) function.  
  
##  <a name="ontimechange"></a>  CWnd::OnTimeChange  
 The framework calls this member function after the system time is changed.  
  
```  
afx_msg void OnTimeChange() ;
```  
  
### Remarks  
 Have any application that changes the system time send this message to all top-level windows. To send the `WM_TIMECHANGE` message to all top-level windows, an application can use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function with its *hwnd* parameter set to **HWND_BROADCAST**.  
  
##  <a name="ontimer"></a>  CWnd::OnTimer  
 The framework calls this member function after each interval specified in the [SetTimer](#settimer) member function used to install a timer.  
  
```  
afx_msg void OnTimer (UINT_PTR nIDEvent) ;
```  
  
### Parameters  
 `nIDEvent`  
 Specifies the identifier of the timer.  
  
### Remarks  
 The [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows function sends a [WM_TIMER](http://msdn.microsoft.com/library/windows/desktop/ms644902) message when no other messages are in the application's message queue.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
### Example  
  See the example in [CWnd::SetTimer](#settimer).  
  
##  <a name="ontoolhittest"></a>  CWnd::OnToolHitTest  
 The framework calls this member function to detemine whether a point is in the bounding rectangle of the specified tool.  
  
```  
OnToolHitTest INT_PTR virtuel (point CPoint,  
    TOOLINFO* pTI) const ;  
```  
  
### Parameters  
 `point`  
 Specifies the x- and y-coordinate of the cursor. These coordinates are always relative to the upper-left corner of the window  
  
 `pTI`  
 A pointer to a [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) structure. The following structure values are set by default:  
  
- *hwnd* = `m_hWnd` Handle to a window  
  
- `uId` = **(UINT)hWndChild** Handle to a child window  
  
- `uFlags` &#124;= **TTF_IDISHWND** Handle of the tool  
  
- `lpszText` = **LPSTR_TEXTCALLBACK** Pointer to the string that is to be displayed in the specified window  
  
### Return Value  
 If the tooltip control was found, the window control ID. If the tooltip control was not found, -1.  
  
### Remarks  
 If the point is in the rectangle, it retrieves information about the tool.  
  
 If the area with which the tooltip is associated is not a button, `OnToolHitTest` sets the structure flags to **TTF_NOTBUTTON** and **TTF_CENTERTIP**.  
  
 Override `OnToolHitTest` to provide different information than the default provides.  
  
 See [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256), in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], for more information about the structure.  
  
##  <a name="ontouchinput"></a>  CWnd::OnTouchInput  
 Process single input from Windows touch.  
  
```  
virtuel BOOL OnTouchInput (CPoint pt,  
    int nInputNumber,  
    int nInputsCount,  
    PInput PTOUCHINPUT) ;
```  
  
### Parameters  
 `pt`  
 Point where screen has been touched (in the client coordinates).  
  
 `nInputNumber`  
 Number of touch input.  
  
 `nInputsCount`  
 Total number of touch inputs.  
  
 `pInput`  
 Pointer to TOUCHINPUT structure.  
  
### Return Value  
 `TRUE` if the application processes Windows touch input; otherwise `FALSE`.  
  
### Remarks  
  
##  <a name="ontouchinputs"></a>  CWnd::OnTouchInputs  
 Processes inputs from Windows touch.  
  
```  
virtuel BOOL OnTouchInputs (UINT nInputsCount,  
    PTOUCHINPUT pInputs) ;
```  
  
### Parameters  
 `nInputsCount`  
 Total number of Windows touch inputs.  
  
 `pInputs`  
 Array of TOUCHINPUT.  
  
### Return Value  
 `TRUE` if application processes Windows touch inputs; otherwise `FALSE`.  
  
### Remarks  
  
##  <a name="onunichar"></a>  CWnd::OnUniChar  
 The framework calls this member function when a key is pressed. That is, the current window has the keyboard focus and a [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) message is translated by the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) function.  
  
```  
afx_msg void OnUniChar (UINT nChar,   
    UINT nRepCnt,   
    UINT nIndicateurs) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nChar`|Specifies the character code of the pressed key.|  
|[in] `nRepCnt`|Specifies the repeat count for the current message. The value is the number of times the keystroke is autorepeated as a result of the user holding down the key. If the keystroke is held long enough, multiple messages are sent. However, the repeat count is not cumulative.|  
|[in] `nFlags`|Flags that specify the scan code, extended key, context code, previous key state, and transition state, as shown in the following table:<br /><br /> **0-7:** Specifies the scan code. The value depends on the original equipment manufacturer (OEM).<br /><br /> **8:** Specifies an extended key, such as the right-hand ALT and CTRL keys that appear on an enhanced 101 or 102-key keyboard. The flag is 1 if the key is an extended key; otherwise, it is 0.<br /><br /> **9-12:**  Used internally by Windows.<br /><br /> **13:**  Specifies the context code. The flag is 1 if the ALT key is held down while the key is pressed; otherwise, the value is 0.<br /><br /> **14:**  Specifies the previous key state. The flag is 1 if the key is down before the message is sent, or 0 if the key is up.<br /><br /> **15:**  Specifies the transition state. The flag is 1 if the key is being released, or 0 if the key is being pressed.|  
  
### Remarks  
 This method receives the [WM_UNICHAR](http://msdn.microsoft.com/library/windows/desktop/ms646288) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. The [WM_UNICHAR](http://msdn.microsoft.com/library/windows/desktop/ms646288) message is designed to send or post Unicode characters to ANSI windows. It is equivalent to the [WM_CHAR](http://msdn.microsoft.com/library/windows/desktop/ms646276) message, but uses Unicode Transformation Format-32 encoding (UTF-32), whereas the [WM_CHAR](http://msdn.microsoft.com/library/windows/desktop/ms646276) message uses UTF-16.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onuninitmenupopup"></a>  CWnd::OnUnInitMenuPopup  
 The framework calls this member function when a drop-down menu or submenu has been destroyed.  
  
```  
afx_msg void OnUnInitMenuPopup (CMenu * pPopupMenu,   
    UINT nIndicateurs) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `pMenu`|Pointer to the [CMenu](../../mfc/reference/cmenu-class.md) object that represents the menu or submenu.|  
|[in] `nFlags`|The menu that was destroyed. Currently, it can only be the window menu, `MF_SYSMENU`.|  
  
### Remarks  
 This method receives the [WM_UNINITMENUPOPUP](http://msdn.microsoft.com/library/windows/desktop/ms647614) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onupdateuistate"></a>  CWnd::OnUpdateUIState  
 Called to to change the user interface (UI) state for the specified window and all its child windows.  
  
```  
afx_msg void OnUpdateUIState (UINT %4%nsortie de l’action,  
    UINT nUIElement) ;
```  
  
### Parameters  
 `nAction`  
 Specifies the action to be performed. Can be one of the following values:  
  
- **UIS_CLEAR** The UI state element (specified by `nUIElement`) should be hidden.  
  
- **UIS_INITIALIZE** The UI state element (specified by `nUIElement`) should be changed based on the last input event. For more information, see the **Remarks** section of [WM_UPDATEISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646361).  
  
- **UIS_SET** The UI state element (specified by `nUIElement`) should be visible.  
  
 `nUIElement`  
 Specifies which UI state elements are affected or the style of the control. Can be one of the following values:  
  
- **UISF_HIDEACCEL** Keyboard accelerators.  
  
- **UISF_HIDEFOCUS** Focus indicators.  
  
- **UISF_ACTIVE Windows XP:** A control should be drawn in the style used for active controls.  
  
### Remarks  
 This member function emulates the functionality of the [WM_UPDATEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646361) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onuserchanged"></a>  CWnd::OnUserChanged  
 The framework calls this member for all windows after the user has logged on or off.  
  
```  
afx_msg void OnUserChanged() ;
```  
  
### Remarks  
 This method receives the [WM_USERCHANGED](http://msdn.microsoft.com/library/windows/desktop/ms632651) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. When the user logs on or off, the operating system updates user-specific settings. The system sends this message immediately after updating the settings.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onvkeytoitem"></a>  CWnd::OnVKeyToItem  
 If the `CWnd` object owns a list box with the [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) style, the list box will send the `WM_VKEYTOITEM` message in response to a `WM_KEYDOWN` message.  
  
```  
int afx_msg OnVKeyToItem (UINT nKey,  
    CListBox * pListBox,  
    UINT nIndex) ;
```  
  
### Parameters  
 `nKey`  
 Specifies the virtual key code of the key that the user pressed. For a list of of standard virtual key codes, see Winuser.h  
  
 `pListBox`  
 Specifies a pointer to the list box. The pointer may be temporary and should not be stored for later use.  
  
 `nIndex`  
 Specifies the current caret position.  
  
### Return Value  
 Specifies the action that the application performed in response to the message. A return value of –2 indicates that the application handled all aspects of selecting the item and requires no further action by the list box. A return value of –1 indicates that the list box should perform the default action in response to the keystroke. A return value of 0 or greater specifies the zero-based index of an item in the list box and indicates that the list box should perform the default action for the keystroke on the given item.  
  
### Remarks  
 This member function is called by the framework only for list boxes that have the [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) style.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onvscroll"></a>  CWnd::OnVScroll  
 The framework calls this member function when the user clicks the window's vertical scroll bar.  
  
```  
afx_msg void OnVScroll (UINT nSBCode,  
    NPos UINT,  
    CScrollBar* pScrollBar) ;
```  
  
### Parameters  
 `nSBCode`  
 Specifies a scroll-bar code that indicates the user's scrolling request. This parameter can be one of the following:  
  
- **SB_BOTTOM** Scroll to bottom.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINEDOWN** Scroll one line down.  
  
- **SB_LINEUP** Scroll one line up.  
  
- **SB_PAGEDOWN** Scroll one page down.  
  
- **SB_PAGEUP** Scroll one page up.  
  
- **SB_THUMBPOSITION** Scroll to the absolute position. The current position is provided in `nPos`.  
  
- **SB_THUMBTRACK** Drag scroll box to specified position. The current position is provided in `nPos`.  
  
- **SB_TOP** Scroll to top.  
  
 `nPos`  
 Contains the current scroll-box position if the scroll-bar code is **SB_THUMBPOSITION** or **SB_THUMBTRACK**; otherwise not used. Depending on the initial scroll range, `nPos` may be negative and should be cast to an `int` if necessary.  
  
 `pScrollBar`  
 If the scroll message came from a scroll-bar control, contains a pointer to the control. If the user clicked a window's scroll bar, this parameter is **NULL**. The pointer may be temporary and should not be stored for later use.  
  
### Remarks  
 `OnVScroll` typically is used by applications that give some feedback while the scroll box is being dragged.  
  
 If `OnVScroll` scrolls the contents of the `CWnd` object, it must also reset the position of the scroll box with the [SetScrollPos](#setscrollpos) member function.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onvscrollclipboard"></a>  CWnd::OnVScrollClipboard  
 The Clipboard owner's `OnVScrollClipboard` member function is called by the Clipboard viewer when the Clipboard data has the `CF_OWNERDISPLAY` format and there is an event in the Clipboard viewer's vertical scroll bar.  
  
```  
afx_msg void OnVScrollClipboard (CWnd * pClipAppWnd,  
    UINT nSBCode,  
    NPos UINT) ;
```  
  
### Parameters  
 `pClipAppWnd`  
 Specifies a pointer to a Clipboard-viewer window. The pointer may be temporary and should not be stored for later use.  
  
 `nSBCode`  
 Specifies one of the following scroll-bar values:  
  
- **SB_BOTTOM** Scroll to bottom.  
  
- **SB_ENDSCROLL** End scroll.  
  
- **SB_LINEDOWN** Scroll one line down.  
  
- **SB_LINEUP** Scroll one line up.  
  
- **SB_PAGEDOWN** Scroll one page down.  
  
- **SB_PAGEUP** Scroll one page up.  
  
- **SB_THUMBPOSITION** Scroll to the absolute position. The current position is provided in `nPos`.  
  
- **SB_TOP** Scroll to top.  
  
 `nPos`  
 Contains the scroll-box position if the scroll-bar code is **SB_THUMBPOSITION**; otherwise `nPos` is not used.  
  
### Remarks  
 The owner should scroll the Clipboard image, invalidate the appropriate section, and update the scroll-bar values.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwindowmaximizedchanged"></a>  CWnd::OnWindowMaximizedChanged  
 The framework calls this member when the current window is maximized, and the window is composed by the Desktop Window Manager (DWM).  
  
```  
afx_msg void OnWindowMaximizedChanged (BOOL bIsMaximized) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `bIsMaximized`|`true` if the current window is maximized, and `false` if it is not.|  
  
### Remarks  
 This method receives the [WM_DWMWINDOWMAXIMIZEDCHANGE](http://msdn.microsoft.com/library/windows/desktop/dd388201) notification message, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwindowposchanged"></a>  CWnd::OnWindowPosChanged  
 The framework calls this member function when the size, position, or Z-order has changed as a result of a call to the [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) member function or another window-management function.  
  
```  
afx_msg void OnWindowPosChanged (WINDOWPOS * lpwndpos) ;
```  
  
### Parameters  
 `lpwndpos`  
 Points to a [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) data structure that contains information about the window's new size and position.  
  
### Remarks  
 The default implementation sends the [WM_SIZE](http://msdn.microsoft.com/library/windows/desktop/ms632646) and [WM_MOVE](http://msdn.microsoft.com/library/windows/desktop/ms632631) messages to the window. These messages are not sent if an application handles the `OnWindowPosChanged` call without calling its base class. It is more efficient to perform any move or size change processing during the call to `OnWindowPosChanged` without calling its base class.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwindowposchanging"></a>  CWnd::OnWindowPosChanging  
 The framework calls this member function when the size, position, or Z-order is about to change as a result of a call to the [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) member function or another window-management function.  
  
```  
afx_msg void OnWindowPosChanging (WINDOWPOS * lpwndpos) ;
```  
  
### Parameters  
 `lpwndpos`  
 Points to a `WINDOWPOS` data structure that contains information about the window's new size and position.  
  
### Remarks  
 An application can prevent changes to the window by setting or clearing the appropriate bits in the **flags** member of the [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) structure.  
  
 For a window with the [WS_OVERLAPPED](../../mfc/reference/window-styles.md) or [WS_THICKFRAME](../../mfc/reference/window-styles.md) style, the default implementation sends a [WM_GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) message to the window. This is done to validate the new size and position of the window and to enforce the **CS_BYTEALIGNCLIENT** and **CS_BYTEALIGN** client styles. An application can override this functionality by not calling its base class.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwininichange"></a>  CWnd::OnWinIniChange  
 The framework calls this member function after a change has been made to the Windows initialization file, WIN.INI.  
  
```  
afx_msg void OnWinIniChange (LPCTSTR lpszSection) ;
```  
  
### Parameters  
 `lpszSection`  
 Points to a string that specifies the name of the section that has changed. (The string does not include the square brackets that enclose the section name.)  
  
### Remarks  
 The [SystemParametersInfo](http://msdn.microsoft.com/library/windows/desktop/ms724947) Windows function calls `OnWinIniChange` after an application uses the function to change a setting in the WIN.INI file.  
  
 To send the `WM_WININICHANGE` message to all top-level windows, an application can use the [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows function with its *hwnd* parameter set to **HWND_BROADCAST**.  
  
 If an application changes many different sections in WIN.INI at the same time, the application should send one `WM_WININICHANGE` message with `lpszSection` set to **NULL**. Otherwise, an application should send `WM_WININICHANGE` each time it makes a change to WIN.INI.  
  
 If an application receives an `OnWinIniChange` call with `lpszSection` set to **NULL**, the application should check all sections in WIN.INI that affect the application.  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onwndmsg"></a>  CWnd::OnWndMsg  
 This member function is called by `WindowProc`, or is called during message reflection.  
  
```  
virtuel BOOL OnWndMsg (UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult) ;
```  
  
### Parameters  
 `message`  
 Specifies the message to be sent.  
  
 `wParam`  
 Specifies additional message-dependent information.  
  
 `lParam`  
 Specifies additional message-dependent information.  
  
 `pResult`  
 The return value of [WindowProc](#windowproc). Depends on the message; may be **NULL**.  
  
### Return Value  
 **TRUE** if message was handled; otherwise **FALSE**.  
  
### Remarks  
 `OnWndMsg` determines the message type and either calls the appropriate framework function (for example, [OnCommand](#oncommand) for **WM_COMMAND**) or finds the appropriate message in the message map.  
  
 For more information about message reflection, see [Handling Reflected Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="onxbuttondblclk"></a>  CWnd::OnXButtonDblClk  
 The framework calls this member function when the user double-clicks XBUTTON1 or XBUTTON2 while the cursor is in the client area of a window.  
  
```  
afx_msg void OnXButtonDblClk (UINT nIndicateurs,   
    UINT nButton,   
    Point CPoint) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button is double-clicked, or `XBUTTON2` if the second X button is double-clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms646244) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. If the mouse is not captured, the message is posted to the window beneath the cursor. Otherwise, the message is posted to the window that has captured the mouse.  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onxbuttondown"></a>  CWnd::OnXButtonDown  
 The framework calls this member function when the user presses XBUTTON1 or XBUTTON2 while the cursor is in the client area of a window.  
  
```  
afx_msg void OnXButtonDown (UINT nIndicateurs,   
    UINT nButton,   
    Point CPoint) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button was clicked, or `XBUTTON2` if the second X button was clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646245) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. If the mouse is not captured, the message is posted to the window beneath the cursor. Otherwise, the message is posted to the window that has captured the mouse.  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="onxbuttonup"></a>  CWnd::OnXButtonUp  
 The framework calls this member function when the user releases XBUTTON1 or XBUTTON2 while the cursor is in the client area of a window.  
  
```  
afx_msg void OnXButtonUp (UINT nIndicateurs,   
    UINT nButton,   
    Point CPoint) ;
```  
  
### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|[in] `nFlags`|A bitwise combination (OR) of flags that indicate which modifier keys are pressed. For example, the `MK_CONTROL` flag indicates that the CTRL key is pressed.|  
|[in] `nButton`|A value of `XBUTTON1` if the first Microsoft Intellimouse X button was double-clicked, or `XBUTTON2` if the second X button was double-clicked.|  
|[in] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that specifies the *x* and *y* coordinates of the cursor relative to the upper-left corner of the client area.|  
  
### Remarks  
 This method receives the [WM_XBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646246) notification, which is described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. If the mouse is not captured, the message is posted to the window beneath the cursor. Otherwise, the message is posted to the window that has captured the mouse.  
  
 The `nFlags` parameter can be a combination of modifier keys listed in the following table. For more information, see [About Mouse Input](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
|Modifier Key|Description|  
|------------------|-----------------|  
|MK_CONTROL|The CTRL key is pressed.|  
|MK_LBUTTON|The left mouse button is pressed.|  
|MK_MBUTTON|The middle mouse button is pressed.|  
|MK_RBUTTON|The right mouse button is pressed.|  
|MK_SHIFT|The SHIFT key is pressed.|  
|MK_XBUTTON1|The XBUTTON1 mouse button of the Microsoft IntelliMouse is pressed.|  
|MK_XBUTTON2|The XBUTTON2 mouse button of the Microsoft IntelliMouse is pressed.|  
  
> [!NOTE]
>  This member function is called by the framework to allow your application to handle a Windows message. The parameters passed to your function reflect the parameters received by the framework when the message was received. If you call the base-class implementation of this function, that implementation will use the parameters originally passed with the message and not the parameters you supply to the function.  
  
##  <a name="openclipboard"></a>  CWnd::OpenClipboard  
 Opens the Clipboard.  
  
```  
BOOL OpenClipboard() ;
```  
  
### Return Value  
 Nonzero if the Clipboard is opened via `CWnd`, or 0 if another application or window has the Clipboard open.  
  
### Remarks  
 Other applications will not be able to modify the Clipboard until the [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Windows function is called.  
  
 The current `CWnd` object will not become the owner of the Clipboard until the [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) Windows function is called.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#111](../../mfc/reference/codesnippet/cpp/cwnd-class_52.cpp)]  
  
##  <a name="operator_hwnd"></a>  CWnd::operator HWND  
 Use this operator to get the handle to the `CWnd` object.  
  
```  
opérateur HWND() const ;  
```  
  
##  <a name="operator_neq"></a>  CWnd::operator !=  
 Compares two `CWnd` objects to determine if they do not have the same [m_hWnd](#m_hwnd).  
  
```  
Opérateur BOOL ! = (const CWnd se wnd) const ;  
```  
  
### Parameters  
 `wnd`  
 A reference to a `CWnd` object.  
  
### Return Value  
 Nonzero if equal; otherwise 0.  
  
##  <a name="operator_eq_eq"></a>  CWnd::operator ==  
 Compares two `CWnd` objects to determine if they have the same [m_hWnd](#m_hwnd).  
  
```  
Opérateur BOOL == (const CWnd se wnd) const ;  
```  
  
### Parameters  
 `wnd`  
 A reference to a `CWnd` object.  
  
### Return Value  
 Nonzero if equal; otherwise 0.  
  
##  <a name="paintwindowlesscontrols"></a>  CWnd::PaintWindowlessControls  
 Draws windowless controls on the control container.  
  
```  
BOOL PaintWindowlessControls(CDC* pDC) ;
```  
  
### Parameters  
 `pDC`  
 The device context on which to draw the windowless controls.  
  
### Return Value  
 Returns TRUE if there is a control container and the windowless controls are drawn successfully, otherwise FALSE.  
  
##  <a name="postmessage"></a>  CWnd::PostMessage  
 Places a message in the window's message queue and then returns without waiting for the corresponding window to process the message.  
  
```  
BOOL PostMessage (UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0) ;
```  
  
### Parameters  
 `message`  
 Specifies the message to be posted.  
  
 `wParam`  
 Specifies additional message information. The content of this parameter depends on the message being posted.  
  
 `lParam`  
 Specifies additional message information. The content of this parameter depends on the message being posted.  
  
### Return Value  
 Nonzero if the message is posted; otherwise 0.  
  
### Remarks  
 Messages in a message queue are retrieved by calls to the [GetMessage](http://msdn.microsoft.com/library/windows/desktop/ms644936) or [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Windows function.  
  
 The Windows [PostMessage](http://msdn.microsoft.com/library/windows/desktop/ms644944) function can be used to access another application.  
  
### Example  
  See the example for [AfxGetMainWnd](../../mfc/reference/application-information-and-management.md#afxgetmainwnd).  
  
##  <a name="postncdestroy"></a>  CWnd::PostNcDestroy  
 Called by the default [OnNcDestroy](#onncdestroy) member function after the window has been destroyed.  
  
```  
PostNcDestroy() void virtuel ;
```  
  
### Remarks  
 Derived classes can use this function for custom cleanup such as the deletion of the **this** pointer.  
  
##  <a name="precreatewindow"></a>  CWnd::PreCreateWindow  
 Called by the framework before the creation of the Windows window attached to this `CWnd` object.  
  
```  
virtuel BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### Parameters  
 *cs*  
 A [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) structure.  
  
### Return Value  
 Nonzero if the window creation should continue; 0 to indicate creation failure.  
  
### Remarks  
  
> [!WARNING]
> `CWnd::PreCreateWindow` now assigns the hMenu member of `cs` to the `this` pointer if the menu is `NULL` and the style contains `WS_CHILD`. For proper functionality, ensure that your dialog control has an ID that is not `NULL`.  
>   
>  This change fixes a crash in managed/native interop scenarios. A `TRACE` statement in `CWnd::Create` alerts the developer of the problem.  
  
 Never call this function directly.  
  
 The default implementation of this function checks for a **NULL** window class name and substitutes an appropriate default. Override this member function to modify the `CREATESTRUCT` structure before the window is created.  
  
 Each class derived from `CWnd` adds its own functionality to its override of `PreCreateWindow`. By design, these derivations of `PreCreateWindow` are not documented. To determine the styles appropriate to each class and the interdependencies between the styles, you can examine the MFC source code for your application's base class. If you choose to override **PreCreateWindow,** you can determine whether the styles used in your application's base class provide the functionality you need by using information gathered from the MFC source code.  
  
 For more information on changing window styles, see the [Changing the Styles of a Window Created by MFC](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#112](../../mfc/reference/codesnippet/cpp/cwnd-class_53.cpp)]  
  
##  <a name="presubclasswindow"></a>  CWnd::PreSubclassWindow  
 This member function is called by the framework to allow other necessary subclassing to occur before the window is subclassed.  
  
```  
PreSubclassWindow() void virtuel ;
```  
  
### Remarks  
 Overriding this member function allows for dynamic subclassing of controls. It is an advanced overridable.  
  
##  <a name="pretranslatemessage"></a>  CWnd::PreTranslateMessage  
 Used by class [CWinApp](../../mfc/reference/cwinapp-class.md) to translate window messages before they are dispatched to the [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) and [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows functions.  
  
```  
virtuel BOOL PreTranslateMessage(MSG* pMsg) ;
```  
  
### Parameters  
 `pMsg`  
 Points to a [MSG](../../mfc/reference/msg-structure1.md) structure that contains the message to process.  
  
### Return Value  
 Nonzero if the message was translated and should not be dispatched; 0 if the message was not translated and should be dispatched.  
  
##  <a name="print"></a>  CWnd::Print  
 Call this member function to draw the current window in the specified device context, which is most commonly in a printer device context.  
  
```  
void Print (CDC * pDC,  
    DwFlags DWORD) const ;  
```  
  
### Parameters  
 `pDC`  
 A pointer to a device context.  
  
 `dwFlags`  
 Specifies the drawing options. This parameter can be one or more of these flags:  
  
- `PRF_CHECKVISIBLE` Draw the window only if it is visible.  
  
- `PRF_CHILDREN` Draw all visible children windows.  
  
- `PRF_CLIENT` Draw the client area of the window.  
  
- `PRF_ERASEBKGND` Erase the background before drawing the window.  
  
- `PRF_NONCLIENT` Draw the nonclient area of the window.  
  
- `PRF_OWNED` Draw all owned windows.  
  
### Remarks  
 [CWnd::DefWindowProc](#defwindowproc) function processes this message based on which drawing option is specified:  
  
-   If `PRF_CHECKVISIBLE` is specified and the window is not visible, do nothing.  
  
-   If `PRF_NONCLIENT` is specified, draw the nonclient area in the given device context.  
  
-   If `PRF_ERASEBKGND` is specified, send the window a [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message.  
  
-   If `PRF_CLIENT` is specified, send the window a [WM_PRINTCLIENT](http://msdn.microsoft.com/library/windows/desktop/dd145217) message.  
  
-   If `PRF_CHILDREN` is set, send each visible child window a [WM_PRINT](http://msdn.microsoft.com/library/windows/desktop/dd145216) message.  
  
-   If `PRF_OWNED` is set, send each visible owned window a `WM_PRINT` message.  
  
##  <a name="printclient"></a>  CWnd::PrintClient  
 Call this member function to draw any window in the specified device context (usually a printer device context).  
  
```  
void PrintClient (CDC * pDC,  
    DwFlags DWORD) const ;  
```  
  
### Parameters  
 `pDC`  
 A pointer to a device context.  
  
 `dwFlags`  
 Specifies drawing options. This parameter can be one or more of these flags:  
  
- `PRF_CHECKVISIBLE` Draw the window only if it is visible.  
  
- `PRF_CHILDREN` Draw all visible children windows.  
  
- `PRF_CLIENT` Draw the client area of the window.  
  
- `PRF_ERASEBKGND` Erase the background before drawing the window.  
  
- `PRF_NONCLIENT` Draw the nonclient area of the window.  
  
- `PRF_OWNED` Draw all owned windows.  
  
##  <a name="printwindow"></a>  CWnd::PrintWindow  
 Copies a visual window into the specified device context, typically a printer DC.  
  
```  
BOOL PrintWindow (CDC * pDC,  
    UINT nIndicateurs) const ;  
```  
  
### Parameters  
 `pDC`  
 A pointer to the device context to be printed to.  
  
 `nFlags`  
 Specifies the drawing options. For a list of possible values, see [PrintWindow](http://msdn.microsoft.com/library/windows/desktop/dd162869).  
  
### Return Value  
 Nonzero if the function succeeds; otherwise 0.  
  
### Remarks  
 This member function emulates the functionality of the function [PrintWindow](http://msdn.microsoft.com/library/windows/desktop/dd162869), as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="redrawwindow"></a>  CWnd::RedrawWindow  
 Updates the specified rectangle or region in the given window's client area.  
  
```  
BOOL RedrawWindow (LPCRECT lpRectUpdate = NULL,  
    CRgn * prgnUpdate = NULL,  
    Les indicateurs UINT = RDW_INVALIDATE | RDW_UPDATENOW | RDW_ERASE) ;
```  
  
### Parameters  
 `lpRectUpdate`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) containing the coordinates of the update rectangle. This parameter is ignored if *prgnUpdate* contains a valid region handle.  
  
 *prgnUpdate*  
 Identifies the update region. If both *prgnUpdate* and `lpRectUpdate` are **NULL**, the entire client area is added to the update region.  
  
 `flags`  
 The following flags are used to invalidate the window:  
  
- **RDW_ERASE** Causes the window to receive a [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message when the window is repainted. The **RDW_INVALIDATE** flag must also be specified; otherwise **RDW_ERASE** has no effect.  
  
- **RDW_FRAME** Causes any part of the nonclient area of the window that intersects the update region to receive a [WM_NCPAINT](http://msdn.microsoft.com/library/windows/desktop/dd145212) message. The **RDW_INVALIDATE** flag must also be specified; otherwise **RDW_FRAME** has no effect.  
  
- **RDW_INTERNALPAINT** Causes a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message to be posted to the window regardless of whether the window contains an invalid region.  
  
- **RDW_INVALIDATE** Invalidate `lpRectUpdate` or *prgnUpdate* (only one may be not **NULL**). If both are **NULL**, the entire window is invalidated.  
  
 The following flags are used to validate the window:  
  
- **RDW_NOERASE** Suppresses any pending `WM_ERASEBKGND` messages.  
  
- **RDW_NOFRAME** Suppresses any pending `WM_NCPAINT` messages. This flag must be used with **RDW_VALIDATE** and is typically used with **RDW_NOCHILDREN**. This option should be used with care, as it could prevent parts of a window from painting properly.  
  
- **RDW_NOINTERNALPAINT** Suppresses any pending internal `WM_PAINT` messages. This flag does not affect `WM_PAINT` messages resulting from invalid areas.  
  
- **RDW_VALIDATE** Validates `lpRectUpdate` or *prgnUpdate* (only one may be not **NULL**). If both are **NULL**, the entire window is validated. This flag does not affect internal `WM_PAINT` messages.  
  
 The following flags control when repainting occurs. Painting is not performed by the `RedrawWindow` function unless one of these bits is specified.  
  
- **RDW_ERASENOW** Causes the affected windows (as specified by the **RDW_ALLCHILDREN** and **RDW_NOCHILDREN** flags) to receive `WM_NCPAINT` and `WM_ERASEBKGND` messages, if necessary, before the function returns. `WM_PAINT` messages are deferred.  
  
- **RDW_UPDATENOW** Causes the affected windows (as specified by the **RDW_ALLCHILDREN** and **RDW_NOCHILDREN** flags) to receive `WM_NCPAINT`, `WM_ERASEBKGND`, and `WM_PAINT` messages, if necessary, before the function returns.  
  
 By default, the windows affected by the `RedrawWindow` function depend on whether the specified window has the **WS_CLIPCHILDREN** style. The child windows of **WS_CLIPCHILDREN** windows are not affected. However, those windows that are not **WS_CLIPCHILDREN** windows are recursively validated or invalidated until a **WS_CLIPCHILDREN** window is encountered. The following flags control which windows are affected by the `RedrawWindow` function:  
  
- **RDW_ALLCHILDREN** Includes child windows, if any, in the repainting operation.  
  
- **RDW_NOCHILDREN** Excludes child windows, if any, from the repainting operation.  
  
### Return Value  
 Nonzero if the window was redrawn successfully; otherwise 0.  
  
### Remarks  
 When the `RedrawWindow` member function is used to invalidate part of the desktop window, that window does not receive a [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message. To repaint the desktop, an application should use [CWnd::ValidateRgn](#validatergn), [CWnd::InvalidateRgn](#invalidatergn), [CWnd::UpdateWindow](#updatewindow), or [RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911)  
  
##  <a name="reflectchildnotify"></a>  CWnd::ReflectChildNotify  
 This message function is called by the framework from [OnChildNotify](#onchildnotify).  
  
```  
BOOL ReflectChildNotify (UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult) ;
```  
  
### Parameters  
 `message`  
 Specifies the message to be reflected.  
  
 `wParam`  
 Specifies additional message-dependent information.  
  
 `lParam`  
 Specifies additional message-dependent information.  
  
 `pResult`  
 The result generated by the child window to be returned by the parent window. Can be **NULL**.  
  
### Return Value  
 **TRUE** if message was reflected; otherwise **FALSE**.  
  
### Remarks  
 It is a helper function which reflects `message` to its source.  
  
 Reflected messages are sent directly to [CWnd::OnWndMsg](#onwndmsg) or [CCmdTarget::OnCmdMsg](../../mfc/reference/ccmdtarget-class.md#oncmdmsg).  
  
 For more information about message reflection, see [Handling Reflected Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="reflectlastmsg"></a>  CWnd::ReflectLastMsg  
 This member function is called by the framework to reflect the last message to the child window.  
  
```  
static BOOL de PASCAL ReflectLastMsg (HWND hWndChild,  
    LRESULT* pResult = NULL) ;
```  
  
### Parameters  
 `hWndChild`  
 A handle to a child window.  
  
 `pResult`  
 The result generated by the child window to be returned by the parent window. Can be **NULL**.  
  
### Return Value  
 Nonzero if the message was handled; otherwise 0.  
  
### Remarks  
 This member function calls [SendChildNotifyLastMsg](#sendchildnotifylastmsg) if the window identified by `hWndChild` is an OLE control or a window in the permanent map.  
  
 For more information about message reflection, see [Handling Reflected Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="releasedc"></a>  CWnd::ReleaseDC  
 Releases a device context, freeing it for use by other applications.  
  
```  
int ReleaseDC (CDC * pDC) ;
```  
  
### Parameters  
 `pDC`  
 Identifies the device context to be released.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 The effect of the `ReleaseDC` member function depends on the device-context type.  
  
 The application must call the `ReleaseDC` member function for each call to the [GetWindowDC](#getwindowdc) member function and for each call to the [GetDC](#getdc) member function.  
  
##  <a name="repositionbars"></a>  CWnd::RepositionBars  
 Called to reposition and resize control bars in the client area of a window.  
  
```  
void RepositionBars (UINT nIDFirst, UINT nIDLast, UINT nIDLeftOver, UINT nFlag = reposDefault, LPRECT lpRectParam = NULL, LPCRECT lpRectClient = NULL, BOOL bStretch = TRUE) ;  
```  
  
### Parameters  
 `nIDFirst`  
 The ID of the first in a range of control bars to reposition and resize.  
  
 `nIDLast`  
 The ID of the last in a range of control bars to reposition and resize.  
  
 `nIDLeftOver`  
 Specifies ID of pane that fills the rest of the client area.  
  
 `nFlag`  
 Can have one of the following values:  
  
- **CWnd::reposDefault** Performs the layout of the control bars. `lpRectParam` is not used and can be **NULL**.  
  
- **CWnd::reposQuery** The layout of the control bars is not done; instead `lpRectParam` is initialized with the size of the client area, as if the layout had actually been done.  
  
- **CWnd::reposExtra** Adds the values of `lpRectParam` to the client area of `nIDLast` and also performs the layout *.*  
  
 `lpRectParam`  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md); the usage of which depends on the value of `nFlag`.  
  
 *lpRectClient*  
 Points to a [RECT structure](../../mfc/reference/rect-structure1.md) containing the available client area. If **NULL**, the window's client area will be used.  
  
 `bStretch`  
 Indicates whether the bar should be stretched to the size of the frame.  
  
### Remarks  
 The `nIDFirst` and `nIDLast` parameters define a range of control-bar IDs to be repositioned in the client area. The `nIDLeftOver` parameter specifies the ID of the child window (normally the view) which is repositioned and resized to fill the rest of the client area not filled by control bars.  
  
##  <a name="runmodalloop"></a>  CWnd::RunModalLoop  
 Call this member function to retrieve, translate, or dispatch messages until [ContinueModal](#continuemodal) returns **FALSE**.  
  
```  
int RunModalLoop (DWORD dwFlags = 0) ;
```  
  
### Parameters  
 `dwFlags`  
 Specifies the Windows message to be sent. Can be one of the following values:  
  
- **MLF_NOIDLEMSG** Don't send [WM_ENTERIDLE](http://msdn.microsoft.com/library/windows/desktop/ms645422) messages to the parent.  
  
- **MLF_NOKICKIDLE** Don't send **WM_KICKIDLE** messages to the window.  
  
- **MLF_SHOWONIDLE** Show the window when message queue goes idle.  
  
### Return Value  
 Specifies the value of the `nResult` parameter passed to the [EndModalLoop](#endmodalloop) member function, which is then used to end the modal loop.  
  
### Remarks  
 By default, `ContinueModal` returns **FALSE** after `EndModalLoop` is called. Returns the value provided as `nResult` to `EndModalLoop`.  
  
##  <a name="screentoclient"></a>  CWnd::ScreenToClient  
 Converts the screen coordinates of a given point or rectangle on the display to client coordinates.  
  
```  
void ScreenToClient (LPPOINT lpPoint) const ;  void ScreenToClient (LPRECT lpRect) const ;  ```  
  
### <a name="parameters"></a>Paramètres  
 `lpPoint`  
 Pointe vers une [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet ou [structure POINT](../../mfc/reference/point-structure1.md) qui contient les coordonnées d’écran à convertir.  
  
 `lpRect`  
 Pointe vers une [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou [Rect, structure](../../mfc/reference/rect-structure1.md) qui contient les coordonnées d’écran à convertir.  
  
### <a name="remarks"></a>Notes  
 Le `ScreenToClient` fonction membre remplace les coordonnées d’écran figurant `lpPoint` ou `lpRect` avec les coordonnées clientes. Les nouvelles coordonnées sont exprimées par rapport au coin supérieur gauche de la `CWnd` zone cliente.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CListCtrl::GetItemRect](../../mfc/reference/clistctrl-class.md#getitemrect).  
  
##  <a name="a-namescrollwindowa--cwndscrollwindow"></a><a name="scrollwindow"></a>CWnd::ScrollWindow  
 Fait défiler le contenu de la zone cliente de l’utilisateur actuel `CWnd` objet.  
  
```  
void ScrollWindow(
    int xAmount,  
    int yAmount,  
    LPCRECT lpRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `xAmount`  
 Spécifie la quantité, en unités de périphérique de défilement horizontal. Ce paramètre doit être une valeur négative pour faire défiler vers la gauche.  
  
 `yAmount`  
 Spécifie la quantité, en unités de périphérique de défilement verticale. Ce paramètre doit être une valeur négative pour défiler vers le haut.  
  
 `lpRect`  
 Pointe vers une [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou [Rect, structure](../../mfc/reference/rect-structure1.md) qui spécifie la partie de la zone cliente de défilement. Si `lpRect` est **NULL**, le défilement de la zone client entière. Le point d’insertion est repositionné si le rectangle de curseur entre en intersection avec le rectangle de défilement.  
  
 `lpClipRect`  
 Pointe vers une `CRect` objet ou `RECT` structure qui spécifie le rectangle de découpage pour faire défiler. Seuls les bits à l’intérieur de ce rectangle défile. Bits en dehors de ce rectangle ne sont pas affectées même si elles se trouvent dans le `lpRect` rectangle. Si `lpClipRect` est **NULL**, aucun découpage n’est effectuée sur le rectangle de défilement.  
  
### <a name="remarks"></a>Remarques  
 Si le point d’insertion se trouve dans le `CWnd` en cours de défilement, `ScrollWindow` masque automatiquement le signe insertion pour l’empêcher d’être effacé et restaure ensuite le point d’insertion après le défilement est terminé. La position du point d’insertion est ajustée en conséquence.  
  
 La zone non traités par le `ScrollWindow` fonction membre n’est pas redessinée mais sont regroupée dans le courant `CWnd` région de mise à jour de l’objet. L’application recevra par la suite un [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message de notification que la région doit être repeinte. Pour repeindre la zone non couvert en même temps que le défilement est terminé, appelez le [UpdateWindow](#updatewindow) fonction membre immédiatement après l’appel `ScrollWindow`.  
  
 Si `lpRect` est **NULL**, les positions des fenêtres enfants dans la fenêtre sont compensées par la quantité spécifiée par `xAmount` et `yAmount`et les zones non valides (non peints) dans le `CWnd` sont également décalée. `ScrollWindow`est plus rapide lorsque `lpRect` est **NULL**.  
  
 Si `lpRect` n’est pas **NULL**, les positions des fenêtres enfants ne sont pas des zones modifiées et non valides dans `CWnd` pas d’offset. Afin d’éviter des problèmes de mise à jour lors de la `lpRect` n’est pas **NULL**, appelez le `UpdateWindow` fonction membre à repeindre `CWnd` avant d’appeler `ScrollWindow`.  
  
##  <a name="a-namescrollwindowexa--cwndscrollwindowex"></a><a name="scrollwindowex"></a>CWnd::ScrollWindowEx  
 Fait défiler le contenu de la zone cliente d’une fenêtre.  
  
```  
int ScrollWindowEx(
    int dx,  
    int dy,  
    LPCRECT lpRectScroll,  
    LPCRECT lpRectClip,  
    CRgn* prgnUpdate,  
    LPRECT lpRectUpdate,  
    UINT flags);
```  
  
### <a name="parameters"></a>Paramètres  
 `dx`  
 Spécifie la quantité, en unités de périphérique de défilement horizontal. Ce paramètre doit avoir une valeur négative pour faire défiler vers la gauche.  
  
 *dy*  
 Spécifie la quantité, en unités de périphérique de défilement verticale. Ce paramètre doit avoir une valeur négative pour défiler vers le haut.  
  
 `lpRectScroll`  
 Pointe vers une [Rect, structure](../../mfc/reference/rect-structure1.md) qui spécifie la partie de la zone cliente de défilement. Si ce paramètre est **NULL**, le défilement de la zone client entière.  
  
 `lpRectClip`  
 Pointe vers une `RECT` structure qui spécifie le rectangle de découpage pour faire défiler. Cette structure est prioritaire sur le rectangle indiqué par `lpRectScroll`. Seuls les bits à l’intérieur de ce rectangle défile. Bits en dehors de ce rectangle ne sont pas affectées même si elles se trouvent dans le `lpRectScroll` rectangle. Si ce paramètre est **NULL**, aucun découpage n’est effectuée sur le rectangle de défilement.  
  
 *prgnUpdate*  
 Identifie la région qui est modifiée pour contenir la région invalidée par défilement. Ce paramètre peut être **NULL**.  
  
 `lpRectUpdate`  
 Pointe vers une `RECT` structure qui recevra les limites du rectangle invalidée par défilement. Ce paramètre peut être **NULL**.  
  
 `flags`  
 Peut avoir l’une des valeurs suivantes :  
  
- **SW_ERASE** lorsque spécifié avec **SW_INVALIDATE**, efface la zone qui vient d’être invalidée en envoyant un [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message dans la fenêtre.  
  
- **SW_INVALIDATE** invalide la région identifiée par *prgnUpdate* après le défilement.  
  
- **SW_SCROLLCHILDREN** fait défiler toutes les fenêtres enfants qui croisent le rectangle indiqué par `lpRectScroll` par le nombre de pixels spécifié dans `dx` et *dy*. Windows envoie une [WM_MOVE](http://msdn.microsoft.com/library/windows/desktop/ms632631) message à toutes les fenêtres enfants qui croisent `lpRectScroll`, même si elles ne sont pas déplacés. Le point d’insertion est repositionné lorsqu’une fenêtre enfant défile et le rectangle de curseur entre en intersection avec le rectangle de défilement.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour est **SIMPLEREGION** (zone rectangulaire invalidé), **COMPLEXREGION** (région invalidée non rectangulaire ; rectangles de chevauchement), ou **NULLREGION** (aucune région invalidée), si la fonction réussit ; sinon, la valeur de retour est **erreur**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est similaire à la [ScrollWindow](http://msdn.microsoft.com/library/windows/desktop/bb787591) fonction, avec quelques fonctionnalités supplémentaires.  
  
 Si [SW_INVALIDATE](http://msdn.microsoft.com/library/windows/desktop/bb787593) et [SW_ERASE](http://msdn.microsoft.com/library/windows/desktop/bb787593) ne sont pas spécifiés, le `ScrollWindowEx` fonction membre n’invalide pas la zone de défilement. Si une de ces indicateurs est définie, `ScrollWindowEx` invalide cette zone. La zone n’est pas mis à jour jusqu'à ce que l’application appelle la [UpdateWindow](http://msdn.microsoft.com/library/windows/desktop/dd145167) fonction membre, appelle le [RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) fonction membre (spécifiant [RDW_UPDATENOW](http://msdn.microsoft.com/library/windows/desktop/dd162911) ou [RDW_ERASENOW](http://msdn.microsoft.com/library/windows/desktop/dd162911)), ou récupère le [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message de la file d’attente de l’application.  
  
 Si la fenêtre a la [WS_CLIPCHILDREN](http://msdn.microsoft.com/library/windows/desktop/ms632679) style, les zones retournés spécifiés par *prgnUpdate* et `lpRectUpdate` représentent la zone totale de la fenêtre de défilement qui doit être mis à jour, y compris toutes les zones dans les fenêtres enfants qui doivent mettre à jour.  
  
 Si le [SW_SCROLLCHILDREN](http://msdn.microsoft.com/library/windows/desktop/bb787593) indicateur est spécifié, Windows sera correctement si pas à jour l’écran défile partie d’une fenêtre enfant. La partie de la fenêtre de défilement enfant qui se trouve en dehors du rectangle source n’est pas effacée et ne sera pas redessinée correctement dans la nouvelle destination. Utilisez le [DeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632681) fonction Windows aux fenêtres enfants de déplacement qui ne se trouvent pas complètement dans le `lpRectScroll` rectangle. Le curseur est repositionné si le **SW_SCROLLCHILDREN** est défini et le rectangle de signe insertion entre en intersection avec le rectangle de défilement.  
  
 Toutes les coordonnées d’entrée et de sortie (pour `lpRectScroll`, `lpRectClip`, `lpRectUpdate`, et *prgnUpdate*) sont supposés pour être dans les coordonnées clientes, indépendamment de si la fenêtre a la **CS_OWNDC** ou **CS_CLASSDC** style de classe. Utilisez le [LPtoDP](http://msdn.microsoft.com/library/windows/desktop/dd145042) et [DPtoLP](http://msdn.microsoft.com/library/windows/desktop/dd162474) des fonctions de Windows pour convertir vers et à partir des coordonnées logiques, si nécessaire.  
  
##  <a name="a-namesendchildnotifylastmsga--cwndsendchildnotifylastmsg"></a><a name="sendchildnotifylastmsg"></a>CWnd::SendChildNotifyLastMsg  
 Cette fonction membre est appelée par l’infrastructure pour fournir un message de notification à une fenêtre enfant, à partir de la fenêtre parente, afin que la fenêtre enfant peut gérer une tâche.  
  
```  
BOOL SendChildNotifyLastMsg(LRESULT* pResult = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pResult`  
 Le résultat généré par la fenêtre enfant doivent être retournées par la fenêtre parente.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fenêtre enfant a traité le message envoyé à son parent ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 `SendChildNotifyLastMsg`envoyer le message en cours à la source s’il s’agit d’un message qui apparaît.  
  
 Pour plus d’informations sur la réflexion de message, consultez [gestion des Messages](../../mfc/handling-reflected-messages.md).  
  
##  <a name="a-namesenddlgitemmessagea--cwndsenddlgitemmessage"></a><a name="senddlgitemmessage"></a>CWnd::SendDlgItemMessage  
 Envoie un message à un contrôle.  
  
```  
LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Spécifie l’identificateur du contrôle de boîte de dialogue qui recevra le message.  
  
 `message`  
 Spécifie le message à envoyer.  
  
 `wParam`  
 Spécifie des informations de message dépendant supplémentaires.  
  
 `lParam`  
 Spécifie des informations de message dépendant supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 Spécifie la valeur retournée par la procédure de fenêtre du contrôle, ou 0 si le contrôle est introuvable.  
  
### <a name="remarks"></a>Remarques  
 Le `SendDlgItemMessage` fonction membre ne retourne pas jusqu'à ce que le message a été traité.  
  
 À l’aide de `SendDlgItemMessage` est identique à l’obtention d’un `CWnd`* sur le contrôle et en appelant le [SendMessage](#sendmessage) fonction membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#113;](../../mfc/reference/codesnippet/cpp/cwnd-class_54.cpp)]  
  
##  <a name="a-namesendmessagea--cwndsendmessage"></a><a name="sendmessage"></a>CWnd::SendMessage  
 Envoie le message spécifié à cette fenêtre.  
  
```  
LRESULT SendMessage(
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `message`  
 Spécifie le message à envoyer.  
  
 `wParam`  
 Spécifie des informations de message dépendant supplémentaires.  
  
 `lParam`  
 Spécifie des informations de message dépendant supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 Le résultat du traitement du message ; sa valeur dépend du message envoyé.  
  
### <a name="remarks"></a>Remarques  
 Le **SendMessage** fonction membre appelle directement de la procédure de fenêtre et ne retourne pas tant que cette procédure de fenêtre a traité le message. Contrairement à la [PostMessage](#postmessage) fonction membre, ce qui place le message dans la file d’attente de messages de la fenêtre et retourne immédiatement.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#101;](../../mfc/reference/codesnippet/cpp/cwnd-class_41.cpp)]  
  
##  <a name="a-namesendmessagetodescendantsa--cwndsendmessagetodescendants"></a><a name="sendmessagetodescendants"></a>CWnd::SendMessageToDescendants  
 Appelez cette fonction membre pour envoyer le message Windows spécifié pour toutes les fenêtres.  
  
```  
void SendMessageToDescendants(
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0,  
    BOOL bDeep = TRUE,  
    BOOL bOnlyPerm = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `message`  
 Spécifie le message à envoyer.  
  
 `wParam`  
 Spécifie des informations de message dépendant supplémentaires.  
  
 `lParam`  
 Spécifie des informations de message dépendant supplémentaires.  
  
 `bDeep`  
 Spécifie le niveau auquel vous souhaitez rechercher. Si **TRUE**, récursivement rechercher tous les enfants ; si **FALSE**, rechercher uniquement les enfants immédiats.  
  
 `bOnlyPerm`  
 Spécifie si le message sera reçu par windows temporaires. Si **TRUE**, windows temporaires peuvent recevoir le message ; si **FALSE**, seul windows permanentes, le message. Pour plus d’informations sur windows temporaires, consultez [Technical Note 3](../../mfc/tn003-mapping-of-windows-handles-to-objects.md).  
  
### <a name="remarks"></a>Notes  
 Si `bDeep` est **FALSE**, le message est envoyé uniquement pour les enfants immédiats de la fenêtre ; sinon, le message est envoyé à toutes les fenêtres.  
  
 Si `bDeep` et `bOnlyPerm` sont **TRUE**, la recherche se poursuit sous windows temporaires. Dans ce cas, que les fenêtres permanentes s’est produites lors de la recherche le message. Si `bDeep` est **FALSE**, le message est envoyé uniquement pour les enfants immédiats de la fenêtre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#114;](../../mfc/reference/codesnippet/cpp/cwnd-class_55.cpp)]  
  
##  <a name="a-namesendnotifymessagea--cwndsendnotifymessage"></a><a name="sendnotifymessage"></a>CWnd::SendNotifyMessage  
 Envoie le message spécifié dans la fenêtre.  
  
```  
BOOL SendNotifyMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `message`  
 Spécifie le message à envoyer.  
  
 `wParam`  
 Spécifie des informations de message dépendant supplémentaires.  
  
 `lParam`  
 Spécifie des informations de message dépendant supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Si la fenêtre a été créée par le thread appelant, `SendNotifyMessage` appelle la procédure de fenêtre pour la fenêtre et ne retourne pas jusqu'à ce que la procédure de fenêtre a traité le message. Si la fenêtre a été créée par un thread différent, `SendNotifyMessage` transmet le message à la procédure de fenêtre et retourne immédiatement ; il n’attend pas la procédure de fenêtre Terminer le traitement du message.  
  
##  <a name="a-namesetactivewindowa--cwndsetactivewindow"></a><a name="setactivewindow"></a>CWnd::SetActiveWindow  
 Rend `CWnd` la fenêtre active.  
  
```  
CWnd* SetActiveWindow();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La fenêtre qui était précédemment active.  
  
 Le pointeur retourné peut être temporaire et ne doit pas être stocké pour une utilisation ultérieure.  
  
### <a name="remarks"></a>Remarques  
 Le `SetActiveWindow` fonction membre doit être utilisée avec précaution, car elle permet à une application en arbitrairement sur la fenêtre active et le focus d’entrée. Normalement, Windows prend en charge de l’activation de tous.  
  
##  <a name="a-namesetcapturea--cwndsetcapture"></a><a name="setcapture"></a>CWnd::SetCapture  
 La souris toutes les entrées à envoyer au cours `CWnd` objet quelle que soit la position du curseur.  
  
```  
CWnd* SetCapture();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’objet de fenêtre précédemment reçu toutes les souris. Il est `NULL` s’il n’existe pas de fenêtre. Le pointeur retourné peut être temporaire et ne doit pas être stocké pour une utilisation ultérieure.  
  
### <a name="remarks"></a>Remarques  
 Lors de la `CWnd` ne requiert plus toutes les entrées de la souris, l’application doit appeler la [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261) fonction afin que les autres fenêtres peuvent recevoir des entrées de la souris.  
  
 Bien que l’entrée de la souris est capturée, aucun `WM_NCHITTEST` ou `WM_SETCURSOR` les messages sont envoyés à la fenêtre active.  
  
##  <a name="a-namesetcaretposa--cwndsetcaretpos"></a><a name="setcaretpos"></a>CWnd::SetCaretPos  
 Définit la position du signe insertion.  
  
```  
static void PASCAL SetCaretPos(POINT point);
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Spécifie la nouvelle x et y coordonnées (dans les coordonnées clientes) du signe insertion.  
  
### <a name="remarks"></a>Remarques  
 Le `SetCaretPos` fonction membre déplace le signe insertion uniquement si elle est détenue par une fenêtre dans la tâche en cours. `SetCaretPos`Déplace le point d’insertion si le signe insertion est masqué ou non.  
  
 Le point d’insertion est une ressource partagée. Une fenêtre ne doit pas placer le signe insertion si elle ne possède pas le signe insertion.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#115;](../../mfc/reference/codesnippet/cpp/cwnd-class_56.cpp)]  
  
##  <a name="a-namesetclipboardviewera--cwndsetclipboardviewer"></a><a name="setclipboardviewer"></a>CWnd::SetClipboardViewer  
 Ajoute cette fenêtre à la chaîne de windows qui sont avertis (au moyen de la `WM_DRAWCLIPBOARD` message) chaque fois que le contenu du Presse-papiers est modifié.  
  
```  
HWND SetClipboardViewer();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Handle vers la fenêtre suivante dans la chaîne de Presse-papiers si l’opération réussit. Les applications doivent enregistrer ce handle (il peut être stocké en tant que variable membre) et l’utiliser pour répondre aux messages en chaîne-Presse-papiers.  
  
### <a name="remarks"></a>Remarques  
 Une fenêtre qui fait partie de la chaîne de Presse-papiers doit répondre aux [WM_DRAWCLIPBOARD](#ondrawclipboard), [WM_CHANGECBCHAIN](#onchangecbchain), et [WM_DESTROY](#ondestroy) des messages et de transmettre le message à la fenêtre suivante de la chaîne.  
  
 Cette fonction membre envoie une `WM_DRAWCLIPBOARD` message dans la fenêtre. Étant donné que le handle vers la fenêtre suivante de la chaîne Presse-papiers n’a pas encore été retourné, l’application ne doit pas passer le `WM_DRAWCLIPBOARD` message reçu au cours de l’appel à `SetClipboardViewer`.  
  
 Pour supprimer de la chaîne Presse-papiers, une application doit appeler la [ChangeClipboardChain](#changeclipboardchain) fonction membre.  
  
##  <a name="a-namesetdlgctrlida--cwndsetdlgctrlid"></a><a name="setdlgctrlid"></a>CWnd::SetDlgCtrlID  
 Définit l’ID de fenêtre ou contrôle de la fenêtre vers une nouvelle valeur.  
  
```  
int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 La nouvelle valeur à définir pour l’identificateur du contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 L’identificateur précédent de la fenêtre, en cas de réussite ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 La fenêtre peut être n’importe quelle fenêtre enfant, non seulement un contrôle dans une boîte de dialogue. La fenêtre ne peut pas être une fenêtre de niveau supérieur.  
  
##  <a name="a-namesetdlgiteminta--cwndsetdlgitemint"></a><a name="setdlgitemint"></a>CWnd::SetDlgItemInt  
 Définit le texte d’un contrôle donné dans une boîte de dialogue pour la représentation sous forme de chaîne d’une valeur d’entier spécifié.  
  
```  
void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Spécifie l’ID d’entier du contrôle d’être modifié.  
  
 `nValue`  
 Spécifie la valeur entière utilisée pour générer le texte de l’élément.  
  
 `bSigned`  
 Spécifie si la valeur entière est signée ou non signée. Si ce paramètre est **TRUE**, `nValue` est signé. Si ce paramètre est **TRUE** et `nValue` est inférieur à 0, un signe moins signe est placé avant le premier chiffre de la chaîne. Si ce paramètre est **FALSE**, `nValue` n’est pas signé.  
  
### <a name="remarks"></a>Notes  
 `SetDlgItemInt`envoie une [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) message au contrôle donné.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWnd::SetDlgItemText](#setdlgitemtext).  
  
##  <a name="a-namesetdlgitemtexta--cwndsetdlgitemtext"></a><a name="setdlgitemtext"></a>CWnd::SetDlgItemText  
 Définit la légende ou le texte d’un contrôle appartenant à une fenêtre ou boîte de dialogue.  
  
```  
void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Identifie le contrôle dont le texte doit être défini.  
  
 `lpszString`  
 Pointe vers une [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet ou chaîne terminée par le caractère null qui contient le texte à copier vers le contrôle.  
  
### <a name="remarks"></a>Notes  
 `SetDlgItemText`envoie une [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) message au contrôle donné.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#116;](../../mfc/reference/codesnippet/cpp/cwnd-class_57.cpp)]  
  
##  <a name="a-namesetforegroundwindowa--cwndsetforegroundwindow"></a><a name="setforegroundwindow"></a>CWnd::SetForegroundWindow  
 Place le thread créé par la fenêtre au premier plan et active la fenêtre.  
  
```  
BOOL SetForegroundWindow();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Entrée au clavier est dirigée vers la fenêtre, et différents signaux visuels sont modifiées pour l’utilisateur. La fenêtre de premier plan est la fenêtre à laquelle l’utilisateur est actuellement chargé. La fenêtre de premier plan s’applique uniquement aux fenêtres de niveau supérieur (zones fenêtres ou boîtes de dialogue de frame).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWnd::FindWindow](#findwindow).  
  
##  <a name="a-namesetfocusa--cwndsetfocus"></a><a name="setfocus"></a>CWnd::SetFocus  
 Revendique le focus d'entrée.  
  
```  
CWnd* SetFocus();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’objet window qui avait le focus d’entrée. Il est **NULL** s’il n’existe pas de fenêtre. Le pointeur retourné peut être temporaire et ne doit pas être stocké.  
  
### <a name="remarks"></a>Remarques  
 Le focus d’entrée dirige toutes les entrées au clavier suivantes dans cette fenêtre. Les fenêtres qui avaient le focus d’entrée le perd.  
  
 Le `SetFocus` fonction membre envoie un [WM_KILLFOCUS](http://msdn.microsoft.com/library/windows/desktop/ms646282) message dans la fenêtre qui perd le focus d’entrée et un [WM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/ms646283) message dans la fenêtre qui reçoit le focus d’entrée. Il active également la fenêtre ou son parent.  
  
 Si la fenêtre active est active mais n’a pas le focus (autrement dit, aucune fenêtre n’a le focus), n’importe quelle touche enfoncée produira les messages [WM_SYSCHAR](#onsyschar), [WM_SYSKEYDOWN](#onsyskeydown), ou [WM_SYSKEYUP](#onsyskeyup).  
  
##  <a name="a-namesetfonta--cwndsetfont"></a><a name="setfont"></a>CWnd::SetFont  
 Envoie le `WM_SETFONT` message dans la fenêtre à utiliser la police spécifiée.  
  
```  
void SetFont(
    CFont* pFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pFont`  
 Pointeur vers un `CFont` objet.  
  
 `bRedraw`  
 `TRUE`dans la fenêtre pour redessiner immédiatement après celui-ci traite le `WM_SETFONT` message ; sinon `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode n’a aucun effet à moins que la fenêtre traite le `WM_SETFONT` message. Nombreuses classes MFC dérivées de `CWnd` traiter ce message, car ils sont attachés à une classe de fenêtre prédéfini qui inclut un gestionnaire de messages pour le `WM_SETFONT` message. Pour utiliser cette méthode, les classes que vous dérivez de `CWnd` doit définir un gestionnaire d’événements pour le `WM_SETFONT` message.  
  
##  <a name="a-nameseticona--cwndseticon"></a><a name="seticon"></a>CWnd::SetIcon  
 Appelez cette fonction membre pour définir le handle de l’icône spécifique, tel qu’identifié par `hIcon`.  
  
```  
HICON SetIcon(
    HICON hIcon,  
    BOOL bBigIcon);
```  
  
### <a name="parameters"></a>Paramètres  
 `hIcon`  
 Handle d’une icône précédent.  
  
 `bBigIcon`  
 Spécifie un pixel 32 par une icône de 32 pixels si **TRUE**; spécifie un pixel 16 par une icône de 16 pixels si **FALSE**.  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle d’une icône.  
  
### <a name="remarks"></a>Remarques  
 Lorsque la classe de fenêtre est inscrit, il sélectionne une icône.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWnd::GetSystemMenu](#getsystemmenu).  
  
##  <a name="a-namesetlayeredwindowattributesa--cwndsetlayeredwindowattributes"></a><a name="setlayeredwindowattributes"></a>CWnd::SetLayeredWindowAttributes  
 Définit la clé de couleur d'opacité et de transparence d'une fenêtre superposée.  
  
```  
BOOL SetLayeredWindowAttributes(
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 `crKey`  
 Pointeur vers un **COLORREF** valeur qui spécifie la clé de couleur de transparence à utiliser lors de la composition de la fenêtre superposée. Tous les pixels de peinture par la fenêtre dans cette couleur est transparents. Pour générer un **COLORREF**, utilisez la macro RVB.  
  
 `bAlpha`  
 Valeur alpha permet de décrire l’opacité de la fenêtre superposée. Pour plus d’informations, consultez la **SourceConstantAlpha** membre de la [BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393) structure. Lorsque `bAlpha` est 0, la fenêtre est complètement transparente. Lorsque `bAlpha` est de 255, la fenêtre est opaque.  
  
 `dwFlags`  
 Spécifie l’action à entreprendre. Ce paramètre peut être une ou plusieurs des valeurs suivantes. Pour obtenir la liste des valeurs possibles, consultez la page [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre émule les fonctionnalités de la fonction [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetmenua--cwndsetmenu"></a><a name="setmenu"></a>CWnd::SetMenu  
 Définit le menu en cours sur le menu spécifié.  
  
```  
BOOL SetMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Paramètres  
 `pMenu`  
 Identifie le nouveau menu. Si ce paramètre est **NULL**, le menu en cours est supprimé.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le menu est modifié ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 La fenêtre est redessiné pour refléter les modifications de menu.  
  
 `SetMenu`pas détruire un menu précédent. Une application doit appeler la [CMenu::DestroyMenu](../../mfc/reference/cmenu-class.md#destroymenu) fonction membre pour accomplir cette tâche.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CMenu::LoadMenu](../../mfc/reference/cmenu-class.md#loadmenu).  
  
##  <a name="a-namesetownera--cwndsetowner"></a><a name="setowner"></a>CWnd::SetOwner  
 Définit le propriétaire de la fenêtre active à l’objet de la fenêtre spécifiée.  
  
```  
void SetOwner(CWnd* pOwnerWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 *pOwnerWnd*  
 Identifie le nouveau propriétaire de l’objet window. Si ce paramètre est **NULL**, l’objet de fenêtre n’a aucun propriétaire.  
  
### <a name="remarks"></a>Notes  
 Cet utilisateur peut recevoir des messages de commande à partir de l’objet en cours de la fenêtre. Par défaut, le parent de la fenêtre active est son propriétaire.  
  
 Il est souvent utile d’établir des connexions entre des objets de fenêtre qui ne sont pas liées à la hiérarchie de la fenêtre. Par exemple, [CToolBar](../../mfc/reference/ctoolbar-class.md) envoie des notifications à son propriétaire plutôt qu’à son parent. Ainsi, la barre d’outils devienne l’enfant d’une fenêtre (par exemple, une fenêtre d’application conteneur OLE) lors de l’envoi de notifications à une autre fenêtre (par exemple, la fenêtre frame en place). En outre, lorsqu’une fenêtre de serveur est désactivée ou activée au cours du déplacement, modification de toute fenêtre de la fenêtre frame est masqué ou affiché. Cette propriété est définie par un appel à `SetOwner`.  
  
 Le concept de propriété de cette fonction est différent du concept de propriété de [GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms633515).  
  
##  <a name="a-namesetparenta--cwndsetparent"></a><a name="setparent"></a>CWnd::SetParent  
 Modifie la fenêtre parent d’une fenêtre enfant.  
  
```  
CWnd* SetParent(CWnd* pWndNewParent);
```  
  
### <a name="parameters"></a>Paramètres  
 *pWndNewParent*  
 Identifie la nouvelle fenêtre parent.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’objet de fenêtre parent précédent en cas de réussite. Le pointeur retourné peut être temporaire et ne doit pas être stocké pour une utilisation ultérieure.  
  
### <a name="remarks"></a>Remarques  
 Si la fenêtre enfant est visible, Windows effectue le redessin appropriée et la mise à jour.  
  
##  <a name="a-namesetpropertya--cwndsetproperty"></a><a name="setproperty"></a>CWnd::SetProperty  
 Appelez cette fonction membre pour définir la propriété de contrôle OLE spécifiée par `dwDispID`.  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwDispID`  
 Identifie la propriété à définir.  
  
 `vtProp`  
 Spécifie le type de la propriété à définir. Pour les valeurs possibles, consultez la section Notes pour [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Un seul paramètre du type spécifié par `vtProp`.  
  
### <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  Cette fonction doit être appelée uniquement sur un `CWnd` objet qui représente un contrôle OLE.  
  
 Pour plus d’informations sur l’utilisation de cette fonction membre avec les conteneurs de contrôles OLE, consultez l’article [conteneurs de contrôles ActiveX : programmation de contrôles ActiveX dans un conteneur de contrôles ActiveX](../../mfc/programming-activex-controls-in-a-activex-control-container.md).  
  
##  <a name="a-namesetredrawa--cwndsetredraw"></a><a name="setredraw"></a>CWnd::SetRedraw  
 Une application appelle `SetRedraw` pour autoriser les modifications à redessiner ou pour éviter que des modifications est redessiné.  
  
```  
void SetRedraw(BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bRedraw`  
 Spécifie l’état de l’indicateur de renouvellement. Si ce paramètre est **TRUE**, l’indicateur de renouvellement est défini ; si **FALSE**, l’indicateur est désactivé.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre Active ou désactive l’indicateur de renouvellement. Si l’indicateur de renouvellement est désactivée, le contenu ne sera pas mis à jour après chaque modification et ne sera pas redessiné jusqu'à ce que l’indicateur de renouvellement est défini. Par exemple, une application qui doit ajouter plusieurs éléments à une zone de liste peut effacer l’indicateur de renouvellement, ajouter les éléments, puis définissez l’indicateur de renouvellement. Enfin, l’application peut appeler le [Invalidate](#invalidate) ou [InvalidateRect](#invalidaterect) fonction membre pour provoquer la zone de liste à être redessinée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#117;](../../mfc/reference/codesnippet/cpp/cwnd-class_58.cpp)]  
  
##  <a name="a-namesetscrollinfoa--cwndsetscrollinfo"></a><a name="setscrollinfo"></a>CWnd::SetScrollInfo  
 Appelez cette fonction membre pour définir les informations qui le `SCROLLINFO` structure conserve sur une barre de défilement.  
  
```  
BOOL SetScrollInfo(
    int nBar,  
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nBar`  
 Spécifie si la barre de défilement est un contrôle ou une partie d’une zone non cliente d’une fenêtre. S’il fait partie de la zone non cliente, nBar indique également si la barre de défilement est positionnée horizontalement, verticalement, ou les deux. Il doit être une des opérations suivantes :  
  
- **SB_CTL** contient les paramètres pour un contrôle de barre de défilement. Le `m_hWnd` membre de données doit être le handle du contrôle de barre de défilement.  
  
- **SB_HORZ** Spécifie que la fenêtre est une barre de défilement horizontale.  
  
- **SB_VERT** Spécifie que la fenêtre est une barre de défilement verticale.  
  
 `lpScrollInfo`  
 Un pointeur vers un [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) structure. Consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur cette structure.  
  
 `bRedraw`  
 Spécifie si la barre de défilement doit être redessinée pour refléter la nouvelle position. Si `bRedraw` est **TRUE**, la barre de défilement est redessinée. S’il s’agit **FALSE**, il n’est pas redessiné. Par défaut, la barre de défilement est redessinée.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la réussite, la valeur de retour est **TRUE**. Sinon, il est **FALSE**.  
  
### <a name="remarks"></a>Notes  
 Le [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) structure contient des informations sur une barre de défilement, y compris les minimale et maximale de défilement positions, la taille de page et la position du curseur de défilement (curseur de défilement). Consultez le `SCROLLINFO` rubrique structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur la modification des valeurs par défaut des structure.  
  
 Les gestionnaires qui indiquent la position de la barre de défilement, de message Windows MFC [CWnd::OnHScroll](#onhscroll) et [CWnd::OnVScroll](#onvscroll), fournir seulement 16 bits de placer les données. [GetScrollInfo](#getscrollinfo) et `SetScrollInfo` fournissent des 32 bits de données de position de barre de défilement. Par conséquent, une application peut appeler `GetScrollInfo` lors du traitement d’une `CWnd::OnHScroll` ou `CWnd::OnVScroll` pour obtenir des données de position de barre de défilement 32 bits.  
  
> [!NOTE]
> [CWnd::GetScrollInfo](#getscrollinfo) permet aux applications d’utiliser des positions de la barre de défilement 32 bits.  
  
##  <a name="a-namesetscrollposa--cwndsetscrollpos"></a><a name="setscrollpos"></a>CWnd::SetScrollPos  
 Définit la position actuelle d’une zone de défilement et, si nécessaire, redessine la barre de défilement pour refléter la nouvelle position du curseur de défilement.  
  
```  
int SetScrollPos(
    int nBar,  
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nBar`  
 Spécifie la barre de défilement à définir. Ce paramètre peut être une des opérations suivantes :  
  
- **SB_HORZ** définit la position du curseur de défilement dans la barre de défilement horizontale de la fenêtre.  
  
- **SB_VERT** définit la position du curseur de défilement dans la barre de défilement verticale de la fenêtre.  
  
 `nPos`  
 Spécifie la nouvelle position du curseur de défilement. Il doit être dans la plage de défilement.  
  
 `bRedraw`  
 Spécifie si la barre de défilement doit être repeinte afin de refléter la nouvelle position de la case de défilement. Si ce paramètre est **TRUE**, la barre de défilement est redessinée ; si **FALSE**, la barre de défilement n’est pas redessinée.  
  
### <a name="return-value"></a>Valeur de retour  
 La position précédente de la case de défilement.  
  
### <a name="remarks"></a>Notes  
 Paramètre `bRedraw` à **FALSE** est utile lorsque la barre de défilement est redessinée par un appel ultérieur à une autre fonction.  
  
##  <a name="a-namesetscrollrangea--cwndsetscrollrange"></a><a name="setscrollrange"></a>CWnd::SetScrollRange  
 Définit les valeurs de position minimale et maximale de la barre de défilement donnée.  
  
```  
void SetScrollRange(
    int nBar,  
    int nMinPos,  
    int nMaxPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nBar`  
 Spécifie la barre de défilement à définir. Ce paramètre peut être une des valeurs suivantes :  
  
- **SB_HORZ** définit la plage de la barre de défilement horizontale de la fenêtre.  
  
- **SB_VERT** définit la plage de la barre de défilement verticale de la fenêtre.  
  
 `nMinPos`  
 Spécifie la valeur minimale que la position du défilement.  
  
 `nMaxPos`  
 Spécifie la position de défilement au maximum.  
  
 `bRedraw`  
 Spécifie si la barre de défilement doit être redessinée pour refléter la modification. Si `bRedraw` est **TRUE**, la barre de défilement est redessinée ; si **FALSE**, la barre de défilement n’est pas redessinée.  
  
### <a name="remarks"></a>Notes  
 Il peut également être utilisé pour masquer ou afficher les barres de défilement standard.  
  
 Une application ne doit pas appeler cette fonction pour masquer une barre de défilement lors du traitement d’un message de notification de barre de défilement.  
  
 Si l’appel à `SetScrollRange` suit immédiatement un appel à la [SetScrollPos](#setscrollpos) fonction membre, le `bRedraw` paramètre dans le `SetScrollPos` fonction membre doit être 0 pour empêcher que la barre de défilement qui est dessiné deux fois.  
  
 La plage par défaut pour une barre de défilement standard est 0 et 100. La plage par défaut pour un contrôle de barre de défilement est vide (à la fois le `nMinPos` et `nMaxPos` les valeurs sont 0). La différence entre les valeurs spécifiées par `nMinPos` et `nMaxPos` ne doit pas être supérieure à **INT_MAX**.  
  
##  <a name="a-namesettimera--cwndsettimer"></a><a name="settimer"></a>CWnd::SetTimer  
 Installe une horloge système.  
  
```  
UINT_PTR SetTimer(
    UINT_PTR nIDEvent,  
    UINT nElapse,  
    void (CALLBACK* lpfnTimer)(HWND,  
    UINT, 
    UINT_PTR, 
    DWORD));
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDEvent`  
 Spécifie l’identificateur du minuteur différente de zéro. Si l’identificateur du minuteur est unique, cette même valeur est retournée par `SetTimer`. Dans le cas contraire, `SetTimer` détermine une nouvelle valeur unique et qui retourne. D’une minuterie de fenêtre (qui a une fonction de rappel NULL), la valeur doit être unique que pour les autres minuteurs windows qui sont associés à la fenêtre active. Pour rappel, timer, la valeur doit être unique pour toutes les minuteries de tous les processus. Par conséquent, lorsque vous créez un minuteur de rappel, il est plus probable que la valeur renvoyée peut-être différer de la valeur que vous spécifiez.  
  
 `nElapse`  
 Spécifie le délai d’attente ou un intervalle en millisecondes.  
  
 `lpfnTimer`  
 Spécifie l’adresse de l’application fourni `TimerProc` fonction de rappel qui traite les [WM_TIMER](http://msdn.microsoft.com/library/windows/desktop/ms644902) messages. Si ce paramètre est `NULL`, le `WM_TIMER` les messages sont placés dans la file d’attente de l’application et gérées par le `CWnd` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 L’identificateur du minuteur de la nouvelle minuterie si la fonction réussit. Cette valeur peut ou peut ne pas être égale à la valeur transmise dans le `nIDEvent` paramètre. Une application doit toujours passer la valeur de retour à la [KillTimer](#killtimer) fonction membre pour mettre fin à la minuterie. Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Une valeur d’intervalle est spécifiée, et chaque fois que l’intervalle est écoulé, le système publie un `WM_TIMER` message à la file d’attente de message l’installation de l’application d’installation ou transmet le message défini par une application `TimerProc` fonction de rappel.  
  
 Le `lpfnTimer` fonction de rappel ne doive pas être nommée `TimerProc`, mais elle doit être déclarée comme statique et définie comme suit.  
  
```  
void CALLBACK TimerProc(
    HWND hWnd,   // handle of CWnd that called SetTimer  
    UINT nMsg,   // WM_TIMER  
    UINT_PTR nIDEvent,   // timer identification  
    DWORD dwTime    // system time);
```  
  
### <a name="example"></a>Exemple  
 Cet exemple utilise `CWnd::SetTimer`, `CWnd::OnTimer`, et `CWnd::KillTimer` gérer `WM_TIMER` messages. Le premier timer est configuré pour envoyer un `WM_TIMER` message dans la fenêtre frame principale toutes les 2 secondes dans `OnStartTimer`. Le `OnTimer` Gestionnaire d’événements gère `WM_TIMER` messages de la fenêtre frame principale. Cette méthode provoque le haut-parleur du PC émettre un signal sonore toutes les 2 secondes. Le deuxième timer envoie un message à la fonction de rappel 3,75 toutes les secondes. `OnStopTimer`arrête les minuteries en appelant `CWnd::KillTimer` pour chaque ID de la minuterie.  
  
 [!code-cpp[NVC_MFCWindowing&#118;](../../mfc/reference/codesnippet/cpp/cwnd-class_59.cpp)]  
  
##  <a name="a-namesetwindowcontexthelpida--cwndsetwindowcontexthelpid"></a><a name="setwindowcontexthelpid"></a>CWnd::SetWindowContextHelpId  
 Appelez cette fonction membre pour associer un identificateur de contexte d’aide à la fenêtre spécifiée.  
  
```  
BOOL SetWindowContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwContextHelpId`  
 L’identificateur de contexte d’aide.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Si une fenêtre enfant n’a pas un identificateur de contexte d’aide, il hérite de l’identificateur de la fenêtre parente. De même, si une fenêtre enfant n’a pas un identificateur de contexte d’aide, il hérite de l’identificateur de la fenêtre propriétaire. Cet héritage d’identificateurs de contexte d’aide permet à une application de définir qu’un seul identificateur pour une boîte de dialogue et tous ses contrôles.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#119;](../../mfc/reference/codesnippet/cpp/cwnd-class_60.cpp)]  
  
##  <a name="a-namesetwindowplacementa--cwndsetwindowplacement"></a><a name="setwindowplacement"></a>CWnd::SetWindowPlacement  
 Définit l'état d'affichage et les positions normale (restaurée), réduite et agrandie d'une fenêtre.  
  
```  
BOOL SetWindowPlacement(const WINDOWPLACEMENT* lpwndpl);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpwndpl`  
 Pointe vers une [WINDOWPLACEMENT](../../mfc/reference/windowplacement-structure.md) structure qui spécifie le nouvel état d’affichage et les positions.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
##  <a name="a-namesetwindowposa--cwndsetwindowpos"></a><a name="setwindowpos"></a>CWnd::SetWindowPos  
 Modifie la taille, la position et la position z des fenêtres publicitaires et de niveau supérieur d’enfants.  
  
```  
BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWndInsertAfter`  
 Identifie la `CWnd` objet précède (dépasser) cela `CWnd` objet dans l’ordre de plan. Ce paramètre peut être un pointeur vers un `CWnd` ou **pointeur** à une des valeurs suivantes :  
  
- **wndBottom** place la fenêtre au bas de l’axe z. Si cette `CWnd` est une fenêtre au premier plan, la fenêtre perd son état au premier plan, le système place la fenêtre au bas de toutes les autres fenêtres.  
  
- **wndTop** place la fenêtre en haut de l’axe z.  
  
- **wndTopMost** place la fenêtre au-dessus de toutes les non-fenêtres au premier plan. La fenêtre conserve sa position supérieure même lorsqu’elle est désactivée.  
  
- **wndNoTopMost** repositionne la fenêtre vers le haut de toutes les fenêtres de premier (autrement dit, derrière toutes les fenêtres de niveau supérieur). Cet indicateur n’a aucun effet si la fenêtre est déjà une fenêtre de premier.  
  
 Pour les règles concernant l’utilisation de ce paramètre, consultez la section « Notes » de cette rubrique.  
  
 *x*  
 Spécifie la nouvelle position du côté gauche de la fenêtre.  
  
 *y*  
 Spécifie la nouvelle position du bord supérieur de la fenêtre.  
  
 `cx`  
 Spécifie la nouvelle largeur de la fenêtre.  
  
 `cy`  
 Spécifie la nouvelle hauteur de la fenêtre.  
  
 `nFlags`  
 Spécifie le dimensionnement et les options de positionnement. Ce paramètre peut être une combinaison des indicateurs suivants :  
  
- **SWP_DRAWFRAME** Dessine une image (définie lors de la création de la fenêtre) autour de la fenêtre.  
  
- **SWP_FRAMECHANGED** envoie un `WM_NCCALCSIZE` de message dans la fenêtre, même si la taille de la fenêtre n’est pas modifiée. Si cet indicateur n’est pas spécifié, `WM_NCCALCSIZE` est envoyée uniquement lorsque la taille de la fenêtre est en cours de modification.  
  
- **SWP_HIDEWINDOW** masque la fenêtre.  
  
- `SWP_NOACTIVATE`N’active pas la fenêtre. Si cet indicateur n’est pas défini, la fenêtre est activée et déplacée vers le haut le plus haut ou le groupe de premier (selon la configuration de le `pWndInsertAfter` paramètre).  
  
- **SWP_NOCOPYBITS** ignore tout le contenu de la zone cliente. Si cet indicateur n’est pas spécifié, le contenu valid de la zone cliente est enregistré et copié dans la zone cliente, une fois que la fenêtre est dimensionnée ou repositionnée.  
  
- `SWP_NOMOVE`Conserve la position actuelle (ignore le *x* et *y* paramètres).  
  
- **SWP_NOOWNERZORDER** ne modifie pas la position de la fenêtre propriétaire de l’axe z.  
  
- **SWP_NOREDRAW** ne redessine pas les modifications. Si cet indicateur est défini, aucune mise à jour quelconque se produit. Cela s’applique à la zone cliente et une partie de la fenêtre parente non traitée en raison de la fenêtre déplacée la zone non cliente (y compris les titre et barres de défilement). Lorsque cet indicateur est défini, l’application doit explicitement invalider ou redessiner toutes les parties de la fenêtre et une fenêtre parente qui doit être redessiné.  
  
- **SWP_NOREPOSITION** identique **SWP_NOOWNERZORDER**.  
  
- **SWP_NOSENDCHANGING** empêche la fenêtre de réception du `WM_WINDOWPOSCHANGING` message.  
  
- `SWP_NOSIZE`Conserve la taille actuelle (ignore le `cx` et `cy` paramètres).  
  
- `SWP_NOZORDER`Conserve le classement actuel (ignore `pWndInsertAfter`).  
  
- **SWP_SHOWWINDOW** affiche la fenêtre.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Windows sont classés à l’écran en fonction de leur ordre de plan ; la fenêtre en haut de l’ordre de plan apparaît au-dessus de toutes les autres fenêtres dans l’ordre.  
  
 Toutes les coordonnées des fenêtres enfants sont coordonnées clientes (par rapport à l’angle supérieur gauche de la zone cliente de la fenêtre parente).  
  
 Une fenêtre peut être déplacée vers le haut de l’ordre de plan soit en définissant le `pWndInsertAfter` paramètre **se wndTopMost** et s’assurer que le `SWP_NOZORDER` indicateur est pas défini ou en définissant une fenêtre de l’ordre de plan afin qu’elle soit au-dessus des fenêtres de niveau supérieur existants. Établissement d’une fenêtre de premier supérieure, ses fenêtres enfants sont également apportées au premier plan. Ses propriétaires ne sont pas modifiés.  
  
 Fenêtre de niveau supérieur n’est plus au premier plan si elle est repositionné vers le bas ( **se wndBottom**) ou après n’importe quelle fenêtre de premier de l’axe z. Établissement d’une fenêtre de niveau supérieur non au premier plan, tous ses propriétaires et ses fenêtres enfants sont également mis à windows de premier.  
  
 Si ni `SWP_NOACTIVATE` ni `SWP_NOZORDER` est spécifié (autrement dit, lorsque l’application demande qu’une fenêtre être simultanément activée et placée dans l’ordre spécifié), la valeur spécifiée dans `pWndInsertAfter` est utilisé uniquement dans les circonstances suivantes :  
  
-   Ni **se wndTopMost** ni **se wndNoTopMost** est spécifié dans le `pWndInsertAfter` paramètre.  
  
-   Cette fenêtre n’est pas la fenêtre active.  
  
 Une application ne peut pas activer une fenêtre inactive sans également l’afficher en haut de l’axe z. Les applications peuvent modifier l’ordre de plan d’une fenêtre activée sans restrictions.  
  
 Une fenêtre de premier peut posséder une fenêtre de niveau supérieur, mais pas l’inverse. N’importe quelle fenêtre (par exemple, une boîte de dialogue) appartenant à une fenêtre de niveau supérieur est lui-même effectué une fenêtre de niveau supérieur pour s’assurer que tous les appartient windows restent au-dessus de leur propriétaire.  
  
 Avec Windows 3.1 et versions ultérieures, windows peuvent être déplacés vers le haut de l’ordre de plan et verrouillés en définissant leur **WS_EX_TOPMOST** styles. Une telle fenêtre au premier plan maintient sa position supérieure, même quand désactivée. Par exemple, en sélectionnant la commande WinHelp toujours visible la fenêtre d’aide au premier plan et il puis reste visible lorsque vous revenez à votre application.  
  
 Pour créer une fenêtre de niveau supérieur, appelez `SetWindowPos` avec la `pWndInsertAfter` égal au paramètre **se wndTopMost**, ou définir le **WS_EX_TOPMOST** style lors de la création de la fenêtre.  
  
 Si l’ordre de plan contenait toutes les fenêtres avec la **WS_EX_TOPMOST** style, une fenêtre déplacés avec la **se wndTopMost** valeur est placée en haut de toutes les fenêtres de premier, mais en dessous des fenêtres de niveau supérieur. Lorsqu’une application active une fenêtre inactive sans le **WS_EX_TOPMOST** bit, la fenêtre est déplacée au-dessus de toutes les fenêtres de premier mais en dessous des fenêtres de niveau supérieur.  
  
 Si `SetWindowPos` est appelée lorsque le `pWndInsertAfter` paramètre est **se wndBottom** et `CWnd` est une fenêtre au premier plan, la fenêtre perd son état au premier plan ( **WS_EX_TOPMOST** est désactivée), et le système place la fenêtre au bas de l’axe z.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#120;](../../mfc/reference/codesnippet/cpp/cwnd-class_61.cpp)]  
  
##  <a name="a-namesetwindowrgna--cwndsetwindowrgn"></a><a name="setwindowrgn"></a>CWnd::SetWindowRgn  
 Appelez cette fonction membre pour définir la région d’une fenêtre.  
  
```  
int SetWindowRgn(
    HRGN hRgn,  
    BOOL bRedraw);
```  
  
### <a name="parameters"></a>Paramètres  
 `hRgn`  
 Handle d’une région.  
  
 `bRedraw`  
 Si **TRUE**, le système d’exploitation redessine la fenêtre après la définition de la région ; sinon, il n’existe pas. En règle générale, définissez `bRedraw` à **TRUE** si la fenêtre est visible. Si la valeur **TRUE**, le système envoie la `WM_WINDOWPOSCHANGING` et `WM_WINDOWPOSCHANGED` messages dans la fenêtre.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la fonction réussit, la valeur de retour est différent de zéro. Si la fonction échoue, la valeur de retour est égale à zéro.  
  
### <a name="remarks"></a>Remarques  
 Les coordonnées de la zone de la fenêtre d’une fenêtre sont par rapport à l’angle supérieur gauche de la fenêtre, pas la zone cliente de la fenêtre.  
  
 Après un appel réussi à `SetWindowRgn`, le système d’exploitation possède la région spécifiée par le handle de région `hRgn`. Le système d’exploitation ne fait pas une copie de la région, donc pas apporter d’autres appels de fonction avec ce handle de région et ne fermez pas ce handle de région.  
  
##  <a name="a-namesetwindowtexta--cwndsetwindowtext"></a><a name="setwindowtext"></a>CWnd::SetWindowText  
 Définit le titre de la fenêtre pour le texte spécifié.  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszString`  
 Pointe vers une [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet ou la chaîne à utiliser en tant que le nouveau texte de titre ou le contrôle.  
  
### <a name="remarks"></a>Remarques  
 Si la fenêtre est un contrôle, le texte dans le contrôle est défini.  
  
 Cette fonction provoque une [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) message à envoyer à cette fenêtre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#121;](../../mfc/reference/codesnippet/cpp/cwnd-class_62.cpp)]  
  
##  <a name="a-nameshowcareta--cwndshowcaret"></a><a name="showcaret"></a>CWnd::ShowCaret  
 Affiche le signe insertion sur l’écran à la position actuelle du signe insertion.  
  
```  
void ShowCaret();
```  
  
### <a name="remarks"></a>Remarques  
 Une fois affiché, le caret se met à clignoter automatiquement.  
  
 Le `ShowCaret` fonction membre affiche le signe insertion uniquement si elle possède une forme actuelle et le n'a pas été masquée au moins deux fois consécutives. Si le point d’insertion n’est pas détenu par cette fenêtre, le point d’insertion n’est pas affiché.  
  
 Masquer le point d’insertion est cumulative. Si le [HideCaret](#hidecaret) fonction membre a été appelée cinq fois consécutives, `ShowCaret` doit être appelé cinq fois pour afficher le signe insertion.  
  
 Le point d’insertion est une ressource partagée. La fenêtre doit afficher le signe insertion uniquement lorsqu’il a le focus d’entrée ou n’est active.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWnd::CreateCaret](#createcaret).  
  
##  <a name="a-nameshowownedpopupsa--cwndshowownedpopups"></a><a name="showownedpopups"></a>CWnd::ShowOwnedPopups  
 Affiche ou masque toutes les fenêtres pop-up appartenant à cette fenêtre.  
  
```  
void ShowOwnedPopups(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bShow`  
 Spécifie si les fenêtres publicitaires doivent être affichées ou masquées. Si ce paramètre est **TRUE**, toutes les fenêtres pop-up masquées sont affichées. Si ce paramètre est **FALSE**, toutes les fenêtres publicitaires visibles sont masqués.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWnd::SetWindowPos](#setwindowpos).  
  
##  <a name="a-nameshowscrollbara--cwndshowscrollbar"></a><a name="showscrollbar"></a>CWnd::ShowScrollBar  
 Affiche ou masque une barre de défilement.  
  
```  
void ShowScrollBar(
    UINT nBar,  
    BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nBar`  
 Spécifie si la barre de défilement est un contrôle ou une partie d’une zone non cliente d’une fenêtre. S’il fait partie de la zone non cliente, `nBar` indique également si la barre de défilement est positionnée horizontalement, verticalement, ou les deux. Il doit être une des opérations suivantes :  
  
- **SB_BOTH** spécifie les barres de défilement horizontale et verticale de la fenêtre.  
  
- **SB_HORZ** Spécifie que la fenêtre est une barre de défilement horizontale.  
  
- **SB_VERT** Spécifie que la fenêtre est une barre de défilement verticale.  
  
 `bShow`  
 Spécifie si Windows affiche ou masque la barre de défilement. Si ce paramètre est **TRUE**, la barre de défilement s’affiche ; sinon, la barre de défilement est masquée.  
  
### <a name="remarks"></a>Remarques  
 Une application ne doit pas appeler `ShowScrollBar` pour masquer une barre de défilement lors du traitement d’un message de notification de barre de défilement.  
  
##  <a name="a-nameshowwindowa--cwndshowwindow"></a><a name="showwindow"></a>CWnd::ShowWindow  
 Définit l’état de visibilité de la fenêtre.  
  
```  
BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>Paramètres  
 `nCmdShow`  
 Spécifie comment la `CWnd` doit être affiché. Il doit être une des valeurs suivantes :  
  
- **SW_HIDE** masque cette fenêtre et Active une autre fenêtre.  
  
- **SW_MINIMIZE** réduit la fenêtre et Active la fenêtre de niveau supérieur dans la liste du système.  
  
- **SW_RESTORE** active et affiche la fenêtre. Si la fenêtre est réduite ou agrandie, Windows le restaure à sa taille et sa position d’origine.  
  
- **SW_SHOW** Active la fenêtre et l’affiche dans sa taille actuelle et son emplacement.  
  
- **SW_SHOWMAXIMIZED** Active la fenêtre et l’affiche comme une fenêtre agrandie.  
  
- **SW_SHOWMINIMIZED** active de la fenêtre et l’affiche sous forme d’icône.  
  
- **SW_SHOWMINNOACTIVE** affiche la fenêtre sous forme d’icône. La fenêtre actuellement active reste active.  
  
- **SW_SHOWNA** affiche la fenêtre dans son état actuel. La fenêtre actuellement active reste active.  
  
- **SW_SHOWNOACTIVATE** affiche la fenêtre dans sa taille et la position la plus récente. La fenêtre actuellement active reste active.  
  
- **SW_SHOWNORMAL** active et affiche la fenêtre. Si la fenêtre est réduite ou agrandie, Windows le restaure à sa taille et sa position d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fenêtre a été précédemment visible ; 0 si le `CWnd` précédemment masqué.  
  
### <a name="remarks"></a>Remarques  
 `ShowWindow`doit être appelée qu’une seule fois par application de la fenêtre principale avec [CWinApp::m_nCmdShow](../../mfc/reference/cwinapp-class.md#m_ncmdshow). Les appels suivants à `ShowWindow` doit utiliser une des valeurs répertoriées ci-dessus, au lieu de celui spécifié par `CWinApp::m_nCmdShow`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWnd::CalcWindowRect](#calcwindowrect).  
  
##  <a name="a-namesubclassdlgitema--cwndsubclassdlgitem"></a><a name="subclassdlgitem"></a>CWnd::SubclassDlgItem  
 Appelez cette fonction membre pour « sous-classe dynamiquement » un contrôle créé à partir d’un modèle de boîte de dialogue et l’associer à cette `CWnd` objet.  
  
```  
BOOL SubclassDlgItem(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 ID. du contrôle  
  
 `pParent`  
 Le parent du contrôle (généralement une boîte de dialogue).  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Lorsqu’un contrôle est sous-classé dynamiquement, achemine les messages windows via le `CWnd`du mappage de message et appeler des gestionnaires de messages dans la `CWnd`de première classe. Les messages qui sont passés à la classe de base seront passées au Gestionnaire de messages par défaut dans le contrôle.  
  
 Cette fonction membre attache le contrôle Windows à un `CWnd` de l’objet et remplace le contrôle **WndProc** et **AfxWndProc** fonctions. La fonction stocke l’ancienne **WndProc** dans l’emplacement retourné par la `GetSuperWndProcAddr` fonction membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#122;](../../mfc/reference/codesnippet/cpp/cwnd-class_63.cpp)]  
  
##  <a name="a-namesubclasswindowa--cwndsubclasswindow"></a><a name="subclasswindow"></a>CWnd::SubclassWindow  
 Appelez cette fonction membre pour « sous-classe dynamiquement » une fenêtre et l’associer à cette `CWnd` objet.  
  
```  
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 Handle vers la fenêtre.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Lorsqu’une fenêtre est sous-classée dynamiquement, achemine les messages windows via le `CWnd`du mappage de message et appeler des gestionnaires de messages dans la `CWnd`de première classe. Les messages qui sont passés à la classe de base seront passées au Gestionnaire de messages par défaut dans la fenêtre.  
  
 Cette fonction membre attache le contrôle Windows à un `CWnd` de l’objet et remplace la fenêtre **WndProc** et **AfxWndProc** fonctions. La fonction stocke un pointeur vers l’ancien **WndProc** dans les `CWnd` objet.  
  
> [!NOTE]
>  La fenêtre de ne doit pas déjà être attachée à un objet MFC lorsque cette fonction est appelée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#123;](../../mfc/reference/codesnippet/cpp/cwnd-class_64.cpp)]  
  
##  <a name="a-nameunlockwindowupdatea--cwndunlockwindowupdate"></a><a name="unlockwindowupdate"></a>CWnd::UnlockWindowUpdate  
 Appelez cette fonction membre pour déverrouiller une fenêtre qui a été verrouillée avec `CWnd::LockWindowUpdate`.  
  
```  
void UnlockWindowUpdate();
```  
  
### <a name="remarks"></a>Remarques  
 Une seule fenêtre à la fois peut être verrouillée à l’aide de `LockWindowUpdate`. Consultez la page [CWnd::LockWindowUpdate](#lockwindowupdate) ou la fonction Win32 [LockWindowUpdate](http://msdn.microsoft.com/library/windows/desktop/dd145034) pour plus d’informations sur le verrouillage de windows.  
  
##  <a name="a-nameunsubclasswindowa--cwndunsubclasswindow"></a><a name="unsubclasswindow"></a>CWnd::UnsubclassWindow  
 Appelez cette fonction membre pour définir **WndProc** revenir à sa valeur d’origine et détacher la fenêtre identifiée par `HWND` à partir de la **CWnd** objet.  
  
```  
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Handle vers la fenêtre unsubclassed.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWnd::SubclassWindow](#subclasswindow).  
  
##  <a name="a-nameupdatedataa--cwndupdatedata"></a><a name="updatedata"></a>CWnd::UpdateData  
 Appelez cette fonction membre pour initialiser les données dans une boîte de dialogue, extraire et valider les données de la boîte de dialogue.  
  
```  
BOOL UpdateData(BOOL bSaveAndValidate = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bSaveAndValidate`  
 Indicateur qui indique si la boîte de dialogue est initialisée ( **FALSE**) ou de la récupération des données ( **TRUE**).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; sinon 0. Si *bSaveAndValidat*e **TRUE**, puis une valeur de retour différente de zéro signifie que les données sont validées avec succès.  
  
### <a name="remarks"></a>Remarques  
 Le framework appelle automatiquement `UpdateData` avec `bSaveAndValidate` la valeur **FALSE** lorsqu’une boîte de dialogue modale est créée dans l’implémentation par défaut de [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog). L’appel se produit avant que la boîte de dialogue est visible. L’implémentation par défaut de [CDialog::OnOK](../../mfc/reference/cdialog-class.md#onok) appelle cette fonction membre avec `bSaveAndValidate` la valeur **TRUE** pour récupérer les données et si l’opération réussit, va se fermer la boîte de dialogue. (Si l’utilisateur clique sur le bouton Annuler dans la boîte de dialogue, la boîte de dialogue est fermée sans les données récupérées).  
  
##  <a name="a-nameupdatedialogcontrolsa--cwndupdatedialogcontrols"></a><a name="updatedialogcontrols"></a>CWnd::UpdateDialogControls  
 Appelez cette fonction membre pour mettre à jour l’état des boutons de la boîte de dialogue et d’autres contrôles dans une boîte de dialogue ou la fenêtre qui utilise le [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4) mécanisme de rappel.  
  
```  
void UpdateDialogControls(
    CCmdTarget* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Paramètres  
 `pTarget`  
 Pointe vers la fenêtre frame principale de l’application et est utilisé pour router des messages de mise à jour *.*  
  
 `bDisableIfNoHndler`  
 Indicateur qui indique si un contrôle qui ne possède aucun gestionnaire de mise à jour doit être affiché automatiquement désactivé.  
  
### <a name="remarks"></a>Remarques  
 Si un contrôle enfant n’a pas de gestionnaire et `bDisableIfNoHndler` est **TRUE**, puis le contrôle enfant sera désactivé.  
  
 L’infrastructure appelle cette fonction membre pour les contrôles dans les barres de boîte de dialogue ou les barres d’outils dans le cadre de l’application des processus inactifs.  
  
##  <a name="a-nameupdatelayeredwindowa--cwndupdatelayeredwindow"></a><a name="updatelayeredwindow"></a>CWnd::UpdateLayeredWindow  
 Met à jour la position, la taille, la forme, le contenu et la transparence d'une fenêtre superposée.  
  
```  
BOOL UpdateLayeredWindow(
    CDC* pDCDst,  
    POINT* pptDst,  
    SIZE* psize,  
    CDC* pDCSrc,  
    POINT* pptSrc,  
    COLORREF crKey,  
    BLENDFUNCTION* pblend,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDCDst`  
 Pointeur vers un contexte de périphérique de l’écran. Il est utilisé pour la correspondance de couleurs de palette lorsque le contenu de la fenêtre est mis à jour. Si `pDCDst` est **NULL**, la palette par défaut sera utilisée.  
  
 If `pDCSrc` is **NULL**, `pDCDst` must be **NULL**.  
  
 `pptDst`  
 Un pointeur vers un **POINT** structure qui spécifie la nouvelle position d’écran de la fenêtre superposée. Si la position actuelle ne change pas, `pptDst` peut être **NULL**.  
  
 *psize*  
 Pointeur vers un **taille** structure qui spécifie la nouvelle taille de la fenêtre superposée. Si la taille de la fenêtre ne change pas, *psize* peut être **NULL**.  
  
 If `pDCSrc` is **NULL**, *psize* must be **NULL**.  
  
 `pDCSrc`  
 Pointeur vers un contrôleur de domaine pour la surface qui définit la fenêtre superposée. Si vous ne modifient pas la forme et le contexte visuel de la fenêtre, `pDCSrc` peut être **NULL**.  
  
 `pptSrc`  
 Pointeur vers un **POINT** structure qui spécifie l’emplacement de la couche dans le contexte de périphérique.  
  
 If `pDCSrc` is **NULL**, `pptSrc` should be **NULL**.  
  
 `crKey`  
 Pointeur vers un **COLORREF** valeur qui spécifie la clé de couleur de transparence à utiliser lors de la composition de la fenêtre superposée. Tous les pixels de peinture par la fenêtre dans cette couleur est transparents. Pour générer un **COLORREF**, utilisez la macro RVB.  
  
 *pblend*  
 Pointeur vers un [BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393) structure qui spécifie la valeur de transparence à utiliser lors de la composition de la fenêtre superposée.  
  
 `dwFlags`  
 Spécifie l’action à entreprendre. Ce paramètre peut être une ou plusieurs des valeurs suivantes. Pour obtenir la liste des valeurs possibles, consultez la page [UpdateLayeredWindow](http://msdn.microsoft.com/library/windows/desktop/ms633556).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre émule les fonctionnalités de la fonction [UpdateLayeredWindow](http://msdn.microsoft.com/library/windows/desktop/ms633556), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameupdatewindowa--cwndupdatewindow"></a><a name="updatewindow"></a>CWnd::UpdateWindow  
 Met à jour la zone cliente en envoyant un [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message si la région de mise à jour n’est pas vide.  
  
```  
void UpdateWindow();
```  
  
### <a name="remarks"></a>Notes  
 Le `UpdateWindow` fonction membre envoie une `WM_PAINT` message directement, en contournant la file d’attente de l’application. Si la zone de mise à jour est vide, `WM_PAINT` n’est pas envoyé.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#124;](../../mfc/reference/codesnippet/cpp/cwnd-class_65.cpp)]  
  
##  <a name="a-namevalidaterecta--cwndvalidaterect"></a><a name="validaterect"></a>CWnd::ValidateRect  
 Valide la zone cliente dans le rectangle spécifié en supprimant le rectangle de la zone de mise à jour de la fenêtre.  
  
```  
void ValidateRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 Pointe vers une [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou [Rect, structure](../../mfc/reference/rect-structure1.md) qui contient les coordonnées clientes du rectangle à supprimer de la région de mise à jour. Si `lpRect` est **NULL**, la totalité de la fenêtre est validé.  
  
### <a name="remarks"></a>Remarques  
 Le [BeginPaint](#beginpaint) fonction membre valide automatiquement la zone client entière. Ni le `ValidateRect` ni le [ValidateRgn](#validatergn) fonction membre doit être appelée si une partie de la zone de mise à jour doit être validée avant [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) est ensuite généré.  
  
 Windows continue à générer `WM_PAINT` messages jusqu'à ce que la zone de mise à jour en cours est validée.  
  
##  <a name="a-namevalidatergna--cwndvalidatergn"></a><a name="validatergn"></a>CWnd::ValidateRgn  
 Valide la zone cliente d’une région donnée en supprimant la région à partir de la zone en cours de mise à jour de la fenêtre.  
  
```  
void ValidateRgn(CRgn* pRgn);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRgn`  
 Un pointeur vers un [CRgn](../../mfc/reference/crgn-class.md) objet qui identifie une région qui définit la zone à supprimer de la région de mise à jour. Si ce paramètre est **NULL**, la zone client entière est supprimée.  
  
### <a name="remarks"></a>Remarques  
 La région donnée doit avoir été créée par une fonction de la région. Les coordonnées de la région sont supposées pour être coordonnées clientes.  
  
 Le [BeginPaint](#beginpaint) fonction membre valide automatiquement la zone client entière. Ni le [fonction ValidateRect](#validaterect) et `ValidateRgn` fonction membre doit être appelée si une partie de la zone de mise à jour doit être validée avant le prochain [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) message est généré.  
  
##  <a name="a-namewindowfrompointa--cwndwindowfrompoint"></a><a name="windowfrompoint"></a>CWnd::WindowFromPoint  
 Récupère la fenêtre qui contient le point spécifié ; `point` doit spécifier les coordonnées d’écran d’un point sur l’écran.  
  
```  
static CWnd* PASCAL WindowFromPoint(POINT point);
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Spécifie un [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet ou [POINT](../../mfc/reference/point-structure1.md) structure de données qui définit le point de vérification.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’objet de fenêtre dans laquelle se trouve le point. Il est **NULL** si aucune fenêtre n’existe à un point précis. Le pointeur retourné peut être temporaire et ne doit pas être stocké pour une utilisation ultérieure.  
  
### <a name="remarks"></a>Remarques  
 `WindowFromPoint`ne récupère pas une fenêtre masquée ou désactivée, même si le point se trouve dans la fenêtre. Une application doit utiliser le [ChildWindowFromPoint](#childwindowfrompoint) fonction membre pour effectuer une recherche non restrictifs.  
  
##  <a name="a-namewindowproca--cwndwindowproc"></a><a name="windowproc"></a>CWnd::WindowProc  
 Fournit une procédure de Windows ( `WindowProc`) pour un `CWnd` objet.  
  
```  
virtual LRESULT WindowProc(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `message`  
 Spécifie le message Windows à traiter.  
  
 `wParam`  
 Fournit des informations supplémentaires utilisées dans le traitement du message. La valeur du paramètre dépend du message.  
  
 `lParam`  
 Fournit des informations supplémentaires utilisées dans le traitement du message. La valeur du paramètre dépend du message.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour dépend du message.  
  
### <a name="remarks"></a>Remarques  
 Il distribue des messages via une table des messages de la fenêtre.  
  
##  <a name="a-namewinhelpa--cwndwinhelp"></a><a name="winhelp"></a>CWnd::WinHelp  
 Appelé pour lancer l'application WinHelp.  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwData`  
 Spécifie les données supplémentaires. La valeur utilisée dépend de la valeur de le `nCmd` paramètre.  
  
 `nCmd`  
 Spécifie le type d’aide demandée. Pour obtenir la liste des valeurs possibles et comment elles affectent le `dwData` paramètre, consultez le [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) Windows fonctionnent dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [CWinApp::WinHelp](../../mfc/reference/cwinapp-class.md#winhelp) pour plus d’informations.  
  
##  <a name="a-nameregistertouchwindowa--cwndregistertouchwindow"></a><a name="registertouchwindow"></a>CWnd::RegisterTouchWindow  
 Les registres ou annule l’enregistrement de la prise en charge tactile de Windows.  
  
```  
BOOL RegisterTouchWindow(
    BOOL bRegister = TRUE,  
    ULONG ulFlags = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `bRegister`  
 `TRUE`Indique le Registre Windows touch prise en charge ; `FALSE` dans le cas contraire.  
  
 `ulFlags`  
 Un ensemble de bits indicateurs qui spécifient les modifications facultatif. Ce champ peut contenir 0 ou l’une des valeurs suivantes : TWF_FINETOUCH, TWF_WANTPALM.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` en cas de réussite ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameresizedynamiclayouta--cwndresizedynamiclayout"></a><a name="resizedynamiclayout"></a>CWnd::ResizeDynamicLayout  
 Appelé par l'infrastructure quand la taille de fenêtre change pour ajuster la disposition des fenêtres enfants, si la disposition dynamique est activée pour la fenêtre.  
  
```  
virtual void ResizeDynamicLayout();
```  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CFrameWnd (classe)](../../mfc/reference/cframewnd-class.md)   
 [CView (classe)](../../mfc/reference/cview-class.md)

