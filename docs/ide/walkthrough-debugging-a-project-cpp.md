---
title: 'Procédure pas à pas : Débogage d’un projet (C++) | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecfda5e2549b3aa9be1f0471e301cc2a21c6fd5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-debugging-a-project-c"></a>Procédure pas à pas : débogage d'un projet (C++)
Dans cette procédure pas à pas, vous modifiez le programme pour résoudre le problème que vous avez découvert lorsque vous avez testé le projet.  
  
## <a name="prerequisites"></a>Prérequis  
  
-   Cette procédure pas à pas part du principe que vous comprenez les notions de base du langage C++.  
  
-   Il suppose également que vous avez effectué les procédures plus haut connexes qui sont répertoriés dans [à l’aide de l’IDE de Visual Studio pour le développement de bureau C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-fix-a-program-that-has-a-bug"></a>Pour résoudre un programme qui comporte un bogue  
  
1.  Pour voir ce qui se produit lorsqu’un `Cardgame` objet est détruit, consultez le destructeur de la `Cardgame` classe.  
  
     Dans la barre de menus, choisissez **vue**, **affichage de classes**.  
  
     Dans le **affichage de classes** fenêtre, développez le **jeu** arborescence du projet et sélectionnez le **Cardgame** classe pour afficher les membres de classe et les méthodes.  
  
     Ouvrez le menu contextuel pour le **~Cardgame(void)** destructeur, puis choisissez **atteindre la définition**.  
  
2.  Pour réduire le `totalParticipants` lorsqu’un Cardgame se termine, ajoutez le code suivant entre les accolades ouvrantes et fermantes de le `Cardgame::~Cardgame` destructeur.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  Le fichier Cardgame.cpp doit ressembler à ceci après modification :  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  Dans la barre de menus, choisissez **Générer**, puis **Générer la solution**.  
  
5.  Lors de la génération terminée, exécutez-le en mode débogage en choisissant **déboguer**, **démarrer le débogage** sur la barre de menus, ou en choisissant la touche F5. Le programme s’interrompt au premier point d’arrêt.  
  
6.  Pour exécuter le programme, dans la barre de menus, choisissez **déboguer**, **pas à pas principal**, ou appuyez sur la touche F10.  
  
     Notez que, après chaque constructeur Cardgame, la valeur de `totalParticipants` augmente. Lorsque le `PlayGames` fonction renvoie, chaque instance Cardgame est hors de portée et est supprimé (et le destructeur est appelé), `totalParticipants` diminue. Juste avant la `return` instruction est exécutée, `totalParticipants` est égal à 0.  
  
7.  Continuer l’exécution pas à pas le programme jusqu'à ce qu’il se termine, ou autoriser son exécution en choisissant **déboguer**, **exécuter** sur la barre de menus, ou en choisissant la touche F5.  
  
## <a name="next-steps"></a>Étapes suivantes  
 **Précédente :** [procédure pas à pas : test d’un projet (C++)](../ide/walkthrough-testing-a-project-cpp.md) &#124; **suivant :**[procédure pas à pas : déploiement de votre programme (C++)](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Génération de programmes C/C++](../build/building-c-cpp-programs.md)