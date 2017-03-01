---
title: Classe de IPersistStorageImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IPersistStorageImpl
- ATL::IPersistStorageImpl<T>
- ATL.IPersistStorageImpl<T>
- IPersistStorageImpl
- ATL.IPersistStorageImpl
dev_langs:
- C++
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a5a855f81072316510efb47c3f9650a5feafa39b
ms.lasthandoff: 02/24/2017

---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl (classe)
Cette classe implémente le [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) interface.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IPersistStorageImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|Récupère le CLSID de l’objet.|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Demande à l’objet pour libérer tous les objets de stockage et de passer en mode HandsOff. Retourne l’implémentation ATL `S_OK`.|  
|[IPersistStorageImpl::InitNew](#initnew)|Initialise un nouveau stockage.|  
|[IPersistStorageImpl::IsDirty](#isdirty)|Vérifie si les données de l’objet a changé depuis son dernier enregistrement.|  
|[IPersistStorageImpl::Load](#load)|Charge les propriétés de l’objet à partir du stockage spécifié.|  
|[IPersistStorageImpl::Save](#save)|Enregistre les propriétés de l’objet dans le stockage spécifié.|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Avertit un objet qu’il peut retourner en mode Normal pour écrire dans son objet de stockage. Retourne l’implémentation ATL `S_OK`.|  
  
## <a name="remarks"></a>Remarques  
 `IPersistStorageImpl`implémente le [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) d’interface, ce qui permet à un client de demander à ce que votre charge de l’objet et enregistrer ses données persistantes à l’aide d’un stockage.  
  
 L’implémentation de cette classe requiert la classe `T` pour rendre une implémentation de la `IPersistStreamInit` interface disponible via `QueryInterface`. En général, cela signifie que cette classe `T` doit dériver de [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), fournir une entrée pour `IPersistStreamInit` dans les [mappage COM](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333)et utiliser un [mappage des propriétés](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427) pour décrire les données persistantes de la classe.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="a-namegetclassida--ipersiststorageimplgetclassid"></a><a name="getclassid"></a>IPersistStorageImpl::GetClassID  
 Récupère le CLSID de l’objet.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehandsoffstoragea--ipersiststorageimplhandsoffstorage"></a><a name="handsoffstorage"></a>IPersistStorageImpl::HandsOffStorage  
 Demande à l’objet pour libérer tous les objets de stockage et de passer en mode HandsOff.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinitnewa--ipersiststorageimplinitnew"></a><a name="initnew"></a>IPersistStorageImpl::InitNew  
 Initialise un nouveau stockage.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Remarques  
 L’implémentation ATL délègue à la [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) interface.  
  
 Consultez la page [IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisdirtya--ipersiststorageimplisdirty"></a><a name="isdirty"></a>IPersistStorageImpl::IsDirty  
 Vérifie si les données de l’objet a changé depuis son dernier enregistrement.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Notes  
 L’implémentation ATL délègue à la [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) interface.  
  
 Consultez la page [IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameloada--ipersiststorageimplload"></a><a name="load"></a>IPersistStorageImpl::Load  
 Charge les propriétés de l’objet à partir du stockage spécifié.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Notes  
 L’implémentation ATL délègue à la [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) interface. **Charge** utilise un flux nommé « Contenu » pour récupérer les données de l’objet. Le [enregistrer](#save) méthode crée à l’origine de ce flux.  
  
 Consultez la page [IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesavea--ipersiststorageimplsave"></a><a name="save"></a>IPersistStorageImpl::Save  
 Enregistre les propriétés de l’objet dans le stockage spécifié.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Remarques  
 L’implémentation ATL délègue à la [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) interface. Lors de la **enregistrer** est d’abord appelée, elle crée un flux nommé « Contenu » sur le stockage spécifié. Ce flux est ensuite utilisé dans les appels ultérieurs à **enregistrer** et dans les appels à [charge](#load).  
  
 Consultez la page [IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesavecompleteda--ipersiststorageimplsavecompleted"></a><a name="savecompleted"></a>IPersistStorageImpl::SaveCompleted  
 Avertit un objet qu’il peut retourner en mode Normal pour écrire dans son objet de stockage.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Les flux et les stockages](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl (classe)](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl (classe)](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

