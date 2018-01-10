---
title: Erreur du compilateur C2414 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2414
dev_langs: C++
helpviewer_keywords: C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6238cf17686eb168a2f120c00fc34655715a950
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2414"></a>Erreur du compilateur C2414
nombre non conforme d’opérandes  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  L’opcode ne prend pas en charge le nombre d’opérandes utilisés. Vérifier un manuel de référence de langage d’assembly pour déterminer le nombre d’opérandes correct.  
  
2.  Un processeur plus récent prend en charge l’instruction avec un nombre différent d’opérandes. Ajuster la [/arch (Architecture d’UC minimale)](../../build/reference/arch-minimum-cpu-architecture.md) permet d’utiliser le processeur le plus récent.