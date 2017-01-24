---
title: "3.1.9 omp_set_nested Function | Microsoft Docs"
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
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.9 omp_set_nested Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la fonction d' **omp\_set\_nested** active ou désactive le parallélisme imbriqué.  Le format est comme suit :  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 Si *imbriqué* correspond à 0, le parallélisme imbriqué est désactivé, qui est la valeur par défaut, les régions et parallèles imbriquées sont sérialisées et exécutées par le thread actuel.  Si *imbriqué* prend une valeur différente de zéro, le parallélisme imbriqué est activé, et des zones de parallèle qui sont imbriquées peuvent déployer des threads supplémentaires pour former les équipes imbriquées.  
  
 Cette fonction a les effets décrits ci\-dessus en cas de appel d'une partie du programme où la fonction d' **omp\_in\_parallel** retourne zéro.  S'il s'agit d'une partie du programme où la fonction d' **omp\_in\_parallel** retourne une valeur différente de zéro, le comportement de cette fonction n'est pas défini.  
  
 Cet appel est prioritaire sur la variable d'environnement **OMP\_NESTED** .  
  
 Lorsque le parallélisme imbriqué est activé, le nombre de threads utilisés pour exécuter les régions parallèles imbriquées implémentation\-est défini.  Par conséquent, il permet aux des implémentations OpenMP\-conformes pour sérialiser les régions parallèles imbriquées même lorsque le parallélisme imbriqué est activé.  
  
## Références croisées :  
  
-   La variable d'environnement**OMP\_NESTED** , consultez [section 4,4](../../parallel/openmp/4-4-omp-nested.md) à la page 49.  
  
-   la fonction d'**omp\_in\_parallel** , consultez [section 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) à la page 38.