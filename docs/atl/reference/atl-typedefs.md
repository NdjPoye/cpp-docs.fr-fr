---
title: Typedefs ATL | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
caps.latest.revision: 20
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
ms.sourcegitcommit: 347e7bf7cd9173fb2815f44fc052ec23ab4055a6
ms.openlocfilehash: aa57212b602538e4e8d2854c6075562e72472796
ms.lasthandoff: 02/24/2017

---
# <a name="atl-typedefs"></a>Typedefs ATL
Active Template Library inclut les typedefs suivants.  
  
|||  
|-|-|  
|[_ATL_BASE_MODULE](#_atl_base_module)|Défini comme un typedef selon [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|  
|[_ATL_COM_MODULE](#_atl_com_module)|Défini comme un typedef selon [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|  
|[_ATL_MODULE](#_atl_module)|Défini comme un typedef selon [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|  
|[_ATL_WIN_MODULE](#_atl_win_module)|Défini comme un typedef selon [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|  
|[ATL_URL_PORT](#atl_url_port)|Le type utilisé par [CUrl](../../atl/reference/curl-class.md) pour spécifier un numéro de port.|  
|[CComDispatchDriver](#ccomdispatchdriver)|Cette classe gère des pointeurs d’interface COM.|  
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Appelle des méthodes du modèle, quel que soit le modèle de thread utilisé le thread approprié.|  
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Appelle des méthodes du modèle, quel que soit le modèle de thread utilisé le thread approprié.|  
|[CContainedWindow](#ccontainedwindow)|Cette classe est une spécialisation de **CContainedWindowT.**|  
|[CPath](#cpath)|Une spécialisation de [CPathT](../../atl/reference/cpatht-class.md) à l’aide de `CString`.|  
|[CPathA](#cpatha)|Une spécialisation de [CPathT](../../atl/reference/cpatht-class.md) à l’aide de `CStringA`.|  
|[CPathW](#cpathw)|Une spécialisation de [CPathT](../../atl/reference/cpatht-class.md) à l’aide de `CStringW`.|  
|[CSimpleValArray](#csimplevalarray)|Représente un tableau pour le stockage des types simples.|  
|[DefaultThreadTraits](#defaultthreadtraits)|La classe de traits de thread par défaut.|  
|[LPCURL](#lpcurl)|Un pointeur vers une constante [CUrl](../../atl/reference/curl-class.md) objet.|  
|[LPURL](#lpurl)|Un pointeur vers un [CUrl](../../atl/reference/curl-class.md) objet.|  
  
##  <a name="a-nameatlbasemodulea--atlbasemodule"></a><a name="_atl_base_module"></a>_ATL_BASE_MODULE  
 Défini comme un typedef selon _ATL_BASE_MODULE70.  
  
```   
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;   
```  
  
### <a name="remarks"></a>Notes  
 Utilisé dans tous les projets ATL. Selon [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).  
  
 La structure _ATL_BASE_MODULE dérivent de classes qui font partie des Classes de Module ATL 7.0.  Pour plus d’informations sur les Classes du Module ATL, consultez [Classes de Modules COM](../../atl/com-modules-classes.md).  
  
##  <a name="a-nameatlcommodulea--atlcommodule"></a><a name="_atl_com_module"></a>_ATL_COM_MODULE  
 Défini comme un typedef selon _ATL_COM_MODULE70.  
  
```   
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;   
```  
  
### <a name="remarks"></a>Notes  
 Utilisé par les projets ATL qui utilisent des fonctionnalités COM. Selon [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).  
  
##  <a name="a-nameatlmodulea--atlmodule"></a><a name="_atl_module"></a>_ATL_MODULE  
 Défini comme un typedef selon _ATL_MODULE70.  
  
```   
typedef ATL::_ATL_MODULE70 _ATL_MODULE;   
```  
  
### <a name="remarks"></a>Notes  
 Selon [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).  
  
##  <a name="a-nameatlwinmodulea--atlwinmodule"></a><a name="_atl_win_module"></a>_ATL_WIN_MODULE  
 Défini comme un typedef selon _ATL_WIN_MODULE70.  
  
```   
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE; 
 
```  
  
### <a name="remarks"></a>Remarques  
 Utilisé par les projets ATL qui utilisent des fonctions de fenêtrage. Selon [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md).  
  
##  <a name="a-nameatlurlporta--atlurlport"></a><a name="atl_url_port"></a>ATL_URL_PORT 
  Le type utilisé par [CUrl](curl-class.md) pour spécifier un numéro de port.
```  
typedef WORD ATL_URL_PORT;
```  

##  <a name="a-nameccomdispatchdrivera--ccomdispatchdriver"></a><a name="ccomdispatchdriver"></a>CComDispatchDriver  
 Cette classe gère des pointeurs d’interface COM.  
  
```   
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;   
```  
  
##  <a name="a-nameccomglobalsthreadmodela--ccomglobalsthreadmodel"></a><a name="ccomglobalsthreadmodel"></a>CComGlobalsThreadModel  
 Appelle des méthodes du modèle, quel que soit le modèle de thread utilisé le thread approprié.  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>Remarques  
 Selon le modèle de thread utilisé par votre application, le `typedef` nom `CComGlobalsThreadModel` fait référence à une [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ou [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Ces classes de fournir des fonctionnalités supplémentaires `typedef` noms à référencer une classe de la section critique.  
  
> [!NOTE]
> `CComGlobalsThreadModel`ne référence pas de classe [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 À l’aide de `CComGlobalsThreadModel` vous évite de spécification d’une classe de modèle de thread particulier. Quel que soit le modèle de thread utilisé, il s’appellera les méthodes appropriées.  
  
 En plus de `CComGlobalsThreadModel`, ATL fournit le `typedef` nom [CComObjectThreadModel](#ccomobjectthreadmodel). La classe référencée par chaque `typedef` varie selon le modèle de thread utilisé, comme indiqué dans le tableau suivant :  
  
|typedef|Thread unique|Modèle de thread cloisonné|Modèle de thread libre|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 Utilisez `CComObjectThreadModel` au sein d’une classe d’objet unique. Utilisez `CComGlobalsThreadModel` dans un objet qui est globalement disponible pour votre programme, ou lorsque vous souhaitez protéger des ressources du module entre plusieurs threads.  
  
##  <a name="a-nameccomobjectthreadmodela--ccomobjectthreadmodel"></a><a name="ccomobjectthreadmodel"></a>CComObjectThreadModel  
 Appelle des méthodes du modèle, quel que soit le modèle de thread utilisé le thread approprié.  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComObjectThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>Notes  
 Selon le modèle de thread utilisé par votre application, le `typedef` nom `CComObjectThreadModel` fait référence à une [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ou [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Ces classes de fournir des fonctionnalités supplémentaires `typedef` noms à référencer une classe de la section critique.  
  
> [!NOTE]
> `CComObjectThreadModel`ne référence pas de classe [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 À l’aide de `CComObjectThreadModel` vous évite de spécification d’une classe de modèle de thread particulier. Quel que soit le modèle de thread utilisé, il s’appellera les méthodes appropriées.  
  
 En plus de `CComObjectThreadModel`, ATL fournit le `typedef` nom [CComGlobalsThreadModel](#ccomglobalsthreadmodel). La classe référencée par chaque `typedef` varie selon le modèle de thread utilisé, comme indiqué dans le tableau suivant :  
  
|typedef|Thread unique|Modèle de thread cloisonné|Modèle de thread libre|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 Utilisez `CComObjectThreadModel` au sein d’une classe d’objet unique. Utilisez `CComGlobalsThreadModel` dans un objet qui est globalement disponible pour votre programme, ou lorsque vous souhaitez protéger des ressources du module entre plusieurs threads.  
  
##  <a name="a-nameccontainedwindowa--ccontainedwindow"></a><a name="ccontainedwindow"></a>CContainedWindow  
 Cette classe est une spécialisation de **CContainedWindowT.**  
  
```   
typedef CContainedWindowT<CWindow> CContainedWindow;   
```  
  
### <a name="remarks"></a>Remarques  
 `CContainedWindow`est une spécialisation de [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md). Si vous souhaitez modifier la classe de base ou traits, utilisez `CContainedWindowT` directement.  
  
##  <a name="a-namecpatha--cpath"></a><a name="cpath"></a>CPath  
 Une spécialisation de [CPathT](../../atl/reference/cpatht-class.md) à l’aide de `CString`.  
  
```   
typedef CPathT<CString> CPath;   
```  
  
##  <a name="a-namecpathaa--cpatha"></a><a name="cpatha"></a>CPathA  
 Une spécialisation de [CPathT](../../atl/reference/cpatht-class.md) à l’aide de `CStringA`.  
  
```   
typedef CPathT<CStringA> CPathA;   
```  
  
##  <a name="a-namecpathwa--cpathw"></a><a name="cpathw"></a>CPathW  
 Une spécialisation de [CPathT](../../atl/reference/cpatht-class.md) à l’aide de `CStringW`.  
  
```   
typedef ATL::CPathT<CStringW> CPathW;   
```  
  
##  <a name="a-namecsimplevalarraya--csimplevalarray"></a><a name="csimplevalarray"></a>CSimpleValArray  
 Représente un tableau pour le stockage des types simples.  
  
```   
#define CSimpleValArray CSimpleArray   
```  
  
### <a name="remarks"></a>Notes  
 `CSimpleValArray`est fourni pour créer et gérer des tableaux contenant les types de données simples. Il s’agit d’une simple #define de [CSimpleArray](../../atl/reference/csimplearray-class.md).  
  
##  <a name="a-namelpcurla--lpcurl"></a><a name="lpcurl"></a>LPCURL  
 Un pointeur vers une constante [CUrl](../../atl/reference/curl-class.md) objet.  
  
```   
typedef const CUrl* LPCURL;   
```  

##  <a name="a-namedefaultthreadtraitsa--defaultthreadtraits"></a><a name="defaultthreadtraits"></a>DefaultThreadTraits
La classe de traits de thread par défaut.

### <a name="syntax"></a>Syntaxe
```  
      #if defined(_MT)  
   typedef CRTThreadTraits DefaultThreadTraits;  
#else  
   typedef Win32ThreadTraits DefaultThreadTraits;  
#endif  
```

## <a name="remarks"></a>Remarques
Si le projet actif utilise la bibliothèque CRT multithread, DefaultThreadTraits est défini comme CRTThreadTraits. Sinon, Win32ThreadTraits est utilisé.
  
##  <a name="a-namelpurla--lpurl"></a><a name="lpurl"></a>LPURL  
 Un pointeur vers un [CUrl](../../atl/reference/curl-class.md) objet.  
  
```   
typedef CUrl* LPURL;   
```  
  
## <a name="see-also"></a>Voir aussi  
 [Composants COM bureau ATL](../../atl/atl-com-desktop-components.md)   
 [Fonctions](../../atl/reference/atl-functions.md)   
 [Variables globales](../../atl/reference/atl-global-variables.md)   
 [Structures](../../atl/reference/atl-structures.md)   
 [Macros](../../atl/reference/atl-macros.md)   
 [Classes](../../atl/reference/atl-classes.md)
