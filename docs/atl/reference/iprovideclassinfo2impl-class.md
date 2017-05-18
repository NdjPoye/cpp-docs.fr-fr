---
title: Classe de IProvideClassInfo2Impl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
dev_langs:
- C++
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 0d3bed0f625e396b63ada19ded02ba9ad3b697b0
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl (classe)
Cette classe fournit une implémentation par défaut de la [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) et [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) méthodes.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>  
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```  
  
#### <a name="parameters"></a>Paramètres  
 *pcoclsid*  
 Pointeur vers l’identificateur de la coclasse.  
  
 *psrcid*  
 Pointeur vers l’identificateur par défaut de la coclasse sortant dispinterface.  
  
 `plibid`  
 Pointeur vers le LIBID de la bibliothèque de types qui contient des informations sur l’interface. Par défaut, la bibliothèque de types de niveau serveur est passée.  
  
 `wMajor`  
 La version principale de la bibliothèque de types. La valeur par défaut est 1.  
  
 `wMinor`  
 La version secondaire de la bibliothèque de types. La valeur par défaut est 0.  
  
 `tihclass`  
 La classe utilisée pour gérer les informations de type de la coclasse. La valeur par défaut est `CComTypeInfoHolder`.  
  
## <a name="members"></a>Membres  
  
### <a name="constructors"></a>Constructeurs  
  
|Nom|Description|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Récupère un **ITypeInfo** pointeur vers les informations de type de la coclasse.|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Récupère le GUID pour dispinterface sortant de l’objet.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|Gère les informations de type pour la coclasse.|  
  
## <a name="remarks"></a>Notes  
 Le [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) interface étend [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) en ajoutant le `GetGUID` (méthode). Cette méthode permet à un client récupérer sortant IID d’interface un objet pour son jeu d’événements par défaut. Classe `IProvideClassInfo2Impl` fournit une implémentation par défaut de la **IProvideClassInfo** et `IProvideClassInfo2` méthodes.  
  
 `IProvideClassInfo2Impl`contient un membre statique de type `CComTypeInfoHolder` qui gère les informations de type pour la coclasse.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo  
 Récupère un `ITypeInfo` pointeur vers les informations de type de la coclasse.  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IProvideClassInfo::GetClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms690192) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getguid"></a>IProvideClassInfo2Impl::GetGUID  
 Récupère le GUID pour dispinterface sortant de l’objet.  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 Constructeur.  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>Notes  
 Appels `AddRef` sur la [_tih](#_tih) membre. Le destructeur appelle **version**.  
  
##  <a name="_tih"></a>IProvideClassInfo2Impl::_tih  
 Ce membre de données statique est une instance du paramètre de modèle de classe, `tihclass`, qui par défaut est `CComTypeInfoHolder`.  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>Notes  
 `_tih`gère les informations de type pour la coclasse.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

