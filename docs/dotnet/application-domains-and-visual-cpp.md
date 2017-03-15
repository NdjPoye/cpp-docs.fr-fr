---
title: "Domaines d&#39;application et Visual&#160;C++ | Microsoft Docs"
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
  - "/clr (option du compilateur C++), domaines d'application"
  - "domaines d'application (C++), C++"
  - "Interop (C++), domaines d'application"
  - "interopérabilité (C++), domaines d'application"
  - "assemblys mixtes (C++), domaines d'application"
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Domaines d&#39;application et Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous avez une fonction virtuelle `__clrcall`, la vtable sera par domaine d'application \(appdomain\).  Si vous créez un objet dans un appdomain, vous ne pouvez appeler la fonction virtuelle que depuis cet appdomain.  Toutes les fonctions définies dans des compilands **\/clr:pure** utilisent la convention d'appel `__clrcall`.  Par conséquent, toutes les vtables définies dans des compilands **\/clr:pure** sont par appdomain.  En mode mixte \(**\/clr**\), vous aurez des vtables par processus si votre type n'a pas de fonctions virtuelles `__clrcall`.  
  
 Pour plus d'informations, consultez  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [\_\_clrcall](../cpp/clrcall.md)  
  
-   [Comment : effectuer une migration vers \/clr:pure](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [processus](../cpp/process.md)  
  
## Voir aussi  
 [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)