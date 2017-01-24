---
title: "Proc&#233;dure pas &#224; pas&#160;: g&#233;n&#233;ration d’un projet (C++) | Microsoft Docs"
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
  - "générer des projets [C++]"
  - "projets [C++], générer"
  - "génération de projets [C++]"
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: g&#233;n&#233;ration d’un projet (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans cette procédure pas à pas, vous introduisez délibérément une erreur de syntaxe Visual C\+\+ dans votre code pour apprendre à reconnaître une erreur de compilation et à la résoudre.  Lorsque vous compilez le projet, un message d'erreur indique en quoi consiste le problème et l'endroit où il s'est produit.  
  
## Composants requis  
  
-   Cette procédure pas à pas part du principe que vous comprenez les notions de base du langage C\+\+.  
  
-   Elle suppose également que vous avez effectué les procédures pas à pas connexes précédentes répertoriées dans [Utilisation de l'IDE de Visual Studio pour le développement de bureau C\+\+](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### Pour résoudre les erreurs de compilation  
  
1.  Dans TestGames.cpp, supprimez le point\-virgule de la dernière ligne pour obtenir ce qui suit :  
  
     `return 0`  
  
2.  Dans la barre de menus, choisissez **Générer**, puis **Générer la solution**.  
  
3.  Un message dans la fenêtre **Liste d'erreurs** indique qu'une erreur s'est produite lors de la génération du projet.  La description ressemble à ceci :  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     Pour afficher l'aide concernant cette erreur, sélectionnez\-la dans la fenêtre **Liste d'erreurs** et appuyez sur la touche F1.  
  
4.  Replacez le point\-virgule à la fin de la ligne où se situe l'erreur de syntaxe :  
  
     `return 0;`  
  
5.  Dans la barre de menus, choisissez **Générer**, puis **Générer la solution**.  
  
     Un message dans la fenêtre **Sortie** indique que le projet a été compilé avec succès.  
  
  **1\>\-\-\-\-\-\- Génération démarrée : Projet : Game, Configuration : Débogage Win32 \-\-\-\-\-\-**  
**1\>  TestGames.cpp**  
**1\>  Game.vcxproj \-\> C:\\Users\\\<username\>\\Documents\\Visual Studio *\<version\>*\\Projects\\Game\\Debug\\Game.exe**  
**\=\=\=\=\=\=\=\=\=\= Génération : 1 a réussi, 0 a échoué, 0 mis à jour, 0 a été ignoré \=\=\=\=\=\=\=\=\=\=**  
  
## Étapes suivantes  
 **Précédent :** [Procédure pas à pas : utilisation de projets et de solutions \(C\+\+\)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) &#124; **Suivant :** [Procédure pas à pas : test d'un projet \(C\+\+\)](../ide/walkthrough-testing-a-project-cpp.md)  
  
## Voir aussi  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](http://msdn.microsoft.com/fr-fr/9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)