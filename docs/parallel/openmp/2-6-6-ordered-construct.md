---
title: "2.6.6 ordered Construct | Microsoft Docs"
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
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.6 ordered Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le bloc structuré après une directive de **dimensionné** est exécuté dans l'ordre dans lequel les itérations sont exécutées dans une boucle séquentielle.  La syntaxe de la directive de **dimensionné** est la suivante :  
  
```  
#pragma omp ordered new-line  
   structured-block  
```  
  
 Une directive de **dimensionné** doit se situer dans l'étendue dynamique d'un élément de **pour** ou de **parallèle pour** .  La directive de **pour** ou de **parallèle pour** à laquelle l'élément de **dimensionné** des liens doit avoir une clause de **dimensionné** spécifiée comme décrit dans [section 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) à la page 11.  Dans l'exécution d'un élément de **pour** ou de **parallèle pour** avec une clause de **dimensionné** , les éléments de **dimensionné** sont exécutés strictement dans l'ordre dans lequel ils seraient exécutés dans une exécution séquentielle de la boucle.  
  
 Les restrictions à la directive de **dimensionné** sont les suivantes :  
  
-   Une itération d'une boucle avec un élément de **pour** ne doit pas effectuer la même directive classée plusieurs fois, et elle ne doit pas exécuter plusieurs directive de **dimensionné** .