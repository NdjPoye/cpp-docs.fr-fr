---
title: "CComAutoThreadModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "apartment model modules"
  - "CComAutoThreadModule class"
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComAutoThreadModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

As of ATL 7,0, `CComAutoThreadModule` est obsolète : consultez [Classes de module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
class ThreadAllocator= CComSimpleThreadAllocator   
>  
class CComAutoThreadModule :  
public CComModule  
```  
  
#### Paramètres  
 `ThreadAllocator`  
 \[in\]  La classe gestion de la sélection de thread.  La valeur par défaut est [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CreateInstance](../Topic/CComAutoThreadModule::CreateInstance.md)|Sélectionne un thread puis crée un objet dans le MTA associé.|  
|[GetDefaultThreads](../Topic/CComAutoThreadModule::GetDefaultThreads.md)|\(Statique\) calcule dynamiquement le nombre de threads pour le package en fonction de le nombre de processeurs.|  
|[Init](../Topic/CComAutoThreadModule::Init.md)|Crée les threads du module.|  
|[Verrouiller](../Topic/CComAutoThreadModule::Lock.md)|Incrémente le nombre de verrous sur le package et sur le thread actuel.|  
|[Déverrouillez](../Topic/CComAutoThreadModule::Unlock.md)|Décrémente le nombre de verrous sur le package et sur le thread actuel.|  
  
### Membres de données  
  
### Membres de données  
  
|||  
|-|-|  
|[dwThreadID](../Topic/CComAutoThreadModule::dwThreadID.md)|Contient l'identificateur du thread actuel.|  
|[m\_Allocator](../Topic/CComAutoThreadModule::m_Allocator.md)|Gère la sélection de thread.|  
|[m\_nThreads](../Topic/CComAutoThreadModule::m_nThreads.md)|Contient le nombre de threads dans le module.|  
|[m\_pApartments](../Topic/CComAutoThreadModule::m_pApartments.md)|Gère les apartments du module.|  
  
## Notes  
  
> [!NOTE]
>  Cette classe est obsolète, après avoir été remplacé par [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) et les classes dérivées par [CAtlModule](../../atl/reference/catlmodule-class.md) .  Les informations qui suivent utilisent des versions plus anciennes ATL.  
  
 `CComAutoThreadModule` dérive de [CComModule](../../atl/reference/ccommodule-class.md) pour implémenter un serveur COM regroupé par thread, de modèle cloisonné pour EXE et des services windows.  `CComAutoThreadModule` utilise [CComApartment](../../atl/reference/ccomapartment-class.md) pour gérer un " apartment " pour chaque thread dans le module.  
  
 Dérivez votre package d' `CComAutoThreadModule` lorsque vous souhaitez créer des objets de plusieurs apartments.  Vous devez également inclure la macro de [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) dans la définition de classe de votre objet pour spécifier [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) comme une fabrique de classe.  
  
 Par défaut, ATL COM AppWizard \(Assistant Projet ATL dans Visual Studio .NET\) dérivera votre package d' `CComModule`.  Pour utiliser `CComAutoThreadModule`, modifiez la définition de classe.  Par exemple :  
  
 [!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/CPP/ccomautothreadmodule-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Module, classes](../../atl/atl-module-classes.md)