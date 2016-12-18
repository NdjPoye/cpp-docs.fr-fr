---
title: "D. Using the schedule Clause | Microsoft Docs"
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
ms.assetid: bf3d8f51-ea05-4803-bf55-657c12e91efe
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D. Using the schedule Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une région parallèle contient au moins un cloisonnement, à la fin, et peut avoir des barrières supplémentaires dans celui\-ci.  À chaque le cloisonnement, les autres membres de l'équipe doivent attendre le dernier thread pour archiver.  Pour réduire ce délai d'attente, le travail partagé doit être distribué afin que tous les threads arrivent au cloisonnement à la même heure.  Si de que le travail partagé est contenu dans des éléments de **pour** , la clause d' `schedule` peut être utilisée à cet effet.  
  
 Lorsqu'il existe des références répétées aux mêmes objets, le choix de planification pour un élément de **pour** peut être déterminé origine par des caractéristiques du système mémoire, telles que la présence et la taille en cache et si les temps d'accès de mémoire sont uniformes ou non\-uniformes.  De telles considérations peuvent s'avérer préférable de le faire référence chaque thread régulièrement au même ensemble d'éléments d'un tableau d'une série de boucles, même si certains threads sont assignés relativement moins de travail dans certaines boucles.  Cela peut être effectuée à l'aide de planification de **statique** avec les mêmes limites pour toutes les boucles.  Dans l'exemple suivant, notez que zéro est utilisé comme la limite inférieure dans la seconde boucle, même si **k** soit plus naturel si la planification n'étaient pas important.  
  
```  
#pragma omp parallel  
{  
#pragma omp for schedule(static)  
  for(i=0; i<n; i++)  
    a[i] = work1(i);  
#pragma omp for schedule(static)  
  for(i=0; i<n; i++)  
    if(i>=k) a[i] += work2(i);  
}  
```  
  
 Dans les exemples restants, on suppose que l'accès à la mémoire n'est pas une attention dominante, et, sauf indication contraire, que tous les threads reçoivent les ressources de calcul comparables.  Dans ces cas, le choix de planification pour un élément de **pour** dépend de tout le travail partagé qui doit être effectuée entre le cloisonnement précédent le plus proche et le cloisonnement fermant implicite ou le cloisonnement suivant le plus proche, s'il existe une clause d' `nowait` .  Pour chaque type de planification, un bref montre comment ce type de planification peut être le meilleur choix.  Une brève description suit chaque exemple.  
  
 La planification de **statique** est également approprié pour le cas le plus simple, une région parallèle contenant un seul élément de **pour** , chaque itération demandant au même volume de travail.  
  
```  
#pragma omp parallel for schedule(static)  
for(i=0; i<n; i++) {  
  invariant_amount_of_work(i);  
}  
```  
  
 La planification de **statique** est caractérisé par les propriétés que chaque thread est environ au même nombre d'itérations que tout autre thread, et chaque thread peut indépendamment déterminer les itérations assignées à celui\-ci.  Donc aucune synchronisation n'est requise pour distribuer le travail, et, en supposant que chaque itération requiert le même volume de travail, tous les threads doivent se terminer à la même heure.  
  
 Pour une équipe de threads d' `p` , conservez *la valeur plafond \(n\/p\)* l'entier *q*, qui satisfait *n \= p\*q \- r* avec *0 \<\= r \< P.* Une implémentation de planification de **statique** pour cet exemple assignerait les itérations *de q* aux premier thread *p\-1* , et itérations *de q\-r* au dernier thread.  Une autre implémentation acceptable assignerait les itérations *de q* aux premier thread *de PRS\-AF.* , et les itérations *q\-1* *au r* restant des threads.  Cela montre pourquoi un programme ne doit pas dépendre des détails d'implémentation particulière.  
  
 La planification de **dynamique** est approprié pour le cas d'un élément de **pour** avec les itérations requérant varier, ou même imprévisible, des montants de travail.  
  
```  
#pragma omp parallel for schedule(dynamic)  
  for(i=0; i<n; i++) {  
    unpredictable_amount_of_work(i);  
}  
```  
  
 La planification de **dynamique** est caractérisé par la propriété qu'aucun thread n'attend au cloisonnement plus longtemps qu'il prend un autre thread pour exécuter son itération finale.  Cela nécessite que les itérations soient assignées un par un des threads lorsqu'elles sont disponibles, avec la synchronisation pour chaque assignation.  La charge de synchronisation peut être réduite en spécifiant une taille du segment minimum *k* supérieure à 1, afin que les threads soient assignés *k* à la fois jusqu'à ce que moins de *k* restent.  Cela garantit qu'aucun thread n'attend au cloisonnement plus longtemps qu'il prend un autre thread pour exécuter son segment final \(au plus\) des itérations *de k* .  
  
 La planification de **dynamique** peut être utile si les threads reçoivent varier les ressources de calcul, qui a plus ou moins le même effet que variant des montants de travail pour chaque itération.  De même, la planification dynamique peut également être utile si les threads arrivent à l'élément de **pour** à diverses périodes toutefois, dans certaines de ces cas dans la planification de **guidée** peut être préférable.  
  
 La planification de **guidée** est approprié pour le cas où les threads peuvent arriver à diverses périodes à un élément de **pour** avec chaque itération nécessitant la quantité de travail à peu près identique.  Cela peut se produire si, par exemple, l'élément de **pour** est précédé d'un ou plusieurs sections ou éléments de **pour** avec les clauses d' `nowait` .  
  
```  
#pragma omp parallel  
{  
  #pragma omp sections nowait  
  {  
    // ...  
  }  
  #pragma omp for schedule(guided)  
  for(i=0; i<n; i++) {  
    invariant_amount_of_work(i);  
  }  
}  
```  
  
 Comme **dynamique**, la planification de **guidée** garantit qu'aucun thread n'attend au cloisonnement plus longtemps qu'il prend un autre thread pour exécuter son itération finale, ou des itérations précédentes *du k* si la taille *du* segment de *k* est spécifiée.  Parmi de ces planifications, la planification de **guidée** est caractérisé par la propriété qu'il requiert les moins synchronisations.  Pour la taille du segment *k*, une implémentation assignera *q \= valeur plafond \(n\/p\)* les itérations au premier thread disponible, définissent *n* au supérieur *du nq* et *du p\*k*, puis répétez l'opération jusqu'à ce que toutes les itérations soient assignées.  
  
 Lorsque le choix de planification optimal n'est pas aussi clairement que pour ces exemples, la planification de **runtime** est pratique pour expérimenter avec des planifications et tailles de segment sans devoir modifier et recompiler le programme.  Il peut également être utile lorsque la planification optimal dépend \(d'une certaine façon prévisible\) de données d'entrée à laquelle le programme est appliqué.  
  
 Pour voir un exemple des compromis entre plusieurs calendriers, envisagez de partager 1000 itérations entre 8 threads.  Supposons une quantité de travail indifférente dans chaque itération, et utilisez ce comme unité de temps.  
  
 Si tous les threads démarrent en même temps, la planification de **statique** entraînera l'exécution de l'élément dans les 125 unités, sans la synchronisation.  mais supposez qu'un thread est 100 unités en retard dans l'arrivée.  Les sept threads restants attendent 100 unités dans le cloisonnement, et la durée d'exécution pour l'élément entière passe à 225.  
  
 Étant donné que les planifications de **dynamique** et de **guidée** garantissent qu'aucun thread n'attend plusieurs unité dans le cloisonnement, le thread suspendu provoque les durées d'exécution pour l'élément passe uniquement jusqu'à 138 unités, probablement affectées par les délais de synchronisation.  Si ces délais ne sont pas négligeables, il est important que le nombre de synchronisations soit 1000 pour **dynamique** mais seulement 41 pour **guidée**, en supposant que la taille du segment par défaut d'une.  Avec une taille du segment de 25, **dynamique** et **guidée** les deux fois dans les 150 unités, plus les délais des synchronisations requises, qui s'attendent maintenant seulement 40 et 20, respectivement.