---
title: "Comparaison entre les fonctionnalit&#233;s mixte, pure et v&#233;rifiable (C++/CLI) | Microsoft Docs"
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
  - "assemblys mixtes (C++)"
  - "assemblys mixtes (C++), et assemblys purs (différences)"
  - "assemblys mixtes (C++), et sécurisé (différences)"
  - "assemblys purs (C++)"
  - "MSIL pur (C++)"
  - "MSIL pur (C++), comparé à mixte et sécurisé"
  - "MSIL pur (C++), et mixtes (différences)"
  - "MSIL pur (C++), et sécurisé (différences)"
  - "assemblys sécurisés (C++)"
  - "assemblys sécurisés (C++), et mixtes (différences)"
  - "assemblys sécurisés (C++), et assemblys purs (différences)"
  - "assemblys vérifiables (C++)"
  - "assemblys vérifiables (C++), et mixtes (différences)"
  - "assemblys vérifiables (C++), et assemblys purs (différences)"
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comparaison entre les fonctionnalit&#233;s mixte, pure et v&#233;rifiable (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique compare les fonctionnalités des différents modes de compilation **\/clr**.  Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Comparaison des fonctionnalités  
  
|Fonctionnalité|Mixte \(\/clr\)|Pur \(\/clr:pure\)|Sécurisé \(\/clr:safe\)|Informations connexes|  
|--------------------|---------------------|------------------------|-----------------------------|---------------------------|  
|Bibliothèque CRT|prise en charge|prise en charge||[Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)|  
|MFC\/ATL|prise en charge|||[MFC, applications de bureau](../mfc/mfc-desktop-applications.md) &#124; [Class Overview](../atl/atl-class-overview.md)|  
|Fonctions non managées|prise en charge|||[Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)|  
|Données non managées|prise en charge|prise en charge||[Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md)|  
|Appelable à partir de fonctions non managées|prise en charge|||[Comment : effectuer une migration vers \/clr:pure](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)|  
|Prend en charge l'appel de fonctions non managées|prise en charge|Fonctions de style C uniquement|P\/Invoke uniquement|[Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|  
|Prend en charge la réflexion|DLL uniquement|prise en charge|prise en charge|[Réflexion](../dotnet/reflection-cpp-cli.md)|  
  
## Voir aussi  
 [Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md)