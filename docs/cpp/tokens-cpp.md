---
title: Jetons (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- tokens [C++]
- parsing, C++ tokens
- translation units
- white space, in C++ tokens
ms.assetid: aa812fd0-6d47-4f3f-aee0-db002ee4d8b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba2e1a6cc36e4e5f2f785c1e5dff03c6fb5e392d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="tokens-c"></a>Jetons (C++)
Un jeton est le plus petit élément d’un programme C++ qui est significatif pour le compilateur. L’analyseur C++ reconnaît les genres de jetons suivants : identificateurs, mots clés, littéraux, opérateurs, signes de ponctuation et autres séparateurs. Un flux de ces jetons constitue une unité de traduction.  
  
 Les jetons sont généralement séparés par un *espace blanc*. Un espace blanc correspond à un ou plusieurs des éléments suivants :  
  
-   Espaces  
  
-   Tabulations horizontales ou verticales  
  
-   Nouvelles lignes  
  
-   Sauts de page  
  
-   Commentaires  
  
 L’analyseur reconnaît les mots clés, les identificateurs, les littéraux, les opérateurs et les signes de ponctuation. Pour plus d’informations sur des types de jeton spécifiques, consultez [Mots clés](../cpp/keywords-cpp.md), [Identificateurs](../cpp/identifiers-cpp.md), [Littéraux numériques, booléens et de pointeur](../cpp/numeric-boolean-and-pointer-literals-cpp.md), [Littéraux de chaîne et de caractère](../cpp/string-and-character-literals-cpp.md), [Littéraux définis par l’utilisateur](../cpp/user-defined-literals-cpp.md), [Opérateurs C++ Priorité des opérateurs et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md), et [Signes de ponctuation](../cpp/punctuators-cpp.md). L’espace blanc est ignoré, sauf s’il est nécessaire pour séparer les jetons.  
  
 Les jetons de prétraitement sont utilisés dans les phases de prétraitement pour générer le flux de jetons passé au compilateur. Les catégories de jetons de prétraitement sont les noms d’en-têtes, les identificateurs, les numéros de prétraitement, les littéraux de caractère, les littéraux de chaîne, les opérateurs de prétraitement et les signes de ponctuation, ainsi que les caractères uniques autres que les espaces blancs qui ne correspondent pas à l’une des autres catégories. Les littéraux de caractère et de chaîne peuvent être des littéraux définis par l’utilisateur. Les jetons de prétraitement peuvent être séparés par un espace blanc ou des commentaires.  
  
 L’analyseur sépare les jetons du flux d’entrée en créant le jeton le plus long possible à l’aide des caractères d’entrée via une analyse de gauche à droite. Prenons le fragment de code suivant :  
  
```  
a = i+++j;  
```  
  
 Le programmeur qui a écrit le code fait référence à deux instructions possibles :  
  
```  
a = i + (++j)  
  
a = (i++) + j  
```  
  
 Dans la mesure où l’analyseur crée le jeton le plus long possible à partir du flux d’entrée, il choisit la seconde interprétation, et crée les jetons `i++`, `+`et `j`.  
  
## <a name="see-also"></a>Voir aussi  
 [Conventions lexicales](../cpp/lexical-conventions.md)