---
title: Classe de COleClientItem | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleClientItem
- AFXOLE/COleClientItem
- AFXOLE/COleClientItem::COleClientItem
- AFXOLE/COleClientItem::Activate
- AFXOLE/COleClientItem::ActivateAs
- AFXOLE/COleClientItem::AttachDataObject
- AFXOLE/COleClientItem::CanCreateFromData
- AFXOLE/COleClientItem::CanCreateLinkFromData
- AFXOLE/COleClientItem::CanPaste
- AFXOLE/COleClientItem::CanPasteLink
- AFXOLE/COleClientItem::Close
- AFXOLE/COleClientItem::ConvertTo
- AFXOLE/COleClientItem::CopyToClipboard
- AFXOLE/COleClientItem::CreateCloneFrom
- AFXOLE/COleClientItem::CreateFromClipboard
- AFXOLE/COleClientItem::CreateFromData
- AFXOLE/COleClientItem::CreateFromFile
- AFXOLE/COleClientItem::CreateLinkFromClipboard
- AFXOLE/COleClientItem::CreateLinkFromData
- AFXOLE/COleClientItem::CreateLinkFromFile
- AFXOLE/COleClientItem::CreateNewItem
- AFXOLE/COleClientItem::CreateStaticFromClipboard
- AFXOLE/COleClientItem::CreateStaticFromData
- AFXOLE/COleClientItem::Deactivate
- AFXOLE/COleClientItem::DeactivateUI
- AFXOLE/COleClientItem::Delete
- AFXOLE/COleClientItem::DoDragDrop
- AFXOLE/COleClientItem::DoVerb
- AFXOLE/COleClientItem::Draw
- AFXOLE/COleClientItem::GetActiveView
- AFXOLE/COleClientItem::GetCachedExtent
- AFXOLE/COleClientItem::GetClassID
- AFXOLE/COleClientItem::GetClipboardData
- AFXOLE/COleClientItem::GetDocument
- AFXOLE/COleClientItem::GetDrawAspect
- AFXOLE/COleClientItem::GetExtent
- AFXOLE/COleClientItem::GetIconFromRegistry
- AFXOLE/COleClientItem::GetIconicMetafile
- AFXOLE/COleClientItem::GetInPlaceWindow
- AFXOLE/COleClientItem::GetItemState
- AFXOLE/COleClientItem::GetLastStatus
- AFXOLE/COleClientItem::GetLinkUpdateOptions
- AFXOLE/COleClientItem::GetType
- AFXOLE/COleClientItem::GetUserType
- AFXOLE/COleClientItem::IsInPlaceActive
- AFXOLE/COleClientItem::IsLinkUpToDate
- AFXOLE/COleClientItem::IsModified
- AFXOLE/COleClientItem::IsOpen
- AFXOLE/COleClientItem::IsRunning
- AFXOLE/COleClientItem::OnActivate
- AFXOLE/COleClientItem::OnActivateUI
- AFXOLE/COleClientItem::OnChange
- AFXOLE/COleClientItem::OnDeactivate
- AFXOLE/COleClientItem::OnDeactivateUI
- AFXOLE/COleClientItem::OnGetClipboardData
- AFXOLE/COleClientItem::OnInsertMenus
- AFXOLE/COleClientItem::OnRemoveMenus
- AFXOLE/COleClientItem::OnSetMenu
- AFXOLE/COleClientItem::OnShowControlBars
- AFXOLE/COleClientItem::OnUpdateFrameTitle
- AFXOLE/COleClientItem::ReactivateAndUndo
- AFXOLE/COleClientItem::Release
- AFXOLE/COleClientItem::Reload
- AFXOLE/COleClientItem::Run
- AFXOLE/COleClientItem::SetDrawAspect
- AFXOLE/COleClientItem::SetExtent
- AFXOLE/COleClientItem::SetHostNames
- AFXOLE/COleClientItem::SetIconicMetafile
- AFXOLE/COleClientItem::SetItemRects
- AFXOLE/COleClientItem::SetLinkUpdateOptions
- AFXOLE/COleClientItem::SetPrintDevice
- AFXOLE/COleClientItem::UpdateLink
- AFXOLE/COleClientItem::CanActivate
- AFXOLE/COleClientItem::OnChangeItemPosition
- AFXOLE/COleClientItem::OnDeactivateAndUndo
- AFXOLE/COleClientItem::OnDiscardUndoState
- AFXOLE/COleClientItem::OnGetClipRect
- AFXOLE/COleClientItem::OnGetItemPosition
- AFXOLE/COleClientItem::OnGetWindowContext
- AFXOLE/COleClientItem::OnScrollBy
- AFXOLE/COleClientItem::OnShowItem
dev_langs:
- C++
helpviewer_keywords:
- OLE containers, client items
- COleClientItem class
- OLE client item class
- container interface class
- OLE containers, interface class
- client items and OLE containers
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
caps.latest.revision: 24
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
ms.openlocfilehash: a200da03305c20eaf2d9c1de1ea585c82410c570
ms.lasthandoff: 02/24/2017

---
# <a name="coleclientitem-class"></a>Classe de COleClientItem
Définit l'interface du conteneur pour les éléments OLE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleClientItem : public CDocItem  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleClientItem::COleClientItem](#coleclientitem)|Construit un objet `COleClientItem`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleClientItem::Activate](#activate)|Ouvre l’élément OLE pour une opération, puis exécute le verbe spécifié.|  
|[COleClientItem::ActivateAs](#activateas)|Active l’élément dans un autre type.|  
|[COleClientItem::AttachDataObject](#attachdataobject)|Accède aux données dans l’objet OLE.|  
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|Indique si une application conteneur peut créer un objet incorporé.|  
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|Indique si une application conteneur peut créer un objet lié.|  
|[COleClientItem::CanPaste](#canpaste)|Indique si le Presse-papiers contient un élément OLE intégrable ou statique.|  
|[COleClientItem::CanPasteLink](#canpastelink)|Indique si le Presse-papiers contient un élément OLE corrélée.|  
|[COleClientItem::Close](#close)|Ferme un lien vers un serveur, mais ne supprime pas l’élément OLE.|  
|[COleClientItem::ConvertTo](#convertto)|Convertit l’élément en un autre type.|  
|[COleClientItem::CopyToClipboard](#copytoclipboard)|Copie l’élément OLE dans le Presse-papiers.|  
|[COleClientItem::CreateCloneFrom](#createclonefrom)|Crée un doublon d’un élément existant.|  
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|Crée un élément incorporé dans le Presse-papiers.|  
|[COleClientItem::CreateFromData](#createfromdata)|Crée un élément incorporé à partir d’un objet de données.|  
|[COleClientItem::CreateFromFile](#createfromfile)|Crée un élément incorporé à partir d’un fichier.|  
|[COleClientItem::CreateLinkFromClipboard](#createlinkfromclipboard)|Crée un élément lié à partir du Presse-papiers.|  
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|Crée un élément lié à partir d’un objet de données.|  
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|Crée un élément lié à partir d’un fichier.|  
|[COleClientItem::CreateNewItem](#createnewitem)|Crée un élément incorporé en lançant l’application serveur.|  
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|Crée un élément statique à partir du Presse-papiers.|  
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|Crée un élément statique à partir d’un objet de données.|  
|[COleClientItem::Deactivate](#deactivate)|Désactive l’élément.|  
|[COleClientItem::DeactivateUI](#deactivateui)|Restaure l’interface utilisateur de l’application conteneur à son état d’origine.|  
|[COleClientItem::Delete](#delete)|Supprime ou ferme l’élément OLE s’il s’agissait d’un élément lié.|  
|[COleClientItem::DoDragDrop](#dodragdrop)|Effectue une opération de glisser-déplacer.|  
|[COleClientItem::DoVerb](#doverb)|Exécute le verbe spécifié.|  
|[COleClientItem::Draw](#draw)|Dessine l’élément OLE.|  
|[COleClientItem::GetActiveView](#getactiveview)|Obtient la vue sur laquelle l’élément est activé sur place.|  
|[COleClientItem::GetCachedExtent](#getcachedextent)|Retourne les limites du rectangle de l’élément OLE.|  
|[COleClientItem::GetClassID](#getclassid)|Obtient l’ID de classe de. l’élément présent|  
|[COleClientItem::GetClipboardData](#getclipboarddata)|Obtient les données qui seraient placées dans le Presse-papiers en appelant le `CopyToClipboard` fonction membre.|  
|[COleClientItem::GetDocument](#getdocument)|Retourne le `COleDocument` objet qui contient l’élément présent.|  
|[COleClientItem::GetDrawAspect](#getdrawaspect)|Obtient le mode actuel de l’élément pour le rendu.|  
|[COleClientItem::GetExtent](#getextent)|Retourne les limites du rectangle de l’élément OLE.|  
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|Récupère un handle d’une icône associée au serveur de CLSID particulier.|  
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|Obtient le métafichier utilisé pour dessiner l’icône de l’élément.|  
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|Retourne un pointeur vers la fenêtre de modification sur place de l’élément.|  
|[COleClientItem::GetItemState](#getitemstate)|Obtient l’état actuel de l’élément.|  
|[COleClientItem::GetLastStatus](#getlaststatus)|Retourne l’état de la dernière opération OLE.|  
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|Renvoie le mode de mise à jour pour un élément lié (fonctionnalité avancée).|  
|[COleClientItem::GetType](#gettype)|Retourne le type de l’élément OLE (incorporé, lié ou statique).|  
|[COleClientItem::GetUserType](#getusertype)|Obtient une chaîne décrivant le type de l’élément.|  
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|Retourne `TRUE` si l’élément est actif sur place.|  
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|Retourne **TRUE** si un élément lié est mis à jour avec le document source.|  
|[COleClientItem::IsModified](#ismodified)|Retourne `TRUE` si l’élément a été modifié depuis son dernier enregistrement.|  
|[COleClientItem::IsOpen](#isopen)|Retourne `TRUE` si l’élément est actuellement ouvert dans l’application serveur.|  
|[COleClientItem::IsRunning](#isrunning)|Retourne `TRUE` si l’application de serveur de l’élément est en cours d’exécution.|  
|[COleClientItem::OnActivate](#onactivate)|Appelée par l’infrastructure pour avertir l’élément qu’il est activé.|  
|[COleClientItem::OnActivateUI](#onactivateui)|Appelée par l’infrastructure pour avertir l’élément qu’il est activé et qu’il doit afficher son interface utilisateur.|  
|[COleClientItem::OnChange](#onchange)|Appelé lorsque le serveur modifie l’élément OLE. Mise en œuvre requis.|  
|[COleClientItem::OnDeactivate](#ondeactivate)|Appelé par l’infrastructure lorsqu’un élément est désactivé.|  
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|Appelé par l’infrastructure lorsque le serveur a supprimé de son interface utilisateur sur place.|  
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|Appelé par l’infrastructure pour obtenir les données à copier dans le Presse-papiers.|  
|[COleClientItem::OnInsertMenus](#oninsertmenus)|Appelé par le framework pour créer un menu composite.|  
|[COleClientItem::OnRemoveMenus](#onremovemenus)|Appelée par l’infrastructure pour supprimer les menus du conteneur d’un menu composite.|  
|[COleClientItem::OnSetMenu](#onsetmenu)|Appelé par l’infrastructure pour installer et supprimer un menu composite.|  
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|Appelé par l’infrastructure pour afficher et masquer des barres de contrôles.|  
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|Appelé par l’infrastructure pour mettre à jour la barre de titre de la fenêtre frame.|  
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|Réactive l’élément et annule la dernière opération de modification sur place.|  
|[COleClientItem::Release](#release)|Libère la connexion à un élément lié OLE et la ferme si elle a été ouvert. Ne supprime pas l’élément client.|  
|[COleClientItem::Reload](#reload)|Recharge l’élément après un appel à `ActivateAs`.|  
|[COleClientItem::Run](#run)|Exécute l’application associée à l’élément.|  
|[COleClientItem::SetDrawAspect](#setdrawaspect)|Définit l’affichage actuel de l’élément pour le rendu.|  
|[COleClientItem::SetExtent](#setextent)|Définit le rectangle englobant de l’élément OLE.|  
|[COleClientItem::SetHostNames](#sethostnames)|Définit le nom du serveur affiche lors de la modification de l’élément OLE.|  
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|Met en cache le métafichier utilisé pour dessiner l’icône de l’élément.|  
|[COleClientItem::SetItemRects](#setitemrects)|Définit le rectangle englobant de l’élément.|  
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|Définit le mode de mise à jour pour un élément lié (fonctionnalité avancée).|  
|[COleClientItem::SetPrintDevice](#setprintdevice)|Définit le périphérique d’impression cible pour cet élément de client.|  
|[COleClientItem::UpdateLink](#updatelink)|Met à jour le cache de la présentation d’un élément.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[COleClientItem::CanActivate](#canactivate)|Appelée par l’infrastructure pour déterminer si l’activation sur place est autorisée.|  
|[COleClientItem::OnChangeItemPosition](#onchangeitemposition)|Appelé par l’infrastructure lors de la position d’un élément change.|  
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|Appelé par l’infrastructure pour annuler après l’activation.|  
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|Appelé par l’infrastructure pour ignorer les informations d’état de l’élément annulation.|  
|[COleClientItem::OnGetClipRect](#ongetcliprect)|Appelée par l’infrastructure pour obtenir les coordonnées du rectangle de découpage de l’élément.|  
|[COleClientItem::OnGetItemPosition](#ongetitemposition)|Appelé par le framework pour obtenir la position par rapport à la vue.|  
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|Appelé par l’infrastructure lorsqu’un élément est activé sur place.|  
|[COleClientItem::OnScrollBy](#onscrollby)|Appelée par l’infrastructure pour faire défiler l’élément dans la vue.|  
|[COleClientItem::OnShowItem](#onshowitem)|Appelé par l’infrastructure pour afficher l’élément OLE.|  
  
## <a name="remarks"></a>Notes  
 Un élément OLE représente les données, créés et gérés par une application serveur, qui peut être incorporée « en toute transparence » dans un document afin qu’il apparaisse à l’utilisateur à un seul document. Le résultat est un « document composé » de l’élément OLE et d’un document conteneur.  
  
 Un élément OLE peut être incorporé ou lié. S’il est incorporé, ses données sont stockées dans le cadre de ce document. S’il est lié, ses données sont stockées dans le cadre d’un fichier séparé est créé par l’application serveur, et seulement un lien vers ce fichier est stocké dans le document composé. Tous les éléments OLE contiennent des informations indiquant l’application serveur qui doit être appelée pour les modifier.  
  
 `COleClientItem`définit plusieurs fonctions substituables qui sont appelées en réponse aux demandes de l’application serveur ; Ces fonctions substituables agissent généralement comme des notifications. Cela permet à l’application serveur pour informer le conteneur de modifications effectuées par l’utilisateur lors de la modification de l’élément OLE ou pour récupérer les informations nécessaires lors de la modification.  
  
 `COleClientItem`peut être utilisée avec le [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc plutôt](../../mfc/reference/colelinkingdoc-class.md), ou [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) classe. Pour utiliser `COleClientItem`, dériver une classe et implémenter les [OnChange](#onchange) fonction membre, qui définit la manière dont le conteneur répond aux modifications apportées à l’élément. Pour prendre en charge l’activation sur place, vous devez remplacer le [OnGetItemPosition](#ongetitemposition) fonction membre. Cette fonction fournit des informations sur la position de l’élément OLE affichée.  
  
 Pour plus d’informations sur l’utilisation de l’interface du conteneur, consultez les articles [conteneurs : implémentation d’un conteneur](../../mfc/containers-implementing-a-container.md) et [Activation](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  Le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] fait référence aux éléments liés et incorporés en tant que « objets » et fait référence aux types d’éléments en tant que « classes ». Cette référence utilise le terme « élément » pour distinguer l’entité OLE de l’objet C++ correspondant et le terme « type » pour distinguer la catégorie OLE à partir de la classe C++.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="activate"></a>COleClientItem::Activate  
 Appelez cette fonction pour exécuter le verbe spécifié à la place de [DoVerb](#doverb) afin que vous pouvez effectuer votre propre traitement lorsqu’une exception est levée.  
  
```  
void Activate(
    LONG nVerb,  
    CView* pView,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nVerb`  
 Spécifie le verbe à exécuter. Il peut avoir l'une des valeurs suivantes :  
  
|Valeur|Signification|Symbole|  
|-----------|-------------|------------|  
|– 0|Primary (verbe)|`OLEIVERB_PRIMARY`|  
|– 1|Verbe secondaire|(Aucun)|  
|– 1|Élément d’affichage pour le modifier|`OLEIVERB_SHOW`|  
|– 2|Modifier l’élément dans une fenêtre distincte|`OLEIVERB_OPEN`|  
|– 3|Masquer l’élément|`OLEIVERB_HIDE`|  
  
 La valeur –&1; est généralement un alias pour un autre verbe. Si la modification d’ouvrir n’est pas pris en charge, –&2; a le même effet que -1. Pour les autres valeurs, consultez [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pView`  
 Pointeur vers la fenêtre d’affichage conteneur qui contient l’élément OLE ; Il est utilisé par l’application serveur pour l’activation sur place. Ce paramètre doit être **NULL** si le conteneur ne prend pas en charge l’activation sur place.  
  
 `lpMsg`  
 Pointeur vers le message qui a provoqué l’élément à activer.  
  
### <a name="remarks"></a>Remarques  
 Si l’application serveur a été écrit à l’aide de la bibliothèque Microsoft Foundation Class, cette fonction provoque la [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb) fonction membre correspondante `COleServerItem` objet à exécuter.  
  
 Si le verbe principal est Edit et zéro est spécifié dans le `nVerb` paramètre, l’application serveur est lancée pour autoriser l’élément OLE à modifier. Si l’application conteneur prend en charge l’activation sur place, modification peut être effectuée en place. Si le conteneur ne prend pas en charge l’activation sur place (ou si le verbe Open est spécifié), le serveur est lancé dans une fenêtre distincte et modification permettre être effectuée. En règle générale, lorsque l’utilisateur de l’application conteneur double-clique sur l’élément OLE, la valeur pour le verbe principal dans le `nVerb` paramètre détermine quelle action que l’utilisateur peut effectuer. Toutefois, si le serveur prend en charge une seule action, il prend cette action, quel que soit ce qui est spécifiée dans le `nVerb` paramètre.  
  
 Pour plus d’informations, consultez [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="activateas"></a>COleClientItem::ActivateAs  
 Utilise les fonctions de conversion d’objets OLE pour activer l’élément comme s’il s’agissait d’un élément du type spécifié par `clsidNew`.  
  
```  
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,  
    REFCLSID clsidOld,  
    REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszUserType*  
 Pointeur vers une chaîne qui représente le type d’utilisateur cible, telles que « Document Word. »  
  
 *clsidOld*  
 ID une référence à la classe en cours de l’élément d'. L’ID de classe doit représenter le type de l’objet réel, tel que stocké, sauf s’il est un lien. Dans ce cas, il doit être le CLSID de l’élément auquel le lien fait référence. Le [classe COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md) fournit automatiquement l’ID de classe approprié pour l’élément.  
  
 `clsidNew`  
 Une référence à l’ID de classe cible.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Il est appelé automatiquement par [COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert). Il n'est pas généralement appelée directement.  
  
##  <a name="attachdataobject"></a>COleClientItem::AttachDataObject  
 Appelez cette fonction pour initialiser un [COleDataObject](../../mfc/reference/coledataobject-class.md) pour accéder aux données dans l’élément OLE.  
  
```  
void AttachDataObject(COleDataObject& rDataObject) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *rDataObject*  
 Référence à un `COleDataObject` objet qui sera initialisée pour autoriser l’accès aux données dans l’élément OLE.  
  
##  <a name="canactivate"></a>COleClientItem::CanActivate  
 Appelé par l’infrastructure lorsque l’utilisateur demande l’activation sur place de l’élément OLE ; valeur de retour de cette fonction détermine si l’activation sur place est autorisée.  
  
```  
virtual BOOL CanActivate();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’activation sur place est autorisée ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut permet l’activation sur place si le conteneur est une fenêtre valide. Remplacez cette fonction pour implémenter une logique spéciale pour accepter ou refuser la demande d’activation. Par exemple, une demande d’activation peut être refusée si l’élément OLE est trop petite ou pas actuellement visible.  
  
 Pour plus d’informations, consultez [IOleInPlaceSite::CanInPlaceActivate](http://msdn.microsoft.com/library/windows/desktop/ms691236) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="cancreatefromdata"></a>COleClientItem::CanCreateFromData  
 Vérifie si une application conteneur peut créer un objet incorporé à partir de la donnée `COleDataObject` objet.  
  
```  
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDataObject`  
 Pointeur vers le [COleDataObject](../../mfc/reference/coledataobject-class.md) objet à partir duquel l’élément OLE doit être créé.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le conteneur peut créer un objet incorporé à partir de la `COleDataObject` objet ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 La `COleDataObject` classe est utilisée dans les transferts de données pour récupérer des données dans divers formats depuis le Presse-papiers, par glisser -déplacer, ou à partir d’un élément OLE incorporé.  
  
 Conteneurs peuvent utiliser cette fonction pour décider d’activer ou désactiver les commandes Édition Coller et Édition Collage spécial.  
  
 Pour plus d’informations, consultez l’article [des objets de données et Sources de données (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="cancreatelinkfromdata"></a>COleClientItem::CanCreateLinkFromData  
 Vérifie si une application conteneur peut créer un objet lié à partir de la donnée `COleDataObject` objet.  
  
```  
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDataObject`  
 Pointeur vers le [COleDataObject](../../mfc/reference/coledataobject-class.md) objet à partir duquel l’élément OLE doit être créé.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le conteneur peut créer un objet lié à partir de la `COleDataObject` objet.  
  
### <a name="remarks"></a>Remarques  
 La `COleDataObject` classe est utilisée dans les transferts de données pour récupérer des données dans divers formats depuis le Presse-papiers, par glisser -déplacer, ou à partir d’un élément OLE incorporé.  
  
 Conteneurs peuvent utiliser cette fonction pour décider d’activer ou désactiver les commandes Édition Collage spécial et Édition Coller avec liaison.  
  
 Pour plus d’informations, consultez l’article [des objets de données et Sources de données (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="canpaste"></a>COleClientItem::CanPaste  
 Appelez cette fonction pour voir si un élément OLE incorporé peut être collé à partir du Presse-papiers.  
  
```  
static BOOL PASCAL CanPaste();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si un élément OLE incorporé peut être collé dans le Presse-papiers. sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) et [OleQueryCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms683739) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="canpastelink"></a>COleClientItem::CanPasteLink  
 Appelez cette fonction pour voir si un élément OLE lié peut être collé à partir du Presse-papiers.  
  
```  
static BOOL PASCAL CanPasteLink();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si un élément OLE lié peut être collé dans le Presse-papiers. sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) et [OleQueryLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms690244) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="close"></a>COleClientItem::Close  
 Appelez cette fonction pour modifier l’état d’un élément OLE à partir de l’état en cours d’exécution à l’état chargé, autrement dit, chargé avec son gestionnaire de mémoire, mais le serveur ne fonctionne ne pas.  
  
```  
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwCloseOption`  
 Indicateur spécifiant dans quelles circonstances l’élément OLE est enregistrée lorsqu’il retourne à l’état chargé. Il peut avoir une des valeurs suivantes :  
  
- `OLECLOSE_SAVEIFDIRTY`Enregistrez l’élément OLE.  
  
- `OLECLOSE_NOSAVE`N’enregistrez pas l’élément OLE.  
  
- `OLECLOSE_PROMPTSAVE`Invite l’utilisateur si vous souhaitez enregistrer l’élément OLE.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction n’a aucun effet lorsque l’élément OLE ne fonctionne pas.  
  
 Pour plus d’informations, consultez [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="coleclientitem"></a>COleClientItem::COleClientItem  
 Construit un `COleClientItem` de l’objet et l’ajoute à la collection du document conteneur d’éléments de document, qui construit l’objet C++ uniquement et n’effectue pas de toute initialisation d’OLE.  
  
```  
COleClientItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pContainerDoc`  
 Pointeur vers le document conteneur qui contient cet élément. Cela peut être un [COleDocument](../../mfc/reference/coledocument-class.md) dérivé.  
  
### <a name="remarks"></a>Notes  
 Si vous passez un **NULL** pointeur, aucun ajout n’est effectuée dans le document conteneur. Vous devez appeler explicitement [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem).  
  
 Vous devez appeler une des fonctions de membre de création suivantes avant d’utiliser l’élément OLE :  
  
- [CreateFromClipboard](#createfromclipboard)  
  
- [CreateFromData](#createfromdata)  
  
- [CreateFromFile](#createfromfile)  
  
- [CreateStaticFromClipboard](#createstaticfromclipboard)  
  
- [CreateStaticFromData](#createstaticfromdata)  
  
- [CreateLinkFromClipboard](#createlinkfromclipboard)  
  
- [CreateLinkFromData](#createlinkfromdata)  
  
- [CreateLinkFromFile](#createlinkfromfile)  
  
- [CreateNewItem](#createnewitem)  
  
- [CreateCloneFrom](#createclonefrom)  
  
##  <a name="convertto"></a>COleClientItem::ConvertTo  
 Appelez cette fonction membre pour convertir le type spécifié par l’élément `clsidNew`.  
  
```  
virtual BOOL ConvertTo(REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Paramètres  
 `clsidNew`  
 L’ID de classe du type cible.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Il est appelé automatiquement par [classe COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md). Il n’est pas nécessaire d’appeler directement.  
  
##  <a name="copytoclipboard"></a>COleClientItem::CopyToClipboard  
 Appelez cette fonction pour copier l’élément OLE dans le Presse-papiers.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bIncludeLink`  
 **TRUE** si les informations de liaison doivent être copiées dans le Presse-papiers, permettant à un élément lié doit être collé ; sinon **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 En règle générale, vous appelez cette fonction lors de l’écriture de gestionnaires de messages pour les commandes copier ou Couper dans le menu Edition. Vous devez implémenter la sélection d’éléments dans votre application conteneur si vous souhaitez implémenter les commandes copier ou Couper.  
  
 Pour plus d’informations, consultez [OleSetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms686623) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createclonefrom"></a>COleClientItem::CreateCloneFrom  
 Appelez cette fonction pour créer une copie de l’élément OLE spécifié.  
  
```  
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```  
  
### <a name="parameters"></a>Paramètres  
 *pSrcItem*  
 Pointeur vers l’élément OLE à dupliquer.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 La copie est identique à l’élément source. Vous pouvez utiliser cette fonction pour prendre en charge les opérations d’annulation.  
  
##  <a name="createfromclipboard"></a>COleClientItem::CreateFromClipboard  
 Appelez cette fonction pour créer un élément incorporé dans le contenu du Presse-papiers.  
  
```  
BOOL CreateFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *rendu*  
 Indicateur spécifiant la façon dont le serveur restitue l’élément OLE. Les valeurs possibles, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Spécifie le format Presse-papiers doit être mis en cache lors de la création de l’élément OLE.  
  
 `lpFormatEtc`  
 Pointeur vers un [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure utilisée si *rendu* est **OLERENDER_FORMAT** ou **OLERENDER_DRAW**. Fournir une valeur pour ce paramètre uniquement si vous souhaitez spécifier des informations de format supplémentaires au-delà du format de Presse-papiers spécifié par `cfFormat`. Si vous omettez ce paramètre, les valeurs par défaut sont utilisées pour les autres champs de la **FORMATETC** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 En général, vous appelez cette fonction à partir du Gestionnaire de messages de la commande Coller dans le menu Edition. (La commande Coller est activée par le framework si la [CanPaste](#canpaste) fonction membre retourne zéro.)  
  
 Pour plus d’informations, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) et [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createfromdata"></a>COleClientItem::CreateFromData  
 Appelez cette fonction pour créer un élément incorporé dans un `COleDataObject` objet.  
  
```  
BOOL CreateFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDataObject`  
 Pointeur vers le [COleDataObject](../../mfc/reference/coledataobject-class.md) objet à partir duquel l’élément OLE doit être créé.  
  
 *rendu*  
 Indicateur spécifiant la façon dont le serveur restitue l’élément OLE. Les valeurs possibles, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Spécifie le format Presse-papiers doit être mis en cache lors de la création de l’élément OLE.  
  
 `lpFormatEtc`  
 Pointeur vers un [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure utilisée si *rendu* est **OLERENDER_FORMAT** ou **OLERENDER_DRAW**. Fournir une valeur pour ce paramètre uniquement si vous souhaitez spécifier des informations de format supplémentaires au-delà du format de Presse-papiers spécifié par `cfFormat`. Si vous omettez ce paramètre, les valeurs par défaut sont utilisées pour les autres champs de la **FORMATETC** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Fournissent des opérations de transfert de données, telles que coller depuis le Presse-papiers ou les opérations de glisser-déplacer, `COleDataObject` objets contenant les informations offertes par un serveur d’applications. Il est généralement utilisé dans la substitution de [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop).  
  
 Pour plus d’informations, consultez [OleCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms691211), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), et [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createfromfile"></a>COleClientItem::CreateFromFile  
 Appelez cette fonction pour créer un élément OLE incorporé à partir d’un fichier.  
  
```  
BOOL CreateFromFile(
    LPCTSTR lpszFileName,  
    REFCLSID clsid = CLSID_NULL,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFileName`  
 Pointeur vers le nom du fichier à partir duquel l’élément OLE doit être créé.  
  
 `clsid`  
 Réservé à un usage ultérieur.  
  
 *rendu*  
 Indicateur spécifiant la façon dont le serveur restitue l’élément OLE. Les valeurs possibles, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Spécifie le format Presse-papiers doit être mis en cache lors de la création de l’élément OLE.  
  
 `lpFormatEtc`  
 Pointeur vers un [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure utilisée si *rendu* est **OLERENDER_FORMAT** ou **OLERENDER_DRAW**. Fournir une valeur pour ce paramètre uniquement si vous souhaitez spécifier des informations de format supplémentaires au-delà du format de Presse-papiers spécifié par `cfFormat`. Si vous omettez ce paramètre, les valeurs par défaut sont utilisées pour les autres champs de la **FORMATETC** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 L’infrastructure appelle cette fonction à partir de [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem) si l’utilisateur choisit OK dans la boîte de dialogue Insérer un objet lors de la création du fichier est sélectionnée.  
  
 Pour plus d’informations, consultez [OleCreateFromFile](http://msdn.microsoft.com/library/windows/desktop/ms690116), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), et [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createlinkfromclipboard"></a>COleClientItem::CreateLinkFromClipboard  
 Appelez cette fonction pour créer un élément lié à partir du contenu du Presse-papiers.  
  
```  
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *rendu*  
 Indicateur spécifiant la façon dont le serveur restitue l’élément OLE. Les valeurs possibles, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Spécifie le format Presse-papiers doit être mis en cache lors de la création de l’élément OLE.  
  
 `lpFormatEtc`  
 Pointeur vers un [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure utilisée si *rendu* est **OLERENDER_FORMAT** ou **OLERENDER_DRAW**. Fournir une valeur pour ce paramètre uniquement si vous souhaitez spécifier des informations de format supplémentaires au-delà du format de Presse-papiers spécifié par `cfFormat`. Si vous omettez ce paramètre, les valeurs par défaut sont utilisées pour les autres champs de la **FORMATETC** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 En général, vous appelez cette fonction à partir du Gestionnaire de messages pour la commande Coller la liaison dans le menu Edition. (La commande Coller la liaison est activée dans l’implémentation par défaut de [COleDocument](../../mfc/reference/coledocument-class.md) si le Presse-papiers contient un élément OLE qui peut être lié à.)  
  
 Pour plus d’informations, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) et [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createlinkfromdata"></a>COleClientItem::CreateLinkFromData  
 Appelez cette fonction pour créer un élément lié dans un `COleDataObject` objet.  
  
```  
BOOL CreateLinkFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDataObject`  
 Pointeur vers le [COleDataObject](../../mfc/reference/coledataobject-class.md) objet à partir duquel l’élément OLE doit être créé.  
  
 *rendu*  
 Indicateur spécifiant la façon dont le serveur restitue l’élément OLE. Les valeurs possibles, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Spécifie le format Presse-papiers doit être mis en cache lors de la création de l’élément OLE.  
  
 `lpFormatEtc`  
 Pointeur vers un [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure utilisée si *rendu* est **OLERENDER_FORMAT** ou **OLERENDER_DRAW**. Fournir une valeur pour ce paramètre uniquement si vous souhaitez spécifier des informations de format supplémentaires au-delà du format de Presse-papiers spécifié par `cfFormat`. Si vous omettez ce paramètre, les valeurs par défaut sont utilisées pour les autres champs de la **FORMATETC** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Appelez pendant une opération de suppression lorsque l’utilisateur indique un lien doit être créé. Il permet également de traiter la commande d’édition coller. Elle est appelée par l’infrastructure dans `COleClientItem::CreateLinkFromClipboard` et [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) lorsque l’option de liaison a été sélectionnée.  
  
 Pour plus d’informations, consultez [OleCreateLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms680731), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), et [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createlinkfromfile"></a>COleClientItem::CreateLinkFromFile  
 Appelez cette fonction pour créer un élément OLE lié à partir d’un fichier.  
  
```  
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFileName`  
 Pointeur vers le nom du fichier à partir duquel l’élément OLE doit être créé.  
  
 *rendu*  
 Indicateur spécifiant la façon dont le serveur restitue l’élément OLE. Les valeurs possibles, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Spécifie le format Presse-papiers doit être mis en cache lors de la création de l’élément OLE.  
  
 `lpFormatEtc`  
 Pointeur vers un [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure utilisée si *rendu* est **OLERENDER_FORMAT** ou **OLERENDER_DRAW**. Fournir une valeur pour ce paramètre uniquement si vous souhaitez spécifier des informations de format supplémentaires au-delà du format de Presse-papiers spécifié par `cfFormat`. Si vous omettez ce paramètre, les valeurs par défaut sont utilisées pour les autres champs de la **FORMATETC** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 L’infrastructure appelle cette fonction si l’utilisateur choisit OK dans la boîte de dialogue Insérer un objet lors de la création du fichier est sélectionnée et la case à cocher lien est activée. Elle est appelée à partir de [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem).  
  
 Pour plus d’informations, consultez [OleCreateLinkToFile](http://msdn.microsoft.com/library/windows/desktop/ms678434), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), et [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createnewitem"></a>COleClientItem::CreateNewItem  
 Appelez cette fonction pour créer un élément incorporé ; Cette fonction lance l’application serveur qui permet à l’utilisateur créer l’élément OLE.  
  
```  
BOOL CreateNewItem(
    REFCLSID clsid,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `clsid`  
 ID qui identifie de façon unique le type d’élément OLE à créer.  
  
 *rendu*  
 Indicateur spécifiant la façon dont le serveur restitue l’élément OLE. Les valeurs possibles, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Spécifie le format Presse-papiers doit être mis en cache lors de la création de l’élément OLE.  
  
 `lpFormatEtc`  
 Pointeur vers un [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure utilisée si *rendu* est **OLERENDER_FORMAT** ou **OLERENDER_DRAW**. Fournir une valeur pour ce paramètre uniquement si vous souhaitez spécifier des informations de format supplémentaires au-delà du format de Presse-papiers spécifié par `cfFormat`. Si vous omettez ce paramètre, les valeurs par défaut sont utilisées pour les autres champs de la **FORMATETC** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 L’infrastructure appelle cette fonction si l’utilisateur choisit OK dans la boîte de dialogue Insérer un objet lorsque le bouton Créer est sélectionné.  
  
 Pour plus d’informations, consultez [OleCreate](http://msdn.microsoft.com/library/windows/desktop/ms678409), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), et [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createstaticfromclipboard"></a>COleClientItem::CreateStaticFromClipboard  
 Appelez cette fonction pour créer un élément statique à partir du contenu du Presse-papiers.  
  
```  
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *rendu*  
 Indicateur spécifiant la façon dont le serveur restitue l’élément OLE. Les valeurs possibles, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Spécifie le format Presse-papiers doit être mis en cache lors de la création de l’élément OLE.  
  
 `lpFormatEtc`  
 Pointeur vers un [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure utilisée si *rendu* est **OLERENDER_FORMAT** ou **OLERENDER_DRAW**. Fournir une valeur pour ce paramètre uniquement si vous souhaitez spécifier des informations de format supplémentaires au-delà du format de Presse-papiers spécifié par `cfFormat`. Si vous omettez ce paramètre, les valeurs par défaut sont utilisées pour les autres champs de la **FORMATETC** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Un élément statique contient les données de présentation, mais pas les données natives ; Par conséquent, il ne peut pas être modifié. En général, vous appelez cette fonction si les [CreateFromClipboard](#createfromclipboard) Échec de la fonction membre.  
  
 Pour plus d’informations, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) et [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createstaticfromdata"></a>COleClientItem::CreateStaticFromData  
 Appelez cette fonction pour créer un élément statique d’un `COleDataObject` objet.  
  
```  
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDataObject`  
 Pointeur vers le [COleDataObject](../../mfc/reference/coledataobject-class.md) objet à partir duquel l’élément OLE doit être créé.  
  
 *rendu*  
 Indicateur spécifiant la façon dont le serveur restitue l’élément OLE. Les valeurs possibles, consultez [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Spécifie le format Presse-papiers doit être mis en cache lors de la création de l’élément OLE.  
  
 `lpFormatEtc`  
 Pointeur vers un [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure utilisée si *rendu* est **OLERENDER_FORMAT** ou **OLERENDER_DRAW**. Fournir une valeur pour ce paramètre uniquement si vous souhaitez spécifier des informations de format supplémentaires au-delà du format de Presse-papiers spécifié par `cfFormat`. Si vous omettez ce paramètre, les valeurs par défaut sont utilisées pour les autres champs de la **FORMATETC** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Un élément statique contient les données de présentation, mais pas les données natives ; Par conséquent, il ne peut pas être modifié. Il s’agit essentiellement le même que [CreateStaticFromClipboard](#createstaticfromclipboard) , sauf qu’un élément statique peut être créé à partir d’une commande arbitraire `COleDataObject`, pas seulement à partir du Presse-papiers.  
  
 Utilisé dans [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) lorsque statique est sélectionné.  
  
 Pour plus d’informations, consultez [OleCreateStaticFromData](http://msdn.microsoft.com/library/windows/desktop/ms687290), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), et [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="deactivate"></a>COleClientItem::Deactivate  
 Appelez cette fonction pour désactiver l’élément OLE et libérer les ressources associées.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Remarques  
 Généralement, vous désactivez un élément d’OLE actif en place lorsque l’utilisateur clique sur la souris sur la zone cliente en dehors des limites de l’élément. Notez que la désactivation de l’élément OLE ignorera le son état d’annulation, ce qui empêche d’appeler le [ReactivateAndUndo](#reactivateandundo) fonction membre.  
  
 Si votre application prend en charge l’annulation, n’appelez pas `Deactivate`; au lieu de cela, appelez [DeactivateUI](#deactivateui).  
  
 Pour plus d’informations, consultez [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="deactivateui"></a>COleClientItem::DeactivateUI  
 Appelez cette fonction lorsque l’utilisateur désactive un élément qui a été activé sur place.  
  
```  
void DeactivateUI();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction restaure l’interface utilisateur de l’application conteneur à son état d’origine, masquer tous les menus et autres contrôles qui ont été créés pour l’activation sur place.  
  
 Cette fonction ne vide pas les informations d’état de restauration de l’élément. Que les informations sont conservées afin que [ReactivateAndUndo](#reactivateandundo) servir ensuite d’exécuter une commande d’annulation de l’application serveur, en cas de commande d’annulation du conteneur est choisie juste après la désactivation de l’élément.  
  
 Pour plus d’informations, consultez [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="delete"></a>COleClientItem::Delete  
 Appelez cette fonction pour supprimer l’élément OLE à partir du document conteneur.  
  
```  
void Delete(BOOL bAutoDelete = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bAutoDelete`  
 Spécifie si l’élément doit être supprimé du document.  
  
### <a name="remarks"></a>Notes  
 Cette fonction appelle le [version](#release) fonction membre, ce qui supprime à son tour l’objet C++ pour l’élément, et supprime définitivement l’élément OLE à partir du document. Si l’élément OLE est incorporé, les données natives pour l’élément sont supprimées. Il ferme toujours un serveur en cours d’exécution. Par conséquent, si l’élément est un lien open, cette fonction ferme.  
  
##  <a name="dodragdrop"></a>COleClientItem::DoDragDrop  
 Appelez le `DoDragDrop` fonction membre pour effectuer une opération de glisser-déplacer.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpItemRect,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpItemRect`  
 Rectangle de l’élément à l’écran en coordonnées clientes (pixels).  
  
 `ptOffset`  
 Le décalage à partir de `lpItemRect` où la position de la souris était au moment de l’opération glisser.  
  
 `bIncludeLink`  
 Affectez la valeur **TRUE** si les données de lien doivent être copiées dans le Presse-papiers. Affectez-lui la valeur **FALSE** si votre application serveur ne prend pas en charge les liens.  
  
 `dwEffects`  
 Détermine les effets de la source de glissement autorisera dans l’opération glisser.  
  
 `lpRectStartDrag`  
 Pointeur vers le rectangle qui définit où commence l’opération glisser. Pour plus d'informations, consultez la section Notes qui suit.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `DROPEFFECT`. S’il est `DROPEFFECT_MOVE`, les données d’origine doivent être supprimées.  
  
### <a name="remarks"></a>Remarques  
 L’opération de glisser-déplacer ne démarre pas immédiatement. Il attend jusqu'à ce que le curseur de la souris quitte le rectangle spécifié par `lpRectStartDrag` ou jusqu'à ce qu’un nombre spécifié de millisecondes écoulées. Si `lpRectStartDrag` est **NULL**, la taille du rectangle est un pixel.  
  
 Délai d’attente est spécifié par un paramètre de clé de Registre. Vous pouvez modifier le délai d’attente en appelant [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) ou [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Si vous ne spécifiez pas de délai d’attente, une valeur par défaut de 200 millisecondes, est utilisée. Faites glisser retarder l’heure est stockée comme suit :  
  
-   Retarder l’heure de glissement de Windows NT est stocké dans HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay.  
  
-   Retarder l’heure de Windows 3.x glisser est stocké dans le fichier WIN. Fichier INI, la section [Windows}.  
  
-   Retarder l’heure de Windows 95/98 glisser est stocké dans une version de WIN. INI.  
  
 Pour plus d’informations sur la façon de faire glisser les informations de délai sont stockées dans le Registre ou le. Fichier INI, consultez [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="doverb"></a>COleClientItem::DoVerb  
 Appelez `DoVerb` pour exécuter le verbe spécifié.  
  
```  
virtual BOOL DoVerb(
    LONG nVerb,  
    CView* pView,
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nVerb`  
 Spécifie le verbe à exécuter. Il peut inclure un des éléments suivants :  
  
|Valeur|Signification|Symbole|  
|-----------|-------------|------------|  
|– 0|Primary (verbe)|`OLEIVERB_PRIMARY`|  
|– 1|Verbe secondaire|(Aucun)|  
|– 1|Élément d’affichage pour le modifier|`OLEIVERB_SHOW`|  
|– 2|Modifier l’élément dans une fenêtre distincte|`OLEIVERB_OPEN`|  
|– 3|Masquer l’élément|`OLEIVERB_HIDE`|  
  
 La valeur –&1; est généralement un alias pour un autre verbe. Si la modification d’ouvrir n’est pas pris en charge, –&2; a le même effet que -1. Pour les autres valeurs, consultez [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pView`  
 Pointeur vers la fenêtre d’affichage. Il est utilisé par le serveur pour l’activation sur place. Ce paramètre doit être **NULL** si l’application conteneur n’autorise pas l’activation sur place.  
  
 `lpMsg`  
 Pointeur vers le message qui a provoqué l’élément à activer.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le verbe a été exécuté avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction appelle le [activer](#activate) fonction membre d’exécuter la commande. Aussi, il intercepte les exceptions et affiche un message à l’utilisateur si une exception est levée.  
  
 Si le verbe principal est Edit et zéro est spécifié dans le `nVerb` paramètre, l’application serveur est lancée pour autoriser l’élément OLE à modifier. Si l’application conteneur prend en charge l’activation sur place, modification peut être effectuée en place. Si le conteneur ne prend pas en charge l’activation sur place (ou si le verbe Open est spécifié), le serveur est lancé dans une fenêtre distincte et modification permettre être effectuée. En règle générale, lorsque l’utilisateur de l’application conteneur double-clique sur l’élément OLE, la valeur pour le verbe principal dans le `nVerb` paramètre détermine quelle action que l’utilisateur peut effectuer. Toutefois, si le serveur prend en charge une seule action, il prend cette action, quel que soit ce qui est spécifiée dans le `nVerb` paramètre.  
  
##  <a name="draw"></a>COleClientItem::Draw  
 Appelez cette fonction pour dessiner l’élément OLE dans le rectangle englobant spécifié en utilisant le contexte de périphérique spécifié.  
  
```  
BOOL Draw(
    CDC* pDC,  
    LPCRECT lpBounds,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointeur vers un [CDC](../../mfc/reference/cdc-class.md) objet utilisé pour dessiner l’élément OLE.  
  
 `lpBounds`  
 Pointeur vers un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou `RECT` structure qui définit le rectangle dans lequel dessiner l’élément OLE (en unités logiques déterminées par le contexte de périphérique).  
  
 `nDrawAspect`  
 Spécifie l’aspect de l’OLE de l’élément, autrement dit, comment il doit s’afficher. Si `nDrawAspect` est –&1;, le dernier aspect défini à l’aide de [SetDrawAspect](#setdrawaspect) est utilisé. Pour plus d’informations sur les valeurs possibles pour cet indicateur, consultez la page [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La fonction peut utiliser la représentation du métafichier de l’élément OLE créé par le [OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw) fonction membre de `COleServerItem`.  
  
 En général, vous utilisez **dessiner** pour afficher l’écran, en passant le contexte de périphérique en tant que `pDC`. Dans ce cas, vous devez spécifier uniquement les deux premiers paramètres.  
  
 Le `lpBounds` paramètre identifie le rectangle dans le contexte de périphérique cible (par rapport à son mode de mappage en cours). Le rendu peut impliquer la mise à l’échelle de l’image et utilisable par les applications conteneurs pour imposer une vue qui met à l’échelle entre l’affichage et l’image finale.  
  
 Pour plus d’informations, consultez [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getactiveview"></a>COleClientItem::GetActiveView  
 Retourne la vue sur laquelle l’élément est activé sur place.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la vue ; dans le cas contraire **NULL** si l’élément n’est pas activé sur place.  
  
##  <a name="getcachedextent"></a>COleClientItem::GetCachedExtent  
 Appelez cette fonction pour récupérer la taille de l’élément OLE.  
  
```  
BOOL GetCachedExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpSize`  
 Pointeur vers un **taille** structure ou un [CSize](../../atl-mfc-shared/reference/csize-class.md) objet qui reçoit les informations de taille.  
  
 `nDrawAspect`  
 Spécifie l’aspect de l’élément OLE dont les limites doivent être récupérés. Pour les valeurs possibles, consultez la page [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; 0 si l’élément OLE est vide.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction fournit les mêmes informations que [GetExtent](#getextent). Toutefois, vous pouvez appeler `GetCachedExtent` pour obtenir des informations de mesure lors du traitement d’autres gestionnaires OLE, tel que [OnChange](#onchange). Les dimensions sont dans `MM_HIMETRIC` unités.  
  
 Cela est possible, car `GetCachedExtent` utilise le [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) interface plutôt que d’utiliser la [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) interface pour obtenir l’étendue de cet élément. Le **IViewObject2** objet COM met en cache les informations de mesure utilisées dans l’appel précédent à [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655).  
  
 Pour plus d’informations, consultez [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclassid"></a>COleClientItem::GetClassID  
 Retourne l’ID de classe de l’élément dans la mémoire pointée par `pClassID`.  
  
```  
void GetClassID(CLSID* pClassID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pClassID`  
 Pointeur vers un identificateur de type [CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) pour récupérer l’ID de classe. Pour plus d’informations sur **CLSID**, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Notes  
 L’ID de classe est un nombre de 128 bits qui identifie de façon unique l’application qui modifie l’élément.  
  
 Pour plus d’informations, consultez [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclipboarddata"></a>COleClientItem::GetClipboardData  
 Appelez cette fonction pour obtenir un `COleDataSource` objet contenant toutes les données qui seraient placées dans le Presse-papiers par un appel à la [CopyToClipboard](#copytoclipboard) fonction membre.  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDataSource`  
 Pointeur vers un [COleDataSource](../../mfc/reference/coledatasource-class.md) objet qui reçoit les données contenues dans l’élément OLE.  
  
 `bIncludeLink`  
 **TRUE** si la liaison de données doit-elle être incluses ; sinon **FALSE**.  
  
 `lpOffset`  
 Le décalage de la souris à l’origine de l’objet en pixels.  
  
 `lpSize`  
 La taille de l’objet en pixels.  
  
### <a name="remarks"></a>Remarques  
 `GetClipboardData`est appelée dans l’implémentation par défaut de [OnGetClipboardData](#ongetclipboarddata). Substituer `OnGetClipboardData` uniquement si vous souhaitez proposer des formats de données en plus de celles offertes par `CopyToClipboard`. Placer ces formats dans la `COleDataSource` objet avant ou après l’appel `CopyToClipboard`, puis passez le `COleDataSource` de l’objet à le [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) (fonction). Par exemple, si vous souhaitez la position de l’élément OLE dans le document conteneur qui accompagne dans le Presse-papiers, définir votre propre format pour transmettre ces informations et placez-le dans le `COleDataSource` avant d’appeler `CopyToClipboard`.  
  
##  <a name="getdocument"></a>COleClientItem::GetDocument  
 Appelez cette fonction pour obtenir un pointeur vers le document qui contient l’élément OLE.  
  
```  
COleDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le document qui contient l’élément OLE. **NULL** si l’élément ne fait pas partie d’un document.  
  
### <a name="remarks"></a>Notes  
 Ce pointeur permet d’accéder à la `COleDocument` objet transmis en tant qu’argument à la `COleClientItem` constructeur.  
  
##  <a name="getdrawaspect"></a>COleClientItem::GetDrawAspect  
 Appelez le `GetDrawAspect` fonction membre pour déterminer l’aspect « actuel », ou, de l’élément.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur à partir de la `DVASPECT` énumération, dont les valeurs sont répertoriées dans la référence pour [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Remarques  
 L’aspect spécifie la façon dont l’élément doit être restitué.  
  
##  <a name="getextent"></a>COleClientItem::GetExtent  
 Appelez cette fonction pour récupérer la taille de l’élément OLE.  
  
```  
BOOL GetExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpSize`  
 Pointeur vers un **taille** structure ou un `CSize` objet qui reçoit les informations de taille.  
  
 `nDrawAspect`  
 Spécifie l’aspect de l’élément OLE dont les limites doivent être récupérés. Pour les valeurs possibles, consultez la page [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; 0 si l’élément OLE est vide.  
  
### <a name="remarks"></a>Remarques  
 Si l’application serveur a été écrit à l’aide de la bibliothèque Microsoft Foundation Class, cette fonction provoque la [OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent) fonction membre correspondante `COleServerItem` objet à appeler. Notez que la taille récupérée peut différer de celle dernièrement défini à la [SetExtent](#setextent) fonction membre ; la taille spécifiée par `SetExtent` est traitée comme une suggestion. Les dimensions sont dans `MM_HIMETRIC` unités.  
  
> [!NOTE]
>  N’appelez pas `GetExtent` lors du traitement d’un gestionnaire d’OLE, tel que [OnChange](#onchange). Appelez [GetCachedExtent](#getcachedextent) à la place.  
  
 Pour plus d’informations, consultez [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="geticonfromregistry"></a>COleClientItem::GetIconFromRegistry  
 Appelez cette fonction membre pour récupérer un handle vers une ressource d’icône associée au serveur de CLSID particulier.  
  
```  
HICON GetIconFromRegistry() const;  
  
static HICON GetIconFromRegistry(CLSID& clsid);
```  
  
### <a name="parameters"></a>Paramètres  
 `clsid`  
 Une référence vers le CLSID du serveur associé à l’icône.  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle valide de la ressource icône, ou **NULL** si du serveur ou une valeur par défaut, est introuvable.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre ne démarrera pas le serveur ou obtenir une icône de manière dynamique, même si le serveur est déjà en cours d’exécution. Au lieu de cela, cette fonction membre ouvre l’image exécutable du serveur et récupère l’icône statique associée au serveur tel qu’il a été enregistré.  
  
##  <a name="geticonicmetafile"></a>COleClientItem::GetIconicMetafile  
 Récupère le métafichier utilisé pour dessiner l’icône de l’élément.  
  
```  
HGLOBAL GetIconicMetafile();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle de métafichier en cas de réussite ; dans le cas contraire **NULL**.  
  
### <a name="remarks"></a>Notes  
 S’il n’existe aucune icône actuelle, une icône par défaut est retournée. Il est appelé automatiquement par les boîtes de dialogue MFC/OLE et n’est généralement pas appelée directement.  
  
 Cette fonction appelle également [SetIconicMetafile](#seticonicmetafile) pour mettre en cache le métafichier pour une utilisation ultérieure.  
  
##  <a name="getinplacewindow"></a>COleClientItem::GetInPlaceWindow  
 Appelez le `GetInPlaceWindow` fonction membre pour obtenir un pointeur vers la fenêtre dans laquelle l’élément a été ouvert pour modification sur place.  
  
```  
CWnd* GetInPlaceWindow();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la fenêtre d’édition sur place de l’élément ; **NULL** si l’élément n’est pas actif ou si son serveur est indisponible.  
  
### <a name="remarks"></a>Notes  
 Cette fonction doit être appelée uniquement pour les éléments qui sont actifs sur place.  
  
##  <a name="getitemstate"></a>COleClientItem::GetItemState  
 Appelez cette fonction pour obtenir l’état actuel de l’élément OLE.  
  
```  
UINT GetItemState() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **COleClientItem::ItemState** énumérée de valeur, qui peut être une des opérations suivantes : `emptyState`, **loadedState**, `openState`, `activeState`, `activeUIState`. Pour plus d’informations sur ces États, consultez l’article [conteneurs : États Client-élément](../../mfc/containers-client-item-states.md).  
  
### <a name="remarks"></a>Notes  
 Pour être informé de l’état de l’élément OLE change, vous devez utiliser le [OnChange](#onchange) fonction membre.  
  
 Pour plus d’informations, consultez l’article [conteneurs : États Client-élément](../../mfc/containers-client-item-states.md).  
  
##  <a name="getlaststatus"></a>COleClientItem::GetLastStatus  
 Retourne le code d’état de la dernière opération OLE.  
  
```  
SCODE GetLastStatus() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `SCODE`.  
  
### <a name="remarks"></a>Remarques  
 Membre pour les fonctions qui retournent un **BOOL** valeur **FALSE**, ou autre membre de fonctions qui retournent **NULL**, `GetLastStatus` retourne plus d’informations sur l’échec. N’oubliez pas que la plupart des fonctions de membre OLE lever des exceptions les plus graves erreurs. Les informations spécifiques sur l’interprétation de la `SCODE` dépend de l’appel OLE sous-jacent qui dernière retourné un `SCODE` valeur.  
  
 Pour plus d’informations sur `SCODE`, consultez [Structure des Codes d’erreur COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] documentation.  
  
##  <a name="getlinkupdateoptions"></a>COleClientItem::GetLinkUpdateOptions  
 Appelez cette fonction pour obtenir la valeur actuelle de l’option de mise à jour de liaisons pour l’élément OLE.  
  
```  
OLEUPDATE GetLinkUpdateOptions();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs suivantes :  
  
- `OLEUPDATE_ALWAYS`Mettre à jour l’élément lié chaque fois que possible. Cette option prend en charge la case lien-mise à jour automatique dans la boîte de dialogue.  
  
- `OLEUPDATE_ONCALL`Mettre à jour l’élément lié uniquement à la demande de l’application conteneur (lorsque le [UpdateLink](#updatelink) la fonction membre est appelée). Cette option prend en charge la case lien-mise à jour manuelle dans la boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 Il s’agit d’une opération avancée.  
  
 Cette fonction est appelée automatiquement par le [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) (classe).  
  
 Pour plus d’informations, consultez [IOleLink::GetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680100) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettype"></a>COleClientItem::GetType  
 Appelez cette fonction pour déterminer si l’élément OLE est incorporé ou lié, ou statique.  
  
```  
OLE_OBJTYPE GetType() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Entier non signé avec l’une des valeurs suivantes :  
  
- `OT_LINK`L’élément OLE est un lien.  
  
- `OT_EMBEDDED`L’élément OLE est incorporé.  
  
- `OT_STATIC`L’élément OLE est statique, autrement dit, il contient uniquement des données de présentation, les données non natives et par conséquent ne peut pas être modifié.  
  
##  <a name="getusertype"></a>COleClientItem::GetUserType  
 Appelez cette fonction pour obtenir la chaîne visible par l’utilisateur, décrivant le type de l’élément OLE, telles que « document Word. »  
  
```  
void GetUserType(
    USERCLASSTYPE nUserClassType,  
    CString& rString);
```  
  
### <a name="parameters"></a>Paramètres  
 *nUserClassType*  
 Une valeur qui indique la variante souhaitée de la chaîne qui décrit le type de l’élément OLE. Cela peut avoir une des valeurs suivantes :  
  
- `USERCLASSTYPE_FULL`Nom complet du type affiché à l’utilisateur.  
  
- `USERCLASSTYPE_SHORT`Un nom court (15 caractères au maximum) pour une utilisation dans les menus déroulants et de la boîte de dialogue Modifier les liaisons.  
  
- `USERCLASSTYPE_APPNAME`Nom de l’application de service de la classe.  
  
 `rString`  
 Une référence à un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet auquel la chaîne qui décrit le type de l’élément OLE est à retourner.  
  
### <a name="remarks"></a>Remarques  
 C’est souvent l’entrée dans la base de données d’inscription.  
  
 Si le nom de type complet est requis mais non disponibles, le nom court est utilisé à la place. Si aucune entrée pour le type de l’élément OLE n’est trouvée dans la base de données d’inscription, ou s’il n’y a aucun type d’utilisateur inscrit pour le type de l’élément OLE, puis le type d’utilisateur actuellement stockés dans l’élément OLE est utilisée. Si ce nom de type utilisateur est une chaîne vide, l’objet « inconnu » est utilisé.  
  
 Pour plus d’informations, consultez [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isinplaceactive"></a>COleClientItem::IsInPlaceActive  
 Appelez cette fonction pour voir si l’élément OLE est actif sur place.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément OLE est actif en place ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Il est courant d’exécuter une logique différente selon que l’élément est modifié sur place. La fonction vérifie si l’état de l’élément actuel est égal à la `activeState` ou `activeUIState`.  
  
##  <a name="islinkuptodate"></a>COleClientItem::IsLinkUpToDate  
 Appelez cette fonction pour voir si l’élément OLE est à jour.  
  
```  
BOOL IsLinkUpToDate() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément OLE est à jour ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Un élément lié peut être obsolète si son document source a été mis à jour. Un élément incorporé qui contient des liens qu’il contient permettre même être obsolète. La fonction effectue une vérification de récursive de l’élément OLE. Notez que pour déterminer si un élément OLE est à jour peut être coûteuse que réellement effectuer une mise à jour.  
  
 Il est appelé automatiquement par le [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) mise en œuvre.  
  
 Pour plus d’informations, consultez [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ismodified"></a>COleClientItem::IsModified  
 Appelez cette fonction pour voir si l’élément OLE est modifié (modifié depuis son dernier enregistrement).  
  
```  
BOOL IsModified() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément OLE est modifiée ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isopen"></a>COleClientItem::IsOpen  
 Appelez cette fonction pour voir si l’élément OLE est ouvert ; Autrement dit, ouvert dans une instance de l’application serveur en cours d’exécution dans une fenêtre distincte.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément OLE est ouvert ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Il est utilisé pour déterminer le moment de dessiner l’objet avec un modèle de hachurage. L’ouverture d’un objet doit avoir un motif hachuré dessiné sur l’objet. Vous pouvez utiliser un [CRectTracker](../../mfc/reference/crecttracker-class.md) objet pour effectuer cette opération.  
  
##  <a name="isrunning"></a>COleClientItem::IsRunning  
 Appelez cette fonction pour voir si l’élément OLE est en cours d’exécution ; Autrement dit, si l’élément est chargé et exécuté dans l’application serveur.  
  
```  
BOOL IsRunning() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément OLE est en cours d’exécution ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [OleIsRunning](http://msdn.microsoft.com/library/windows/desktop/ms688705) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onactivate"></a>COleClientItem::OnActivate  
 Appelée par l’infrastructure pour avertir l’élément qu’il a simplement été activé sur place.  
  
```  
virtual void OnActivate();
```  
  
### <a name="remarks"></a>Remarques  
 Notez que cette fonction est appelée pour indiquer que le serveur est en cours d’exécution, afin de ne pas pour indiquer que son interface utilisateur a été installé dans l’application conteneur. À ce stade, l’objet n’a pas d’interface utilisateur actif (n’est pas `activeUIState`). Il n’a pas installé ses menus ou la barre d’outils. Le [OnActivateUI](#onactivateui) la fonction membre est appelée lorsque cela se produit.  
  
 L’implémentation par défaut appelle la [OnChange](#onchange) fonction membre avec **OLE_CHANGEDSTATE** en tant que paramètre. Remplacez cette fonction pour effectuer un traitement personnalisé lorsqu’un élément devienne actif en place.  
  
##  <a name="onactivateui"></a>COleClientItem::OnActivateUI  
 Le framework appelle `OnActivateUI` lorsque l’objet a entré l’état actif de l’interface utilisateur.  
  
```  
virtual void OnActivateUI();
```  
  
### <a name="remarks"></a>Remarques  
 L’objet est maintenant installé sa barre d’outils et les menus.  
  
 L’implémentation par défaut souvient du serveur `HWND` pour une date ultérieure **GetServerWindow** appels.  
  
##  <a name="onchange"></a>COleClientItem::OnChange  
 Appelé par l’infrastructure lorsque l’utilisateur modifie, enregistre ou ferme l’élément OLE.  
  
```  
virtual void OnChange(
    OLE_NOTIFICATION nCode,  
    DWORD dwParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `nCode`  
 La raison pour laquelle le serveur modifié cet élément. Il peut avoir une des valeurs suivantes :  
  
- `OLE_CHANGED`Apparence de l’élément OLE a changé.  
  
- `OLE_SAVED`L’élément OLE a été enregistré.  
  
- `OLE_CLOSED`L’élément OLE a été fermé.  
  
- `OLE_CHANGED_STATE`L’élément OLE a changé d’état à un autre.  
  
 `dwParam`  
 Si `nCode` est `OLE_SAVED` ou `OLE_CLOSED`, ce paramètre n’est pas utilisé. Si `nCode` est `OLE_CHANGED`, ce paramètre spécifie l’aspect de l’élément OLE a été modifié. Pour les valeurs possibles, consultez la `dwParam` paramètre de [COleClientItem::Draw](#draw). Si `nCode` est `OLE_CHANGED_STATE`, ce paramètre est un **COleClientItem::ItemState** valeur énumérée et décrit l’état en cours. Il peut avoir l’une des valeurs suivantes : `emptyState`, **loadedState**, `openState`, `activeState`, ou `activeUIState`.  
  
### <a name="remarks"></a>Notes  
 (Si l’application serveur est écrite à l’aide de la bibliothèque Microsoft Foundation Class, cette fonction est appelée en réponse à la `Notify` les fonctions membres de `COleServerDoc` ou `COleServerItem`.) L’implémentation par défaut marque le document conteneur comme modifié se `nCode` est `OLE_CHANGED` ou `OLE_SAVED`.  
  
 Pour `OLE_CHANGED_STATE`, l’état actuel est retourné à partir de [GetItemState](#getitemstate) seront toujours l’ancien état, ce qui signifie que l’état qui était actif avant ce changement d’état.  
  
 Remplacez cette fonction pour répondre aux modifications d’état de l’élément OLE. En général vous mettre à jour d’affichage en invalidant la zone dans laquelle l’élément est affiché. Appeler l’implémentation de classe de base au début du remplacement.  
  
##  <a name="onchangeitemposition"></a>COleClientItem::OnChangeItemPosition  
 Appelé par l’infrastructure pour notifier au conteneur que l’étendue de l’élément OLE a été modifié lors de l’activation sur place.  
  
```  
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```  
  
### <a name="parameters"></a>Paramètres  
 *rectPos*  
 Indique la position par rapport à la zone cliente de l’application conteneur.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la position de l’élément a été correctement modifiée ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut détermine le nouveau rectangle visible de l’élément OLE et les appels [SetItemRects](#setitemrects) avec les nouvelles valeurs. L’implémentation par défaut calcule le rectangle visible de l’élément et transmet ces informations au serveur.  
  
 Remplacez cette fonction pour appliquer des règles spécifiques à l’opération de redimensionnement et de déplacement. Si l’application est écrite dans les MFC, cet appel résultats, car le serveur appelé [COleServerDoc::RequestPositionChange](../../mfc/reference/coleserverdoc-class.md#requestpositionchange).  
  
##  <a name="ondeactivate"></a>COleClientItem::OnDeactivate  
 Appelé par l’infrastructure lorsque l’élément OLE est passé de l’état actif sur place ( `activeState`) à l’état chargé, ce qui signifie qu’elle est désactivée après une activation en place.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Remarques  
 Notez que cette fonction est appelée pour indiquer que l’élément OLE est fermée, pas que son interface utilisateur a été supprimé de l’application conteneur. Lorsque cela se produit, le [OnDeactivateUI](#ondeactivateui) la fonction membre est appelée.  
  
 L’implémentation par défaut appelle la [OnChange](#onchange) fonction membre avec **OLE_CHANGEDSTATE** en tant que paramètre. Remplacez cette fonction pour effectuer un traitement personnalisé lorsqu’un élément actif sur place est désactivé. Par exemple, si vous prenez en charge la commande Annuler dans votre application conteneur, vous pouvez substituer cette fonction pour ignorer l’état d’annulation, indiquant que la dernière opération effectuée sur l’élément OLE ne peut pas être annulée une fois que l’élément est désactivé.  
  
##  <a name="ondeactivateandundo"></a>COleClientItem::OnDeactivateAndUndo  
 Appelé par l’infrastructure lorsque l’utilisateur appelle la commande Annuler après l’activation de l’élément OLE sur place.  
  
```  
virtual void OnDeactivateAndUndo();
```  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut appelle [DeactivateUI](#deactivateui) pour désactiver l’interface d’utilisateur du serveur. Remplacez cette fonction si vous implémentez la commande Annuler dans votre application conteneur. Dans votre substitution, appelez la version de classe de base de la fonction et annuler la dernière commande exécutée dans votre application.  
  
 Pour plus d’informations, consultez [IOleInPlaceSite::DeactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms683743) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondeactivateui"></a>COleClientItem::OnDeactivateUI  
 Appelé lorsque l’utilisateur désactive un élément qui a été activé sur place.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Paramètres  
 `bUndoable`  
 Spécifie si les modifications sont annulables.  
  
### <a name="remarks"></a>Notes  
 Cette fonction restaure l’interface utilisateur de l’application conteneur à son état d’origine, masquer tous les menus et autres contrôles qui ont été créés pour l’activation sur place.  
  
 Si `bUndoable` est **FALSE**, le conteneur doit désactiver la commande Annuler, en vigueur en ignorant l’état d’annulation du conteneur, car il indique que la dernière opération effectuée par le serveur n’est pas annulable.  
  
##  <a name="ondiscardundostate"></a>COleClientItem::OnDiscardUndoState  
 Appelé par l’infrastructure lorsque l’utilisateur effectue une action qui ignore l’état d’annulation en modifiant l’élément OLE.  
  
```  
virtual void OnDiscardUndoState();
```  
  
### <a name="remarks"></a>Remarques  
 L'implémentation par défaut n'exécute aucune opération. Remplacez cette fonction si vous implémentez la commande Annuler dans votre application conteneur. Dans votre substitution, ignorer l’état d’annulation de l’application conteneur.  
  
 Si le serveur a été écrit avec la bibliothèque Microsoft Foundation Class, le serveur peut provoquer cette fonction doit être appelée en appelant [COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate).  
  
 Pour plus d’informations, consultez [IOleInPlaceSite::DiscardUndoState](http://msdn.microsoft.com/library/windows/desktop/ms688642) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ongetclipboarddata"></a>COleClientItem::OnGetClipboardData  
 Appelé par l’infrastructure pour obtenir un `COleDataSource` objet contenant toutes les données qui seraient placées dans le Presse-papiers par un appel à la [CopyToClipboard](#copytoclipboard) ou [DoDragDrop](#dodragdrop) fonction membre.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>Paramètres  
 `bIncludeLink`  
 Affectez la valeur **TRUE** si la liaison de données doit être copié dans le Presse-papiers. Affectez la valeur **FALSE** si votre application serveur ne prend pas en charge les liens.  
  
 `lpOffset`  
 Pointeur vers l’offset de la souris à l’origine de l’objet en pixels.  
  
 `lpSize`  
 Pointeur vers la taille de l’objet en pixels.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [COleDataSource](../../mfc/reference/coledatasource-class.md) objet contenant les données du Presse-papiers.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de cette fonction appelle [exception de GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetcliprect"></a>COleClientItem::OnGetClipRect  
 Le framework appelle la `OnGetClipRect` fonction membre pour obtenir les coordonnées du rectangle de découpage de l’élément en cours de modification en place.  
  
```  
virtual void OnGetClipRect(CRect& rClipRect);
```  
  
### <a name="parameters"></a>Paramètres  
 *rClipRect*  
 Pointeur vers un objet de classe [CRect](../../atl-mfc-shared/reference/crect-class.md) qui contiendra les coordonnées du rectangle de découpage de l’élément.  
  
### <a name="remarks"></a>Remarques  
 Coordonnées sont exprimées en pixels par rapport à la zone cliente de la fenêtre d’application de conteneur.  
  
 L’implémentation par défaut retourne simplement le rectangle client de la vue à laquelle l’article est actif en place.  
  
##  <a name="ongetitemposition"></a>COleClientItem::OnGetItemPosition  
 Le framework appelle la `OnGetItemPosition` fonction membre pour obtenir les coordonnées de l’élément en cours de modification en place.  
  
```  
virtual void OnGetItemPosition(CRect& rPosition);
```  
  
### <a name="parameters"></a>Paramètres  
 `rPosition`  
 Référence à la [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui contient les coordonnées de position de l’élément.  
  
### <a name="remarks"></a>Remarques  
 Coordonnées sont exprimées en pixels par rapport à la zone cliente de la fenêtre d’application de conteneur.  
  
 L’implémentation par défaut de cette fonction est sans effet. Les applications qui prennent en charge la modification sur place nécessitent son implémentation.  
  
##  <a name="ongetwindowcontext"></a>COleClientItem::OnGetWindowContext  
 Appelé par l’infrastructure lorsqu’un élément est activé sur place.  
  
```  
virtual BOOL OnGetWindowContext(
    CFrameWnd** ppMainFrame,  
    CFrameWnd** ppDocFrame,  
    LPOLEINPLACEFRAMEINFO lpFrameInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 `ppMainFrame`  
 Pointeur vers un pointeur vers la fenêtre frame principale.  
  
 `ppDocFrame`  
 Pointeur vers un pointeur vers la fenêtre frame de document.  
  
 `lpFrameInfo`  
 Pointeur vers un [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) structure qui doit recevoir des informations sur la fenêtre frame.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utilisée pour récupérer des informations sur la fenêtre parente de l’élément OLE.  
  
 Si le conteneur est une application MDI, l’implémentation par défaut retourne un pointeur vers le [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) dans l’objet `ppMainFrame` et un pointeur vers l’actif [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) dans l’objet `ppDocFrame`. Si le conteneur est une application SDI, l’implémentation par défaut retourne un pointeur vers le [CFrameWnd](../../mfc/reference/cframewnd-class.md) dans l’objet `ppMainFrame` et retourne **NULL** dans `ppDocFrame`. L’implémentation par défaut remplit également les membres de `lpFrameInfo`.  
  
 Remplacez cette fonction uniquement si l’implémentation par défaut ne répondent pas à votre application ; par exemple, si votre application comporte un paradigme d’interface utilisateur qui diffère de type SDI ou MDI. Il s’agit d’une avancée substituable.  
  
 Pour plus d’informations, consultez [IOleInPlaceSite::GetWindowContext](http://msdn.microsoft.com/library/windows/desktop/ms694366) et [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="oninsertmenus"></a>COleClientItem::OnInsertMenus  
 Appelé par l’infrastructure lors de l’activation sur place pour insérer des menus de l’application conteneur dans un menu vide.  
  
```  
virtual void OnInsertMenus(
    CMenu* pMenuShared,  
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```  
  
### <a name="parameters"></a>Paramètres  
 `pMenuShared`  
 Pointe vers un menu vide.  
  
 `lpMenuWidths`  
 Pointe vers un tableau de six **LONG** valeurs indiquant le nombre de menus dans chacun des groupes de menus suivants : fichier, Edition, conteneur, objet, fenêtre, aide. Il incombe à l’application conteneur pour les groupes de menu fichier, conteneur et fenêtre, correspondant aux éléments 0, 2 et 4 de ce tableau.  
  
### <a name="remarks"></a>Remarques  
 Ce menu est ensuite transmis au serveur, ce qui insère ses menus, création d’un menu composite. Cette fonction peut être appelée plusieurs fois pour générer plusieurs menus composites.  
  
 Insère l’implémentation par défaut `pMenuShared` les menus sur place conteneur ; autrement dit, les groupes de menu fichier, conteneur et fenêtre. [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo) est utilisée pour définir cette ressource de menu. L’implémentation par défaut affecte également les valeurs appropriées aux éléments 0, 2 et 4 de `lpMenuWidths`, en fonction de la ressource de menu. Remplacez cette fonction si l’implémentation par défaut n’est pas appropriée pour votre application. par exemple, si votre application n’utilise pas de modèles de document pour associer des ressources avec des types de documents. Si vous remplacez cette fonction, vous devez également substituer [OnSetMenu](#onsetmenu) et [OnRemoveMenus](#onremovemenus). Il s’agit d’une avancée substituable.  
  
 Pour plus d’informations, consultez [IOleInPlaceFrame::InsertMenu](http://msdn.microsoft.com/library/windows/desktop/ms683987) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onremovemenus"></a>COleClientItem::OnRemoveMenus  
 Appelé par l’infrastructure pour supprimer les menus du conteneur dans le menu composite spécifié à la fin de l’activation sur place.  
  
```  
virtual void OnRemoveMenus(CMenu* pMenuShared);
```  
  
### <a name="parameters"></a>Paramètres  
 `pMenuShared`  
 Pointe vers le menu composite construit par les appels à la [OnInsertMenus](#oninsertmenus) fonction membre.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut supprime `pMenuShared` les menus sur place conteneur, qui est, les groupes de menu fichier, conteneur et fenêtre. Remplacez cette fonction si l’implémentation par défaut n’est pas appropriée pour votre application. par exemple, si votre application n’utilise pas de modèles de document pour associer des ressources avec des types de documents. Si vous remplacez cette fonction, vous devez probablement substituer [OnInsertMenus](#oninsertmenus) et [OnSetMenu](#onsetmenu) ainsi. Il s’agit d’une avancée substituable.  
  
 Les sous-menus `pMenuShared` peuvent être partagés par plusieurs menus composite si le serveur a plusieurs fois appelé `OnInsertMenus`. Par conséquent, vous ne devez pas supprimer des sous-menus dans la substitution de `OnRemoveMenus`; vous devez uniquement les détacher.  
  
 Pour plus d’informations, consultez [IOleInPlaceFrame::RemoveMenus](http://msdn.microsoft.com/library/windows/desktop/ms688685) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onscrollby"></a>COleClientItem::OnScrollBy  
 Appelé par l’infrastructure pour faire défiler l’élément OLE en réponse aux demandes à partir du serveur.  
  
```  
virtual BOOL OnScrollBy(CSize sizeExtent);
```  
  
### <a name="parameters"></a>Paramètres  
 *sizeExtent*  
 Spécifie la distance, en pixels, pour faire défiler vers le sens x et y.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur a fait défiler l’élément ; 0 si l’élément ne peut pas faire défiler.  
  
### <a name="remarks"></a>Notes  
 Par exemple, si l’élément OLE est partiellement visible et que l’utilisateur se déplace hors de la zone visible lors de la modification sur place, cette fonction est appelée pour que le curseur reste visible. L'implémentation par défaut n'exécute aucune opération. Remplacez cette fonction pour faire défiler l’élément de la valeur spécifiée. Notez que la partie visible de l’élément OLE peut changer à la suite, le défilement. Appelez [SetItemRects](#setitemrects) pour mettre à jour le rectangle visible de l’élément.  
  
 Pour plus d’informations, consultez [IOleInPlaceSite::Scroll](http://msdn.microsoft.com/library/windows/desktop/ms690291) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onsetmenu"></a>COleClientItem::OnSetMenu  
 Appelé par l’infrastructure deux fois lors de l’activation sur place commence et se termine. la première fois pour installer le menu composite et la deuxième fois (avec `holemenu` égal à **NULL**) pour la supprimer.  
  
```  
virtual void OnSetMenu(
    CMenu* pMenuShared,  
    HOLEMENU holemenu,  
    HWND hwndActiveObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `pMenuShared`  
 Pointeur vers le menu composite construit par les appels à la [OnInsertMenus](#oninsertmenus) fonction membre et le `InsertMenu` (fonction).  
  
 `holemenu`  
 Handle vers le descripteur de menu retourné par le **OleCreateMenuDescriptor** (fonction), ou **NULL** si le code de distribution doit être supprimée.  
  
 *hwndActiveObject*  
 Handle vers la fenêtre d’édition pour l’élément OLE. Il s’agit de la fenêtre qui recevra les commandes d’édition de OLE.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut installe ou supprime le menu composite et appelle ensuite le [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831) (fonction) pour installer ou supprimer le code de distribution. Remplacez cette fonction si l’implémentation par défaut n’est pas appropriée pour votre application. Si vous remplacez cette fonction, vous devez probablement substituer [OnInsertMenus](#oninsertmenus) et [OnRemoveMenus](#onremovemenus) ainsi. Il s’agit d’une avancée substituable.  
  
 Pour plus d’informations, consultez [OleCreateMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms691415), [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831), et [IOleInPlaceFrame::SetMenu](http://msdn.microsoft.com/library/windows/desktop/ms693713) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onshowcontrolbars"></a>COleClientItem::OnShowControlBars  
 Appelé par l’infrastructure pour afficher et masquer des barres de contrôle de l’application conteneur.  
  
```  
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 `pFrameWnd`  
 Pointeur vers la fenêtre frame de l’application conteneur. Cela peut être une fenêtre frame principale ou une fenêtre enfant MDI.  
  
 `bShow`  
 Spécifie si les barres de contrôle doivent être affichées ou masquées.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’appel de fonction entraîne une modification dans l’état des barres de contrôles ; 0 si l’appel n’entraîne aucune modification ou si `pFrameWnd` ne pointe pas vers la fenêtre du conteneur.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction retourne 0 si les barres de contrôles sont déjà dans l’état spécifié par *bShow.* Cela se produirait, par exemple, si les barres de contrôles sont masqués et `bShow` est **FALSE**.  
  
 L’implémentation par défaut supprime la barre d’outils de la fenêtre frame de niveau supérieur.  
  
##  <a name="onshowitem"></a>COleClientItem::OnShowItem  
 Appelé par l’infrastructure pour afficher l’élément OLE, rendant totalement visible lors de la modification.  
  
```  
virtual void OnShowItem();
```  
  
### <a name="remarks"></a>Remarques  
 Il est utilisé lorsque votre application conteneur prend en charge des liens vers des éléments incorporés (autrement dit, si vous avez dérivé votre classe de document de [COleLinkingDoc plutôt](../../mfc/reference/colelinkingdoc-class.md)). Cette fonction est appelée au cours de l’activation sur place ou lorsque l’élément OLE est une source de la liaison et l’utilisateur souhaite modifier. L’implémentation par défaut active la première vue du document conteneur. Remplacez cette fonction pour faire défiler le document afin que l’élément OLE est visible.  
  
##  <a name="onupdateframetitle"></a>COleClientItem::OnUpdateFrameTitle  
 Appelé par l’infrastructure lors de l’activation sur place pour mettre à jour la barre de titre de la fenêtre frame.  
  
```  
virtual BOOL OnUpdateFrameTitle();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si cette fonction mis à jour le titre du frame, sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut ne modifie pas le titre de la fenêtre frame. Remplacez cette fonction si vous souhaitez un titre de cadre différent pour votre application, par exemple « *application serveur* - *élément* dans *docname*» (comme dans « Microsoft Excel - feuille de calcul dans le rapport. DOC »). Il s’agit d’une avancée substituable.  
  
##  <a name="reactivateandundo"></a>COleClientItem::ReactivateAndUndo  
 Appelez cette fonction pour réactiver l’élément OLE et annuler la dernière opération effectuée par l’utilisateur lors de la modification sur place.  
  
```  
BOOL ReactivateAndUndo();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Si votre application conteneur prend en charge la commande Annuler, appelez cette fonction si l’utilisateur choisit la commande Annuler immédiatement après la désactivation de l’élément OLE.  
  
 Si l’application serveur est écrite avec les bibliothèques de classes Microsoft Foundation, cette fonction, le serveur appelle [COleServerDoc::OnReactivateAndUndo](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo).  
  
 Pour plus d’informations, consultez [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="release"></a>COleClientItem::Release  
 Appelez cette fonction pour nettoyer les ressources utilisées par l’élément OLE.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwCloseOption`  
 Indicateur spécifiant dans quelles circonstances l’élément OLE est enregistrée lorsqu’il retourne à l’état chargé. Pour obtenir la liste des valeurs possibles, consultez la page [COleClientItem::Close](#close).  
  
### <a name="remarks"></a>Remarques  
 **Version** est appelée par le `COleClientItem` destructeur.  
  
 Pour plus d’informations, consultez [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="reload"></a>COleClientItem::Reload  
 Ferme et le recharge l’élément.  
  
```  
BOOL Reload();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Appelez le `Reload` fonction après l’activation de l’élément en tant qu’élément d’un autre type par un appel à [ActivateAs](#activateas).  
  
##  <a name="run"></a>COleClientItem::Run  
 Exécute l’application associée à cet élément.  
  
```  
void Run();
```  
  
### <a name="remarks"></a>Notes  
 Appelez le **exécuter** fonction membre pour lancer l’application serveur avant d’activer l’élément. Cette opération est effectuée automatiquement par [activer](#activate) et [DoVerb](#doverb), il est donc généralement pas nécessaire d’appeler cette fonction. Appelez cette fonction s’il est nécessaire exécuter le serveur afin de définir un attribut d’élément, tel que [SetExtent](#setextent), avant d’exécuter [DoVerb](#doverb).  
  
##  <a name="setdrawaspect"></a>COleClientItem::SetDrawAspect  
 Appelez le `SetDrawAspect` fonction membre pour définir la « h », ou la vue, de l’élément.  
  
```  
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Paramètres  
 `nDrawAspect`  
 Valeur de l'énumération `DVASPECT`. Ce paramètre peut prendre l'une des valeurs suivantes :  
  
- `DVASPECT_CONTENT`Élément est représenté de manière à ce qu’il peut être affiché en tant qu’objet incorporé dans son conteneur.  
  
- `DVASPECT_THUMBNAIL`Élément est rendu dans une représentation sous forme de « miniature » afin qu’il peut être affiché dans un outil de navigation.  
  
- `DVASPECT_ICON`Élément est représenté par une icône.  
  
- `DVASPECT_DOCPRINT`Élément est représenté comme s’il était imprimé à l’aide de la commande Imprimer dans le menu fichier.  
  
### <a name="remarks"></a>Remarques  
 L’aspect spécifie comment l’élément doit être restitué par [dessiner](#draw) lorsque la valeur par défaut de cette fonction `nDrawAspect` argument est utilisé.  
  
 Cette fonction est appelée automatiquement par l’icône de modification (et d’autres boîtes de dialogue d’appeler directement la boîte de dialogue Changer d’icône) pour activer l’aspect de l’affichage sous forme d’icône lorsqu’il est demandé par l’utilisateur.  
  
##  <a name="setextent"></a>COleClientItem::SetExtent  
 Appelez cette fonction pour indiquer la quantité d’espace disponible pour l’élément OLE.  
  
```  
void SetExtent(
    const CSize& size,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Paramètres  
 `size`  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) objet qui contient les informations de taille.  
  
 `nDrawAspect`  
 Spécifie l’aspect de l’élément OLE dont les limites doivent être définis. Pour les valeurs possibles, consultez la page [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Remarques  
 Si l’application serveur a été écrit à l’aide de la bibliothèque Microsoft Foundation Class, cela provoque la [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent) fonction membre correspondante `COleServerItem` objet à appeler. L’élément OLE pouvez ajuster son affichage en conséquence. Les dimensions doivent être dans `MM_HIMETRIC` unités. Appelez cette fonction lorsque l’utilisateur redimensionne l’élément OLE ou si vous prenez en charge une forme de négociation de disposition.  
  
 Pour plus d’informations, consultez [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="sethostnames"></a>COleClientItem::SetHostNames  
 Appelez cette fonction pour spécifier le nom de l’application conteneur et le nom du conteneur pour un élément OLE incorporé.  
  
```  
void SetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszHost`  
 Pointeur vers le nom visible par l’utilisateur de l’application conteneur.  
  
 `lpszHostObj`  
 Pointeur vers une chaîne d’identification du conteneur qui contient l’élément OLE.  
  
### <a name="remarks"></a>Notes  
 Si l’application serveur a été écrit à l’aide de la bibliothèque Microsoft Foundation Class, cette fonction appelle le [OnSetHostNames](../../mfc/reference/coleserverdoc-class.md#onsethostnames) fonction membre de la `COleServerDoc` document qui contient l’élément OLE. Ces informations sont utilisées dans les titres de la fenêtre lorsque l’élément OLE est en cours de modification. Chaque fois qu’un document conteneur est chargé, l’infrastructure appelle cette fonction pour tous les éléments OLE dans le document. `SetHostNames`s’applique uniquement aux éléments incorporés. Il n’est pas nécessaire d’appeler cette fonction chaque fois qu’un élément OLE incorporé est activé pour la modification.  
  
 Cela est également appelée automatiquement avec le nom de document et le nom de l’application lorsqu’un objet est chargé ou lorsqu’un fichier est enregistré sous un nom différent. En conséquence, il n’est pas généralement nécessaire d’appeler directement cette fonction.  
  
 Pour plus d’informations, consultez [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="seticonicmetafile"></a>COleClientItem::SetIconicMetafile  
 Met en cache le métafichier utilisé pour dessiner l’icône de l’élément.  
  
```  
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```  
  
### <a name="parameters"></a>Paramètres  
 `hMetaPict`  
 Un handle de métafichier utilisé pour dessiner l’icône de l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Utilisez [GetIconicMetafile](#geticonicmetafile) pour récupérer le métafichier.  
  
 Le `hMetaPict` paramètre est copié dans l’élément ; par conséquent, `hMetaPict` doit être libérée par l’appelant.  
  
##  <a name="setitemrects"></a>COleClientItem::SetItemRects  
 Appelez cette fonction pour définir le rectangle ou le rectangle visible de l’élément OLE.  
  
```  
BOOL SetItemRects(
    LPCRECT lpPosRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *lprcPosRect*  
 Pointeur vers le rectangle contenant les limites de l’élément OLE par rapport à sa fenêtre parente, en coordonnées clientes.  
  
 *lprcClipRect*  
 Pointeur vers le rectangle contenant les limites de la partie visible de l’élément OLE par rapport à sa fenêtre parente, en coordonnées clientes.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée par l’implémentation par défaut de la [OnChangeItemPosition](#onchangeitemposition) fonction membre. Vous devez appeler cette fonction chaque fois que les modifications d’élément de la position ou la partie visible de l’OLE. En général, cela signifie que vous l’appelez à partir de votre vue [OnSize](../../mfc/reference/cwnd-class.md#onsize) et [OnScrollBy](../../mfc/reference/cview-class.md#onscrollby) les fonctions membres.  
  
 Pour plus d’informations, consultez [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setlinkupdateoptions"></a>COleClientItem::SetLinkUpdateOptions  
 Appelez cette fonction pour définir l’option de mise à jour de liaisons pour la présentation de l’élément lié spécifié.  
  
```  
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwUpdateOpt*  
 La valeur de l’option de mise à jour de liaisons pour cet élément. Cette valeur doit être une des opérations suivantes :  
  
- `OLEUPDATE_ALWAYS`Mettre à jour l’élément lié chaque fois que possible. Cette option prend en charge la case lien-mise à jour automatique dans la boîte de dialogue.  
  
- `OLEUPDATE_ONCALL`Mettre à jour l’élément lié uniquement à la demande de l’application conteneur (lorsque le [UpdateLink](#updatelink) la fonction membre est appelée). Cette option prend en charge la case lien-mise à jour manuelle dans la boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 En règle générale, vous ne devez pas modifier les options de mise à jour choisies par l’utilisateur dans la boîte de dialogue.  
  
 Pour plus d’informations, consultez [IOleLink::SetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680120) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setprintdevice"></a>COleClientItem::SetPrintDevice  
 Appelez cette fonction pour modifier le périphérique d’impression cible pour cet élément.  
  
```  
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL SetPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptd`  
 Pointeur vers un [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) structure de données qui contient des informations sur le nouveau périphérique d’impression cible. Peut être **NULL**.  
  
 `ppd`  
 Pointeur vers un [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646940) structure de données qui contient des informations sur le nouveau périphérique d’impression cible. Peut être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction met à jour le périphérique d’impression pour l’élément, mais elle n’actualise pas le cache de présentation. Pour mettre à jour le cache de présentation pour un élément, appelez [UpdateLink](#updatelink).  
  
 Les arguments de cette fonction contiennent des informations que le système OLE utilise pour identifier le périphérique cible. Le **PRINTDLG** structure contient des informations que Windows utilise pour initialiser la boîte de dialogue d’impression. Une fois que l’utilisateur ferme la boîte de dialogue, Windows renvoie des informations sur les sélections d’utilisateur dans cette structure. Le `m_pd` membre d’un [CPrintDialog](../../mfc/reference/cprintdialog-class.md) objet est un **PRINTDLG** structure.  
  
 Pour plus d’informations sur cette structure, consultez [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations, consultez [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="updatelink"></a>COleClientItem::UpdateLink  
 Appelez cette fonction pour mettre immédiatement à jour les données de présentation de l’élément OLE.  
  
```  
BOOL UpdateLink();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro en cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Pour les éléments liés, la fonction recherche la source de la liaison pour obtenir une présentation de l’élément OLE. Ce processus peut impliquer l’exécution d’une ou plusieurs applications de serveur, qui peuvent prendre du temps. Pour les éléments incorporés, la fonction opère de manière récursive, la vérification si l’élément incorporé contient des liens qui peuvent être obsolètes et les mettre à jour. L’utilisateur peut actualiser manuellement les liens à l’aide de la boîte de dialogue.  
  
 Pour plus d’informations, consultez [IOleLink::Update](http://msdn.microsoft.com/library/windows/desktop/ms692660) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC MFCBIND](../../visual-cpp-samples.md)   
 [Exemple MFC OCLIENT](../../visual-cpp-samples.md)   
 [CDocItem (classe)](../../mfc/reference/cdocitem-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe COleServerItem](../../mfc/reference/coleserveritem-class.md)

