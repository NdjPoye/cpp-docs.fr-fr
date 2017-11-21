---
title: Utilisation A.27 de tableaux de longueur Variable C99 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8e542701-39f9-4f28-ab3a-840e8e669723
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 673eeb7229524b17c12a9a40c64380e4e5bb5feb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="a27---use-of-c99-variable-length-arrays"></a>A.27   Utilisation de tableaux de longueur variable C99
L’exemple suivant montre comment utiliser des tableaux de longueur Variable C99 (VLAs) dans un `firstprivate` directive ([Section 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) sur la page 26).  
  
> [!NOTE]
>  Tableaux de longueur variable ne sont pas actuellement pris en charge dans Visual C++.  
  
```  
void f(int m, int C[m][m])  
{  
    double v1[m];  
    ...  
    #pragma omp parallel firstprivate(C, v1)  
    ...  
}  
```