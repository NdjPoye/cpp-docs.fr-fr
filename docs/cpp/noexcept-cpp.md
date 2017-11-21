---
title: noexcept (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noexcept_cpp
dev_langs: C++
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a45a15fcc2e29a31bc43ab493aa15b58985bf336
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="noexcept-c"></a>noexcept (C++)
**C ++ 11 :** Spécifie si une fonction peut lever des exceptions.  
  
## <a name="syntax"></a>Syntaxe  
  
> *expression de noexcept*:  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept**  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *expression constante* **)**  
  
### <a name="parameters"></a>Paramètres  
 *expression de constante*  
 Une expression constante de type `bool` qui indique si l’ensemble des types d’exceptions potentielles est vide. La version non conditionnelle est équivalente à `noexcept(true)`.  
  
## <a name="remarks"></a>Remarques  
 A *noexcept expression* est une sorte de *spécification d’exception*, un suffixe à une déclaration de fonction qui représente un ensemble de types qui peuvent être mis en correspondance par un gestionnaire d’exceptions pour toute exception qui se termine un fonction. Opérateur conditionnel unaire `noexcept(` *expression_constante* `)` où *expression_constante* yeilds `true`et son synonyme inconditionnel `noexcept`, Spécifiez que le jeu de types d’exceptions potentielles peut quitter une fonction est vide. Autrement dit, la fonction lève jamais d’exception et n’autorise jamais être propagées à l’extérieur de son étendue d’une exception. L’opérateur `noexcept(` *expression_constante* `)` où *expression_constante* yeilds `false`, ou l’absence d’une spécification d’exception (autre que pour un fonction destructeur ou de désallocation), indique que le jeu d’exceptions potentielles que vous pouvez quitter la fonction est l’ensemble de tous les types.  
 
 Marquer une fonction comme `noexcept` uniquement si toutes les fonctions qu’elle appelle directement ou indirectement, sont également `noexcept` ou `const`. Le compilateur ne vérifie pas nécessairement chaque chemin d’accès du code pour les exceptions susceptibles d’atteindre un `noexcept` (fonction). Si une exception quitte la portée externe d’une fonction marquée `noexcept`, [std::terminate](../standard-library/exception-functions.md#terminate) est appelé immédiatement, et il n’existe aucune garantie que les destructeurs de tous les objets dans l’étendue seront appelées. Utilisez `noexcept` au lieu du spécificateur d’exception dynamiques `throw`, qui est déconseillé dans C ++ 11 et version ultérieure et pas totalement implémenté dans Visual Studio. Nous vous recommandons `noexcept` à n’importe quelle fonction qui ne laisse une exception se propager dans la pile des appels. Lorsqu’une fonction est déclarée `noexcept`, il permet au compilateur de générer un code plus performant dans plusieurs contextes différents.    
  
## <a name="example"></a>Exemple  
Une fonction de modèle qui copie son argument peut être déclarée `noexcept` à condition que l’objet copié est un type plain old data (POD). Cette fonction peut être déclarée comme suit :  
  
```cpp  
#include <type_traits>  
  
template <typename T>  
T copy_object(const T& obj) noexcept(std::is_pod<T>)  
{  
   // ...   
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des exceptions C++](../cpp/cpp-exception-handling.md) [spécifications d’Exception (throw, noexcept)](../cpp/exception-specifications-throw-cpp.md)