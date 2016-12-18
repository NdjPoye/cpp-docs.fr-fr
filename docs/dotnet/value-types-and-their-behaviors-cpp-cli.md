---
title: "Types valeur et leurs comportements (C++/CLI) | Microsoft Docs"
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
  - "types valeur"
ms.assetid: 5cb872a6-1e0a-429d-853d-df4ab47e8f2a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Types valeur et leurs comportements (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les types valeur ont été transformés de diverses façons entre les Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  Dans cette section, nous nous pencherons sur le type enum du CLR et le type de la classe valeur, sur les conversions boxing et l'accès à l'instance boxed sur le tas du CLR, ainsi que sur les pointeurs intérieurs et épingles.  De nombreuses modifications ont été apportées au langage dans ce domaine.  
  
## Dans cette section  
 [CLR Enum Type](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 Traite des modifications apportées à la déclaration et au comportement des enums.  
  
 [Conversion boxing implicite de types valeur](../dotnet/implicit-boxing-of-value-types.md)  
 Traite des raisons d'effectuer des conversions boxing implicites de types valeur et des modifications conséquentes du comportement.  
  
 [Handle de suivi d'une valeur boxed](../dotnet/a-tracking-handle-to-a-boxed-value.md)  
 Traite de la façon dont la conversion boxing implicite de types valeur se traduit par un handle de suivi de l'objet valeur boxed.  
  
 [Sémantique de type valeur](../dotnet/value-type-semantics.md)  
 Traite des modifications de la sémantique de type valeur, notamment des méthodes virtuelles héritées, des constructeurs de classe par défaut, des pointeurs intérieurs et des pointeurs épingle.  
  
## Voir aussi  
 [Initiation à la migration de C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)