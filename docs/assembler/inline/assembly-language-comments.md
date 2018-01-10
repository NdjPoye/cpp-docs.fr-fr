---
title: Commentaires en langage assembleur | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee9ab1975a1146b598d7955d15b8e91a0f396724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="assembly-language-comments"></a>Commentaires relatifs au langage assembleur
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Les instructions figurant dans un bloc `__asm` peuvent utiliser des commentaires en langage assembleur :  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 Comme les macros C sont développées en une ligne logique unique, évitez d’utiliser des commentaires en langage assembleur dans les macros. (Consultez [définition des blocs __asm en tant que Macros C](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) Un `__asm` bloc peut également contenir des commentaires de style C ; pour plus d’informations, consultez [à l’aide de C ou C++ dans les blocs __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation du langage assembleur dans les blocs __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)