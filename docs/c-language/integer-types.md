---
title: "Types d’entier | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integer data type, integer types in C++
- integer constants
- integer types
- integers, types
ms.assetid: c8926a5e-0e98-4e37-9b05-ce97961379bd
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 7b03bfad7912aa74c5520f6dfc23f70856188f0e
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="integer-types"></a>Types d'entier
Chaque constante entière reçoit un type selon sa valeur et la façon dont elle est exprimée. Vous pouvez forcer une constante entière à être de type **long** en ajoutant la lettre **l** ou **L** à la fin de la constante ; vous pouvez la forcer à être de type `unsigned` en ajoutant **u** ou **U** à la valeur. La minuscule **l** peut être confondue avec le chiffre 1 et doit être évitée. Voici certaines formes de constantes entières **long** :  
  
```  
/* Long decimal constants */  
10L  
79L  
  
/* Long octal constants */  
012L  
0115L  
  
/* Long hexadecimal constants */  
0xaL or 0xAL  
0X4fL or 0x4FL  
  
/* Unsigned long decimal constant */  
776745UL  
778866LU  
```  
  
 Le type que vous assignez à une constante dépend de la valeur que cette constante représente. La valeur d'une constante doit être dans la plage de valeurs pouvant être représentées pour son type. Le type d’une constante détermine quelles conversions sont exécutées lorsque la constante est utilisée dans une expression ou lorsque le signe moins (**-**) est appliqué. La liste suivante résume les règles de conversion des constantes entières.  
  
-   Le type d’une constante décimale sans suffixe est `int`, **long int** ou **unsigned long int**. Le premier de ces trois types dans lesquels la valeur de la constante peut être représentée est le type assigné à la constante.  
  
-   Le type assigné à des constantes octales et hexadécimales sans suffixe est `int`, `unsigned int`, **long int** ou **unsigned long int**, selon la taille de la constante.  
  
-   Le type assigné aux constantes ayant pour suffixe **u** ou **U** est **unsigned int** ou **unsigned long int**, selon leur taille.  
  
-   Le type assigné aux constantes ayant pour suffixe **l** ou **L** est **long int** ou **unsigned long int**, selon leur taille.  
  
-   Le type assigné aux constantes ayant pour suffixe **u** ou **U** et **l** ou **L** est **unsigned long int**.  
  
## <a name="see-also"></a>Voir aussi  
 [Constantes entières C](../c-language/c-integer-constants.md)
