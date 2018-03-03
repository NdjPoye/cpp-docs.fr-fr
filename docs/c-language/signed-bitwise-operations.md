---
title: "Opérateurs de bits signés | Microsoft Docs"
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
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92750e2e309fd0ceaf06e81cc9483c0785795019
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="signed-bitwise-operations"></a>Opérateurs de bits signés
**ANSI 3.3** Résultats des opérations au niveau du bit sur les entiers signés  
  
 Les opérations au niveau du bit sur les entiers signés fonctionnent de la même façon que les opérations au niveau du bit sur les entiers non signés. Par exemple, les valeurs `-16 & 99` peuvent être exprimées au format binaire sous la forme  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Le résultat de l'opération de bits AND est 96.  
  
## <a name="see-also"></a>Voir aussi  
 [Entiers](../c-language/integers.md)