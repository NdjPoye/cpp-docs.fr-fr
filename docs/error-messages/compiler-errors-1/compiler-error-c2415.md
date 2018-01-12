---
title: Erreur du compilateur C2415 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2415
dev_langs: C++
helpviewer_keywords: C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ff0f423ec83b9951e806a2483417f3ab79f817a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2415"></a>Erreur du compilateur C2415
type d’opérande incorrect  
  
 L’opcode n’utilise pas d’opérandes de ce type.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  L’opcode ne prend pas en charge le nombre d’opérandes utilisés. Vérifier un manuel de référence de langage d’assembly pour déterminer le nombre d’opérandes correct.  
  
2.  Un processeur plus récent prend en charge l’instruction avec des types supplémentaires. Ajuster la [/arch (Architecture d’UC minimale)](../../build/reference/arch-minimum-cpu-architecture.md) permet d’utiliser le processeur le plus récent.