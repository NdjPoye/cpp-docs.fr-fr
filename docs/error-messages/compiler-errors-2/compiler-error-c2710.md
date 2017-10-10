---
title: Erreur du compilateur C2710 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2710
dev_langs:
- C++
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5bb6349bf6efb8c63b68c78644343ace5dc07e67
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2710"></a>Erreur du compilateur C2710
'construct' : '__declspec (modifier)' peut uniquement être appliqué à une fonction qui retourne un pointeur  
  
 Une fonction dont la valeur de retournée est un pointeur est la seule construction à laquelle `modifier` peuvent être appliquées.  
  
 L’exemple suivant génère l’erreur C2710 :  
  
```  
// C2710.cpp  
__declspec(restrict) void f();   // C2710  
// try the following line instead  
__declspec(restrict) int * g();  
```
