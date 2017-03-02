---
title: Classe de CDockingManager | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockingManager
dev_langs:
- C++
helpviewer_keywords:
- CDockingManager class
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 37
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
ms.openlocfilehash: 106046dc9dc671b5baea7c6df78b91ba37098978
ms.lasthandoff: 02/24/2017

---
# <a name="cdockingmanager-class"></a>CDockingManager (classe)
Implémente la fonctionnalité principale qui contrôle la disposition d'ancrage dans une fenêtre frame principale.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|Crée un volet d’ancrage et l’ajoute à la liste des barres de contrôles.|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Ajoute un handle à une barre de volet à la liste des masqué MDI avec onglets des volets de barre.|  
|[CDockingManager::AddMiniFrame](#addminiframe)|Ajoute une image à la liste d’images mini.|  
|[CDockingManager::AddPane](#addpane)|Enregistre un volet avec le Gestionnaire d’ancrage.|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|Recalcule et ajuste la disposition de tous les volets dans une fenêtre frame.|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|Provoque la `WM_NCCALCSIZE` message à envoyer à tous les volets et `CPaneFrameWnd` windows.|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|Ajuste l’alignement d’un rectangle.|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Redimensionne un volet d’ancrage en mode de masquage automatique pour qu’elle prend toute la largeur ou hauteur de la zone cliente du bloc entouré par ancrer des sites.|  
|[CDockingManager::AutoHidePane](#autohidepane)|Crée une barre d’outils de masquage automatique.|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Affiche les barres ancrées qui ont l’alignement spécifié vers le haut.|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Ajoute les noms des barres d’outils et des volets d’ancrage à un menu.|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Calcule le rectangle attendu d’une fenêtre ancrée.|  
|[CDockingManager::Create](#create)|Crée un gestionnaire d’ancrage.|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Détermine le volet qui contient un point donné et son état d’ancrage.|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Active ou désactive le chargement de la mise en page d’accueil à partir du Registre.|  
|[CDockingManager::DockPane](#dockpane)|Ancre un volet à un autre volet, ou vers une fenêtre frame.|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Ancre un volet à gauche d'un autre volet.|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Permet d’ancrage du volet au frame principal crée un volet d’ancrage et l’ajoute à la liste des barres de contrôles.|  
|[CDockingManager::EnableDocking](#enabledocking)|Crée un volet d’ancrage et permet d’ancrage du volet vers le frame principal.|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Affiche un bouton supplémentaire qui ouvre un menu contextuel dans les légendes de tous les volets d’ancrage.|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Indique à la bibliothèque pour afficher un menu contextuel spécial qui contient une liste de barres d’outils de l’application et les volets d’ancrage lorsque l’utilisateur clique sur le bouton droit de la souris et la bibliothèque traite le message WM_CONTEXTMENU.|  
|[CDockingManager::FindDockSite](#finddocksite)|Récupère la barre volet qui se trouve à la position spécifiée et qui a l’alignement spécifié.|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Retourne la barre de volet dont l’id du volet barre cible.|  
|[CDockingManager::FindPaneByID](#findpanebyid)|Recherche d’un volet à l’ID du contrôle spécifié.|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Valide toutes les positions de barre d’outils actuelle aux rectangles virtuels.|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|Retourne le frame qui contient le point donné.|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|Obtient le rectangle qui contient les limites de la zone cliente.|  
|[CDockingManager::GetDockingMode](#getdockingmode)|Renvoie le mode d’ancrage actuels.|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Obtient un pointeur vers le frame de fenêtre parente.|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Retourne l’alignement activé des volets.|  
|[CDockingManager::GetMiniFrames](#getminiframes)|Obtient une liste de miniframes.|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Obtient un rectangle qui contient les bords extérieurs de l’image.|  
|[CDockingManager::GetPaneList](#getpanelist)|Retourne une liste de volets qui appartiennent au gestionnaire d’ancrage. Cela inclut tous les volets flottants.|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Récupère un pointeur vers le Gestionnaire d’ancrage intelligent.|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|Récupère un pointeur vers le Gestionnaire d’ancrage intelligent.|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Retourne les paramètres d’ancrage intelligents pour le Gestionnaire d’ancrage.|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Une méthode statique qui retourne un thème utilisé pour afficher les marqueurs d’ancrage intelligents.|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Masque un volet en mode de masquage automatique.|  
|[CDockingManager::InsertDockSite](#insertdocksite)|Crée un volet d’ancrage et l’insère dans la liste des barres de contrôles.|  
|[CDockingManager::InsertPane](#insertpane)|Insère un panneau de configuration dans la liste des barres de contrôles.|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Spécifie si un menu contextuel s’affiche dans les légendes de tous les volets.|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|Détermine si la disposition de tous les volets est ajustée.|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Spécifie si le Gestionnaire d’ancrage est en mode de conteneur OLE.|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Détermine si un point spécifié est proche du site d’ancrage.|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Détermine si le mode Aperçu avant impression est défini.|  
|[CDockingManager::LoadState](#loadstate)|Charge état d’ancrage du responsable à partir du Registre.|  
|[CDockingManager::LockUpdate](#lockupdate)|Verrouille la fenêtre donnée.|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|Appelé par l’infrastructure lorsque la fenêtre frame devient active ou est désactivée.|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Appelée par l’infrastructure quand un menu contextuel actif traite un message WM_DESTROY.|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Appelé par l’infrastructure pour déplacer une fenêtre mini-frame.|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Appelé par l’infrastructure lorsqu’il génère un menu qui contient une liste de volets.|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|Retourne le volet qui contient le point donné.|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Appelée par l’infrastructure pour sélectionner ou effacer une case à cocher pour la commande spécifiée et recalculer la disposition d’un volet indiqué.|  
|[CDockingManager::RecalcLayout](#recalclayout)|Recalcule la disposition des contrôles présents dans la liste des contrôles interne.|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Libère les conteneurs volet vide.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Supprime masqué barre volet spécifié.|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Supprime un intervalle spécifié dans la liste d’images mini.|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Annule l’inscription d’un volet et le supprime de la liste dans le Gestionnaire d’ancrage.|  
|[CDockingManager::ReplacePane](#replacepane)|Remplace un volet par un autre.|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|Les images dans la liste d’images mini est analysée.|  
|[CDockingManager::SaveState](#savestate)|Enregistre l’état de la station d’accueil du responsable dans le Registre.|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Envoie le message spécifié à tous les blocs mini.|  
|[CDockingManager::Serialize](#serialize)|Écrit le Gestionnaire d’ancrage dans une archive. (Substitue [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|Définit la taille, la largeur et la hauteur des barres de contrôles et le volet spécifié.|  
|[CDockingManager::SetDockingMode](#setdockingmode)|Définit le mode d’ancrage.|  
|[CDockingManager::SetDockState](#setdockstate)|Définit l’état d’ancrage de barres de contrôles, les images mini et les barres de masquage automatique.|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Définit le mode Aperçu avant impression, les barres sont affichées dans l’aperçu avant impression.|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Définit les paramètres qui définissent le comportement d’ancrage actif.|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|Affiche ou masque les fenêtres des cadres mini.|  
|[CDockingManager::ShowPanes](#showpanes)|Affiche ou masque les volets des barres de contrôle et de masquage automatique.|  
|[CDockingManager::StartSDocking](#startsdocking)|Démarre l’ancrage actif de la fenêtre spécifiée en fonction de l’alignement du Gestionnaire d’ancrage intelligent.|  
|[CDockingManager::StopSDocking](#stopsdocking)|Arrête actives d’ancrage.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Spécifie si le Gestionnaire d’ancrage masque les volets en mode de conteneur OLE.|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Spécifie le mode d’ancrage global.|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Spécifie le respect de la station d’accueil.|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Spécifie la durée, en millisecondes, avant d’un volet d’ancrage est ancré dans ce mode d’ancrage.|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Spécifie la durée, en millisecondes, avant une barre d’outils est ancrée à la fenêtre frame principale.|  
  
## <a name="remarks"></a>Remarques  
 La fenêtre frame principale crée et initialise automatiquement de cette classe.  
  
 L’objet de gestionnaire d’ancrage contient une liste de tous les volets qui se trouvent dans la mise en page d’accueil et également une liste de tous les [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) windows qui appartiennent à la fenêtre frame principale.  
  
 Le `CDockingManager` classe implémente certains services que vous pouvez utiliser pour rechercher un volet ou un `CPaneFrameWnd` fenêtre. Vous généralement n’appelez pas ces services directement, car ils sont encapsulés dans l’objet de fenêtre frame principale. Pour plus d’informations, consultez [CPaneFrameWnd classe](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="customization-tips"></a>Conseils de personnalisation  
 Les conseils suivants s’appliquent aux `CDockingManager` objets :  
  
- [Classe de CDockingManager](../../mfc/reference/cdockingmanager-class.md) prend en charge ces modes d’accueil :  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     Ces modes d’ancrage sont définis par [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) et sont définies en appelant [CDockingManager::SetDockingMode](#setdockingmode).  
  
-   Si vous souhaitez créer un volet non flottant, non redimensionnable, appelez le [CDockingManager::AddPane](#addpane) (méthode). Cette méthode inscrit le volet avec le Gestionnaire d’ancrage, ce qui est responsable de la disposition du volet.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans le `CDockingManager` classe pour configurer un `CDockingManager` objet. L’exemple montre comment afficher un bouton supplémentaire qui ouvre un menu contextuel dans les légendes de tous les volets d’ancrage et définir le mode d’ancrage de l’objet. Cet extrait de code fait partie de la [exemple de Visual Studio démonstration](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#24;](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxDockingManager.h  
  
##  <a name="a-nameadddocksitea--cdockingmanageradddocksite"></a><a name="adddocksite"></a>CDockingManager::AddDockSite  
 Crée un volet d’ancrage et l’ajoute à la liste des barres de contrôles.  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `info`  
 Une référence à une structure d’informations qui contient alignement du volet d’ancrage.  
  
 [out] `ppDockBar`  
 Pointeur vers un pointeur vers le nouveau volet d’ancrage.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet d’ancrage a été créé avec succès ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameaddhiddenmditabbedbara--cdockingmanageraddhiddenmditabbedbar"></a><a name="addhiddenmditabbedbar"></a>CDockingManager::AddHiddenMDITabbedBar  
 Ajoute un handle à une barre de volet à la liste des masqué MDI avec onglets des volets de barre.  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 Un pointeur vers une barre de volet  
  
##  <a name="a-nameaddpanea--cdockingmanageraddpane"></a><a name="addpane"></a>CDockingManager::AddPane  
 Enregistre un volet avec le Gestionnaire d’ancrage.  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `pWnd`  
 Spécifie le volet pour ajouter au gestionnaire d’ancrage.  
  
 [in] `bTail`  
 `TRUE`Pour ajouter le volet à la fin de la liste des volets pour le Gestionnaire d’ancrage ; dans le cas contraire, `FALSE`.  
  
 [in] `bAutoHide`  
 Uniquement réservé à un usage interne. Utilisez toujours la valeur par défaut `FALSE`.  
  
 [in] `bInsertForOuterEdge`  
 Uniquement réservé à un usage interne. Utilisez toujours la valeur par défaut `FALSE`.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet a été inscrit avec le Gestionnaire d’ancrage ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour inscrire des volets non flottant, non redimensionnable avec le Gestionnaire d’ancrage. Si vous n’enregistrez pas les volets, ils n’apparaissent pas correctement lorsque le Gestionnaire d’ancrage est disposé.  
  
##  <a name="a-nameadjustdockinglayouta--cdockingmanageradjustdockinglayout"></a><a name="adjustdockinglayout"></a>CDockingManager::AdjustDockingLayout  
 Recalcule et ajuste la disposition de tous les volets dans une fenêtre frame.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hdwp`  
 Spécifie la structure de fenêtre différée. Pour plus d’informations, consultez [des Types de données Windows](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameaddminiframea--cdockingmanageraddminiframe"></a><a name="addminiframe"></a>CDockingManager::AddMiniFrame  
 Ajoute une image à la liste d’images mini.  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWnd`  
 Pointeur vers une image.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le frame n’est pas dans la liste d’images mini et a été ajouté avec succès ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameadjustpaneframesa--cdockingmanageradjustpaneframes"></a><a name="adjustpaneframes"></a>CDockingManager::AdjustPaneFrames  
 Provoque la `WM_NCCALCSIZE` message à envoyer à tous les volets et `CPaneFrameWnd` windows.  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameadjustrecttoclientareaa--cdockingmanageradjustrecttoclientarea"></a><a name="adjustrecttoclientarea"></a>CDockingManager::AdjustRectToClientArea  
 Ajuste l’alignement d’un rectangle.  
  
```  
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `rectResult`  
 Une référence à un `CRect` objet  
  
 [in] `dwAlignment`  
 L’alignement de la `CRect` objet  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’alignement de la `CRect` objet a été ajusté ; `FALSE` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Le `dwAlignment` paramètre peut prendre l’une des valeurs suivantes :  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="a-namealignautohidepanea--cdockingmanageralignautohidepane"></a><a name="alignautohidepane"></a>CDockingManager::AlignAutoHidePane  
 Redimensionne un volet d’ancrage en mode de masquage automatique pour qu’elle prend toute la largeur ou hauteur de la zone cliente du bloc entouré par ancrer des sites.  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDefaultSlider`  
 Le volet d’ancrage du curseur.  
  
 [in] `bIsVisible`  
 `TRUE`Si le volet d’ancrage est visible ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameautohidepanea--cdockingmanagerautohidepane"></a><a name="autohidepane"></a>CDockingManager::AutoHidePane  
 Crée une barre d’outils de masquage automatique.  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 Un pointeur vers la barre de volet.  
  
 [in] `pCurrAutoHideToolBar`  
 Pointeur vers une barre d’outils de masquage automatique.  
  
### <a name="return-value"></a>Valeur de retour  
 `NULL`Si la barre d’outils masquer n’a pas été créé ; Sinon, un pointeur vers la nouvelle barre d’outils.  
  
##  <a name="a-namebringbarstotopa--cdockingmanagerbringbarstotop"></a><a name="bringbarstotop"></a>CDockingManager::BringBarsToTop  
 Affiche les barres ancrées qui ont l’alignement spécifié vers le haut.  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwAlignment`  
 L’alignement des barres d’ancrage qui sont mis en haut des autres fenêtres.  
  
 [in] `bExcludeDockedBars`  
 `TRUE`Pour exclure les barres ancrées d’être visible ; dans le cas contraire `FALSE`.  
  
##  <a name="a-namebuildpanesmenua--cdockingmanagerbuildpanesmenu"></a><a name="buildpanesmenu"></a>CDockingManager::BuildPanesMenu  
 Ajoute les noms des barres d’outils et des volets d’ancrage à un menu.  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `menu`  
 Un menu pour ajouter les noms de volets d’ancrage et de barres d’outils.  
  
 [in] `bToolbarsOnly`  
 `TRUE`Pour ajouter uniquement les noms de barre d’outils dans le menu ; `FALSE` dans le cas contraire.  
  
##  <a name="a-namecalcexpecteddockedrecta--cdockingmanagercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CDockingManager::CalcExpectedDockedRect  
 Calcule le rectangle attendu d’une fenêtre ancrée.  
  
```  
void CalcExpectedDockedRect(
    CWnd* pWnd,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWnd`  
 Pointeur vers la fenêtre pour l’ancrer.  
  
 [in] `ptMouse`  
 L’emplacement de la souris.  
  
 [out] `rectResult`  
 Rectangle calculé.  
  
 [in] `bDrawTab`  
 `TRUE`Pour dessiner un onglet ; dans le cas contraire `FALSE`.  
  
 [out] `ppTargetBar`  
 Pointeur vers un pointeur vers le volet cible.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode calcule le rectangle une fenêtre occuperait si un utilisateur a fait glisser la fenêtre vers le point spécifié par `ptMouse` et il il ancré.  
  
##  <a name="a-namecreatea--cdockingmanagercreate"></a><a name="create"></a>CDockingManager::Create  
 Crée un gestionnaire d’ancrage.  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pParentWnd`  
 Pointeur vers le frame parent du Gestionnaire d’ancrage. Cette valeur ne doit pas être `NULL`.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`toujours.  
  
##  <a name="a-namedeterminepaneandstatusa--cdockingmanagerdeterminepaneandstatus"></a><a name="determinepaneandstatus"></a>CDockingManager::DeterminePaneAndStatus  
 Détermine le volet qui contient un point donné et son état d’ancrage.  
  
```  
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,  
    int nSensitivity,  
    DWORD dwEnabledAlignment,  
    CBasePane** ppTargetBar,  
    const CBasePane* pBarToIgnore,  
    const CBasePane* pBarToDock);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pt`  
 L’emplacement du volet à vérifier.  
  
 [in] `nSensitivity`  
 Valeur à augmenter le rectangle de la fenêtre de chaque volet activé. Un volet satisfait les critères de recherche si le point donné est dans cette région accrue.  
  
 [in] `dwEnabledAlignment`  
 L’alignement du volet d’ancrage.  
  
 [out] `ppTargetBar`  
 Pointeur vers un pointeur vers le volet cible.  
  
 [in] `pBarToIgnore`  
 Le volet de la méthode ignore.  
  
 [in] `pBarToDock`  
 Le volet est ancré.  
  
### <a name="return-value"></a>Valeur de retour  
 L’état d’ancrage.  
  
### <a name="remarks"></a>Remarques  
 L’état peut être une des valeurs suivantes :  
  
|Valeur AFX_CS_STATUS|Signification|  
|---------------------------|-------------|  
|CS_NOTHING|Le pointeur n’est pas sur un site d’ancrage. Par conséquent, réduisez le volet flottant.|  
|CS_DOCK_IMMEDIATELY|Le pointeur est sur le site d’ancrage dans le mode immédiat (style DT_IMMEDIATE est activé), donc le volet doit être ancré immédiatement.|  
|CS_DELAY_DOCK|Le pointeur se trouve sur un site d’ancrage est un autre volet d’ancrage ou un bord de l’image principale.|  
|CS_DELAY_DOCK_TO_TAB|Le pointeur se trouve sur un site d’ancrage qui provoque le volet ancré dans une fenêtre à onglets. Cela se produit lorsque la souris est sur une légende d’un autre volet d’ancrage ou sur une zone de l’onglet d’un volet à onglets.|  
  
##  <a name="a-namedisablerestoredockstatea--cdockingmanagerdisablerestoredockstate"></a><a name="disablerestoredockstate"></a>CDockingManager::DisableRestoreDockState  
 Active ou désactive le chargement de la mise en page d’accueil à partir du Registre.  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bDisable`  
 `TRUE`Pour désactiver le chargement de la disposition d’ancrage dans le Registre. dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode lorsque vous devez conserver la disposition actuelle de barres d’outils et des volets d’ancrage lors du chargement de l’état de l’application.  
  
##  <a name="a-namedockpanea--cdockingmanagerdockpane"></a><a name="dockpane"></a>CDockingManager::DockPane  
 Ancre un volet à un autre volet, ou vers une fenêtre frame.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 Un pointeur vers une barre de volet pour ancrer dans.  
  
 [in] `nDockBarID`  
 L’id de la barre d’ancrage.  
  
 [in] `lpRect`  
 Le rectangle de destination.  
  
##  <a name="a-namedockpaneleftofa--cdockingmanagerdockpaneleftof"></a><a name="dockpaneleftof"></a>CDockingManager::DockPaneLeftOf  
 Ancre un volet à gauche d'un autre volet.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBarToDock`  
 Un pointeur vers le volet pour être ancré à gauche de `pTargetBar`.  
  
 [in] `pTargetBar`  
 Pointeur vers le volet cible.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet est ancré avec succès ; dans le cas contraire, `FALSE`.  
  
##  <a name="a-nameenableautohidepanesa--cdockingmanagerenableautohidepanes"></a><a name="enableautohidepanes"></a>CDockingManager::EnableAutoHidePanes  
 Permet d’ancrage du volet au frame principal crée un volet d’ancrage et l’ajoute à la liste des barres de contrôles.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwStyle`  
 L’alignement d’ancrage.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet d’ancrage a été créé avec succès ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameenabledockinga--cdockingmanagerenabledocking"></a><a name="enabledocking"></a>CDockingManager::EnableDocking  
 Crée un volet d’ancrage et permet d’ancrage du volet vers le frame principal.  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwStyle`  
 L’alignement d’ancrage.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet d’ancrage a été créé avec succès ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameenabledocksitemenua--cdockingmanagerenabledocksitemenu"></a><a name="enabledocksitemenu"></a>CDockingManager::EnableDockSiteMenu  
 Affiche un bouton supplémentaire qui ouvre un menu contextuel dans les légendes de tous les volets d’ancrage.  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 `TRUE`Pour activer le menu site d’ancrage ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Le menu site d’ancrage affiche les options suivantes pour modifier l’état d’ancrage du volet :  
  
- `Floating`-Flotte un volet  
  
- `Docking`-Ancre un volet à l’image principale à l’emplacement où le volet a été dernier ancré  
  
- `AutoHide`-Bascule le volet en mode de masquage automatique  
  
- `Hide`-Masque un volet  
  
 Par défaut, ce menu n’est pas affiché.  
  
##  <a name="a-nameenablepanecontextmenua--cdockingmanagerenablepanecontextmenu"></a><a name="enablepanecontextmenu"></a>CDockingManager::EnablePaneContextMenu  
 Indique à la bibliothèque pour afficher un menu contextuel spécial qui contient une liste de barres d’outils de l’application et les volets d’ancrage lorsque l’utilisateur clique sur le bouton droit de la souris et la bibliothèque traite le message WM_CONTEXTMENU.  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 Si `TRUE`, la bibliothèque Active la prise en charge pour le menu contextuel automatique ; si `FALSE` la bibliothèque désactive la prise en charge pour le menu contextuel automatique.  
  
 [in] `uiCustomizeCmd`  
 Id de commande pour le **personnaliser** dans le menu.  
  
 [in] `strCustomizeText`  
 Le texte de la **personnaliser** élément.  
  
 [in] `bToolbarsOnly`  
 Si `TRUE`, le menu affiche uniquement la liste des barres d’outils de l’application ; si `FALSE`, la bibliothèque ajoute des volets d’ancrage application à cette liste.  
  
##  <a name="a-namefinddocksitea--cdockingmanagerfinddocksite"></a><a name="finddocksite"></a>CDockingManager::FindDockSite  
 Récupère la barre volet qui se trouve à la position spécifiée et qui a l’alignement spécifié.  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwAlignment`  
 L’alignement de la barre de volet.  
  
 [in] `bOuter`  
 Si `TRUE`, récupérer la barre à la position principal dans la liste des barres de contrôle. Récupérer dans le cas contraire, la barre à la position de fin dans la liste des barres de contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 Le volet d’ancrage qui a l’alignement spécifié ; `NULL` dans le cas contraire.  
  
##  <a name="a-namefindpanebyida--cdockingmanagerfindpanebyid"></a><a name="findpanebyid"></a>CDockingManager::FindPaneByID  
 Recherche d’un volet à l’ID du contrôle spécifié.  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uBarID`  
 Spécifie l’ID de contrôle du volet de recherche.  
  
 [in] `bSearchMiniFrames`  
 `TRUE`Pour inclure tous les volets flottants dans la recherche. `FALSE`Pour inclure uniquement les volets ancrés.  
  
### <a name="return-value"></a>Valeur de retour  
 Le [CBasePane](../../mfc/reference/cbasepane-class.md) objet ayant l’ID du contrôle spécifié, ou `NULL` si le volet spécifié est introuvable.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namefinddocksitebypanea--cdockingmanagerfinddocksitebypane"></a><a name="finddocksitebypane"></a>CDockingManager::FindDockSiteByPane  
 Retourne la barre de volet dont l’id du volet barre cible.  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pTargetBar`  
 Pointeur vers le volet de barre cible.  
  
### <a name="return-value"></a>Valeur de retour  
 La barre de volet dont l’id du volet barre cible ; `NULL` si ce type ne barre volet existe.  
  
##  <a name="a-namefixupvirtualrectsa--cdockingmanagerfixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDockingManager::FixupVirtualRects  
 Valide toutes les positions de barre d’outils actuelle aux rectangles virtuels.  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Remarques  
 Lorsque l’utilisateur commence à faire glisser une barre d’outils, l’application souvienne de sa position d’origine dans le *virtuel rectangle*. Lorsque l’utilisateur déplace une barre d’outils sur son site d’ancrage, la barre d’outils peut déplacer les autres barres d’outils. Les positions d’origine des autres barres d’outils sont stockées dans les rectangles virtuels correspondants.  
  
##  <a name="a-nameframefrompointa--cdockingmanagerframefrompoint"></a><a name="framefrompoint"></a>CDockingManager::FrameFromPoint  
 Retourne le frame qui contient le point donné.  
  
```  
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,  
    CPaneFrameWnd* pFrameToExclude,  
    BOOL bFloatMultiOnly) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pt`  
 Spécifie le point, en coordonnées d’écran, à vérifier.  
  
 [in] `pFrameToExclude`  
 Pointeur vers une image à exclure.  
  
 [in] `bFloatMultiOnly`  
 `TRUE`Pour exclure les trames qui ne sont pas des instances de `CMultiPaneFrameWnd`; `FALSE` dans le cas contraire.  
  
### <a name="return-value"></a>Valeur de retour  
 Le frame qui contient le point donné ; `NULL` dans le cas contraire.  
  
##  <a name="a-namegetclientareaboundsa--cdockingmanagergetclientareabounds"></a><a name="getclientareabounds"></a>CDockingManager::GetClientAreaBounds  
 Obtient le rectangle qui contient les limites de la zone cliente.  
  
```  
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `rcClient`  
 Une référence vers le rectangle qui contient les limites de la zone cliente.  
  
### <a name="return-value"></a>Valeur de retour  
 Le rectangle qui contient les limites de la zone cliente.  
  
##  <a name="a-namegetdockingmodea--cdockingmanagergetdockingmode"></a><a name="getdockingmode"></a>CDockingManager::GetDockingMode  
 Renvoie le mode d’ancrage actuels.  
  
```  
static AFX_DOCK_TYPE GetDockingMode();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur de l’énumérateur qui représente le mode d’ancrage actuels. Il peut prendre l’une des valeurs suivantes :  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
### <a name="remarks"></a>Notes  
 Pour définir le mode d’ancrage, appelez [CDockingManager::SetDockingMode](#setdockingmode).  
  
##  <a name="a-namegetdocksiteframewnda--cdockingmanagergetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>CDockingManager::GetDockSiteFrameWnd  
 Obtient un pointeur vers le frame de fenêtre parente.  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le frame de fenêtre parente.  
  
##  <a name="a-namegetenabledautohidealignmenta--cdockingmanagergetenabledautohidealignment"></a><a name="getenabledautohidealignment"></a>CDockingManager::GetEnabledAutoHideAlignment  
 Retourne l’alignement activé des volets.  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Combinaison de bits de `CBRS_ALIGN_` indicateurs, ou 0 si les volets de masquage automatique ne sont pas activées. Pour plus d’informations, consultez [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).  
  
### <a name="remarks"></a>Notes  
 La méthode retourne l’alignement activé pour masquer automatiquement les barres de contrôles. Pour activer les barres de masquage automatique, appelez [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes).  
  
##  <a name="a-namegetminiframesa--cdockingmanagergetminiframes"></a><a name="getminiframes"></a>CDockingManager::GetMiniFrames  
 Obtient une liste de miniframes.  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Liste de miniframes qui contiennent des barres de contrôles qui appartiennent au gestionnaire d’ancrage.  
  
##  <a name="a-namegetouteredgeboundsa--cdockingmanagergetouteredgebounds"></a><a name="getouteredgebounds"></a>CDockingManager::GetOuterEdgeBounds  
 Obtient un rectangle qui contient les bords extérieurs de l’image.  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un rectangle qui contient les bords extérieurs de l’image.  
  
##  <a name="a-namegetpanelista--cdockingmanagergetpanelist"></a><a name="getpanelist"></a>CDockingManager::GetPaneList  
 Retourne une liste de volets qui appartiennent au gestionnaire d’ancrage. Cela inclut tous les volets flottants.  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `lstBars`  
 Contient tous les volets du Gestionnaire d’ancrage actuels.  
  
 [in] `bIncludeAutohide`  
 `TRUE`Pour inclure les volets qui sont en mode de masquage automatique ; dans le cas contraire, `FALSE`.  
  
 [in] `pRTCFilter`  
 Si ce n’est pas `NULL`, la liste retournée contient les volets uniquement de la classe runtime spécifié.  
  
 [in] `bIncludeTabs`  
 `TRUE`Pour inclure des onglets ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 S’il existe des volets à onglets dans le Gestionnaire d’ancrage, la méthode retourne des pointeurs vers [CBaseTabbedPane classe](../../mfc/reference/cbasetabbedpane-class.md) objets et vous devez énumérer les onglets explicitement.  
  
 Utilisez `pRTCFilter` pour obtenir une classe particulière de volets. Par exemple, vous pouvez obtenir uniquement les barres d’outils en définissant cette valeur de manière appropriée.  
  
##  <a name="a-namegetsmartdockingmanagera--cdockingmanagergetsmartdockingmanager"></a><a name="getsmartdockingmanager"></a>CDockingManager::GetSmartDockingManager  
 Récupère un pointeur vers le Gestionnaire d’ancrage intelligent.  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le [Gestionnaire d’ancrage intelligent](http://msdn.microsoft.com/en-us/f537a1a6-fb9e-41d7-952f-0f25d5ee7534).  
  
##  <a name="a-namegetsmartdockingmanagerpermanenta--cdockingmanagergetsmartdockingmanagerpermanent"></a><a name="getsmartdockingmanagerpermanent"></a>CDockingManager::GetSmartDockingManagerPermanent  
 Récupère un pointeur vers le Gestionnaire d’ancrage intelligent.  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le Gestionnaire d’ancrage intelligent.  
  
##  <a name="a-namegetsmartdockingparamsa--cdockingmanagergetsmartdockingparams"></a><a name="getsmartdockingparams"></a>CDockingManager::GetSmartDockingParams  
 Retourne les paramètres d’ancrage intelligents pour le Gestionnaire d’ancrage.  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La classe qui contient les paramètres d’ancrage intelligents pour le Gestionnaire d’ancrage actuels. Pour plus d’informations, consultez [CSmartDockingInfo classe](../../mfc/reference/csmartdockinginfo-class.md).  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namehideautohidepanesa--cdockingmanagerhideautohidepanes"></a><a name="hideautohidepanes"></a>CDockingManager::HideAutoHidePanes  
 Masque un volet en mode de masquage automatique.  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBarToExclude`  
 Pointeur vers une barre à exclure de masquage.  
  
 [in] `bImmediately`  
 `TRUE`Pour masquer le volet immédiatement ; `FALSE` pour masquer le volet de l’effet de masquage automatique.  
  
##  <a name="a-nameinsertdocksitea--cdockingmanagerinsertdocksite"></a><a name="insertdocksite"></a>CDockingManager::InsertDockSite  
 Crée un volet d’ancrage et l’insère dans la liste des barres de contrôles.  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `info`  
 Structure qui contient les informations d’alignement sur le volet d’ancrage.  
  
 [in] `dwAlignToInsertAfter`  
 Alignement du volet d’ancrage.  
  
 [out] `ppDockBar`  
 Pointeur vers un pointeur vers un volet d’ancrage.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet d’ancrage a été créé avec succès ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameinsertpanea--cdockingmanagerinsertpane"></a><a name="insertpane"></a>CDockingManager::InsertPane  
 Insère un panneau de configuration dans la liste des barres de contrôles.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pControlBar`  
 Pointeur vers un panneau de configuration.  
  
 [in] `pTarget`  
 Pointeur vers un volet cible.  
  
 [in] `bAfter`  
 `TRUE`Pour insérer le volet après la position du volet cible. `FALSE` dans le cas contraire.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le panneau de configuration est correctement ajoutée à la liste des barres de contrôles ; `FALSE` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode retourne false si le panneau de configuration est déjà dans la liste des barres de contrôle ou si le volet cible n’existe pas dans la liste des barres de contrôles.  
  
##  <a name="a-nameisdocksitemenua--cdockingmanagerisdocksitemenu"></a><a name="isdocksitemenu"></a>CDockingManager::IsDockSiteMenu  
 Spécifie si un menu contextuel s’affiche dans les légendes de tous les volets.  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si un menu site d’ancrage est affiché sur les légendes de tous les volets d’ancrage ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez activer le menu site d’ancrage en appelant [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu).  
  
##  <a name="a-nameisinadjustlayouta--cdockingmanagerisinadjustlayout"></a><a name="isinadjustlayout"></a>CDockingManager::IsInAdjustLayout  
 Détermine si la disposition de tous les volets est ajustée.  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la disposition de tous les volets est ajustée. `FALSE` dans le cas contraire.  
  
##  <a name="a-nameisolecontainermodea--cdockingmanagerisolecontainermode"></a><a name="isolecontainermode"></a>CDockingManager::IsOLEContainerMode  
 Spécifie si le Gestionnaire d’ancrage est en mode de conteneur OLE.  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le Gestionnaire d’ancrage est en mode de conteneur OLE ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 En mode de conteneur OLE, tous les volets d’ancrage et les barres d’outils de l’application sont masqués. Les volets sont également masqués dans ce mode si vous avez défini [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) à `TRUE`.  
  
##  <a name="a-nameispointneardocksitea--cdockingmanagerispointneardocksite"></a><a name="ispointneardocksite"></a>CDockingManager::IsPointNearDockSite  
 Détermine si un point spécifié est proche du site d’ancrage.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 Le point spécifié.  
  
 [out] `dwBarAlignment`  
 Spécifie le bord le point est proche. Les valeurs possibles sont `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP` et `CBRS_ALIGN_BOTTOM`.  
  
 [out] `bOuterEdge`  
 `TRUE`Si le point est proche de la bordure externe du site d’ancrage ; `FALSE` dans le cas contraire.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le point est proche du site d’ancrage ; dans le cas contraire `FALSE`.  
  
##  <a name="a-nameisprintpreviewvalida--cdockingmanagerisprintpreviewvalid"></a><a name="isprintpreviewvalid"></a>CDockingManager::IsPrintPreviewValid  
 Détermine si le mode Aperçu avant impression est défini.  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le mode Aperçu avant impression est défini ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameloadstatea--cdockingmanagerloadstate"></a><a name="loadstate"></a>CDockingManager::LoadState  
 Charge état d’ancrage du responsable à partir du Registre.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Nom du profil.  
  
 [in] `uiID`  
 L’id du Gestionnaire d’ancrage.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’état du Gestionnaire d’ancrage a été chargée avec succès ; dans le cas contraire `FALSE`.  
  
##  <a name="a-namelockupdatea--cdockingmanagerlockupdate"></a><a name="lockupdate"></a>CDockingManager::LockUpdate  
 Verrouille la fenêtre donnée.  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bLock`  
 `TRUE`Si la fenêtre est verrouillée ; `FALSE` dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Lorsqu’une fenêtre est verrouillée, elle ne peut pas être déplacée et qu’il ne peut pas être redessiné.  
  
##  <a name="a-namembhidedockingbarsincontainermodea--cdockingmanagermbhidedockingbarsincontainermode"></a><a name="m_bhidedockingbarsincontainermode"></a>CDockingManager::m_bHideDockingBarsInContainerMode  
 Spécifie si le Gestionnaire d’ancrage masque les volets en mode de conteneur OLE.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>Remarques  
 Définissez cette valeur sur `FALSE` si vous souhaitez conserver tous les volets ancrés à l’image principale visible lorsque l’application est en mode de conteneur OLE. Par défaut, cette valeur est `TRUE`.  
  
##  <a name="a-namemdockmodeglobala--cdockingmanagermdockmodeglobal"></a><a name="m_dockmodeglobal"></a>CDockingManager::m_dockModeGlobal  
 Spécifie le mode d’ancrage global.  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>Remarques  
 Par défaut, chaque volet d’ancrage utilise ce mode d’ancrage. Pour plus d’informations sur les valeurs de ce champ peut être défini sur, consultez [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
##  <a name="a-namemndocksensitivitya--cdockingmanagermndocksensitivity"></a><a name="m_ndocksensitivity"></a>CDockingManager::m_nDockSensitivity  
 Spécifie le respect de la station d’accueil.  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>Notes  
 La sensibilité d’ancrage définit comment fermer flottante volet peut permettre d’approcher un volet d’ancrage, le site d’ancrage ou un autre volet avant que l’infrastructure change son état ancré.  
  
##  <a name="a-namemntimeoutbeforedockingbardocka--cdockingmanagermntimeoutbeforedockingbardock"></a><a name="m_ntimeoutbeforedockingbardock"></a>CDockingManager::m_nTimeOutBeforeDockingBarDock  
 Spécifie la durée, en millisecondes, avant d’un volet d’ancrage est ancré dans ce mode d’ancrage.  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>Notes  
 Avant un volet est ancré, le framework attend pendant le laps de temps spécifié. Cela empêche le volet d’ancrage par inadvertance dans un emplacement tandis que l’utilisateur est toujours en faisant glisser.  
  
##  <a name="a-namemntimeoutbeforetoolbardocka--cdockingmanagermntimeoutbeforetoolbardock"></a><a name="m_ntimeoutbeforetoolbardock"></a>CDockingManager::m_nTimeOutBeforeToolBarDock  
 Spécifie la durée, en millisecondes, avant une barre d’outils est ancrée à la fenêtre frame principale.  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>Notes  
 Avant une barre d’outils est ancrée, le framework attend pendant le laps de temps spécifié. Cela empêche la barre d’outils d’ancrage accidentellement à un emplacement pendant que l’utilisateur est toujours en faisant glisser.  
  
##  <a name="a-nameonactivateframea--cdockingmanageronactivateframe"></a><a name="onactivateframe"></a>CDockingManager::OnActivateFrame  
 Appelé par l’infrastructure lorsque la fenêtre frame devient active ou est désactivée.  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bActivate`  
 Si `TRUE`, la fenêtre frame est rendue active ; si `FALSE`, la fenêtre frame est désactivée.  
  
##  <a name="a-nameonclosepopupmenua--cdockingmanageronclosepopupmenu"></a><a name="onclosepopupmenu"></a>CDockingManager::OnClosePopupMenu  
 Appelée par l’infrastructure quand un menu contextuel actif traite un message WM_DESTROY.  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>Notes  
 Le framework envoie un message WM_DESTROY lorsqu’il est prêt à fermer la fenêtre principale actuelle. Substituez cette méthode pour gérer les notifications de `CMFCPopupMenu` objets qui appartiennent à la fenêtre frame lorsqu’un `CMFCPopupMenu` processus de l’objet une `WM_DESTROY` message.  
  
##  <a name="a-nameonmoveminiframea--cdockingmanageronmoveminiframe"></a><a name="onmoveminiframe"></a>CDockingManager::OnMoveMiniFrame  
 Appelé par l’infrastructure pour déplacer une fenêtre mini-frame.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pFrame`  
 Pointeur vers une fenêtre mini-frame.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la méthode réussit ; dans le cas contraire `FALSE`.  
  
##  <a name="a-nameonpanecontextmenua--cdockingmanageronpanecontextmenu"></a><a name="onpanecontextmenu"></a>CDockingManager::OnPaneContextMenu  
 Appelé par l’infrastructure lorsqu’il génère un menu qui contient une liste de volets.  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 Spécifie l’emplacement du menu.  
  
##  <a name="a-namepanefrompointa--cdockingmanagerpanefrompoint"></a><a name="panefrompoint"></a>CDockingManager::PaneFromPoint  
 Retourne le volet qui contient le point donné.  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL,  
    BOOL bCheckVisibility = FALSE,  
    const CBasePane* pBarToIgnore = NULL) const;  
  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType = NULL,  
    const CBasePane* pBarToIgnore = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 Spécifie le point, en coordonnées d’écran, à vérifier.  
  
 [in] `nSensitivity`  
 Valeur à décompresser le rectangle de la fenêtre de chaque volet activé. Un volet satisfait les critères de recherche si le point donné est dans cette région exagérée.  
  
 [in] `bExactBar`  
 `TRUE`pour ignorer les `nSensitivity` paramètre ; sinon, `FALSE`.  
  
 [in] `pRTCBarType`  
 Si ce n’est pas `NULL`, la méthode recherche uniquement les volets du type spécifié.  
  
 [in] `bCheckVisibility`  
 `TRUE`Pour ne vérifier que les volets visibles ; dans le cas contraire, `FALSE`.  
  
 [out] `dwAlignment`  
 Si un volet se trouve au point spécifié, ce paramètre contient le côté du volet qui a été le plus proche du point spécifié. Pour plus d'informations, consultez la section Remarques.  
  
 [in] `pBarToIgnore`  
 Si ce n’est pas `NULL`, la méthode ignore les volets spécifiées par ce paramètre.  
  
### <a name="return-value"></a>Valeur de retour  
 Le [CBasePane](../../mfc/reference/cbasepane-class.md)-objet qui contient le point donné, dérivé ou `NULL` si aucun volet a été trouvé.  
  
### <a name="remarks"></a>Remarques  
 Lorsque la fonction retourne et un volet a été trouvé, `dwAlignment` contient l’alignement du point spécifié. Par exemple, si le point est la plus proche de la partie supérieure du volet, `dwAlignment` est défini sur `CBRS_ALIGN_TOP`.  
  
##  <a name="a-nameprocesspanecontextmenucommanda--cdockingmanagerprocesspanecontextmenucommand"></a><a name="processpanecontextmenucommand"></a>CDockingManager::ProcessPaneContextMenuCommand  
 Appelée par l’infrastructure pour sélectionner ou effacer une case à cocher pour la commande spécifiée et recalculer la disposition d’un volet indiqué.  
  
```  
BOOL ProcessPaneContextMenuCommand(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 L’id d’une barre de contrôle dans le menu.  
  
 [in] `nCode`  
 Le code de notification de commande.  
  
 [in] `pExtra`  
 Un pointeur vers void qui est converti en un pointeur vers `CCmdUI` si `nCode` est CN_UPDATE_COMMAND_UI.  
  
 [in] `pHandlerInfo`  
 Pointeur vers une structure d’informations. Ce paramètre n'est pas utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si `pEXtra` n’est pas NULL et `nCode` est égal à CN_UPDATE_COMMAND_UI, ou s’il existe une barre de contrôle avec la valeur `nID`.  
  
##  <a name="a-namerecalclayouta--cdockingmanagerrecalclayout"></a><a name="recalclayout"></a>CDockingManager::RecalcLayout  
 Recalcule la disposition des contrôles présents dans la liste des contrôles interne.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bNotify`  
 Ce paramètre n'est pas utilisé.  
  
##  <a name="a-namereleaseemptypanecontainersa--cdockingmanagerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>CDockingManager::ReleaseEmptyPaneContainers  
 Libère les conteneurs volet vide.  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
##  <a name="a-nameremovehiddenmditabbedbara--cdockingmanagerremovehiddenmditabbedbar"></a><a name="removehiddenmditabbedbar"></a>CDockingManager::RemoveHiddenMDITabbedBar  
 Supprime masqué barre volet spécifié.  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 Un pointeur vers une barre de volet à supprimer.  
  
##  <a name="a-nameremoveminiframea--cdockingmanagerremoveminiframe"></a><a name="removeminiframe"></a>CDockingManager::RemoveMiniFrame  
 Supprime un intervalle spécifié dans la liste d’images mini.  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWnd`  
 Pointeur vers une image à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le frame spécifié est supprimé ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameremovepanefromdockmanagera--cdockingmanagerremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CDockingManager::RemovePaneFromDockManager  
 Annule l’inscription d’un volet et le supprime de la liste dans le Gestionnaire d’ancrage.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWnd`  
 Pointeur vers un volet à supprimer.  
  
 [in] `bDestroy`  
 Si `TRUE`, le volet supprimé est détruit.  
  
 [in] `bAdjustLayout`  
 Si `TRUE`, ajuster la disposition d’ancrage immédiatement.  
  
 [in] `bAutoHide`  
 Si `TRUE`, le volet est supprimé de la liste des barres de masquage automatique. Si `FALSE`, le volet est supprimé de la liste de volets régulières.  
  
 [in] `pBarReplacement`  
 Pointeur vers un volet qui remplace le volet supprimé.  
  
##  <a name="a-namereplacepanea--cdockingmanagerreplacepane"></a><a name="replacepane"></a>CDockingManager::ReplacePane  
 Remplace un volet par un autre.  
  
```  
BOOL ReplacePane(
    CDockablePane* pOriginalBar,  
    CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pOriginalBar`  
 Pointeur vers le volet d’origine.  
  
 [in] `pNewBar`  
 Pointeur vers le volet qui remplace le volet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet est remplacé avec succès ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameresortminiframesforzordera--cdockingmanagerresortminiframesforzorder"></a><a name="resortminiframesforzorder"></a>CDockingManager::ResortMiniFramesForZOrder  
 Les images dans la liste d’images mini est analysée.  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="a-namesavestatea--cdockingmanagersavestate"></a><a name="savestate"></a>CDockingManager::SaveState  
 Enregistre l’état de la station d’accueil du responsable dans le Registre.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Un chemin d’accès à une clé de Registre.  
  
 [in] `uiID`  
 L’ID du Gestionnaire d’ancrage.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’état a été enregistré avec succès ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Sauvegarde de l’état d’ancrage du responsable dans le Registre implique d’enregistrer les États des barres de contrôles, les États des barres de masquage automatique et les États des cadres mini présents dans le Gestionnaire d’ancrage.  
  
##  <a name="a-namesendmessagetominiframesa--cdockingmanagersendmessagetominiframes"></a><a name="sendmessagetominiframes"></a>CDockingManager::SendMessageToMiniFrames  
 Envoie le message spécifié à tous les blocs mini.  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uMessage`  
 Le message doit être envoyé.  
  
 [in] `wParam`  
 Dépendants informations supplémentaires.  
  
 [in] `lParam`  
 Dépendants informations supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`toujours.  
  
##  <a name="a-nameserializea--cdockingmanagerserialize"></a><a name="serialize"></a>CDockingManager::Serialize  
 Écrit le Gestionnaire d’ancrage dans une archive.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `ar`  
 Une référence à un objet archive.  
  
### <a name="remarks"></a>Remarques  
 Écriture du Gestionnaire d’ancrage dans une archive implique de déterminer le nombre d’ancrage des barres de contrôles et de curseurs et écrire les barres de contrôles, les images mini, les barres de masquage automatique et les barres avec onglet MDI dans l’archive.  
  
##  <a name="a-namesetautohidezordera--cdockingmanagersetautohidezorder"></a><a name="setautohidezorder"></a>CDockingManager::SetAutohideZOrder  
 Définit la taille, la largeur et la hauteur des barres de contrôles et le volet spécifié.  
  
```  
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pAHDockingBar`  
 Pointeur vers un volet Ancrable.  
  
##  <a name="a-namesetdockingmodea--cdockingmanagersetdockingmode"></a><a name="setdockingmode"></a>CDockingManager::SetDockingMode  
 Définit le mode d’ancrage.  
  
```  
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,  
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```  
  
### <a name="parameters"></a>Paramètres  
 `dockMode`  
 Spécifie le nouveau mode d’ancrage. Pour plus d'informations, consultez la section Remarques.  
  
 `theme`  
 Spécifie le thème à utiliser pour les marqueurs d’ancrage intelligents. Il peut être une des valeurs énumérées suivantes : AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode statique pour définir le mode d’ancrage.  
  
 `dockMode`peut être une des valeurs suivantes :  
  
- `DT_STANDARD`-Standard d’ancrage en mode tel qu’implémenté dans Visual Studio .NET 2003. Les volets sont déplacés sans un contexte de glisser-déplacer.  
  
- `DT_IMMEDIATE`-Le mode d’ancrage immédiat comme implémenté dans Microsoft Visio. Volets sont déplacés avec un contexte d’opération de glissement, mais aucun des marqueurs.  
  
- `DT_SMART`-Actives en mode d’ancrage implémenté dans Visual Studio 2005. Volets sont déplacés avec un contexte de glissement et intelligente des marqueurs qui indiquent où le volet peut être ancré.  
  
##  <a name="a-namesetdockstatea--cdockingmanagersetdockstate"></a><a name="setdockstate"></a>CDockingManager::SetDockState  
 Définit l’état d’ancrage de barres de contrôles, les images mini et les barres de masquage automatique.  
  
```  
virtual void SetDockState();
```  
  
##  <a name="a-namesetprintpreviewmodea--cdockingmanagersetprintpreviewmode"></a><a name="setprintpreviewmode"></a>CDockingManager::SetPrintPreviewMode  
 Définit le mode Aperçu avant impression, les barres sont affichées dans l’aperçu avant impression.  
  
```  
void SetPrintPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bPreview`  
 `TRUE`Si le mode Aperçu avant impression est défini ; `FALSE` dans le cas contraire.  
  
 [in] `pState`  
 Pointeur vers un état d’aperçu. Ce paramètre n'est pas utilisé.  
  
##  <a name="a-namesetsmartdockingparamsa--cdockingmanagersetsmartdockingparams"></a><a name="setsmartdockingparams"></a>CDockingManager::SetSmartDockingParams  
 Définit les paramètres qui définissent le comportement d’ancrage actif.  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `params`  
 Définit les paramètres d’ancrage actif.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode si vous souhaitez personnaliser l’apparence, la couleur ou la forme des marqueurs d’ancrage intelligents.  
  
 Pour utiliser l’apparence par défaut pour les marqueurs d’ancrage intelligents, passez une instance non initialisée de [CSmartDockingInfo classe](../../mfc/reference/csmartdockinginfo-class.md) à `params`.  
  
##  <a name="a-nameshowdelayshowminiframesa--cdockingmanagershowdelayshowminiframes"></a><a name="showdelayshowminiframes"></a>CDockingManager::ShowDelayShowMiniFrames  
 Affiche ou masque les fenêtres des cadres mini.  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bShow`  
 `TRUE`Pour activer la fenêtre de l’image affichée ; `FALSE to` masquer la fenêtre de l’image.  
  
##  <a name="a-nameshowpanesa--cdockingmanagershowpanes"></a><a name="showpanes"></a>CDockingManager::ShowPanes  
 Affiche ou masque les volets des barres de contrôle et de masquage automatique.  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bShow`  
 `TRUE`Pour afficher les volets ; `FALSE to` masquer les volets.  
  
### <a name="return-value"></a>Valeur de retour  
 Toujours `FALSE`.  
  
##  <a name="a-namestartsdockinga--cdockingmanagerstartsdocking"></a><a name="startsdocking"></a>CDockingManager::StartSDocking  
 Démarre l’ancrage actif de la fenêtre spécifiée en fonction de l’alignement du Gestionnaire d’ancrage intelligent.  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDockingWnd`  
 Pointeur vers une fenêtre pour l’ancrer.  
  
##  <a name="a-namestopsdockinga--cdockingmanagerstopsdocking"></a><a name="stopsdocking"></a>CDockingManager::StopSDocking  
 Arrête actives d’ancrage.  
  
```  
void StopSDocking();
```  
  
##  <a name="a-namegetsmartdockingthemea--cdockingmanagergetsmartdockingtheme"></a><a name="getsmartdockingtheme"></a>CDockingManager::GetSmartDockingTheme  
 Une méthode statique qui retourne un thème utilisé pour afficher les marqueurs d’ancrage intelligents.  
  
```  
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une des valeurs énumérées suivantes : AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx (classe)](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane (classe)](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd (classe)](../../mfc/reference/cpaneframewnd-class.md)

