---
title: "G&#233;n&#233;ration d&#39;applications isol&#233;es C/C++ et d&#39;assemblys c&#244;te &#224; c&#244;te | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications isolées (C++)"
  - "WinSxS (C++)"
  - "cache d'assembly natif (C++)"
  - "builds [C++] (applications isolées)"
  - "applications côte à côte (C++)"
  - "builds [C++] (assemblys côte à côte)"
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# G&#233;n&#233;ration d&#39;applications isol&#233;es C/C++ et d&#39;assemblys c&#244;te &#224; c&#244;te
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ prend en charge un modèle de déploiement pour les applications clientes Windows qui s’appuie sur l’idée des [applications isolées](http://msdn.microsoft.com/library/aa375190) et des [assemblys côte à côte](_win32_side_by_side_assemblies). Par défaut, Visual C\+\+ génère toutes les applications C\/C\+\+ natives en tant qu’applications isolées qui utilisent des [manifestes](http://msdn.microsoft.com/library/aa375365) pour décrire leurs dépendances envers des bibliothèques Visual C\+\+.  
  
 La création des programmes C\/C\+\+ en tant qu'applications isolées présente toute une palette d'avantages. Par exemple, une application isolée n'est pas affectée quand d'autres applications C\/C\+\+ installent ou désinstallent des bibliothèques Visual C\+\+. Les bibliothèques Visual C\+\+ utilisées par une application isolée peuvent encore être redistribuées dans le dossier local de l’application ou en étant installées dans le cache d’assembly natif \(WinSxS\). Toutefois, la maintenance des bibliothèques Visual C\+\+ pour des applications déjà déployées peut\-être simplifiée à l’aide d’un [fichier de configuration d’éditeur](http://msdn.microsoft.com/library/aa375680). Le modèle de déploiement d'applications isolées permet de garantir plus aisément que les applications C\/C\+\+ qui s'exécutent sur un ordinateur spécifique utilisent la version la plus récente des bibliothèques Visual C\+\+, tout en continuant de permettre aux administrateurs système et aux auteurs d'applications de contrôler la liaison explicite des versions des applications avec leur DLL dépendantes.  
  
 Cette section explique comment générer une application C\/C\+\+ en tant qu'application isolée et s'assurer qu'elle est liée aux bibliothèques Visual C\+\+ à l'aide d'un manifeste. Les informations fournies dans cette section s'appliquent principalement aux applications Visual C\+\+ natives ou non managées. Pour plus d’informations sur le déploiement d’applications natives générées avec Visual C\+\+, consultez [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md).  
  
## Dans cette section  
 [Concepts d'applications isolées et d'assemblys côte à côte](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)  
  
 [Génération d'applications isolées C\/C\+\+](../build/building-c-cpp-isolated-applications.md)  
  
 [Génération d'assemblys côte à côte C\/C\+\+](../build/building-c-cpp-side-by-side-assemblies.md)  
  
 [Comment : générer des composants COM sans inscription](../build/how-to-build-registration-free-com-components.md)  
  
 [Comment : générer des applications isolées pour consommer des composants COM](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
 [Fonctionnement de la génération de manifestes pour les programmes C\/C\+\+](../build/understanding-manifest-generation-for-c-cpp-programs.md)  
  
 [Dépannage](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
## Rubriques connexes  
 [Applications isolées et assemblys côte à côte](http://msdn.microsoft.com/library/dd408052)  
  
 [Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)