---
title: "MÊME et ALIGNEZ les Directives | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- align
- EVEN
dev_langs:
- C++
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 278794e0105ee054fdd4948967a78982a9d46d8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="even-and-align-directives"></a>MÊME et ALIGNEZ les directives
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Bien que l’assembleur inline ne prend pas en charge la plupart des directives MASM, il prend en charge `EVEN` et **aligner**. Ces directives placent **NOP** (aucune opération) des instructions dans le code de l’assembly en fonction des besoins pour aligner les étiquettes sur des limites spécifiques. Cela rend les opérations de récupération d’instruction plus efficaces pour certains processeurs.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation du langage assembleur dans les blocs __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)