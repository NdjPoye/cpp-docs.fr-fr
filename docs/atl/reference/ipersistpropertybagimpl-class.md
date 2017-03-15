---
title: Classe de IPersistPropertyBagImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPersistPropertyBagImpl
- ATL.IPersistPropertyBagImpl<T>
- ATL::IPersistPropertyBagImpl
- ATL::IPersistPropertyBagImpl<T>
- ATL.IPersistPropertyBagImpl
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 901a6a6bf4097b6aa78a898254766f122bb2f959
ms.lasthandoff: 02/24/2017

---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl (classe)
Cette classe implémente **IUnknown** et permet à un objet enregistrer ses propriétés dans un sac de propriétés fourni par le client.  
  
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
|[IPersistPropertyBagImpl::InitNew](#initnew)|Initialise un objet nouvellement créé. Retourne l’implémentation ATL `S_OK`.|  
|[IPersistPropertyBagImpl::Load](#load)|Charge les propriétés de l’objet à partir d’un jeu de propriétés fourni par le client.|  
|[IPersistPropertyBagImpl::Save](#save)|Enregistre les propriétés de l’objet dans un jeu de propriétés fourni par le client.|  
  
## <a name="remarks"></a>Notes  
 Le [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) interface permet à un objet enregistrer ses propriétés dans un sac de propriétés fourni par le client. Classe `IPersistPropertyBagImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
 **IPersistPropertyBag** fonctionne conjointement avec [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) et [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx). Ces deux interfaces de ce dernier doivent être implémentées par le client. Via `IPropertyBag`, le client enregistre et charge les propriétés individuelles de l’objet. Via **IErrorLog**, l’objet et le client peuvent signaler les erreurs rencontrées.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="a-namegetclassida--ipersistpropertybagimplgetclassid"></a><a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID  
 Récupère le CLSID de l’objet.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinitnewa--ipersistpropertybagimplinitnew"></a><a name="initnew"></a>IPersistPropertyBagImpl::InitNew  
 Initialise un objet nouvellement créé.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameloada--ipersistpropertybagimplload"></a><a name="load"></a>IPersistPropertyBagImpl::Load  
 Charge les propriétés de l’objet à partir d’un jeu de propriétés fourni par le client.  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>Notes  
 ATL utilise le mappage des propriétés de l’objet pour récupérer ces informations.  
  
 Consultez la page [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesavea--ipersistpropertybagimplsave"></a><a name="save"></a>IPersistPropertyBagImpl::Save  
 Enregistre les propriétés de l’objet dans un jeu de propriétés fourni par le client.  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>Notes  
 ATL utilise le mappage des propriétés de l’objet pour stocker ces informations. Par défaut, cette méthode enregistre toutes les propriétés, quelle que soit la valeur de *fSaveAllProperties*.  
  
 Consultez la page [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [BEGIN_PROP_MAP](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

