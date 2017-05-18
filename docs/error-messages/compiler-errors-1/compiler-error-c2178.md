---
title: "C2178 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 96232cdb52fc84a90c768fa23b8a98da913c7982
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2178"></a>C2178 d’erreur du compilateur  
  
'*identificateur*'ne peut pas être déclarée avec'*spécificateur*' spécificateur  
  
A `mutable` spécificateur a été utilisé dans une déclaration, mais le spécificateur n’est pas autorisé dans ce contexte.  
  
Le `mutable` spécificateur peut être appliqué uniquement à des noms de membres de données de classe et ne peut pas être appliqué à des noms déclarés `const` ou `static`et ne peut pas être appliqué aux membres de référence.  
  
## <a name="example"></a>Exemple  
  
L’exemple suivant montre comment C2178 peut se produire et comment la corriger.  
  
```  
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```  

