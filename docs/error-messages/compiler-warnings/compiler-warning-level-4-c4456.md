---
title: "Du compilateur (niveau 4) d’avertissement C4456 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
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
ms.openlocfilehash: 8698c9a430a79bbec1f6e82b8ac58067317c59a1
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4456"></a>Du compilateur (niveau 4) d’avertissement C4456
  
> déclaration de '*identificateur*' masque la déclaration locale précédente
  
La déclaration de *identificateur* dans l’étendue locale masque la déclaration de la déclaration locale précédente du même nom. Cet avertissement vous informe que les références à *identificateur* dans l’étendue locale correspondent à la version déclarée localement, pas précédente local, ce qui peut ou ne peut pas être votre intention. Pour résoudre ce problème, nous vous recommandons de que vous donner des noms de variables locales qui éviter les conflits avec d’autres noms locaux.  
    
## <a name="example"></a>Exemple
  
L’exemple suivant génère C4456, car la variable de contrôle de la boucle `int x` et la variable locale `double x` dans `member_fn` ont le même nom. Pour résoudre ce problème, utilisez des noms différents pour les variables locales.  
  
```cpp  
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        } 
        x += u; // uses local double x
    }
} s;
```  

