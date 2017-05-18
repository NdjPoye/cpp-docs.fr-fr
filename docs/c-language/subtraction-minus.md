---
title: Soustraction (-) | Microsoft Docs
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
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
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
ms.openlocfilehash: 78723d67f5938f8c8e4cfd299a18de39da9787ab
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="subtraction--"></a>Soustraction (-)
L’opérateur de soustraction (**-**) soustrait le second opérande du premier. Les deux opérandes peuvent être des types intégraux ou flottants, ou un opérande peut être un pointeur et l’autre un entier.  
  
 Lorsque deux pointeurs sont soustraits, la différence est convertie en une valeur intégrale signée en décomposant la différence par la taille d'une valeur du type que les pointeurs traitent. La taille de la valeur intégrale est définie par le type **ptrdiff_t** dans le fichier include STDDEF.H standard. Le résultat représente le nombre de positions de mémoire de ce type entre les deux adresses. Le résultat est forcément explicite pour deux éléments du même tableau, comme indiqué dans [Opérations arithmétiques sur les pointeurs](../c-language/pointer-arithmetic.md).  
  
 Lorsqu’une valeur entière est ensuite soustraite d’une valeur de pointeur, l’opérateur de soustraction convertit la valeur entière (*i*) en la multipliant par la taille de la valeur que le pointeur adresse. Après la conversion, la valeur entière représente les emplacements de mémoire *i*, où chaque position a une longueur spécifiée par le type pointeur. Lorsque la valeur entière convertie est ensuite soustraite de la valeur du pointeur, le résultat est les positions *i* de l’adresse mémoire avant l’adresse d’origine. Le nouveau pointeur pointe vers une valeur du type traité par la valeur de pointeur d'origine.  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs additifs C](../c-language/c-additive-operators.md)
