---
title: Erreur du compilateur C3052 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3052
dev_langs:
- C++
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e64f86fca9ec4f356e3af36cc2804daf5970eed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3052"></a>Erreur du compilateur C3052
'var' : la variable n’apparaît pas dans une clause de partage de données sous une clause default(none)  
  
 Si [default(none)](../../parallel/openmp/reference/default-openmp.md) est utilisé, toute variable utilisée dans le bloc structuré doit être spécifiée explicitement comme [shared](../../parallel/openmp/reference/shared-openmp.md) ou [private](../../parallel/openmp/reference/private-openmp.md).  
  
 L’exemple suivant génère l’erreur C3052 :  
  
```  
// C3052.cpp  
// compile with: /openmp /c  
int main() {  
   int n1 = 1;  
  
   #pragma omp parallel default(none) // shared(n1) private(n1)  
   {  
      n1 = 0;   // C3052 use either a shared or private clause  
   }  
}  
```