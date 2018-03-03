---
title: "À l’aide de la version Debug pour vérifier les remplacements de mémoire de | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f18a13992e41cd88bc8edec44f16b02da38ad10c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Utilisation de la version debug pour vérifier les remplacements de mémoire
Pour utiliser la version debug pour vérifier les remplacements de mémoire, vous devez tout d’abord reconstruire votre projet pour le débogage. Ensuite, allez jusqu’au début de votre application `InitInstance` la fonction et ajoutez la ligne suivante :  
  
```  
afxMemDF |= checkAlwaysMemDF;  
```  
  
 L’allocateur de mémoire debug place des octets de protection autour de toutes les allocations de mémoire. Toutefois, ces octets de garde n’est d’aucune utilité, sauf si vous vérifiez s’ils ont été modifiés (ce qui indiquerait un remplacement de mémoire). Dans le cas contraire, il fournit simplement une mémoire tampon qui peut, en fait, vous permettre de vous en sortir avec un remplacement de mémoire.  
  
 En activant le `checkAlwaysMemDF`, vous obligera MFC pour effectuer un appel à la `AfxCheckMemory` fonction chaque fois qu’un appel à **nouveau** ou **supprimer** est effectuée. Si un remplacement de mémoire a été détecté, il génère un message TRACE qui ressemble à ce qui suit :  
  
```  
Damage Occurred! Block=0x5533  
```  
  
 Si vous voyez un de ces messages, vous devez parcourir votre code pour déterminer où l’erreur s’est produite. Pour identifier plus précisément où le remplacement de mémoire s’est produite, vous pouvez adresser des appels explicites à `AfxCheckMemory` vous-même. Exemple :  
  
```  
ASSERT(AfxCheckMemory());  
    DoABunchOfStuff();  
    ASSERT(AfxCheckMemory());  
```  
  
 Si la première instruction ASSERT réussit et que la seconde échoue, cela signifie que le remplacement de mémoire doit s’être produite dans la fonction entre les deux appels.  
  
 Selon la nature de votre application, vous pouvez constater que `afxMemDF` entraîne l’exécution trop lente même pour un test de votre programme. Le `afxMemDF` provoque la variable `AfxCheckMemory` à pour chaque appel à new et delete. Dans ce cas, vous devez distribuer vos propres appels à `AfxCheckMemory`(), comme indiqué ci-dessus et essayer de détecter la mémoire remplacement de cette manière.  
  
## <a name="see-also"></a>Voir aussi  
 [Résolution de problèmes liés à la version Release](../../build/reference/fixing-release-build-problems.md)