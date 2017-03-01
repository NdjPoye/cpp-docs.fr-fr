---
title: COleObjectFactory (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleObjectFactory
dev_langs:
- C++
helpviewer_keywords:
- OLE, class factory
- OLE class factory
- COleObjectFactory class
- objects [C++], creating OLE
- OLE objects
- object creation, OLE objects
- class factories, COleObjectFactory class
- OLE objects, creating
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
caps.latest.revision: 21
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
ms.openlocfilehash: 643d17ccdefb60b561e7e5488753a6dbf778c69f
ms.lasthandoff: 02/24/2017

---
# <a name="coleobjectfactory-class"></a>COleObjectFactory (classe)
Implémente la fabrique de classes OLE, qui crée des objets OLE tels que des serveurs, des objets Automation et des documents.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|Construit un objet `COleObjectFactory`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleObjectFactory::GetClassID](#getclassid)|Retourne le OLE classe ID des objets que cette fabrique crée.|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Détermine si la licence du contrôle est valide.|  
|[COleObjectFactory::IsRegistered](#isregistered)|Indique si la fabrique d’objet est inscrit avec les DLL système OLE.|  
|[COleObjectFactory](#register)|Enregistre cette fabrique d’objet avec les DLL système OLE.|  
|[COleObjectFactory::RegisterAll](#registerall)|Enregistre toutes les fabriques d’objet de l’application avec les DLL système OLE.|  
|[COleObjectFactory::Revoke](#revoke)|Révoque l’inscription de cette fabrique d’objet avec les DLL système OLE.|  
|[COleObjectFactory::RevokeAll](#revokeall)|Révoque les enregistrements des fabriques d’objets d’une application avec les DLL système OLE.|  
|[COleObjectFactory::UnregisterAll](#unregisterall)|Annule l’inscription de toutes les fabriques d’objets d’une application.|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Enregistre cette fabrique d’objet du Registre du système OLE.|  
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|Enregistre toutes les fabriques d’objet de l’application avec le Registre du système OLE.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Demande une clé unique à partir de la DLL du contrôle.|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Appelé par le framework pour créer un nouvel objet de type de cette fabrique.|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Vérifie que la clé incorporée dans le contrôle correspond à la clé incorporée dans le conteneur.|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Vérifie que le contrôle est une licence d’utilisation au moment de la conception.|  
  
## <a name="remarks"></a>Remarques  
 La `COleObjectFactory` classe a des fonctions membres pour effectuer les opérations suivantes :  
  
-   Gestion de l’inscription d’objets.  
  
-   Mise à jour le Registre du système OLE, ainsi que l’inscription de l’exécution qui informe OLE que les objets sont en cours d’exécution et prêt à recevoir des messages.  
  
-   Application de gestion de licences en limitant l’utilisation du contrôle aux développeurs sous licence au moment du design et des applications sous licence au moment de l’exécution.  
  
-   Inscription des fabriques d’objet de contrôle du Registre du système OLE.  
  
 Pour plus d’informations sur la création d’objets, consultez les articles [des objets de données et Sources de données (OLE)](../../mfc/data-objects-and-data-sources-ole.md) et [des objets de données et Sources de données : création et Destruction](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Pour plus d’informations sur l’inscription, consultez l’article [inscription](../../mfc/registration.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdisp.h  
  
##  <a name="a-namecoleobjectfactorya--coleobjectfactorycoleobjectfactory"></a><a name="coleobjectfactory"></a>COleObjectFactory::COleObjectFactory  
 Construit un `COleObjectFactory` objet, initialise comme une fabrique d’objet non enregistré et l’ajoute à la liste des fabriques.  
  
```  
COleObjectFactory(
    REFCLSID clsid,  
    CRuntimeClass* pRuntimeClass,  
    BOOL bMultiInstance,  
    LPCTSTR lpszProgID);

 
COleObjectFactory(
    REFCLSID clsid,  
    CRuntimeClass* pRuntimeClass,  
    BOOL bMultiInstance,  
    int nFlags,  
    LPCTSTR lpszProgID);
```  
  
### <a name="parameters"></a>Paramètres  
 `clsid`  
 Référence à l’ID de classe OLE représente cette fabrique d’objet.  
  
 `pRuntimeClass`  
 Pointeur vers la classe d’exécution des objets C++ que cette fabrique peut créer.  
  
 `bMultiInstance`  
 Indique si une seule instance de l’application peut prendre en charge plusieurs instanciations. Si **TRUE**, plusieurs instances de l’application sont lancées pour chaque demande de création d’un objet.  
  
 `nFlags`  
 Contient un ou plusieurs des indicateurs suivants :  
  
- **afxRegDefault** définit le modèle de thread à ThreadingModel = cloisonnement.  
  
- **afxRegInsertable** permet le contrôle s’affiche dans le **insérer un objet** boîte de dialogue pour les objets OLE.  
  
- `afxRegApartmentThreading`Définit le modèle de thread dans le Registre pour ThreadingModel = cloisonnement.  
  
- **afxRegFreeThreading** définit le modèle de thread dans le Registre pour ThreadingModel = gratuit.  
  
     Vous pouvez combiner les deux indicateurs `afxRegApartmentThreading` et `afxRegFreeThreading` pour définir ThreadingModel = les deux. Consultez la page [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur l’inscription du modèle de thread.  
  
 `lpszProgID`  
 Pointeur vers une chaîne contenant un identificateur de programme verbale, telle que « Microsoft Excel ».  
  
### <a name="remarks"></a>Notes  
 Pour utiliser l’objet, toutefois, vous devez l’inscrire.  
  
 Pour plus d’informations, consultez [clé CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetclassida--coleobjectfactorygetclassid"></a><a name="getclassid"></a>COleObjectFactory::GetClassID  
 Retourne une référence à l’ID de classe OLE représente cette fabrique.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’ID de classe cette fabrique représente.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [clé CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetlicensekeya--coleobjectfactorygetlicensekey"></a><a name="getlicensekey"></a>COleObjectFactory::GetLicenseKey  
 Demande une clé de licence unique à partir de la DLL du contrôle et le stocke dans le `BSTR` désigné par `pbstrKey`.  
  
```  
virtual BOOL GetLicenseKey(
    DWORD dwReserved,  
    BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwReserved`  
 Réservé à un usage ultérieur.  
  
 `pbstrKey`  
 Pointeur vers un `BSTR` qui stocke la clé de licence.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la chaîne de la clé de licence n’est pas **NULL**; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de cette fonction renvoie la valeur 0 et stocke rien dans le `BSTR`. Si vous utilisez MFC ActiveX ControlWizard pour créer votre projet, ControlWizard fournit un remplacement qui Récupère la clé de licence du contrôle.  
  
##  <a name="a-nameislicensevalida--coleobjectfactoryislicensevalid"></a><a name="islicensevalid"></a>COleObjectFactory::IsLicenseValid  
 Détermine si la licence du contrôle est valide.  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la réussite ; Sinon, false.  
  
##  <a name="a-nameisregistereda--coleobjectfactoryisregistered"></a><a name="isregistered"></a>COleObjectFactory::IsRegistered  
 Retourne une valeur différente de zéro si la fabrique est enregistrée avec les DLL système OLE.  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fabrique est enregistrée ; sinon 0.  
  
##  <a name="a-nameoncreateobjecta--coleobjectfactoryoncreateobject"></a><a name="oncreateobject"></a>COleObjectFactory::OnCreateObject  
 Appelé par le framework pour créer un nouvel objet.  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’objet créé. Il peut lever une exception de mémoire en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction pour créer l’objet d’un élément autre que le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) passé au constructeur.  
  
##  <a name="a-nameregistera--coleobjectfactoryregister"></a><a name="register"></a>COleObjectFactory  
 Enregistre cette fabrique d’objet avec les DLL système OLE.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fabrique est inscrit correctement ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est généralement appelée par [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) lorsque l’application est lancée.  
  
##  <a name="a-nameregisteralla--coleobjectfactoryregisterall"></a><a name="registerall"></a>COleObjectFactory::RegisterAll  
 Enregistre toutes les fabriques d’objet de l’application avec les DLL système OLE.  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les fabriques ont été correctement inscrits ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est généralement appelée par [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) lorsque l’application est lancée.  
  
##  <a name="a-namerevokea--coleobjectfactoryrevoke"></a><a name="revoke"></a>COleObjectFactory::Revoke  
 Révoque l’inscription de cette fabrique d’objet avec les DLL système OLE.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure appelle cette fonction automatiquement avant l’application se termine. Si nécessaire, l’appeler à partir d’une substitution de [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="a-namerevokealla--coleobjectfactoryrevokeall"></a><a name="revokeall"></a>COleObjectFactory::RevokeAll  
 Révoque tous les enregistrements des fabriques d’objets de l’application avec les DLL système OLE.  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure appelle cette fonction automatiquement avant l’application se termine. Si nécessaire, l’appeler à partir d’une substitution de [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="a-nameunregisteralla--coleobjectfactoryunregisterall"></a><a name="unregisterall"></a>COleObjectFactory::UnregisterAll  
 Annule l’inscription de toutes les fabriques d’objets d’une application.  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE en cas de réussite, sinon FALSE.  
  
##  <a name="a-nameupdateregistrya--coleobjectfactoryupdateregistry"></a><a name="updateregistry"></a>COleObjectFactory::UpdateRegistry  
 Enregistre toutes les fabriques d’objet de l’application avec le Registre du système OLE.  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszProgID`  
 Pointeur vers une chaîne contenant l’identificateur de programme explicite, tel que « Excel.Document.5 ».  
  
 `bRegister`  
 Détermine si la fabrique d’objet de la classe de contrôle doit être enregistré.  
  
### <a name="remarks"></a>Notes  
 Brève discussion des deux formes pour le suivi de cette fonction :  
  
- **UpdateRegistry (** `lpszProgID` **)** enregistre cette fabrique d’objet du Registre du système OLE. Cette fonction est généralement appelée par [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) lorsque l’application est lancée.  
  
- **UpdateRegistry (** `bRegister` **)** cette forme de la fonction est substituable. Si `bRegister` est **TRUE**, cette fonction enregistre la classe de contrôle du Registre système. Dans le cas contraire, il annule l’inscription de la classe.  
  
     Si vous utilisez MFC ActiveX ControlWizard pour créer votre projet, ControlWizard fournit une substitution de cette fonction virtuelle pure.  
  
##  <a name="a-nameupdateregistryalla--coleobjectfactoryupdateregistryall"></a><a name="updateregistryall"></a>COleObjectFactory::UpdateRegistryAll  
 Enregistre toutes les fabriques d’objet de l’application avec le Registre du système OLE.  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bRegister`  
 Détermine si la fabrique d’objet de la classe de contrôle doit être enregistré.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les fabriques sont correctement mis à jour ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est généralement appelée par [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) lorsque l’application est lancée.  
  
##  <a name="a-nameverifylicensekeya--coleobjectfactoryverifylicensekey"></a><a name="verifylicensekey"></a>COleObjectFactory::VerifyLicenseKey  
 Vérifie que le conteneur est concédé sous licence pour utiliser le contrôle OLE.  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>Paramètres  
 `bstrKey`  
 A `BSTR` le stockage de la version du conteneur de la chaîne de licence.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la licence d’exécution est valide ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 La version par défaut appelle [GetLicenseKey](#getlicensekey) pour obtenir une copie du contrôle de la chaîne de licence et la compare à la chaîne dans `bstrKey`. Si les deux chaînes sont identiques, la fonction retourne une valeur différente de zéro ; Sinon, elle retourne 0.  
  
 Vous pouvez remplacer cette fonction pour assurer une vérification personnalisée de la licence.  
  
 La fonction [VerifyUserLicense](#verifyuserlicense) vérifie la licence au moment du design.  
  
##  <a name="a-nameverifyuserlicensea--coleobjectfactoryverifyuserlicense"></a><a name="verifyuserlicense"></a>COleObjectFactory::VerifyUserLicense  
 Vérifie la licence au moment du design pour le contrôle OLE.  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la licence est valide ; sinon 0.  
  
## <a name="see-also"></a>Voir aussi  
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer (classe)](../../mfc/reference/coletemplateserver-class.md)

