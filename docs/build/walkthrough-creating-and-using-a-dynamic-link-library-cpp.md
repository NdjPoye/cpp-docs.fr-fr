---
title: "Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation et utilisation d&#39;une biblioth&#232;que de liens dynamiques (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), procédures pas à pas"
  - "bibliothèques (C++), DLL"
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
caps.latest.revision: 36
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation et utilisation d&#39;une biblioth&#232;que de liens dynamiques (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette procédure pas à pas indique comment créer une bibliothèque de liens dynamiques \(DLL\) utilisable avec une application C\+\+.  L'utilisation d'une bibliothèque est un excellent moyen de réutiliser le code.  Au lieu d'implémenter les mêmes routines dans chaque programme que vous créez, vous les écrivez une seule fois, puis vous les référencez dans les applications qui requièrent ces fonctionnalités.  En plaçant du code dans la DLL, vous économisez de l'espace dans chaque application qui la référence, et vous pouvez mettre à jour la DLL sans recompiler toutes les applications.  Pour plus d'informations sur les DLL, voir [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md).  
  
 Cette procédure pas à pas couvre les tâches suivantes :  
  
-   Création d'un projet de DLL  
  
-   Ajout d'une classe dans la DLL  
  
-   Création d'une application console qui utilise la liaison dynamique au moment du chargement pour référencer la DLL  
  
-   Utilisation des fonctionnalités de la classe dans l'application  
  
-   Exécution de l'application  
  
 Cette procédure pas à pas crée une DLL pouvant être appelée uniquement à partir d'applications qui utilisent les conventions d'appel C\+\+.  Pour obtenir des informations sur la manière de créer des DLL utilisables avec d'autres langages, consultez [Appel de fonctions de la DLL à partir d'applications Visual Basic](../build/calling-dll-functions-from-visual-basic-applications.md).  
  
## Composants requis  
 Cette rubrique suppose que vous comprenez les notions de base du langage C\+\+.  
  
### Pour créer un projet de bibliothèque de liens dynamiques \(DLL\)  
  
1.  Dans la barre de menus, sélectionnez **Fichier**, **Nouveau**, **Projet**.  
  
2.  Dans le volet gauche de la boîte de dialogue **Nouveau projet**, développez **Installés**, **Modèles**, **Visual C\+\+**, puis sélectionnez **Win32**.  
  
3.  Dans le volet central, sélectionnez **Application console Win32**.  
  
4.  Spécifiez un nom pour le projet \(par exemple, MathFuncsDll\) dans la zone **Nom**.  Spécifiez un nom pour la solution \(par exemple, DynamicLibrary\) dans la zone **Nom de la solution**.  Sélectionnez le bouton **OK**.  
  
5.  Dans la page **Vue d'ensemble** de la boîte de dialogue **Assistant Application Win32**, choisissez le bouton **Suivant**.  
  
6.  Dans la page **Paramètres de l'application** sous **Type d'application**, sélectionnez **DLL**.  
  
7.  Choisissez le bouton **Terminer** pour créer le projet.  
  
### Pour ajouter une classe à la bibliothèque de liens dynamiques  
  
1.  Pour créer un fichier d'en\-tête pour une nouvelle classe, dans la barre de menus, choisissez **Projet**, **Ajouter un nouvel élément**.  Dans la boîte de dialogue **Ajouter un nouvel élément**, dans le volet gauche, sous **Visual C\+\+**, sélectionnez **Code**.  Dans le volet central, sélectionnez **Fichier d'en\-tête \(.h\)**.  Spécifiez un nom pour le fichier d'en\-tête \(par exemple, MathFuncsDll.h\), puis choisissez le bouton **Ajouter**.  Un fichier d'en\-tête vierge s'affiche.  
  
2.  Ajoutez le code suivant au début du fichier d'en\-tête :  
  
     [!code-cpp[NVC_Create_DLL_Walkthrough#100](../build/codesnippet/CPP/walkthrough-creating-and-using-a-dynamic-link-library-cpp_1.h)]  
  
3.  Ajoutez une classe élémentaire nommée MyMathFuncs pour effectuer des opérations mathématiques courantes telles que l'addition, la soustraction, la multiplication et la division.  Le code doit se présenter comme suit :  
  
     [!code-cpp[NVC_Create_DLL_Walkthrough#101](../build/codesnippet/CPP/walkthrough-creating-and-using-a-dynamic-link-library-cpp_2.h)]  
  
     Quand le symbole MATHFUNCSDLL\_EXPORTS est défini, le symbole MATHFUNCSDLL\_API définira le modificateur `__declspec(dllexport)` dans les déclarations des fonctions membres dans ce code.  Ce modificateur permet à la fonction d'être exportée par la DLL afin d'être utilisée par d'autres applications.  Quand MATHFUNCSDLL\_EXPORTS n'est pas défini \(par exemple, quand le fichier d'en\-tête est inclus par une application\) MATHFUNCSDLL\_API définit le modificateur `__declspec(dllimport)` dans les déclarations des fonctions membres.  Ce modificateur optimise l'importation de la fonction dans une application.  Par défaut, le modèle Nouveau projet pour une DLL ajoute `PROJECTNAME`\_EXPORTS aux symboles définis pour le projet de DLL.  Dans cet exemple, MATHFUNCSDLL\_EXPORTS est défini quand votre projet MathFuncsDll est généré.  Pour plus d'informations, voir [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
    > [!NOTE]
    >  Si vous générez le projet de DLL sur la ligne de commande, utilisez l'option **\/D** du compilateur pour définir le symbole MATHFUNCSDLL\_EXPORTS.  
  
4.  Dans le projet **MathFuncsDll**, dans l'**Explorateur de solutions**, dans le dossier **Fichiers sources**, ouvrez MathFuncsDll.cpp.  
  
5.  Implémentez les fonctionnalités pour MyMathFuncs dans ce fichier source.  Le code doit se présenter comme suit :  
  
     [!code-cpp[NVC_Create_DLL_Walkthrough#110](../build/codesnippet/CPP/walkthrough-creating-and-using-a-dynamic-link-library-cpp_3.cpp)]  
  
6.  Compilez la bibliothèque de liens dynamiques en choisissant **Générer**, puis **Générer la solution** dans la barre de menus.  
  
    > [!NOTE]
    >  Si vous utilisez une édition Express qui n'affiche pas de menu **Générer**, dans la barre de menus, choisissez **Outils**, **Paramètres**, **Paramètres avancés** pour l'activer, puis choisissez **Générer** et **Générer la solution**.  
  
    > [!NOTE]
    >  Si vous générez un projet sur la ligne de commande, utilisez l'option **\/LD** du compilateur pour spécifier que le fichier de sortie doit être une DLL.  Pour plus d'informations, voir [\/MD, \/MT, \/LD \(Utiliser la bibliothèque Runtime\)](../build/reference/md-mt-ld-use-run-time-library.md).  Utilisez l'option **\/EHsc** du compilateur pour activer la gestion des exceptions C\+\+.  Pour plus d'informations, voir [\/EH \(Modèle de gestion des exceptions\)](../build/reference/eh-exception-handling-model.md).  
  
### Pour créer une application qui référence la DLL  
  
1.  Pour créer une application C\+\+ qui référence et utilise la DLL que vous venez de créer, dans la barre de menus, choisissez **Fichier**, **Nouveau**, puis **Projet**.  
  
2.  Dans le volet gauche, sous **Visual C\+\+**, sélectionnez **Win32**.  
  
3.  Dans le volet central, sélectionnez **Application console Win32**.  
  
4.  Spécifiez un nom pour le projet \(par exemple, MyExecRefsDll\) dans la zone **Nom**.  Dans la liste déroulante, en regard de **Solution**, sélectionnez **Ajouter à la solution**.  Le nouveau projet est ajouté à la solution qui contient la DLL.  Sélectionnez le bouton **OK**.  
  
5.  Dans la page **Vue d'ensemble** de la boîte de dialogue **Assistant Application Win32**, choisissez le bouton **Suivant**.  
  
6.  Dans la page **Paramètres de l'application** sous **Type d'application**, sélectionnez **Application console**.  
  
7.  Dans la page **Paramètres de l'application**, sous **Options supplémentaires**, décochez la case **En\-tête précompilé**.  
  
8.  Choisissez le bouton **Terminer** pour créer le projet.  
  
### Pour utiliser les fonctionnalités de la bibliothèque de classes dans l'application  
  
1.  Une fois que vous avez créé une application console, un programme vide est créé à votre intention.  Le nom du fichier source est identique au nom que vous avez choisi précédemment.  Dans cet exemple, il s'agit de MyExecRefsDll.cpp.  
  
2.  Pour pouvoir utiliser dans l'application les routines mathématiques que vous avez créées dans la DLL, vous devez la référencer.  Pour cela, sélectionnez le projet MyExecRefsDll dans l'**Explorateur de solutions**, puis, dans la barre de menus, choisissez **Projet** et **Références**.  Dans la boîte de dialogue **Pages de propriétés**, développez le nœud **Propriétés communes**, sélectionnez **Structure et références**, puis choisissez le bouton **Ajouter une nouvelle référence**.  Pour plus d'informations sur la boîte de dialogue **Références**, consultez [Ajout de références](../ide/adding-references-in-visual-cpp-projects.md).  
  
3.  La boîte de dialogue **Ajouter une référence** répertorie les bibliothèques que vous pouvez référencer.  L'onglet **Projet** répertorie les projets figurant dans la solution actuelle et toutes les bibliothèques qu'ils contiennent.  Sous l'onglet **Projets**, cochez la case en regard de MathFuncsDll, puis choisissez le bouton **OK**.  
  
4.  Pour référencer les fichiers d'en\-tête de la DLL, vous devez modifier le chemin d'accès aux répertoires inclus.  Pour cela, dans la boîte de dialogue **Pages de propriétés**, développez le nœud **Propriétés de configuration** puis le nœud **C\/C\+\+**, puis sélectionnez **Général**.  En regard de **Autres répertoires Include**, spécifiez le chemin d'accès de l'emplacement du fichier d'en\-tête MathFuncsDll.h.  Vous pouvez utiliser un chemin d'accès relatif \(par exemple, ..\\MathFuncsDll\\\), puis choisissez le bouton **OK**.  
  
5.  Vous pouvez maintenant utiliser la classe MyMathFuncs dans cette application.  Remplacez le contenu du fichier MyExecRefsDll.cpp par le code suivant :  
  
     [!code-cpp[NVC_Create_DLL_Walkthrough#120](../build/codesnippet/CPP/walkthrough-creating-and-using-a-dynamic-link-library-cpp_4.cpp)]  
  
6.  Générez le fichier exécutable en sélectionnant **Générer**, **Générer la solution** dans la barre de menus.  
  
### Pour exécuter l'application  
  
1.  Assurez\-vous que MyExecRefsDll est sélectionné en tant que projet par défaut.  Dans l'**Explorateur de solutions**, sélectionnez MyExecRefsDll, puis, dans la barre de menus, choisissez **Projet** et **Définir comme projet de démarrage**.  
  
2.  Pour exécuter le projet, dans la barre de menus, choisissez **Exécuter sans débogage** dans le menu **Débogage**.  La sortie doit ressembler à ceci :  
  
  **a \+ b \= 106.4**  
**a \- b \= \-91.6**  
**a \* b \= 732.6**  
**a \/ b \= 0.0747475**  
**Caught exception: b cannot be zero\!**  
  
## Voir aussi  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Procédure pas à pas : déploiement de votre programme \(C\+\+\)](../ide/walkthrough-deploying-your-program-cpp.md)   
 [Appel de fonctions de la DLL à partir d'applications Visual Basic](../build/calling-dll-functions-from-visual-basic-applications.md)