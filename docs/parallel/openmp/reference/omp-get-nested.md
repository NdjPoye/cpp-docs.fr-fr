---
title: "omp_get_nested | Microsoft Docs"
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
  - "omp_get_nested"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_nested OpenMP function"
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_get_nested
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Retourne une valeur qui indique si le parallélisme imbriqué est activé.  
  
## Syntaxe  
  
```  
int omp_get_nested( );  
```  
  
## Valeur de retour  
 si une valeur différente de zéro, parallélisme imbriqué est activé.  
  
## Notes  
 le parallélisme imbriqué est spécifié avec [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) et [OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md).  
  
 Pour plus d'informations, consultez [3.1.10 omp\_get\_nested Function](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).  
  
## Exemple  
 Consultez l' [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) pour un exemple d'utilisation `omp_get_nested`.  
  
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)