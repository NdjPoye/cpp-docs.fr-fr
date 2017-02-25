---
title: "Comment&#160;: g&#233;rer une instance de planificateur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gérer une instance de planificateur (runtime d'accès concurrentiel)"
  - "instances de planificateur, gérer [runtime d’accès concurrentiel]"
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Comment&#160;: g&#233;rer une instance de planificateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les instances du planificateur vous permettent d'associer des stratégies de planification spécifiques à différents genres de charges de travail.  Cette rubrique contient deux exemples de base qui indiquent comment créer et gérer une instance du planificateur.  
  
 Les exemples créent des planificateurs qui utilisent les stratégies du planificateur par défaut.  Pour obtenir un exemple qui crée un planificateur qui utilise une stratégie personnalisée, consultez [Comment : spécifier des stratégies de planificateur](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).  
  
### Pour gérer une instance du planificateur dans votre application  
  
1.  Créez un objet [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) qui contient les valeurs de stratégie que le planificateur doit utiliser.  
  
2.  Appelez la méthode [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md) ou la méthode [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) pour créer une instance du planificateur.  
  
     Si vous utilisez la méthode `Scheduler::Create`, appelez la méthode [concurrency::Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md) lorsque vous devez associer le planificateur au contexte actuel.  
  
3.  Appelez la fonction [CreateEvent](http://msdn.microsoft.com/library/windows/desktop/ms682396) pour créer un handle vers un objet événement à réinitialisation automatique non signalé.  
  
4.  Passez le handle vers l'objet événement que vous venez de créer à la méthode [concurrency::CurrentScheduler::RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md) ou [concurrency::Scheduler::RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md).  Cela enregistre l'événement à définir lors de la destruction du planificateur.  
  
5.  Effectuez les tâches que vous voulez que le planificateur actuel planifie.  
  
6.  Appelez la méthode [concurrency::CurrentScheduler::Detach](../Topic/CurrentScheduler::Detach%20Method.md) pour détacher le planificateur actuel et restaurer le planificateur précédent comme planificateur actuel.  
  
     Si vous utilisez la méthode `Scheduler::Create`, appelez la méthode [concurrency::Scheduler::Release](../Topic/Scheduler::Release%20Method.md) pour décrémenter le décompte de références de l'objet `Scheduler`.  
  
7.  Passez le handle vers l'événement à la fonction [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032) pour attendre que le planificateur s'arrête.  
  
8.  Appelez la fonction [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) pour fermer le handle vers l'objet événement.  
  
## Exemple  
 Le code suivant illustre deux manières de gérer une instance du planificateur.  Chaque exemple utilise d'abord le planificateur par défaut pour effectuer une tâche qui imprime l'identificateur unique du planificateur actuel.  Chaque exemple utilise ensuite une instance du planificateur pour effectuer de nouveau la même tâche.  Pour finir, chaque exemple restaure le planificateur par défaut comme planificateur actuel et exécute la tâche une fois de plus.  
  
 Le premier exemple utilise la classe [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) pour créer une instance du planificateur et l'associer au contexte actuel.  Le deuxième exemple utilise la classe [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) pour effectuer la même tâche.  En général, la classe `CurrentScheduler` s'utilise avec le planificateur actuel.  Le deuxième exemple, qui utilise la classe `Scheduler`, est utile lorsque vous voulez contrôler le moment où le planificateur est associé au contexte actuel ou lorsque vous voulez associer des planificateurs spécifiques à des tâches spécifiques.  
  
 [!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/CPP/how-to-manage-a-scheduler-instance_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **Utilisation de la classe de CurrentScheduler…**  
**ID du planificateur actuel : 0**  
**Création et attachement du planificateur…**  
**ID du planificateur actuel : 1**  
**Détachement du planificateur…**  
**ID du planificateur actuel : 0**  
**Utilisation de la classe du planificateur…**  
**ID du planificateur actuel : 0**  
**Création du planificateur…**  
**Attachement du planificateur…**  
**ID du planificateur actuel : 2**  
**Détachement du planificateur…**  
**ID du planificateur actuel : 0**   
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio, ou collez\-le dans un fichier nommé `scheduler-instance.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc scheduler\-instance.cpp**  
  
## Voir aussi  
 [Instances de planificateur](../../parallel/concrt/scheduler-instances.md)   
 [Comment : spécifier des stratégies de planificateur](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)