---
title: "Dur&#233;e de vie | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "classe de stockage automatique"
  - "classe de stockage automatique, durée"
  - "allocation de mémoire dynamique"
  - "fonctions (C++), durée de vie"
  - "variables globales, durée de vie"
  - "durée de vie"
  - "variables locales, durée de vie"
  - "allocation de mémoire, dynamique"
  - "allocation de mémoire, allocation dynamique"
  - "spécificateurs de classe de stockage, durée du stockage"
  - "classes de stockage, durée de vie"
  - "durée du stockage"
  - "variables, automatique"
  - "variables, durée de vie"
ms.assetid: ff0b42cb-3f0f-49a3-a94f-d1d825d8ddfe
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Dur&#233;e de vie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La « durée de vie » est la période durant l'exécution d'un programme pendant laquelle une variable ou une fonction existe.  La durée de stockage de l'identificateur détermine sa durée de vie.  
  
 Un identificateur déclaré avec le *storage\-class\-specifier* **static** possède une durée de stockage statique.  Les identificateurs avec une durée de stockage statique \(également appelés identificateurs « globaux »\) ont un stockage et une valeur définie pendant toute la durée d'un programme.  Le stockage est réservé et la valeur stockée de l'identificateur est initialisée une seule fois, avant le démarrage du programme.  Un identificateur déclaré avec liaison externe ou interne a également une durée de stockage statique \(consultez [Liaison](../c-language/linkage.md)\).  
  
 Un identificateur déclaré sans spécificateur de classe de stockage **static** a une durée de stockage automatique s'il est déclaré dans une fonction.  Un identificateur avec une durée de stockage automatique \(un « identificateur local »\) a un stockage et une valeur définie uniquement dans le bloc où il est défini ou déclaré.  Un nouveau stockage est alloué à un identificateur automatique chaque fois que le programme accède à ce bloc, et il perd son stockage \(et sa valeur\) lorsque le programme quitte le bloc.  Les identificateurs déclarés dans une fonction sans liaison ont également une durée de stockage automatique.  
  
 Les règles suivantes spécifient si un identificateur a une durée de vie globale \(statique\) ou locale \(automatique\) :  
  
-   Toutes les fonctions ont une durée de vie statique.  Par conséquent, elles existent à tout moment pendant l'exécution du programme.  Les identificateurs déclarés au niveau externe \(autrement dit, en dehors de tous les blocs du programme au même niveau que les définitions de fonction\) ont toujours une durée de vie globale \(statique\).  
  
-   Si une variable locale a un initialiseur, elle est initialisée chaque fois qu'elle est créée \(sauf si elle est déclarée comme **static**\).  Les paramètres des fonctions ont également une durée de vie locale.  Vous pouvez spécifier une durée de vie globale pour un identificateur dans un bloc en incluant le spécificateur de classe de stockage **static** dans sa déclaration.  Une fois déclarée **static**, la variable conserve sa valeur d'une entrée du bloc à la suivante.  
  
 Bien qu'un identificateur à la durée de vie globale existe durant toute l'exécution du programme source \(c'est le cas par exemple d'une variable déclarée de manière externe ou d'une variable locale déclarée avec le mot clé **static** \), il peut ne pas être visible dans toutes les parties du programme.  Pour plus d'informations sur la visibilité, consultez [Portée et visibilité](../c-language/scope-and-visibility.md). Pour obtenir une discussion du non terminal *spécificateur\-classe\-stockage*, consultez [Classes de stockage](../c-language/c-storage-classes.md).  
  
 La mémoire peut être allouée en fonction des besoins \(de manière dynamique\) lorsqu'elle est créée par l'intermédiaire de routines de bibliothèque spéciales telles que `malloc`.  Comme l'allocation dynamique de la mémoire utilise des routines de bibliothèque, cela n'est pas considéré comme faisant partie du langage.  Consultez la fonction [malloc](../c-runtime-library/reference/malloc.md) dans la *Référence de la bibliothèque Runtime*.  
  
## Voir aussi  
 [Durée de vie, portée, visibilité et liaison](../c-language/lifetime-scope-visibility-and-linkage.md)