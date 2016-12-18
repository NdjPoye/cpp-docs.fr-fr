---
title: "D&#233;bogage et listes pour l&#39;assembly inline | Microsoft Docs"
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
  - "__asm (mot clé) (C++), débogage"
  - "bogues, __asm (blocs)"
  - "déboguer (C++), code assembleur inline"
  - "assembleur inline, débogage"
  - "assembleur inline, listes"
  - "débogueur au niveau de la source"
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;bogage et listes pour l&#39;assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Les programmes contenant du code assembleur inline peuvent être débogués avec un débogueur au niveau de la source si vous compilez avec l'option [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 Dans le débogueur, vous pouvez définir des points d'arrêt sur C ou C\+\+ et des lignes en langage assembleur.  Si vous activez le mode mixte assembly et source, vous pouvez consulter la source et le formulaire désassemblé du code assembleur.  
  
 Notez que mettre plusieurs instructions assembleur ou plusieurs instructions de langage source sur une ligne peut entraver le débogage.  En mode source, vous pouvez utiliser le débogueur pour définir des points d'arrêt sur une ligne unique, mais pas sur des instructions individuelles sur la même ligne.  Le même principe s'applique à un bloc `__asm` défini comme macro C, qui se développe en une seule ligne logique.  
  
 Si vous créez une liste mixte de source et d'assemblys à l'aide de l'option du compilateur [\/FAs](../../build/reference/fa-fa-listing-file.md), la liste contient les formulaires source et d'assembly de chaque ligne en langage assembleur.  Les macros ne sont pas développées dans les listes, mais elles sont développées pendant la compilation.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation du langage assembleur dans les blocs \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)