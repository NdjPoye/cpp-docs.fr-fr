---
title: "3. Fonctions de la bibliothèque Runtime | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1cbedf8782c9c5ccb25bda3f8b43df8a526f268
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="3-run-time-library-functions"></a>3. Fonctions de la bibliothèque Runtime
Cette section décrit les fonctions de bibliothèque OpenMP C et C++. L’en-tête  **\<omp.h >** déclare deux types, plusieurs fonctions qui peuvent être utilisées pour contrôler l’environnement d’exécution parallèle de la requête et verrouiller des fonctions qui peuvent être utilisées pour synchroniser l’accès aux données.  
  
 Le type **omp_lock_t** un type d’objet n’est capable de représenter qu’un verrou est disponible ou qu’un thread possède un verrou. Ces verrous sont appelés *verrous simples*.  
  
 Le type **omp_nest_lock_t** est un type d’objet capable de représenter qu’un verrou est disponible, ou l’identité du thread qui détient le verrou et un *imbrication nombre* (décrites ci-dessous). Ces verrous sont appelés *verrous pouvant*.  
  
 Les fonctions de bibliothèque sont des fonctions externes avec une liaison de « C ».  
  
 Les descriptions de ce chapitre sont réparties dans les rubriques suivantes :  
  
-   Fonctions de l’environnement d’exécution (consultez [Section 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) à la page 35).  
  
-   Fonctions de verrouillage (consultez [Section 3.2](../../parallel/openmp/3-2-lock-functions.md) page 41).