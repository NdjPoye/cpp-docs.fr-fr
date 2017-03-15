---
title: "Proc&#233;dure pas &#224; pas&#160;: test d&#39;un projet (C++) | Microsoft Docs"
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
  - "tests de projets (C++)"
  - "projets (C++), tester"
  - "tester des projets"
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: test d&#39;un projet (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous exécutez un programme en mode débogage, vous pouvez utiliser des points d'arrêt pour suspendre le programme afin d'examiner l'état des variables et des objets.  
  
 Dans cette procédure pas à pas, vous observez la valeur d'une variable pendant l'exécution du programme et vous en déduisez pourquoi la valeur n'est pas celle qui est prévue.  
  
## Composants requis  
  
-   Cette procédure pas à pas suppose que vous compreniez les notions de base du langage C\+\+.  
  
-   Elle suppose également que vous avez effectué les procédures pas à pas connexes précédentes répertoriées dans [Utilisation de l'IDE de Visual Studio pour le développement de bureau C\+\+](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### Pour exécuter un programme en mode débogage  
  
1.  Ouvrez TestGames.cpp pour modification.  
  
2.  Sélectionnez cette ligne de code :  
  
     `Cardgame.solitaire(1);`  
  
3.  Pour définir un point d'arrêt sur cette ligne, dans la barre de menus, choisissez **Déboguer**, **Basculer le point d'arrêt** ou utilisez la touche F9.  Un cercle rouge apparaît à gauche de la ligne ; il indique qu'un point d'arrêt est défini.  Pour supprimer un point d'arrêt, vous pouvez sélectionner la commande de menu ou à nouveau la touche F9.  
  
     Si vous utilisez une souris, vous pouvez également définir ou supprimer un point d'arrêt en cliquant dans la marge de gauche.  
  
4.  Dans la barre de menus, choisissez **Déboguer**, **Démarrer le débogage**, ou appuyez sur la touche F5.  
  
     Lorsque le programme atteint la ligne comportant le point d'arrêt, l'exécution s'arrête temporairement car votre programme se trouve en mode Arrêt.  Une flèche jaune à gauche d'une ligne de code indique la prochaine ligne à exécuter.  
  
5.  Pour examiner la valeur de la variable `Cardgame::totalParticipants`, déplacez le pointeur sur `Cardgame`, puis déplacez\-le sur le contrôle d'expansion existe à gauche de la fenêtre d'info\-bulle.  Le nom de variable `totalParticipants` et sa valeur 12 s'affichent.  
  
     Ouvrez le menu contextuel de la variable `Cardgame::totalParticipants`, puis choisissez **Ajouter un espion** pour afficher cette variable dans la fenêtre **Espion 1**.  Vous pouvez également sélectionner une variable et la faire glisser sur la fenêtre **Espion 1**.  
  
6.  Pour passer à la ligne de code suivante, dans la barre de menus, choisissez **Déboguer**, **Pas à pas principal** ou appuyez sur F10 .  
  
     La valeur `Cardgame::totalParticipants` dans la fenêtre **Espion 1** s'affiche maintenant sous la forme 13.  
  
7.  Ouvrez le menu contextuel de l'instruction `return 0;`, puis choisissez **Exécuter jusqu'au curseur**.  La flèche jaune à gauche du code pointe sur la prochaine instruction à exécuter.  
  
8.  Le nombre `Cardgame::totalParticipants` doit diminuer lorsque Cardgame se termine.  À ce stade, `Cardgame::totalParticipants` doit être égal à 0 car toutes les instances Cardgame ont été supprimées, mais la fenêtre **Espion 1** indique que `Cardgame::totalparticipants` est égal à 18.  Cela indique la présence d'un bogue dans le code, que vous pouvez détecter et corriger en exécutant la procédure suivante, [Procédure pas à pas : débogage d'un projet \(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md).  
  
9. Pour arrêter le programme, dans la barre de menus, sélectionnez **Déboguer**, **Arrêter le débogage**, ou sélectionnez le raccourci clavier Maj\+F5.  
  
## Étapes suivantes  
 **Précédent :** [Procédure pas à pas : génération d’un projet \(C\+\+\)](../ide/walkthrough-building-a-project-cpp.md) &#124; **Suivant :** [Procédure pas à pas : débogage d'un projet \(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## Voir aussi  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](http://msdn.microsoft.com/fr-fr/9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)