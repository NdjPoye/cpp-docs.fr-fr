---
title: Erreur du compilateur C3012 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3012
dev_langs: C++
helpviewer_keywords: C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a75b8845fafef81768ae5a2da8c81e8734db4ebf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3012"></a>Erreur du compilateur C3012
  
> '*intrinsèque*' : fonction intrinsèque non autorisée directement dans une région parallèle  
  
 Une fonction [intrinsèque du compilateur](../../intrinsics/compiler-intrinsics.md) n’est pas autorisée dans une région `omp parallel` . Pour résoudre ce problème, déplacez intrinsèques hors de la région, ou remplacez-les par leurs équivalents non intrinsèque.   
  
## <a name="example"></a>Exemple  
  
 L’exemple suivant génère l’erreur C3012 et illustre une façon de pour résoudre ce problème :  
  
```cpp  
// C3012.cpp  
// compile with: /openmp  
#ifdef __cplusplus  
extern "C" {  
#endif  
void* _ReturnAddress();  
#ifdef __cplusplus  
}  
#endif  
  
int main()  
{  
   #pragma omp parallel  
   {  
      _ReturnAddress();   // C3012  
   }  
   _ReturnAddress();      // OK  
}  
```