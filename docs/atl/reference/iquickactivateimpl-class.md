---
title: "IQuickActivateImpl Class | Microsoft Docs"
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
  - "ATL::IQuickActivateImpl"
  - "ATL::IQuickActivateImpl<T>"
  - "ATL.IQuickActivateImpl"
  - "ATL.IQuickActivateImpl<T>"
  - "IQuickActivateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activating ATL controls"
  - "controls [ATL], activer"
  - "IQuickActivate ATL implementation"
  - "IQuickActivateImpl class"
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IQuickActivateImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe associe l'initialisation de contrôle des conteneurs dans un seul appel.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template<   
class T   
>  
class ATL_NO_VTABLE IQuickActivateImpl :  
public IQuickActivate  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IQuickActivateImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](../Topic/IQuickActivateImpl::GetContentExtent.md)|Extrait la taille d'affichage actuelle d'un contrôle en cours de exécution.|  
|[IQuickActivateImpl::QuickActivate](../Topic/IQuickActivateImpl::QuickActivate.md)|Exécute l'initialisation rapide des contrôles qui sont chargés.|  
|[IQuickActivateImpl::SetContentExtent](../Topic/IQuickActivateImpl::SetContentExtent.md)|Informe le contrôle de la quantité d'espace d'affichage le conteneur est assigné.|  
  
## Notes  
 Les conteneurs d'aide d'interface d' [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) évitent les délais lorsque les contrôles de charge en combinant l'initialisation dans un seul appel.  La méthode d' `QuickActivate` permet au conteneur pour passer un pointeur vers une structure de [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) qui contient des pointeurs vers toutes les interfaces les besoins de contrôle.  Au retour, le contrôle passe privilégient un pointeur vers une structure de [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) qui contient des pointeurs vers ses propres interfaces, qui sont utilisées par le conteneur.  La classe `IQuickActivateImpl` fournit une implémentation par défaut d' **IQuickActivate** et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)