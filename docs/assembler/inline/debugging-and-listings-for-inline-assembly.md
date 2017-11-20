---
title: "Débogage et listes pour l’Assembly Inline | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 532d76f5f7a51e6c84067b442e6469b83994db7d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Débogage et listes pour l'assembly inline
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Programmes contenant le code assembleur inline peuvent être débogués avec un débogueur au niveau source si vous compilez avec le [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) option.  
  
 Dans le débogueur, vous pouvez définir des points d'arrêt sur C ou C++ et des lignes en langage assembleur. Si vous activez le mode mixte assembly et source, vous pouvez consulter la source et le formulaire désassemblé du code assembleur.  
  
 Notez que mettre plusieurs instructions assembleur ou plusieurs instructions de langage source sur une ligne peut entraver le débogage. En mode source, vous pouvez utiliser le débogueur pour définir des points d'arrêt sur une ligne unique, mais pas sur des instructions individuelles sur la même ligne. Le même principe s'applique à un bloc `__asm` défini comme macro C, qui se développe en une seule ligne logique.  
  
 Si vous créez une source mixte et l’assembly répertorier avec la [/FAS](../../build/reference/fa-fa-listing-file.md) option du compilateur, la liste contient des formes de la source et l’assembly de chaque ligne en langage assembleur. Les macros ne sont pas développées dans les listes, mais elles sont développées pendant la compilation.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation du langage assembleur dans les blocs __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)