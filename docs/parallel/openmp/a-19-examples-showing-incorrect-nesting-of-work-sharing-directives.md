---
title: "Exemples A.19 montrant l’imbrication incorrecte de Directives de partage de travail | Documents Microsoft"
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
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8a3f8a4e1ca62a77c16dafedd0921ca842d7a048
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="a19---examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19   Exemples illustrant l'imbrication incorrecte de directives de partage de travail
Les exemples de cette section illustrent les règles d’imbrication de la directive. Pour plus d’informations sur l’imbrication de directive, consultez [Section 2.9](../../parallel/openmp/2-9-directive-nesting.md) sur la page 33.  
  
 L’exemple suivant n’est pas conforme, car la valeur interne et externe `for` directives sont imbriqués et les lier à la même `parallel` directive :  
  
```  
void wrong1(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
      int i, j;  
      #pragma omp for  
      for (i=0; i<n; i++) {  
          #pragma omp for  
              for (j=0; j<n; j++)  
                 work(i, j);  
     }  
   }  
}  
```  
  
 La version de l’exemple précédent dynamiquement imbriquée suivante est également non conforme :  
  
```  
void wrong2(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++)  
        work1(i, n);  
  }  
}  
  
void work1(int i, int n)  
{  
  int j;  
  #pragma omp for  
    for (j=0; j<n; j++)  
      work2(i, j);  
}  
```  
  
 L’exemple suivant n’est pas conforme, car le `for` et `single` directives sont imbriqués, et ils sont liés à la même région parallèle :  
  
```  
void wrong3(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        #pragma omp single  
          work(i);  
      }  
  }  
}  
```  
  
 L’exemple suivant n’est pas conforme, car un `barrier` directive à l’intérieur d’un `for` peut entraîner un interblocage :  
  
```  
void wrong4(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        work1(i);  
        #pragma omp barrier  
        work2(i);  
      }  
  }  
}  
```  
  
 L’exemple suivant n’est pas conforme, car le `barrier` entraîne un blocage dû au fait que seul thread à la fois peut entrer dans la section critique :  
  
```  
void wrong5()  
{  
  #pragma omp parallel  
  {  
    #pragma omp critical  
    {  
       work1();  
       #pragma omp barrier  
       work2();  
    }  
  }  
}  
```  
  
 L’exemple suivant n’est pas conforme, car le `barrier` entraîne un blocage dû au fait que seul un thread s’exécute le `single` section :  
  
```  
void wrong6()  
{  
  #pragma omp parallel  
  {  
    setup();  
    #pragma omp single  
    {  
      work1();  
      #pragma omp barrier  
      work2();  
    }  
    finish();  
  }  
}  
```