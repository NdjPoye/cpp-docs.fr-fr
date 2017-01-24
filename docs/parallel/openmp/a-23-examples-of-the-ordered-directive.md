---
title: "A.23   Examples of the ordered Directive | Microsoft Docs"
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
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.23   Examples of the ordered Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Il est possible d'avoir les sections classées par plusieurs avec `for` spécifié avec la clause d' `ordered` .  le premier exemple est non conforme parce que l'API spécifie ce qui suit :  
  
 « Une itération d'une boucle avec un élément d' `for` ne doit pas effectuer la même directive d' `ordered` plusieurs fois, et elle ne doit pas exécuter plusieurs directive d' `ordered` ». \(Consultez [section 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) à la page 22\)  
  
 dans cet exemple non conforme, toutes les itérations exécutent 2 sections classées :  
  
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
  
 L'exemple conforme suivant montre `for` avec plusieurs section classée :  
  
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