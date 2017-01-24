---
title: "Informations de type au moment de l&#39;ex&#233;cution | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RTTI (option du compilateur)"
  - "au moment de l'exécution, contrôle de type"
  - "vérifications à l'exécution, contrôle de type"
  - "informations de type au moment de l'exécution"
  - "informations de type, vérification des types au moment de l'exécution"
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Informations de type au moment de l&#39;ex&#233;cution
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les informations de type au moment de l'exécution \(RTTI\) sont un mécanisme qui permet de déterminer le type d'un objet pendant l'exécution du programme.  RTTI a été ajouté au langage C\+\+ car de nombreux fournisseurs de bibliothèques de classes implémentaient cette fonctionnalité eux\-mêmes.  Cela provoquait des incompatibilités entre les bibliothèques.  Par conséquent, il est devenu évident que la prise en charge des informations de type au moment de l'exécution s'avérait nécessaire au niveau du langage.  
  
 Pour des raisons de simplicité, cette discussion sur RTTI se limite presque exclusivement aux pointeurs.  Toutefois, les concepts présentés également s'appliquent également aux références.  
  
 Il existe trois principaux éléments de langage C\+\+ se rapportant aux informations de type au moment de l'exécution :  
  
-   L'opérateur [dynamic\_cast](../cpp/dynamic-cast-operator.md).  
  
     Utilisé pour la conversion des types polymorphes.  
  
-   L'opérateur [typeid](../cpp/typeid-operator.md).  
  
     Utilisé pour identifier le type exact d'un objet.  
  
-   La classe [type\_info](../cpp/type-info-class.md).  
  
     Utilisée pour stocker les informations de type retournées par l'opérateur `typeid`.  
  
## Voir aussi  
 [Effectuer un cast](../cpp/casting.md)