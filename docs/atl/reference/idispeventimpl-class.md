---
title: "IDispEventImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl class"
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IDispEventImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des implémentations de méthodes d' `IDispatch` .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid= &IID_NULL,  
const GUID* plibid= &GUID_NULL,  
WORD wMajor= 0,  
WORD wMinor= 0,  
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE IDispEventImpl :  
public IDispEventSimpleImpl<nID, T, pdiid>  
```  
  
#### Paramètres  
 `nID`  
 Un identificateur unique de l'objet source.  Lorsque `IDispEventImpl` est la classe de base pour un contrôle composite, utilisez l'ID de ressource du contrôle contenu souhaité pour ce paramètre.  Dans d'autres cas, utilisez un entier positif arbitraire.  
  
 `T`  
 La classe de l'utilisateur, qui est dérivée d' `IDispEventImpl`.  
  
 `pdiid`  
 Le pointeur à l'IID de la dispinterface d'événements implémentée par cette classe.  Cette interface doit être définie dans la bibliothèque de types dénotée par `plibid`, `wMajor`, et `wMinor`.  
  
 `plibid`  
 Un pointeur vers la bibliothèque de types qui définit l'interface de dispatch a globale pointe vers `pdiid`.  Si **&GUID\_NULL**, la bibliothèque de types est chargé d'approvisionnement d'objet des événements.  
  
 `wMajor`  
 Version principale de la bibliothèque de types.  La valeur par défaut est 0.  
  
 `wMinor`  
 Version secondaire de la bibliothèque de types.  La valeur par défaut est 0.  
  
 `tihclass`  
 La classe utilisée pour gérer les informations de type pour `T`.  La valeur par défaut est une classe de type `CComTypeInfoHolder`; toutefois, vous pouvez remplacer ce paramètre de modèle en fournissant une classe d'un type autre que `CComTypeInfoHolder`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[IDispEventImpl::\_tihclass](../../atl/reference/idispeventimpl-class.md)|La classe utilisée pour gérer les informations de type.  Par défaut, `CComTypeInfoHolder`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[IDispEventImpl::IDispEventImpl](../Topic/IDispEventImpl::IDispEventImpl.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](../Topic/IDispEventImpl::GetFuncInfoFromId.md)|Localise l'index de la fonction de l'identificateur spécifié d'expédition.|  
|[IDispEventImpl::GetIDsOfNames](../Topic/IDispEventImpl::GetIDsOfNames.md)|Mappe un membre unique et un jeu facultatif de noms d'argument à un ensemble correspondant de Dispid entier.|  
|[IDispEventImpl::GetTypeInfo](../Topic/IDispEventImpl::GetTypeInfo.md)|Extrait les informations de type d'un objet.|  
|[IDispEventImpl::GetTypeInfoCount](../Topic/IDispEventImpl::GetTypeInfoCount.md)|Récupère le nombre d'interfaces des informations de type.|  
|[IDispEventImpl::GetUserDefinedType](../Topic/IDispEventImpl::GetUserDefinedType.md)|Récupère le type de base d'un type défini par l'utilisateur.|  
  
## Notes  
 `IDispEventImpl` permet d'implémenter une dispinterface d'événements sans qu'il soit nécessaire de fournir le code d'implémentation pour chaque méthode\/événement sur cette interface.  `IDispEventImpl` fournit des implémentations de méthodes d' `IDispatch` .  Vous devez seulement fournir des implémentations pour les événements qui vous intéressent par la gestion.  
  
 `IDispEventImpl` fonctionne avec [table de récepteurs d'événements](../Topic/BEGIN_SINK_MAP.md) dans votre classe pour router des événements à la fonction gestionnaire appropriée.  Pour utiliser cette classe :  
  
 Ajoutez une macro de [SINK\_ENTRY](../Topic/SINK_ENTRY.md) ou de [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md) à la table de récepteurs d'événements pour chaque événement sur chaque objet que vous souhaitez gérer.  Lorsque vous utilisez `IDispEventImpl` comme classe de base d'un contrôle composite, vous pouvez appeler [AtlAdviseSinkMap](../Topic/AtlAdviseSinkMap.md) pour générer et arrêter la connexion avec les sources d'événements pour toute la carte du récepteur d'entrées dans le.  Dans d'autres cas, ou pour un contrôle, un appel supérieurs [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) pour établir la connexion entre l'objet source et la classe de base.  Appel [DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) pour arrêter la connexion.  
  
 Vous devez dériver d' `IDispEventImpl` \(à l'aide d'une valeur unique pour `nID`\) pour chaque objet dont vous devez gérer des événements.  Vous pouvez réutiliser la classe de base par unadvising à un objet source informant ensuite à un objet source différent, mais le nombre maximal d'objets sources qui peuvent être gérés par un objet unique en même temps est limité par le nombre de classes de base d' `IDispEventImpl` .  
  
 `IDispEventImpl` fournit les mêmes fonctionnalités que [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), à moins qu'il puisse obtenir des informations de type sur l'interface d'une bibliothèque de types plutôt que l'ayant l'a fourni comme pointeur vers une structure de [\_ATL\_FUNC\_INFORMATION](../../atl/reference/atl-func-info-structure.md) .  Utilisez `IDispEventSimpleImpl` lorsque vous n'avez pas une bibliothèque de types décrivant l'interface d'événement ou ne souhaitez pas éviter la charge mémoire associée à utiliser la bibliothèque de types.  
  
> [!NOTE]
>  `IDispEventImpl` et `IDispEventSimpleImpl` fournissent leur propre implémentation d' **IUnknown::QueryInterface** ce qui permet à chaque classe de base d' `IDispEventImpl` et d' `IDispEventSimpleImpl` d'agir en tant qu'identité séparée COM tout en permettant à l'accès direct aux membres de classe dans votre objet COM principal.  
  
 L'implémentation ATL windows embedded CE des récepteurs d'événements ActiveX ne prend en charge que les valeurs de retour de type HRESULT ou void de vos méthodes de gestionnaire d'événements ; toute autre valeur de retour n'est pas prise en charge et son comportement n'est pas défini.  
  
 Pour plus d'informations, consultez l' [IDispEventImpl prenant](../../atl/supporting-idispeventimpl.md).  
  
## Hiérarchie d'héritage  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [\_ATL\_FUNC\_INFO Structure](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl Class](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY](../Topic/SINK_ENTRY.md)   
 [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [Class Overview](../../atl/atl-class-overview.md)