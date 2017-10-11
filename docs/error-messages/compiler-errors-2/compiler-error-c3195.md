---
title: Erreur du compilateur C3195 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3195
dev_langs:
- C++
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e6e95ce1592c98fae59869e0153ee27c0f727397
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3195"></a>Erreur du compilateur C3195
'operator' : est réservé et ne peut pas être utilisé comme membre d'une classe ref ou d'un type valeur. Les opérateurs CLR ou WinRT doivent être définis à l'aide du mot clé 'operator'  
  
Le compilateur a détecté une définition d’opérateur utilisant la syntaxe des extensions managées pour C++. Vous devez utiliser la syntaxe C++ pour les opérateurs.  
  
L'exemple suivant génère l'erreur C3195 et montre comment la corriger :  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```
