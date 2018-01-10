---
title: "Procédure pas à pas : Utilisation de projets et Solutions (C++) | Documents Microsoft"
ms.custom: 
ms.date: 12/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a20c0ee933d49465a841b638a8260181d7175ac5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>Procédure pas à pas : utilisation de projets et de solutions (C++)

Voici comment créer un projet C++ dans Visual Studio, ajouter du code, puis générer et exécuter le projet. Le projet dans cette procédure pas à pas est un programme qui assure le suivi du nombre de joueurs qui jouent à différents jeux de cartes.

Dans Visual Studio, le travail est organisé en projets et solutions. Une solution peut contenir plusieurs projets, par exemple une DLL et un fichier exécutable référençant cette DLL. Pour plus d’informations, consultez [Solutions et projets](/visualstudio/ide/solutions-and-projects-in-visual-studio).

## <a name="before-you-start"></a>Avant de commencer

Pour effectuer cette procédure pas à pas, vous avez besoin de Visual Studio 2017 version 15,3 ou version ultérieure. Si vous avez besoin d’une copie, Voici un guide court : [prise en charge de l’installation de C++ dans Visual Studio](../build/vscpp-step-0-installation.md). Si vous n’avez pas le fait encore, suivez les étapes suivants après l’installation via le didacticiel « Hello, World » pour vous assurer que Visual C++ est correctement installé et tous les travaux.

Il est utile si vous comprenez les notions de base du langage C++ et que vous savez qu’un compilateur, éditeur de liens et débogueur sont utilisés pour. Le didacticiel suppose également que vous êtes familiarisé avec Windows et comment utiliser les menus, boîtes de dialogue

## <a name="create-a-project"></a>Créer un projet

Pour créer un projet, choisissez d'abord un modèle de type de projet. Pour chaque type de projet, Visual Studio définit les paramètres du compilateur et, en fonction du type, génère le code de démarrage que vous pouvez modifier ultérieurement.

### <a name="to-create-a-project"></a>Pour créer un projet

1. Dans la barre de menus, choisissez **fichier > Nouveau > projet**.

1. Dans le volet gauche de la **nouveau projet** boîte de dialogue, développez **installé** et sélectionnez **Visual C++**, si elle est déjà fermé.

1. Dans la liste des modèles installés dans le volet central, sélectionnez **Application Console Windows**.

1. Entrez un nom pour le projet dans le **nom** boîte. Par exemple, entrez **jeu**.

   Vous pouvez accepter l’emplacement par défaut dans le **emplacement** la liste déroulante, indiquez un emplacement différent, ou choisissez la **Parcourir** bouton pour accéder à un répertoire où vous souhaitez enregistrer le projet.

   Lorsque vous créez un projet, Visual Studio ajoute le projet à une solution. Par défaut, la solution porte le même nom que le projet. Vous pouvez modifier le nom dans la **nom de la Solution** zone, mais pour cet exemple, conservez le nom par défaut.

1. Choisissez le bouton **OK** pour créer le projet.

   Visual Studio crée votre solution et les fichiers projet et ouvre l’éditeur pour le fichier de code source Game.cpp qu'il généré.

## <a name="organize-projects-and-files"></a>Organiser les projets et des fichiers

Vous pouvez utiliser **l’Explorateur de solutions** pour organiser et gérer les projets, fichiers et autres ressources dans votre solution.

Cette partie de la procédure pas à pas montre comment ajouter une classe au projet. Lorsque vous ajoutez la classe, Visual Studio ajoute les fichiers .cpp et .h correspondants. Vous pouvez afficher les résultats dans **l’Explorateur de solutions**.

### <a name="to-add-a-class-to-a-project"></a>Pour ajouter une classe à un projet

1. Si le **l’Explorateur de solutions** fenêtre n’est pas affichée dans Visual Studio, dans la barre de menus, choisissez **vue > Explorateur de solutions**.

1. Dans **l’Explorateur de solutions**, sélectionnez le **jeu** projet. Dans la barre de menus, choisissez **projet > Ajouter une classe**.

1. Dans le **ajouter une classe** boîte de dialogue, entrez *Cardgame* dans les **nom de la classe** boîte. Ne modifiez pas les noms de fichiers et les paramètres par défaut. Sélectionnez le bouton **OK** .

   Visual Studio crée de nouveaux fichiers et les ajoute à votre projet. Vous pouvez les consulter dans le **l’Explorateur de solutions** fenêtre. Les fichiers Cardgame.h et Cardgame.cpp sont ouverts dans l’éditeur.

1. Modifiez le fichier Cardgame.h et apporter ces modifications :

   - Ajoutez deux membres de données privés après l'accolade gauche de la définition de classe.
      <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Modifiez le constructeur par défaut généré par Visual Studio. Après le spécificateur d'accès `public:`, recherchez la ligne qui ressemble à ceci :

      `Cardgame();`

      Modifiez ce constructeur pour prendre un paramètre de type `int`, nommé *joueurs*.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - Après le destructeur par défaut, ajoutez une déclaration inline pour un `static int` fonction membre nommée *GetParticipants* qui ne prend aucun paramètre et retourne le `totalParticipants` valeur.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->
      `static int GetParticipants() { return totalParticipants; }`

   Après modification, le fichier Cardgame.h doit ressembler à cela :

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]-->
   ```cpp
   #pragma once
   class Cardgame
   {
       int players;
       static int totalParticipants;
   public:
       Cardgame(int players);
       ~Cardgame(void);
       static int GetParticipants() { return totalParticipants; }
   };
   ```

   La ligne `#pragma once` indique au compilateur d’inclure le fichier d’en-tête qu’une seule fois. Pour plus d’informations, consultez [une fois](../preprocessor/once.md). Pour plus d’informations sur les autres mots clés de C++ dans ce fichier d’en-tête, consultez [classe](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [statique](../cpp/storage-classes-cpp.md), et [public](../cpp/public-cpp.md).

1. Choisissez le **Cardgame.cpp** onglet en haut du volet d’édition pour ouvrir pour le modifier.

1. Supprimez tout le contenu du fichier et remplacez-le par ce code :

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]-->
   ```cpp
   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   int Cardgame::totalParticipants = 0;

   Cardgame::Cardgame(int players)
       : players(players)
   {
       totalParticipants += players;
       cout << players << " players have started a new game.  There are now "
            << totalParticipants << " players in total." << endl;
   }

   Cardgame::~Cardgame()
   {
   }
   ```

   > [!NOTE]
   > Vous pouvez utiliser la saisie semi-automatique lorsque vous écrivez du code. Par exemple, si vous entrez ce code à l’aide du clavier, vous pouvez entrer *pl* ou *assurances* , puis appuyez sur Ctrl + espace. La saisie semi-automatique passe `players` ou `totalParticipants` pour vous.

## <a name="add-test-code-to-your-main-function"></a>Ajoutez le code de test à votre fonction main

Ajoutez du code à votre application qui vérifie les nouvelles fonctions.

### <a name="to-add-test-code-to-the-project"></a>Pour ajouter du code de test au projet

1. Dans la fenêtre d’éditeur Game.cpp, remplacez le code existant avec ce :

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]-->
   ```cpp
   // Game.cpp : Defines the entry point for the console application.
   //

   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   void PlayGames()
   {
       Cardgame bridge(4);
       Cardgame blackjack(8);
       Cardgame solitaire(1);
       Cardgame poker(5);
   }

   int main()
   {
       PlayGames();
       return 0;
   }
   ```
Ce code ajoute une fonction de test, `PlayGames`, pour le code source et les appels dans `main`. 

## <a name="build-and-run-your-app-project"></a>Générer et exécuter votre projet d’application

Ensuite, générez le projet et exécuter l’application.

### <a name="to-build-and-run-the-project"></a>Pour générer et exécuter le projet

1. Dans la barre de menus, choisissez **Générer > Générer la solution**.

   Sortie à partir d’une build s’affiche dans le **sortie** fenêtre. Si la génération réussit, la sortie doit ressembler à ceci :

   ```Output
   1>------ Build started: Project: Game, Configuration: Debug Win32 ------
   1>  stdafx.cpp
   1>  Game.cpp
   1>  Cardgame.cpp
   1>  Generating Code...
   1>  Game.vcxproj -> C:\Users\username\Source\Repos\Game\Debug\Game.exe
   ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
   ```

   Le **sortie** fenêtre peut afficher différentes étapes, selon la configuration de build, mais si la génération du projet réussit, la dernière ligne doit ressembler à la sortie.

   Si votre build n’a pas réussi, comparez votre code pour le code qui est indiqué dans les étapes précédentes.

1. Pour exécuter le projet, dans la barre de menus, choisissez **Déboguer > Démarrer sans débogage**. Une fenêtre de console doit s’afficher, et la sortie doit ressembler à ceci :

   ```Output
   4 players have started a new game.  There are now 4 players in total.
   8 players have started a new game.  There are now 12 players in total.
   1 players have started a new game.  There are now 13 players in total.
   5 players have started a new game.  There are now 18 players in total.
   ```
Appuyez sur une touche pour fermer la fenêtre de console.

Félicitations, vous avez créé avec succès une solution et un projet d’application. Continuer la procédure pas à pas pour en savoir plus sur la façon de générer des projets de code C++ dans Visual Studio.

## <a name="next-steps"></a>Étapes suivantes

**Précédente :** [à l’aide de l’IDE de Visual Studio pour le développement de bureau C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
**Ensuite :** [procédure pas à pas : création d’un projet (C++)](../ide/walkthrough-building-a-project-cpp.md).

## <a name="see-also"></a>Voir aussi

[Informations de référence sur le langage C++](../cpp/cpp-language-reference.md)  
[Génération de programmes C/C++](../build/building-c-cpp-programs.md)