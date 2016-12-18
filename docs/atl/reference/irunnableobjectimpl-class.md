---
title: "IRunnableObjectImpl Class | Microsoft Docs"
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
  - "IRunnableObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conteneurs, running controls"
  - "controls [ATL], exécuter"
  - "contrôles (C++), container running in ATL"
  - "IRunnableObject, ATL (implémentation)"
  - "IRunnableObjectImpl class"
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRunnableObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et fournit une implémentation par défaut de l'interface d' [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template< class   
      T  
      >  
class IRunnableObjectImpl  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IRunnableObjectImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](../Topic/IRunnableObjectImpl::GetRunningClass.md)|Retourne le CLSID du contrôle en cours de exécution.  L'implémentation ATL définit le CLSID à `GUID_NULL` et retourne **E\_UNEXPECTED**.|  
|[IRunnableObjectImpl::IsRunning](../Topic/IRunnableObjectImpl::IsRunning.md)|Détermine si le contrôle exécute.  L'implémentation ATL retourne **TRUE**.|  
|[IRunnableObjectImpl::LockRunning](../Topic/IRunnableObjectImpl::LockRunning.md)|Verrouille le contrôle dans l'état d'exécution.  L'implémentation ATL retourne `S_OK`.|  
|[IRunnableObjectImpl::Run](../Topic/IRunnableObjectImpl::Run.md)|Force le contrôle pour exécuter.  L'implémentation ATL retourne `S_OK`.|  
|[IRunnableObjectImpl::SetContainedObject](../Topic/IRunnableObjectImpl::SetContainedObject.md)|Indique que le contrôle est incorporé.  L'implémentation ATL retourne `S_OK`.|  
  
## Notes  
 L'interface d' [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) permet à un conteneur de déterminer si un contrôle exécute, le forcent à exécuter, ou le verrouillent dans l'état d'exécution.  La classe `IRunnableObjectImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)