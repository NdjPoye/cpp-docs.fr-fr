---
title: "Fonctions globales de l’inscription de serveur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4ace3bb50d824827071260e3f43cec3cda32742f
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="server-registration-global-functions"></a>Fonctions globales de l’inscription de serveur
Ces fonctions fournissent la prise en charge de l’inscription et la désinscription des objets serveur dans la table des objets.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peut pas être utilisées dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Cette fonction est appelée pour inscrire chaque objet du mappage d'objets.|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Cette fonction est appelée pour annuler l'inscription de chaque objet du mappage d'objets.|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Cette fonction est appelée pour inscrire des objets de classe.|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Cette fonction est appelée pour supprimer des objets de classe à partir d’un module COM.|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Cette fonction est appelée pour obtenir l’objet de classe.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
   
##  <a name="atlcommoduleregisterserver"></a>AtlComModuleRegisterServer  
 Cette fonction est appelée pour inscrire chaque objet du mappage d'objets.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Paramètres  
 `pComModule`  
 Pointeur vers le module COM.  
  
 `bRegTypeLib`  
 TRUE si la bibliothèque de types doit être enregistré.  
  
 `pCLSID`  
 Pointe vers le CLSID de l’objet à inscrire. Si la valeur NULL, tous les objets du mappage d’objets seront enregistrés.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 `AtlComModuleRegisterServer`Décrit le mappage d’objets ATL générées automatiquement et enregistre chaque objet dans la carte. Si `pCLSID` n’est pas NULL, alors seulement l’objet référencé par `pCLSID` est enregistré ; sinon, tous les objets sont enregistrés.  
  
 Cette fonction est appelée par [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).  
  
##  <a name="atlcommoduleunregisterserver"></a>AtlComModuleUnregisterServer  
 Cette fonction est appelée pour annuler l'inscription de chaque objet du mappage d'objets.  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Paramètres  
 `pComModule`  
 Pointeur vers le module COM.  
  
 `bUnRegTypeLib`  
 TRUE si la bibliothèque de types doit être enregistré.  
  
 `pCLSID`  
 Pointe vers le CLSID de l’objet doit être annulée. Si NULL, tous les objets du mappage d’objets sera annulées.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 `AtlComModuleUnregisterServer`Décrit le mappage d’objets ATL et annule l’inscription de chaque objet de la carte. Si `pCLSID` n’est pas NULL, alors seulement l’objet référencé par `pCLSID` est désinscrite ; sinon tous les objets sont annulées.  
  
 Cette fonction est appelée par [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).  
  
##  <a name="atlcommoduleregisterclassobjects"></a>AtlComModuleRegisterClassObjects  
 Cette fonction est appelée pour inscrire des objets de classe.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 `pComModule`  
 Pointeur vers le module COM.  
  
 `dwClsContext`  
 Spécifie le contexte dans lequel l’objet de classe doit être exécutée. Les valeurs possibles sont CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER ou CLSCTX_LOCAL_SERVER. Consultez la page [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) pour plus de détails.  
  
 `dwFlags`  
 Détermine les types de connexion à l’objet de classe. Les valeurs possibles sont REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE ou REGCLS_MULTI_SEPARATE. Consultez la page [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) pour plus de détails.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction d’assistance utilisée par [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (obsolète dans ATL 7.0) et [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).  
  
##  <a name="atlcommodulerevokeclassobjects"></a>AtlComModuleRevokeClassObjects  
 Cette fonction est appelée pour supprimer la ou les fabriques de classes de la table des objets en cours d'exécution (ROT).  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>Paramètres  
 `pComModule`  
 Pointeur vers le module COM.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction d’assistance utilisée par [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (obsolète dans ATL 7.0) et [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).  
  
##  <a name="atlcommodulegetclassobject"></a>AtlComModuleGetClassObject  
 Cette fonction est appelée pour retourner la fabrique de classe.  
  
```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```  
  
### <a name="parameters"></a>Paramètres  
 `pComModule`  
 Pointeur vers le module COM.  
  
 `rclsid`  
 Le CLSID de l’objet à créer.  
  
 `riid`  
 L’IID de l’interface demandée.  
  
 `ppv`  
 Un pointeur vers le pointeur d’interface identifié par `riid`. Si l’objet ne prend pas en charge cette interface, `ppv` a la valeur NULL.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction d’assistance utilisée par [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (obsolète dans ATL 7.0) et [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)

