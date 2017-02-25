---
title: "Comment&#160;: utiliser le surabonnement pour compenser la latence | Microsoft Docs"
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
  - "surabonnement, utiliser [runtime d’accès concurrentiel]"
  - "utiliser le surabonnement (runtime d'accès concurrentiel)"
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Comment&#160;: utiliser le surabonnement pour compenser la latence
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le surabonnement peut améliorer l'efficacité globale de certaines applications qui contiennent des tâches qui ont une quantité élevée de latence.  Cette rubrique illustre comment utiliser le surabonnement afin de compenser la latence provoquée par la lecture de données à partir d'une connexion réseau.  
  
## Exemple  
 Cet exemple utilise la [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) pour télécharger des fichiers à partir de serveurs HTTP.  La classe `http_reader` dérive de [concurrency::agent](../../parallel/concrt/reference/agent-class.md) et utilise le passage de message pour lire de façon asynchrone les noms des URL à télécharger.  
  
 La classe `http_reader` utilise la classe [concurrency::task\_group](../Topic/task_group%20Class.md) pour lire chaque fichier simultanément.  Chaque tâche appelle la méthode [concurrency::Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md) avec le paramètre `_BeginOversubscription` défini sur la valeur `true` pour permettre le surabonnement dans le contexte actuel.  Chaque tâche utilise ensuite les classes MFC \(Microsoft Foundation Classes\) [CInternetSession](../../mfc/reference/cinternetsession-class.md) et [CHttpFile](../../mfc/reference/chttpfile-class.md) pour télécharger le fichier.  Pour finir, chaque tâche appelle `Context::Oversubscribe` avec le paramètre `_BeginOversubscription` défini à `false` pour désactiver le surabonnement.  
  
 Lorsque le surabonnement est activé, le runtime crée un thread supplémentaire dans lequel exécuter des tâches.  Chacun de ces threads peut également surabonner le contexte actuel et ainsi créer des threads supplémentaires.  La classe `http_reader` utilise un objet [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) pour limiter le nombre de threads utilisés par l'application.  L'agent initialise la mémoire tampon avec un nombre fixe de valeurs de jeton.  Pour chaque opération de téléchargement, l'agent lit une valeur de jeton à partir de la mémoire tampon avant que l'opération démarre, puis réécrit cette valeur dans la mémoire tampon une fois l'opération terminée.  Lorsque la mémoire tampon est vide, l'agent attend que l'une des opérations de téléchargement réécrive une valeur dans la mémoire tampon.  
  
 L'exemple suivant limite le nombre de tâches simultanées à deux fois le nombre de threads matériels disponibles.  Cette valeur est un bon point de départ à utiliser en cas d'expérimentation avec le surabonnement.  Vous pouvez utiliser une valeur adaptée à un environnement de traitement particulier ou modifier cette valeur de manière dynamique afin de répondre à la charge de travail réelle.  
  
 [!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/CPP/how-to-use-oversubscription-to-offset-latency_1.cpp)]  
  
 Cet exemple produit la sortie suivante sur un ordinateur qui a quatre processeurs :  
  
  **Téléchargement depuis http:\/\/www.adatum.com\/...**  
**Téléchargement depuis http:\/\/www.adventure\-works.com\/...**  
**Téléchargement depuis http:\/\/www.alpineskihouse.com\/...**  
**Téléchargement depuis http:\/\/www.cpandl.com\/..**  
**Téléchargement depuis http:\/\/www.cohovineyard.com\/..**  
**Téléchargement depuis http:\/\/www.cohowinery.com\/..**  
**Téléchargement depuis http:\/\/www.cohovineyardandwinery.com\/..**  
**Téléchargement depuis http:\/\/www.contoso.com\/...**  
**Téléchargement depuis http:\/\/www.consolidatedmessenger.com\/..**  
**Téléchargement depuis http:\/\/www.fabrikam.com\/..**  
**Téléchargement depuis http:\/\/www.fourthcoffee.com\/..**  
**Téléchargement depuis http:\/\/www.graphicdesigninstitute.com\/..**  
**Téléchargement depuis http:\/\/www.humongousinsurance.com\/..**  
**Téléchargement depuis http:\/\/www.litwareinc.com\/..**  
**Téléchargement depuis http:\/\/www.lucernepublishing.com\/..**  
**Téléchargement depuis http:\/\/www.margiestravel.com\/..**  
**Téléchargement depuis http:\/\/www.northwindtraders.com\/..**  
**Téléchargement depuis http:\/\/www.proseware.com\/..**  
**Téléchargement depuis http:\/\/www.fineartschool.net..**  
**Téléchargement depuis http:\/\/www.tailspintoys.com\/..**  
**1801040 Octets téléchargés en 3276 ms.** L'exemple peut s'exécuter plus rapidement lorsque le surabonnement est activé car des tâches supplémentaires s'exécutent pendant que d'autres tâches attendent qu'une opération latente se termine.  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `download-oversubscription.cpp` puis exécutez l'une des commandes suivantes dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc \/MD \/D "\_AFXDLL" download\-oversubscription.cpp**  
  
 **cl.exe \/EHsc \/MT download\-oversubscription.cpp**  
  
## Programmation fiable  
 Désactivez toujours le surabonnement une fois que vous n'en avez plus besoin.  Considérez une fonction qui ne gère pas une exception levée par une autre fonction.  Si vous ne désactivez pas le surabonnement avant que la fonction ne retourne, tout travail parallèle supplémentaire surabonnera également le contexte actuel.  
  
 Vous pouvez utiliser le modèle RAII \(*Resource Acquisition Is Initialization*\) pour limiter le surabonnement à une portée donnée.  Selon le modèle RAII, une structure de données est allouée sur la pile.  Cette structure de données initialise ou acquiert une ressource lorsqu'elle est créée et détruit ou libère cette ressource lorsque la structure de données est détruite.  Le modèle RAII garantit que le destructeur est appelé avant que la portée englobante ne quitte.  Par conséquent, la ressource est gérée correctement lorsqu'une exception est levée ou lorsqu'une fonction contient plusieurs instructions `return`.  
  
 L'exemple suivant définit une structure nommée `scoped_blocking_signal`.  Le constructeur de la structure `scoped_blocking_signal` active le surabonnement et le destructeur désactive le surabonnement.  
  
 [!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/CPP/how-to-use-oversubscription-to-offset-latency_2.cpp)]  
  
 L'exemple suivant modifie le corps de la méthode `download` de façon à utiliser RAII pour s'assurer que le surabonnement est désactivé avant que la fonction ne soit retournée.  Cette technique garantit que la méthode `download` est sécurisée du point de vue des exceptions.  
  
 [!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/CPP/how-to-use-oversubscription-to-offset-latency_3.cpp)]  
  
## Voir aussi  
 [Contextes](../../parallel/concrt/contexts.md)   
 [Context::Oversubscribe, méthode](../Topic/Context::Oversubscribe%20Method.md)