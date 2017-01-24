---
title: "Classes de mod&#232;le pour les tableaux, listes et tables | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.template"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), classes"
  - "classes de liste"
  - "map (classes)"
  - "classes de modèle"
  - "classes de modèle, pour les tableaux/listes et tables"
ms.assetid: a8331c4b-068a-48f8-a629-b8449601e121
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de mod&#232;le pour les tableaux, listes et tables
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces classes de collection sont des modèles dont les paramètres déterminent les types des objets stockés dans les agrégats.  `CArray`, `CMap`, et les classes `CList` utilisent les fonctions d'assistance globales qui doivent généralement être personnalisées.  Pour plus d'informations sur ces fonctions d'assistance, consultez [Assistance de classe de collection](../mfc/reference/collection-class-helpers.md).  Les classes de pointeur typé sont des wrappers pour les autres classes dans la bibliothèque de classes.  En utilisant ces wrappers, vous inscrivez le contrôle de type du compilateur pour vous aider à éviter des erreurs.  Pour plus d'informations sur l'utilisation de ces classes, consultez [Collections](../mfc/collections.md).  
  
 Ces classes sont des modèles que vous pouvez utiliser pour créer des tableaux, des listes, des maps de n'importe quel type vous souhaitez.  
  
 [CArray](../mfc/reference/carray-class.md)  
 Classe du modèle pour effectuer des tableaux de types arbitraires.  
  
 [CList](../mfc/reference/clist-class.md)  
 Classe du modèle pour effectuer des listes de types arbitraires.  
  
 [CMap](../mfc/reference/cmap-class.md)  
 Classe du modèle pour effectuer des cartes avec la clé arbitraire et les types de valeur.  
  
 [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md)  
 Classe du modèle pour les tables de type sécurisé de pointeurs.  
  
 [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md)  
 Classe du modèle pour les listes de type sécurisé de pointeurs.  
  
 [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md)  
 Classe du modèle pour les cartes de type sécurisé avec des pointeurs.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)