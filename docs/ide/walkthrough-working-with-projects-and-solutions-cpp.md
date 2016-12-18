---
title: "Proc&#233;dure pas &#224; pas&#160;: utilisation de projets et de solutions (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "projets (C++)"
  - "projets (C++), à propos des projets"
  - "solutions (C++)"
  - "solutions (C++), à propos des solutions"
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: utilisation de projets et de solutions (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Voici comment créer un projet C\+\+ dans Visual Studio, ajouter du code, puis générer et exécuter le projet.  Le projet dans cette procédure pas à pas est un programme qui assure le suivi du nombre de joueurs qui jouent à différents jeux de cartes.  
  
 Dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], le travail est organisé en projets et solutions.  Une solution peut contenir plusieurs projets, par exemple une DLL et un fichier exécutable référençant cette DLL.  Pour plus d'informations, consultez [Projets et solutions](../Topic/Solutions%20and%20Projects%20in%20Visual%20Studio.md).  
  
## Composants requis  
  
-   Pour compléter cette procédure pas à pas, vous devez comprendre les notions de base du langage C\+\+.  
  
## Création d'un projet  
 Pour créer un projet, choisissez d'abord un modèle de type de projet.  Pour chaque type de projet, [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] définit les paramètres de compilateur et, en fonction du type, génère du code de démarrage que vous pouvez modifier ultérieurement.  
  
#### Pour créer un projet  
  
1.  Dans la barre de menus, sélectionnez **Fichier**, **Nouveau**, **Projet**.  
  
2.  Dans le volet gauche de la boîte de dialogue **Nouveau projet**, développez le nœud **Modèles installés**, le nœud **Visual C\+\+**, puis sélectionnez **Win32**.  
  
3.  Dans la liste de modèles installés dans le volet central, sélectionnez **Application console Win32**.  
  
4.  Entrez un nom pour le projet dans la zone **Nom**.  Pour cet exemple, entrez Game.  
  
     Vous pouvez accepter l'emplacement par défaut dans la liste déroulante **Emplacement**, entrer un emplacement différent ou choisir le bouton **Parcourir** pour naviguer jusqu'à un répertoire où vous souhaitez enregistrer le projet.  
  
     Lorsque vous créez un projet, [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ajoute le projet à une solution.  Par défaut, la solution porte le même nom que le projet.  Vous pouvez modifier le nom dans la zone **Nom de la solution**, mais pour cet exemple, conservez le nom par défaut.  
  
     Choisissez le bouton **OK** pour démarrer l'**Assistant Application Win32**.  
  
5.  Dans la page **Vue d'ensemble** de l'**Assistant Application Win32**, choisissez le bouton **Suivant** .  
  
6.  Dans la page **Paramètres de l'application** sous **Type d'application**, sélectionnez **Application console**.  Sous **Options supplémentaires**, désactivez l'option **En\-tête précompilé**, puis sélectionnez le paramètre **Projet vide**.  Choisissez le bouton **Terminer** pour créer le projet.  
  
     Vous disposez maintenant d'un projet, mais pas encore de fichiers de code source.  
  
## Organisation des projets et des fichiers dans une solution  
 Vous pouvez utiliser l'**Explorateur de solutions** pour organiser et gérer les projets, fichiers et autres ressources dans votre solution.  
  
 Cette partie de la procédure pas à pas montre comment ajouter une classe au projet.  Lorsque vous ajoutez la classe, [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ajoute les fichiers .cpp et .h correspondants.  Ensuite, ajoutez un nouveau fichier de code source pour le programme principal qui teste la classe.  
  
#### Pour ajouter une classe à un projet  
  
1.  Si l'**Explorateur de solutions** n'est pas visible, dans la barre de menus, choisissez **Affichage**, puis **Explorateur de solutions**.  
  
2.  Dans l'**Explorateur de solutions**, ouvrez le menu contextuel du dossier **Fichiers d'en\-tête**, puis choisissez **Ajouter**, **Classe**.  
  
     Dans le volet gauche de la boîte de dialogue **Ajouter une classe**, développez le nœud **Visual C\+\+** et sélectionnez **C\+\+** puis, dans la liste de modèles installés dans le volet central, sélectionnez **Classe C\+\+**.  Choisissez le bouton **Ajouter**.  
  
3.  Dans **Assistant Classe C\+\+ générique**, entrez Cardgame dans la zone **Nom de la classe**.  Ne modifiez pas les noms de fichiers et les paramètres par défaut.  Choisissez le bouton **Terminer**.  
  
4.  Le fichier Cardgame.h est ouvert dans l'éditeur.  Effectuez les modifications suivantes :  
  
    -   Ajoutez deux membres de données privés après l'accolade gauche de la définition de classe.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)]  
  
    -   Modifiez le constructeur par défaut généré par Visual Studio.  Après le spécificateur d'accès `public:`, recherchez la ligne qui ressemble à ceci :  
  
         `Cardgame(void);`  
  
         Modifiez\-la pour prendre un paramètre de type `int` nommé Readers.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]  
  
    -   Après le destructeur par défaut, ajoutez une déclaration inline pour une fonction membre int statique nommée GetParticipants qui n'accepte aucun paramètre et retourne la valeur totalParticipants.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]  
  
5.  Après modification, le fichier Cardgame.h doit ressembler à cela :  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]  
  
     La ligne `#pragma once` indique au compilateur qu'il doit inclure le fichier une seule fois.  Pour plus d'informations, consultez [once](../preprocessor/once.md).  
  
     Pour plus d'informations sur les autres mots clés C\+\+ de ce fichier d'en\-tête, consultez [class](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [static](../misc/static-cpp.md) et [public](../cpp/public-cpp.md).  
  
6.  Choisissez l'onglet **Cardgame.cpp** dans le volet de modification pour l'ouvrir et le modifier.  
  
7.  Supprimez tout le contenu du fichier et remplacez\-le par ce code :  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]  
  
    > [!NOTE]
    >  Vous pouvez utiliser la saisie semi\-automatique lorsque vous écrivez du code.  Par exemple, si vous entrez le code suivant, vous pouvez taper pl ou tot puis appuyez sur Ctrl\+Espace afin que la saisie semi\-automatique termine d'entrer `players` ou `totalParticipants`.  
  
     Pour plus d'informations sur `#include`, consultez [\#include, directive](../preprocessor/hash-include-directive-c-cpp.md).  
  
## Ajout d'un fichier source  
 Maintenant, ajoutez un fichier de code source pour le programme principal qui teste la classe.  
  
#### Pour ajouter un nouveau fichier source  
  
1.  Dans l'**Explorateur de solutions**, ouvrez le menu contextuel du dossier **Fichiers sources**, puis choisissez **Ajouter**, **Nouvel élément**.  
  
     Dans la boîte de dialogue **Ajouter un nouvel élément**, dans le volet gauche, développez le nœud **Installé**, le nœud **Visual C\+\+**, puis sélectionnez **Code**.  Dans le volet central, sélectionnez **Fichier C\+\+ \(.cpp\)**.  
  
2.  Entrez TestGames.cpp dans la zone de texte **Nom**, puis choisissez le bouton **Ajouter**.  
  
3.  Dans la fenêtre de modification TestGames.cpp, entrez le code suivant.  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]  
  
## Génération et exécution d'un projet  
 Maintenant, générez le projet et exécutez l'application.  
  
#### Pour générer et exécuter le projet  
  
1.  Dans la barre de menus, choisissez **Générer**, puis **Générer la solution**.  
  
    > [!NOTE]
    >  Si vous utilisez une édition Express qui n'affiche pas de menu **Générer**, dans la barre de menus, sélectionnez **Outils**, **Paramètres**, **Paramètres avancés** pour l'activer.  
  
     La sortie de l'une génération est affichée dans la fenêtre **Sortie**.  Si la génération réussit, la sortie doit ressembler à ceci :  
  
  **1\>\-\-\-\-\-\- Génération démarrée : Projet : Game, Configuration : Débogage Win32 \-\-\-\-\-\-**  
**1\>  TestGames.cpp**  
**1\>  Cardgame.cpp**  
**1\>  Génération du code...**  
**1\>  Game.vcxproj \-\> c:\\users\\username\\documents\\visual studio\\Projects\\Game\\Debug\\Game.exe**  
**\=\=\=\=\=\=\=\=\=\= Génération : 1 a réussi, 0 a échoué, 0 mis à jour, 0 a été ignoré \=\=\=\=\=\=\=\=\=\=**     La fenêtre **Sortie** peut afficher différentes étapes, selon l'édition et la configuration de build, mais si la génération du projet réussit, la dernière ligne doit ressembler à la sortie indiquée.  
  
     Si la génération a échoué, comparez votre code au code fourni aux étapes précédentes.  
  
2.  Pour exécuter le projet, dans la barre de menus, choisissez **Exécuter sans débogage** dans le menu **Débogage**.  La sortie doit ressembler à ceci :  
  
  **4 players have started a new game.  There are now 4 players in total.**  
**8 players have started a new game.  There are now 12 players in total.**  
**1 players have started a new game.  There are now 13 players in total.**  
**5 players have started a new game.  There are now 18 players in total.**  
  
## Étapes suivantes  
 **Précédent :** [Utilisation de l'IDE de Visual Studio pour le développement de bureau C\+\+](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  **Suivant :** [Procédure pas à pas : génération d’un projet \(C\+\+\)](../ide/walkthrough-building-a-project-cpp.md).  
  
## Voir aussi  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)