---
title: "Vue d&#39;ensemble du runtime d&#39;acc&#232;s concurrentiel | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency Runtime, architecture"
  - "Concurrency Runtime, expressions lambda"
  - "Concurrency Runtime, vue d'ensemble"
  - "Concurrency Runtime, spécification"
ms.assetid: 56237d96-10b0-494a-9cb4-f5c5090436c5
caps.latest.revision: 22
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Vue d&#39;ensemble du runtime d&#39;acc&#232;s concurrentiel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document fournit une vue d'ensemble du runtime d'accès concurrentiel.  Il décrit les avantages du runtime d'accès concurrentiel, quand l'utiliser et la façon dont ses composants interagissent entre eux et avec le système d'exploitation et les applications.  
  
> [!IMPORTANT]
>  Dans Visual Studio 2015 et versions ultérieures, le planificateur de tâches du runtime d'accès concurrentiel n'est plus le planificateur de la classe de tâche et des types associés dans ppltasks.h.  Ces types utilisent désormais le pool de threads Windows pour de meilleures performances et une meilleure interopérabilité avec les primitives de synchronisation Windows.  Les algorithmes parallèles comme parallel\_for continuent à utiliser le planificateur de tâches du runtime d'accès concurrentiel.  
  
##  <a name="top"></a> Sections  
 Ce document contient les sections suivantes :  
  
-   [Pourquoi un runtime d'accès concurrentiel est\-il important ?](#runtime)  
  
-   [Architecture](#architecture)  
  
-   [Expressions lambda C\+\+](#lambda)  
  
-   [Spécifications](#requirements)  
  
##  <a name="runtime"></a> Pourquoi un runtime d'accès concurrentiel est\-il important ?  
 Un runtime d'accès concurrentiel fournit l'uniformité et la prévisibilité aux applications et à leurs composants qui s'exécutent simultanément.  Voici deux exemples des avantages du runtime d'accès concurrentiel : *planification de tâches coopérative* et *blocage coopératif*.  
  
 Le runtime d'accès concurrentiel utilise un planificateur de tâches coopératif qui implémente un algorithme de vol de travail pour distribuer efficacement le travail entre les ressources informatiques.  Par exemple, considérez une application qui a deux threads gérés par le même runtime.  Si un thread termine sa tâche planifiée, il peut décharger du travail de l'autre thread.  Ce mécanisme équilibre la charge de travail globale de l'application.  
  
 Le runtime d'accès concurrentiel fournit également des primitives de synchronisation qui utilisent le blocage coopératif pour synchroniser l'accès aux ressources.  Par exemple, considérez une tâche qui doit avoir un accès exclusif à une ressource partagée.  Par un blocage coopératif, le runtime peut utiliser le quantum restant pour effectuer une autre tâche, pendant que la première tâche attend la ressource.  Ce mécanisme favorise l'utilisation maximale des ressources informatiques.  
  
 \[[Haut](#top)\]  
  
##  <a name="architecture"></a> Architecture  
 Le runtime d'accès concurrentiel se divise en quatre composants : la bibliothèque de modèles parallèles \(PPL\), la bibliothèque d'agents asynchrones, le planificateur de tâches et le gestionnaire des ressources.  Ces composants résident entre le système d'exploitation et les applications.  L'illustration suivante montre comment les composants du runtime d'accès concurrentiel interagit entre le système d'exploitation et les applications :  
  
 **Architecture du runtime d'accès concurrentiel**  
  
 ![Architecture de runtime d'accès concurrentiel](../../parallel/concrt/media/concurrencyrun.png "ConcurrencyRun")  
  
> [!IMPORTANT]
>  Les composants du planificateur de tâches et du gestionnaire des ressources ne sont pas disponibles dans une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] ou quand vous utilisez la classe de tâche ou d'autres types dans ppltasks.h.  
  
 Le runtime d'accès concurrentiel est hautement *composable*, autrement dit, vous pouvez combiner les fonctionnalités existantes pour les optimiser.  Le runtime d'accès concurrentiel compose de nombreuses fonctionnalités, telles que des algorithmes parallèles, à partir de composants de niveau inférieur.  
  
 Le runtime d'accès concurrentiel fournit également des primitives de synchronisation qui utilisent le blocage coopératif pour synchroniser l'accès aux ressources.  Pour plus d'informations sur ces primitives de synchronisation, consultez [Structures de données de synchronisation](../../parallel/concrt/synchronization-data-structures.md).  
  
 Les sections suivantes fournissent un bref aperçu de ce que fournit chaque composant et quand les utiliser.  
  
### bibliothèque de modèles parallèles  
 La bibliothèque de modèles parallèles \(PPL\) fournit des algorithmes et des conteneurs à usage général pour effectuer un parallélisme affiné.  La PPL permet un *parallélisme des données impératif* en fournissant des algorithmes parallèles qui distribuent des calculs sur des collections ou ensembles de données entre les ressources informatiques.  Elle permet également un *parallélisme des tâches* en fournissant des objets de tâche qui distribuent plusieurs opérations indépendantes entre les ressources informatiques.  
  
 Utilisez la bibliothèque de modèles parallèles quand vous avez un calcul local qui peut tirer parti d'une exécution en parallèle.  Par exemple, vous pouvez utiliser l'algorithme [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) pour transformer une boucle `for` existante afin qu'elle agisse en parallèle.  
  
 Pour plus d'informations sur la bibliothèque de modèles parallèles, consultez [Bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md).  
  
### Bibliothèque d'agents asynchrones  
 La bibliothèque d'agents asynchrones \(ou simplement *bibliothèque d'agents*\) fournit à la fois un modèle de programmation basé sur des acteurs et des interfaces de passage de messages pour le flux de données à granularité grossière et les tâches de traitement « pipeline ».  Les agents asynchrones vous permettent d'utiliser de façon productive la latence, en effectuant le travail pendant que d'autres composants attendent des données.  
  
 Utilisez la bibliothèque d'agents quand vous avez plusieurs entités qui communiquent entre elles de façon asynchrone.  Par exemple, vous pouvez créer un agent qui lit des données à partir d'un fichier ou d'une connexion réseau, puis utilise les interfaces de passage de messages pour envoyer ces données à un autre agent.  
  
 Pour plus d'informations sur la bibliothèque d'agents, consultez [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md).  
  
### Planificateur de tâches  
 Le planificateur de tâches planifie et coordonne les tâches au moment de l'exécution.  Il est coopératif et utilise un algorithme de vol de travail pour optimiser l'utilisation des ressources de traitement.  
  
 Le runtime d'accès concurrentiel fournit un planificateur par défaut pour que vous n'ayez pas à gérer les détails de l'infrastructure.  Toutefois, pour répondre aux besoins de qualité de votre application, vous pouvez également fournir votre propre stratégie de planification ou associer des planificateurs spécifiques à des tâches spécifiques.  
  
 Pour plus d'informations sur le planificateur de tâches, consultez [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
### Gestionnaire des ressources  
 Le rôle du gestionnaire des ressources est de gérer les ressources informatiques, comme les processeurs et la mémoire.  Le gestionnaire des ressources répond aux charges de travail à mesure qu'elles changent au moment de l'exécution en affectant des ressources là où elles peuvent être les plus efficaces.  
  
 Le gestionnaire des ressources sert d'abstraction sur les ressources informatiques et interagit principalement avec le planificateur de tâches.  Bien que vous puissiez utiliser le gestionnaire des ressources pour ajuster les performances de vos bibliothèques et applications, vous utilisez généralement la fonctionnalité fournie par la bibliothèque de modèles parallèles, la bibliothèque d'agents et le planificateur de tâches.  Ces bibliothèques utilisent le gestionnaire des ressources pour rééquilibrer de manière dynamique les ressources à mesure que les charges de travail évoluent.  
  
 \[[Haut](#top)\]  
  
##  <a name="lambda"></a> Expressions lambda C\+\+  
 La plupart des types et algorithmes définis par le runtime d'accès concurrentiel sont implémentés en tant que modèles C\+\+.  Certains de ces types et algorithmes prennent comme paramètre une routine qui effectue le travail.  Ce paramètre peut être une fonction lambda, un objet de fonction ou un pointeur de fonction.  Ces entités sont également appelées *fonctions de travail* ou *routines de travail*.  
  
 Les expressions lambda sont une nouvelle fonctionnalité importante du langage Visual C\+\+, car elles offrent un moyen concis de définir des fonctions de travail pour un traitement parallèle.  Les objets de fonction et les pointeurs de fonction vous permettent d'utiliser le runtime d'accès concurrentiel avec votre code existant.  Toutefois, nous vous recommandons d'utiliser des expressions lambda quand vous écrivez un nouveau code en raison des avantages en matière de sécurité et de productivité qu'elles apportent.  
  
 L'exemple suivant compare la syntaxe de fonctions lambda, d'objets de fonction et de pointeurs de fonction dans plusieurs appels à l'algorithme [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md).  Chaque appel à `parallel_for_each` utilise une technique différente pour calculer le carré de chaque élément dans un objet [std::array](../../standard-library/array-class-stl.md).  
  
 [!code-cpp[concrt-comparing-work-functions#1](../../parallel/concrt/codesnippet/CPP/overview-of-the-concurrency-runtime_1.cpp)]  
  
 **Sortie**  
  
  **1**  
**256**  
**6561**  
**65536**  
**390625** Pour plus d'informations sur les fonctions lambda en C\+\+, consultez [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md).  
  
 \[[Haut](#top)\]  
  
##  <a name="requirements"></a> Spécifications  
 Le tableau suivant présente les fichiers d'en\-tête associés à chaque composant du runtime d'accès concurrentiel :  
  
|Composant|Fichiers d'en\-tête|  
|---------------|-------------------------|  
|Bibliothèque de modèles parallèles|ppl.h<br /><br /> concurrent\_queue.h<br /><br /> concurrent\_vector.h|  
|Bibliothèque d'agents asynchrones|agents.h|  
|Planificateur de tâches|concrt.h|  
|Gestionnaire des ressources|concrtrm.h|  
  
 Le runtime d'accès concurrentiel est déclaré dans l'espace de noms [Concurrency](../../parallel/concrt/reference/concurrency-namespace.md).  \(Vous pouvez également utiliser [concurrency](../../parallel/concrt/reference/concurrency-namespace.md), qui est un alias de cet espace de noms.\) L'espace de noms `concurrency::details` prend en charge l'infrastructure du runtime d'accès concurrentiel et n'a pas vocation à être utilisé directement à partir de votre code.  
  
 Le runtime d'accès concurrentiel est fourni dans le cadre de la bibliothèque Runtime C \(CRT\).  Pour plus d'informations sur la création d'une application qui utilise la bibliothèque Runtime C \(CRT\), consultez [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
 \[[Haut](#top)\]