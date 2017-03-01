---
title: "Conventions de la bibliothèque C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, conventions
- classes [C++]
- functions [C++], library naming conventions
- naming conventions [C++], C++ Standard Library
- conventions [C++], C++ Standard Library
- function names [C++]
- coding conventions, C++ Standard Library
- naming conventions [C++], C++ library
ms.assetid: bf41b79a-2d53-4f46-8d05-779358335146
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 55d3959b12b1b1a25a6c4b5c65fce59db57cf838
ms.lasthandoff: 02/24/2017

---
# <a name="c-library-conventions"></a>Conventions de la bibliothèque C++
La bibliothèque C++ obéit à une grande partie des conventions de la bibliothèque C Standard, plus quelques autres décrites ici.  
  
 Une implémentation a une certaine latitude dans la façon dont elle déclare des types et des fonctions dans la bibliothèque C++ :  
  
-   Les noms de fonctions dans la bibliothèque C Standard peuvent avoir une liaison externe #« C++ » ou « C ». Incluez l’en-tête C Standard approprié au lieu de déclarer une entité de bibliothèque en ligne.  
  
-   Un nom de fonction membre dans une classe de bibliothèque peut avoir des signatures de fonction supplémentaires par rapport à celles qui sont répertoriées dans ce document. Vous pouvez être certain qu’un appel de fonction décrit ici se comporte comme prévu, mais vous ne pouvez pas prendre de manière fiable l’adresse d’une fonction membre de bibliothèque. (Le type peut ne pas être celui que vous attendez.)  
  
-   Une classe de bibliothèque peut avoir des classes de base (non virtuelles) non documentées. Une classe documentée comme étant dérivée d’une autre classe peut, en fait, être dérivée de cette classe par le biais d’autres classes non documentées.  
  
-   Un type défini comme synonyme d’un type entier peut être identique à l’un de plusieurs types entiers différents.  
  
-   Un type de masque de bits peut être implémenté comme un type entier ou une énumération. Dans les deux cas, vous pouvez effectuer des opérations au niveau du bit (comme `AND` et `OR`) sur des valeurs du même type de masque de bits. Les éléments `A` et `B` d’un type de masque de bits sont des valeurs différentes de zéro de sorte que `A` & `B` est égal à zéro.  
  
-   Une fonction de bibliothèque qui n’a aucune spécification d’exception peut lever une exception arbitraire, sauf si sa définition restreint clairement cette possibilité.  
  
 En revanche, il existe certaines restrictions :  
  
-   La bibliothèque C Standard n’utilise aucune macro de masque. Seules les signatures de fonctions spécifiques sont réservées, mais pas les noms des fonctions.  
  
-   Un nom de fonction de bibliothèque en dehors d’une classe n’a pas de signature de fonction non documentée supplémentaire. Vous pouvez prendre son adresse de manière fiable.  
  
-   Les classes de base et les fonctions membres décrites comme virtuelles sont réellement virtuelles, et celles qui sont décrites comme non virtuelles sont réellement non virtuelles.  
  
-   Deux types définis par la bibliothèque C++ sont toujours différents, sauf si ce document indique explicitement le contraire.  
  
-   Les fonctions fournies par la bibliothèque, y compris les versions par défaut des fonctions remplaçables, peuvent lever *au maximum* les exceptions répertoriées dans une spécification d’exception. Aucun destructeur fourni par la bibliothèque ne lève d’exception. Les fonctions de la bibliothèque C Standard peuvent propager une exception, comme quand `qsort` appelle une fonction de comparaison qui lève une exception, mais elles ne lèvent pas d’exception dans les autres cas.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la bibliothèque standard C++](../standard-library/cpp-standard-library-overview.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


