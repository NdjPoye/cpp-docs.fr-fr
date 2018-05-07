---
title: 'Procédure pas à pas : Création d’un projet (C++) | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c8d04dc3692076b867302af0e793eaac7ed25cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-building-a-project-c"></a>Procédure pas à pas : génération d’un projet (C++)
Dans cette procédure pas à pas, vous introduisez délibérément une erreur de syntaxe Visual C++ dans votre code pour apprendre à reconnaître une erreur de compilation et à la résoudre. Lorsque vous compilez le projet, un message d'erreur indique en quoi consiste le problème et l'endroit où il s'est produit.  
  
## <a name="prerequisites"></a>Prérequis  
  
-   Cette procédure pas à pas part du principe que vous comprenez les notions de base du langage C++.  
  
-   Il suppose également que vous avez effectué les procédures plus haut connexes qui sont répertoriés dans [à l’aide de l’IDE de Visual Studio pour le développement de bureau C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-fix-compilation-errors"></a>Pour résoudre les erreurs de compilation  
  
1.  Dans TestGames.cpp, supprimez le point-virgule de la dernière ligne pour obtenir ce qui suit :  
  
     `return 0`  
  
2.  Dans la barre de menus, choisissez **Générer**, puis **Générer la solution**.  
  
3.  Un message dans le **liste d’erreurs** fenêtre indique qu’il existe une erreur dans la génération du projet. La description ressemble à ceci :  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     Pour afficher les informations d’aide sur cette erreur, mettez en surbrillance dans le **liste d’erreurs** fenêtre, puis sur la touche F1.  
  
4.  Replacez le point-virgule à la fin de la ligne où se situe l'erreur de syntaxe :  
  
     `return 0;`  
  
5.  Dans la barre de menus, choisissez **Générer**, puis **Générer la solution**.  
  
     Un message dans le **sortie** fenêtre indique que le projet a été compilé avec succès.  
  
    ```Output  
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------  
    1>  TestGames.cpp  
    1>  Game.vcxproj -> C:\Users\<username>\Documents\Visual Studio <version>\Projects\Game\Debug\Game.exe  
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
    ```  
  
## <a name="next-steps"></a>Étapes suivantes  
 **Précédente :** [procédure pas à pas : utilisation de projets et Solutions (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) &#124; **suivant :**[procédure pas à pas : test d’un projet (C++)](../ide/walkthrough-testing-a-project-cpp.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Génération de programmes C/C++](../build/building-c-cpp-programs.md)