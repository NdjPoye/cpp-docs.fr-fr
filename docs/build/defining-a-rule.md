---
title: "D&#233;finition d&#39;une r&#232;gle | Microsoft Docs"
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
  - "définir des règles d'inférence"
  - "programme NMAKE, règles d'inférence"
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;finition d&#39;une r&#232;gle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'option *fromext* représente l'extension d'un fichier dépendant, et *toext* l'extension d'un fichier cible.  
  
```  
.fromext.toext:  
   commands  
```  
  
## Notes  
 Les extensions ne respectent pas la casse.  Les macros peuvent être appelées pour représenter *fromext* et *toext* ; l'expansion des macros intervient lors du prétraitement.  Le point \(.\) qui précède *fromext* doit apparaître en début de ligne.  Le signe deux\-points \(:\) est précédé par aucun ou plusieurs espaces ou tabulations.  Il ne peut être suivi que par des espaces ou des tabulations, un point\-virgule \(;\) pour spécifier une commande, un signe dièse \(\#\) pour indiquer un commentaire ou un caractère de saut de ligne.  Aucun autre espace n'est admis.  Les commandes sont définies comme dans les blocs de description.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 [Chemins de recherche utilisés dans les règles](../build/search-paths-in-rules.md)  
  
## Voir aussi  
 [Règles d'inférence](../build/inference-rules.md)