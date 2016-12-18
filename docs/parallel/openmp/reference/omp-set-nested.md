---
title: "omp_set_nested | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_set_nested"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_nested OpenMP function"
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_nested
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Permet un imbriqué le parallélisme.  
  
## Syntaxe  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## Notes  
 où,  
  
 `val`  
 si une valeur différente de zéro, active le parallélisme imbriqué.  Si le zéro, désactive imbriquait le parallélisme.  
  
## Notes  
 Le parallélisme imbriqué par OMP peut être activé avec `omp_set_nested`, ou en définissant la variable d'environnement [OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md) .  
  
 Le paramètre pour `omp_set_nested` substitue le paramètre de la variable d'environnement `OMP_NESTED` .  
  
 En cas de activation, la variable d'environnement peut arrêter le programme sinon opérationnel parce que le nombre de threads augmente de façon exponentielle en imbriquant les régions parallèles.  Par exemple une fonction que le recurses 6 expiration avec le nombre de threads d'OMP a la valeur 4 requiert 4.096 \(4 à la puissance de 6\) entraîne généralement les performances de votre application diminueront si le nombre de threads dépasse le nombre de processeurs.  La seule exception à cette règle serait des applications liées aux E\/S.  
  
 Utilisez [omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md) pour afficher le paramètre actuel d' `omp_set_nested`.  
  
 Pour plus d'informations, consultez [3.1.9 omp\_set\_nested Function](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).  
  
## Exemple  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
  **1**  
**1**   
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)