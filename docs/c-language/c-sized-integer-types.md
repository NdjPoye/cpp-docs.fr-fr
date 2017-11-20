---
title: "Types d’entier dimensionnés C | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 101c8facb8871d814d1a1ea05c2856d3105a8bfc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="c-sized-integer-types"></a>Types d'entier dimensionné C
**Section spécifique à Microsoft**  
  
 Microsoft C prend en charge les types d’entiers dimensionnés. Vous pouvez déclarer des variables de type entier à 8, 16, 32 ou 64 bits, à l'aide du spécificateur de type __int*n*, où *n* est la taille, en bits, de la variable de type entier. La valeur de *n* peut être 8, 16, 32 ou 64. L'exemple suivant déclare une variable de chacun des quatre types d'entiers dimensionnés :  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Les trois premiers types d'entiers dimensionnés sont des synonymes des types ANSI de la même taille, et permettent d'écrire du code portable qui se comporte de façon identique entre plusieurs plateformes. Notez que le type de données __int8 est synonyme du type char, que \__int16 est synonyme du type short et que \__int32 est synonyme du type int. Le type \__int64 n'a pas d'équivalent ANSI.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Stockage de types de base](../c-language/storage-of-basic-types.md)