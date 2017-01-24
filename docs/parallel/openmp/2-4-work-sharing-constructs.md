---
title: "2.4 Work-sharing Constructs | Microsoft Docs"
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
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4 Work-sharing Constructs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un élément de partage du travail distribue l'exécution de l'instruction associée au sein de les membres de l'équipe qui la rencontrent.  Les directives de partage du travail ne lancent pas de nouveaux threads, et il n'existe aucun cloisonnement implicite sur l'entrée à un élément de partage du travail.  
  
 la séquence d'éléments de partage du travail et de directives de **cloisonnement** produits doit être la même pour chaque thread dans une équipe.  
  
 OpenMP définit les éléments suivants de partage du travail, et ceux\-ci sont décrits dans les sections qui suivent :  
  
-   directive de**pour**  
  
-   directive de**sections**  
  
-   directive d'**unique**