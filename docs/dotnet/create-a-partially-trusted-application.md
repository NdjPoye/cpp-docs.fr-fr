---
title: "Comment&#160;: cr&#233;er une application partiellement approuv&#233;e en supprimant la d&#233;pendance de la DLL de la biblioth&#232;que CRT | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr (option du compilateur C++), applications de confiance partielle"
  - "Interop (C++), applications de confiance partielle"
  - "interopérabilité (C++), applications de confiance partielle"
  - "assemblys mixtes (C++), applications de confiance partielle"
  - "msvcm90[d].dll"
  - "applications de confiance partielle (C++)"
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: cr&#233;er une application partiellement approuv&#233;e en supprimant la d&#233;pendance de la DLL de la biblioth&#232;que CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment créer une application du Common Language Runtime à niveau de confiance partiel à l'aide de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] en supprimant la dépendance vis\-à\-vis de msvcm90.dll.  
  
 Une application Visual C\+\+ construite avec **\/clr** sera dépendante de msvcm90.dll, qui fait partie de la bibliothèque Runtime C.  Si vous souhaitez que votre application soit utilisée dans un environnement à confiance partielle, le CLR activera certaines règles de sécurité d'accès du code sur votre DLL.  Il sera donc nécessaire de supprimer cette dépendance puisque msvcm90.dll contient du code natif et que la stratégie de sécurité d'accès du code ne peut pas lui être appliquée.  
  
 Si votre application n'utilise pas toutes les fonctionnalités de la Bibliothèque d'exécution C et que vous souhaitez supprimer la dépendance de votre code sur cette bibliothèque, vous devrez utiliser l'option de l'éditeur de liens **\/NODEFAULTLIB:msvcmrt.lib** et lier avec ptrustm.lib ou ptrustmd.lib.  Ces bibliothèques contiennent des fichiers objets pour l'initialisation et l'annulation de l'initialisation d'une application, les classes d'exception utilisées par le code d'initialisation, et le code de gestion des exceptions managées.  La liaison dans l'une de ces bibliothèques supprimera toute dépendance vis\-à\-vis de msvcm90.dll.  
  
> [!NOTE]
>  L'ordre de désinitialisation des assemblys peut être différent pour les applications qui utilisent les bibliothèques ptrust.  Pour les applications normales, les assemblys sont habituellement déchargés dans l'ordre inverse de leur chargement, mais cela n'est pas garanti.  Pour les applications de confiance partielle, les assemblys sont habituellement déchargés dans l'ordre de leur chargement.  Cela n'est pas non plus garanti.  
  
### Pour créer une application mixte \(\/clr\) de confiance partielle  
  
1.  Pour supprimer la dépendance vis\-à\-vis de msvcm90.dll, vous devez spécifier à l'éditeur de liens de ne pas inclure cette bibliothèque à l'aide de l'option de l'éditeur de liens **\/NODEFAULTLIB:msvcmrt.lib**.  Pour plus d'informations sur la façon de faire à l'aide de l'environnement de développement Visual Studio ou par programme, consultez [\/NODEFAULTLIB \(Ignorer les bibliothèques\)](../build/reference/nodefaultlib-ignore-libraries.md).  
  
2.  Ajoutez l'une des bibliothèques ptrustm aux dépendances d'entrée de l'éditeur de liens.  Utilisez ptrustm.lib si vous générez votre application en mode release.  Pour le mode débogage, utilisez ptrustmd.lib.  Pour plus d'informations sur la façon de faire à l'aide de l'environnement de développement Visual Studio ou par programme, consultez [.Fichiers .lib en tant qu'entrée de l'Éditeur de liens](../build/reference/dot-lib-files-as-linker-input.md).  
  
## Voir aussi  
 [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Initialisation d'assemblys mixtes](../dotnet/initialization-of-mixed-assemblies.md)   
 [Prise en charge de bibliothèque pour les assemblys mixtes](../dotnet/library-support-for-mixed-assemblies.md)   
 [\/link \(Passer des options à l'Éditeur de liens\)](../build/reference/link-pass-options-to-linker.md)   
 [PAVE Security in Native and .NET Framework Code](http://msdn.microsoft.com/fr-fr/bd61be84-c143-409a-a75a-44253724f784)