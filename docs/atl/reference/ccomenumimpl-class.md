---
title: Classe de CComEnumImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComEnumImpl
- ATL::CComEnumImpl
- CComEnumImpl
dev_langs:
- C++
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 6dc6a8ed6a318642efe58dfb94835d45b2163b54
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenumimpl-class"></a>CComEnumImpl (classe)
Cette classe fournit l’implémentation pour une interface d’énumérateur COM où les éléments en cours d’énumération sont stockés dans un tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Base,
    const IID* piid, class T, class Copy>  
class ATL_NO_VTABLE CComEnumImpl : public Base
```  
  
#### <a name="parameters"></a>Paramètres  
 `Base`  
 Un énumérateur COM ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) interface.  
  
 `piid`  
 Pointeur vers l’ID de l’interface de l’énumérateur.  
  
 `T`  
 Le type d’élément exposé par l’interface de l’énumérateur.  
  
 `Copy`  
 Un homogènes [copier la classe de stratégie](../../atl/atl-copy-policy-classes.md).  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|Constructeur.|  
|[CComEnumImpl :: ~ CComEnumImpl](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComEnumImpl::Clone](#clone)|L’implémentation de [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx).|  
|[CComEnumImpl::Init](#init)|Initialise l’énumérateur.|  
|[CComEnumImpl::Next](#next)|L’implémentation de [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx).|  
|[CComEnumImpl::Reset](#reset)|L’implémentation de [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx).|  
|[CComEnumImpl::Skip](#skip)|L’implémentation de [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx).|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComEnumImpl::m_begin](#m_begin)|Pointeur vers le premier élément du tableau.|  
|[CComEnumImpl::m_dwFlags](#m_dwflags)|Copier les indicateurs passés via `Init`.|  
|[CComEnumImpl::m_end](#m_end)|Pointeur vers l’emplacement situé juste après le dernier élément du tableau.|  
|[CComEnumImpl::m_iter](#m_iter)|Pointeur vers l’élément actuel dans le tableau.|  
|[CComEnumImpl::m_spUnk](#m_spunk)|Le **IUnknown** pointeur de l’objet en fournissant la collection énumérée.|  
  
## <a name="remarks"></a>Remarques  
 `CComEnumImpl`fournit l’implémentation pour une interface d’énumérateur COM où les éléments en cours d’énumération sont stockés dans un tableau. Cette classe est analogue à la `IEnumOnSTLImpl` classe, qui fournit une implémentation d’une interface d’énumérateur basé sur un conteneur de bibliothèque C++ Standard.  
  
> [!NOTE]
>  Pour plus d’informations sur les autres différences entre `CComEnumImpl` et `IEnumOnSTLImpl`, consultez [CComEnumImpl::Init](#init).  
  
 En règle générale, vous allez *pas* devez créer votre propre classe d’énumérateur par dérivation à partir de l’implémentation de cette interface. Si vous souhaitez utiliser un énumérateur fournis par ATL basé sur un tableau, il est plus courant de créer une instance de [CComEnum](../../atl/reference/ccomenum-class.md).  
  
 Toutefois, si vous n’avez pas besoin de fournir un énumérateur personnalisé (par exemple, un qui expose des interfaces en plus de l’interface d’énumérateur), vous pouvez dériver de cette classe. Dans ce cas, il est probable que vous devrez remplacer le [CComEnumImpl::Clone](#clone) méthode pour fournir votre propre implémentation.  
  
 Pour plus d’informations, consultez [Collections et énumérateurs ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `Base`  
  
 `CComEnumImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="a-nameccomenumimpla--ccomenumimplccomenumimpl"></a><a name="ccomenumimpl"></a>CComEnumImpl::CComEnumImpl  
 Constructeur.  
  
```
CComEnumImpl();
```  
  
##  <a name="a-namedtora--ccomenumimplccomenumimpl"></a><a name="dtor"></a>CComEnumImpl :: ~ CComEnumImpl  
 Destructeur.  
  
```
~CComEnumImpl();
```  
  
##  <a name="a-nameinita--ccomenumimplinit"></a><a name="init"></a>CComEnumImpl::Init  
 Vous devez appeler cette méthode avant de passer un pointeur à l’interface de l’énumérateur sur tous les clients.  
  
```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```  
  
### <a name="parameters"></a>Paramètres  
 *begin*  
 Pointeur vers le premier élément du tableau qui contient les éléments à énumérer.  
  
 `end`  
 Pointeur vers l’emplacement situé juste après le dernier élément du tableau qui contient les éléments à énumérer.  
  
 *pUnk*  
 [in] Le **IUnknown** pointeur d’un objet qui doit être maintenu actif pendant la durée de vie de l’énumérateur. Transmettez **NULL** si aucun objet n’existe.  
  
 `flags`  
 Indicateurs qui spécifient si l’énumérateur doit prendre possession du tableau ou faire une copie. Les valeurs possibles sont décrites ci-dessous.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Notes  
 Appelez cette méthode uniquement une fois — initialiser l’énumérateur, utiliser, puis supprimez-le.  
  
 Si vous passez des pointeurs vers les éléments d’un tableau dans un autre objet (et vous dispense de l’énumérateur pour copier les données), vous pouvez utiliser la *pUnk* paramètre pour vous assurer que l’objet et le tableau qu’il contient sont disponibles pour les tant que l’énumérateur a besoin. L’énumérateur conserve simplement une référence COM sur l’objet pour conserver actif. La référence COM est automatiquement libérée lorsque l’énumérateur est détruit.  
  
 Le `flags` paramètre permet de spécifier comment l’énumérateur doit traiter les éléments du tableau passés. `flags`peut prendre l’une des valeurs de la **CComEnumFlags** énumération indiquée ci-dessous :  
  
 `enum CComEnumFlags`  
  
 `{`  
  
 `AtlFlagNoCopy = 0,`  
  
 `AtlFlagTakeOwnership = 2, // BitOwn`  
  
 `AtlFlagCopy = 3           // BitOwn | BitCopy`  
  
 `};`  
  
 **AtlFlagNoCopy** signifie que la durée de vie du tableau n’est pas contrôlée par l’énumérateur. Dans ce cas, soit le tableau sera statique ou l’objet identifié par *pUnk* sera responsable de la libération du tableau lorsqu’il n’est plus nécessaire.  
  
 **AtlFlagTakeOwnership** signifie que la destruction du tableau est contrôlé par l’énumérateur. Dans ce cas, le tableau doit avoir été alloué de manière dynamique à l’aide de **nouveau**. L’énumérateur entraîne la suppression du tableau dans son destructeur. En règle générale, vous pouvez transmettre **NULL** de *pUnk*, bien que vous pouvez passer un pointeur valide si vous souhaitez être averti de la destruction de l’énumérateur pour une raison quelconque.  
  
 **AtlFlagCopy** signifie qu’un nouveau groupe est créé par la copie du tableau passé à `Init`. Durée de vie de la nouvelle baie est contrôlé par l’énumérateur. L’énumérateur entraîne la suppression du tableau dans son destructeur. En règle générale, vous pouvez transmettre **NULL** de *pUnk*, bien que vous pouvez passer un pointeur valide si vous souhaitez être averti de la destruction de l’énumérateur pour une raison quelconque.  
  
> [!NOTE]
>  Le prototype de cette méthode spécifie les éléments du tableau comme étant de type **T**, où **T** a été défini comme un paramètre de modèle à la classe. Il s’agit du même type qui est exposé au moyen de la méthode d’interface COM [CComEnumImpl::Next](#next). Cela est que, contrairement à [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md), cette classe ne prend pas en charge les différents stockages et exposé les types de données. Le type de données des éléments du tableau doit être le même que le type de données exposé à l’aide de l’interface COM.  
  
##  <a name="a-nameclonea--ccomenumimplclone"></a><a name="clone"></a>CComEnumImpl::Clone  
 Cette méthode fournit l’implémentation de la [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) méthode en créant un objet de type `CComEnum`, l’initialiser avec le même tableau et itérateur utilisé par l’objet actuel et le renvoi de l’interface sur l’objet nouvellement créé.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Paramètres  
 `ppEnum`  
 [out] L’interface de l’énumérateur sur un nouvel objet cloné à partir de l’énumérateur en cours.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Notez que les énumérateurs clonés jamais leurs propre copie (ou prendre possession) des données utilisées par l’énumérateur d’origine. Si nécessaire, les énumérateurs clonés conservera l’énumérateur d’origine actif (à l’aide d’une référence COM) pour vous assurer que les données sont disponibles pour tant qu’ils en ont besoin.  
  
##  <a name="a-namemspunka--ccomenumimplmspunk"></a><a name="m_spunk"></a>CComEnumImpl::m_spUnk  
 Ce pointeur intelligent conserve une référence de l’objet passé à [CComEnumImpl::Init](#init), s’assurer qu’il reste actif pendant la durée de vie de l’énumérateur.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
##  <a name="a-namembegina--ccomenumimplmbegin"></a><a name="m_begin"></a>CComEnumImpl::m_begin  
 Pointeur vers l’emplacement situé juste après le dernier élément du tableau qui contient les éléments à énumérer.  
  
```
T* m_begin;
```  
  
##  <a name="a-namemenda--ccomenumimplmend"></a><a name="m_end"></a>CComEnumImpl::m_end  
 Pointeur vers le premier élément du tableau qui contient les éléments à énumérer.  
  
```
T* m_end;
```  
  
##  <a name="a-namemitera--ccomenumimplmiter"></a><a name="m_iter"></a>CComEnumImpl::m_iter  
 Pointeur vers l’élément actuel du tableau contenant les éléments à énumérer.  
  
```
T* m_iter;
```  
  
##  <a name="a-namemdwflagsa--ccomenumimplmdwflags"></a><a name="m_dwflags"></a>CComEnumImpl::m_dwFlags  
 Les indicateurs passés à [CComEnumImpl::Init](#init).  
  
```
DWORD m_dwFlags;
```  
  
##  <a name="a-namenexta--ccomenumimplnext"></a><a name="next"></a>CComEnumImpl::Next  
 Cette méthode fournit l’implémentation de la [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) (méthode).  
  
```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>Paramètres  
 `celt`  
 [in] Le nombre d’éléments demandés.  
  
 `rgelt`  
 [out] Tableau à remplir avec les éléments.  
  
 `pceltFetched`  
 [out] Le nombre d’éléments réellement retournés dans `rgelt`. Cela peut être inférieur à `celt` si moins de `celt` éléments restant dans la liste.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="a-namereseta--ccomenumimplreset"></a><a name="reset"></a>CComEnumImpl::Reset  
 Cette méthode fournit l’implémentation de la [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) (méthode).  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="a-nameskipa--ccomenumimplskip"></a><a name="skip"></a>CComEnumImpl::Skip  
 Cette méthode fournit l’implémentation de la [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) (méthode).  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>Paramètres  
 `celt`  
 [in] Le nombre d’éléments à ignorer.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Retourne E_INVALIDARG si `celt` est égal à zéro, retourne S_FALSE si moins de `celt` les éléments sont retournés, sinon, retourne S_OK.  
  
## <a name="see-also"></a>Voir aussi  
 [IEnumOnSTLImpl (classe)](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum (classe)](../../atl/reference/ccomenum-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

