---
title: "Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d’une application bas&#233;e sur un agent | Microsoft Docs"
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
  - "agents asynchrones, création"
  - "agent, classe, exemple"
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
caps.latest.revision: 24
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d’une application bas&#233;e sur un agent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit comment créer une application de base basée sur agent.  Dans cette procédure pas à pas, vous pouvez créer un agent qui lit de façon asynchrone des données à partir d'un fichier texte.  L'application utilise l'algorithme de somme de contrôle Adler\-32 pour calculer la somme de contrôle du contenu de ce fichier.  
  
## Composants requis  
 Vous devez comprendre les sujets suivants afin d'effectuer cette procédure pas\-à\-pas :  
  
-   [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md)  
  
-   [Structures de données de synchronisation](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> Sections  
 Cette procédure pas\-à\-pas explique comment effectuer les tâches suivantes :  
  
-   [Création de l'application console](#createApplication)  
  
-   [Création de la classe file\_reader](#createAgentClass)  
  
-   [Utilisation de la classe file\_reader dans l'application](#useAgentClass)  
  
##  <a name="createApplication"></a> Création de l'application console  
 Cette section indique comment créer une application console Visual C\+\+ qui fait référence aux fichiers d'en\-tête que le programme utilisera.  
  
#### Pour créer une application Visual C\+\+ à l'aide de l'Assistant Application console Win32  
  
1.  Dans le menu **Fichier**, cliquez sur **Nouveau**, puis sur **Projet** pour afficher la boîte de dialogue **Nouveau projet**.  
  
2.  Dans la boîte de dialogue **Nouveau projet**, sélectionnez le nœud **Visual C\+\+** dans le volet **Types de projets**, puis sélectionnez **Application console Win32** dans le volet **Modèles**.  Tapez un nom pour le projet, par exemple `AgentDeBase`, puis cliquez sur **OK** pour afficher l'**Assistant Application console Win32**.  
  
3.  Dans la boîte de dialogue **Assistant Application console Win32**, cliquez sur **Terminer**.  
  
4.  Dans stdafx.h, ajoutez le code suivant :  
  
     [!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_1.h)]  
  
     Le fichier d'en\-tête agents.h contient la fonctionnalité de la classe [concurrency::agent](../../parallel/concrt/reference/agent-class.md).  
  
5.  Vérifiez que l'application a été créée avec succès en la générant et en l'exécutant.  Pour générer l'application, dans le menu **Générer**, cliquez sur **Générer la solution**.  Si l'application est générée avec succès, exécutez\-la en cliquant sur le bouton **Démarrer le débogage** dans le menu **Déboguer**.  
  
 \[[Premières](#top)\]  
  
##  <a name="createAgentClass"></a> Création de la classe file\_reader  
 Cette section indique comment créer la classe `file_reader`.  Le runtime planifie chaque agent pour effectuer le travail dans son propre contexte.  Par conséquent, vous pouvez créer un agent qui effectue le travail de façon synchrone, mais qui interagit de façon asynchrone avec d'autres composants.  La classe `file_reader` lit des données à partir d'un fichier d'entrée donné et envoie des données de ce fichier vers un composant cible donné.  
  
#### Pour créer la classe file\_reader  
  
1.  Ajoutez un nouveau fichier d'en\-tête C\+\+ à votre projet.  Pour cela, cliquez avec le bouton droit sur le nœud **Fichiers d'en\-tête** dans l'**Explorateur de solutions**, cliquez sur **Ajouter**, puis sur **Nouvel élément**.  Dans le volet **Modèles**, sélectionnez **Fichier d'en\-tête \(.h\)**.  Dans la boîte de dialogue **Ajouter un nouvel élément**, tapez `file_reader.h` dans la zone **Nom**, puis cliquez sur **Ajouter**.  
  
2.  Dans file\_reader.h, ajoutez le code suivant.  
  
     [!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_2.h)]  
  
3.  Dans file\_reader.h, créez une classe nommée `file_reader` qui dérive d'`agent`.  
  
     [!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_3.h)]  
  
4.  Ajoutez les membres de données suivants à la section `private` de votre classe.  
  
     [!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_4.h)]  
  
     Le membre `_file_name` est le nom de fichier à partir duquel l'agent lit.  Le membre `_target` est un objet [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) dans lequel l'agent écrit le contenu du fichier.  Le membre `_error` contient toute erreur qui se produit pendant la vie de l'agent.  
  
5.  Ajoutez le code suivant pour les constructeurs `file_reader` à la section `public` de la classe `file_reader`.  
  
     [!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_5.h)]  
  
     Chaque surcharge de constructeur définit les membres de données `file_reader`.  La surcharge des deuxième et troisième constructeurs permet à votre application d'utiliser un planificateur spécifique avec votre agent.  La première surcharge utilise le planificateur par défaut avec votre agent.  
  
6.  Ajoutez la méthode `get_error` à la section public de la classe `file_reader`.  
  
     [!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_6.h)]  
  
     La méthode `get_error` extrait toute erreur qui se produit pendant la vie de l'agent.  
  
7.  Implémentez la méthode [concurrency::agent::run](../Topic/agent::run%20Method.md) dans la section `protected` de votre classe.  
  
     [!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_7.h)]  
  
     La méthode `run` ouvre le fichier et lit les données qu'il contient.  La méthode `run` utilise la gestion des exceptions pour capturer les erreurs qui se produisent pendant le traitement de fichier.  
  
     Chaque fois que cette méthode lit des données à partir du fichier, elle appelle la fonction [concurrency::asend](../Topic/asend%20Function.md) pour envoyer ces données à la mémoire tampon cible.  Elle envoie la chaîne vide à sa mémoire tampon cible pour indiquer la fin du traitement.  
  
 L'exemple suivant affiche le contenu complet de file\_reader.h.  
  
 [!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_8.h)]  
  
 \[[Premières](#top)\]  
  
##  <a name="useAgentClass"></a> Utilisation de la classe file\_reader dans l'application  
 Cette section indique comment utiliser la classe `file_reader` pour lire le contenu d'un fichier texte.  Il indique également comment créer un objet [concurrency::call](../../parallel/concrt/reference/call-class.md) qui reçoit ces données du fichier et calcule leur somme de contrôle Adler\-32.  
  
#### Pour utiliser la classe file\_reader dans votre application  
  
1.  Dans BasicAgent.cpp, ajoutez l'instruction `#include` suivante.  
  
     [!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_9.cpp)]  
  
2.  Dans BasicAgent.cpp, ajoutez les directives `using` suivantes.  
  
     [!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_10.cpp)]  
  
3.  Dans la fonction `_tmain`, créez un objet [concurrency::event](../../parallel/concrt/reference/event-class.md) qui signale la fin du traitement.  
  
     [!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_11.cpp)]  
  
4.  Créez un objet `call` qui met à jour la somme de contrôle lorsqu'il reçoit des données.  
  
     [!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_12.cpp)]  
  
     Cet objet `call` définit également l'objet `event` lorsqu'il reçoit la chaîne vide pour signaler la fin du traitement.  
  
5.  Créez un objet `file_reader` qui lit à partir du fichier test.txt et écrit le contenu de ce fichier dans l'objet `call`.  
  
     [!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_13.cpp)]  
  
6.  Démarrez l'agent et attendez qu'il ait terminé.  
  
     [!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_14.cpp)]  
  
7.  Attendez que l'objet `call` reçoive toutes les données et se termine.  
  
     [!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_15.cpp)]  
  
8.  Vérifiez si le lecteur de fichier contient des erreurs.  Si aucune erreur ne s'est produite, calculez la somme Adler\-32 finale et imprimez\-la sur la console.  
  
     [!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_16.cpp)]  
  
 L'exemple suivant montre le fichier BasicAgent.cpp complet.  
  
 [!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_17.cpp)]  
  
 \[[Premières](#top)\]  
  
## Exemple d'entrée  
 Voici l'exemple de contenu du fichier d'entrée text.txt :  
  
  **Le renard marron rapide**  
**saute**  
**sur le chien paresseux**   
## Résultat de l'exemple  
 En cas d'utilisation avec l'exemple d'entrée, ce programme génère la sortie suivante :  
  
  **La somme Adler\-32 est fefb0d75**   
## Programmation fiable  
 Pour empêcher l'accès simultané aux membres de données, nous vous recommandons d'ajouter des méthodes qui effectuent le travail à la section `protected` ou `private` de votre classe.  Vous devez ajouter à la section `public` de votre classe uniquement des méthodes qui envoient ou reçoivent des messages à ou en provenance de l'agent.  
  
 Appelez toujours la méthode [concurrency::agent::done](../Topic/agent::done%20Method.md) pour déplacer votre agent vers l'état terminé.  On appelle en général cette méthode avant le retour de la méthode `run`.  
  
## Étapes suivantes  
 Pour obtenir un autre exemple d'une application basée sur agent, consultez [Procédure pas à pas : utilisation de la classe join pour empêcher l’interblocage](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).  
  
## Voir aussi  
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md)   
 [Structures de données de synchronisation](../../parallel/concrt/synchronization-data-structures.md)   
 [Procédure pas à pas : utilisation de la classe join pour empêcher l’interblocage](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)