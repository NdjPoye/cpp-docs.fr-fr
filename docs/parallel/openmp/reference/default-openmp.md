---
title: "default (OpenMP) | Microsoft Docs"
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
  - "default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default OpenMP clause"
  - "defaults, OpenMP clause"
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# default (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie le comportement des variables unscoped dans la région parallèle.  
  
## Syntaxe  
  
```  
default(shared | none)  
```  
  
## Notes  
 `shared`, qui est appliqué si la clause d' `default` n'est pas spécifiée, signifie que toute variable dans une région parallèle est traitée comme si elle était spécifiées avec la clause de [shared](../../../parallel/openmp/reference/shared-openmp.md) .  `none` signifie que toutes les variables utilisées dans une région parallèle qui ne sont pas limitées à [private](../../../parallel/openmp/reference/private-openmp.md), [shared](../../../parallel/openmp/reference/shared-openmp.md), [reduction](../../../parallel/openmp/reference/reduction.md), [firstprivate](../../../parallel/openmp/reference/firstprivate.md), ou la clause de [lastprivate](../../../parallel/openmp/reference/lastprivate.md) provoque une erreur du compilateur.  
  
 `default` s'applique aux directives suivantes :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d'informations, consultez [2.7.2.5 default](../../../parallel/openmp/2-7-2-5-default.md).  
  
## Exemple  
 Consultez [private](../../../parallel/openmp/reference/private-openmp.md) pour un exemple d'utilisation `default`.  
  
## Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)