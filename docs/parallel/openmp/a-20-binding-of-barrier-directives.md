---
title: "Liaison A.20 des Directives de barrière | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8d88c431753d918c05866324dd6436a091d6057a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="a20---binding-of-barrier-directives"></a>A.20   Liaison de directives barrier
La liaison de directives de règles de l’appel pour un **barrière** directive à lier englobant le plus proche `parallel` directive. Pour plus d’informations sur la liaison de directives, consultez [Section 2.8](../../parallel/openmp/2-8-directive-binding.md) à la page 32.  
  
 Dans l’exemple suivant, l’appel de *principal* à *sub2* est conforme, car le **barrière** (dans *sub3*) est liée à la région parallèle dans *sub2*. L’appel de *principal* à *sub1* est conforme, car le **barrière** est liée à la région parallèle de la sous-routine *sub2*.  L’appel de *principal* à *sub3* est conforme, car le **barrière** n’est pas lié à une région parallèle et est ignoré. Notez également que la **barrière** synchronise uniquement les threads dans la région parallèle englobante et pas tous les threads créés dans les équipes *sub1*.  
  
```  
int main()  
{  
    sub1(2);  
    sub2(2);  
    sub3(2);  
}  
  
void sub1(int n)  
{  
    int i;  
    #pragma omp parallel private(i) shared(n)  
    {  
        #pragma omp for  
        for (i=0; i<n; i++)  
            sub2(i);  
    }  
}  
  
void sub2(int k)  
{  
     #pragma omp parallel shared(k)  
     sub3(k);  
}  
  
void sub3(int n)  
{  
    work(n);  
    #pragma omp barrier  
    work(n);  
}  
```