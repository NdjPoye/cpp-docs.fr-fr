---
title: "Utilisation de la version debug pour v&#233;rifier les remplacements de m&#233;moire | Microsoft Docs"
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
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation de la version debug pour v&#233;rifier les remplacements de m&#233;moire
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour utiliser la version debug afin de vérifier les remplacements de mémoire, vous devez d'abord régénérer votre projet en vue de produire une version debug.  Ensuite, allez au début de la fonction `InitInstance` de votre application et ajoutez la ligne suivante :  
  
```  
afxMemDF |= checkAlwaysMemDF;  
```  
  
 L'allocateur de mémoire debug place des octets de garde autour de toutes les allocations de mémoire.  Cependant, ces octets de garde ne servent à rien si vous ne vérifiez pas s'ils ont été modifiés \(ce qui indiquerait un remplacement de mémoire\).  Sinon, il s'agirait juste d'une mémoire tampon qui peut, en fait, vous permettre de vous en sortir avec un remplacement de mémoire.  
  
 En activant `checkAlwaysMemDF`, vous forcerez les MFC à lancer un appel à la fonction `AfxCheckMemory` chaque fois qu'un appel est adressé à **new** ou à **delete**.  Si un remplacement de mémoire est détecté, un message TRACE similaire à celui\-ci apparaît :  
  
```  
Damage Occurred! Block=0x5533  
```  
  
 Si vous obtenez l'un de ces messages, vous devez exécuter le code pas à pas afin de déterminer où les dommages se sont produits.  Pour identifier avec plus de précision l'emplacement où le remplacement de mémoire a eu lieu, vous pouvez adresser vous\-même des appels explicites à `AfxCheckMemory`.  Par exemple :  
  
```  
ASSERT(AfxCheckMemory());  
    DoABunchOfStuff();  
    ASSERT(AfxCheckMemory());  
```  
  
 Si la première instruction ASSERT réussit et que la seconde échoue, cela signifie que le remplacement de mémoire a dû se produire dans la fonction entre les deux appels.  
  
 Selon la nature de votre application, vous pouvez constater que `afxMemDF` entraîne une exécution trop lente de votre programme, même pour un test.  La variable `afxMemDF` fait correspondre un appel à `AfxCheckMemory` à chaque appel à new et delete.  En ce cas, vous devez distribuer vos propres appels à `AfxCheckMemory`\( \) comme indiqué ci\-dessus, et essayer de détecter le remplacement de mémoire de cette manière.  
  
## Voir aussi  
 [Résolution de problèmes liés à la version release](../../build/reference/fixing-release-build-problems.md)