---
title: Classe de IObjectSafetyImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: cdcc008797e94988fb42fd6239603fa300a84233
ms.lasthandoff: 03/31/2017

---
# <a name="iobjectsafetyimpl-class"></a>Classe de IObjectSafetyImpl
Cette classe fournit une implémentation par défaut de la `IObjectSafety` interface pour permettre à un client récupérer et définir des niveaux de sécurité d’un objet.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Spécifie les options de sécurité pris en charge pour le contrôle. Peut avoir l'une des valeurs suivantes :  
  
- **INTERFACESAFE_FOR_UNTRUSTED_CALLER** l’interface identifiée par le [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) paramètre `riid` doivent être apportées sécurisé pour le script.  
  
- **INTERFACESAFE_FOR_UNTRUSTED_DATA** l’interface identifiée par le `SetInterfaceSafetyOptions` paramètre `riid` convient sécurisés pour les données non fiables lors de l’initialisation.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Récupère les options de sécurité pris en charge par l’objet, ainsi que les options de sécurité actuellement définies pour l’objet.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Rend l’objet sécurisé pour l’initialisation ou de script.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Stocke le niveau de sécurité de l’objet actuel.|  
  
## <a name="remarks"></a>Remarques  
 Classe `IObjectSafetyImpl` fournit une implémentation par défaut de `IObjectSafety`. Le `IObjectSafety` interface permet à un client récupérer et définir des niveaux de sécurité d’un objet. Par exemple, un navigateur web peut appeler **IObjectSafety::SetInterfaceSafetyOptions** pour rendre un contrôle pour l’initialisation ou sécurisé pour le script.  
  
 Notez que l’utilisation du [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) macro avec le **CATID_SafeForScripting** et **CATID_SafeForInitializing** catégories de composants vous permet également de spécifier qu’un composant est sécurisé.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions  
 Récupère les options de sécurité pris en charge par l’objet, ainsi que les options de sécurité actuellement définies pour l’objet.  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>Remarques  
 L’implémentation retourne les valeurs appropriées pour n’importe quelle interface prise en charge par l’implémentation de l’objet de **IUnknown::QueryInterface**.  
  
> [!IMPORTANT]
>  Tout objet qui prend en charge `IObjectSafety` est responsable de sa propre sécurité et de n’importe quel objet, elle délègue. Le programmeur doit prendre en considération les questions découlant de l’exécution de code dans le contexte de l’utilisateur, de scripts entre sites et effectuer une vérification de la zone appropriée.  
  
 Consultez [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety  
 Stocke le niveau de sécurité de l’objet actuel.  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterfaceSafetyOptions  
 Rend l’objet sécurisé pour l’initialisation ou de scripts en définissant le [m_dwCurrentSafety](#m_dwcurrentsafety) membre à la valeur appropriée.  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>Remarques  
 L’implémentation retourne **E_NOINTERFACE** pour toute interface ne pas pris en charge par l’implémentation de l’objet de **IUnknown::QueryInterface**.  
  
> [!IMPORTANT]
>  Tout objet qui prend en charge `IObjectSafety` est responsable de sa propre sécurité et de n’importe quel objet, elle délègue. Le programmeur doit prendre en considération les questions découlant de l’exécution de code dans le contexte de l’utilisateur, de scripts entre sites et effectuer une vérification de la zone appropriée.  
  
 Consultez [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Interface IObjectSafety](https://msdn.microsoft.com/library/aa768224.aspx)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
