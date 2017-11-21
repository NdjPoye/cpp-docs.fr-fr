---
title: "Étape 2 : générer et exécuter un projet d’application console C++ | Documents Microsoft"
description: Installer la prise en charge de Visual Studio pour Visual C++
ms.custom: mvc
ms.date: 10/17/2017
ms.topic: get-started-article
ms.technology: devlang-C++
ms.devlang: C++
dev_langs: C++
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20a8bafa69631ef8df1fb20f613dfbb81578f94a
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2017
---
# <a name="build-and-run-a-c-console-app-project"></a>Générer et exécuter un projet d’application console C++

Lorsque vous avez créé un projet d’application console C++ et entré votre code, vous pouvez générer et exécuter dans Visual Studio et puis l’exécuter comme une application autonome à partir de la ligne de commande.

## <a name="prerequisites"></a>Conditions préalables

- Visual Studio avec le développement de bureau dotées de la charge de travail C++ installé et en cours d’exécution sur votre ordinateur. S’il n’est pas encore installé, suivez les étapes de [étape 0 - prise en charge de l’installation de C++ dans Visual Studio](../build/vscpp-step-0-installation.md).

- Créer un « Hello, World ! » projet et entrez son code source. Si vous n’avez pas cela encore, suivez les étapes de [étape 1 : créer un projet d’application console C++](../build/vscpp-step-1-create.md).

Si Visual Studio ressemble à ceci, vous êtes prêt à générer et exécuter votre application :

   ![Prêt à créer le nouveau projet](../build/media/vscpp-ready-to-build.png "prêt à créer le nouveau projet")

## <a name="build-and-run-your-code-in-visual-studio"></a>Générer et exécuter votre code dans Visual Studio

1. Pour générer votre projet, choisissez **générer la Solution** à partir de la **générer** menu. Le **sortie** fenêtre affiche les résultats du processus de génération.

   ![Générez le projet](../build/media/vscpp-build-solution.gif "générer le projet")

1. Pour exécuter le code, dans la barre de menus, choisissez **déboguer**, **démarrer sans débogage**.

   ![Démarrer le projet](../build/media/vscpp-start-without-debugging.gif "démarrer le projet")

    Une fenêtre de console s’ouvre, puis exécute votre application. Lorsque vous démarrez une application console dans Visual Studio, votre code est exécuté, puis imprime « appuyez sur n’importe quelle touche pour continuer. . ." Pour vous donner la possibilité de voir la sortie.

Félicitations ! Vous avez créé votre premier « Hello, world ! » application de console dans Visual Studio ! Appuyez sur une touche pour fermer la fenêtre de console et revenir à Visual Studio.

[J’ai rencontré un problème.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>Exécutez votre code dans une fenêtre de commande

En règle générale, vous exécutez des applications console à l’invite de commandes, pas dans Visual Studio. Une fois que votre application est générée par Visual Studio, vous pouvez l’exécuter à partir de n’importe quelle fenêtre de commande. Voici comment procéder rechercher et exécuter votre nouvelle application dans une fenêtre d’invite de commandes.

1. Dans **l’Explorateur de solutions**avec le bouton droit pour ouvrir le menu contextuel et sélectionnez la solution HelloWorld. Choisissez **ouvrir le dossier dans l’Explorateur de fichiers** pour ouvrir un **l’Explorateur de fichiers** fenêtre dans le dossier de solution HelloWorld.

1. Dans le **l’Explorateur de fichiers** fenêtre, ouvrez le dossier de débogage. Il contient votre application, HelloWorld.exe et deux autres fichiers de débogage. Sélectionnez HelloWorld.exe, maintenez la touche MAJ enfoncée et avec le bouton droit pour ouvrir le menu contextuel. Choisissez **copie comme chemin d’accès** pour copier le chemin d’accès à votre application dans le Presse-papiers.

1. Pour ouvrir une fenêtre d’invite de commandes, appuyez sur R de Windows pour ouvrir le **exécuter** boîte de dialogue. Entrez *cmd.exe* dans les **ouvrir** zone de texte, puis choisissez **OK** pour exécuter une fenêtre d’invite de commandes.

1. Dans la fenêtre d’invite de commandes, cliquez sur pour coller le chemin d’accès à votre application dans l’invite de commandes. Appuyez sur ENTRÉE pour exécuter votre application.

   ![Exécuter l’application à l’invite de commandes](../build/media/vscpp-run-in-cmd.gif "à l’invite de commande, exécutez l’application")

Félicitations, vous avez créé et exécuter une application de console dans Visual Studio.

[J’ai rencontré un problème.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>Étapes suivantes

Une fois que vous avez créé et exécuter cette application simple, vous êtes prêt pour les projets plus complexes. Consultez les Démarrages rapides, didacticiels et exemples de Code pour obtenir des exemples des choses que vous pouvez effectuer en C++ à l’aide de Visual Studio.

## <a name="troubleshooting-guide"></a>Guide de dépannage

Viens pour les solutions aux problèmes courants rencontrés lorsque vous créez votre premier projet C++.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Générer et exécuter votre code dans Visual Studio problèmes

Si les soulignements ondulés rouges s’affichent sous n’importe où dans l’éditeur de code source, la build peut avoir des erreurs ou des avertissements. Vérifiez que votre code correspond à l’exemple dans le cas, signes de ponctuation et l’orthographe.

[Retour.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>Exécuter votre code dans une fenêtre de commande problèmes

Vous pouvez également accéder au dossier de débogage de solution sur la ligne de commande pour exécuter votre application. Vous ne pouvez pas exécuter votre application à partir d’autres annuaires sans spécifier le chemin d’accès à l’application. Toutefois, vous pouvez copier votre application vers un autre répertoire et exécutez-le à partir de là.

[Retour.](#run-your-code-in-a-command-window)


<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
