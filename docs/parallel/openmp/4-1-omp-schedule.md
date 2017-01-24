---
title: "4.1 OMP_SCHEDULE | Microsoft Docs"
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
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.1 OMP_SCHEDULE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_SCHEDULE** s'applique uniquement à **pour** et aux directives de **parallèle pour** ayant le type **runtime**de planification.  Le type et la taille du segment de planification pour toutes ces boucles peuvent être fixés au moment de l'exécution en définissant cette variable d'environnement substituent les types marqués l'un des de planification et à un facultatif *chunk\_size*.  
  
 Pour **pour** et les directives de **parallèle pour** qui ont un type de planification autre que **runtime**, **OMP\_SCHEDULE** est ignoré.  La valeur par défaut de cette variable d'environnement implémentation\-est définie.  si le facultatif *chunk\_size* est défini, la valeur doit être positif.  Si *chunk\_size* n'est pas défini, une valeur de 1 est supposé, à moins que dans le cas d'une planification de **statique** .  Pour une planification de **statique** , la taille du segment par défaut est égale à l'espace d'itération de boucle divisé par le nombre de threads appliqués à la boucle.  
  
 Exemple :  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## Références croisées :  
  
-   la directive de**pour** , consultez [section 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) à la page 11.  
  
-   la directive de**parallèle pour** , consultez [section 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) à la page 16.