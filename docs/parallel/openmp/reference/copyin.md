---
title: "copyin | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "copyin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "copyin OpenMP clause"
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# copyin
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Permet aux threads d'accéder à la principale valeur du thread, pour une variable de [threadprivate](../../../parallel/openmp/reference/threadprivate.md) .  
  
## Syntaxe  
  
```  
copyin(var)  
```  
  
## Notes  
 où,  
  
 `var`  
 La variable d' `threadprivate` qui sera initialisée avec la valeur de la variable dans le thread principal, comme il existe avant que l'élément parallèle.  
  
## Notes  
 `copyin` s'applique aux directives suivantes :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d'informations, consultez [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## Exemple  
 Consultez [threadprivate](../../../parallel/openmp/reference/threadprivate.md) pour un exemple d'utilisation `copyin`.  
  
## Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)