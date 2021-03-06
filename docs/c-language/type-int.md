---
title: Type int | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ed3fcd9b11a76f8ff211bf8be5cf50ee6664cda
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="type-int"></a>Type int
La taille d'un élément `int` signé ou non signé est la taille standard d'un entier sur un ordinateur particulier. Par exemple, dans les systèmes d'exploitation 16 bits, le type `int` inclut habituellement 16 bits, ou 2 octets. Dans les systèmes d'exploitation 32 bits, le type `int` inclut habituellement 32 bits, ou 4 octets. Ainsi, le type `int` équivaut au type `short int` ou **long int**, et le type `unsigned int` équivaut au type **unsigned short** ou `unsigned long`, selon l'environnement cible. Les types `int` représentent tous des valeurs signées, sauf indication contraire.  
  
 Les spécificateurs de type `int` et `unsigned int` (ou simplement `unsigned`) définissent certaines fonctionnalités du langage C (par exemple, le type `enum`). Dans ces cas, les définitions des types `int` et unsigned int pour une implémentation particulière déterminent le stockage réel.  
  
 **Section spécifique à Microsoft**  
  
 Les entiers signés sont représentés sous la forme d'un complément à deux. Le bit le plus significatif indique le signe : 1 pour les nombres négatifs, 0 pour les nombres positifs et zéro. La plage de valeurs est fournie dans les [Limites d’entier C++](../c-language/cpp-integer-limits.md), qui proviennent du fichier d'en-tête LIMITS.H.  
  
 **FIN de la section spécifique à Microsoft**  
  
> [!NOTE]
>  Les spécificateurs de type int et unsigned int sont couramment utilisés dans les programmes C car ils permettent à un ordinateur particulier de traiter les valeurs entières de la façon la plus efficace possible pour cet ordinateur. Toutefois, puisque les tailles des types int et unsigned int varient, les programmes qui dépendent d'une taille d'entier spécifique peuvent ne pas être transposables à d'autres ordinateurs. Pour améliorer la portabilité des programmes, vous pouvez utiliser des expressions avec l'opérateur sizeof (comme indiqué dans [Opérateur sizeof](../c-language/sizeof-operator-c.md)) au lieu de tailles de données codées en dur.  
  
## <a name="see-also"></a>Voir aussi  
 [Stockage de types de base](../c-language/storage-of-basic-types.md)