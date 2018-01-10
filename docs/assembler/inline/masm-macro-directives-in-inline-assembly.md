---
title: "Directives de Macro MASM dans l’Assembly Inline | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0df9f8584b87e511c43430a5c0df7dac61805ede
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Directives relatives aux macros MASM dans l'assembly inline
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 L'assembleur inline n'est pas un macro-assembleur. Vous ne pouvez pas utiliser les directives de macro MASM (**MACRO**, `REPT`, **IRC**, `IRP`, et `ENDM`) ou des opérateurs de macro (**<>**, **!** ,  **&** , `%`, et `.TYPE`). Un bloc `__asm` peut cependant utiliser des directives de préprocesseur C. Consultez [à l’aide de C ou C++ dans les blocs __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) pour plus d’informations.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation du langage assembleur dans les blocs __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)