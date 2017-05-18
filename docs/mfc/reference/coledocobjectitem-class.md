---
title: Classe COleDocObjectItem | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
dev_langs:
- C++
helpviewer_keywords:
- COleDocObjectItem class
- document object containment
- containment
- containment, doc object
- doc object containment
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0815454fa4b194e97a2d16a621cfc25da61d5fd0
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="coledocobjectitem-class"></a>Classe COleDocObjectItem
Implémente la relation contenant-contenu de document actif.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Construit un `COleDocObject` élément.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Imprime le document de l’application conteneur en utilisant les paramètres d’imprimante par défaut.|  
|[COleDocObjectItem::ExecCommand](#execcommand)|Exécute la commande spécifiée par l’utilisateur.|  
|[COleDocObjectItem::GetActiveView](#getactiveview)|Récupère le mode du document actif.|  
|[COleDocObjectItem::GetPageCount](#getpagecount)|Récupère le nombre de pages dans le document de l’application conteneur.|  
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|Prépare le document de l’application conteneur pour l’impression.|  
|[COleDocObjectItem::OnPrint](#onprint)|Imprime le document de l’application conteneur.|  
|[COleDocObjectItem::QueryCommand](#querycommand)|Demande l’état d’une ou plusieurs commandes générées par des événements d’interface utilisateur.|  
|[COleDocObjectItem::Release](#release)|Libère la connexion à un élément lié OLE et la ferme si elle a été ouvert. Ne supprime pas l’élément client.|  
  
## <a name="remarks"></a>Remarques  
 Dans MFC, un document actif est confiée à un standard, place modifiable l’incorporation, avec les différences suivantes :  
  
-   Le `COleDocument`-classe dérivée conserve une liste des éléments actuellement incorporés ; Toutefois, ces éléments peuvent être `COleDocObjectItem`-éléments dérivés.  
  
-   Lorsqu’un document actif est actif, qu’il occupe la zone client entière de la vue lorsqu’il est actif sur place.  
  
-   Un conteneur de documents actifs possède le contrôle total de la **aide** menu.  
  
-   Le **aide** menu contient des éléments de menu pour le conteneur de documents actifs et le serveur.  
  
 Étant donné que le conteneur de documents actifs détient le **aide** menu, le conteneur est chargé pour le serveur de transfert **aide** messages de menu sur le serveur. Cette intégration est gérée par `COleDocObjectItem`.  
  
 Pour plus d’informations sur la fusion de menus et de l’activation du document actif, consultez Vue d’ensemble de [relation contenant-contenu de Document actif](../../mfc/active-document-containment.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="coledocobjectitem"></a>COleDocObjectItem::COleDocObjectItem  
 Appelez cette fonction membre pour initialiser le `COleDocObjectItem` objet.  
  
```  
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pContainerDoc`  
 Un pointeur vers le `COleDocument` objet agissant en tant que le conteneur de documents actifs. Ce paramètre doit être **NULL** pour activer **IMPLEMENT_SERIALIZE**. Normalement les éléments OLE sont construits avec un non - **NULL** pointeur de document.  
  
##  <a name="dodefaultprinting"></a>COleDocObjectItem::DoDefaultPrinting  
 Appelée par l’infrastructure pour un document en utilisant les paramètres par défaut.  
  
```  
static HRESULT DoDefaultPrinting(
    CView* pCaller,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCaller`  
 Un pointeur vers un [CView](../../mfc/reference/cview-class.md) objet qui envoie la commande d’impression.  
  
 `pInfo`  
 Un pointeur vers un [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) objet qui décrit le travail d’impression.  
  
##  <a name="execcommand"></a>COleDocObjectItem::ExecCommand  
 Appelez cette fonction membre pour exécuter la commande spécifiée par l’utilisateur.  
  
```  
HRESULT ExecCommand(
    DWORD nCmdID,  
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,  
    const GUID* pguidCmdGroup = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nCmdID`  
 Identificateur de la commande à exécuter. Doit être dans le groupe identifié par `pguidCmdGroup`.  
  
 `nCmdExecOpt`  
 Spécifie les options de commande en cours d’exécution. Par défaut, défini pour exécuter la commande sans solliciter l’utilisateur. Consultez la page [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) pour obtenir la liste de valeurs.  
  
 `pguidCmdGroup`  
 Identificateur unique du groupe de commandes. Par défaut, **NULL**, qui spécifie le groupe standard. La commande passée dans `nCmdID` doivent appartenir au groupe.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` en cas de réussite ; sinon, retourne un des codes d’erreur suivants.  
  
|Valeur|Description|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Une erreur inattendue s’est produite.|  
|**E_FAIL**|Erreur s’est produite.|  
|**E_NOTIMPL**|Indique les MFC elle-même doit tenter de convertir et de distribuer la commande.|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`est non - **NULL** mais ne spécifie ne pas un groupe de commandes reconnu.|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`n’est pas reconnu comme une commande valide dans le groupe pGroup.|  
|**OLECMDERR_DISABLED**|La commande identifiée par `nCmdID` est désactivé et ne peut pas être exécutée.|  
|**OLECMDERR_NOHELP**|L’appelant a demandé de l’aide sur la commande identifiée par `nCmdID` mais aucune aide n’est disponible.|  
|**OLECMDERR_CANCELLED**|L’utilisateur a annulé l’exécution.|  
  
### <a name="remarks"></a>Remarques  
 Le `pguidCmdGroup` et `nCmdID` paramètres identifier de façon unique la commande à appeler. Le `nCmdExecOpt` paramètre spécifie l’action à entreprendre exacte.  
  
##  <a name="getactiveview"></a>COleDocObjectItem::GetActiveView  
 Appelez cette fonction membre pour obtenir un pointeur vers le `IOleDocumentView` interface de la vue actuellement active.  
  
```  
LPOLEDOCUMENTVIEW GetActiveView() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le [IOleDocumentView](http://msdn.microsoft.com/library/windows/desktop/ms678455) interface de la vue actuellement active. S’il n’existe aucun affichage actuel, elle retourne **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Le décompte de références sur le `IOleDocumentView` pointeur n’est pas incrémenté avant d’être retournée par cette fonction.  
  
##  <a name="getpagecount"></a>COleDocObjectItem::GetPageCount  
 Appelez cette fonction membre pour récupérer le nombre de pages dans le document.  
  
```  
BOOL GetPageCount(
    LPLONG pnFirstPage,  
    LPLONG pcPages);
```  
  
### <a name="parameters"></a>Paramètres  
 *pnFirstPage*  
 Pointeur vers le numéro de la page du document première. Peut être **NULL**, ce qui indique à l’appelant n’a pas besoin de ce numéro.  
  
 *pcPages*  
 Pointeur vers le nombre total de pages dans le document. Peut être **NULL**, ce qui indique à l’appelant n’a pas besoin de ce numéro.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
##  <a name="onprepareprinting"></a>COleDocObjectItem::OnPreparePrinting  
 Cette fonction membre est appelée par l’infrastructure pour préparer un document pour l’impression.  
  
```  
static BOOL OnPreparePrinting(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCaller`  
 Un pointeur vers un [CView](../../mfc/reference/cview-class.md) objet qui envoie la commande d’impression.  
  
 `pInfo`  
 Un pointeur vers un [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) objet qui décrit le travail d’impression.  
  
 `bPrintAll`  
 Spécifie si l’ensemble du document doit être imprimée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
##  <a name="onprint"></a>COleDocObjectItem::OnPrint  
 Cette fonction membre est appelée par l’infrastructure pour imprimer un document.  
  
```  
static void OnPrint(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCaller`  
 Pointeur vers un objet CView qui envoie la commande d’impression.  
  
 `pInfo`  
 Un pointeur vers un [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) objet qui décrit le travail d’impression.  
  
 `bPrintAll`  
 Spécifie si l’ensemble du document doit être imprimée.  
  
##  <a name="querycommand"></a>COleDocObjectItem::QueryCommand  
 Demande l’état d’une ou plusieurs commandes générées par des événements d’interface utilisateur.  
  
```  
HRESULT QueryCommand(
    ULONG nCmdID,  
    DWORD* pdwStatus,  
    OLECMDTEXT* pCmdText =NULL,  
    const GUID* pguidCmdGroup =NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nCmdID`  
 identificateur de la commande en cours d’interrogation.  
  
 `pdwStatus`  
 Pointeur vers les indicateurs retournés suite à la requête. Pour obtenir la liste des valeurs possibles, consultez la page [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237).  
  
 `pCmdText`  
 Pointeur vers un [OLECMDTEXT](http://msdn.microsoft.com/library/windows/desktop/ms693314) structure dans laquelle retourner des informations de nom et l’état d’une commande unique. Peut être **NULL** pour indiquer que l’appelant ne doit pas ces informations.  
  
 `pguidCmdGroup`  
 Identificateur unique du groupe de commandes ; peut être **NULL** pour spécifier le groupe standard.  
  
### <a name="return-value"></a>Valeur de retour  
 Pour obtenir une liste complète des valeurs de retour, voir [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre émule les fonctionnalités de la [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) (méthode), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="release"></a>COleDocObjectItem::Release  
 Libère la connexion à un élément lié OLE et la ferme si elle a été ouvert. Ne supprime pas l’élément client.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwCloseOption`  
 Indicateur spécifiant dans quelles circonstances l’élément OLE est enregistrée lorsqu’il retourne à l’état chargé. Pour obtenir la liste des valeurs possibles, consultez la page [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close).  
  
### <a name="remarks"></a>Remarques  
 Ne supprime pas l’élément client.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC MFCBIND](../../visual-cpp-samples.md)   
 [Classe de COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe de COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [CDocObjectServerItem (classe)](../../mfc/reference/cdocobjectserveritem-class.md)

