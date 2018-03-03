---
title: "Classement partiel des modèles de fonction (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cddc0f1680a3354276a2135dd28c31a2037a8202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="partial-ordering-of-function-templates-c"></a>Tri partiel des modèles de fonction (C++)

Plusieurs modèles de fonction qui correspondent à la liste d’arguments d’un appel de fonction peuvent être disponibles. C++ définit un classement partiel des modèles de fonction pour spécifier quelle fonction doit être appelée. Le classement est partiel car certains modèles peuvent être considérés comme également spécialisés.

Le compilateur sélectionne la fonction de modèle la plus spécialisée disponible parmi les correspondances possibles. Par exemple, si un modèle de fonction prend un type __T__et un autre modèle de fonction prenant __T\*__  n’est disponible, le __T\*__  version est dite plus spécialisée et sont préférable à l’objet générique __T__ version chaque fois que l’argument est un type pointeur, même si les deux sont autorisées correspondances.

Utilisez le processus suivant pour déterminer si un candidat de modèle de fonction est plus spécialisé :

1. Considérez deux modèles de fonction, T1 et T2.

2. Remplacez les paramètres dans T1 par un type unique hypothétique X.

3. Avec la liste de paramètres dans T1, vérifiez si T2 est un modèle valide pour cette liste de paramètres. Ignorez toutes les conversions implicites.

4. Répétez le même processus en inversant T1 et T2.

5. Si un modèle est une liste d’arguments template valide pour l’autre modèle, mais que l’inverse n’est pas vrai, ce modèle est considéré comme moins spécialisé que l’autre modèle. Si les deux modèles en utilisant les arguments valides précédente étape formulaire pour eux, ils sont considérés comme également spécialisés et les résultats d’un appel ambigu lorsque vous tentez d’utiliser.

6. Grâce à ces règles :

     1. Une spécialisation de modèle pour un type spécifique est plus spécialisée qu’une spécialisation acceptant un argument de type générique.

     2. Un modèle en prenant uniquement __T\*__  est plus spécialisé qu’un prenant uniquement __T__, car le type d’un hypothétique __X\*__  est un argument valid pour un __T__ argument de modèle, mais __X__ n’est pas un argument valide pour un __T\*__  argument template.

     3. __const T__ est plus spécialisé que __T__, car __X const__ est un argument valid pour un __T__ argument de modèle, mais __X__ n’est pas un argument valide pour un __const T__ argument template.

     4. __const T\*__  est plus spécialisé que __T\*__, car __X const\*__  est un argument valid pour un __T\*__  argument de modèle, mais __X\*__  n’est pas un argument valide pour un __const T\*__  argument template.

## <a name="example"></a>Exemple

L’exemple suivant fonctionne comme indiqué dans la norme :

```cpp
// partial_ordering_of_function_templates.cpp
// compile with: /EHsc
#include <iostream>

extern "C" int printf(const char*,...);
template <class T> void f(T) {
   printf_s("Less specialized function called\n");
}

template <class T> void f(T*) {
   printf_s("More specialized function called\n");
}

template <class T> void f(const T*) {
   printf_s("Even more specialized function for const T*\n");
}

int main() {
   int i =0;
   const int j = 0;
   int *pi = &i;
   const int *cpi = &j;

   f(i);   // Calls less specialized function.
   f(pi);  // Calls more specialized function.
   f(cpi); // Calls even more specialized function.
   // Without partial ordering, these calls would be ambiguous.
}
```  
  
### <a name="output"></a>Sortie  
  
```  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## <a name="see-also"></a>Voir aussi

[Modèles de fonctions](../cpp/function-templates.md)
