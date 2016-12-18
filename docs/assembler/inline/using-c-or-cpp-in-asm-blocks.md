---
title: "Utilisation de C ou C++ dans les blocs __asm | Microsoft Docs"
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
  - "__asm (mot clé) (C++), éléments de C/C++ dans"
  - "commentaires, in __asm (blocs)"
  - "constantes, in __asm (blocs)"
  - "assembleur inline, combiner des instructions et des instructions C/C++"
  - "macros, __asm (blocs)"
  - "directives de préprocesseur"
  - "directives de préprocesseur, utilisé dans les blocs in __asm"
  - "préprocesseur, directives"
  - "symboles, in __asm (blocs)"
  - "noms de types, utilisé dans les blocs in __asm"
  - "noms typedef, utilisé dans les blocs in __asm"
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Utilisation de C ou C++ dans les blocs __asm
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Étant donné que les instructions d'assembly inline peuvent être combinées avec des instructions C ou C\+\+, elles peuvent faire référence à des variables C ou C\+\+ par nom et utiliser de nombreux autres éléments de ces langages.  
  
 Un bloc `__asm` peut utiliser les éléments de langage suivants :  
  
-   Symboles, notamment les étiquettes et les noms de variable et de fonction  
  
-   Constantes, notamment les constantes symboliques et les membres `enum`  
  
-   Macros et directives de préprocesseur  
  
-   Commentaires \(**\/\* \*\/** et **\/\/**\)  
  
-   Noms de types \(partout où un type MASM est autorisé\)  
  
-   Noms `typedef`, généralement utilisés avec des opérateurs tels que **PTR** et **TYPE** ou pour spécifier les membres de structure ou d'union  
  
 Dans un bloc `__asm`, vous pouvez spécifier des constantes entières avec la notation C ou la notation de base de l'assembleur \(0x100 et 100h sont équivalents, par exemple\).  Cela vous permet de définir \(avec `#define`\) une constante en C puis de l'utiliser dans C ou C\+\+ et dans des parties d'assembly du programme.  Vous pouvez également spécifier des constantes au format octal en les faisant précéder d'un 0.  Par exemple, 0777 spécifie une constante octale.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation d'opérateurs dans les blocs \_\_asm](../../assembler/inline/using-operators-in-asm-blocks.md)  
  
-   [Utilisation de symboles C ou C\+\+ dans les blocs \_\_asm](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)  
  
-   [Accès aux données C ou C\+\+ dans les blocs \_\_asm](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)  
  
-   [Écriture de fonctions avec un assembly inline](../../assembler/inline/writing-functions-with-inline-assembly.md)  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Assembleur inline](../../assembler/inline/inline-assembler.md)