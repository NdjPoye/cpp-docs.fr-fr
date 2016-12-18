---
title: "Comment&#160;: impl&#233;menter divers mod&#232;les de producteur-consommateur | Microsoft Docs"
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
  - "modèles de producteur-consommateur, implémenter [runtime d’accès concurrentiel]"
  - "implémenter des modèles de producteur-consommateur (runtime d'accès concurrentiel)"
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
caps.latest.revision: 17
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: impl&#233;menter divers mod&#232;les de producteur-consommateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit comment implémenter le modèle de producteur\-consommateur dans votre application.  Dans ce modèle, le *producteur* envoie des messages à un bloc de messages et le *consommateur* lit les messages à partir de ce bloc.  
  
 La rubrique illustre deux scénarios.  Dans le premier scénario, le consommateur doit recevoir chaque message envoyé par le producteur.  Dans le deuxième scénario, le consommateur vérifie périodiquement la présence de données, et par conséquent n'est pas obligé de recevoir chaque message.  
  
 Les deux exemples de cette rubrique utilisent des agents, des blocs de messages et des fonctions de passage de messages pour transmettre les messages du producteur au consommateur.  L'agent producteur utilise la fonction [concurrency::send](../Topic/send%20Function.md) pour écrire des messages sur un objet [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md).  L'agent du consommateur utilise la fonction [concurrency::receive](../Topic/receive%20Function.md) pour lire les messages d'un objet [concurrency::ISource](../../parallel/concrt/reference/isource-class.md).  Les deux agents conservent une valeur de sentinelle pour coordonner la fin du traitement.  
  
 Pour plus d'informations sur les agents asynchrones, consultez [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md).  Pour plus d'informations sur les blocs de messages et les fonctions de passage de messages, consultez [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md) et [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md).  
  
## Exemple  
 Dans cet exemple, le agent producteur envoie une série de nombres à l'agent consommateur.  Le consommateur reçoit chacun de ces nombres et calcule leur moyenne.  L'application écrit la moyenne dans la console.  
  
 Cet exemple utilise un objet [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) pour permettre au producteur de mettre les messages en file d'attente.  La classe `unbounded_buffer` implémente `ITarget` et `ISource` afin que le producteur et le consommateur puissent envoyer et recevoir des messages vers et à partir d'une mémoire tampon partagée.  Les fonctions `receive` et `send` coordonnent la tâche de propagation des données du producteur au consommateur.  
  
 [!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/CPP/how-to-implement-various-producer-consumer-patterns_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **La moyenne est 50.**   
## Exemple  
 Dans cet exemple, l'agent producteur envoie une série de cotations boursières à l'agent consommateur.  L'agent consommateur lit périodiquement la cotation actuelle et l'imprime sur la console.  
  
 Cet exemple ressemble au précédent, mais il utilise un objet [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) pour permettre au producteur de partager un message avec le consommateur.  Comme dans l'exemple précédent, la classe `overwrite_buffer` implémente `ITarget` et `ISource` afin que le producteur et le consommateur puissent agir sur un tampon de messages partagé.  
  
 [!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/CPP/how-to-implement-various-producer-consumer-patterns_2.cpp)]  
  
 Cet exemple génère l'exemple de sortie suivant.  
  
  **L'estimation actuelle est 24,44.**  
**L'estimation actuelle est 24,44.**  
**L'estimation actuelle est 24,65.**  
**L'estimation actuelle est 24,99.**  
**L'estimation actuelle est 23,76.**  
**L'estimation actuelle est 22,30.**  
**L'estimation actuelle est 25,89.** Contrairement à ce qui se produit avec un objet `unbounded_buffer`, la fonction `receive` ne supprime pas le message de l'objet `overwrite_buffer`.  Si le consommateur lit à partir du tampon de messages à plusieurs reprises avant que le producteur ne remplace ce message, le récepteur obtient le même message à chaque fois.  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio, ou collez\-le dans un fichier nommé `producer-consumer.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc producer\-consumer.cpp**  
  
## Voir aussi  
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md)