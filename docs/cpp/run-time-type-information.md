---
title: "Les informations de Type au moment de l’exécution | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs: C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b0b0124a69a0110bda94055964fbcdb54e5a754
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="run-time-type-information"></a>Informations de type au moment de l'exécution
Les informations de type au moment de l'exécution (RTTI) sont un mécanisme qui permet de déterminer le type d'un objet pendant l'exécution du programme. RTTI a été ajouté au langage C++ car de nombreux fournisseurs de bibliothèques de classes implémentaient cette fonctionnalité eux-mêmes. Cela provoquait des incompatibilités entre les bibliothèques. Par conséquent, il est devenu évident que la prise en charge des informations de type au moment de l'exécution s'avérait nécessaire au niveau du langage.  
  
 Pour des raisons de simplicité, cette discussion sur RTTI se limite presque exclusivement aux pointeurs. Toutefois, les concepts présentés également s'appliquent également aux références.  
  
 Il existe trois principaux éléments de langage C++ se rapportant aux informations de type au moment de l'exécution :  
  
-   Le [dynamic_cast](../cpp/dynamic-cast-operator.md) opérateur.  
  
     Utilisé pour la conversion des types polymorphes.  
  
-   Le [typeid](../cpp/typeid-operator.md) opérateur.  
  
     Utilisé pour identifier le type exact d'un objet.  
  
-   Le [type_info](../cpp/type-info-class.md) classe.  
  
     Utilisée pour stocker les informations de type retournées par l'opérateur `typeid`.  
  
## <a name="see-also"></a>Voir aussi  
 [Cast](../cpp/casting.md)