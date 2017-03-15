---
title: "Comment&#160;: convertir une boucle OpenMP qui a recours &#224; une variable de r&#233;duction pour utiliser le runtime d’acc&#232;s concurrentiel | Microsoft Docs"
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
  - "convertir d’OpenMP en runtime d’accès concurrentiel, variables de réduction"
  - "variables de réduction, convertir d’OpenMP en runtime d’accès concurrentiel"
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
caps.latest.revision: 13
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: convertir une boucle OpenMP qui a recours &#224; une variable de r&#233;duction pour utiliser le runtime d’acc&#232;s concurrentiel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment convertir une boucle [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) OpenMP qui utilise la clause [reduction](../../parallel/openmp/reference/reduction.md) pour utiliser le runtime d'accès concurrentiel.  
  
 La clause `reduction` OpenMP vous permet de spécifier une ou plusieurs variables de thread privé qui sont soumises à une opération de réduction à la fin de la zone parallèle.  OpenMP prédéfinit un ensemble d'opérateurs de réduction.  Chaque variable de réduction doit être une variable scalaire \(par exemple, `int`, `long` et `float`\).  OpenMP définit également plusieurs restrictions sur la façon dont les variables de réduction sont utilisées dans la région parallèle.  
  
 La bibliothèque de modèles parallèles \(PPL\) fournit la classe [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md), qui fournit un stockage local des threads réutilisable qui vous permet d'effectuer des calculs affinés, puis de fusionner ces calculs dans un résultat final.  La classe `combinable` est un modèle qui agit sur les types scalaires et les types complexes.  Pour utiliser la classe `combinable`, exécutez les sous\-calculs dans le corps d'un élément parallèle, puis appelez la méthode [concurrency::combinable::combine](../Topic/combinable::combine%20Method.md) ou [concurrency::combinable::combine\_each](../Topic/combinable::combine_each%20Method.md) pour produire le résultat final.  Les méthodes `combine` et `combine_each` prennent chacune une *fonction de combinaison* qui spécifie comment combiner chaque paire d'éléments.  Par conséquent, la classe `combinable` ne se limite pas à un ensemble fixe d'opérateurs de réduction.  
  
## Exemple  
 Cet exemple utilise OpenMP et le runtime d'accès concurrentiel pour calculer la somme des 35 premiers nombres de Fibonacci.  
  
 [!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/CPP/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **Utilisation de OpenMP…**  
**La somme des 35 premiers numéros de Fibonacci est 14930351.**  
**utilise le runtime d'accès concurrentiel...**  
**La somme des 35 premiers numéros de Fibonacci est 14930351.** Pour plus d'informations sur la classe `combinable`, consultez [Conteneurs et objets parallèles](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet `Visual Studio`, ou collez\-le dans un fichier nommé concrt\-omp\-fibonacci\-reduction.cpp. Exécutez ensuite la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-fibonacci\-reduction.cpp**  
  
## Voir aussi  
 [Migration d'OpenMP au runtime d'accès concurrentiel](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Conteneurs et objets parallèles](../../parallel/concrt/parallel-containers-and-objects.md)