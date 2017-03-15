---
title: "V&#233;rification des remplacements de m&#233;moire | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mémoire, remplacements"
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# V&#233;rification des remplacements de m&#233;moire
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Si vous obtenez une violation d'accès à la suite d'un appel à une fonction de manipulation de tas, il est possible que votre programme ait endommagé le tas en question.  Cette situation se caractérise par le symptôme commun suivant :  
  
```  
Access Violation in _searchseg  
```  
  
 La fonction [\_heapchk](../../c-runtime-library/reference/heapchk.md) est disponible dans les deux versions debug et release \(Windows NT uniquement\) pour vérifier l'intégrité du tas de la bibliothèque d'exécution.  Vous pouvez utiliser `_heapchk` pratiquement de la même manière que la fonction `AfxCheckMemory` pour identifier un remplacement de tas ; par exemple :  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 Si cette fonction échoue, vous devez déterminer à quel niveau le tas a été endommagé.  
  
## Voir aussi  
 [Résolution de problèmes liés à la version release](../../build/reference/fixing-release-build-problems.md)