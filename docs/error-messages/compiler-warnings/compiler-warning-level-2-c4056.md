---
title: Compilateur avertissement (niveau 2) C4056 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4056
dev_langs:
- C++
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf5a5855d0b4291105826679e2ae81ed6d69e5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4056"></a>Compilateur avertissement (niveau 2) C4056
dépassement de capacité dans les calculs en virgule flottante constant  
  
 Opération arithmétique de constante à virgule flottante génère un résultat qui dépasse la valeur maximale autorisée.  
  
 Cet avertissement peut être dû à des optimisations du compilateur effectuées pendant une opération arithmétique de constante. Vous pouvez ignorer cet avertissement s’il disparaît lorsque vous désactivez l’optimisation ([/Od](../../build/reference/od-disable-debug.md)).  
  
 L’exemple suivant génère l’erreur C4056 :  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```