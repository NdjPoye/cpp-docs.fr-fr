---
title: "Exemples A.25 de la Clause d’attribut de données copyprivate | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cdf7598e00bab72966fe79454567b0a59dcbaae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="a25---examples-of-the-copyprivate-data-attribute-clause"></a>A.25   Exemples de la clause d'attribut de données copyprivate
**Exemple 1 :** le `copyprivate` clause ([Section 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) à la page 32) peut être utilisé pour la diffusion des valeurs acquis par un seul thread directement à toutes les instances des variables privées dans les autres threads.  
  
```  
float x, y;  
#pragma omp threadprivate(x, y)  
  
void init( )   
{  
    float a;  
    float b;  
  
    #pragma omp single copyprivate(a,b,x,y)  
    {  
        get_values(a,b,x,y);  
    }  
  
    use_values(a, b, x, y);  
}  
```  
  
 Si la routine *init* est appelée à partir d’une région de série, son comportement n’est pas affecté par la présence des directives. Après l’appel à la *get_values* routine a été exécutée par un thread, aucun thread ne quitte la construction jusqu'à ce que les objets privés désignés par *un*, *b*, *x*, et *y* dans tous les threads sont définis avec les valeurs lues.  
  
 **Exemple 2 :** Contrairement à l’exemple précédent, supposons que la lecture doit être exécutée par un thread particulier, par exemple le thread principal. Dans ce cas, le `copyprivate` clause ne peut pas être utilisée pour effectuer la diffusion directement, mais il peut être utilisé pour fournir l’accès à un objet temporaire.  
  
```  
float read_next( )   
{  
    float * tmp;  
    float return_val;  
  
    #pragma omp single copyprivate(tmp)  
    {  
        tmp = (float *) malloc(sizeof(float));  
    }  
  
    #pragma omp master  
    {  
        get_float( tmp );  
    }  
  
    #pragma omp barrier  
    return_val = *tmp;  
    #pragma omp barrier  
  
    #pragma omp single  
    {  
       free(tmp);  
    }  
  
    return return_val;  
}  
```  
  
 **Exemple 3 :** Supposons que le nombre d’objets de verrou requis dans une région parallèle ne peut pas être déterminé facilement avant la saisie de celui-ci. Le `copyprivate` clause peut être utilisée pour fournir l’accès aux objets de verrou partagé sont alloués dans cette région parallèle.  
  
```  
#include <omp.h>  
  
omp_lock_t *new_lock()  
{  
    omp_lock_t *lock_ptr;  
  
    #pragma omp single copyprivate(lock_ptr)  
    {  
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));  
        omp_init_lock( lock_ptr );  
    }  
  
    return lock_ptr;  
}  
```