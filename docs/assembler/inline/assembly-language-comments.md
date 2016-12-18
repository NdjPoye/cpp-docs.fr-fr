---
title: "Commentaires en langage assembleur | Microsoft Docs"
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
  - "__asm (mot clé) (C++), instructions"
  - "langage assembleur (C++), commentaires"
  - "commentaires (C++), langage assembleur"
  - "macros (C++), langage assembleur"
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Commentaires en langage assembleur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Spécifique à Microsoft  
 Instructions dans une  `__asm`bloc peut utiliser des commentaires de langage assembleur :  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 Étant donné que l'expansion des macros C dans une même ligne logique, évitez d'utiliser des commentaires de langage d'assemblage dans les macros.  \(Voir  [définition \_\_asm \(blocs\) en tant que Macros C](../../assembler/inline/defining-asm-blocks-as-c-macros.md).\) Un  `__asm`bloc peut également contenir des commentaires de style C ; Pour plus d'informations, consultez  [à l'aide de C ou C\+\+ dans \_\_asm \(blocs\)](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **FIN spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation du langage assembleur dans les blocs \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)