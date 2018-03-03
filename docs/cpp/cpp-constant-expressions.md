---
title: Expressions constantes C++ | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0cd30dd51b3d87b7d82b917734d187ae2278837a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c-constant-expressions"></a>Expressions constantes C++
A *constante* valeur est une tâche qui ne change pas. C++ fournit deux mots clés qui vous permettent d'exprimer l'intention qu'un objet n'est pas destiné à être modifié, et d'appliquer cette intention.  
  
 C++ requiert des expressions constantes (expressions qui ont pour valeur une constante) pour les déclarations des éléments suivants :  
  
-   Limites d'index de tableau  
  
-   Sélecteurs dans les instructions case  
  
-   Spécification de longueur de champ de bits  
  
-   Initialiseurs d'énumération  
  
 Les seuls opérandes autorisés dans les expressions constantes sont :  
  
-   Littéraux  
  
-   Constantes d'énumération  
  
-   Valeurs déclarées comme const qui sont initialisées avec des expressions constantes  
  
-   Expressions `sizeof`  
  
 Les constantes non intégrales doivent être converties (explicitement ou implicitement) en types intégraux pour être autorisées dans une expression constante. Par conséquent, le code suivant est conforme :  
  
```  
const double Size = 11.0;  
char chArray[(int)Size];  
```  
  
 Les conversions explicites en types intégraux sont autorisées dans les expressions constantes ; tous les autres types et types dérivés ne sont pas autorisés, sauf quand ils sont utilisés en tant qu'opérandes par rapport à l'opérateur `sizeof`.  
  
 L'opérateur virgule et les opérateurs d'assignation de virgule ne peuvent pas être utilisés dans les expressions constantes.  
  
## <a name="see-also"></a>Voir aussi  
 [Types d’expressions](../cpp/types-of-expressions.md)