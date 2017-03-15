---
title: "Fichiers et flux | Microsoft Docs"
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
  - "fichiers (C++)"
  - "flux"
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Fichiers et flux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un programme communique avec l'environnement cible en écrivant et lisant des fichiers.  Un fichier peut etre:  
  
-   Un jeu de données que vous pouvez lire et écrire à plusieurs reprises.  
  
-   Un flux d'octets générés par un programme \(tel qu'un pipeline\).  
  
-   Un flux d'octets reçus ou envoyé par un periphérique.  
  
 Les deux derniers éléments sont des fichiers interactifs.  Les fichiers sont généralement les principaux moyens par lesquels interagir avec un programme.  Vous manipulez tous les types de fichiers à peu près de la même manière\_en appelant des bibliothèques de fonctions.  Vous incluez l'en\-tête standard STDIO.H pour déclarer la plupart de ces fonctions.  
  
 Avant de pouvoir exécuter plusieurs des opérations sur un fichier, le fichier doit être ouvert.  L'ouverture d'un fichier l'associe à un flux de données, une structure de données dans la bibliothèque dstandard C, qui glisses sur de nombreuses différences entre les fichiers de différents types.  La bibliothèque contient l'état de chaque flux de données dans un objet de type FILE.  
  
 L'environnement cible ouvre trois fichiers avant le démarrage du programme.  Vous pouvez ouvrir un fichier en appelant la bibliothèque de fonctions [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md) avec deux arguments. \(La fonction `fopen` a été déconseillée, utilisez [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) à la place.\) Le premier argument est un nom de fichier.  Le deuxième argument est une chaîne C, qui indique:  
  
-   Si vous avez l'intention de lire des données à partir du fichiers ou d'y écrire des données ou les deux.  
  
-   Si vous envisagez de générer de nouveaux contenus pour le fichier \(ou de créer un fichier s'il n'existait pas précédemment\) ou de laisser le contenu existant en place.  
  
-   Ecrire dans un fichier peut soit modifier le contenu existant ou devrait seulement ajouter des octets à la fin du fichier.  
  
-   Si vous voulez manipuler un flux de texte ou un flux binaire.  
  
 Une fois que le fichier a été ouvert, vous pouvez déterminer si le flux est orienté octet \(un flux d'octets\) ou large orienté \(un flux de données larges\).  Un flux de données est initialement indépendant.  Appeler certaines fonctions pour traiter le flux de données le rend orienté octets, alors que d'autres le rende orienté large.  Une fois la connexion établie, un flux de données maintient son orientation jusqu'à ce qu'il soit fermé par un appel à [fclose](../c-runtime-library/reference/fclose-fcloseall.md) ou à [freopen](../c-runtime-library/reference/freopen-wfreopen.md).  
  
 © 1989\-2001 par P.J.  Plauger et JIM Brodie.  Tous droits réservés.  
  
## Voir aussi  
 [Flux texte et binaires](../c-runtime-library/text-and-binary-streams.md)   
 [Flux d'octets et flux larges](../c-runtime-library/byte-and-wide-streams.md)   
 [Contrôle des flux](../c-runtime-library/controlling-streams.md)   
 [États de flux](../c-runtime-library/stream-states.md)