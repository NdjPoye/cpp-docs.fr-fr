---
title: IDispEventImpl (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: 22
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
ms.openlocfilehash: 235955f8573ae7e430be3de2a96efdd7496d15de
ms.lasthandoff: 02/24/2017

---
# <a name="idispeventimpl-class"></a>IDispEventImpl (classe)
Cette classe fournit des implémentations de la `IDispatch` méthodes.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```  
  
#### <a name="parameters"></a>Paramètres  
 `nID`  
 Identificateur unique de l’objet source. Lorsque `IDispEventImpl` est la classe de base pour un contrôle composite, utilisez l’ID de ressource, le contrôle de contenu souhaitée pour ce paramètre. Dans d’autres cas, utilisez un entier positif aléatoire.  
  
 `T`  
 Classe de l’utilisateur, qui est dérivée de `IDispEventImpl`.  
  
 `pdiid`  
 Pointeur vers l’IID de l’interface des événements implémentée par cette classe. Cette interface doit être définie dans la bibliothèque de types dénotée par `plibid`, `wMajor`, et `wMinor`.  
  
 `plibid`  
 Un pointeur vers la bibliothèque de types qui définit l’interface de dispatch désigné par `pdiid`. Si **se GUID_NULL**, la bibliothèque de types est chargée à partir de l’objet source d’événements.  
  
 `wMajor`  
 La version principale de la bibliothèque de types. La valeur par défaut est 0.  
  
 `wMinor`  
 La version secondaire de la bibliothèque de types. La valeur par défaut est 0.  
  
 `tihclass`  
 La classe utilisée pour gérer les informations de type `T`. La valeur par défaut est une classe de type `CComTypeInfoHolder`; Toutefois, vous pouvez remplacer ce paramètre de modèle en fournissant une classe d’un type autre que `CComTypeInfoHolder`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|La classe utilisée pour gérer les informations de type. Par défaut, `CComTypeInfoHolder`.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Recherche l’index de la fonction de l’identificateur de dispatch spécifié.|  
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Mappe un membre unique et un jeu facultatif de noms d’arguments avec un jeu correspondant d’entier DISPID.|  
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Récupère les informations de type pour un objet.|  
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Récupère le nombre d’interfaces d’informations de type.|  
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Récupère le type de base d’un type défini par l’utilisateur.|  
  
## <a name="remarks"></a>Remarques  
 `IDispEventImpl`fournit un moyen d’implémenter une interface des événements sans avoir à fournir le code d’implémentation pour chaque méthode/événement sur cette interface. `IDispEventImpl`Fournit des implémentations de la `IDispatch` méthodes. Vous devez uniquement fournir des implémentations pour les événements que vous êtes intéressé par la gestion.  
  
 `IDispEventImpl`fonctionne conjointement avec le [table de récepteur d’événements](http://msdn.microsoft.com/library/32542b3d-ac43-4139-8ac4-41c48481744f) dans votre classe pour router les événements vers la fonction gestionnaire appropriée. Pour utiliser cette classe :  
  

 Ajouter un [aide de SINK_ENTRY](http://msdn.microsoft.com/library/33a5fff6-5248-47c0-8cf4-8bdf760e86e5) ou [SINK_ENTRY_EX](http://msdn.microsoft.com/library/e1d14342-838f-4791-ac2f-5dae2801c1ac) (macro) à la table de récepteur d’événements pour chaque événement sur chaque objet que vous souhaitez gérer. Lorsque vous utilisez `IDispEventImpl` une classe de base d’un contrôle composite, vous pouvez appeler la méthode [AtlAdviseSinkMap](http://msdn.microsoft.com/library/0757a6af-3de3-4179-8b4f-ccd137d919b4) pour établir et rompre la connexion avec les sources d’événements pour toutes les entrées de table de récepteur de l’événement. Dans d’autres cas, ou pour un meilleur contrôle, appelez [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) pour établir la connexion entre l’objet source et la classe de base. Appelez [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) pour rompre la connexion.  

  
 Vous devez dériver de `IDispEventImpl` (à l’aide d’une valeur unique pour `nID`) pour chaque objet pour lequel vous devez gérer des événements. Vous pouvez réutiliser la classe de base en désinformation sur objet une seule source puis conseiller par rapport à un objet source différente, mais le nombre maximal d’objets source qui peuvent être gérés par un seul objet à la fois est limité par le nombre de `IDispEventImpl` classes de base.  
  
 `IDispEventImpl`fournit les mêmes fonctionnalités que [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), sauf qu’il obtient le type d’informations sur l’interface à partir d’une bibliothèque de types au lieu qu’il est fourni comme un pointeur vers un [les structures _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) structure. Utilisez `IDispEventSimpleImpl` lorsque vous ne disposez d’une bibliothèque de types décrivant l’interface d’événement ni pour éviter la surcharge associée à l’aide de la bibliothèque de types.  
  
> [!NOTE]
> `IDispEventImpl`et `IDispEventSimpleImpl` fournir leur propre implémentation de **IUnknown::QueryInterface** chaque activation `IDispEventImpl` et `IDispEventSimpleImpl` classe d’agir comme une identité distincte de COM tout en permettant un accès direct aux membres de classe dans votre objet COM principal de base.  
  
 Implémentation de CE ATL de ActiveX événement récepteurs uniquement prend en charge valeurs de retour de type HRESULT ou void à partir de vos méthodes de gestionnaire d’événements ; toute autre valeur de retour non pris en charge et son comportement est indéfini.  
  
 Pour plus d’informations, consultez [prise en charge de IDispEventImpl](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="a-namegetfuncinfofromida--idispeventimplgetfuncinfofromid"></a><a name="getfuncinfofromid"></a>IDispEventImpl::GetFuncInfoFromId  
 Recherche l’index de la fonction de l’identificateur de dispatch spécifié.  
  
```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Une référence à l’ID de la fonction.  
  
 *dispidMember*  
 [in] L’ID de dispatch de la fonction.  
  
 `lcid`  
 [in] Contexte des paramètres régionaux de l’ID de fonction.  
  
 `info`  
 [in] La structure indiquant comment la fonction est appelée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="a-namegetidsofnamesa--idispeventimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames  
 Mappe un membre unique et un jeu facultatif de noms d’arguments avec un jeu correspondant d’entier DISPID, qui peut être utilisé dans les appels ultérieurs à [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IDispatch::GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettypeinfoa--idispeventimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo  
 Récupère les informations de type pour un objet, qui peuvent être utilisées ensuite pour obtenir les informations de type d'une interface.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegettypeinfocounta--idispeventimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount  
 Récupère le nombre d'interfaces d'informations de type fourni par un objet (0 ou 1).  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetuserdefinedtypea--idispeventimplgetuserdefinedtype"></a><a name="getuserdefinedtype"></a>IDispEventImpl::GetUserDefinedType  
 Récupère le type de base d’un type défini par l’utilisateur.  
  
```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```  
  
### <a name="parameters"></a>Paramètres  
 `pTI`  
 [in] Un pointeur vers le [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) interface qui contient le type défini par l’utilisateur.  
  
 *hrt*  
 [in] Handle de la description du type à récupérer.  
  
### <a name="return-value"></a>Valeur de retour  
 Le type variant.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [ITypeInfo::GetRefTypeInfo a](http://msdn.microsoft.com/en-us/61d3b31d-6591-4e55-9e82-5246a168be00).  
  
##  <a name="a-nameidispeventimpla--idispeventimplidispeventimpl"></a><a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl  
 Constructeur. Stocke les valeurs des paramètres du modèle de classe `plibid`, `pdiid`, `wMajor`, et `wMinor`.  
  
```
IDispEventImpl();
```  
  
##  <a name="a-nametihclassa--idispeventimpltihclass"></a><a name="tihclass"></a>IDispEventImpl::tihclass  
 Ce typedef est une instance de la classe du paramètre de modèle `tihclass`.  
  
```
typedef tihclass _tihclass;
```  
  
### <a name="remarks"></a>Remarques  
 Par défaut, la classe est `CComTypeInfoHolder`. `CComTypeInfoHolder`gère les informations de type pour la classe.  
  
## <a name="see-also"></a>Voir aussi  
 [Les structures _ATL_FUNC_INFO structure](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl (classe)](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl (classe)](../../atl/reference/idispeventsimpleimpl-class.md)   
 [AIDE DE SINK_ENTRY](http://msdn.microsoft.com/library/33a5fff6-5248-47c0-8cf4-8bdf760e86e5)   
 [SINK_ENTRY_EX](http://msdn.microsoft.com/library/e1d14342-838f-4791-ac2f-5dae2801c1ac)   
 [MACRO SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
