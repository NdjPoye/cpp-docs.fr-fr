---
title: Compilateur avertissement (niveau 1) C4799 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f41535c01d67e28baa2569ace2684865407a1d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4799"></a>Avertissement du compilateur (niveau 1) C4799  
  
> Aucune instruction EMMS à la fin de la fonction '*fonction*'  
  
La fonction a au moins une instruction MMX, mais n’a pas un `EMMS` instruction. Lorsqu’une instruction multimédia est utilisée, un `EMMS` instruction ou `_mm_empty` intrinsèque doit également être utilisée pour effacer le mot de la balise multimédia à la fin du code MMX.  
  
C4799 peut apparaître lorsque vous utilisez ivec.h, indiquant que le code n’utilise pas correctement exécuter l’instruction EMMS avant de retourner. Il s’agit d’un avertissement erroné pour ces en-têtes. Vous pouvez désactiver ceux-ci en définissant _SILENCE_IVEC_C4799 dans ivec.h. Toutefois, sachez que cela empêchera le compilateur de fournir des avertissements corrects de ce type.  
  
Pour plus d’informations, consultez [du jeu d’instructions MMX d’Intel](../../assembler/inline/intel-s-mmx-instruction-set.md).