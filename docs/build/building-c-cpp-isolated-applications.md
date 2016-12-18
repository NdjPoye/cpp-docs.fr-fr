---
title: "G&#233;n&#233;ration d&#39;applications isol&#233;es C/C++ | Microsoft Docs"
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
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# G&#233;n&#233;ration d&#39;applications isol&#233;es C/C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une application isolée ne dépend que d'assemblys côte à côte et se lie à ses dépendances à l'aide d'un manifeste.  Il n'est pas nécessaire que votre application soit complètement isolée pour s'exécuter correctement sur Windows ; toutefois, cette procédure vous permet d'économiser du temps si vous devez assurer la maintenance de votre application dans l'avenir.  Pour plus d'informations sur les avantages qu'il y a à isoler totalement votre application, consultez [Applications isolées](http://msdn.microsoft.com/library/aa375190).  
  
 Lorsque vous générez votre application C\/C\+\+ native à l'aide de Visual C\+\+, le système de projet Visual Studio génère par défaut un fichier manifeste qui décrit les dépendances de votre application vis\-à\-vis des bibliothèques Visual C\+\+.  S'il s'agit des seules dépendances de votre application, celle\-ci devient alors une application isolée dès qu'elle est régénérée avec Visual Studio.  Si votre application utilise d'autres bibliothèques au moment de l'exécution, vous devrez peut\-être régénérer ces bibliothèques en tant qu'assemblys côte à côte en suivant les procédures décrites dans [Génération d'assemblys côte à côte C\/C\+\+](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## Voir aussi  
 [Concepts d'applications isolées et d'assemblys côte à côte](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Génération d'applications isolées C\/C\+\+ et d'assemblys côte à côte](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)