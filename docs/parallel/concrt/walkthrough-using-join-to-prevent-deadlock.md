---
title: "Proc&#233;dure pas &#224; pas&#160;: utilisation de la classe join pour emp&#234;cher l’interblocage | Microsoft Docs"
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
  - "empêcher l’interblocage avec des jointures [Runtime d’accès concurrentiel]"
  - "interblocage, empêcher [Runtime d’accès concurrentiel]"
  - "jointures non gourmandes, exemple"
  - "join, classe, exemple"
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Proc&#233;dure pas &#224; pas&#160;: utilisation de la classe join pour emp&#234;cher l’interblocage
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique utilise le problème du dîner de philosophes pour illustrer comment utiliser la classe [concurrency::join](../../parallel/concrt/reference/join-class.md) pour empêcher tout interblocage dans votre application.  Dans une application, l'*interblocage* se produit lorsque plusieurs processus détiennent chacun une ressource et attendent mutuellement qu'un autre processus libère une autre ressource.  
  
 Le problème du dîner de philosophes est un exemple spécifique de l'ensemble général de problèmes qui peuvent se produire lorsqu'un jeu de ressources est partagé par plusieurs processus simultanés.  
  
## Composants requis  
 Lisez les rubriques suivantes avant de démarrer cette procédure pas\-à\-pas :  
  
-   [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Procédure pas à pas : création d’une application basée sur un agent](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
  
-   [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md)  
  
-   [Structures de données de synchronisation](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> Sections  
 Cette procédure pas\-à\-pas contient les sections suivantes :  
  
-   [Le problème du dîner de philosophes](#problem)  
  
-   [Une implémentation naïve](#deadlock)  
  
-   [Utilisation de la jointure pour empêcher l'interblocage](#solution)  
  
##  <a name="problem"></a> Le problème du dîner de philosophes  
 Le problème du dîner de philosophes illustre comment l'interblocage se produit dans une application.  Dans ce problème, cinq philosophes sont assis à une table ronde.  Chaque philosophe pense et mange de manière alternée.  Chaque philosophe doit partager une baguette avec son voisin de gauche et une autre baguette avec son voisin de droite.  Voici une illustration.  
  
 ![Problème Dîner des philosophes](../../parallel/concrt/media/dining_philosophersproblem.png "Dining\_PhilosophersProblem")  
  
 Pour manger, un philosophe doit tenir deux baguettes.  Si chaque philosophe tient une seule baguette et en attend une autre, aucun philosophe ne peut manger et tous meurent de faim.  
  
 \[[Premières](#top)\]  
  
##  <a name="deadlock"></a> Une implémentation naïve  
 L'exemple suivant illustre une implémentation naïve du problème du dîner de philosophes.  La classe `philosopher`, qui dérive de [concurrency::agent](../../parallel/concrt/reference/agent-class.md), permet à chaque philosophe d'agir indépendamment.  L'exemple utilise un tableau partagé d'objets [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) pour accorder à chaque objet `philosopher` un accès exclusif à une paire de baguettes.  
  
 Pour comparer l'implémentation à l'illustration, la classe `philosopher` représente un philosophe.  Une variable `int` représente chaque baguette.  Les objets `critical_section` servent de supports sur lesquels reposent les baguettes.  La méthode `run` simule la vie du philosophe.  La méthode `think` simule l'acte de penser et la méthode `eat` simule l'acte de manger.  
  
 Un objet `philosopher` verrouille les deux objets `critical_section` pour simuler la suppression des baguettes des supports avant d'appeler la méthode `eat`.  Après l'appel à `eat`, l'objet `philosopher` repose les baguettes sur les supports en replaçant les objets `critical_section` à l'état déverrouillé.  
  
 La méthode `pickup_chopsticks` illustre où l'interblocage peut se produire.  Si chaque objet `philosopher` accède à l'un des verrous, aucun objet `philosopher` ne peut continuer car l'autre verrou est contrôlé par un autre objet `philosopher`.  
  
## Exemple  
  
### Description  
  
### Code  
 [!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_1.cpp)]  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `philosophers-deadlock.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc philosophers\-deadlock.cpp**  
  
 \[[Premières](#top)\]  
  
##  <a name="solution"></a> Utilisation de la jointure pour empêcher l'interblocage  
 Cette section indique comment utiliser des tampons de messages et des fonctions de passage de messages pour éliminer tout risque d'interblocage.  
  
 Pour comparer cet exemple au précédent, la classe `philosopher` remplace chaque objet `critical_section` à l'aide d'un objet [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) et d'un objet `join`.  L'objet `join` fait office d'arbitre qui fournit les baguettes au philosophe.  
  
 Cet exemple utilise la classe `unbounded_buffer` car quand une cible reçoit un message d'un objet `unbounded_buffer`, le message est supprimé de la file d'attente de messages.  Cela active un objet `unbounded_buffer` qui contient un message pour indiquer que la baguette est disponible.  Un objet `unbounded_buffer` qui ne contient aucun message indique que la baguette est utilisée.  
  
 Cet exemple utilise un objet `join` non gourmand car une jointure non gourmande accorde à chaque objet `philosopher` un accès aux deux baguettes uniquement lorsque les deux objets `unbounded_buffer` contiennent un message.  Une jointure gourmande n'empêcherait pas l'interblocage car elle accepte les messages dès qu'ils sont disponibles.  L'interblocage peut se produire si tous les objets `join` gourmands reçoivent l'un des messages mais attendent indéfiniment que l'autre soit disponible.  
  
 Pour plus d'informations sur les jointures gourmandes et non gourmandes et sur les différences entre les différents types de tampons de messages, consultez [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md).  
  
#### Pour empêcher l'interblocage dans cet exemple  
  
1.  Supprimez le code suivant de l'exemple.  
  
     [!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_2.cpp)]  
  
2.  Modifiez le type des membres de données `_right` et `_left` de la classe `philosopher` en `unbounded_buffer`.  
  
     [!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_3.cpp)]  
  
3.  Modifiez le constructeur `philosopher` de façon à prendre des objets `unbounded_buffer` comme paramètres.  
  
     [!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_4.cpp)]  
  
4.  Modifiez la méthode `pickup_chopsticks` de façon à utiliser un objet `join` non gourmand pour recevoir des messages en provenance des tampons de messages pour les deux baguettes.  
  
     [!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_5.cpp)]  
  
5.  Modifiez la méthode `putdown_chopsticks` de façon à libérer l'accès aux baguettes en envoyant un message aux tampons de messages pour les deux baguettes.  
  
     [!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_6.cpp)]  
  
6.  Modifiez la méthode `run` de façon à stocker les résultats de la méthode `pickup_chopsticks` et à passer ces résultats à la méthode `putdown_chopsticks`.  
  
     [!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_7.cpp)]  
  
7.  Modifiez la déclaration de la variable `chopsticks` dans la fonction `wmain` de sorte qu'elle soit un tableau d'objets `unbounded_buffer` contenant chacun un message.  
  
     [!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_8.cpp)]  
  
## Exemple  
  
### Description  
 Voici l'exemple complet qui utilise des objets `join` non gourmands pour éliminer le risque d'interblocage.  
  
### Code  
 [!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_9.cpp)]  
  
### Commentaires  
 Cet exemple génère la sortie suivante.  
  
  **Aristote a mangé 50 fois.**  
**Descartes a mangé 50 fois.**  
**les hobbes a mangé 50 fois.**  
**Socrates a mangé 50 fois.**  
**platon a mangé 50 fois.**   
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `philosophers-join.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc philosophers\-join.cpp**  
  
 \[[Premières](#top)\]  
  
## Voir aussi  
 [Procédures pas à pas relatives au runtime d'accès concurrentiel](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md)   
 [Structures de données de synchronisation](../../parallel/concrt/synchronization-data-structures.md)