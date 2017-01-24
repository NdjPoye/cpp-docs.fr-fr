---
title: "IOleInPlaceObjectWindowlessImpl Class | Microsoft Docs"
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
  - "IOleInPlaceObjectWindowlessImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activation [C++], ATL"
  - "contrôles ActiveX (C++), communication between container and control"
  - "controls [ATL], windowless"
  - "deactivating ATL"
  - "IOleInPlaceObjectWindowless, ATL (implémentation)"
  - "IOleInPlaceObjectWindowlessImpl class"
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IOleInPlaceObjectWindowlessImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et fournit des méthodes qui permettent à un contrôle sans fenêtre de recevoir des messages de fenêtre et de participer aux opérations de glisser\-déplacer.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template< class   
      T  
      >  
class IOleInPlaceObjectWindowlessImpl  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IOleInPlaceObjectWindowlessImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](../Topic/IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp.md)|Active l'aide contextuelle.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](../Topic/IOleInPlaceObjectWindowlessImpl::GetDropTarget.md)|Fournit l'interface d' `IDropTarget` pour un objet actif et sans fenêtre visuelle qui prend en charge le glisser\-déplacer.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](../Topic/IOleInPlaceObjectWindowlessImpl::GetWindow.md)|Obtient un handle de fenêtre.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate.md)|Place un contrôle sur place actif.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](../Topic/IOleInPlaceObjectWindowlessImpl::OnWindowMessage.md)|Distribue un message du conteneur à un contrôle sans fenêtre qui est actif sur place.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](../Topic/IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo.md)|Réactive un contrôle précédemment désactivé.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](../Topic/IOleInPlaceObjectWindowlessImpl::SetObjectRects.md)|Indique quelle partie du contrôle sur place est visible.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::UIDeactivate.md)|Met désactivé et supprime l'interface utilisateur qui prend en charge l'activation sur place.|  
  
## Notes  
 L'interface d' [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) gère la réactivation et la mise hors fonction de les contrôles sur place et détermine quelle quantité de contrôle doit être visible.  L'interface d' [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) permet à un contrôle sans fenêtre de recevoir des messages de fenêtre et de participer aux opérations de glisser\-déplacer.  La classe `IOleInPlaceObjectWindowlessImpl` fournit une implémentation par défaut d' `IOleInPlaceObject` et d' `IOleInPlaceObjectWindowless` et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)