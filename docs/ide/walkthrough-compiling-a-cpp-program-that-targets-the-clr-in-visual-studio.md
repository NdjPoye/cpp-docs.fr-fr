---
title: "Compilation d’un programme C++ qui cible le CLR | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
caps.latest.revision: "40"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eca6960d23c43fbe27d753ab4f79a27dea7bd7e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>Procédure pas à pas : compilation d'un programme C++ qui cible le CLR dans Visual Studio
Vous pouvez créer des programmes Visual C++ qui utilisent des classes .NET et les compiler à l’aide de l’environnement de développement Visual Studio.  
  
 Pour cette procédure, vous pouvez taper votre propre programme Visual C++ ou utiliser un des exemples de programmes. L’exemple de programme que nous utilisons dans cette procédure crée un fichier texte nommé textfile.txt et l’enregistre dans le répertoire du projet.  
  
## <a name="prerequisites"></a>Prérequis  
 Ces rubriques supposent que vous comprenez les notions de base du langage C++.  
  
### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>Pour créer un nouveau projet dans Visual Studio et ajoutez un nouveau fichier source  
  
1.  Créer un nouveau projet. Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet**.  
  
2.  Dans les types de projets Visual C++, cliquez sur **CLR**, puis cliquez sur **projet vide CLR**.  
  
3.  Tapez un nom de projet.  
  
     Par défaut, la solution qui contient le projet porte le même nom que le nouveau projet, mais vous pouvez entrer un autre nom. Vous pouvez entrer un autre emplacement pour le projet si vous le souhaitez.  
  
     Cliquez sur **OK** pour créer le projet.  
  
4.  Si l’Explorateur de solutions n’est pas visible, cliquez sur **l’Explorateur de solutions** sur la **vue** menu.  
  
5.  Ajoutez un nouveau fichier source au projet :  
  
    -   Avec le bouton droit le **fichiers sources** dossier dans l’Explorateur de solutions, pointez sur **ajouter** et cliquez sur **un nouvel élément**.  
  
    -   Cliquez sur **fichier C++ (.cpp)** , tapez un nom de fichier, puis cliquez **ajouter**.  
  
     Le **.cpp** fichier s’affiche dans le **fichiers sources** dossier dans l’Explorateur de solutions et une fenêtre à onglets s’affiche lorsque vous tapez le code souhaité dans ce fichier.  
  
6.  Cliquez dans l’onglet nouvellement créé dans Visual Studio et tapez un programme Visual C++ valide, ou copiez et collez un des exemples de programmes.  
  
     Par exemple, vous pouvez utiliser la [Comment : écrire un fichier texte (C + c++ / CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md) exemple de programme (dans le **e/s et gestion des fichiers** nœud du Guide de programmation).  
  
     Si vous utilisez l’exemple de programme, notez que vous utilisez le `gcnew` (mot clé) au lieu de `new` lors de la création d’un objet .NET et qui `gcnew` retourne un handle (`^`) au lieu d’un pointeur (`*`) :  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     Pour plus d’informations sur la nouvelle syntaxe Visual C++, consultez [Extensions du composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md).  
  
7.  Dans le menu **Générer** , cliquez sur **Générer la solution**.  
  
     Le **sortie** fenêtre affiche des informations sur la progression de la compilation, telles que l’emplacement du journal de génération et un message qui indique l’état de la build.  
  
     Si vous modifiez et exécutez le programme sans effectuer une génération, une boîte de dialogue peut indiquer que le projet est obsolète. Sélectionnez la case à cocher dans cette boîte de dialogue avant de cliquer sur **OK** si vous souhaitez que Visual Studio utilisent toujours les dernières versions des fichiers au lieu de vous inviter chaque fois qu’il génère l’application.  
  
8.  Sur le **déboguer** menu, cliquez sur **démarrer sans débogage**.  
  
9. Si vous avez utilisé l’exemple de programme, lorsque vous exécutez le programme d’une fenêtre de commande s’affiche qui indique le fichier texte a été créé. Appuyez sur n’importe quelle touche pour fermer la fenêtre de commande.  
  
     Le **textfile.txt** fichier texte se trouve désormais dans votre répertoire de projet. Vous pouvez ouvrir ce fichier à l’aide du bloc-notes.  
  
    > [!NOTE]
    >  En choisissant le CLR vide le modèle de projet définit automatiquement le **/CLR** option du compilateur. Pour vérifier cela, cliquez sur le projet dans **l’Explorateur de solutions** et en cliquant sur **propriétés**, puis vérifiez la **prise en charge du Common Language Runtime** option dans le  **Général** nœud de **propriétés de Configuration**.  
  
## <a name="whats-next"></a>Étapes suivantes  
 **Précédente :** [procédure pas à pas : compilation d’un programme C++ natif sur la ligne de commande](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **Suivant :**[procédure pas à pas : compilation d’un programme C sur la ligne de commande](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Génération de programmes C/C++](../build/building-c-cpp-programs.md)