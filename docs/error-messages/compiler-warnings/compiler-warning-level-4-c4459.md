---
title: "Du compilateur (niveau 4) d’avertissement C4459 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4459
dev_langs: C++
helpviewer_keywords: C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47380915dd18387fa3cc2af54d42a3777aab3f5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4459"></a>Du compilateur (niveau 4) d’avertissement C4459
  
> déclaration de '*identificateur*' masque la déclaration globale
  
La déclaration de *identificateur* dans l’étendue locale masque la déclaration de la portant le même nom *identificateur* dans la portée globale. Cet avertissement vous informe que les références à *identificateur* dans cette portée correspondent à la version déclarée localement, pas la version globale, ce qui peut ou ne peut pas être votre intention. En règle générale, nous vous recommandons de que vous réduisez l’utilisation de variables globales comme une bonne pratique d’ingénierie. Pour réduire la pollution de l’espace de noms global, nous vous recommandons d’utiliser un espace de noms nommé pour les variables globales.  
  
Cet avertissement était nouvel dans Visual Studio 2015, dans Visual C++ version du compilateur 18,00. Pour supprimer les avertissements de cette version du compilateur ou version ultérieure lors de la migration de votre code, utilisez la [/WV : 18](../../build/reference/compiler-option-warning-level.md) option du compilateur. 

## <a name="example"></a>Exemple
  
 L’exemple suivant génère C4459 :  
  
```cpp  
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() { 
    int global_or_local; // warning C4459 
    global_or_local = 2;
} 
```  
  
Une méthode pour résoudre ce problème consiste à créer un espace de noms pour vos variables globales, mais pas utiliser un `using` directive pour placer cet espace de noms dans la portée, par conséquent, toutes les références doivent utiliser la non équivoque des noms complets :  
  
```cpp  
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() { 
    int global_or_local; // OK 
    global_or_local = 2;
    globals::global_or_local = 3;
} 
```  
