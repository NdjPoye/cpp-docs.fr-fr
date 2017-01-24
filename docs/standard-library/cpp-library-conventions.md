---
title: "Conventions de la biblioth&#232;que C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++)"
  - "conventions de codage, bibliothèque C++ standard"
  - "conventions (C++), bibliothèque C++ standard"
  - "noms de fonctions (C++)"
  - "fonctions (C++), conventions d'affectation de noms aux bibliothèques"
  - "conventions d'affectation de noms (C++), C++ (bibliothèque)"
  - "conventions d'affectation de noms (C++), bibliothèque C++ standard"
  - "bibliothèque C++ standard, conventions"
ms.assetid: bf41b79a-2d53-4f46-8d05-779358335146
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Conventions de la biblioth&#232;que C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque C\+\+ obéit pratiquement les mêmes conventions que la bibliothèque de l'Assistant de c standard, ainsi que certains plus à tracer les grandes lignes ici.  
  
 Une implémentation une certaine latitude dans la façon dont il déclare des types et des fonctions de la bibliothèque C\+\+ :  
  
-   Les noms des fonctions de la bibliothèque de l'Assistant de c standard peuvent avoir extern " \# » C\+\+ ou la liaison extern « c » c.  Incluez l'en\-tête de l'Assistant De c de niveau adéquat plutôt que déclarent une entité de bibliothèque en ligne.  
  
-   Un nom de fonction membre dans une classe de bibliothèque peut avoir les signatures de la fonction supplémentaires sur celles indiquées dans ce document.  Vous pouvez vous assurer qu'un appel de fonction décrit ici se comporte comme prévu, mais vous ne pouvez pas de manière fiable être l'adresse d'une fonction membre de bibliothèque. \(Ne pas être le type est ce que vous vous attendez.\)  
  
-   Une classe de bibliothèque peut avoir des classes de base \(virtuelles\) non documentées.  Une classe documentée comme dérivée d'une classe peut, en fait, être dérivées de cette classe à d'autres classes non documentées.  
  
-   Un type défini comme synonyme d'un certain type entier peut être identique à l'un des différents types entier différent.  
  
-   Un type de masque binaire peut être implémenté en tant que soit un type entier ou une énumération.  Dans l'un et l'autre cas, vous pouvez effectuer des opérations de bits \(telles que `AND` et `OR`\) sur des valeurs de même type de masque de bits.  Les éléments `A` et `B` d'un type de masque de bits sont des valeurs différentes de sorte que `A` &`B` est zéro.  
  
-   Une fonction de bibliothèque qui n'a aucune spécification d'exception peut lever une exception aléatoire, sauf si sa définition restreint clairement une telle possibilité.  
  
 En revanche, certaines restrictions :  
  
-   La bibliothèque de l'Assistant de c standard n'utilise aucune macro masquante.  Seules les signatures de la fonction spécifiques ne sont réservées, pas les noms de fonctions eux\-mêmes.  
  
-   Un nom de fonction dans la bibliothèque à l'extérieur d'une classe n'aura pas supplémentaire, non documenté, signatures de la fonction.  Vous pouvez de manière fiable effectuer son adresse.  
  
-   Les classes de base et virtuel et décrit par fonctions membres sont assurément virtuels, tandis que celles décrites que virtuelles sont assurément virtuels.  
  
-   Deux types définis par la bibliothèque C\+\+ sont toujours différents sauf si ce document suggère explicitement sinon.  
  
-   Les fonctionnalités offertes par la bibliothèque, y compris les versions par défaut des fonctions substituables, peut lever *au plus* ces exceptions énumérées dans toute spécification d'exception.  Destructeur fourni par la bibliothèque ne lève pas d'exceptions.  Les fonctions de la bibliothèque de l'Assistant de c standard peuvent se propager une exception, comme lorsque `qsort` appelle une fonction de comparaison qui lève une exception, mais ils ne lèvent pas d'exceptions sinon.  
  
## Voir aussi  
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)