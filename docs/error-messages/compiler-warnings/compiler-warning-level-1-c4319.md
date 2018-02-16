---
title: Compilateur avertissement (niveau 1) C4319 | Documents Microsoft
ms.custom: 
ms.date: 1/18/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4319
dev_langs:
- C++
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a492194003a639f684e84d125450067cd425276
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="compiler-warning-level-1-c4319"></a>Avertissement du compilateur (niveau 1) C4319

> ' ~' : zéro étendant '*type1*'à'*type2*' d’une taille supérieure

Le résultat de la  **~**  (opérateur) (complément au niveau du bit) est non signé et puis étendu par zéro lorsqu’il est converti en un type plus grand.

## <a name="example"></a>Exemple

Dans l’exemple suivant, `~(a - 1)` est évaluée comme une expression de type long non signée 32 bits et puis convertie au format 64 bits par extension zéro. Cela peut entraîner des résultats d'opération inattendus.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
