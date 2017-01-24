---
title: "A.20   Binding of barrier Directives | Microsoft Docs"
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
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.20   Binding of barrier Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'appel de directive règles de liaison pour qu'une directive de **cloisonnement** une liaison avec la directive d' `parallel` englobante la plus proche.  Pour plus d'informations sur la liaison directive, consultez [section 2,8](../../parallel/openmp/2-8-directive-binding.md) à la page 32.  
  
 Dans l'exemple suivant, l'appel *de* main vers *sub2* est conforme parce que **cloisonnement** \(dans *sub3*\) se lie à la région parallèle dans *sub2*.  L'appel *de* main vers *sub1* est conforme parce que **cloisonnement** l'associe à la région parallèle de la sous\-routine *sub2*.  L'appel *de* main vers *sub3* est conforme parce que **cloisonnement** ne se lie à aucune zone parallèle et est ignoré.  Notez également que **cloisonnement** synchronise uniquement l'équipe de threads dans une région parallèle englobante et de tous les threads créés dans *sub1*.  
  
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