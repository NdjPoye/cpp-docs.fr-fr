---
title: "Minutage de la gestion des exceptions : résumé | Documents Microsoft"
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
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- SETJMPEX.H
- termination handlers [C++], timing
- SETJMP.H
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0ba1075095381229667c7164aa7de7f3e4537486
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="timing-of-exception-handling-a-summary"></a>Synchronisation de la gestion des exceptions : Résumé
Un gestionnaire de terminaisons est exécuté quelle que soit la raison pour laquelle le bloc d'instructions `__try` est arrêté. Les causes incluent la sortie du bloc `__try`, une instruction `longjmp` qui transfère le contrôle à l'extérieur du bloc et le déroulement de la pile en raison de la gestion des exceptions.  
  
> [!NOTE]
>  Visual C++ prend en charge deux formes des instructions `setjmp` et `longjmp`. La version rapide ignore la gestion du bloc de fin mais est plus efficace. Pour utiliser cette version, incluez le fichier SETJMP.H. L'autre version prend en charge la gestion du bloc de fin, comme il est décrit dans le paragraphe précédent. Pour utiliser cette version, incluez le fichier SETJMPEX.H. L'augmentation des performances de la version rapide dépend de la configuration matérielle.  
  
 Le système d'exploitation exécute tous les gestionnaires de terminaisons dans l'ordre approprié avant que tout autre code soit exécuté, notamment le corps d'un gestionnaire d'exceptions.  
  
 Lorsque la cause de l'interruption est une exception, le système doit d'abord exécuter la partie de filtre d'un ou plusieurs gestionnaires d'exceptions avant de décider ce qui doit être terminé. L'ordre des événements est le suivant :  
  
1.  une exception est levée.  
  
2.  Le système examine la hiérarchie des gestionnaires d'exceptions actifs et applique le filtre du gestionnaire avec la priorité la plus élevée. C'est le gestionnaire d'exceptions dernièrement installé et le plus profondément imbriqué en termes de blocs et d'appels de fonction.  
  
3.  Si ce filtre passe la main (retourne 0), le processus se poursuit jusqu'à ce qu'il trouve un filtre qui ne passe pas la main.  
  
4.  Si ce filtre retourne -1, l’exécution continue où l’exception a été levée et aucun arrêt n’a lieu.  
  
5.  Si le filtre retourne 1, les événements suivants se produisent :  
  
    -   Le système déroule la pile, effaçant tous les frames de pile entre le code en cours d'exécution (où l'exception a été levée) et le frame de pile qui contient le gestionnaire d'exceptions qui prend la main.  
  
    -   Au fur et à mesure que la pile est déroulée, chaque gestionnaire de terminaisons figurant sur la pile est exécuté.  
  
    -   Le gestionnaire d'exceptions lui-même est exécuté.  
  
    -   La ligne de code prend la main après la fin de ce gestionnaire d'exceptions.  
  
## <a name="see-also"></a>Voir aussi  
 [L’écriture d’un gestionnaire de terminaisons](../cpp/writing-a-termination-handler.md)   
 [Gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
