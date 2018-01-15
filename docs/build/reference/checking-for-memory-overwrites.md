---
title: "Vérification des remplacements de mémoire | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 573710ae62384c8674009770b3c4fb29100db446
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="checking-for-memory-overwrites"></a>Vérification des remplacements de mémoire
Si vous obtenez une violation d’accès sur un appel à une fonction de manipulation de segment de mémoire, il est possible que votre programme a endommagé le tas. Un problème courant de cette situation serait :  
  
```  
Access Violation in _searchseg  
```  
  
 Le [_heapchk](../../c-runtime-library/reference/heapchk.md) fonction est disponible dans les versions debug et les versions release (Windows NT uniquement) pour vérifier l’intégrité du tas de bibliothèque d’exécution. Vous pouvez utiliser `_heapchk` dans la même façon que le `AfxCheckMemory` fonction afin d’isoler le remplacement d’un segment de mémoire, par exemple :  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 Si cette fonction échoue, vous devez isoler à quel point le tas a été endommagé.  
  
## <a name="see-also"></a>Voir aussi  
 [Résolution de problèmes liés à la version Release](../../build/reference/fixing-release-build-problems.md)