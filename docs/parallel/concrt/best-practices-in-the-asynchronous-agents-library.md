---
title: "meilleures pratiques pour la biblioth&#232;que d’agents asynchrones | Microsoft Docs"
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
  - "meilleures pratiques, bibliothèque d’agents asynchrones"
  - "bibliothèque d’agents asynchrones, meilleure pratiques"
  - "bibliothèque d’agents asynchrones, pratiques à éviter"
  - "pratiques à éviter, bibliothèque d’agents asynchrones"
ms.assetid: 85f52354-41eb-4b0d-98c5-f7344ee8a8cf
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# meilleures pratiques pour la biblioth&#232;que d’agents asynchrones
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit comment tirer le meilleur parti de la bibliothèque d'agents asynchrones.  La bibliothèque d'agents fournit un modèle de programmation basé sur acteur et un passage de messages in\-process pour les tâches de traitement « pipeline » et de flux de données de granularité grossière.  
  
 Pour plus d'informations sur la Bibliothèque d'agents, consultez [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md).  
  
##  <a name="top"></a> Sections  
 Ce document contient les sections suivantes :  
  
-   [Utiliser des agents pour isoler l'état](#isolation)  
  
-   [Utiliser un mécanisme de limitation pour restreindre le nombre de messages dans un pipeline de données](#throttling)  
  
-   [Ne pas exécuter de travail de granularité fine dans un pipeline de données](#fine-grained)  
  
-   [Ne pas passer de charges de messages volumineux par valeur](#large-payloads)  
  
-   [Utiliser shared\_ptr dans un réseau de données lorsque la propriété n'est pas définie](#ownership)  
  
##  <a name="isolation"></a> Utiliser des agents pour isoler l'état  
 La bibliothèque d'agents fournit des alternatives à l'état partagé en vous permettant de connecter des composants isolés via un mécanisme asynchrone de passage de message.  Les agents asynchrones sont les plus efficaces lorsqu'il s'agit d'isoler leur état interne d'autres composants.  Lorsque l'état est isolé, plusieurs composants ne traitent généralement pas les données partagées.  L'isolation d'état peut permettre à votre application d'être mise à l'échelle, car elle réduit les conflits sur la mémoire partagée.  L'isolation d'état réduit également le risque d'interblocage et les conditions de concurrence, étant donné que les composants ne doivent pas synchroniser l'accès aux données partagées.  
  
 En général, vous isolez l'état dans un agent en maintenant les membres de données dans les sections `private` ou `protected` de la classe d'agent et en utilisant des mémoires tampons de messages pour communiquer les changements d'état.  L'exemple suivant montre la classe `basic_agent`, qui dérive de [concurrency::agent](../../parallel/concrt/reference/agent-class.md).  La classe `basic_agent` utilise deux mémoires tampons de messages pour communiquer avec les composants externes.  Une mémoire tampon de messages contient les messages entrants. L'autre mémoire tampon de messages contient les messages sortants.  
  
 [!code-cpp[concrt-simple-agent#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-asynchronous-agents-library_1.cpp)]  
  
 Pour obtenir des exemples sur la définition et l'utilisation des agents, consultez [Procédure pas à pas : création d’une application basée sur un agent](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md) et [Procédure pas à pas : création des agents de flux de données](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="throttling"></a> Utiliser un mécanisme de limitation pour restreindre le nombre de messages dans un pipeline de données  
 De nombreux types de mémoires tampons de messages, tel que [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md), peuvent contenir un nombre illimité de messages.  Lorsqu'un producteur de message envoie des messages à un pipeline de données en moins de temps qu'il n'en faut au consommateur pour les traiter, la mémoire de l'application peut s'avérer insuffisante ou faible.  Vous pouvez utiliser un mécanisme de limitation, par exemple, un sémaphore, pour restreindre le nombre de messages actifs simultanément dans un pipeline de données.  
  
 L'exemple de base suivant montre comment utiliser un sémaphore pour restreindre le nombre de messages dans un pipeline de données.  Le pipeline de données utilise la fonction [concurrency::wait](../Topic/wait%20Function.md) pour simuler une opération qui dure au moins 100 millisecondes.  Étant donné que l'expéditeur produit des messages en moins de temps qu'il n'en faut au consommateur pour les traiter, cet exemple définit la classe `semaphore` pour permettre à l'application de restreindre le nombre de messages actifs.  
  
 [!code-cpp[concrt-message-throttling#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-asynchronous-agents-library_2.cpp)]  
  
 L'objet `semaphore` restreint le pipeline à traiter à deux messages simultanés maximum.  
  
 Dans cet exemple, le producteur envoie relativement peu de messages au consommateur.  Par conséquent, cet exemple ne présente pas une mémoire faible ou insuffisante.  Toutefois, ce mécanisme est utile lorsqu'un pipeline de données contient un nombre de messages relativement élevé.  
  
 Pour plus d'informations sur la création de la classe de sémaphore utilisée dans cet exemple, consultez [Comment : utiliser la classe Context pour implémenter un sémaphore coopératif](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="fine-grained"></a> Ne pas exécuter de travail de granularité fine dans un pipeline de données  
 La bibliothèque d'agents est très utile lorsque la granularité du travail exécuté par un pipeline de données est plutôt grossière.  Par exemple, un composant d'application peut lire des données à partir d'un fichier ou d'une connexion réseau et envoyer de temps en temps cet élément vers un autre composant.  Le protocole utilisé par la bibliothèque d'agents pour propager les messages provoque une surcharge du mécanisme de passage de message plus importante que celle des éléments de tâche parallèles fournis par la [bibliothèque de modèles parallèles](../../parallel/concrt/parallel-patterns-library-ppl.md).  Par conséquent, vous devez vous assurer que le travail effectué par un pipeline de données dure assez longtemps pour compenser cette surcharge.  
  
 Bien qu'un pipeline de données soit plus efficace lorsque la granularité de ses tâches est grossière, chaque étape du pipeline de données peut utiliser des éléments de la bibliothèque de modèles parallèles, tels que les groupes de tâches et les algorithmes parallèles, pour effectuer un travail de granularité plus fine.  Pour obtenir un exemple de réseau de données de granularité grossière qui utilise un parallélisme de granularité fine à chaque étape de traitement, consultez [Procédure pas à pas : création d'un réseau de traitement d'image](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 \[[Premières](#top)\]  
  
##  <a name="large-payloads"></a> Ne pas passer de charges de messages volumineux par valeur  
 Dans certains cas, le runtime crée une copie de chaque message qu'il passe d'une mémoire tampon de messages à une autre mémoire tampon de messages.  Par exemple, la classe [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) offre une copie de chaque message qu'elle reçoit à chacune de ses cibles.  Le runtime crée également une copie des données du message lorsque vous utilisez des fonctions de passage de messages, telles que [concurrency::send](../Topic/send%20Function.md) et [concurrency::receive](../Topic/receive%20Function.md) pour écrire des messages dans un tampon de message et pour lire des messages provenant d'une mémoire tampon de messages.  Bien que ce mécanisme permette d'éliminer le risque d'écrire simultanément sur des données partagées, il peut détériorer les performances de la mémoire lorsque la charge de message est relativement importante.  
  
 Vous pouvez utiliser des pointeurs ou des références pour améliorer les performances de la mémoire lorsque vous passez des messages dont la charge est importante.  L'exemple suivant compare le passage par valeur de messages importants au passage de pointeurs vers le même type de message.  L'exemple définit deux types d'agent, `producer` et `consumer`, qui agissent sur les objets `message_data`.  L'exemple compare le temps nécessaire pour que le producteur envoie plusieurs objets `message_data` au consommateur au temps nécessaire pour que l'agent producteur envoie plusieurs pointeurs vers des objets `message_data` au consommateur.  
  
 [!code-cpp[concrt-message-payloads#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-asynchronous-agents-library_3.cpp)]  
  
 Cet exemple génère l'exemple de sortie suivant :  
  
  **Utilisation de message\_data…**  
**a pris 437ms.**  
**Utilisation de message\_data\*…**  
**a pris 47ms.** La version qui utilise des pointeurs est plus performante, car elle n'exige pas que le runtime crée une copie complète de chaque objet `message_data` passé du producteur au consommateur.  
  
 \[[Premières](#top)\]  
  
##  <a name="ownership"></a> Utiliser shared\_ptr dans un réseau de données lorsque la propriété n'est pas définie  
 Lorsque vous envoyez un message par le pointeur via un pipeline ou un réseau de passage de message, vous allouez en général de la mémoire pour chaque message à l'avant du réseau et vous libérez de la mémoire à l'arrière du réseau.  Bien que ce mécanisme fonctionne habituellement correctement, il est difficile ou impossible de l'utiliser dans certains cas.  Envisagez le cas où le réseau de données contient plusieurs nœuds de fin.  Dans ce cas, il n'existe aucun emplacement évident pour libérer de la mémoire pour les messages.  
  
 Pour résoudre ce problème, vous pouvez utiliser un mécanisme, par exemple, [std::shared\_ptr](../../standard-library/shared-ptr-class.md), qui permet à un pointeur d'être partagé par plusieurs composants.  Lorsque l'objet final `shared_ptr` qui possède une ressource est détruit, la ressource est également libérée.  
  
 L'exemple suivant illustre l'utilisation de `shared_ptr` pour partager des valeurs de pointeur entre plusieurs mémoires tampons de messages.  L'exemple connecte un objet [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) à trois objets [concurrency::call](../../parallel/concrt/reference/call-class.md).  La classe `overwrite_buffer` offre des messages à chacune de ses cibles.  Étant donné qu'il existe plusieurs propriétaires pour les données à l'arrière du réseau de données, cet exemple utilise `shared_ptr` pour permettre à chaque objet `call` de partager la propriété des messages.  
  
 [!code-cpp[concrt-message-sharing#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-asynchronous-agents-library_4.cpp)]  
  
 Cet exemple génère l'exemple de sortie suivant :  
  
  **Création de la ressource 42...**  
**receiver1: ressource 42 reçue**  
**Création de la resource 64...**  
**receiver2: ressource 42 reçue**  
**receiver1: ressource 64 reçue**  
**Ressource de destruction 42…**  
**receiver2: ressource 64 reçue**  
**Ressource de destruction 64…**   
## Voir aussi  
 [Meilleures pratiques sur le runtime d'accès concurrentiel](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Procédure pas à pas : création d’une application basée sur un agent](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)   
 [Procédure pas à pas : création des agents de flux de données](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [Procédure pas à pas : création d'un réseau de traitement d'image](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [Meilleures pratiques de la Bibliothèque de modèles parallèles](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [Meilleures pratiques en général du runtime d’accès concurrentiel](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)