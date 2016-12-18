---
title: "1.2 Definition of Terms | Microsoft Docs"
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
ms.assetid: fcaa8eb8-bbbf-4a24-ad0e-e299c442db79
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1.2 Definition of Terms
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les termes suivants sont utilisés dans le document :  
  
 cloisonnement  
 Un point de synchronisation qui doit être atteint par tous les threads dans une équipe.  Chaque thread attend que tous les threads de l'équipe arrivent à ce stade.  Il existe des barrières explicites identifiés par des directives et les cloisonnements implicites créés par l'implémentation.  
  
 élément  
 un élément est une instruction.  il se compose d'une directive et du bloc structuré suivant.  Notez que certaines directives ne sont pas partie d'un élément.  \(Voir *l'openmp\-directive* dans [annexe C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)\).  
  
 directive  
 Le c ou C\+\+ **\#pragma** suivi par l'identificateur d' **omp** , définissez le texte, et une nouvelle ligne.  La directive spécifie le comportement du programme.  
  
 étendue dynamique  
 Toutes les instructions de *l'étendue lexicale*, ainsi que toute instruction à l'intérieur d'une fonction qui est exécutée à la suite de l'exécution des instructions dans l'étendue lexicale.  Une étendue dynamique est également appelée *d'une zone*.  
  
 étendue lexicale  
 Instructions lexicale contenues dans *un bloc structuré*.  
  
 thread principal  
 Le thread qui crée une équipe lorsqu' *une région parallèle* est entrée.  
  
 région parallèle  
 Instructions qui les lient à un élément de parallèle OpenMP et peuvent être exécutées par plusieurs threads.  
  
 private  
 Noms de variables privés un bloc de stockage qui est unique au thread qui effectue la référence.  Notez qu'il existe plusieurs façons de spécifier une variable est privée : une définition dans une région parallèle, une directive de **threadprivate** , un **privé**, **firstprivate**, **elle**, ou clause de **réduction** , ou à l'aide de la variable comme variable de contrôle de boucle de **pour**dans une boucle de **pour** immédiatement après une directive de **pour** ou de **parallèle pour** .  
  
 zone  
 Une étendue dynamique.  
  
 zone série  
 Instructions exécutées uniquement par *le thread principal* en dehors de l'étendue dynamique d'une *région parallèle*.  
  
 sérialisez  
 Pour exécuter un élément parallèle avec une équipe de thread se compose uniquement d'un thread unique \(qui est le thread principal pour cet élément parallèle\), avec la commande série d'exécution pour les instructions dans le bloc structurée \(le même ordre que si le bloc n'étaient pas partie d'un élément parallèle\), et sans aucun effet sur la valeur retournée par **omp\_in\_parallel \(\)** \(en dehors de les effets de tous les éléments parallèles imbriqués\).  
  
 shared \(partagé\)  
 Noms de variables partagés multiples d'un bloc de stockage.  Tous les threads dans une équipe qui accèdent à cette variable accèdent à ce bloc unique de stockage.  
  
 bloc structuré  
 Un bloc structurée est une instruction \(unique ou composée\) que a une entrée unique et une sortie unique.  Aucune instruction n'est un bloc structuré s'il existe un saut dans ou hors de cette instruction \(appel y compris à **longjmp**\(3C\) ou l'utilisation de **throw**, mais un appel à **sortie** est autorisé\).  Une instruction composée est un bloc structuré si son exécution commence toujours à l'adresse **{** ouvrant et se termine toujours à l'adresse **}**fermante.  Une instruction d'expression, l'instruction de sélection, l'instruction d'itération, ou le bloc de **test** est un bloc structuré si l'instruction composée correspondante obtenues par l'englobant dans **{** et **}**serait un bloc structuré.  une instruction de saut, étiquetée instruction, ou instruction de déclaration n'est pas un bloc structuré.  
  
 équipe  
 Un ou plusieurs threads coopérant à l'exécution d'un élément.  
  
 thread  
 une entité d'exécution ayant un ordre d'exécution série, un ensemble de variables privées, et accès aux variables partagées.  
  
 variable  
 Un identificateur, éventuellement qualifié par les noms d'espaces de noms, qui désigne un objet.