---
title: "E. Implementation-Defined Behaviors in OpenMP C/C++ | Microsoft Docs"
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
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# E. Implementation-Defined Behaviors in OpenMP C/C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cette annexe résume les comportements qui sont décrits comme « implémentation\-définis » dans cette API.  Chaque comportement est établi les références croisées rétablissant sa description dans la spécification principale.  
  
## Remarques  
 Une implémentation est requise pour définir et documenter son comportement dans ces cas, mais cette liste peut être incomplète.  
  
-   **Nombre de threads :** si une région parallèle est produite lors de la modification dynamique du nombre de threads est désactivé, et le nombre de threads demandés pour la région parallèle dépasse le nombre que le système runtime peut fournir, le comportement du programme implémentation\-est défini \(voir la page 9\).  
  
     Dans Visual C\+\+, pour une zone parallèle non imbriquée, 64 threads \(le maximum\) seront fournis.  
  
-   **Nombre de processeurs :** le nombre de processeurs physiques qui hébergent réellement les threads à un moment donné implémentation\-est défini \(voir la page 10\).  
  
     Dans Visual C\+\+, ce numéro n'est pas fixe, qui est contrôlé par le système d'exploitation.  
  
-   **Créer des équipes de threads :** le nombre de threads dans une équipe qui exécutent une région parallèle imbriquée implémentation\-est défini. \(consultez la page 10\).  
  
     Dans Visual C\+\+, il est déterminé par le système d'exploitation.  
  
-   **planifier \(runtime\) :** la décision concernant la planification est différé au moment de l'exécution.  Le type et la taille du segment de planification peuvent être choisis au moment de l'exécution en définissant la variable d'environnement `OMP_SCHEDULE` .  Si cette variable d'environnement n'est pas définie, la planification résultant implémentation\-est défini \(voir la page 13\).  
  
     Dans Visual C\+\+, le type de planification est `static` sans la taille du segment.  
  
-   **planifier par défaut :** en l ' absence d'une clause de planification, le calendrier par défaut implémentation\-est défini \(voir la page 13\).  
  
     Dans Visual C\+\+, le type de planification par défaut est `static` sans la taille du segment.  
  
-   **ATOMIQUE :** elle implémentation\-est la valeur si une implémentation remplace toutes les directives d' `atomic` par les directives de **critique** qui ont le même nom unique \(voir la page 20\).  
  
     Dans Visual C\+\+, si les données modifiées par [atomic](../../parallel/openmp/reference/atomic.md) n'est pas sur un alignement naturel ou si elle est de 1 ou 2 octets toutes les opérations atomiques qui satisfont cette propriété utiliseront une section critique.  Sinon, des sections critiques ne seront pas utilisées.  
  
-   **omp\_get\_num\_threads :** si le nombre de threads n'a pas été explicitement défini par l'utilisateur, la valeur par défaut implémentation\-est défini \(voir la page 9, et le [section 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) à la page 37\).  
  
     Dans Visual C\+\+, le nombre par défaut de threads est égal au nombre de processeurs.  
  
-   **omp\_set\_dynamic :** la valeur par défaut pour l'ajustement dynamique de thread implémentation\-est défini \(consultez [section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39\).  
  
     dans Visual C\+\+, la valeur par défaut est `FALSE`.  
  
-   **omp\_set\_nested :** lorsque le parallélisme imbriqué est activé, le nombre de threads utilisés pour exécuter les régions parallèles imbriquées implémentation\-est défini \(consultez [section 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) à la page 40\).  
  
     Dans Visual C\+\+, le nombre de threads est déterminé par le système d'exploitation.  
  
-   variable d'environnement`OMP_SCHEDULE` : La valeur par défaut de cette variable d'environnement implémentation\-est la valeur \(consultez [section 4,1](../../parallel/openmp/4-1-omp-schedule.md) à la page 48\).  
  
     Dans Visual C\+\+, le type de planification est `static` sans la taille du segment.  
  
-   variable d'environnement`OMP_NUM_THREADS` : Si aucune valeur n'est spécifiée pour la variable d'environnement `OMP_NUM_THREADS` , ou si la valeur spécifiée n'est pas un entier positif, ou si la valeur est supérieure au nombre maximal de threads le système peut prendre en charge, le nombre de threads à utiliser implémentation\-est défini \(consultez [section 4,2](../../parallel/openmp/4-2-omp-num-threads.md) à la page 48\).  
  
     Dans Visual C\+\+, si la valeur spécifiée est zéro ou moins, le nombre de threads est égal au nombre de processeurs.  Si la valeur est supérieure à 64, le nombre de threads est 64.  
  
-   variable d'environnement`OMP_DYNAMIC` : La valeur par défaut implémentation\-est la valeur \(consultez [section 4,3](../../parallel/openmp/4-3-omp-dynamic.md) à la page 49\).  
  
     dans Visual C\+\+, la valeur par défaut est `FALSE`.