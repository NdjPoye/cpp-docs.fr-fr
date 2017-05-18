---
title: Classe de CAtlDllModuleT | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 13cd0adb860660e06c92e8f02c07721ede391fb7
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT (classe)
Cette classe représente le module d’une DLL.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe dérivée de `CAtlDllModuleT`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Constructeur.|  
|[CAtlDllModuleT :: ~ CAtlDllModuleT](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|Teste si la DLL peut être déchargée.|  
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|Retourne une fabrique de classe.|  
|[CAtlDllModuleT::DllMain](#dllmain)|Le point d’entrée facultative dans une bibliothèque de liens dynamiques (DLL).|  
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|Ajoute des entrées au Registre du système pour les objets dans la DLL.|  
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|Supprime les entrées dans le Registre système pour les objets dans la DLL.|  
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Retourne une fabrique de classe. Appelé par [DllGetClassObject](#dllgetclassobject).|  
  
## <a name="remarks"></a>Remarques  
 `CAtlDllModuleT`représente le module pour une bibliothèque de liens dynamiques (DLL) et fournit des fonctions utilisées par tous les projets DLL. Cette spécialisation de [CAtlModuleT](../../atl/reference/catlmodulet-class.md) classe inclut la prise en charge de l’inscription.  
  
 Pour plus d’informations sur les modules dans ATL, consultez [Classes du Module ATL](../../atl/atl-module-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlDllModuleT`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="catldllmodulet"></a>CAtlDllModuleT::CAtlDllModuleT  
 Constructeur.  
  
```
CAtlDllModuleT() throw();
```  
  
##  <a name="dtor"></a>CAtlDllModuleT :: ~ CAtlDllModuleT  
 Destructeur.  
  
```
~CAtlDllModuleT() throw();
```  
  
##  <a name="dllcanunloadnow"></a>CAtlDllModuleT::DllCanUnloadNow  
 Teste si la DLL peut être déchargée.  
  
```
HRESULT DllCanUnloadNow() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK si la DLL peut être déchargée ou S_FALSE si elle ne peut pas.  
  
##  <a name="dllgetclassobject"></a>CAtlDllModuleT::DllGetClassObject  
 Retourne la fabrique de classe.  
  
```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `rclsid`  
 Le CLSID de l’objet à créer.  
  
 `riid`  
 L’IID de l’interface demandée.  
  
 `ppv`  
 Un pointeur vers le pointeur d’interface identifié par `riid`. Si l’objet ne prend pas en charge cette interface, `ppv` a la valeur NULL.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="dllmain"></a>CAtlDllModuleT::DllMain  
 Le point d’entrée facultative dans une bibliothèque de liens dynamiques (DLL).  
  
```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dwReason`  
 Si défini sur les appels de notification DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH et DLL_THREAD_DETACH est désactivé.  
  
 *lpReserved*  
 Réservé.  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie toujours TRUE.  
  
### <a name="remarks"></a>Remarques  
 La désactivation DLL_THREAD_ATTACH et DLL_THREAD_DETACH d’appels de notification peuvent être une optimisation utile pour les applications multithread qui ont de nombreuses DLL, qui souvent de créer et de supprimer des threads, et dont les DLL n’est pas nécessaire de ces notifications au niveau du thread d’attachement/détachement.  
  
##  <a name="dllregisterserver"></a>CAtlDllModuleT::DllRegisterServer  
 Ajoute des entrées au Registre du système pour les objets dans la DLL.  
  
```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `bRegTypeLib`  
 TRUE si la bibliothèque de types doit être enregistré. La valeur par défaut est TRUE.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="dllunregisterserver"></a>CAtlDllModuleT::DllUnregisterServer  
 Supprime les entrées dans le Registre système pour les objets dans la DLL.  
  
```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `bUnRegTypeLib`  
 TRUE si la bibliothèque de types doit être supprimée du Registre. La valeur par défaut est TRUE.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="getclassobject"></a>CAtlDllModuleT::GetClassObject  
 Crée un objet du CLSID spécifié.  
  
```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `rclsid`  
 Le CLSID de l’objet à créer.  
  
 `riid`  
 L’IID de l’interface demandée.  
  
 `ppv`  
 Un pointeur vers le pointeur d’interface identifié par `riid`. Si l’objet ne prend pas en charge cette interface, `ppv` a la valeur NULL.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) et est inclus pour la compatibilité descendante.  
  
## <a name="see-also"></a>Voir aussi  
 [CAtlModuleT (classe)](../../atl/reference/catlmodulet-class.md)   
 [CAtlExeModuleT (classe)](../../atl/reference/catlexemodulet-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Module (Classes)](../../atl/atl-module-classes.md)

