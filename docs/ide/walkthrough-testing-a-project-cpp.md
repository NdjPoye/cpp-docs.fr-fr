---
title: "Procédure pas à pas : Test d’un projet (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ba928d4a81252b76856273160af63ed8707e7e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-testing-a-project-c"></a>Procédure pas à pas : test d'un projet (C++)
Lorsque vous exécutez un programme en mode débogage, vous pouvez utiliser des points d’arrêt pour interrompre le programme pour examiner l’état des variables et des objets.  
  
 Dans cette procédure pas à pas, vous observez la valeur d’une variable que le programme s’exécute et déduisez pourquoi la valeur n’est pas ce que vous attendez.  
  
## <a name="prerequisites"></a>Prérequis  
  
-   Cette procédure pas à pas part du principe que vous comprenez les notions de base du langage C++.  
  
-   Il suppose également que vous avez effectué les procédures plus haut connexes qui sont répertoriés dans [à l’aide de l’IDE de Visual Studio pour le développement de bureau C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-run-a-program-in-debug-mode"></a>Pour exécuter un programme en mode débogage  
  
1.  Ouvrez TestGames.cpp pour la modification.  
  
2.  Sélectionnez cette ligne de code :  
  
     `Cardgame.solitaire(1);`  
  
3.  Pour définir un point d’arrêt sur cette ligne, dans la barre de menus, choisissez **déboguer**, **point d’arrêt**, ou appuyez sur la touche F9. Un cercle rouge apparaît à gauche de la ligne ; Il indique qu’un point d’arrêt est défini. Pour supprimer un point d’arrêt, vous pouvez choisir à nouveau la commande de menu ou la touche F9.  
  
     Si vous utilisez une souris, vous pouvez également définir ou supprimer un point d’arrêt en cliquant dans la marge de gauche.  
  
4.  Dans la barre de menus, choisissez **déboguer**, **démarrer le débogage**, ou appuyez sur la touche F5.  
  
     Lorsque le programme atteint la ligne contenant le point d’arrêt, l’exécution s’arrête temporairement, car votre programme est en mode arrêt. Une flèche jaune à gauche d’une ligne de code indique que la ligne suivante à exécuter.  
  
5.  Pour examiner la valeur de la `Cardgame::totalParticipants` variable, placez le pointeur sur `Cardgame` , puis le déplacer sur le contrôle d’extension à gauche de la fenêtre d’info-bulle. Le nom de variable `totalParticipants` et sa valeur de 12 sont affichés.  
  
     Ouvrez le menu contextuel pour le `Cardgame::totalParticipants` variable, puis choisissez **ajouter un espion** pour afficher cette variable dans le **Espion 1** fenêtre. Vous pouvez également sélectionner une variable et faites-la glisser vers le **Espion 1** fenêtre.  
  
6.  Pour passer à la ligne suivante de code, dans la barre de menus, choisissez **déboguer**, **pas à pas principal**, ou appuyez sur la touche F10.  
  
     La valeur de `Cardgame::totalParticipants` dans les **Espion 1** fenêtre est maintenant affichée comme 13.  
  
7.  Ouvrez le menu contextuel pour le `return 0;` instruction, puis choisissez **exécuter jusqu’au curseur**. La flèche jaune à gauche des points de code à l’instruction suivante à exécuter.  
  
8.  Le `Cardgame::totalParticipants` doit diminuer lorsqu’un Cardgame se termine. À ce stade, `Cardgame::totalParticipants` doit être égal à 0, car toutes les instances Cardgame ont été supprimés, mais la **Espion 1** fenêtre indique que `Cardgame::totalparticipants` est égal à 18. Cela indique qu’il existe un bogue dans le code, vous pouvez détecter et résoudre en effectuant la procédure suivante, [procédure pas à pas : débogage d’un projet (C++)](../ide/walkthrough-debugging-a-project-cpp.md).  
  
9. Pour arrêter le programme, dans la barre de menus, choisissez **déboguer**, **arrêter le débogage**, ou choisissez le raccourci MAJ + F5.  
  
## <a name="next-steps"></a>Étapes suivantes  
 **Précédente :** [procédure pas à pas : création d’un projet (C++)](../ide/walkthrough-building-a-project-cpp.md) &#124; **Suivant :**[procédure pas à pas : débogage d’un projet (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Génération de programmes C/C++](../build/building-c-cpp-programs.md)