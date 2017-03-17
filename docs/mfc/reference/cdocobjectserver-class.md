---
title: Classe de CDocObjectServer | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
dev_langs:
- C++
helpviewer_keywords:
- document object server
- CDocObjectServer class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 75fb0ba49d105a673e862ed3044e85ac9e990e9c
ms.lasthandoff: 02/24/2017

---
# <a name="cdocobjectserver-class"></a>CDocObjectServer (classe)
Implémente les interfaces OLE supplémentaires nécessaires pour transformer un serveur normal `COleDocument` en serveur DocObject complet : `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`et `IPrint`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Construit un objet `CDocObjectServer`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Active le serveur d’objet de document, mais ne sera pas affichée.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|Affiche la vue DocObject.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|Restaure l’état de la vue DocObject.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|Enregistre l’état de la vue DocObject.|  
  
## <a name="remarks"></a>Remarques  
 `CDocObjectServer`est dérivé `CCmdTarget` et travaille en étroite collaboration avec `COleServerDoc` pour exposer les interfaces.  
  
 Un document de serveur DocObject peut contenir [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) objets qui représentent l’interface serveur aux éléments de DocObject.  
  
 Pour personnaliser votre serveur DocObject, dérivez votre propre classe de `CDocObjectServer` et remplacer ses fonctions le programme d’installation de la vue, [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), et [OnSaveViewState](#onsaveviewstate). Vous devez fournir une nouvelle instance de votre classe en réponse aux appels de framework.  
  
 Pour plus d’informations sur DocObjects, consultez [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) et [COleCmdUI](../../mfc/reference/colecmdui-class.md) dans les *référence MFC*. Consultez également [Internet premières étapes : Documents actifs](../../mfc/active-documents-on-the-internet.md) et [Documents actifs](../../mfc/active-documents-on-the-internet.md).  
  
 Consultez également l’article suivant de la Base de connaissances :  
  
-   Q247382 : PRB : info-bulles pour les contrôles de serveur de Document ActiveX sont masqués par le conteneur de documents ActiveX  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdocob.h  
  
##  <a name="activatedocobject"></a>CDocObjectServer::ActivateDocObject  
 Appelez cette fonction pour activer (mais pas) le serveur d’objet de document.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Remarques  
 `ActivateDocObject`appels `IOleDocumentSite`de **ActivateMe** (méthode), mais n’affiche ne pas la vue, car il attend des instructions spécifiques sur la façon de configurer et afficher la vue, indiqué dans l’appel à [CDocObjectServer::OnActivateView](#onactivateview).  
  
 Ensemble, `ActivateDocObject` et `OnActivateView` activer et afficher la vue DocObject. DocObject activation diffère des autres types d’activation des OLE sur place. L’activation de DocObject contourne affichage in situ hachurage bordures et ornements d’objet (par exemple, des poignées de redimensionnement), ignore les fonctions de mesure d’objet et dessine des barres de défilement dans le rectangle d’affichage au lieu des faire glisser en dehors de ce rectangle (par exemple, l’activation sur place normal).  
  
##  <a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer  
 Construit et initialise un objet `CDocObjectServer`.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *pOwner*  
 Pointeur vers le document du site client qui est le client pour le serveur DocObject.  
  
 `pDocSite`  
 Un pointeur vers le `IOleDocumentSite` interface implémentée par le conteneur.  
  
### <a name="remarks"></a>Notes  
 Lorsqu’un DocObject est actif, le client du site OLE (interface) ( `IOleDocumentSite`) qui permet au serveur DocObject de communiquer avec son client (le conteneur). Lorsqu’un serveur DocObject est activé, il vérifie d’abord que le conteneur implémente la `IOleDocumentSite` interface. Dans ce cas, [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) est appelé pour déterminer si le conteneur prend en charge DocObjects. Par défaut, `GetDocObjectServer` retourne **NULL**. Vous devez substituer `COleServerDoc::GetDocObjectServer` pour construire une nouvelle `CDocObjectServer` objet ou un objet dérivé de votre choix, avec des pointeurs vers les `COleServerDoc` conteneur et ses `IOleDocumentSite` interface comme arguments au constructeur.  
  
##  <a name="onactivateview"></a>CDocObjectServer::OnActivateView  
 Appelez cette fonction pour afficher la vue DocObject.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une erreur ou une valeur d’avertissement. Par défaut, retourne **NOERROR** cas de réussite ; sinon, **E_FAIL**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction crée une fenêtre frame en place, dessine des barres de défilement dans la vue, configure les menus, le serveur partage avec son conteneur, ajoute les contrôles frame, définit l’objet actif, puis enfin présente la fenêtre frame en place et définit le focus.  
  
##  <a name="onapplyviewstate"></a>CDocObjectServer::OnApplyViewState  
 Remplacez cette fonction pour restaurer l’état de la vue DocObject.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Paramètres  
 `ar`  
 Un `CArchive` objet permettant de sérialiser l’état d’affichage.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée lorsque la vue est affichée pour la première fois après son instanciation. `OnApplyViewState`Indique une vue à se réinitialiser lui-même en fonction des données dans le `CArchive` objet précédemment enregistré avec [OnSaveViewState](#onsaveviewstate). La vue doit valider les données dans le `CArchive` de l’objet, car le conteneur n’essaie pas d’interpréter les données d’état de vue en aucune façon.  
  
 Vous pouvez utiliser `OnSaveViewState` pour stocker les informations persistantes spécifiques à l’état de votre affichage. Si vous substituez `OnSaveViewState` pour stocker les informations, vous pouvez substituer `OnApplyViewState` pour lire les informations et les appliquer à votre vue lorsqu’elle est qui vient d’être activée.  
  
##  <a name="onsaveviewstate"></a>CDocObjectServer::OnSaveViewState  
 Remplacez cette fonction pour enregistrer les informations d’état supplémentaires sur votre vue DocObject.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Paramètres  
 `ar`  
 Un `CArchive` de l’objet pour lequel l’état d’affichage est sérialisé.  
  
### <a name="remarks"></a>Remarques  
 L’état peut inclure des propriétés telles que le type d’affichage, facteur de zoom, l’insertion et point de sélection et ainsi de suite. En règle générale, le conteneur appelle cette fonction avant la désactivation de la vue. L’état enregistré peut être restaurée ultérieurement via [OnApplyViewState](#onapplyviewstate).  
  
 Vous pouvez utiliser `OnSaveViewState` pour stocker les informations persistantes spécifiques à l’état de votre affichage. Si vous substituez `OnSaveViewState` pour stocker les informations, vous pouvez substituer `OnApplyViewState` pour lire les informations et les appliquer à votre vue lorsqu’elle est qui vient d’être activée.  
  
## <a name="see-also"></a>Voir aussi  
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem (classe)](../../mfc/reference/cdocobjectserveritem-class.md)

