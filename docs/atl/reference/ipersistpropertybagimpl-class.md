---
title: Classe de IPersistPropertyBagImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
dev_langs:
- C++
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: abef2ffa759cf74ee2316c7e0c9dd84f5c76b1d7
ms.contentlocale: fr-fr
ms.lasthandoff: 03/31/2017

---
# <a name="ipersistpropertybagimpl-class"></a>Classe de IPersistPropertyBagImpl
Cette classe implémente **IUnknown** et permet à un objet enregistrer ses propriétés à un jeu de propriétés de fourni par le client.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IPersistPropertyBagImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Récupère le CLSID de l’objet.|  
|[IPersistPropertyBagImpl::InitNew](#initnew)|Initialise un objet nouvellement créé. L’implémentation ATL retourne `S_OK`.|  
|[IPersistPropertyBagImpl::Load](#load)|Charge les propriétés de l’objet à partir d’un jeu de propriétés de fourni par le client.|  
|[IPersistPropertyBagImpl::Save](#save)|Enregistre les propriétés de l’objet dans un jeu de propriétés de fourni par le client.|  
  
## <a name="remarks"></a>Remarques  
 Le [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) interface permet à un objet enregistrer ses propriétés à un jeu de propriétés de fourni par le client. Classe `IPersistPropertyBagImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations pour le vidage de builds périphérique en mode débogage.  
  
 **IPersistPropertyBag** fonctionne conjointement avec [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) et [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx). Ces deux interfaces ce dernier doivent être implémentées par le client. Via `IPropertyBag`, le client enregistre et charge les propriétés individuelles de l’objet. Via **IErrorLog**, l’objet et le client peuvent signaler les erreurs rencontrées.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID  
 Récupère le CLSID de l’objet.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="initnew"></a>IPersistPropertyBagImpl::InitNew  
 Initialise un objet nouvellement créé.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
### <a name="remarks"></a>Remarques  
 Consultez [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="load"></a>IPersistPropertyBagImpl::Load  
 Charge les propriétés de l’objet à partir d’un jeu de propriétés de fourni par le client.  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>Remarques  
 ATL utilise le mappage des propriétés de l’objet pour récupérer ces informations.  
  
 Consultez [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="save"></a>IPersistPropertyBagImpl::Save  
 Enregistre les propriétés de l’objet dans un jeu de propriétés de fourni par le client.  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>Remarques  
 ATL utilise le mappage des propriétés de l’objet pour stocker ces informations. Par défaut, cette méthode enregistre toutes les propriétés, quelle que soit la valeur de *fSaveAllProperties*.  
  
 Consultez [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

