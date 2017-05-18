---
title: Compilateur avertissement (niveau 4) C4938 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4938
dev_langs:
- C++
helpviewer_keywords:
- C4938
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f4e3184d1833da65c73149eb89ab1be8b2249b4e
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4938"></a>Avertissement du compilateur (niveau 4) C4938
'var' : la variable de réduction à virgule flottante peut générer des résultats incohérents sous /fp:strict ou #pragma fenv_access  
  
 Vous ne devez pas utiliser [/fp : strict](../../build/reference/fp-specify-floating-point-behavior.md) ou [fenv_access](../../preprocessor/fenv-access.md) avec des réductions à virgule flottante OpenMP, car la somme est calculée dans un ordre différent. Par conséquent, les résultats peuvent différer des résultats obtenus sans /openmp.  
  
 L’exemple suivant génère l’avertissement C4938 :  
  
```  
// C4938.cpp  
// compile with: /openmp /W4 /fp:strict /c  
// #pragma fenv_access(on)  
extern double *a;   
  
double test(int first, int last) {   
   double sum = 0.0;   
   #pragma omp parallel for reduction(+: sum)   // C4938  
   for (int i = first ; i <= last ; ++i)   
      sum += a[i];   
   return sum;   
}  
```  
  
 Sans une parallélisation explicite, la somme est calculée comme suit :  
  
```  
sum = a[first] + a[first + 1] + ... + a[last];   
```  
  
 Avec une parallélisation explicite (et deux threads), la somme est calculée comme suit :  
  
```  
sum1 = a[first] + ... a[first + last / 2];   
sum2 = a[(first + last / 2) + 1] + ... a[last];   
sum = sum1 + sum2;  
```
