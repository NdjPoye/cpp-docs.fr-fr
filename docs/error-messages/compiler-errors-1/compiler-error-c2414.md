---
title: Erreur du compilateur C2414 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2414
dev_langs:
- C++
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f3b532fdb8448f616916adcaf047dc83923f62c0
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2414"></a>Erreur du compilateur C2414
nombre non conforme d’opérandes  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  L’opcode ne prend pas en charge le nombre d’opérandes utilisés. Vérifier un manuel de référence de langage d’assembly pour déterminer le nombre d’opérandes correct.  
  
2.  Un processeur plus récent prend en charge l’instruction avec un nombre différent d’opérandes. Ajuster la [/arch (Architecture d’UC minimale)](../../build/reference/arch-minimum-cpu-architecture.md) permet d’utiliser le processeur le plus récent.
