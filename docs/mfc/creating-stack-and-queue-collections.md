---
title: "Cr&#233;ation de collections de piles et de files d&#39;attente | Microsoft Docs"
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
  - "classes de collection, créer"
  - "collections, file d'attente"
  - "collections, pile"
  - "classes de collection MFC, file d'attente (collections)"
  - "classes de collection MFC, pile (collections)"
  - "file d'attente (collections)"
  - "pile"
  - "pile (collections)"
ms.assetid: 3c7bc198-35f0-4fc3-aaed-6005a0f22638
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation de collections de piles et de files d&#39;attente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment créer d'autres structures de données, telles que des [piles](#_core_stacks) et [files d'attente](#_core_queues), les classes de liste de MFC.  Les exemples utilisent des classes dérivées de `CList`, mais vous pouvez utiliser `CList` directement à moins que vous deviez ajouter des fonctionnalités.  
  
##  <a name="_core_stacks"></a> Piles  
 Étant donné que la collection de listes standard a un début et une fin, il est facile de créer une collection de listes dérivée qui reproduit le comportement d'une pile de type " dernier entré \- premier sortie ".  Une pile est similaire à un empilement de plateaux dans un cafétéria.  Lorsque les plateaux sont ajoutés à la pile, elles sont sur le dessus de la pile.  Le dernier plateau ajouté est le premier à être enlevé.  Les méthodes `AddHead` et `RemoveHead` de collection de listes peuvent être utilisées pour ajouter et supprimer des éléments spécifiquement de la tête de la liste ; ainsi, l'élément le plus récemment ajouté est le premier à être supprimé.  
  
#### Pour créer une collection de piles  
  
1.  Dérivez une nouvelle classe de liste de l'une des classes existantes de la liste de MFC et ajoutez des méthodes pour prendre en charge les fonctionnalités des opérations de pile.  
  
     L'exemple suivant montre comment ajouter des méthodes pour empiler des éléments, jeter un coup d'œil sur l'élément supérieur de la pile, et dépiler l'élément supérieur de la pile :  
  
     [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/CPP/creating-stack-and-queue-collections_1.h)]  
  
 Notez que cette approche présente la classe sous\-jacente `CObList`.  L'utilisateur peut appeler toute méthode de `CObList`, que ce soit logique pour une pile ou non.  
  
##  <a name="_core_queues"></a> Files d'attente  
 Étant donné que la collection de listes standard a un début et une fin, il est facile de créer une collection de listes dérivée qui reproduit le comportement d'une file de type "premier entré\-premier sorti".  Une file est similaire à une ligne de personnes dans une cafétéria.  La première personne dans la file de est la première à être servie.  Lorsque plusieurs personnes viennent, elles arrivent à la fin de la file pour attendre leur tour.  Les méthodes `AddTail` et `RemoveHead` des collections de listes peuvent être utilisées pour ajouter et supprimer des éléments spécifiquement de la tête ou de la queue de la liste ; ainsi, l'élément le plus récemment ajouté est toujours le dernier à être supprimé.  
  
#### Pour créer une file  
  
1.  Dérivez une classe de liste de l'une des classes de liste prédéfinie fournies dans la bibliothèque MFC et ajoutez des méthodes pour prendre en charge la sémantique des opérations de file.  
  
     L'exemple suivant montre comment ajouter des méthodes pour ajouter un élément à la fin de la file et obtenir l'élément situé au début de la file.  
  
     [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/CPP/creating-stack-and-queue-collections_2.h)]  
  
## Voir aussi  
 [Collections](../mfc/collections.md)