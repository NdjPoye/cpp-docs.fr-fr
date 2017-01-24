---
title: "noexcept (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noexcept_cpp"
dev_langs: 
  - "C++"
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# noexcept (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+11** : spécifie si une fonction peut lever des exceptions.  
  
## Syntaxe  
  
```vb  
ReturnType FunctionName(params) noexcept;  
ReturnType FunctionName(params) noexcept(noexcept(expression);  
```  
  
#### Paramètres  
 expression  
 Expression constante qui prend la valeur True ou False.  La version non conditionnelle est équivalente à noexcept\(true\).  
  
## Notes  
 `noexcept` et son synonyme `noecept(true)` spécifient que la fonction ne lèvera jamais d'exception et qu'elle n'autorisera jamais la propagation d'une exception à partir d'une autre fonction qu'elle appelle directement ou indirectement.  Plus précisément, `noexcept` signifie que la fonction est `noexcept` uniquement si toutes les fonctions qu'elle appelle sont également noexcept ou const, et s'il n'y a pas de casts dynamiques potentiellement évalués qui nécessitent une vérification à l'exécution, des expressions typeid appliquées à une expression glvalue ayant un type de classe polymorphe, ou des expressions throw.  Toutefois, le compilateur ne vérifie pas toujours chaque chemin de code pour rechercher la présence d'exceptions susceptibles d'atteindre une fonction `noexcept`.  Si une exception atteint une fonction marquée avec `noexcept`, [std::terminate](../Topic/terminate%20\(%3Cexception%3E\).md) est appelé immédiatement, sans garantie d'appel des destructeurs des objets dans la portée.  
  
 Une fonction déclarée avec un noexcept conditionnel qui prend la valeur noexcept\(false\) spécifie qu'elle autorise la propagation des exceptions.  Par exemple, une fonction qui copie son argument peut être déclarée noexcept si l'objet copié est un type POD \(Plain Old Data\).  Cette fonction peut être déclarée comme suit :  
  
```  
#include <type_traits>  
  
template <typename T>  
T copy_object(T& obj) noexcept(std::is_pod<T>)  
{  
 //. . .   
}  
  
```  
  
 Utilisez `noexcept` au lieu du spécificateur d'exception `throw`, qui est déconseillé dans C\+\+11 et les versions ultérieures.  Nous vous recommandons de déclarer une fonction avec `noexcept` quand vous êtes sûr qu'elle n'autorisera jamais la propagation d'une exception vers le haut de la pile des appels.  Une fonction déclarée avec `noexcept` permet aux compilateurs de générer un code plus performant dans plusieurs contextes différents.  
  
## Voir aussi  
 [Gestion d'exceptions C\+\+](../cpp/cpp-exception-handling.md)