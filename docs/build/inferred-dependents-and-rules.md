---
title: "R&#232;gles et d&#233;pendants inf&#233;r&#233;s | Microsoft Docs"
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
  - "dépendants, déduites"
  - "dépendants inférés dans NMAKE"
  - "règles inférées dans NMAKE"
  - "règles, déduites"
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# R&#232;gles et d&#233;pendants inf&#233;r&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE suppose un dépendant déduit pour une cible si une règle d'inférence applicable existe.  Une règle s'applique si :  
  
-   *toext* correspond à l'extension de la cible ;  
  
-   *fromext* correspond à l'extension d'un fichier qui porte le nom de base de la cible et qui existe dans le répertoire en cours ou spécifié ;  
  
-   *fromext* se trouve dans [.SUFFIXES](../build/dot-directives.md), aucune autre *fromext* dans une règle correspondante ne possède une priorité **.SUFFIXES** supérieure ;  
  
-   aucun dépendant explicite n'a une priorité **.SUFFIXES** supérieure.  
  
 Les dépendants déduits peuvent avoir des effets secondaires inattendus.  Si le bloc de description de la cible contient des commandes, NMAKE les exécute à la place des commandes de la règle.  
  
## Voir aussi  
 [Règles d'inférence](../build/inference-rules.md)