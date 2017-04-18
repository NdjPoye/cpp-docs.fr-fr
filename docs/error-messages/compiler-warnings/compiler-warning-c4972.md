---
title: Avertissement du compilateur C4972 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4972
dev_langs:
- C++
helpviewer_keywords:
- C4972
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
caps.latest.revision: 4
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
ms.openlocfilehash: a7a135fdcaed2be284c4762a9124188871187ba0
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4972"></a>Avertissement du compilateur C4972
La modification ou le traitement direct du résultat d'une conversion unboxing comme lvalue est non vérifiable  
  
 Quand vous procédez au déréférencement d’un handle en un type valeur, (également appelé « conversion unboxing »), puis effectuez une assignation à celui-ci, le résultat est non vérifiable.  
  
 Pour plus d’informations, consultez [Boxing](../../windows/boxing-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4972.  
  
```  
// C4972.cpp  
// compile with: /clr:safe  
using namespace System;  
ref struct R {  
   int ^ p;   // a value type  
};  
  
int main() {  
   R ^ r = gcnew R;  
   *(r->p) = 10;   // C4972  
  
   // OK  
   r->p = 10;  
   Console::WriteLine( r->p );  
   Console::WriteLine( *(r->p) );  
}  
```
