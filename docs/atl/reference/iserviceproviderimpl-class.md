---
title: "IServiceProviderImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl"
  - "ATL::IServiceProviderImpl"
  - "IServiceProviderImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IServiceProvider (interface), ATL (implémentation)"
  - "IServiceProviderImpl class"
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IServiceProviderImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit une implémentation par défaut de l'interface d' `IServiceProvider` .  
  
## Syntaxe  
  
```  
  
      template <  
   class T  
>   
class ATL_NO_VTABLE IServiceProviderImpl :  
   public IServiceProvider  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IServiceProviderImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IServiceProviderImpl::QueryService](../Topic/IServiceProviderImpl::QueryService.md)|Crée ou accède au service spécifié et retourne un pointeur d'interface vers l'interface spécifiée pour le service.|  
  
## Notes  
 L'interface d' `IServiceProvider` localise un service spécifié par son GUID et retourne le pointeur d'interface de l'interface demandée sur le service.  La classe `IServiceProviderImpl` fournit une implémentation par défaut de cette interface.  
  
 **IServiceProviderImpl** spécifie une méthode : [QueryService](../Topic/IServiceProviderImpl::QueryService.md), qui crée ou accède au service spécifié et retourne un pointeur d'interface vers l'interface spécifiée pour le service.  
  
 `IServiceProviderImpl` utilise un mappage de service, à partir [BEGIN\_SERVICE\_MAP](../Topic/BEGIN_SERVICE_MAP.md) jusqu'à la [END\_SERVICE\_MAP](../Topic/END_SERVICE_MAP.md).  
  
 Le mappage de service contient deux entrées : [SERVICE\_ENTRY](../Topic/SERVICE_ENTRY.md), qui indique un identificateur de service spécifié \(SID\) pris en charge par l'objet, et [SERVICE\_ENTRY\_CHAIN](../Topic/SERVICE_ENTRY_CHAIN.md), qui appelle `QueryService` pour chaîner à un autre objet.  
  
## Hiérarchie d'héritage  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)