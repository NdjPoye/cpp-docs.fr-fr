---
title: "A.25   Examples of the copyprivate Data Attribute Clause | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.25   Examples of the copyprivate Data Attribute Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**exemple 1 :** la clause d' `copyprivate` \([section 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) à la page 32\) peut être utilisé pour diffuser des valeurs acquises par un thread unique directement à toutes les instances des variables privées dans les autres threads.  
  
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
  
 Si *l'init* actuelle est appelé d'une zone série, son comportement n'est pas affecté par la présence de directives.  Après l'appel à la routine *de get\_values* a été exécuté par un thread, aucun thread ne quitte l'élément jusqu'à ce que les objets privés indiqués par *a*, *b*, *x*, *y* et dans tous les threads sont devenus défini avec la lecture de valeurs.  
  
 **exemple 2 :** contrairement à l'exemple précédent, supposent que la lecture doit être exécutée par un thread particulier, de déterminer le thread principal.  Dans ce cas, la clause d' `copyprivate` ne peut pas être utilisée pour effectuer la diffusion directement, mais elle peut être utilisée pour fournir l'accès à un objet partagé temporaire.  
  
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
  
 **exemple 3 :** supposent que le nombre d'objets lock requis dans une région parallèle ne peut pas être facilement déterminé avant de l'écrire.  La clause d' `copyprivate` peut être utilisée pour fournir l'accès aux objets de verrou partagé qui sont alloués dans cette région parallèle.  
  
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