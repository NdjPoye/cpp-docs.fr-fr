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
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8333b761aa51de44c8225e5ace97885eaaed56da
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

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
