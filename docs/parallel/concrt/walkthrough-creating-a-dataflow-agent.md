---
title: "Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation des agents de flux de donn&#233;es | Microsoft Docs"
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
  - "créer des agents de flux de données [Runtime d’accès concurrentiel]"
  - "agents de flux de données, créer [Runtime d’accès concurrentiel]"
ms.assetid: 9db5ce3f-c51b-4de1-b79b-9ac2a0cbd130
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation des agents de flux de donn&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document montre comment créer des applications basées sur agent selon le flux de données, plutôt que selon le flux de contrôle.  
  
 Le *flux de contrôle* fait référence à l'ordre d'exécution des opérations dans un programme.  Le flux de contrôle est régulé à l'aide de structures de contrôle, telles que des instructions conditionnelles, des boucles, etc.  Par ailleurs, le *flux de données* fait référence à un modèle de programmation où les calculs sont effectués uniquement lorsque toutes les données requises sont disponibles.  Le modèle de programmation de flux de données est lié au concept de passage de message, dans lequel les composants indépendants d'un programme communiquent les uns avec les autres en envoyant des messages.  
  
 Les agents asynchrones prennent en charge les modèles de programmation de flux de contrôle et de flux de données.  Bien que le modèle de flux de contrôle soit approprié dans de nombreux cas, le modèle de flux de données est approprié dans d'autres cas, par exemple lorsqu'un agent reçoit des données et effectue une action basée sur la charge de ces données.  
  
## Composants requis  
 Lisez les documents suivants avant de démarrer cette procédure pas\-à\-pas :  
  
-   [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Comment : utiliser un filtre de bloc de message](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
##  <a name="top"></a> Sections  
 Cette procédure pas\-à\-pas contient les sections suivantes :  
  
-   [Création d'un agent de flux de contrôle de base](#control-flow)  
  
-   [Création d'un agent de flux de données de base](#dataflow)  
  
-   [Création d'un agent d'enregistrement des messages](#logging)  
  
##  <a name="control-flow"></a> Création d'un agent de flux de contrôle de base  
 Prenons l'exemple suivant, qui définit la classe `control_flow_agent`.  La classe `control_flow_agent` agit sur trois mémoires tampons de messages : une mémoire tampon d'entrée et deux mémoires tampons de sortie.  La méthode `run` lit à partir de la mémoire tampon de messages source dans une boucle et utilise une instruction conditionnelle pour diriger le flux d'exécution du programme.  L'agent incrémente un compteur pour les valeurs négatives différentes de zéro et incrémente un autre compteur pour les valeurs positives différentes de zéro.  Lorsque l'agent reçoit la valeur de sentinelle zéro, il envoie les valeurs des compteurs aux mémoires tampons de messages de sortie.  Les méthodes `negatives` et `positives` permettent à l'application de lire le nombre de valeurs positives et négatives à partir de l'agent.  
  
 [!code-cpp[concrt-dataflow-agent#1](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-dataflow-agent_1.cpp)]  
  
 Bien que cet exemple utilise le flux de contrôle dans un agent de façon élémentaire, il montre que la programmation basée sur le contrôle de flux est de nature consécutive.  Chaque message doit être traité de façon séquentielle, même si plusieurs messages peuvent être disponibles dans la mémoire tampon des messages d'entrée.  Le modèle de flux de données permet aux deux branches de l'instruction conditionnelle de procéder à une évaluation simultanément.  Le modèle de flux de données vous permet également de créer des réseaux de messagerie plus complexes, qui agissent sur les données à mesure qu'elles deviennent disponibles.  
  
 \[[Premières](#top)\]  
  
##  <a name="dataflow"></a> Création d'un agent de flux de données de base  
 Cette section indique comment convertir la classe `control_flow_agent` afin d'utiliser le modèle de flux de données pour effectuer la même tâche.  
  
 L'agent de flux de données repose sur la création d'un réseau de mémoires tampons de messages, chaque réseau répondant à des besoins précis.  Certains blocs de messages utilisent une fonction de filtre pour accepter ou rejeter un message en fonction de sa charge.  Une fonction de filtre permet de vérifier qu'un bloc de message ne reçoit que certaines valeurs.  
  
#### Pour convertir l'agent de flux de contrôle en agent de flux de données  
  
1.  Copiez le corps de la classe `control_flow_agent` vers une autre classe, par exemple, `dataflow_agent`.  Vous pouvez également renommer la classe `control_flow_agent`.  
  
2.  Supprimez le corps de la boucle qui appelle `receive` à partir de la méthode `run`.  
  
     [!code-cpp[concrt-dataflow-agent#2](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-dataflow-agent_2.cpp)]  
  
3.  Dans la méthode `run`, après l'initialisation des variables `negative_count` et `positive_count`, ajoutez un objet `countdown_event` qui assure le suivi du nombre d'opérations actives.  
  
     [!code-cpp[concrt-dataflow-agent#6](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-dataflow-agent_3.cpp)]  
  
     La classe `countdown_event` est illustrée plus loin dans cette rubrique.  
  
4.  Créez les objets de la mémoire tampon des messages qui participeront au réseau du flux de données.  
  
     [!code-cpp[concrt-dataflow-agent#3](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-dataflow-agent_4.cpp)]  
  
5.  Connectez les mémoires tampons des messages pour former un réseau.  
  
     [!code-cpp[concrt-dataflow-agent#4](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-dataflow-agent_5.cpp)]  
  
6.  Attendez que les objets `event` et `countdown event` soient définis.  Ces événements signalent que l'agent a reçu la valeur de sentinelle et que toutes les opérations sont terminées.  
  
     [!code-cpp[concrt-dataflow-agent#5](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-dataflow-agent_6.cpp)]  
  
 Le schéma suivant illustre le réseau de flux de données complet pour la classe `dataflow_agent` :  
  
 ![Le réseau de flux de données](../../parallel/concrt/media/concrt_dataflow.png "ConcRT\_Dataflow")  
  
 Le tableau suivant décrit les membres du réseau.  
  
|Membre|Description|  
|------------|-----------------|  
|`increment_active`|Objet [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) qui incrémente le compteur d'événements actifs et passe la valeur d'entrée au reste du réseau.|  
|`negatives`, `positives`|Objets [concurrency::call](../../parallel/concrt/reference/call-class.md) qui incrémentent le nombre de nombres et décrémente le compteur d'événements actifs.  Chaque objet utilise un filtre pour accepter des nombres négatifs ou des nombres positifs.|  
|`sentinel`|Objet [concurrency::call](../../parallel/concrt/reference/call-class.md) qui accepte uniquement la valeur sentinelle zéro et décrémente le compteur d'événements actifs.|  
|`connector`|Objet [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) qui connecte la mémoire tampon des messages sources au réseau interne.|  
  
 Étant donné que la méthode `run` est appelée sur un thread séparé, d'autres threads peuvent envoyer des messages au réseau avant que le réseau soit entièrement connecté.  Le membre de données `_source` est un objet `unbounded_buffer` qui met en mémoire tampon toute entrée envoyée de l'application à l'agent.  Pour s'assurer que le réseau traite tous les messages d'entrée, l'agent commence par associer les nœuds internes du réseau, puis associe le début de ce réseau, `connector`, au membre de données `_source`.  Vous êtes ainsi certain que les messages ne sont pas traités pendant la formation du réseau.  
  
 Étant donné que, dans cet exemple, le réseau est basé sur le flux de données, et non pas sur le flux de contrôle, le réseau doit informer l'agent lorsqu'il a terminé de traiter chaque valeur d'entrée et que le nœud de sentinelle a reçu sa valeur.  Cet exemple utilise un objet `countdown_event` pour signaler que toutes les valeurs d'entrée ont été traitées et un objet [concurrency::event](../../parallel/concrt/reference/event-class.md) pour indiquer que le nœud de sentinelle a reçu sa valeur.  La classe `countdown_event` utilise un objet `event` pour signaler qu'une valeur de compteur atteint zéro.  Le début du réseau de flux de données incrémente le compteur chaque fois qu'il reçoit une valeur.  Chaque nœud de terminaison du réseau décrémente le compteur après qu'il ait traité la valeur d'entrée.  Une fois que l'agent a formé le réseau de flux de données, il attend que le nœud de sentinelle définisse l'objet `event` et que l'objet `countdown_event` signale que son compteur a atteint zéro.  
  
 L'exemple suivant illustre les classes `control_flow_agent`, `dataflow_agent` et `countdown_event`.  La fonction `wmain` crée un objet `control_flow_agent` et un objet `dataflow_agent`, et utilise la fonction `send_values` pour envoyer une série de valeurs aléatoires aux agents.  
  
 [!code-cpp[concrt-dataflow-agent#7](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-dataflow-agent_7.cpp)]  
  
 Cet exemple génère l'exemple de sortie suivant :  
  
  **Agent de flux de contrôle :**  
**Il existe 500523 nombres négatifs.**  
**Il existe 499477 nombres positifs.**  
**agent de flux de données :**  
**Il existe 500523 nombres négatifs.**  
**Il existe 499477 nombres positifs.**   
### Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio  ou dans un fichier nommé dataflow\-agent.cpp, puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc dataflow\-agent.cpp**  
  
 \[[Premières](#top)\]  
  
##  <a name="logging"></a> Création d'un agent d'enregistrement des messages  
 L'exemple suivant illustre la classe `log_agent`, qui s'apparente à la classe `dataflow_agent`.  La classe `log_agent` implémente un agent d'enregistrement asynchrone qui écrit des messages d'enregistrement dans un fichier et dans la console.  La classe `log_agent` permet à l'application de classer les messages en tant que messages d'information, d'avertissement ou d'erreur.  Elle permet également à l'application de spécifier si chaque catégorie d'enregistrement est écrite dans un fichier, dans la console ou dans les deux.  Cet exemple écrit tous les messages d'enregistrement dans un fichier et écrit uniquement les messages d'erreur dans la console.  
  
 [!code-cpp[concrt-log-filter#1](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-dataflow-agent_8.cpp)]  
  
 Cet exemple écrit la sortie suivante dans la console.  
  
  **erreur : Ceci est un message d'erreur témoin.** Cet exemple génère également le fichier log.txt, qui contient le texte suivant.  
  
  **info : \=\=\=connection lancée\=\=\=**  
**avertissement : ceci est message d'avertissement témoin.**  
**erreur : Ceci est un message d'erreur témoin.**  
**les informations : \=\=\=connection terminée \=\=\=**   
### Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio  ou dans un fichier nommé log\-filter.cpp, puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc log\-filter.cpp**  
  
 \[[Premières](#top)\]  
  
## Voir aussi  
 [Procédures pas à pas relatives au runtime d'accès concurrentiel](../../parallel/concrt/concurrency-runtime-walkthroughs.md)