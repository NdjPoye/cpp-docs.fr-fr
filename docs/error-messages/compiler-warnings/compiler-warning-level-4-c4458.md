---
title: "Du compilateur (niveau 4) d’avertissement C4458 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4458
dev_langs:
- C++
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
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
ms.openlocfilehash: 07b8db673b2db27f456f0e7228695c83497d1278
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4458"></a>Du compilateur (niveau 4) d’avertissement C4458
  
> déclaration de '*identificateur*' masque le membre de classe
  
La déclaration de *identificateur* dans l’étendue locale masque la déclaration de la portant le même nom *identificateur* à portée de classe. Cet avertissement vous informe que les références à *identificateur* dans cette portée correspondent à la version déclarée localement, pas la classe membre version, ce qui peut ou ne peut pas être votre intention. Pour résoudre ce problème, nous vous recommandons de que vous donnez des noms de variables locales qui éviter les conflits avec les noms de membres de classe.  
    
## <a name="example"></a>Exemple
  
L’exemple suivant génère C4458, car le paramètre `x` et la variable locale `y` dans `member_fn` ont les mêmes noms que les membres de données dans la classe. Pour résoudre ce problème, utilisez des noms différents pour les paramètres et les variables locales.  
  
```cpp  
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;  
        // To fix this issue, change the parameter name x
        // and local name y to something that does not 
        // conflict with the data member names.
    }
} s;
```  

