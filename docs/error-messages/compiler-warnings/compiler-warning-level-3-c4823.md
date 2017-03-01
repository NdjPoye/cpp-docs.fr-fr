---
title: Compilateur avertissement (niveau 3) C4823 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: 12
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ea03723f9ccae2348a47ae4894097f5cd9f8b5a1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4823"></a>Avertissement du compilateur (niveau 3) C4823
'fonction' : utilise des pointeurs épingle mais déroulement sémantique n’est pas activée. Utilisez /EHa  
  
Pour supprimer un objet sur le tas managé vers lequel pointé un pointeur épingle déclaré dans une portée de bloc, le compilateur simule le comportement de destructeurs de classes locales, « prétendant » que le pointeur épingle possède un destructeur qui annule le pointeur. Pour activer un appel à un destructeur après une levée d’exception, vous devez activer le déroulement de l’objet, qui est possible à l’aide de [/EHsc](../../build/reference/eh-exception-handling-model.md).  
  
Vous pouvez également supprimer l’objet et ignorer l’avertissement.  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère l’erreur C4823.  
  
```  
// C4823.cpp  
// compile with: /clr /W3 /EHa-  
using namespace System;  
  
ref struct G {  
   int m;  
};  
  
void f(G ^ pG) {  
   try {  
      pin_ptr<int> p = &pG->m;  
      // manually unpin, ignore warning  
      // p = nullptr;  
      throw gcnew Exception;  
   }  
   catch(Exception ^) {}  
}   // C4823 warning  
  
int main() {  
   f( gcnew G );  
}  
```  

