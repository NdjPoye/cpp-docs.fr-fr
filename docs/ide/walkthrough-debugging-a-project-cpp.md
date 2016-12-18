---
title: "Proc&#233;dure pas &#224; pas&#160;: d&#233;bogage d&#39;un projet (C++) | Microsoft Docs"
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
  - "déboguer des projets"
  - "débogage de projets (C++)"
  - "projets (C++), débogage"
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: d&#233;bogage d&#39;un projet (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans ce guide, vous allez modifier le programme pour résoudre le problème que vous avez découvert lors du test du projet.  
  
## Composants requis  
  
-   Cette procédure pas à pas suppose que vous compreniez les notions de base du langage C\+\+.  
  
-   Elle suppose également que vous avez effectué les procédures pas à pas connexes précédentes répertoriées dans [Utilisation de l'IDE de Visual Studio pour le développement de bureau C\+\+](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### Pour résoudre un programme qui présente un bogue  
  
1.  Pour voir ce qui se passe lorsqu'un objet `Cardgame` est détruit, consultez le destructeur de la classe `Cardgame`.  
  
     Dans la barre de menus, sélectionnez **View**, **Class View**.  
  
     Dans la fenêtre **Class View**, développez l'arborescence du projet **Game** et sélectionnez la classe **Cardgame** pour afficher les membres et les méthodes de la classe.  
  
     Ouvrez le menu contextuel du destructeur **~Cardgame \(void\)** puis choisissez **Go To Definition**.  
  
2.  Pour diminuer le `totalParticipants` lorsque Cardgame est terminé, ajoutez le code suivant entre les accolades ouvrante et fermante du destructeur `Cardgame::~Cardgame` .  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  Après modification, le fichier Cardgame.cpp doit ressembler à cela :  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  Dans la barre de menus, choisissez **Générer**, puis **Générer la solution**.  
  
5.  Lorsque la génération est terminée, exécutez\-la en mode débogage en choisissant **Debug**, **Start Debugging** dans la barre de menu , ou en utilisant la touche F5.  Le programme s'interrompt au premier point d'arrêt.  
  
6.  Pour parcourir le programme, dans la barre de menus, choisissez **Debug**, **Step Over**, ou utilisez la touche F10.  
  
     Remarquez qu'après l'exécution de chaque constructeur Cardgame, la valeur de `totalParticipants` augmente.  Lorsque la fonction `PlayGames` retourne, tandis que chaque instance de Cardgame devient hors de portée et est supprimée \(et le destructeur est appelé\), `totalParticipants` diminue.  Avant l'exécution de l'instruction `return`, `totalParticipants` est égal à 0.  
  
7.  Continuez à parcourir le programme jusqu'à sa fermeture, ou laissez le tourner en utilisant **Debug**, **Run** dans la barre de menus, ou en utilisant la touche F5.  
  
## Étapes suivantes  
 **Précédent :** [Procédure pas à pas : test d'un projet \(C\+\+\)](../ide/walkthrough-testing-a-project-cpp.md) &#124; **Suivant :** [Procédure pas à pas : déploiement de votre programme \(C\+\+\)](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## Voir aussi  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](http://msdn.microsoft.com/fr-fr/9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)