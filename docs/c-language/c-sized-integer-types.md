---
title: "Types d&#39;entier dimensionn&#233; C | Microsoft Docs"
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
  - "types d'entier dimensionné"
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Types d&#39;entier dimensionn&#233; C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Microsoft C prend en charge les types d'entiers dimensionnés.  Vous pouvez déclarer des variables de type entier à 8, 16, 32 ou 64 bits, à l'aide du spécificateur de type \_\_int*n*, où *n* est la taille, en bits, de la variable de type entier.  La valeur de *n* peut être 8, 16, 32 ou 64.  L'exemple suivant déclare une variable de chacun des quatre types d'entiers dimensionnés :  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Les trois premiers types d'entiers dimensionnés sont des synonymes des types ANSI de la même taille, et permettent d'écrire du code portable qui se comporte de façon identique entre plusieurs plateformes.  Notez que le type de données \_\_int8 est synonyme du type char, que \_\_int16 est synonyme du type short et que \_\_int32 est synonyme du type int.  Le type \_\_int64 n'a pas d'équivalent ANSI.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Stockage de types de base](../c-language/storage-of-basic-types.md)