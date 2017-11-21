---
title: Erreur du compilateur C3003 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3003
dev_langs: C++
helpviewer_keywords: C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 98479fda012d06b9eff57b5fcbf4dc883c94d9e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3003"></a>Erreur du compilateur C3003
'directive' : nom de directive OpenMP non autorisé après des clauses de directive  
  
 Un nom de directive OpenMP ne peut pas suivre une clause de directive OpenMP.  
  
 L’exemple suivant génère l’erreur C3003 :  
  
```  
// C3003.c  
// compile with: /openmp  
int main()  
{  
   int x, y, z;  
   #pragma omp parallel shared(x, y, z) for   // C3003  
}  
```