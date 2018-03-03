---
title: "Directives de données et les opérateurs dans l’Assembly Inline | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2352b1809f2c0377f17fde8127fcbda6464617a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Directives et opérateurs de données dans l'assembly inline
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Bien qu'un bloc `__asm` puisse faire référence à des types de données et des objets C ou C++, il ne peut pas définir d'objets de données avec des directives ou des opérateurs MASM. Plus précisément, vous ne pouvez pas utiliser les directives de définition **DB**, `DW`, **jj**, `DQ`, `DT`, et `DF`, ou les opérateurs `DUP` ou  **Cela**. Les structures et les enregistrements MASM ne sont pas non plus disponibles. L’assembleur inline n’accepte pas les directives `STRUC`, `RECORD`, **largeur**, ou **masque**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation du langage assembleur dans les blocs __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)