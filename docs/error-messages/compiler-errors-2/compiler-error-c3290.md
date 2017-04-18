---
title: Erreur du compilateur C3290 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3290
dev_langs:
- C++
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
caps.latest.revision: 8
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 70cb6104f0aca5ae0e33cad2042d34a52cdc1945
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3290"></a>Erreur du compilateur C3290
'type' : une propriété triviale ne peut pas avoir de type référence  
  
 Une propriété n’a pas été correctement déclarée. Quand vous déclarez une propriété triviale, le compilateur crée une variable que la propriété va mettre à jour et il n’est pas possible d’avoir une variable de référence de suivi dans une classe.  
  
 Consultez [propriété](../../windows/property-cpp-component-extensions.md) et [opérateur de référence de suivi](../../windows/tracking-reference-operator-cpp-component-extensions.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3290.  
  
```  
// C3290.cpp  
// compile with: /clr /c  
ref struct R {};  
  
ref struct X {  
   R^ mr;  
  
   property R % y;   // C3290  
   property R ^ x;   // OK  
  
   // OK  
   property R% prop {  
      R% get() {   
         return *mr;   
      }  
  
      void set(R%) {}  
   }  
};  
  
int main() {  
   X x;  
   R% xp = x.prop;  
}  
```
