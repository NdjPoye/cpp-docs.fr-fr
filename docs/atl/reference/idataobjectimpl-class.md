---
title: Classe de IDataObjectImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDataObjectImpl
dev_langs:
- C++
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: afd5fe7cf9bbac582e59ed46dc33e99de5fc2876
ms.lasthandoff: 02/24/2017

---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl (classe)
Cette classe fournit des méthodes pour prendre en charge le transfert de données uniforme et la gestion des connexions.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IDataObjectImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|Établit une connexion entre l’objet de données et un récepteur de notifications. Ainsi, le récepteur de notifications recevoir des notifications de modifications dans l’objet.|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|Met fin à une connexion précédemment établie par `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Crée un énumérateur pour itérer sur les connexions de notifications actuelles.|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Crée un énumérateur pour itérer au sein du **FORMATETC** structures pris en charge par l’objet de données. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|Envoie une notification de modification à chaque récepteur de notifications.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Récupère un logiquement équivalente **FORMATETC** structure à celui qui est plus complexe. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::GetData](#getdata)|Transfère des données à partir de l’objet de données au client. Les données sont décrites dans un **FORMATETC** de la structure et est transférée via un **STGMEDIUM** structure.|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|Semblable à `GetData`, hormis le fait que le client doit allouer la **STGMEDIUM** structure. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|Détermine si l’objet de données prend en charge un particulier **FORMATETC** structure de transfert de données. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IDataObjectImpl::SetData](#setdata)|Transfère des données à partir du client à l’objet de données. Retourne l’implémentation ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Remarques  
 Le [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) interface fournit des méthodes pour prendre en charge le transfert de données uniforme. `IDataObject`utilise les structures du format standard [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) et [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) pour récupérer et stocker les données.  
  
 `IDataObject`gère également les connexions pour informer les récepteurs pour gérer les notifications de modification de données. Le client peut recevoir des notifications de modification de données à partir de l’objet de données, le client doit implémenter les [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) interface sur un objet appelé un récepteur de notifications. Lorsque le client appelle ensuite **IDataObject::DAdvise**, une connexion est établie entre l’objet de données et le récepteur de notifications.  
  
 Classe `IDataObjectImpl` fournit une implémentation par défaut de `IDataObject` et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="a-namedadvisea--idataobjectimpldadvise"></a><a name="dadvise"></a>IDataObjectImpl::DAdvise  
 Établit une connexion entre l’objet de données et un récepteur de notifications.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Remarques  
 Ainsi, le récepteur de notifications recevoir des notifications de modifications dans l’objet.  
  
 Pour terminer la connexion, appelez [DUnadvise](#dunadvise).  
  
 Consultez la page [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedunadvisea--idataobjectimpldunadvise"></a><a name="dunadvise"></a>IDataObjectImpl::DUnadvise  
 Met fin à une connexion précédemment établie par [DAdvise](#dadvise).  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameenumdadvisea--idataobjectimplenumdadvise"></a><a name="enumdadvise"></a>IDataObjectImpl::EnumDAdvise  
 Crée un énumérateur pour itérer sur les connexions de notifications actuelles.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameenumformatetca--idataobjectimplenumformatetc"></a><a name="enumformatetc"></a>IDataObjectImpl::EnumFormatEtc  
 Crée un énumérateur pour itérer au sein du **FORMATETC** structures pris en charge par l’objet de données.  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
##  <a name="a-namefiredatachangea--idataobjectimplfiredatachange"></a><a name="firedatachange"></a>IDataObjectImpl::FireDataChange  
 Envoie une notification de modification à chaque récepteur de notifications en cours de gestion.  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="a-namegetcanonicalformatetca--idataobjectimplgetcanonicalformatetc"></a><a name="getcanonicalformatetc"></a>IDataObjectImpl::GetCanonicalFormatEtc  
 Récupère un logiquement équivalente **FORMATETC** structure à celui qui est plus complexe.  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdataa--idataobjectimplgetdata"></a><a name="getdata"></a>IDataObjectImpl::GetData  
 Transfère des données à partir de l’objet de données au client.  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>Remarques  
 Le *pformatetcIn* paramètre doit spécifier un type de support de stockage de **TYMED_MFPICT**.  
  
 Consultez la page [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdataherea--idataobjectimplgetdatahere"></a><a name="getdatahere"></a>IDataObjectImpl::GetDataHere  
 Semblable à `GetData`, hormis le fait que le client doit allouer la **STGMEDIUM** structure.  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IDataObject::GetDataHere a](http://msdn.microsoft.com/library/windows/desktop/ms687266) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namequerygetdataa--idataobjectimplquerygetdata"></a><a name="querygetdata"></a>IDataObjectImpl::QueryGetData  
 Détermine si l’objet de données prend en charge un particulier **FORMATETC** structure de transfert de données.  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetdataa--idataobjectimplsetdata"></a><a name="setdata"></a>IDataObjectImpl::SetData  
 Transfère des données à partir du client à l’objet de données.  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

