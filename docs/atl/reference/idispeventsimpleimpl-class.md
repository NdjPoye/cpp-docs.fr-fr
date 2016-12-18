---
title: "IDispEventSimpleImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispEventSimpleImpl"
  - "ATL::IDispEventSimpleImpl"
  - "ATL.IDispEventSimpleImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventSimpleImpl class"
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDispEventSimpleImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des implémentations de méthodes d' `IDispatch` , sans obtenir des informations de type d'une bibliothèque de types.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid  
>  
class ATL_NO_VTABLE IDispEventSimpleImpl :  
public _IDispEventLocator<nID, pdiid>  
```  
  
#### Paramètres  
 `nID`  
 Un identificateur unique de l'objet source.  Lorsque `IDispEventSimpleImpl` est la classe de base pour un contrôle composite, utilisez l'ID de ressource du contrôle contenu souhaité pour ce paramètre.  Dans d'autres cas, utilisez un entier positif arbitraire.  
  
 `T`  
 La classe de l'utilisateur, qui est dérivée d' `IDispEventSimpleImpl`.  
  
 `pdiid`  
 Le pointeur à l'IID de la dispinterface d'événements implémentée par cette classe.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IDispEventSimpleImpl::Advise](../Topic/IDispEventSimpleImpl::Advise.md)|Établit une connexion à la source de l'événement par défaut.|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|Établit une connexion à la source de l'événement.|  
|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|Arrête la connexion à la source de l'événement.|  
|[IDispEventSimpleImpl::GetIDsOfNames](../Topic/IDispEventSimpleImpl::GetIDsOfNames.md)|Retourne **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfo](../Topic/IDispEventSimpleImpl::GetTypeInfo.md)|Retourne **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](../Topic/IDispEventSimpleImpl::GetTypeInfoCount.md)|Retourne **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::Invoke](../Topic/IDispEventSimpleImpl::Invoke.md)|Appelle dans le mappage de récepteur indiqué par gestionnaires d'événements.|  
|[IDispEventSimpleImpl::Unadvise](../Topic/IDispEventSimpleImpl::Unadvise.md)|Arrête la connexion à la source de l'événement par défaut.|  
  
## Notes  
 `IDispEventSimpleImpl` permet d'implémenter une dispinterface d'événements sans qu'il soit nécessaire de fournir le code d'implémentation pour chaque méthode\/événement sur cette interface.  `IDispEventSimpleImpl` fournit des implémentations de méthodes d' `IDispatch` .  Vous devez seulement fournir des implémentations pour les événements qui vous intéressent par la gestion.  
  
 `IDispEventSimpleImpl` fonctionne avec [table de récepteurs d'événements](../Topic/BEGIN_SINK_MAP.md) dans votre classe pour router des événements à la fonction gestionnaire appropriée.  Pour utiliser cette classe :  
  
-   Ajoutez une macro de [SINK\_ENTRY\_INFORMATION](../Topic/SINK_ENTRY_INFO.md) à la table de récepteurs d'événements pour chaque événement sur chaque objet que vous souhaitez gérer.  
  
-   Les informations de type d'approvisionnement pour chaque événement en passant un pointeur vers une structure de [\_ATL\_FUNC\_INFORMATION](../../atl/reference/atl-func-info-structure.md) comme paramètre à chaque entrée.  Sur la plateforme x86, la valeur d' `_ATL_FUNC_INFO.cc` doit être CC\_CDECL avec la méthode d'appel de fonction de rappel du \_\_stdcall.  
  
-   Appelez [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) pour établir la connexion entre l'objet source et la classe de base.  
  
-   Appel [DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) pour arrêter la connexion.  
  
 Vous devez dériver d' `IDispEventSimpleImpl` \(à l'aide d'une valeur unique pour `nID`\) pour chaque objet dont vous devez gérer des événements.  Vous pouvez réutiliser la classe de base par unadvising à un objet source informant ensuite à un objet source différent, mais le nombre maximal d'objets sources qui peuvent être gérés par un objet unique en même temps est limité par le nombre de classes de base d' `IDispEventSimpleImpl` .  
  
 **IDispEventSimplImpl** fournit les mêmes fonctionnalités que [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), à moins qu'il ne pas obtenir les informations de type sur l'interface d'une bibliothèque de types.  Les assistants génèrent un code basé uniquement sur `IDispEventImpl`, mais vous pouvez utiliser `IDispEventSimpleImpl` en ajoutant le code manuellement.  Utilisez `IDispEventSimpleImpl` lorsque vous n'avez pas une bibliothèque de types décrivant l'interface d'événement ou ne souhaitez pas éviter la charge mémoire associée à utiliser la bibliothèque de types.  
  
> [!NOTE]
>  `IDispEventImpl` et `IDispEventSimpleImpl` fournissent leur propre implémentation d' **IUnknown::QueryInterface** ce qui permet à chaque classe de base d' `IDispEventImpl` ou d' `IDispEventSimpleImpl` d'agir en tant qu'identité séparée COM tout en permettant à l'accès direct aux membres de classe dans votre objet COM principal.  
  
 L'implémentation ATL windows embedded CE des récepteurs d'événements ActiveX ne prend en charge que les valeurs de retour de type HRESULT ou void de vos méthodes de gestionnaire d'événements ; toute autre valeur de retour n'est pas prise en charge et son comportement n'est pas défini.  
  
 Pour plus d'informations, consultez l' [IDispEventImpl prenant](../../atl/supporting-idispeventimpl.md).  
  
## Hiérarchie d'héritage  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [\_ATL\_FUNC\_INFO Structure](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl Class](../../atl/reference/idispeventimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [Class Overview](../../atl/atl-class-overview.md)