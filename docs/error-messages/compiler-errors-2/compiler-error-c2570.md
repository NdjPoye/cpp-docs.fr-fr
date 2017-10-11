---
title: Erreur du compilateur C2570 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2570
dev_langs:
- C++
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6b5d53463e889504f202b7d50b8c5ac877f27cf8
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2570"></a>Erreur du compilateur C2570
'identificateur' : union ne peut pas avoir de classes de base  
  
 Une union dérive d’une classe, structure ou union. Cela n'est pas autorisé. Déclarez le type dérivé en tant que classe ou structure à la place.  
  
 L’exemple suivant génère l’erreur C2570 :  
  
```  
// C2570.cpp  
// compile with: /c  
class base {};  
union hasPubBase : public base {};   // C2570  
union hasNoBase {};   // OK  
```
