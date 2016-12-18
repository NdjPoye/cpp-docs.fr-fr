---
title: "Structures de donn&#233;es de synchronisation | Microsoft Docs"
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
  - "structures de données de synchronisation"
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
caps.latest.revision: 26
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Structures de donn&#233;es de synchronisation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le runtime d'accès concurrentiel fournit plusieurs structures de données qui vous permettent de synchroniser l'accès aux données partagées de plusieurs threads.  Ces structures de données sont utiles lorsque vous avez des données partagées que vous modifiez rarement.  Un objet de synchronisation, par exemple une section critique, fait en sorte que d'autres threads attendent que la ressource partagée soit disponible.  Par conséquent, si vous utilisez un tel objet pour synchroniser l'accès à des données qui sont utilisées fréquemment, vous pouvez perdre l'extensibilité dans votre application.  La [Bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md) fournit la classe [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md), qui vous permet de partager une ressource entre plusieurs threads ou tâches sans avoir recours à la synchronisation.  Pour plus d'informations sur la classe `combinable`, consultez [Conteneurs et objets parallèles](../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="top"></a> Sections  
 Cette rubrique décrit les types de blocs de messages asynchrones en détail :  
  
-   [critical\_section](#critical_section)  
  
-   [reader\_writer\_lock](#reader_writer_lock)  
  
-   [scoped\_lock et scoped\_lock\_read](#scoped_lock)  
  
-   [event](#event)  
  
##  <a name="critical_section"></a> critical\_section  
 La classe [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) représente un objet d'exclusion mutuelle coopératif qui cède à d'autres tâches au lieu de les préempter.  Les sections critiques sont utiles lorsque plusieurs threads requièrent un accès en lecture et en écriture exclusif aux données partagées.  
  
 La classe `critical_section` est non réentrante.  La méthode [concurrency::critical\_section::lock](../Topic/critical_section::lock%20Method.md) lève une exception de type [concurrency::improper\_lock](../../parallel/concrt/reference/improper-lock-class.md) si elle est appelée par le thread qui détient déjà le verrou.  
  
### Méthodes et fonctionnalités  
 Le tableau suivant répertorie les méthodes importantes définies par la classe `critical_section`.  
  
|Méthode|Description|  
|-------------|-----------------|  
|[verrouiller](../Topic/critical_section::lock%20Method.md)|Acquiert la section critique.  Le contexte appelant bloque jusqu'à ce qu'il acquière le verrou.|  
|[try\_lock](../Topic/critical_section::try_lock%20Method.md)|Essaie d'acquérir la section critique, mais ne bloque pas.|  
|[unlock](../Topic/critical_section::unlock%20Method.md)|Libère la section critique.|  
  
 \[[Premières](#top)\]  
  
##  <a name="reader_writer_lock"></a> reader\_writer\_lock  
 La classe [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) fournit des opérations en lecture\/écriture thread\-safe aux données partagées.  Utilisez des verrous de lecteur\/writer lorsque plusieurs threads requièrent un accès en lecture simultané à une ressource partagée mais écrivent rarement dans cette ressource partagée.  Cette classe accorde un accès en écriture à un objet à un seul thread à tout moment.  
  
 La classe `reader_writer_lock` peut offrir de meilleures performances que la classe `critical_section` car un objet `critical_section` acquiert l'accès exclusif à une ressource partagée, ce qui empêche l'accès en lecture simultané.  
  
 Comme la classe `critical_section`, la classe `reader_writer_lock` représente un objet d'exclusion mutuelle coopératif qui cède à d'autres tâches au lieu de les préempter.  
  
 Lorsqu'un thread qui doit écrire dans une ressource partagée acquiert un verrou de writer\/lecteur, les autres threads qui doivent également accéder à la ressource sont bloqués jusqu'à ce que le writer libère le verrou.  La classe `reader_writer_lock` est un exemple de verrou de *préférence d'écriture*, à savoir un verrou qui débloque les writers en attente avant de débloquer les lecteurs en attente.  
  
 Comme la classe `critical_section`, la classe `reader_writer_lock` est non réentrante.  Les méthodes [concurrency::reader\_writer\_lock::lock](../Topic/reader_writer_lock::lock%20Method.md) et [concurrency::reader\_writer\_lock::lock\_read](../Topic/reader_writer_lock::lock_read%20Method.md) lèvent une exception de type `improper_lock` si elles sont appelées par un thread qui détient déjà le verrou.  
  
> [!NOTE]
>  Étant donné que la classe `reader_writer_lock` est non réentrante, il n'est pas possible de mettre à niveau un verrou en lecture seule en un verrou lecture\/écriture, ni de rétrograder un verrou lecture\/écriture en un verrou en lecture seule.  L'exécution de l'une ou l'autre de ces opérations provoque un comportement inattendu.  
  
### Méthodes et fonctionnalités  
 Le tableau suivant répertorie les méthodes importantes définies par la classe `reader_writer_lock`.  
  
|Méthode|Description|  
|-------------|-----------------|  
|[verrouiller](../Topic/reader_writer_lock::lock%20Method.md)|Acquiert l'accès en lecture\/écriture au verrou.|  
|[try\_lock](../Topic/reader_writer_lock::try_lock%20Method.md)|Essaie d'acquérir l'accès en lecture\/écriture au verrou, mais ne bloque pas.|  
|[lock\_read](../Topic/reader_writer_lock::lock_read%20Method.md)|Acquiert l'accès en lecture seule au verrou.|  
|[try\_lock\_read](../Topic/reader_writer_lock::try_lock_read%20Method.md)|Essaie d'acquérir l'accès en lecture seule au verrou, mais ne bloque pas.|  
|[unlock](../Topic/reader_writer_lock::unlock%20Method.md)|Libère le verrou.|  
  
 \[[Premières](#top)\]  
  
##  <a name="scoped_lock"></a> scoped\_lock et scoped\_lock\_read  
 Les classes `reader_writer_lock` et `critical_section` fournissent des classes d'assistance imbriquées qui simplifient la façon dont vous utilisez les objets d'exclusion mutuelle.  Ces classes d'assistance portent le nom de *verrous à portée limitée*.  
  
 La classe `critical_section` contient la classe [concurrency::critical\_section::scoped\_lock](../Topic/critical_section::scoped_lock%20Class.md).  Le constructeur acquiert l'accès à l'objet `critical_section` fourni ; le destructeur libère l'accès à cet objet.  La classe `reader_writer_lock` contient la classe [concurrency::reader\_writer\_lock::scoped\_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md), qui s'apparente à `critical_section::scoped_lock` mais gère l'accès en écriture à l'objet `reader_writer_lock` fourni.  La classe `reader_writer_lock` contient également la classe [concurrency::reader\_writer\_lock::scoped\_lock\_read](../Topic/reader_writer_lock::scoped_lock_read%20Class.md).  Cette classe gère l'accès en lecture à l'objet `reader_writer_lock` fourni.  
  
 Les verrous à portée limitée procurent plusieurs avantages lorsque vous travaillez manuellement avec des objets `critical_section` et `reader_writer_lock`.  En général, vous allouez un verrou à portée limitée sur la pile.  Un verrou à portée limitée libère automatiquement l'accès à son objet d'exclusion mutuelle lorsqu'il est détruit ; par conséquent, vous ne déverrouillez pas l'objet sous\-jacent manuellement.  Ceci est utile lorsqu'une fonction contient plusieurs instructions `return`.  Les verrous à portée limitée peuvent également vous aider à écrire du code sécurisé du point de vue des exceptions.  Lorsqu'une instruction `throw` provoque le déroulement de la pile, le destructeur de tout verrou à portée limitée actif est appelé. Par conséquent, l'objet d'exclusion mutuelle est toujours libéré correctement.  
  
> [!NOTE]
>  Lorsque vous utilisez les classes `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock` et `reader_writer_lock::scoped_lock_read`, ne libérez pas manuellement l'accès à l'objet d'exclusion mutuelle sous\-jacent.  Cela peut mettre le runtime dans un état non valide.  
  
##  <a name="event"></a> event  
 La classe [concurrency::event](../../parallel/concrt/reference/event-class.md) représente un objet de synchronisation dont l'état peut être signalé ou non signalé.  Contrairement aux objets de synchronisation, tels que les sections critiques, dont l'objectif est de protéger l'accès aux données partagées, les événements synchronisent le flux d'exécution.  
  
 La classe `event` est utile lorsqu'une tâche a terminé du travail pour une autre tâche.  Par exemple, une tâche peut signaler à une autre tâche qu'elle a lu des données à partir d'une connexion réseau ou d'un fichier.  
  
### Méthodes et fonctionnalités  
 Le tableau suivant répertorie plusieurs des méthodes importantes définies par la classe `event`.  
  
|Méthode|Description|  
|-------------|-----------------|  
|[wait](../Topic/event::wait%20Method.md)|Attend que l'événement soit signalé.|  
|[set](../Topic/event::set%20Method.md)|Place l'événement à l'état signalé.|  
|[reset](../Topic/event::reset%20Method.md)|Place l'événement à l'état non signalé.|  
|[wait\_for\_multiple](../Topic/event::wait_for_multiple%20Method.md)|Attend que plusieurs événements soient signalés.|  
  
### Exemple  
 Pour obtenir un exemple qui illustre l'utilisation de la classe `event`, consultez [Comparaison des structures de données de synchronisation avec l’API Windows](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).  
  
 \[[Premières](#top)\]  
  
## Rubriques connexes  
 [Comparaison des structures de données de synchronisation avec l’API Windows](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)  
 Compare le comportement des structures de données de synchronisation à celles fournies par l'API Windows.  
  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)  
 Décrit le runtime d'accès concurrentiel, qui simplifie la programmation parallèle et contient des liens vers des rubriques connexes.