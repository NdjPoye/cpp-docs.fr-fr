---
title: "Expressions constantes C | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e7b9beac4d87e0580279190cca005fc56c951af8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="c-constant-expressions"></a>Expressions constantes C
Une expression constante est évaluée au moment de la compilation, et non au moment de l'exécution, et elle peut être utilisée partout où une constante peut être utilisée. L'expression constante doit être évaluée en une constante qui est comprise dans la plage des valeurs représentables pour ce type. Les opérandes d'une expression constante peuvent être des constantes entières, des constantes caractère, des constantes à virgule flottante, des constantes d'énumération, des casts de type, des expressions `sizeof` et d'autres expressions constantes.  
  
## <a name="syntax"></a>Syntaxe  
 *constant-expression* :  
 *conditional-expression*  
  
 *conditional-expression* :  
 *logical-OR-expression*  
  
 *logical-OR-expression* **?**  *expression* **:**  *conditional-expression*  
  
 *expression* :  
 *assignment-expression*  
  
 *expression* **,**  *assignment-expression*  
  
 *assignment-expression* :  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator* : un des éléments suivants :  
 **= \*= /= %= += -= <\<= >>= &= ^= &#124;=**  
  
 Les éléments non terminaux pour les déclarateurs de struct, l’énumérateur, le déclarateur direct, le déclarateur direct-abstract et l’instruction étiquetée contiennent l’élément non terminal *constant-expression*.  
  
 Une expression constante intégrale doit être utilisée pour spécifier la taille d’un membre champ de bits d’une structure, la valeur d’une constante d’énumération, la taille d’un tableau ou la valeur d’une constante **case**.  
  
 Les expressions constantes utilisées dans les directives de préprocesseur sont soumises à des restrictions supplémentaires. Par conséquent, elles portent le nom d'« expressions constantes restreintes ». Une expression constante restreinte ne peut pas contenir d'expression `sizeof`, de constantes d'énumération, de casts de type en tout type, ni de constantes de type flottant. Elle peut toutefois contenir l’expression constante spéciale `defined (`*identifier*`)`.  
  
## <a name="see-also"></a>Voir aussi  
 [Opérandes et expressions](../c-language/operands-and-expressions.md)