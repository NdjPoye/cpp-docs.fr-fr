---
title: "4.3 OMP_DYNAMIC | Microsoft Docs"
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
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.3 OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La variable d'environnement **OMP\_DYNAMIC** active ou désactive le réglage dynamique du nombre de threads disponibles pour l'exécution des régions parallèles sauf si le réglage dynamique soit explicitement activé ou désactivé en appelant la routine de bibliothèque d' **omp\_set\_dynamic** .  sa valeur doit être **TRUE** ou **FALSE**.  
  
 Si l'ensemble à **TRUE**, le nombre de threads utilisés pour exécuter les régions parallèles peut être contrôlé par l'environnement d'exécution au mieux utiliser des ressources système.  si l'ensemble à **FALSE**, réglage dynamique est désactivé.  l'état par défaut implémentation\-est défini.  
  
 Exemple :  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## Références croisées :  
  
-   Pour plus d'informations sur les régions parallèles, consultez [section 2,3](../../parallel/openmp/2-3-parallel-construct.md) à la page 8.  
  
-   la fonction d'**omp\_set\_dynamic** , consultez [section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39.