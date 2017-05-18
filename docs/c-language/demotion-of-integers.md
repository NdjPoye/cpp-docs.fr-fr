---
title: "Rétrogradation des entiers | Microsoft Docs"
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
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
caps.latest.revision: 6
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
ms.openlocfilehash: 468b88ccb64c06e64e9b234188295b3fcc148b1f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="demotion-of-integers"></a>Rétrogradation des entiers
**ANSI 3.2.1.2** Le résultat de la conversion d’un entier en un entier signé plus court, ou le résultat de la conversion d’un entier non signé en entier signé de longueur égale si la valeur ne peut pas être représentée  
  
 Lorsqu’un entier **long** est casté en un **short** ou qu’un **short** est casté en un `char`, les octets moins significatifs sont conservés.  
  
 Par exemple, cette ligne  
  
```  
short x = (short)0x12345678L;  
```  
  
 assigne la valeur 0x5678 à `x`, et cette ligne  
  
```  
char y = (char)0x1234;  
```  
  
 assigne la valeur 0x34 à `y`.  
  
 Lorsque des variables signées sont converties en variables non signées et vice versa, les modèles binaires restent les mêmes. Par exemple, le cast de -2 (0xFE) en une valeur non signée produit 254 (également 0xFE).  
  
## <a name="see-also"></a>Voir aussi  
 [Entiers](../c-language/integers.md)
