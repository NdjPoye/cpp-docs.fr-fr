---
title: "3. Fonctions de la biblioth&#232;que d’ex&#233;cution | Microsoft Docs"
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
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3. Fonctions de la biblioth&#232;que d’ex&#233;cution
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette section décrit les fonctions de bibliothèque OpenMP C et C++. L’en-tête **\< omp.h >** déclare deux types, plusieurs fonctions qui peuvent être utilisées pour contrôler et de l’environnement d’exécution en parallèle de la requête et de verrouiller les fonctions qui peuvent être utilisées pour synchroniser l’accès aux données.  
  
 Le type **omp_lock_t** est un type d’objet permettant de représenter qu’un verrou est disponible, ou qu’un thread détient un verrou. Ces verrous sont appelés *verrous simples*.  
  
 Le type **être imbriqué omp_nest_lock_t** est un type d’objet permettant de représenter qu’un verrou est disponible, ou l’identité du thread qui possède le verrou et un *imbrication nombre* (décrite ci-dessous). Ces verrous sont appelés *verrous pouvant être imbriqués*.  
  
 Les fonctions de bibliothèque sont des fonctions externes avec une liaison de « C ».  
  
 Les descriptions contenues dans ce chapitre sont réparties dans les rubriques suivantes :  
  
-   Fonctions de l’environnement d’exécution (voir [Section 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) à la page 35).  
  
-   Fonctions de verrouillage (voir [Section 3.2](../../parallel/openmp/3-2-lock-functions.md) page 41).