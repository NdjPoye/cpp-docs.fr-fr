---
title: "OMP_NESTED | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OMP_NESTED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_NESTED OpenMP environment variable"
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# OMP_NESTED
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

spécifie si le parallélisme imbriqué est activé, à moins que le parallélisme imbriqué soit activé ou désactivé avec `omp_set_nested`.  
  
## Syntaxe  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## Notes  
 La variable d'environnement `OMP_NESTED` peut être remplacée par la fonction d' [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) .  
  
 la valeur par défaut dans l'implémentation de Visual C\+\+ du standard d'OpenMP est `OMP_DYNAMIC=FALSE`.  
  
 Pour plus d'informations, consultez [4.4 OMP\_NESTED](../../../parallel/openmp/4-4-omp-nested.md).  
  
## Exemple  
 La commande suivante définit la variable d'environnement `OMP_NESTED` la valeur TRUE :  
  
```  
set OMP_NESTED=TRUE  
```  
  
 La commande suivante affiche le paramètre actuel de la variable d'environnement `OMP_NESTED` :  
  
```  
set OMP_NESTED  
```  
  
## Voir aussi  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)