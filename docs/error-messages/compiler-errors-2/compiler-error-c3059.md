---
title: Erreur du compilateur C3059 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3059
dev_langs:
- C++
helpviewer_keywords:
- C3059
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
caps.latest.revision: 10
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
ms.openlocfilehash: c48d0f5017fa22b0ecb725278fdc6818ecebf405
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3059"></a>Erreur du compilateur C3059
'var' : le symbole 'threadprivate' ne peut pas être utilisé dans la clause 'clause'  
  
 A [threadprivate](../../parallel/openmp/reference/threadprivate.md) symbole a été utilisé dans une clause.  
  
 L’exemple suivant génère l’erreur C3059 :  
  
```  
// C3059.cpp  
// compile with: /openmp  
#include "omp.h"  
int x, y;  
#pragma omp threadprivate(x, y)  
  
int main() {  
   #pragma omp parallel private(x, y)   // C3059  
   {  
      x = y;  
   }  
}  
```  
  
 Solution possible :  
  
```  
// C3059b.cpp  
// compile with: /openmp  
#include "omp.h"  
int x = 0, y = 0;  
  
int main() {  
   #pragma omp parallel firstprivate(y) private(x)  
   {  
      x = y;  
   }  
}  
```
