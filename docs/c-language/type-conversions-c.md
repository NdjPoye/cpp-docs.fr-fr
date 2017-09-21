---
title: Conversions de type (C) | Microsoft Docs
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
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b2d02ad9494bce2c1d9a0e94cd87c9327526e2f3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="type-conversions-c"></a>Conversions de type (C)
Les conversions de type dépendent de l’opérateur spécifié et du type de l’opérande ou des opérateurs. Les conversions de type sont effectuées dans les cas suivants :  
  
-   Lorsqu'une valeur d'un type est assignée à une variable d'un type différent ou qu'un opérateur convertit le type de son opérande ou de ses opérandes avant d'exécuter une opération  
  
-   Lorsqu'une valeur d'un type est explicitement convertie en un type différent  
  
-   Lorsqu'une valeur est passée comme argument à une fonction ou lorsqu'un type est retourné depuis une fonction  
  
 Un caractère, un entier court ou un champ de bits entier, tous signés ou non signés, ou un objet de type énumération, peuvent être utilisés dans une expression partout où un entier peut être utilisé. Si `int` peut représenter toutes les valeurs du type d'origine, la valeur est convertie en `int` ; sinon, elle est convertie en `unsigned int`. Ce processus porte le nom de « promotion d'un intégral ». Les promotions d'un intégral conservent la valeur. Autrement dit, vous pouvez être sûr que la valeur après la promotion est identique à celle précédant la promotion. Pour plus d'informations, consultez [Conversions arithmétiques ordinaires](../c-language/usual-arithmetic-conversions.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions et assignations](../c-language/expressions-and-assignments.md)