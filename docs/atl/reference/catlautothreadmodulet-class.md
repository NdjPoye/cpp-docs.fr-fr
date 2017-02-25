---
title: "CAtlAutoThreadModuleT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlAutoThreadModuleT"
  - "ATL::CAtlAutoThreadModuleT"
  - "CAtlAutoThreadModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlAutoThreadModuleT class"
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAtlAutoThreadModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour implémenter un regroupé par thread, serveur COM de modèle cloisonné.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class T,  
class ThreadAllocator= CComSimpleThreadAllocator,  
DWORD dwWait= INFINITE   
>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT :  
public IAtlAutoThreadModule  
```  
  
#### Paramètres  
 `T`  
 La classe qui implémentera le serveur COM.  
  
 `ThreadAllocator`  
 La classe gestion de la sélection de thread.  La valeur par défaut est [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Spécifie l'intervalle de délai d'attente, en millisecondes.  La valeur par défaut est INFINIE, ce qui signifie que l'intervalle de délai d'attente de la méthode ne s'écoule jamais.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](../Topic/CAtlAutoThreadModuleT::GetDefaultThreads.md)|Cette fonction statique calcule dynamiquement et retourne le nombre maximal de threads pour le package EXE, en fonction de le nombre de processeurs.|  
  
## Notes  
 La classe [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) dérive d' `CAtlAutoThreadModuleT` pour implémenter un regroupé par thread, serveur COM de modèle cloisonné.  Il substitue la classe obsolète [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Cette classe ne doit pas être utilisée dans une DLL, comme valeur par défaut d' `dwWait` d'INFINITÉ provoque un interblocage quand la DLL est déchargé.  
  
## Hiérarchie d'héritage  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Module, classes](../../atl/atl-module-classes.md)