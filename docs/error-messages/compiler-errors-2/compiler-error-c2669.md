---
title: Erreur du compilateur C2669 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2669
dev_langs: C++
helpviewer_keywords: C2669
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0cd56be9cba1fcefa269f30579dcace4f3166660
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2669"></a>Erreur du compilateur C2669
fonction membre non autorisée dans une union anonyme  
  
[Les unions anonymes](../../cpp/unions.md#anonymous_unions) ne peut pas avoir de fonctions membres.  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère l’erreur C2669 :  
  
```cpp  
// C2669.cpp  
struct X {  
   union {  
      int i;  
      void f() {   // C2669, remove function  
         i = 0;   
      }  
   };  
};  
```  
  