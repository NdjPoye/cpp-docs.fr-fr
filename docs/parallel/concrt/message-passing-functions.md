---
title: "Fonctions de passage de messages | Microsoft Docs"
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
  - "fonctions de passage de messages"
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
caps.latest.revision: 23
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions de passage de messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La Bibliothèque d'agents asynchrones fournit plusieurs fonctions qui vous permettent de passer des messages parmi des composants.  
  
 Ces fonctions de passage de messages sont utilisées avec les différents types de blocs de messages.  Pour plus d'informations sur les types de blocs de messages définis par le runtime d'accès concurrentiel, consultez [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md).  
  
##  <a name="top"></a> Sections  
 Cette rubrique décrit les fonctions de passage de messages suivantes :  
  
-   [send et asend](#send)  
  
-   [receive et try\_receive](#receive)  
  
-   [Exemples](#examples)  
  
##  <a name="send"></a> send et asend  
 The [concurrency::send](../Topic/send%20Function.md) function sends a message to the specified target synchronously and the [concurrency::asend](../Topic/asend%20Function.md) function sends a message to the specified target asynchronously.  Les fonctions `send` et `asend` attendent toutes deux que la cible indique qu'elle accepte ou refuse le message.  
  
 La fonction `send` attend que la cible accepte ou refuse le message avant de retourner.  La fonction `send` retourne `true` si le message a été remis et `false` dans le cas contraire.  Étant donné que la fonction `send` opère de façon synchrone, la fonction `send` attend que la cible reçoive le message avant de retourner.  
  
 En revanche, la fonction `asend` n'attend pas que la cible accepte ou refuse le message avant de retourner une valeur.  Au lieu de cela, la fonction `asend` retourne la valeur `true` si la cible accepte le message et le prendra finalement.  Sinon, `asend` retourne la valeur `false` pour indiquer que la cible a refusé le message ou différé la décision relative à la prise du message.  
  
 \[[Premières](#top)\]  
  
##  <a name="receive"></a> receive et try\_receive  
 The [concurrency::receive](../Topic/receive%20Function.md) and [concurrency::try\_receive](../Topic/try_receive%20Function.md) functions read data from a given source.  La fonction `receive` attend que les données deviennent disponibles, tandis que la fonction `try_receive` retourne immédiatement.  
  
 Utilisez la fonction `receive` lorsque vous devez avoir les données pour continuer.  Utilisez la fonction `try_receive` si vous ne devez pas bloquer le contexte actuel ou si vous n'êtes pas obligé d'avoir les données pour continuer.  
  
 \[[Premières](#top)\]  
  
##  <a name="examples"></a> Exemples  
 Pour obtenir des exemples qui utilisent les fonctions `send`, `asend` et `receive`, consultez les rubriques suivantes :  
  
-   [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Comment : implémenter divers modèles de producteur\-consommateur](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [Comment : fournir des fonctions de travail aux classes call et transformer](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [Comment : utiliser la classe transformer dans un pipeline de données](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [Comment : effectuer une sélection parmi les tâches terminées](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [Comment : envoyer un message à intervalles réguliers](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [Comment : utiliser un filtre de bloc de message](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 \[[Premières](#top)\]  
  
## Voir aussi  
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [send, fonction](../Topic/send%20Function.md)   
 [asend, fonction](../Topic/asend%20Function.md)   
 [receive, fonction](../Topic/receive%20Function.md)   
 [try\_receive, fonction](../Topic/try_receive%20Function.md)