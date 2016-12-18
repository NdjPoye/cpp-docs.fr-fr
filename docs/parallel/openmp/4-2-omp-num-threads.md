---
title: "4.2 OMP_NUM_THREADS | Microsoft Docs"
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
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.2 OMP_NUM_THREADS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La variable d'environnement **OMP\_NUM\_THREADS** définit le nombre par défaut de threads à utiliser pendant l'exécution, à moins que ce nombre est explicitement modifié en appelant la routine de bibliothèque d' **omp\_set\_num\_threads** ou par une clause explicite de **num\_threads** sur une directive de **parallèle** .  
  
 La valeur de la variable d'environnement **OMP\_NUM\_THREADS** doit être un entier positif.  Son effet dépend au moment si le réglage dynamique du nombre de threads est activé.  Pour un ensemble de règles sur l'interaction entre la variable d'environnement **OMP\_NUM\_THREADS** et la modification dynamique des threads, consultez la section 2,3 à la page 8.  
  
 Si aucune valeur n'est spécifiée pour la variable d'environnement **OMP\_NUM\_THREADS** , ou si la valeur spécifiée n'est pas un entier positif, ou si la valeur est supérieure au nombre maximal de threads le système peut prendre en charge, le nombre de threads à utiliser implémentation\-est défini.  
  
 Exemple :  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## Références croisées :  
  
-   la clause de**num\_threads** , consultez [section 2,3](../../parallel/openmp/2-3-parallel-construct.md) à la page 8.  
  
-   la fonction d'**omp\_set\_num\_threads** , consultez [section 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) à la page 36.  
  
-   la fonction d'**omp\_set\_dynamic** , consultez [section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39.