---
title: La classe CComAutoThreadModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 07aaf6dc7029452fa6822c5f5f1ae09b724ddc8b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule (classe)
À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class ThreadAllocator = CComSimpleThreadAllocator>  
class CComAutoThreadModule : public CComModule
```  
  
#### <a name="parameters"></a>Paramètres  
 `ThreadAllocator`  
 [in] La classe de la gestion de sélection de thread. La valeur par défaut est [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[CreateInstance](#createinstance)|Sélectionne un thread, puis crée un objet dans le compartiment associé.|  
|[GetDefaultThreads](#getdefaultthreads)|(Statique) Calcule dynamiquement le nombre de threads pour le module en fonction du nombre de processeurs.|  
|[Init](#init)|Crée les threads du module.|  
|[Verrou](#lock)|Incrémente le nombre de verrous sur le module et sur le thread actuel.|  
|[Déverrouiller](#unlock)|Décrémente le nombre de verrous sur le module et sur le thread actuel.|  
  
### <a name="data-members"></a>Membres de données  
  
### <a name="data-members"></a>Membres de données  
  
|||  
|-|-|  
|[dwThreadID](#dwthreadid)|Contient l’identificateur du thread actuel.|  
|[m_Allocator](#m_allocator)|Gère la sélection du thread.|  
|[m_nThreads](#m_nthreads)|Contient le nombre de threads dans le module.|  
|[m_pApartments](#m_papartments)|Gère des cloisonnements du module.|  
  
## <a name="remarks"></a>Notes  
  
> [!NOTE]
>  Cette classe est obsolète, a été remplacée par la [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) et [CAtlModule](../../atl/reference/catlmodule-class.md) des classes dérivées. Les informations suivantes sont utilisée avec les versions plus anciennes d’ATL.  
  
 `CComAutoThreadModule`dérive de [CComModule](../../atl/reference/ccommodule-class.md) pour implémenter un serveur COM thread regroupée, modèle de cloisonnement pour les services Windows et les fichiers exe. `CComAutoThreadModule`utilise [CComApartment](../../atl/reference/ccomapartment-class.md) pour gérer un cloisonnement pour chaque thread dans le module.  
  
 Dériver votre module de `CComAutoThreadModule` lorsque vous souhaitez créer des objets dans des compartiments à plusieurs. Vous devez également inclure le [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) macro dans votre définition de l’objet classe pour spécifier [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) en tant que la fabrique de classe.  
  
 Par défaut, l’outil ATL COM AppWizard (l’Assistant de projet ATL dans Visual Studio .NET) dérivera votre module de `CComModule`. Pour utiliser `CComAutoThreadModule`, modifiez la définition de classe. Exemple :  
  
 [!code-cpp[NVC_ATL_AxHost n °&2;](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="a-namecreateinstancea--ccomautothreadmodulecreateinstance"></a><a name="createinstance"></a>CComAutoThreadModule::CreateInstance  
 À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>Paramètres  
 *pfnCreateInstance*  
 [in] Pointeur vers une fonction du créateur.  
  
 `riid`  
 [in] L’IID de l’interface demandée.  
  
 `ppvObj`  
 [out] Un pointeur vers le pointeur d’interface identifié par `riid`. Si l’objet ne prend pas en charge cette interface, `ppvObj` a la valeur NULL.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
### <a name="remarks"></a>Remarques  
 Sélectionne un thread, puis crée un objet dans le compartiment associé.  
  
##  <a name="a-namedwthreadida--ccomautothreadmoduledwthreadid"></a><a name="dwthreadid"></a>CComAutoThreadModule::dwThreadID  
 À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
```
DWORD dwThreadID;
```  
  
### <a name="remarks"></a>Notes  
 Contient l’identificateur du thread actuel.  
  
##  <a name="a-namegetdefaultthreadsa--ccomautothreadmodulegetdefaultthreads"></a><a name="getdefaultthreads"></a>CComAutoThreadModule::GetDefaultThreads  
 À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de threads doit être créé dans le module du fichier EXE.  
  
### <a name="remarks"></a>Notes  
 Cette fonction statique calcule dynamiquement le nombre maximal de threads pour le module EXE, en fonction du nombre de processeurs. Par défaut, cette valeur de retour est passée à la [Init](#init) pour créer les threads.  
  
##  <a name="a-nameinita--ccomautothreadmoduleinit"></a><a name="init"></a>CComAutoThreadModule::Init  
 À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 [in] Pointeur vers un tableau d’entrées de mappage d’objet.  
  
 `h`  
 [in] Le `HINSTANCE` transmis à **DLLMain** ou `WinMain`.  
  
 `plibid`  
 [in] Pointeur vers le LIBID de la bibliothèque de types associé au projet.  
  
 `nThreads`  
 [in] Le nombre de threads doit être créé. Par défaut, `nThreads` est la valeur retournée par [GetDefaultThreads](#getdefaultthreads).  
  
### <a name="remarks"></a>Remarques  
 Initialise les membres de données et crée le nombre de threads spécifié par `nThreads`.  
  
##  <a name="a-namelocka--ccomautothreadmodulelock"></a><a name="lock"></a>CComAutoThreadModule::Lock  
 À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui peut être utile pour les tests de diagnostic ou de test.  
  
### <a name="remarks"></a>Notes  
 Effectue un incrément atomique sur le nombre de verrous pour le module et le thread actuel. `CComAutoThreadModule`utilise le nombre de verrous du module pour déterminer si tous les clients accèdent à du module. Le nombre de verrous sur le thread actuel est utilisé à des fins statistiques.  
  
##  <a name="a-namemallocatora--ccomautothreadmodulemallocator"></a><a name="m_allocator"></a>CComAutoThreadModule::m_Allocator  
 À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
```
ThreadAllocator  m_Allocator;
```     
  
### <a name="remarks"></a>Remarques  
 L’objet de gestion de la sélection de thread. Par défaut, le `ThreadAllocator` paramètre de modèle de classe [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
##  <a name="a-namemnthreadsa--ccomautothreadmodulemnthreads"></a><a name="m_nthreads"></a>CComAutoThreadModule::m_nThreads  
 À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
```
int m_nThreads;
```  
  
### <a name="remarks"></a>Remarques  
 Contient le nombre de threads dans le module du fichier EXE. Lors de la [Init](#init) est appelée, `m_nThreads` est défini sur la `nThreads` la valeur du paramètre. Cloisonnement associés de chaque thread est géré par un [CComApartment](../../atl/reference/ccomapartment-class.md) objet.  
  
##  <a name="a-namempapartmentsa--ccomautothreadmodulempapartments"></a><a name="m_papartments"></a>CComAutoThreadModule::m_pApartments  
 À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
```
CComApartment* m_pApartments;
```  
  
### <a name="remarks"></a>Remarques  
 Pointe vers un tableau de [CComApartment](../../atl/reference/ccomapartment-class.md) objets, chacun d’eux gère un cloisonnement dans le module. Le nombre d’éléments dans le tableau est basé sur le [m_nThreads](#m_nthreads) membre.  
  
##  <a name="a-nameunlocka--ccomautothreadmoduleunlock"></a><a name="unlock"></a>CComAutoThreadModule::Unlock  
 À compter d’ATL 7.0, `CComAutoThreadModule` est obsolète : consultez [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui peut être utile pour les tests de diagnostic ou de test.  
  
### <a name="remarks"></a>Remarques  
 Effectue une décrémentation atomique sur le nombre de verrous pour le module et le thread actuel. `CComAutoThreadModule`utilise le nombre de verrous du module pour déterminer si tous les clients accèdent à du module. Le nombre de verrous sur le thread actuel est utilisé à des fins statistiques.  
  
 Lorsque le nombre de verrous du module atteint zéro, le module peut être déchargé.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Module (Classes)](../../atl/atl-module-classes.md)

