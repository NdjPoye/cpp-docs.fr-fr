---
title: "Utilisation de plusieurs jeux de r&#233;sultats &#224; partir d&#39;une seule proc&#233;dure stock&#233;e | Microsoft Docs"
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
  - "jeux de résultats multiples"
  - "procédures stockées, retourner des jeux de résultats"
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation de plusieurs jeux de r&#233;sultats &#224; partir d&#39;une seule proc&#233;dure stock&#233;e
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La plupart des procédures stockées retournent plusieurs jeux de résultats.  Les procédures stockées de ce type englobent généralement une ou plusieurs instructions Select.  Le consommateur doit tenir compte de ce point pour gérer tous les jeux de résultats.  
  
### Pour gérer plusieurs jeux de résultats  
  
1.  Créez une classe `CCommand` à l'aide de `CMultipleResults` comme argument de modèle et avec l'accesseur de votre choix.  Généralement, il s'agit d'un accesseur dynamique ou manuel.  Si vous utilisez un autre type d'accesseur, vous ne pourrez peut\-être pas déterminer les colonnes de sortie pour chaque jeu de ligne.  
  
2.  Exécutez la procédure stockée selon la méthode habituelle et liez les colonnes \(consultez [Comment extraire des données ?](../../data/oledb/fetching-data.md)\).  
  
3.  Utilisez les données.  
  
4.  Appelez `GetNextResult` sur la classe `CCommand`.  Si un autre jeu de lignes de résultats est disponible, `GetNextResult` retourne S\_OK et vous devez lier de nouveau les colonnes si vous utilisez un accesseur manuel.  Si `GetNextResult` retourne une erreur, plus aucun jeu de résultats n'est disponible.  
  
## Voir aussi  
 [Utilisation des procédures stockées](../../data/oledb/using-stored-procedures.md)