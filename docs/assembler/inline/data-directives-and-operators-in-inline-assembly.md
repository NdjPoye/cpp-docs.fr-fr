---
title: "Directives de donn&#233;es et op&#233;rateurs dans un assembly inline | Microsoft Docs"
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
  - "__asm (mot clé) (C++), référencer des limitations"
  - "directives de données [C++]"
  - "directives (C++), MASM"
  - "assembleur inline, directives de données"
  - "assembleur inline, opérateurs"
  - "MASM (Microsoft Macro Assembler), directives"
  - "MASM (Microsoft Macro Assembler), opérateurs"
  - "MASM (Microsoft Macro Assembler), structures"
  - "opérateurs (MASM)"
  - "structures (C++), MASM"
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Directives de donn&#233;es et op&#233;rateurs dans un assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Bien qu'un bloc `__asm` puisse faire référence à des types de données et des objets C ou C\+\+, il ne peut pas définir d'objets de données avec des directives ou des opérateurs MASM.  Plus précisément, vous ne pouvez pas utiliser les directives de définition **DB**, `DW`, **JJ**, `DQ`, `DT` et `DF` ou les opérateurs `DUP` ou **THIS**.  Les structures et les enregistrements MASM ne sont pas non plus disponibles.  L'assembleur inline n'accepte pas les directives `STRUC`, `RECORD`, **WIDTH** ou **MASK**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation du langage assembleur dans les blocs \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)