---
title: Classe de COleServerDoc | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
dev_langs:
- C++
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a636b07b73da6ded6fb1646b7efa30b4685e55ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="coleserverdoc-class"></a>Classe de COleServerDoc
Classe de base des documents serveur OLE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](#coleserverdoc)|Construit un objet `COleServerDoc`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](#activatedocobject)|Active le document DocObject associé.|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|Active le document pour modification sur place.|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Désactive l’interface d’utilisateur du serveur.|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|Ignore les informations d’état d’annulation.|  
|[COleServerDoc::GetClientSite](#getclientsite)|Récupère un pointeur vers l’objet sous-jacent `IOleClientSite` interface.|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Retourne un pointeur vers un élément qui représente l’ensemble du document.|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Retourne le rectangle de découpage en cours de modification sur place.|  
|[COleServerDoc::GetItemPosition](#getitemposition)|Retourne le rectangle de position actuelle, par rapport à la zone cliente de l’application conteneur, de modification sur place.|  
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Retourne le facteur de zoom en pixels.|  
|[COleServerDoc::IsDocObject](#isdocobject)|Détermine si le document est un DocObject.|  
|[COleServerDoc::IsEmbedded](#isembedded)|Indique si le document est en cours d’exécution autonome ou incorporé dans un document conteneur.|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Retourne `TRUE` si l’élément est actuellement activé sur place.|  
|[COleServerDoc::NotifyChanged](#notifychanged)|Notifie les conteneurs que l’utilisateur a modifié le document.|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|Notifie les conteneurs que l’utilisateur a fermé le document.|  
|[COleServerDoc::NotifyRename](#notifyrename)|Notifie les conteneurs que l’utilisateur a renommé le document.|  
|[COleServerDoc::NotifySaved](#notifysaved)|Notifie les conteneurs que l’utilisateur a enregistré le document.|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|Appelé par le framework lorsque l’utilisateur désactive un élément qui a été activé sur place.|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Appelé par l’infrastructure pour détruire des contrôles et autres éléments d’interface utilisateur créés pour l’activation sur place.|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Appelé par l’infrastructure lors de la fenêtre frame de document du conteneur est activée ou désactivée.|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Appelé par l’infrastructure lors de la fenêtre frame ou la fenêtre de document de l’application de conteneur est redimensionné.|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Appelé par l’infrastructure pour afficher ou masquer les barres de contrôles pour la modification sur place.|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Appelé par l’infrastructure lorsqu’un document serveur qui est un élément incorporé est enregistré, la mise à jour de la copie du conteneur de l’élément.|  
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Modifie la position de la frame de modification sur place.|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|Indique à l’application conteneur pour enregistrer le document.|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Fait défiler le document conteneur.|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|Notifie les conteneurs que l’utilisateur a modifié le document.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Appelé par l’infrastructure pour créer une fenêtre frame de modification sur place.|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Appelé par l’infrastructure pour détruire une fenêtre frame de modification sur place.|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Remplacez cette fonction pour créer un nouveau `CDocObjectServer` de l’objet et d’indiquer que ce document est un conteneur DocObject.|  
|[COleServerDoc::OnClose](#onclose)|Appelé par l’infrastructure lors de la demande d’un conteneur pour fermer le document.|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Exécute une commande spécifiée ou affiche l’aide de la commande.|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Appelé par l’infrastructure lors de la fenêtre de frame du conteneur est activée ou désactivée.|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Appelé pour obtenir un `COleServerItem` qui représente le document entier ; utilisée pour obtenir un élément incorporé. Implémentation requise.|  
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Appelé par l’infrastructure pour annuler les modifications apportées au cours de la modification sur place.|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Appelé par l’infrastructure lorsqu’un conteneur définit le titre de fenêtre pour un objet incorporé.|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Appelé par l’infrastructure pour positionner la fenêtre frame de modification sur place dans la fenêtre de l’application conteneur.|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|Appelé par l’infrastructure pour afficher ou masquer le document.|  
  
## <a name="remarks"></a>Notes  
 Un document serveur peut contenir [COleServerItem](../../mfc/reference/coleserveritem-class.md) objets qui représentent l’interface du serveur pour les éléments liés ou incorporés. Lorsqu’une application serveur est lancée par un conteneur pour modifier un élément incorporé, l’élément est chargé comme son propre document serveur ; le `COleServerDoc` objet contient un seul `COleServerItem` objet, qui se compose de l’ensemble du document. Lorsqu’une application serveur est lancée par un conteneur pour modifier un élément lié, un document existant est chargé à partir du disque ; une partie du contenu du document est mis en surbrillance pour indiquer que l’élément lié.  
  
 `COleServerDoc` objets peuvent également contenir des éléments de la [COleClientItem](../../mfc/reference/coleclientitem-class.md) classe. Cela vous permet de créer des applications de conteneur-serveur. Le framework fournit des fonctions pour stocker correctement les `COleClientItem` éléments lors de la maintenance du `COleServerItem` objets.  
  
 Si votre application serveur ne prend pas en charge les liens, un document serveur contiendra toujours qu’un seul élément du serveur, qui représente l’objet incorporé entier sous forme de document. Si votre application serveur ne prend pas en charge les liens, il doit créer un élément de serveur chaque fois qu’une sélection est copiée dans le Presse-papiers.  
  
 Pour utiliser `COleServerDoc`, dériver une classe et implémenter la [OnGetEmbeddedItem](#ongetembeddeditem) fonction membre, ce qui permet à votre serveur prendre en charge les éléments incorporés. Dérivez une classe de `COleServerItem` pour implémenter les éléments de vos documents et retournent des objets de cette classe à partir de `OnGetEmbeddedItem`.  
  
 Pour prendre en charge les éléments liés, `COleServerDoc` fournit le [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) fonction membre. Vous pouvez utiliser l’implémentation par défaut ou remplacer si vous avez votre propre méthode de gestion des éléments de document.  
  
 Vous devez installer un `COleServerDoc`-pour chaque type de serveur de document de votre application prend en charge la classe dérivée. Par exemple, si votre application serveur prend en charge les feuilles de calcul et des graphiques, vous avez besoin de deux `COleServerDoc`-classes dérivées.  
  
 Pour plus d’informations sur les serveurs, consultez l’article [serveurs : implémentation d’un serveur](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc plutôt](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="activatedocobject"></a>  COleServerDoc::ActivateDocObject  
 Active le document DocObject associé.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Notes  
 Par défaut, `COleServerDoc` ne prend pas en charge les documents actifs (également appelés DocObjects). Pour activer cette prise en charge, consultez [GetDocObjectServer](#getdocobjectserver) et classe [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).  
  
##  <a name="activateinplace"></a>  COleServerDoc::ActivateInPlace  
 Active l’élément pour la modification sur place.  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0, qui indique que l’élément est complètement ouvert.  
  
### <a name="remarks"></a>Notes  
 Cette fonction effectue toutes les opérations nécessaires pour l’activation sur place. Crée une fenêtre frame en place, il active et redimensionne à l’élément, définit les menus partagés et autres contrôles, fait défiler l’élément dans la vue et définit le focus à la fenêtre frame en place.  
  
 Cette fonction est appelée par l’implémentation par défaut de [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Appelez cette fonction si votre application prend en charge un autre verbe pour l’activation sur place (par exemple, lecture).  
  
##  <a name="coleserverdoc"></a>  COleServerDoc::COleServerDoc  
 Construit un `COleServerDoc` objet sans établir de connexion avec les DLL système OLE.  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) pour ouvrir des communications avec OLE. Si vous utilisez [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) dans votre application, `COleLinkingDoc::Register` est appelée pour vous par `COleLinkingDoc`d’implémentation de `OnNewDocument`, `OnOpenDocument`, et `OnSaveDocument`.  
  
##  <a name="createinplaceframe"></a>  COleServerDoc::CreateInPlaceFrame  
 L’infrastructure appelle cette fonction pour créer une fenêtre frame de modification sur place.  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointeur vers la fenêtre parente de l’application conteneur.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la fenêtre frame en place, ou **NULL** en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut utilise les informations spécifiées dans le modèle de document pour créer le frame. La vue utilisée est la première vue créée pour le document. Cette vue est temporairement détachée de l’image d’origine et attachée au frame nouvellement créé.  
  
 Il s’agit d’une avancée substituable.  
  
##  <a name="deactivateandundo"></a>  COleServerDoc::DeactivateAndUndo  
 Appelez cette fonction si votre application prend en charge annule et que l’utilisateur choisit d’annuler après l’activation d’un élément, mais avant de le modifier.  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro en cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Si l’application conteneur est écrit à l’aide de la bibliothèque Microsoft Foundation Class, appel de cette fonction provoque [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) pour être appelée, ce qui désactive l’interface d’utilisateur du serveur.  
  
##  <a name="destroyinplaceframe"></a>  COleServerDoc::DestroyInPlaceFrame  
 L’infrastructure appelle cette fonction pour détruire une fenêtre frame en place et renvoyer le serveur de fenêtre de document de l’application à son état avant l’activation sur place.  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pFrameWnd`  
 Pointeur vers la fenêtre frame en place le point d’être détruit.  
  
### <a name="remarks"></a>Notes  
 Il s’agit d’une avancée substituable.  
  
##  <a name="discardundostate"></a>  COleServerDoc::DiscardUndoState  
 Si l’utilisateur effectue une opération de modification qui ne peut pas être annulée, appelez cette fonction pour forcer l’application conteneur pour ignorer les informations d’état d’annulation.  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro en cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est fournie afin que les serveurs qui prennent en charge d’annulation peuvent libérer des ressources qui sont autrement consommées par les informations d’état d’annulation qui ne peut pas être utilisées.  
  
##  <a name="getclientsite"></a>  COleServerDoc::GetClientSite  
 Récupère un pointeur vers l’objet sous-jacent `IOleClientSite` interface.  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Récupère un pointeur vers l’objet sous-jacent [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706) interface.  
  
##  <a name="getdocobjectserver"></a>  COleServerDoc::GetDocObjectServer  
 Remplacez cette fonction pour créer un nouveau `CDocObjectServer` d’élément et retournent un pointeur vers elle.  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDocSite`  
 Pointeur vers le `IOleDocumentSite` interface que ce document se connectera au serveur.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CDocObjectServer`; **NULL** si l’opération a échoué.  
  
### <a name="remarks"></a>Notes  
 Quand un serveur DocObject est activé, le retour d’un **NULL** pointeur indique que le client peut prendre en charge DocObjects. L’implémentation par défaut retourne **NULL**.  
  
 Une implémentation classique pour un document qui prend en charge DocObjects simplement alloue un nouveau `CDocObjectServer` de l’objet et le retourner à l’appelant. Par exemple :  
  
 [!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="getembeddeditem"></a>  COleServerDoc::GetEmbeddedItem  
 Appelez cette fonction pour obtenir un pointeur vers un élément qui représente l’ensemble du document.  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un élément qui représente l’ensemble du document ; **NULL** si l’opération a échoué.  
  
### <a name="remarks"></a>Notes  
 Il appelle [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), une fonction virtuelle avec aucune implémentation par défaut.  
  
##  <a name="getitemcliprect"></a>  COleServerDoc::GetItemClipRect  
 Appelez le `GetItemClipRect` fonction membre pour obtenir les coordonnées du rectangle de découpage de l’élément qui est en cours de modification en place.  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpClipRect`  
 Pointeur vers un `RECT` structure ou un `CRect` objet pour recevoir les coordonnées du rectangle de découpage de l’élément.  
  
### <a name="remarks"></a>Notes  
 Coordonnées sont exprimées en pixels par rapport à la zone cliente de la fenêtre d’application de conteneur.  
  
 Dessin ne doit pas avoir lieu en dehors du rectangle de découpage. En règle générale, le dessin est automatiquement limité. Utilisez cette fonction pour déterminer si l’utilisateur a atteint en dehors de la partie visible du document ; Dans ce cas, faites défiler le document conteneur en fonction des besoins au moyen d’un appel à [ScrollContainerBy](#scrollcontainerby).  
  
##  <a name="getitemposition"></a>  COleServerDoc::GetItemPosition  
 Appelez le `GetItemPosition` fonction membre pour obtenir les coordonnées de l’élément en cours de modification en place.  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpPosRect`  
 Pointeur vers un `RECT` structure ou un `CRect` objet pour recevoir les coordonnées de l’élément.  
  
### <a name="remarks"></a>Notes  
 Coordonnées sont exprimées en pixels par rapport à la zone cliente de la fenêtre d’application de conteneur.  
  
 Position de l’élément peut être comparée avec le rectangle de découpage en cours pour déterminer l’étendue à laquelle l’élément est visible (ou n’est pas visible) sur l’écran.  
  
##  <a name="getzoomfactor"></a>  COleServerDoc::GetZoomFactor  
 Le `GetZoomFactor` fonction membre détermine le facteur de zoom « » d’un élément qui a été activé pour la modification sur place.  
  
```  
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,  
    LPSIZE lpSizeDenom = NULL,  
    LPCRECT lpPosRect = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *lpSizeNum*  
 Pointeur vers un objet de classe `CSize` qui contiendra les numérateur du facteur de zoom. Peut être **NULL**.  
  
 *lpSizeDenom*  
 Pointeur vers un objet de classe `CSize` qui contiendra le dénominateur du facteur de zoom. Peut être **NULL**.  
  
 `lpPosRect`  
 Pointeur vers un objet de classe `CRect` qui décrit la nouvelle position. Si cet argument est **NULL**, la fonction utilise la position actuelle de l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément est activé sur place pour les modifier et le facteur de zoom est autre que 100 % (1:1) ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Le facteur de zoom, en pixels, est la proportion de la taille de l’élément à son étendue actuelle. Si l’application conteneur n’a pas défini la mesure où l’élément, son extension naturelle (comme déterminé par [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) est utilisé.  
  
 La fonction définit les deux premiers arguments pour le numérateur et dénominateur de « facteur de zoom » de l’élément. Si l’élément n’est pas modifié sur place, la fonction définit ces arguments à une valeur par défaut de 100 % (ou 1:1) et retourne la valeur zéro. Pour plus d’informations, consultez Technical Note 40, [redimensionnement sur Place MFC/OLE et le zoom](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
##  <a name="isdocobject"></a>  COleServerDoc::IsDocObject  
 Détermine si le document est un DocObject.  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si le document est DocObject ; sinon **FALSE**.  
  
##  <a name="isembedded"></a>  COleServerDoc::IsEmbedded  
 Appelez le `IsEmbedded` fonction membre pour déterminer si le document représente un objet incorporé dans un conteneur.  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la `COleServerDoc` objet est un document qui représente un objet incorporé dans un conteneur ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Un document chargé à partir d’un fichier n’est pas incorporé même si elles peuvent être manipulées par une application conteneur en tant que lien. Un document qui est incorporé dans un document conteneur est considéré comme devant être incorporée.  
  
##  <a name="isinplaceactive"></a>  COleServerDoc::IsInPlaceActive  
 Appelez le `IsInPlaceActive` fonction membre pour déterminer si l’élément est actuellement dans l’état actif sur place.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la `COleServerDoc` objet est actif en place ; sinon, 0.  
  
##  <a name="notifychanged"></a>  COleServerDoc::NotifyChanged  
 Appelez cette fonction pour notifier tous les éléments liés connectés au document que le document a été modifié.  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>Notes  
 En règle générale, vous appelez cette fonction une fois que l’utilisateur modifie des attributs globaux tels que les dimensions du document serveur. Si un élément OLE est lié au document avec un lien automatique, l’élément est mis à jour pour refléter les modifications. Dans les applications conteneur écrites avec la bibliothèque Microsoft Foundation Class, le [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) fonction membre de `COleClientItem` est appelée.  
  
> [!NOTE]
>  Cette fonction est incluse pour la compatibilité avec OLE 1. Nouvelles applications doivent utiliser [UpdateAllItems](#updateallitems).  
  
##  <a name="notifyclosed"></a>  COleServerDoc::NotifyClosed  
 Appelez cette fonction pour avertir les conteneurs que le document a été fermé.  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>Notes  
 Lorsque l’utilisateur choisit la commande Fermer dans le menu fichier, `NotifyClosed` est appelée par `COleServerDoc`d’implémentation de la [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) fonction membre. Dans les applications conteneur écrites avec la bibliothèque Microsoft Foundation Class, le [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) fonction membre de `COleClientItem` est appelée.  
  
##  <a name="notifyrename"></a>  COleServerDoc::NotifyRename  
 Appelez cette fonction une fois que l’utilisateur renomme le document serveur.  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszNewName`  
 Pointeur vers une chaîne qui spécifie le nouveau nom du document serveur ; Il s’agit généralement d’un chemin d’accès qualifié complet.  
  
### <a name="remarks"></a>Notes  
 Lorsque l’utilisateur choisit la commande Enregistrer sous dans le menu fichier, `NotifyRename` est appelée par `COleServerDoc`d’implémentation de la [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) fonction membre. Cette fonction notifie le système OLE DLL, qui à son tour notifier les conteneurs. Dans les applications conteneur écrites avec la bibliothèque Microsoft Foundation Class, le [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) fonction membre de `COleClientItem` est appelée.  
  
##  <a name="notifysaved"></a>  COleServerDoc::NotifySaved  
 Appelez cette fonction une fois que l’utilisateur enregistre le document serveur.  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>Notes  
 Lorsque l’utilisateur choisit la commande Enregistrer dans le menu fichier, `NotifySaved` est appelée pour vous par `COleServerDoc`d’implémentation de [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Cette fonction notifie le système OLE DLL, qui à son tour notifier les conteneurs. Dans les applications conteneur écrites avec la bibliothèque Microsoft Foundation Class, le [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) fonction membre de `COleClientItem` est appelée.  
  
##  <a name="onclose"></a>  COleServerDoc::OnClose  
 Appelé par l’infrastructure lorsqu’un conteneur demande que le document serveur soit fermée.  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwCloseOption`  
 Une valeur de l’énumération `OLECLOSE`. Ce paramètre peut prendre l'une des valeurs suivantes :  
  
- `OLECLOSE_SAVEIFDIRTY` Le fichier est enregistré s’il a été modifié.  
  
- `OLECLOSE_NOSAVE` Le fichier est fermé sans être enregistré.  
  
- `OLECLOSE_PROMPTSAVE` Si le fichier a été modifié, l’utilisateur est invité à l’enregistrer.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut appelle `CDocument::OnCloseDocument`.  
  
 Pour plus d’informations et des valeurs supplémentaires, consultez [OLECLOSE](http://msdn.microsoft.com/library/windows/desktop/ms680623) dans le Kit de développement logiciel Windows.  
  
##  <a name="ondeactivate"></a>  COleServerDoc::OnDeactivate  
 Appelé par le framework lorsque l’utilisateur désactive un élément incorporé ou lié qui est actif actuellement en place.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction restaure l’interface utilisateur de l’application conteneur à son état d’origine et détruit tous les menus et autres contrôles qui ont été créés pour l’activation sur place.  
  
 Les informations d’état de restauration doivent être libérées de manière inconditionnelle à ce stade.  
  
 Pour plus d’informations, consultez l’article [Activation](../../mfc/activation-cpp.md)...  
  
##  <a name="ondeactivateui"></a>  COleServerDoc::OnDeactivateUI  
 Appelé lorsque l’utilisateur désactive un élément qui a été activé sur place.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Paramètres  
 `bUndoable`  
 Spécifie si des modifications peuvent être annulées.  
  
### <a name="remarks"></a>Notes  
 Cette fonction restaure l’interface utilisateur de l’application conteneur à son état d’origine, le masquage des menus et autres contrôles qui ont été créés pour l’activation sur place.  
  
 Le framework définit toujours `bUndoable` à **FALSE**. Si le serveur prend en charge l’annulation et qu’une opération qui peut être annulée, appelez l’implémentation de classe de base avec `bUndoable` la valeur **TRUE**.  
  
##  <a name="ondocwindowactivate"></a>  COleServerDoc::OnDocWindowActivate  
 L’infrastructure appelle cette fonction pour activer ou désactiver une fenêtre de document pour modification sur place.  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Paramètres  
 `bActivate`  
 Spécifie si la fenêtre de document doit être activée ou désactivée.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut supprime ou ajoute les éléments d’interface utilisateur au niveau du frame comme il convient. Remplacez cette fonction si vous souhaitez effectuer des actions supplémentaires lorsque le document qui contient votre élément est activé ou désactivé.  
  
 Pour plus d’informations, consultez l’article [Activation](../../mfc/activation-cpp.md)...  
  
##  <a name="onexecolecmd"></a>  COleServerDoc::OnExecOleCmd  
 L’infrastructure appelle cette fonction pour exécuter une commande spécifiée ou affiche l’aide de la commande.  
  
```  
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,  
    DWORD nCmdID,  
    DWORD nCmdExecOpt,  
    VARIANTARG* pvarargIn,  
    VARIANTARG* pvarargOut);
```  
  
### <a name="parameters"></a>Paramètres  
 `pguidCmdGroup`  
 Pointeur vers un GUID qui identifie un ensemble de commandes. Peut être **NULL** pour indiquer le groupe de commandes par défaut.  
  
 `nCmdID`  
 La commande à exécuter. Doit être dans le groupe identifié par `pguidCmdGroup`.  
  
 *nCmdExecOut*  
 Le moyen de l’objet doit exécuter la commande, la valeur d’un ou plusieurs des valeurs suivantes à partir de la **OLECMDEXECOPT** énumération :  
  
 **OLECMDEXECOPT_DODEFAULT**  
  
 **OLECMDEXECOPT_PROMPTUSER**  
  
 **OLECMDEXECOPT_DONTPROMPTUSER**  
  
 **OLECMDEXECOPT_SHOWHELP**  
  
 `pvarargIn`  
 Pointeur vers un **VARIANTARG** contenant les arguments d’entrée pour la commande. Peut être **NULL**.  
  
 `pvarargOut`  
 Pointeur vers un **VARIANTARG** pour recevoir les valeurs de retour de sortie de la commande. Peut être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` cas de réussite ; sinon, un des codes d’erreur suivants :  
  
|Value|Description|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Une erreur inattendue s’est produite|  
|**E_FAIL**|Erreur s’est produite|  
|**E_NOTIMPL**|Indique les MFC elle-même doit tenter de traduction et de distribuer la commande|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup` est non - **NULL** mais ne spécifie ne pas un groupe de commandes reconnu|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID` n’est pas reconnu comme une commande valide dans le groupe `pguidCmdGroup`|  
|**OLECMDERR_DISABLED**|La commande identifiée par `nCmdID` est désactivé et ne peut pas être exécutée.|  
|**OLECMDERR_NOHELP**|L’appelant a demandé de l’aide sur la commande identifiée par `nCmdID` mais aucune aide n’est disponible|  
|**OLECMDERR_CANCELED**|L’utilisateur a annulé l’exécution|  
  
### <a name="remarks"></a>Notes  
 `COleCmdUI` peut être utilisé pour activer, de mettre à jour et de définir d’autres propriétés de commandes d’interface utilisateur de DocObject. Une fois que les commandes sont initialisés, vous pouvez les exécuter avec `OnExecOleCmd`.  
  
 L’infrastructure appelle la fonction avant de tenter de traduire et distribuer une commande de document OLE. Vous n’avez pas besoin de substituer cette fonction pour gérer les commandes de document OLE standard, mais vous devez fournir un remplacement pour cette fonction si vous souhaitez gérer vos propres commandes personnalisées ou de gérer les commandes qui acceptent des paramètres ou de retournent des résultats.  
  
 La plupart des commandes n’acceptent des arguments et valeurs de retour. Pour la plupart des commandes de l’appelant peut transmettre **NULL**s pour `pvarargIn` et `pvarargOut`. Pour les commandes qui attendent des valeurs d’entrée, l’appelant peut déclarer et initialiser un **VARIANTARG** variable et passer un pointeur vers la variable dans `pvarargIn`. Pour les commandes qui nécessitent une seule valeur, l’argument peut être stocké directement dans le **VARIANTARG** et passé à la fonction. Plusieurs arguments doivent être empaquetées dans le **VARIANTARG** à l’aide d’un des types pris en charge (tels que `IDispatch` et **SAFEARRAY** ).  
  
 De même, si une commande retourne les arguments de l’appelant doit déclarer un **VARIANTARG**, initialisez-le à `VT_EMPTY`et passer son adresse dans `pvarargOut`. Si une commande retourne une valeur unique, l’objet peut stocker cette valeur directement dans `pvarargOut`. Plusieurs valeurs de sortie doivent être empaquetées d’une certaine façon appropriée pour le **VARIANTARG**.  
  
 L’implémentation de classe de base de cette fonction aidera les **OLE_COMMAND_MAP** structures associées à la cible de la commande et essayez de distribuer la commande pour un gestionnaire approprié. L’implémentation de classe de base fonctionne uniquement avec les commandes qui ne puissent pas accepter des arguments ou les valeurs de retour. Si vous avez besoin gérer les commandes qui retournent des valeurs ou n’accepter des arguments, vous devez substituer cette fonction et travailler avec les `pvarargIn` et `pvarargOut` paramètres vous-même.  
  
##  <a name="onframewindowactivate"></a>  COleServerDoc::OnFrameWindowActivate  
 L’infrastructure appelle cette fonction lorsque la fenêtre frame de l’application conteneur est activée ou désactivée.  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Paramètres  
 `bActivate`  
 Spécifie si la fenêtre frame doit être activée ou désactivée.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut annule la fenêtre frame peut être dans n’importe quel modes d’aide. Remplacez cette fonction si vous souhaitez exécuter un traitement spécial lors de la fenêtre frame est activée ou désactivée.  
  
 Pour plus d’informations, consultez l’article [Activation](../../mfc/activation-cpp.md)...  
  
##  <a name="ongetembeddeditem"></a>  COleServerDoc::OnGetEmbeddedItem  
 Appelé par le framework lorsqu’une application conteneur appelle l’application de serveur pour créer ou modifier un élément incorporé.  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un élément qui représente l’ensemble du document ; **NULL** si l’opération a échoué.  
  
### <a name="remarks"></a>Notes  
 Il n'y a pas d'implémentation par défaut. Vous devez substituer cette fonction pour retourner un élément qui représente l’ensemble du document. Cette valeur de retour doit être un objet d’un `COleServerItem`-classe dérivée.  
  
##  <a name="onreactivateandundo"></a>  COleServerDoc::OnReactivateAndUndo  
 L’infrastructure appelle cette fonction lorsque l’utilisateur choisit d’annuler les modifications apportées à un élément qui a été activé sur place, modifié et par la suite désactivé.  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut n’exécute aucune opération à l’exception de retour **FALSE** pour indiquer un échec.  
  
 Remplacez cette fonction si votre application prend en charge l’annulation. Généralement, vous devez effectuer l’opération d’annulation, puis activer l’élément en appelant `ActivateInPlace`. Si l’application conteneur est écrit avec la bibliothèque Microsoft Foundation Class, l’appel `COleClientItem::ReactivateAndUndo` , cette fonction à appeler.  
  
##  <a name="onresizeborder"></a>  COleServerDoc::OnResizeBorder  
 L’infrastructure appelle cette fonction lorsque les fenêtres frame de l’application conteneur changent de taille.  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRectBorder`  
 Pointeur vers un `RECT` structure ou un `CRect` objet qui spécifie les coordonnées de la bordure.  
  
 `lpUIWindow`  
 Pointeur vers un objet de classe **IOleInPlaceUIWindow** qui est propriétaire de la session de modification sur place.  
  
 *bFrame*  
 **TRUE** si `lpUIWindow` pointe vers la fenêtre frame de niveau supérieur de l’application conteneur, ou **FALSE** si `lpUIWindow` pointe vers la fenêtre frame d’au niveau du document de l’application conteneur.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est redimensionné et ajuste les barres d’outils et autres éléments d’interface utilisateur conformément à la nouvelle taille de fenêtre.  
  
 Pour plus d’informations, consultez [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) dans le Kit de développement logiciel Windows.  
  
 Il s’agit d’une avancée substituable.  
  
##  <a name="onsethostnames"></a>  COleServerDoc::OnSetHostNames  
 Appelé par le framework lorsque le conteneur définit ou modifie les noms d’hôte pour ce document.  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszHost`  
 Pointeur vers une chaîne qui spécifie le nom de l’application conteneur.  
  
 `lpszHostObj`  
 Pointeur vers une chaîne qui spécifie le nom du conteneur pour le document.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut modifie le titre du document pour toutes les vues faisant référence à ce document.  
  
 Remplacez cette fonction si votre application définit les titres via un mécanisme différent.  
  
##  <a name="onsetitemrects"></a>  COleServerDoc::OnSetItemRects  
 L’infrastructure appelle cette fonction afin de positionner la fenêtre frame de modification sur place dans la fenêtre frame de l’application conteneur.  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpPosRect`  
 Pointeur vers un `RECT` structure ou un `CRect` objet qui spécifie la position de la fenêtre frame en place par rapport à la zone cliente de l’application conteneur.  
  
 `lpClipRect`  
 Pointeur vers un `RECT` structure ou un `CRect` objet qui spécifie le rectangle de découpage de la fenêtre frame en place par rapport à la zone cliente de l’application conteneur.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction pour mettre à jour le facteur de zoom de la vue, si nécessaire.  
  
 Cette fonction est généralement appelée en réponse à une `RequestPositionChange` appeler, même si elle peut être appelée à tout moment par le conteneur pour demander une modification de la position de l’élément en place.  
  
##  <a name="onshowcontrolbars"></a>  COleServerDoc::OnShowControlBars  
 L’infrastructure appelle cette fonction pour afficher ou masquer les barres de contrôles de l’application serveur associés à la fenêtre frame identifiée par `pFrameWnd`.  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 `pFrameWnd`  
 Pointeur vers la fenêtre frame dont les barres de contrôle doivent être masqués ou affichés.  
  
 `bShow`  
 Détermine si les barres de contrôles sont affichés ou masqués.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut énumère toutes les barres de contrôles appartenant à cette fenêtre frame et affiche ou masque les.  
  
##  <a name="onshowdocument"></a>  COleServerDoc::OnShowDocument  
 Le framework appelle la `OnShowDocument` fonctionner lorsque le document serveur doit être masqué ou affiché.  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 `bShow`  
 Spécifie si l’interface utilisateur pour le document doit être affichée ou masquée.  
  
### <a name="remarks"></a>Notes  
 Si `bShow` est **TRUE**, l’implémentation par défaut active l’application serveur, si nécessaire et entraîne l’application de conteneur faire défiler la fenêtre afin que l’élément est visible. Si `bShow` est **FALSE**, l’implémentation par défaut désactive l’élément via un appel à `OnDeactivate`, puis détruit ou masque toutes les fenêtres frame qui ont été créés pour le document, sauf la première. Si aucun document n’est visible est conservé, l’implémentation par défaut masque l’application serveur.  
  
##  <a name="onupdatedocument"></a>  COleServerDoc::OnUpdateDocument  
 Appelé par l’infrastructure lors de l’enregistrement d’un document qui est un élément incorporé dans un document composé.  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le document a été correctement mis à jour ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut appelle la [COleServerDoc::NotifySaved](#notifysaved) et [COleServerDoc::SaveEmbedding](#saveembedding) les fonctions de membre et marque ensuite le document en tant que nouvelle. Remplacez cette fonction si vous souhaitez effectuer un traitement lors de la mise à jour d’un élément incorporé particulier.  
  
##  <a name="requestpositionchange"></a>  COleServerDoc::RequestPositionChange  
 Appelez cette fonction membre pour que l’application conteneur de modifier la position de l’élément.  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpPosRect`  
 Pointeur vers un `RECT` structure ou un `CRect` objet contenant la nouvelle position.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est généralement appelée (conjointement avec `UpdateAllItems`) lorsque les données dans un élément actif sur place a changé. Après cet appel, le conteneur peut ou peut ne pas exécuter la modification en appelant `OnSetItemRects`. La position résultante peut être différente de celle demandée.  
  
##  <a name="saveembedding"></a>  COleServerDoc::SaveEmbedding  
 Appelez cette fonction pour indiquer à l’application conteneur pour enregistrer l’objet incorporé.  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction est appelée automatiquement à partir de `OnUpdateDocument`. Notez que cette fonction provoque l’élément à mettre à jour sur le disque, elle est généralement appelée uniquement à la suite d’une action utilisateur spécifique.  
  
##  <a name="scrollcontainerby"></a>  COleServerDoc::ScrollContainerBy  
 Appelez le `ScrollContainerBy` fonction membre pour faire défiler le document conteneur par la quantité, en pixels, indiquée par `sizeScroll`.  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>Paramètres  
 `sizeScroll`  
 Indique la distance séparant le document conteneur est à faire défiler.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Les valeurs positives indiquent le défilement vers le bas et vers la droite. les valeurs négatives indiquent le défilement de haut et vers la gauche.  
  
##  <a name="updateallitems"></a>  COleServerDoc::UpdateAllItems  
 Appelez cette fonction pour notifier tous les éléments liés connectés au document que le document a été modifié.  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSender`  
 Pointeur vers l’élément qui a modifié le document, ou **NULL** si tous les éléments doivent être mis à jour.  
  
 `lHint`  
 Contient des informations sur la modification.  
  
 `pHint`  
 Pointeur vers un objet stockant les informations sur la modification.  
  
 `nDrawAspect`  
 Détermine la façon dont l’élément doit être dessiné. Il s’agit d’une valeur à partir de la `DVASPECT` énumération. Ce paramètre peut prendre l'une des valeurs suivantes :  
  
- `DVASPECT_CONTENT` Élément est représenté de façon à ce qu’il peut être affiché en tant qu’objet incorporé à l’intérieur de son conteneur.  
  
- `DVASPECT_THUMBNAIL` Élément est rendu dans une représentation sous forme de « miniature » afin qu’il peut être affiché dans un outil de navigation.  
  
- `DVASPECT_ICON` Élément est représenté par une icône.  
  
- `DVASPECT_DOCPRINT` Élément est représenté comme s’il était imprimé à l’aide de la commande Imprimer dans le menu fichier.  
  
### <a name="remarks"></a>Notes  
 En règle générale, vous appelez cette fonction une fois que l’utilisateur modifie le document serveur. Si un élément OLE est lié au document avec un lien automatique, l’élément est mis à jour pour refléter les modifications. Dans les applications conteneur écrites avec la bibliothèque Microsoft Foundation Class, le [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) fonction membre de `COleClientItem` est appelée.  
  
 Cette fonction appelle le `OnUpdate` fonction membre pour chacun des éléments du document à l’exception de l’envoi, passage `pHint`, `lHint`, et `nDrawAspect`. Utilisez ces paramètres pour passer des informations sur les éléments sur les modifications apportées au document. Vous pouvez encoder à l’aide des informations `lHint` ou vous pouvez définir un `CObject`-classe dérivée stockent des informations sur les modifications et passer un objet de classe à l’aide `pHint`. Remplacer la `OnUpdate` fonction membre dans votre `COleServerItem`-classe pour optimiser la mise à jour de chaque élément selon qu’a modifié sa présentation dérivée.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC HIERSVR](../../visual-cpp-samples.md)   
 [Classe de COleLinkingDoc plutôt](../../mfc/reference/colelinkingdoc-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDocument (classe)](../../mfc/reference/coledocument-class.md)   
 [Classe de COleLinkingDoc plutôt](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer, classe](../../mfc/reference/coletemplateserver-class.md)
