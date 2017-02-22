---
title: "IPointerInactiveImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPointerInactiveImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inactive objects"
  - "IPointerInactive ATL implementation"
  - "IPointerInactiveImpl class"
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# IPointerInactiveImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et les méthodes d'interface d' [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template< class   
      T  
      >  
class IPointerInactiveImpl  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IPointerInactiveImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IPointerInactiveImpl::GetActivationPolicy](../Topic/IPointerInactiveImpl::GetActivationPolicy.md)|Extrait la stratégie en cours de activation de l'objet.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveMouseMove](../Topic/IPointerInactiveImpl::OnInactiveMouseMove.md)|Informe l'objet que le pointeur de la souris a atteint dessus, indiquant l'objet peut déclencher des événements de souris.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveSetCursor](../Topic/IPointerInactiveImpl::OnInactiveSetCursor.md)|Place le pointeur de la souris pour l'objet inactif.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
  
## Notes  
 Un objet est inactif un qui est chargé ou simplement exécuter.  Contrairement à un objet actif, un objet inactif ne peut pas recevoir des messages de clavier et de souris windows.  Par conséquent, les objets inactifs utilisent moins de ressources et sont généralement plus efficaces.  
  
 L'interface d' [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) permet à un objet pour prendre en charge un niveau minimal d'interaction souris tout en restant inactive.  Cette fonctionnalité est particulièrement utile pour les contrôles.  
  
 La classe `IPointerInactiveImpl` implémente les méthodes d' `IPointerInactive` en retournant simplement **E\_NOTIMPL**.  Toutefois, il implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)