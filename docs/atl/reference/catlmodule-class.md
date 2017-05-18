---
title: Classe de CAtlModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 19
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
ms.sourcegitcommit: 5a06fc417902378c88e2e65a9b51ee5e4356a39d
ms.openlocfilehash: 75cb5b42cd6c9de14d9abf09b20a1e23716f1149
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodule-class"></a>Classe de CAtlModule
Cette classe fournit des méthodes utilisées par plusieurs classes du module ATL.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|Constructeur.|  
|[CAtlModule :: ~ CAtlModule](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|Substituez cette méthode pour ajouter des paramètres à la table de remplacement de composant de Registre ATL (inscription).|  
|[CAtlModule::AddTermFunc](#addtermfunc)|Ajoute une nouvelle fonction à appeler lorsque le module se termine.|  
|[CAtlModule::GetGITPtr](#getgitptr)|Retourne le pointeur d’Interface globale.|  
|[CAtlModule::GetLockCount](#getlockcount)|Retourne le nombre de verrous.|  
|[CAtlModule::Lock](#lock)|Incrémente le nombre de verrous.|  
|[CAtlModule::Term](#term)|Libère toutes les données membres.|  
|[CAtlModule::Unlock](#unlock)|Décrémente le nombre de verrous.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Exécute le script contenu dans une ressource pour enregistrer ou annuler l’inscription d’un objet spécifiée.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Cette méthode est appelée par `UpdateRegistryFromResourceD` pour effectuer la mise à jour du Registre.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Exécute le script contenu dans une ressource pour enregistrer ou annuler l’inscription d’un objet spécifiée. Cette méthode lie statiquement au composant de Registre ATL.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|Contient le GUID du module actuel.|  
|[CAtlModule::m_pGIT](#m_pgit)|Pointeur vers la Table d’Interface globale.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe est utilisée par [CAtlDllModuleT classe](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT classe](../../atl/reference/catlexemodulet-class.md), et [CAtlServiceModuleT classe](../../atl/reference/catlservicemodulet-class.md) pour prendre en charge les applications DLL, ces applications et services Windows, respectivement.  
  
 Pour plus d’informations sur les modules dans ATL, consultez [Classes du Module ATL](../../atl/atl-module-classes.md).  
  
 Cette classe remplace obsolète [CComModule (classe)](../../atl/reference/ccommodule-class.md) utilisé dans les versions antérieures de l’ATL.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements  
 Substituez cette méthode pour ajouter des paramètres à la table de remplacement de composant de Registre ATL (inscription).  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 *pRegistrar*  
 Réservé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Paramètres remplaçables permettent à un client de Registrar spécifier les données d’exécution. Pour ce faire, Registrar maintient une table de remplacement dans laquelle il entre les valeurs associées aux paramètres remplaçables dans votre script. Registrar effectue ces entrées au moment de l’exécution.  
  
 Consultez la rubrique [à l’aide des paramètres remplaçables (le préprocesseur de Registrar)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) pour plus de détails.  
  
##  <a name="addtermfunc"></a>CAtlModule::AddTermFunc  
 Ajoute une nouvelle fonction à appeler lorsque le module se termine.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *pFunc*  
 Pointeur vers la fonction à ajouter.  
  
 `dw`  
 Données définies par l’utilisateur est passé à la fonction.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="catlmodule"></a>CAtlModule::CAtlModule  
 Constructeur.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Initialise les membres de données et lance une section critique sur les threads du module.  
  
##  <a name="dtor"></a>CAtlModule :: ~ CAtlModule  
 Destructeur.  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>Notes  
 Libère toutes les données membres.  
  
##  <a name="getgitptr"></a>CAtlModule::GetGITPtr  
 Récupère un pointeur vers la Table d’Interface globale.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ppGIT`  
 Pointeur vers la variable qui reçoit le pointeur vers la Table d’Interface globale.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite ou un code d’erreur en cas d’échec. E_POINTER est retournée si `ppGIT` est égal à NULL.  
  
### <a name="remarks"></a>Notes  
 Si l’objet Global Interface Table n’existe pas, il est créé et son adresse est stockée dans la variable membre [CAtlModule::m_pGIT](#m_pgit).  
  
 Dans les versions debug, une erreur d’assertion se produit si `ppGIT` est égal à NULL, ou si le pointeur de la Table d’Interface globale ne peut pas être obtenu.  
  
 Consultez la page [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) pour plus d’informations sur la Table d’Interface globale.  
  
##  <a name="getlockcount"></a>CAtlModule::GetLockCount  
 Retourne le nombre de verrous.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de verrous. Cette valeur peut être utile pour le diagnostic et le débogage.  
  
##  <a name="lock"></a>CAtlModule::Lock  
 Incrémente le nombre de verrous.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Incrémente le nombre de verrous et retourne la valeur mise à jour. Cette valeur peut être utile pour le diagnostic et le débogage.  
  
##  <a name="m_libid"></a>CAtlModule::m_libid  
 Contient le GUID du module actuel.  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>CAtlModule::m_pGIT  
 Pointeur vers la Table d’Interface globale.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="term"></a>CAtlModule::Term  
 Libère toutes les données membres.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les données membres. Cette méthode est appelée par le destructeur.  
  
##  <a name="unlock"></a>CAtlModule::Unlock  
 Décrémente le nombre de verrous.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Décrémente le nombre de verrous et retourne la valeur mise à jour. Cette valeur peut être utile pour le diagnostic et le débogage.  
  
##  <a name="updateregistryfromresourced"></a>CAtlModule::UpdateRegistryFromResourceD  
 Exécute le script contenu dans une ressource pour enregistrer ou annuler l’inscription d’un objet spécifiée.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszRes`  
 Un nom de ressource.  
  
 `nResID`  
 Un ID de ressource.  
  
 `bRegister`  
 **TRUE** si l’objet doit être enregistré ; **FALSE** dans le cas contraire.  
  
 `pMapEntries`  
 Pointeur vers la carte de remplacement stocker des valeurs associées aux paramètres remplaçables du script. ATL utilise automatiquement le MODULE %. Pour utiliser les paramètres remplaçables supplémentaires, consultez [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Sinon, utilisez le **NULL** valeur par défaut.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Exécute le script contenu dans la ressource spécifiée par *lpszRes ou nResID*. Si `bRegister` est **TRUE**, cette méthode enregistre l’objet dans le Registre système ; sinon, elle supprime l’objet à partir du Registre.  
  
 Pour lier statiquement au composant de Registre ATL (inscription), consultez [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Cette méthode appelle [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) et [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).  
  
##  <a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper  
 Cette méthode est appelée par `UpdateRegistryFromResourceD` pour effectuer la mise à jour du Registre.  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszRes`  
 Un nom de ressource.  
  
 `bRegister`  
 Indique si l’objet doit être enregistré.  
  
 `pMapEntries`  
 Pointeur vers la carte de remplacement stocker des valeurs associées aux paramètres remplaçables du script. ATL utilise automatiquement le MODULE %. Pour utiliser les paramètres remplaçables supplémentaires, consultez [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Sinon, utilisez le **NULL** valeur par défaut.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode fournit l’implémentation de [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).  
  
##  <a name="updateregistryfromresources"></a>CAtlModule::UpdateRegistryFromResourceS  
 Exécute le script contenu dans une ressource pour enregistrer ou annuler l’inscription d’un objet spécifiée. Cette méthode lie statiquement au composant de Registre ATL.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nResID`  
 Un ID de ressource.  
  
 `lpszRes`  
 Un nom de ressource.  
  
 `bRegister`  
 Indique si le script de ressources doit être enregistré.  
  
 `pMapEntries`  
 Pointeur vers la carte de remplacement stocker des valeurs associées aux paramètres remplaçables du script. ATL utilise automatiquement le MODULE %. Pour utiliser les paramètres remplaçables supplémentaires, consultez [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Sinon, utilisez le **NULL** valeur par défaut.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Semblable à [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) sauf `CAtlModule::UpdateRegistryFromResourceS` crée un lien statique avec le composant de Registre ATL (inscription).  
  
## <a name="see-also"></a>Voir aussi  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Module (Classes)](../../atl/atl-module-classes.md)   
 [Composant de Registre (inscription)](../../atl/atl-registry-component-registrar.md)  

