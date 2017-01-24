---
title: "Performances des biblioth&#232;ques multithread | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "bibliothèques, multithread"
  - "bibliothèques multithread"
  - "performances, multithreading"
  - "threads (C++), performances"
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Performances des biblioth&#232;ques multithread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le CRT monothread n'est plus disponible.  Cette rubrique explique comment obtenir des performances maximales des bibliothèques multithread.  
  
## optimiser les performances  
 Les performances des bibliothèques multithread ont été améliorées et sont proches des performances des bibliothèques monothread, qui n'existent plus désormais.  Pour ces situations quand des performances encore meilleures sont requises, il existe plusieurs nouvelles fonctionnalités.  
  
-   Le verrouillage indépendant de flux de données permet de verrouiller un flux de données puis d'utiliser [\_nolock, fonctions](../c-runtime-library/nolock-functions.md) qui accèdent au flux de données directement.  Cela permet à l'usage verrouillé de s'élever hors des bucles critiques.  
  
-   Les paramètres régionaux par thread réduisent le coût d'accès des paramètres régionaux pour les scénarios multithread \(consultez [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)\).  
  
-   Les fonctions liées aux paramètres régionaux \(dont le nom se termine par \_l\) prennent les paramètres régionaux en tant que paramètre, ce qui supprime des couts substantiels \(par exemple, [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\).  
  
-   Les optimisations pour des pages de codes communes réduisent le coût de nombreuses opérations courtes.  
  
-   La définition de[\_\(CRT\)\_DISABLE\_PERFCRIT\_LOCKS](../c-runtime-library/crt-disable-perfcrit-locks.md) force toutes les opérations d'E\/S à assumer le modèle monothread d'E\/S et à utiliser les formes \_nolock des fonctions.  Cela permet à des applications mono\-thread très axées E\/S d'avoir de meilleures performances.  
  
-   L'exposition du gestionnaire de segment CRT vous permet de vérifier le segment \(LFH\) de fragmentation windows pour le segment CRT, ce qui peut améliorer considérablement les performances dans les cas très mis à l'échelle.  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)