---
title: "Types manag&#233;s (C++/CL) | Microsoft Docs"
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
  - "types _gc"
  - "types (C++), CLR"
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Types manag&#233;s (C++/CL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La syntaxe servant à déclarer des types managés et à créer et utiliser des objets de ces types a été sensiblement modifiée entre les Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  Cela a été fait pour favoriser leur intégration dans le système de type d'ISO\-C\+\+.  Ces changements sont décrits en détail dans les sous\-sections suivantes.  
  
## Dans cette section  
 [Déclaration d'un type de classe managée](../dotnet/declaration-of-a-managed-class-type.md)  
 Traite de la façon de déclarer une `class`, un `struct` ou une `interface` managée.  
  
 [Déclaration d'un objet de classe de référence du CLR](../dotnet/declaration-of-a-clr-reference-class-object.md)  
 Traite de la façon de déclarer un objet de type de classe de référence à l'aide d'un handle de suivi.  
  
 [Déclaration d'un tableau CLR](../dotnet/declaration-of-a-clr-array.md)  
 Explique comment déclarer et initialiser un tableau.  
  
 [Modifications dans l'ordre d'initialisation des constructeurs](../dotnet/changes-in-constructor-initialization-order.md)  
 Traite des principales modifications dans l'ordre d'initialisation du constructeur de classe.  
  
 [Modifications de la sémantique du destructeur](../dotnet/changes-in-destructor-semantics.md)  
 Traite de finalisation non déterministe, de la différence entre `Finalize` et `Dispose`, des ramifications des objets de référence et de l'utilisation d'une méthode `Finalize` explicite.  
  
 **Remarque :** l'explication des délégués est différée jusqu'à celle de [Délégués et événements](../dotnet/delegates-and-events.md), afin de les présenter en même temps que les membres d'événement au sein d'une classe, ce qui constitue le sujet général de [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md).  
  
## Voir aussi  
 [Initiation à la migration de C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Arrays](../windows/arrays-cpp-component-extensions.md)