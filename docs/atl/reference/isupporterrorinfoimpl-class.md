---
title: "ISupportErrorInfoImpl Class | Microsoft Docs"
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
  - "ATL::ISupportErrorInfoImpl<piid>"
  - "ATL::ISupportErrorInfoImpl"
  - "ISupportErrorInfoImpl"
  - "ATL.ISupportErrorInfoImpl<piid>"
  - "ATL.ISupportErrorInfoImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error information, ATL"
  - "ISupportErrorInfo ATL implementation"
  - "ISupportErrorInfoImpl class"
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ISupportErrorInfoImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit une implémentation par défaut d' [ISupportErrorInfo Interface](http://msdn.microsoft.com/fr-fr/42d33066-36b4-4a5b-aa5d-46682e560f32) et peut être utilisée lorsque qu'une seule interface génère des erreurs dans un objet.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template<  
const IID* piid   
>  
class ATL_NO_VTABLE ISupportErrorInfoImpl :  
public ISupportErrorInfo  
```  
  
#### Paramètres  
 `piid`  
 Pointeur vers l'IID d'une interface qui prend en charge [IErrorInfo](http://msdn.microsoft.com/fr-fr/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](../Topic/ISupportErrorInfoImpl::InterfaceSupportsErrorInfo.md)|Indique si l'interface identifiée par `riid` prend en charge l'interface d' [IErrorInfo](http://msdn.microsoft.com/fr-fr/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) .|  
  
## Notes  
 [ISupportErrorInfo Interface](http://msdn.microsoft.com/fr-fr/42d33066-36b4-4a5b-aa5d-46682e560f32) garantit que les informations d'erreur peuvent être retournées au client.  Les objets qui utilisent **IErrorInfo** doivent implémenter **ISupportErrorInfo**.  
  
 La classe `ISupportErrorInfoImpl` fournit une implémentation par défaut d' **ISupportErrorInfo** et peut être utilisée lorsque qu'une seule interface génère des erreurs dans un objet.  Par exemple :  
  
 [!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/CPP/isupporterrorinfoimpl-class_1.h)]  
  
## Hiérarchie d'héritage  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)