---
title: "Comparaison des structures de donn&#233;es de synchronisation avec l’API Windows | Microsoft Docs"
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
helpviewer_keywords: 
  - "structures de données de synchronisation, en comparaison avec l’API Windows"
  - "event, classe, exemple"
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
caps.latest.revision: 16
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comparaison des structures de donn&#233;es de synchronisation avec l’API Windows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique compare le comportement des structures de données de synchronisation fournies par le runtime d'accès concurrentiel à celles fournies par l'API Windows.  
  
 Les structures de données de synchronisation fournies par le runtime d'accès concurrentiel suivent le *modèle de thread coopératif*.  Dans le modèle de thread coopératif, les primitives de synchronisation cèdent explicitement leurs ressources de traitement à d'autres threads.  Cela diffère du *modèle de thread préemptif*, selon lequel les ressources de traitement sont transférées à d'autres threads par le système d'exploitation ou le planificateur de contrôle.  
  
## critical\_section  
 La classe [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) s'apparente à la structure `CRITICAL_SECTION` Windows, car elle peut uniquement être utilisée par les threads d'un seul processus.  Pour plus d'informations sur les sections critiques dans l'API Windows, consultez [Objets de section critique](http://msdn.microsoft.com/library/windows/desktop/ms682530).  
  
## reader\_writer\_lock  
 La classe [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) s'apparente aux verrous SRW \(Slim Reader\/Writer\) de Windows.  Le tableau suivant explique quelles sont les similarités et les différences.  
  
|Fonctionnalité|`reader_writer_lock`|Verrou SRW|  
|--------------------|--------------------------|----------------|  
|Non réentrant|Oui|Oui|  
|Peut promouvoir un lecteur en enregistreur \(prise en charge de la mise à niveau\)|Non|Non|  
|Peut rétrograder un enregistreur en lecteur \(prise en charge de la rétrogradation\)|Non|Non|  
|Verrou à préférence d'écriture|Oui|Non|  
|Accès FIFO aux enregistreurs|Oui|Non|  
  
 Pour plus d'informations sur les verrous SRW, consultez la rubrique sur les [verrous SRW \(Slim Reader\/Writer\)](http://msdn.microsoft.com/library/windows/desktop/aa904937) dans le Kit de développement Platform SDK.  
  
## event  
 La classe [concurrency::event](../../parallel/concrt/reference/event-class.md) s'apparente à un événement Windows à réinitialisation manuelle sans nom.  Toutefois, un objet `event` se comporte de manière coopérative, alors qu'un événement Windows se comporte de manière préemptive.  Pour plus d'informations sur les événements Windows, consultez [Objets événements](http://msdn.microsoft.com/library/windows/desktop/ms682655).  
  
## Exemple  
  
### Description  
 Pour mieux comprendre la différence entre la classe `event` et les événements Windows, considérez l'exemple suivant.  Cet exemple permet au planificateur de créer au plus deux tâches simultanées, puis il appelle deux fonctions semblables qui utilisent la classe `event` et un événement Windows à réinitialisation manuelle.  Chaque fonction crée d'abord plusieurs tâches qui attendent qu'un événement partagé soit signalé.  Chaque fonction cède ensuite aux tâches en cours d'exécution, puis signale l'événement.  Chaque fonction attend ensuite l'événement signalé.  
  
### Code  
 [!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/CPP/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]  
  
### Commentaires  
 Cet exemple génère l'exemple de sortie suivant :  
  
  **Événement coopératif :**  
 **Contexte 0 : attente sur un événement.**  
 **Contexte 1 : attente sur un événement.**  
 **Contexte 2 : attente sur un événement.**  
 **Contexte 3 : attente sur un événement.**  
 **Contexte 4 : attente sur un événement.**  
 **Définit l'événement.**  
 **Contexte 5 : a reçu l'événement.**  
 **Contexte 6 : événement reçu.**  
 **Contexte 7 : événement reçu.**  
 **Contexte 8 : événement reçu.**  
 **Contexte 9 : événement reçu.**  
**Événement Windows**  
 **Contexte 10 : attente d'un événement.**  
 **Contexte 11 : attente d'un événement.**  
 **Définit l'événement.**  
 **Contexte 12 : événement reçu.**  
 **Contexte 14 : attente d'un événement.**  
 **Contexte 15 : événement reçu.**  
 **Contexte 16 : attente d'un événement.**  
 **Contexte 17 : événement reçu.**  
 **Contexte 18 : attente d'un événement.**  
 **Contexte 19 : événement reçu.**  
 **Contexte 13 : événement reçu.** Étant donné que la classe `event` se comporte de manière coopérative, le planificateur peut réaffecter les ressources de traitement à un autre contexte lorsqu'un événement attend de passer à l'état signalé.  Par conséquent, davantage de travail est accompli par la version qui utilise la classe `event`.  Dans la version qui utilise des événements Windows, chaque tâche en attente doit passer à l'état signalé avant que la tâche suivante soit démarrée.  
  
 Pour plus d'informations sur les tâches, consultez [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## Voir aussi  
 [Structures de données de synchronisation](../../parallel/concrt/synchronization-data-structures.md)   
 [Objets de section critique](http://msdn.microsoft.com/library/windows/desktop/ms682530)   
 [Verrous légers \(SRW\) de lecture\/écriture léger](http://msdn.microsoft.com/library/windows/desktop/aa904937)   
 [Objets événement](http://msdn.microsoft.com/library/windows/desktop/ms682655)