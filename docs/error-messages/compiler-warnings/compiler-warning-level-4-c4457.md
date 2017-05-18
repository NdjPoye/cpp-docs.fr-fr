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
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 4977ade625e3f4af5f01364b865d2c2f41ebe80a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

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

