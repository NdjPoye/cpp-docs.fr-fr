---
title: "D&#233;finition d&#39;une macro NMAKE | Microsoft Docs"
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
  - "définir des macros NMAKE"
  - "macros, NMAKE"
  - "NMAKE (macros), définition"
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;finition d&#39;une macro NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
macroname=string  
```  
  
## Notes  
 L'élément *macroname* est une combinaison de lettres, de chiffres et de traits de soulignement \(\_\) limitée à 1 024 caractères et respectant la casse.  L'élément *macroname* peut contenir une macro appelée.  Si *macroname* est constitué entièrement d'une macro appelée, la macro appelée ne peut être ni nulle ni non définie.  
  
 L'élément `string` peut correspondre à une séquence quelconque de zéro ou plusieurs caractères.  Une chaîne nulle contient zéro caractère ou seulement des espaces ou des tabulations.  L'élément `string` peut contenir un appel de macro.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 [Caractères spéciaux dans les macros](../build/special-characters-in-macros.md)  
  
 [Macros nulles et non définies](../build/null-and-undefined-macros.md)  
  
 [Où définir des macros](../build/where-to-define-macros.md)  
  
 [Préséance dans les définitions de macros](../build/precedence-in-macro-definitions.md)  
  
## Voir aussi  
 [NMAKE et les macros](../build/macros-and-nmake.md)