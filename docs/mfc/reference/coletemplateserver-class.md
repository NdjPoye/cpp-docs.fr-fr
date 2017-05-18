---
title: Classe de COleTemplateServer | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [C++], implementing
- servers, OLE
- OLE server applications, managing server documents
- link containers [C++]
- visual editing, servers
- OLE link containers
- COleTemplateServer class
- OLE server applications, COleTemplateServer class
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ea82939cd0e8a8ba5612c65d238be8ae9996ef08
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="coletemplateserver-class"></a>COleTemplateServer (classe)
Utilisée pour les serveurs d'édition visuelle OLE, les serveurs Automation et les conteneurs de lien (applications qui prennent en charge les liaisons aux incorporations).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|Construit un objet `COleTemplateServer`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Se connecte un modèle de document sous-jacent `COleObjectFactory` objet.|  
|[COleTemplateServer::Unregister](#unregister)|Annule l’inscription du modèle de document associé.|  
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Enregistre le type de document avec le Registre du système OLE.|  
  
## <a name="remarks"></a>Notes  
 Cette classe est dérivée de la classe [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); en règle générale, vous pouvez utiliser `COleTemplateServer` directement au lieu de dériver votre propre classe. `COleTemplateServer`utilise un [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) objet pour gérer les documents de serveur. Utilisez `COleTemplateServer` lors de l’implémentation d’un serveur complet, autrement dit, un serveur qui peut être exécuté comme une application autonome. Serveurs complets sont généralement plusieurs applications d’interface (multidocument MDI) document, bien que les applications à interface (monodocument SDI) document unique sont pris en charge. Un `COleTemplateServer` objet est nécessaire pour chaque type de document serveur prend en charge par une application ; autrement dit, si votre application serveur prend en charge des feuilles de calcul et des graphiques, vous devez disposer de deux `COleTemplateServer` objets.  
  
 `COleTemplateServer`remplace le `OnCreateInstance` fonction membre définie par `COleObjectFactory`. Cette fonction membre est appelée par l’infrastructure pour créer un objet C++ du type approprié.  
  
 Pour plus d’informations sur les serveurs, consultez l’article [serveurs : implémentation d’un serveur](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdisp.h  
  
##  <a name="coletemplateserver"></a>COleTemplateServer::COleTemplateServer  
 Construit un objet `COleTemplateServer`.  
  
```  
COleTemplateServer();
```  
  
### <a name="remarks"></a>Notes  
 Pour une brève description de l’utilisation de la `COleTemplateServer` de classe, consultez la [COleLinkingDoc plutôt](../../mfc/reference/colelinkingdoc-class.md) vue d’ensemble de la classe.  
  
##  <a name="connecttemplate"></a>COleTemplateServer::ConnectTemplate  
 Connecte le modèle de document vers lequel pointé `pDocTemplate` sous-jacentes [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) objet.  
  
```  
void ConnectTemplate(
    REFCLSID clsid,  
    CDocTemplate* pDocTemplate,  
    BOOL bMultiInstance);
```  
  
### <a name="parameters"></a>Paramètres  
 `clsid`  
 Référence à l’ID de classe que le modèle de demande.  
  
 `pDocTemplate`  
 Pointeur vers le modèle de document.  
  
 `bMultiInstance`  
 Indique si une seule instance de l’application peut prendre en charge plusieurs instanciations. Si **TRUE**, plusieurs instances de l’application sont lancées pour chaque demande de création d’un objet.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [clé CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="unregister"></a>COleTemplateServer::Unregister  
 Annule l’inscription du modèle de document associé.  
  
```  
BOOL Unregister();
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE en cas de réussite, sinon FALSE.  
  
### <a name="remarks"></a>Remarques  
 EnterRemarks  
  
##  <a name="updateregistry"></a>COleTemplateServer::UpdateRegistry  
 Charge les informations de type de fichier à partir de la chaîne de modèle de document et les place dans le Registre du système OLE.  
  
```  
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL,  
    BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nAppType`  
 Une valeur à partir de la **OLE_APPTYPE** énumération, qui est définie dans AFXDISP. H. Il peut avoir l’une des valeurs suivantes :  
  
- `OAT_INPLACE_SERVER`Serveur a interface utilisateur complète du serveur.  
  
- `OAT_SERVER`Prend en charge uniquement l’incorporation.  
  
- `OAT_CONTAINER`Conteneur prend en charge des liens vers des objets incorporés.  
  
- `OAT_DISPATCH_OBJECT`Objet `IDispatch`-compatible.  
  
- **OAT_DOC_OBJECT_SERVER** Server prend en charge l’incorporation et le modèle de composant d’objet de Document.  
  
 `rglpszRegister`  
 Une liste d’entrées qui est écrit dans le Registre uniquement si aucune entrée n’existe.  
  
 `rglpszOverwrite`  
 Une liste d’entrées est consignée dans le Registre, quelle que soit l’existent de toutes les entrées précédentes.  
  
 `bRegister`  
 Détermine si la classe doit être enregistré. Si `bRegister` est **TRUE**, la classe est inscrite dans le Registre système. Dans le cas contraire, il annule l’inscription de la classe.  
  
### <a name="remarks"></a>Remarques  
 Les informations d’inscription sont chargées au moyen d’un appel à [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Les sous-chaînes extraites sont ceux identifiés par les index **regFileTypeId**, **regFileTypeName**, et **fileNewName**, comme décrit dans le `GetDocString` pages de référence.  
  
 Si le **regFileTypeId** sous-chaîne est vide ou si l’appel à `GetDocString` échoue pour une raison quelconque, cette fonction échoue et les informations de fichier ne sont pas entrées dans le Registre.  
  
 Les informations contenues dans les arguments `rglpszRegister` et `rglpszOverwrite` est écrit dans le Registre via un appel à [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). Les informations par défaut, qui sont enregistrées lorsque les deux arguments sont **NULL**, convient à la plupart des applications. Pour plus d’informations sur la structure des informations dans ces arguments, consultez `AfxOleRegisterServerClass`.  
  
 Pour plus d’informations, consultez [implémentant l’IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC HIERSVR](../../visual-cpp-samples.md)   
 [COleObjectFactory (classe)](../../mfc/reference/coleobjectfactory-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe de COleServerDoc](../../mfc/reference/coleserverdoc-class.md)   
 [Classe COleServerItem](../../mfc/reference/coleserveritem-class.md)

