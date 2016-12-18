---
title: "Assembleur inline | Microsoft Docs"
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
  - "assembleur (C++)"
  - "assembleur (C++), inline"
  - "langage assembleur (C++), inline"
  - "assembleur inline (C++)"
  - "assembleur inline (C++)"
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Assembleur inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le langage assembleur atteint de nombreux objectifs, tels que l'amélioration de la vitesse du programme, la réduction des besoins en mémoire et le contrôle du matériel.  Vous pouvez utiliser l'assembleur inline pour incorporer des instructions en langage assembleur directement dans vos programmes sources C et C\+\+ sans code assembleur ni étapes de liaison supplémentaires.  L'assembleur inline est intégré au compilateur. Par conséquent, vous n'avez pas besoin d'assembleur distinct tel que MASM \(Microsoft Macro Assembler\).  
  
> [!NOTE]
>  Les programmes avec du code assembleur inline ne sont pas entièrement portables sur d'autres plateformes matérielles.  Si vous concevez pour la portabilité, évitez d'utiliser l'assembleur inline.  
  
 L'assembly inline n'est pas pris en charge sur les processeurs ARM et [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].  Les rubriques suivantes expliquent comment utiliser l'assembleur inline de Visual C\/C\+\+ avec des processeurs x86 :  
  
-   [Vue d'ensemble de l'assembleur inline](../../assembler/inline/inline-assembler-overview.md)  
  
-   [Avantages de l'assembly inline](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [\_\_asm](../../assembler/inline/asm.md)  
  
-   [Utilisation du langage assembleur dans les blocs \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [Utilisation de C ou C\+\+ dans les blocs \_\_asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [Utilisation et conservation des registres dans un assembly inline](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [Accès aux étiquettes dans l'assembly inline](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [Appel des fonctions C dans l'assembly inline](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [Appel des fonctions C\+\+ dans l'assembly inline](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [Définition des blocs \_\_asm sous forme de macros C](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [Optimisation de l'assembly inline](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Fonctions intrinsèques du compilateur et langage assembleur](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [Référence du langage C\+\+](../../cpp/cpp-language-reference.md)