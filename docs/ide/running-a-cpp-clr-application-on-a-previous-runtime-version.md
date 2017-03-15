---
title: "Ex&#233;cution d&#39;une application&#160;C++ /clr sur une version ant&#233;rieure du runtime | Microsoft Docs"
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
  - "fichiers app.config, runtime (version spécifiée)"
  - "déploiement d'applications (C++), runtime (version spécifiée)"
  - "applications (C++), runtime (version spécifiée)"
  - "compatibilité descendante (C++), runtime (version spécifiée)"
  - "Common Language Runtime (C++), version spécifiée"
  - "compatibilité (C++), runtime (version spécifiée)"
  - "déployer des applications (C++), runtime (version spécifiée)"
  - "versions (C++)"
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ex&#233;cution d&#39;une application&#160;C++ /clr sur une version ant&#233;rieure du runtime
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sauf indication contraire, une application .NET de Visual C\+\+ .NET est générée pour s'exécuter sur la version du common langage runtime \(CLR\) que le compilateur utilise pour générer l'application.  Toutefois, il est possible pour une application .exe qui est créée pour une version du runtime à exécuter sur n'importe quelle autre version qui fournit la fonctionnalité requise.  
  
 Pour ce faire, fournissez un fichier app.config qui contient les informations de version du runtime dans la balise d' `supportedRuntime` .  
  
 Au moment de l'exécution, le fichier app.config doit avoir un nom de formulaire *filename.ext*.config, où *filename.ext* est le nom du fichier exécutable qui a démarré l'application, et il doit figurer dans le même répertoire que le fichier exécutable.  Par exemple, si votre application est nommée TestApp.exe, le fichier app.config est nommé TestApp.exe.config.  
  
 Si vous spécifiez plusieurs versions du runtime et l'application s'exécute sur un ordinateur doté de plusieurs versions du runtime installée, l'application utilise la première version spécifiée dans le fichier de configuration et est installée.  
  
 Pour plus d'informations, consultez [How to: Configure an App to Target a .NET Framework Version](http://msdn.microsoft.com/fr-fr/5247b307-89ca-417b-8dd0-e8f9bd2f4717).  
  
 Pour exécuter sur la version 1,0 ou la version 1,1 du CLR, une application générée par le compilateur Visual C\+\+ doit être compilée à l'aide de [\/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Voir aussi  
 [Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)