---
title: "Threading Models and Critical Sections Classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.threads.models"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, critical sections"
  - "ATL, multithreading"
  - "critical sections"
  - "threads (ATL), modèles"
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Threading Models and Critical Sections Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes suivantes définissent un modèle de thread et une section critique :  
  
-   [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) implémente un regroupé par thread, serveur COM de modèle cloisonné.  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) fournit des méthodes pour implémenter un regroupé par thread, serveur COM de modèle cloisonné.  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) fournit des méthodes thread\-safe pour incrémenter ou décrémenter une variable.  Fournit une section critique.  
  
-   [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) fournit des méthodes thread\-safe pour incrémenter ou décrémenter une variable.  Ne fournit pas une section critique.  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) fournit des méthodes pour incrémenter ou décrémenter une variable.  Ne fournit pas une section critique.  
  
-   [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) détermine la classe appropriée du modèle de thread pour une classe d'objet unique.  
  
-   [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md) détermine la classe appropriée du modèle de thread pour un objet qui est globalement disponible.  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) contient des méthodes pour obtenir et libérer une section critique.  La section critique est initialisée automatiquement.  
  
-   [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) contient des méthodes pour obtenir et libérer une section critique.  La section critique doit être explicitement initialisée.  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) reflète les méthodes dans `CComCriticalSection` sans fournir une section critique.  Les méthodes dans `CComFakeCriticalSection` ne font rien.  
  
-   [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) fournit la fonction de création d'un thread CRT.  Utilisez cette classe si le thread utilise des fonctions CRT.  
  
-   [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) fournit la fonction de création d'un thread windows.  Utilisez cette classe si le thread n'utilise pas les fonctions CRT.  
  
## Voir aussi  
 [Class Overview](../atl/atl-class-overview.md)