---
title: "Conversions d’assignation | Microsoft Docs"
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
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
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
ms.openlocfilehash: 44b9b5ede24d3b6e44813de46e7507f5d943a78f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="assignment-conversions"></a>Conversions d'assignation
Dans les opérations d'assignation, le type de la valeur assignée est converti en type de la variable qui reçoit l'assignation. C permet des conversions par assignation entre les types intégraux et les types flottants, même si les informations sont perdues lors de la conversion. La méthode de conversion utilisée dépend des types impliqués dans l'assignation, comme décrit dans [Conversions arithmétiques courantes](../c-language/usual-arithmetic-conversions.md) et dans les sections suivantes :  
  
-   [Conversions depuis les types intégraux signés](../c-language/conversions-from-signed-integral-types.md)  
  
-   [Conversions depuis les types intégraux non signés](../c-language/conversions-from-unsigned-integral-types.md)  
  
-   [Conversions depuis les types à virgule flottante](../c-language/conversions-from-floating-point-types.md)  
  
-   [Conversions vers et depuis les types pointeur](../c-language/conversions-to-and-from-pointer-types.md)  
  
-   [Conversions depuis les autres types](../c-language/conversions-from-other-types.md)  
  
 Les qualificateurs de type n'affectent pas l'admissibilité de la conversion bien qu'il ne soit pas possible d'utiliser une l-value **const** à gauche de l'assignation.  
  
## <a name="see-also"></a>Voir aussi  
 [Conversions de type](../c-language/type-conversions-c.md)
