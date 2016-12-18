---
title: "Proc&#233;dures pas &#224; pas relatives au runtime d&#39;acc&#232;s concurrentiel | Microsoft Docs"
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
  - "Concurrency Runtime, procédures pas à pas"
  - "procédures pas à pas (runtime d'accès concurrentiel)"
ms.assetid: 7374c5e9-54eb-44bf-9ed9-5e190cfd290b
caps.latest.revision: 14
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dures pas &#224; pas relatives au runtime d&#39;acc&#232;s concurrentiel
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans cette section, les rubriques basées sur des scénarios indiquent comment utiliser de nombreuses fonctionnalités du runtime d'accès concurrentiel.  
  
## Dans cette section  
 [Procédure pas à pas : connexion à l’aide de tâches et de requêtes HTTP XML](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
 Montre comment utiliser les interfaces [IXMLHTTPRequest2](http://msdn.microsoft.com/fr-fr/bbc11c4a-aecf-4d6d-8275-3e852e309908) et [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/fr-fr/aa4b3f4c-6e28-458b-be25-6cce8865fc71) avec des tâches envoyant des requêtes HTTP GET et POST à un service Web dans une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  
  
 [Procédure pas à pas : création d’une application basée sur un agent](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
 Indique comment créer une application de base basée sur agent.  
  
 [Procédure pas à pas : création des agents de flux de données](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)  
 Montre comment créer des applications basées sur agent selon le flux de données, plutôt que selon le flux de contrôle.  
  
 [Procédure pas à pas : création d'un réseau de traitement d'image](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)  
 Montre comment créer un réseau des blocs de messages asynchrones qui effectuent le traitement d'image.  
  
 [Procédure pas à pas : implémentation d’objets future](../../parallel/concrt/walkthrough-implementing-futures.md)  
 Indique comment calculer des valeurs de façon asynchrone pour une utilisation ultérieure.  
  
 [Procédure pas à pas : utilisation de la classe join pour empêcher l’interblocage](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)  
 Utilise le problème du dîner de philosophes pour illustrer comment utiliser la classe [concurrency::join](../../parallel/concrt/reference/join-class.md) pour empêcher tout interblocage dans votre application.  
  
 [Procédure pas à pas : suppression de travail d'un thread d'interface utilisateur](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)  
 Montre comment améliorer les performances d'une application MFC qui dessine une fractale de Mandelbrot.  
  
 [Procédure pas à pas : utilisation du runtime d'accès concurrentiel routage dans une application COM](../../parallel/concrt/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application.md)  
 Montre comment utiliser le runtime d'accès concurrentiel dans une application qui utilise le Modèle COM.  
  
 [Procédure pas à pas : adaptation d’un code existant pour l’utilisation de tâches légères](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)  
 Indique comment adapter du code existant qui utilise l'API Windows pour créer et exécuter un thread de façon à utiliser une tâche légère.  
  
 [Procédure pas à pas : création d'un bloc de message personnalisé](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)  
 Décrit comment créer un type de bloc de message personnalisé qui classe les messages entrants par priorité.  
  
## Rubriques connexes  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)  
 Présente l'infrastructure de programmation simultanée pour Visual C\+\+.