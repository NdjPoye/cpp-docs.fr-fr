---
title: "2.3 parallel Construct | Microsoft Docs"
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
ms.assetid: 190eacdf-2c16-4c06-8cb7-ac60eb211425
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.3 parallel Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive suivante définit une région parallèle, qui est une zone de programme qui doit être exécuté par plusieurs threads en parallèle.  Il s'agit de l'élément fondamental qui commence l'exécution parallèle.  
  
```  
#pragma omp parallel [clause[ [, ]clause] ...] new-line  
   structured-block  
```  
  
 *La clause* est l'une des opérations suivantes :  
  
 *grandeur\-expression* **\)**de**si \(**  
  
 *variable\-liste* **\)**de**privé \(**  
  
 *variable\-liste* **\)**de**firstprivate \(**  
  
 **valeur par défaut \(partagée &#124; aucun\)**  
  
 *variable\-liste* **\)**de**\(partagé**  
  
 *variable\-liste* **\)**de**copyin \(**  
  
 *variable\-liste* **\)**de**Numéro de téléphone :** d'*opérateur de***réduction \(**  
  
 *entier\-expression* **\)**de**num\_threads \(**  
  
 Lorsqu'un thread rencontre un élément parallèle, une équipe de threads est créée si l'un des cas suivants est vrai :  
  
-   aucune clause d' **if** n'est présente.  
  
-   L'expression d' **if** prend une valeur différente de zéro.  
  
 Ce thread devient le thread principal de l'équipe, avec un nombre de threads de 0, et tous les threads de l'équipe, notamment le thread principal, exécutent la zone en parallèle.  si la valeur de l'expression d' **if** est zéro, la zone est sérialisée.  
  
 Pour déterminer le nombre de threads qui sont demandés, les règles suivantes sont considérées comme dans l'ordre.  La première règle dont la condition est satisfaite sera appliquée :  
  
1.  Si la clause de **num\_threads** est présente, la valeur de l'expression entière est le nombre de threads demandés.  
  
2.  Si la fonction de bibliothèque d' **omp\_set\_num\_threads** a été appelée, la valeur de l'argument dans l'appel récemment exécution est le nombre de threads demandés.  
  
3.  Si la variable d'environnement **OMP\_NUM\_THREADS** est définie, la valeur de cette variable d'environnement est le nombre de threads demandés.  
  
4.  Si aucune des méthodes ci\-dessus n'a été utilisée, le nombre de threads demandés implémentation\-est défini.  
  
 Si la clause de **num\_threads** est présent puis elle remplace le nombre de threads demandés par la fonction de bibliothèque d' **omp\_set\_num\_threads** ou la variable d'environnement **OMP\_NUM\_THREADS** uniquement pour la région parallèle qu'elle s'applique.  Les régions parallèles suivantes ne sont pas affectées par elle.  
  
 Le nombre de threads qui exécutent la région parallèle également dépend au moment si le réglage dynamique du nombre de threads est activé.  Si le réglage dynamique est désactivé, le nombre demandé de thread exécute la région parallèle.  Si le réglage dynamique est activé le nombre demandé de threads est le nombre maximal de threads qui peuvent s'exécuter la région parallèle.  
  
 Si une région parallèle est produite lors de la modification dynamique du nombre de threads est désactivé, et le nombre de threads demandés pour la région parallèle dépasse le nombre que le système runtime peut fournir, le comportement du programme implémentation\-est défini.  Une implémentation peut, par exemple, interrompre l'exécution du programme, ou elle peut sérialiser la région parallèle.  
  
 La fonction de bibliothèque d' **omp\_set\_dynamic** et la variable d'environnement **OMP\_DYNAMIC** peuvent être utilisées pour activer et désactiver le réglage dynamique du nombre de threads.  
  
 Le nombre de processeurs physiques qui hébergent réellement les threads à un moment donné implémentation\-est défini.  Une fois créées, le nombre de threads dans l'équipe reste constant pour la durée de cette zone parallèle.  Elle peut être modifiée explicitement par l'utilisateur ou automatiquement par le système d'exécution d'une région parallèle à un autre.  
  
 Les instructions contenues dans l'étendue dynamique de la zone parallèle sont exécutées par chaque thread, et chaque thread peut exécuter un chemin d'accès des instructions qui est différent des autres threads.  Les directives produites en dehors de l'étendue lexicale d'une région parallèle renvoie aux directives orphelines.  
  
 Il existe un cloisonnement implicite à la fin d'une zone parallèle.  Seul le thread principal de l'équipe l'exécution se poursuit à la fin d'une zone parallèle.  
  
 Si un thread dans une équipe qui exécute une région parallèle rencontre un autre élément parallèle, elle crée une nouvelle équipe, et il devient la forme de base de cette nouvelle équipe.  Les régions parallèles imbriquées sont sérialisées par défaut.  En conséquence, par défaut, une région parallèle imbriquée est exécutée par l'équipe composée d'un thread.  Le comportement par défaut peut être modifié à l'aide de la fonction de la bibliothèque Runtime **omp\_set\_nested** ou de la variable d'environnement **OMP\_NESTED**.  Toutefois, le nombre de threads dans une équipe qui exécutent une région parallèle imbriquée implémentation\-est défini.  
  
 Les restrictions à la directive de **parallèle** sont les suivantes :  
  
-   Au plus une clause d' **if** peut apparaître sur la directive.  
  
-   Il n'est pas spécifiée si tous les effets secondaires à l'intérieur de si l'expression ou l'expression de **num\_threads** se produisent.  
  
-   Un intérieur exécuté par **throw** une région parallèle doit provoquer l'exécution au résumé dans l'étendue dynamique du même bloc structuré, et il doit être intercepté par le même thread qui a levé l'exception.  
  
-   Uniquement une clause unique de **num\_threads** peut apparaître sur la directive.  L'expression de **num\_threads** est évaluée en dehors de le contexte de la zone parallèle, et doit prendre une valeur entière positive.  
  
-   L'ordre d'évaluation des clauses d' **if** et de **num\_threads** n'est pas spécifiée.  
  
## Références croisées :  
  
-   **privé**, **firstprivate**, **valeur par défaut**, **partagé**, **copyin**, et les clauses de **réduction** , consultez [section 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) à la page 25.  
  
-   Variable d'environnement**OMP\_NUM\_THREADS** , [section 4,2](../../parallel/openmp/4-2-omp-num-threads.md) à la page 48.  
  
-   la fonction de bibliothèque d'**omp\_set\_dynamic** , consultez [section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39.  
  
-   La variable d'environnement**OMP\_DYNAMIC** , consultez [section 4,3](../../parallel/openmp/4-3-omp-dynamic.md) à la page 49.  
  
-   la fonction d'**omp\_set\_nested** , consultez [section 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) à la page 40.  
  
-   La variable d'environnement**OMP\_NESTED** , consultez [section 4,4](../../parallel/openmp/4-4-omp-nested.md) à la page 49.  
  
-   la fonction de bibliothèque d'**omp\_set\_num\_threads** , consultez [section 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) à la page 36.