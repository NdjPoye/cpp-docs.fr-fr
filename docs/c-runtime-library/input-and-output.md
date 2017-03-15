---
title: "Entr&#233;es et sorties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "E/S (CRT)"
  - "E/S (CRT), routines"
  - "routines E/S"
  - "routines des entrées"
  - "routines des sorties"
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Entr&#233;es et sorties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les E\/S s'exécute des données en lecture et en écriture vers et à partir de fichiers et les périphériques.  Les opérations d'E\/S de fichier se situent dans le mode texte ou en mode binaire.  La bibliothèque Runtime\) de Microsoft propose trois types de fonctions d'E\/S :  
  
-   données de traiter des fonctions d'[E\/S de flux de données](../c-runtime-library/stream-i-o.md) en tant que flux de données d'autres caractères.  
  
-   Les fonctions [Low\-level I\/O](../c-runtime-library/low-level-i-o.md) appellent le système d'exploitation directement à l'opération de niveau inférieur à celui fourni par les entrées\/sorties \(E\/S\) de flux de données.  
  
-   [E\/S de la console et de port](../c-runtime-library/console-and-port-i-o.md) fonctions lire ou écrire directement à une console \(clavier et écran\) ou un port d'E\/S \(tel qu'un port imprimante\).  
  
    > [!NOTE]
    >  Les fonctionnalités du flux de données sont mises en mémoire tampon et les fonctions de bas niveau ne sont pas, ces deux types de fonctions sont généralement incompatibles.  Pour traiter un fichier spécifique, utilisez le flux ou le bas niveau s'exécute exclusivement.  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)