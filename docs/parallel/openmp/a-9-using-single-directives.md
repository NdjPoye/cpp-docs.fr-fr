---
title: "A.9   Using single Directives | Microsoft Docs"
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
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.9   Using single Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'exemple suivant illustre la directive d' `single` \([section 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) à la page 15\).  Dans l'exemple, un seul thread \(généralement le premier thread qui rencontre la directive d' `single` \) imprime le message de progression.  L'utilisateur ne doit effectuer aucune hypothèses quant à laquelle le thread exécute la section d' `single` .  Tous les autres threads ignorent la section d' `single` et arrêtera au cloisonnement à la fin de l'élément d' `single` .  Si d'autres threads peuvent continuer sans attendre que le thread s'exécutant la section d' `single` , une clause d' `nowait` peut être spécifiée dans la directive d' `single` .  
  
```  
#pragma omp parallel  
{  
    #pragma omp single  
        printf_s("Beginning work1.\n");  
    work1();  
    #pragma omp single  
        printf_s("Finishing work1.\n");  
    #pragma omp single nowait  
        printf_s("Finished work1 and beginning work2.\n");  
    work2();  
}  
```