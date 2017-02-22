---
title: "OMP_DYNAMIC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OMP_DYNAMIC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_DYNAMIC OpenMP environment variable"
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie si le runtime OpenMP peut ajuster le nombre de threads dans une région parallèle.  
  
## Syntaxe  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## Notes  
 La variable d'environnement `OMP_DYNAMIC` peut être remplacée par la fonction d' [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) .  
  
 la valeur par défaut dans l'implémentation de Visual C\+\+ du standard d'OpenMP est `OMP_DYNAMIC=FALSE`.  
  
 Pour plus d'informations, consultez [4.3 OMP\_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).  
  
## Exemple  
 La commande suivante définit la variable d'environnement `OMP_DYNAMIC` la valeur TRUE :  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 La commande suivante affiche le paramètre actuel de la variable d'environnement `OMP_DYNAMIC` :  
  
```  
set OMP_DYNAMIC  
```  
  
## Voir aussi  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)