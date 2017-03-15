---
title: "Directives EVEN et ALIGN | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "align"
  - "EVEN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIGN (directive)"
  - "directives, MASM"
  - "EVEN (directive)"
  - "MASM (Microsoft Macro Assembler), directives"
  - "NOP (instruction de non fonctionnement)"
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Directives EVEN et ALIGN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Bien que l'assembleur inline ne prenne pas en charge la plupart des directives MASM, il prend en charge `EVEN` et **ALIGN**.  Ces directives placent de façon adéquate l'instruction **NOP** \(aucune opération\) dans le code assembleur pour aligner les étiquettes sur des limites spécifiques.  Cela rend les opérations d'extraction d'instruction plus efficaces pour certains processeurs.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation du langage assembleur dans les blocs \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)