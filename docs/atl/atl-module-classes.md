---
title: "Module ATL, classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, module (classes)"
  - "CComModule (classe), nouveautés"
  - "module (classes)"
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module ATL, classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit les classes de package qui étaient nouvelles dans ATL 7,0.  
  
## Classes de remplacement de CComModule  
 Les versions antérieures ATL ont utilisé `CComModule`.  Dans ATL 7,0, la fonctionnalité d' `CComModule` est remplacée par plusieurs classes :  
  
-   [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) contient les informations requises par la plupart des applications qui utilisent ATL.  Contient le HINSTANCE du module et de l'instance de ressource.  
  
-   [CAtlComModule](../atl/reference/catlcommodule-class.md) contient les informations requises par les classes COM dans ATL.  
  
-   [CAtlWinModule](../atl/reference/catlwinmodule-class.md) contient les informations requises par les classes de fenêtrage dans ATL.  
  
-   [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) contient la prise en charge du débogage d'interface.  
  
-   [CAtlModule](../atl/reference/catlmodule-class.md) `CAtlModule`suivant \- les classes dérivées sont personnalisées pour contenir les informations requises dans un type d'application particulier.  La plupart des membres de ces classes peuvent être substituées :  
  
    -   [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) celle utilisée dans les applications de DLL.  Fournit le code pour les exportations standard.  
  
    -   [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) celle utilisée dans les applications EXE.  Fournit le code requis dans un fichier EXE.  
  
    -   [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) fournit le support pour créer Windows NT et des services Windows 2000.  
  
 `CComModule` est toujours disponible pour la compatibilité descendante.  
  
## Raisons pour distribuer la fonctionnalité de CComModule  
 La fonctionnalité d' `CComModule` a été distribuée dans plusieurs nouvelles classes pour les raisons suivantes :  
  
-   Rendez la fonctionnalité dans `CComModule` précise.  
  
     La prise en charge COM, de fenêtrage, de le débogage d'interface, et \(DLL ou EXE\) des fonctionnalités spécifiques à l'application est maintenant dans les classes séparées.  
  
-   Déclarez automatiquement l'instance globale de chacun de ces modules.  
  
     Une instance globale des classes de package requis est incorporée dans le projet.  
  
-   Supprimez le besoin d'appeler Init et nommez les méthodes.  
  
     Les méthodes d'Init et term sont entrées dans les constructeurs et les destructeurs pour les classes de module ; il n'y a plus d'un besoin d'appeler Init et terme.  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)   
 [Class Overview](../atl/atl-class-overview.md)