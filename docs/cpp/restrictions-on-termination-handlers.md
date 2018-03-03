---
title: Restrictions sur les gestionnaires de terminaisons | Documents Microsoft
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
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 71486b167f4e9939d4913b3660ed3513dc02b8f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="restrictions-on-termination-handlers"></a>Restrictions sur les gestionnaires de terminaison
Vous ne pouvez pas utiliser une instruction `goto` pour accéder à un bloc d'instructions `__try` ou à un bloc d'instructions `__finally`. À la place, vous devez entrer dans le bloc d'instruction via le flux de contrôle normal. (Vous pouvez toutefois sauter hors d'un bloc d'instructions `__try`.) En outre, vous ne pouvez pas imbriquer un gestionnaire d'exceptions ou un gestionnaire de terminaisons dans un bloc `__finally`.  
  
 Certains types de code autorisés dans un gestionnaire de terminaisons produisent des résultats incertains. Si vous en utilisez, faites-le avec précaution. Par exemple, une instruction `goto` qui saute hors d'un bloc d'instructions `__finally`. Si le bloc s'exécute dans le cadre de l'arrêt normal, rien d'inhabituel ne se produit. Mais si le système est en train de dérouler la pile, ce déroulement s'arrête, et la fonction actuelle prend le contrôle comme s'il n'y avait pas eu d'arrêt anormal.  
  
 Une instruction `return` dans un bloc d'instructions `__finally` présente à peu près la même situation. Le contrôle retourne à l'appelant immédiat de la fonction contenant le gestionnaire de terminaisons. Si le système était en train de dérouler la pile, ce processus est désactivé, et le programme continue comme si aucune exception n'était levée.  
  
## <a name="see-also"></a>Voir aussi  
 [L’écriture d’un gestionnaire de terminaisons](../cpp/writing-a-termination-handler.md)   
 [Gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md)