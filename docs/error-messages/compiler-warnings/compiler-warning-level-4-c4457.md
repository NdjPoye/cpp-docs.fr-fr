---
title: "Du compilateur (niveau 4) d’avertissement C4457 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4457
dev_langs:
- C++
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 77965ba08b311768b54788692d3f5b7fa724f5b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4457"></a>Du compilateur (niveau 4) d’avertissement C4457
  
> déclaration de '*identificateur*' paramètre de fonction de masque
  
La déclaration de *identificateur* dans l’étendue locale masque la déclaration du paramètre portant le même nom de fonction. Cet avertissement vous informe que les références à *identificateur* dans l’étendue locale correspondent à la version déclarée localement, pas le paramètre, ce qui peut ou ne peut pas être votre intention. Pour résoudre ce problème, nous vous recommandons de que vous donnez des noms de variables locales qui ne sont pas conflictuels portant des noms de paramètre.  
    
## <a name="example"></a>Exemple
  
L’exemple suivant génère C4457, car le paramètre `x` et la variable locale `x` dans `member_fn` ont le même nom. Pour résoudre ce problème, utilisez des noms différents pour les paramètres et les variables locales.  
  
```cpp  
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        } 
        a += x; // uses parameter x
    }
} s;
```  
