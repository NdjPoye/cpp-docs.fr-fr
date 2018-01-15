---
title: "Exemples A.23 de la Directive ordonnée | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83d77bb4f064a7ee69b013b36de919b57486b3e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   Exemples de directive ordered
Il est possible d’avoir plusieurs sections triées avec une `for` spécifié avec le `ordered` clause. Le premier exemple n’est pas conforme parce que l’API spécifie les éléments suivants :  
  
 « Une itération d’une boucle avec une `for` construction ne doit pas exécuter le même `ordered` directive plus qu’une seule fois et il ne doivent pas exécuter plusieurs `ordered` directive. » (Consultez [Section 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) à la page 22)  
  
 Dans cet exemple non conforme, toutes les itérations exécutent 2 sections ordonnées :  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
}  
```  
  
 L’exemple conforme suivant un `for` avec plusieurs triées section :  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    if (i <= 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
    (i > 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
}  
```