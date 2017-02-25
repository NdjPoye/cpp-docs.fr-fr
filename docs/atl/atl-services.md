---
title: "Services ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL (services)"
  - "objets COM, ATL"
  - "CServiceModule (classe)"
  - "services, ATL"
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Services ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour créer votre ATL COM objet afin qu'il s'exécute à un service, sélectionnez simplement le service \(EXE\) de la liste d'options de serveur dans l'Assistant Projet ATL.  L'assistant crée ensuite une classe dérivée d' `CAtlServiceModuleT` pour implémenter le service.  
  
 Lorsque l'objet COM ATL est généré en tant que service, il ne sera stocké en tant que serveur local, et il n'apparaît pas dans la liste des services dans le panneau de configuration.  C'est parce qu'il est plus facile de déboguer le service en tant que serveur local qu'en tant que service.  Pour l'installer en tant que service, exécutez le code suivant à l'invite de commandes :  
  
 `YourEXE` `.exe /Service`  
  
 Pour la désinstallation, exécutez les opérations suivantes :  
  
 `YourEXE` `.exe /UnregServer`  
  
 Les quatre premiers rubriques de cette section décrivent les actions qui se produisent lors de l'exécution des fonctions membres d' `CAtlServiceModuleT` .  Ces rubriques s'affichent dans la même séquence que les fonctions sont généralement appelé.  Pour mieux comprendre le fonctionnement de ces rubriques, il est conseillé d'utiliser du code source généré par l'Assistant Projet ATL en tant que référence.  Ces quatre premiers rubriques suivantes :  
  
-   [La fonction de CAtlServiceModuleT::Start](../atl/catlservicemodulet-start-function.md)  
  
-   [La fonction de CAtlServiceModuleT::ServiceMain](../atl/catlservicemodulet-servicemain-function.md)  
  
-   [La fonction de CAtlServiceModuleT::Run](../atl/catlservicemodulet-run-function.md)  
  
-   [La fonction de CAtlServiceModuleT::Handler](../atl/catlservicemodulet-handler-function.md)  
  
 Les trois derniers rubriques décrivent les concepts liés au développement un service :  
  
-   [Entrées du registre](../atl/registry-entries.md) pour les services ATL  
  
-   [DCOMCNFG](../atl/dcomcnfg.md)  
  
-   [conseils de débogage](../atl/debugging-tips.md) pour les services ATL  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)