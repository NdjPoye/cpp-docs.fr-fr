---
title: "1.3 Execution Model | Microsoft Docs"
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
ms.assetid: 85ae8bc4-5bf0-45e0-a45f-02de9adaf716
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1.3 Execution Model
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP utilise le modèle bifurcation\-jointure de l'exécution parallèle.  Bien que ce modèle bifurcation\-jointure puisse être utile pour résoudre de nombreux problèmes, il est quelque peu appropriée pour les grandes applications basées sur les tableaux.  OpenMP est destiné aux programmes de prise en charge qui effectueront correctement les deux lorsque les programmes parallèles \(plusieurs threads d'exécution et un OpenMP complet prennent en charge la bibliothèque\) et en tant que programmes séquentiels \(les directives ignorées et un OpenMP simple choisit une bibliothèque\).  Toutefois, il est possible et laissé de développer un programme qui ne se comporte pas correctement lorsqu'il est exécuté séquentiellement.  En outre, les différents degrés de parallélisme peuvent entraîner des résultats numériques à cause de modifications de l'association des opérations numériques.  Par exemple, une réduction d'addition série peut avoir un modèle différent des associations d'addition qu'une réduction parallèle.  ces différentes associations peuvent modifier les résultats de l'ajout à virgule flottante.  
  
 Un programme écrit avec l'API d'OpenMP C\/C\+\+ commence l'exécution qu'un seul thread d'exécution a appelé *le thread principal*.  Le principal thread s'exécute dans une région série jusqu'à ce que le premier élément parallèle est produit.  dans l'API d'OpenMP C\/C\+\+, la directive de **parallèle** constitue un élément parallèle.  Lorsqu'un élément parallèle est produit, le thread principal crée une équipe de thread, et la page maître devient forme de base de l'équipe.  Chaque thread dans l'équipe exécute les instructions dans l'étendue dynamique d'une région parallèle, à l'exception de les éléments de partage du travail.  Les éléments de partage du travail doivent être produits par tous les threads de l'équipe dans le même ordre, et les instructions dans le bloc de type associé exécutent un ou plusieurs threads.  Le cloisonnement implicite à la fin d'un élément de partage du travail sans clause d' `nowait` est exécuté par tous les threads de l'équipe.  
  
 Si un thread modifie un objet partagé, il affecte non seulement son propre environnement d'exécution, mais également ceux des autres threads du programme.  La modification est garantie être terminée, du point de vue de l'un des autres threads, au point de séquence suivant \(défini dans la langue de base\) uniquement si l'objet est déclarée comme étant volatiles.  Sinon, la modification est garantie être terminée après d'abord le thread modifiant, puis \(ou simultané\) les autres threads, rencontrent une directive de **vide** qui spécifie l'objet \(implicitement ou explicitement\).  Notez que lorsque les directives de **vide** qui sont implicites par d'autres directives d'OpenMP ne sont pas suffisantes pour garantir l'ordre souhaité des effets secondaires, il revient au programmeur de fournir des directives supplémentaires et explicites de **vide** .  
  
 Au terme de l'élément parallèle, les threads dans l'équipe synchronisent à un cloisonnement implicite, et uniquement le principal thread reprend l'exécution.  un certain nombre d'éléments parallèles peuvent être spécifiés dans un programme unique.  Par conséquent, un programme peut répliquer et joindre plusieurs fois pendant l'exécution.  
  
 L'API d'OpenMP C\/C\+\+ permet aux programmeurs aux directives d'utilisation dans les fonctions appelées des éléments parallèles.  Les directives qui n'apparaissent pas dans l'étendue lexicale d'un élément parallèle mais peuvent se situer dans l'étendue dynamique sont appelées des directives *orphelines* .  Les directives orphelines offrent aux programmeurs la possibilité d'exécuter les parties importantes de leur programme en parallèle uniquement aux modifications minimes dans le programme séquentiel.  Avec cette fonctionnalité, les utilisateurs peuvent écrire du code pour les éléments parallèles à des niveaux supérieurs de l'arborescence des appels du programme et utiliser des directives pour contrôler l'exécution dans les fonctions appelées l'une d'elles.  
  
 Les appels non synchronisés aux fonctions de sortie C et C\+\+ qui écrivent dans le même fichier peuvent générer une sortie dans laquelle les données entrées par différents threads s'affiche dans un ordre non déterministe.  De même, les appels désynchronisés aux fonctions d'entrée qui les lisent à partir de le même fichier peuvent lire des données dans un ordre non déterministe.  L'utilisation n'est pas synchronisée d'E\/S, telle que chaque thread accède à un fichier différent, produit les mêmes résultats que l'exécution série d'E\/S s'exécute.