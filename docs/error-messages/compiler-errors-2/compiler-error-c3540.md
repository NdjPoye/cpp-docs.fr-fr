---
title: Erreur du compilateur C3540 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3540
dev_langs: C++
helpviewer_keywords: C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0ff7a017ce86e567d0aabcf494e11f48d1cdea05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3540"></a>Erreur du compilateur C3540
'type' : Impossible d’appliquer sizeof à un type contenant 'auto'  
  
 Le [sizeof](../../cpp/sizeof-operator.md) opérateur ne peut pas être appliqué au type indiqué car il contient le `auto` spécificateur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant donne C3540.  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)   
 [/ Zc : auto (déduire le Type de Variable)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof, opérateur](../../cpp/sizeof-operator.md)