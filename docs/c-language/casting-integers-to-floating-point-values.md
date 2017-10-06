---
title: "Cast de nombres entiers en nombres à virgule flottante | Microsoft Docs"
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
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 5635ddf0e940e1f374bfd97d7d6f53dc1b57daec
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="casting-integers-to-floating-point-values"></a>Cast d'entiers en valeurs à virgule flottante
**ANSI 3.2.1.3** Direction de la troncation lorsqu'un nombre intégral est converti en nombre à virgule flottante qui ne peut pas représenter exactement la valeur d'origine  
  
 Lorsqu'un nombre intégral est casté en une valeur à virgule flottante qui ne peut pas représenter exactement la valeur, la valeur est arrondie à la valeur appropriée (inférieure ou supérieure) la plus proche.  
  
 Par exemple, effectuer un cast d'un type **long non signé** (avec 32 bits de précision) en type **flottant** (dont la précision de la mantisse est 23 bits) arrondit le nombre au multiple de 256 le plus proche. Toutes les valeurs **long** 4,294,966,913 à 4,294,967,167 sont arrondies à la valeur **flottante** 4,294,967,040.  
  
## <a name="see-also"></a>Voir aussi  
 [Mathématiques à virgule flottante](../c-language/floating-point-math.md)
