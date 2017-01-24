---
title: "3.1.7 omp_set_dynamic Function | Microsoft Docs"
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
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.7 omp_set_dynamic Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' **omp\_set\_dynamic** active ou désactive le réglage dynamique du nombre de threads disponibles pour l'exécution des régions parallèles.  Le format est comme suit :  
  
```  
#include <omp.h>  
void omp_set_dynamic(int dynamic_threads);  
```  
  
 Si *les dynamic\_threads* prend une valeur différente de zéro, le nombre de threads utilisés pour exécuter les régions parallèles suivantes peut être ajusté automatiquement par l'environnement d'exécution au mieux utilisent des ressources système.  Par conséquent, le nombre de threads spécifiés par l'utilisateur est le nombre de threads maximale.  Le nombre de threads de l'équipe qui exécute une région parallèle reste fixe pour la durée de cette région parallèle et est indiqué par la fonction d' **omp\_get\_num\_threads** .  
  
 Si *les dynamic\_threads* correspond à 0, la modification dynamique est désactivé.  
  
 Cette fonction a les effets décrits ci\-dessus en cas de appel d'une partie du programme où la fonction d' **omp\_in\_parallel** retourne zéro.  S'il s'agit d'une partie du programme où la fonction d' **omp\_in\_parallel** retourne une valeur différente de zéro, le comportement de cette fonction n'est pas défini.  
  
 Un appel à **omp\_set\_dynamic** est prioritaire sur la variable d'environnement **OMP\_DYNAMIC** .  
  
 La valeur par défaut pour la modification dynamique des threads implémentation\-est définie.  Par conséquent, les codes d'utilisateur qui dépendent d'un nombre spécifique de threads pour l'exécution correcte doivent désactiver explicitement les threads dynamiques.  Les implémentations ne sont pas requises pour vous permettre de modifier dynamiquement le nombre de threads, mais elles doivent fournir l'interface pour prendre en charge la portabilité sur toutes les plateformes.  
  
## Références croisées :  
  
-   la fonction d'**omp\_get\_num\_threads** , consultez [section 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) à la page 37.  
  
-   La variable d'environnement**OMP\_DYNAMIC** , consultez [section 4,3](../../parallel/openmp/4-3-omp-dynamic.md) à la page 49.  
  
-   la fonction d'**omp\_in\_parallel** , consultez [section 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) à la page 38.