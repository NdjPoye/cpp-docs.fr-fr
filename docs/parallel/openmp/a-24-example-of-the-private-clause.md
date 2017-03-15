---
title: "A.24   Example of the private Clause | Microsoft Docs"
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
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.24   Example of the private Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La clause d' `private` \([section 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) à la page 25\) d'une région parallèle est uniquement en vigueur pour l'étendue lexicale de la zone, pas pour l'étendue dynamique de la zone.  Par conséquent, dans l'exemple qui suit, toutes les utilisations de la variable *a* dans la boucle d' `for` dans la routine *f* fait référence à une copie privée *d'un*, alors qu'une utilisation dans la routine *g* fait référence *à.*global *.*  
  
```  
int a;  
  
void f(int n)   
{  
    a = 0;  
  
    #pragma omp parallel for private(a)  
    for (int i=1; i<n; i++)   
    {  
        a = i;  
        g(i, n);  
        d(a);     // Private copy of "a"  
        ...  
    }  
    ...  
  
void g(int k, int n)   
{  
    h(k,a); // The global "a", not the private "a" in f  
}  
```