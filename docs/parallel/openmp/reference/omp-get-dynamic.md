---
title: "omp_get_dynamic | Microsoft Docs"
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
  - "omp_get_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_dynamic OpenMP function"
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_get_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Retourne une valeur qui indique si le nombre de threads disponibles dans la région parallèle suivante peut être ajusté par le runtime.  
  
## Syntaxe  
  
```  
int omp_get_dynamic();  
```  
  
## Valeur de retour  
 Si une valeur différente de zéro, réglage dynamique des threads est activé.  
  
## Notes  
 La modification dynamique des threads est spécifié avec [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) et [OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md).  
  
 Pour plus d'informations, consultez [3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## Exemple  
 Consultez l' [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) pour un exemple d'utilisation `omp_get_dynamic`.  
  
## Voir aussi  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)