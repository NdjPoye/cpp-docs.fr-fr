---
title: Écriture et refactorisation du code (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/27/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02a028ddf5cbd4ac33f1ff9b148e7f20e5114c69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="writing-and-refactoring-code-c"></a>Écriture et refactorisation du code (C++)

L'IDE et l'éditeur de code Visual C++ fournissent de nombreux outils de codage. Certains sont propres à C++, alors que d'autres sont quasiment identiques pour tous les langages Visual Studio. Pour plus d’informations sur les fonctionnalités partagées, consultez [l’écriture de Code dans l’éditeur de texte et le Code](/visualstudio/ide/writing-code-in-the-code-and-text-editor). Options d’activation et configuration des fonctionnalités propres à C++ se trouvent dans le [avancées C++ de l’éditeur de texte](/visualstudio/ide/reference/options-text-editor-c-cpp-advanced) boîte de dialogue (**outils &#124; Options &#124; éditeur de texte &#124; C/C++ &#124; avancé** ou tapez « Avancées C++ » dans **lancement rapide**). Après avoir choisi l’option que vous souhaitez définir, vous pouvez obtenir de l’aide en appuyant sur **F1** lorsque la boîte de dialogue est dans le focus. Pour les options de mise en forme de code général, tapez `Editor C++` dans **lancement rapide**.

Les fonctionnalités expérimentales, ce qui peut ou ne peuvent pas être incluses dans une future version de Visual Studio, sont trouvent dans le [éditeur de texte C++ expérimental](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) boîte de dialogue. Dans Visual Studio 2017, vous pouvez activer **Intellisense prédictive** dans cette boîte de dialogue.

## <a name="adding-new-code"></a>Ajout de code

Après avoir créé un projet, vous pouvez commencer à coder dans les fichiers qui ont été générés pour vous. Pour ajouter de nouveaux fichiers, avec le bouton droit sur le nœud de projet dans l’Explorateur de solutions et choisissez **ajouter &#124; nouveau**.

Pour définir la mise en forme des options telles que les retraits, saisie semi-automatique des accolades et la colorisation, tapez `C++ Formatting` dans les **lancement rapide** fenêtre.

### <a name="intellisense"></a>IntelliSense

IntelliSense est le nom d’un ensemble de fonctionnalités qui fournissent des informations inline sur les membres, les types et les surcharges de fonction. L'illustration suivante montre la liste déroulante des membres qui s'affiche quand vous commencez à taper. Vous pouvez appuyer sur la touche Tab pour entrer le texte de l'élément sélectionné dans votre fichier de code.

![C&#43; &#43; membre liste déroulante](../ide/media/vs2015_cpp_statement_completion.png "vs2015_cpp_statement_completion")

Pour plus d’informations, consultez [Intellisense Visual C++](/visualstudio/ide/visual-cpp-intellisense).

### <a name="insert-snippets"></a>Insérer des extraits de code

Un extrait de code est un bloc de code source prédéfini. Cliquez avec le bouton droit sur un point précis ou sur le texte sélectionné pour insérer un extrait de code ou entourer le texte sélectionné de l'extrait de code. L'illustration ci-dessous montre les trois étapes à suivre pour entourer une instruction sélectionnée d'une boucle for. Les éléments en jaune dans l'image finale sont des champs modifiables auxquels vous accédez avec la touche Tab. Pour plus d’informations, consultez [Extraits de code](/visualstudio/ide/code-snippets).

![Visual C&#43; &#43; insérer le supprimer extrait&#45;vers le bas](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

### <a name="add-class"></a>Ajouter une classe

Ajoutez une nouvelle classe à partir de la **projet** menu à l’aide de l’Assistant classe.

![Ajouter une nouvelle classe dans Visual C#&#43;&#43;](../ide/media/vs2015_cpp_add_class.png "vs2015_cpp_add_class")

### <a name="class-wizard"></a>Assistant Classe

Modifiez ou examinez une classe existante, ou ajoutez une nouvelle classe, à l'aide de l'Assistant Classe. Pour plus d’informations, consultez [Ajout de fonctionnalités avec les Assistants Code (C++)](../ide/adding-functionality-with-code-wizards-cpp.md).

![Visual C&#43; &#43; classe Assistant](../ide/media/vs2015_cpp_class_wizard.png "vs2015_cpp_class_wizard")

## <a name="refactoring"></a>Refactorisation

Refactorisations sont disponibles sous le menu contextuel Action rapide ou en cliquant sur un [ampoule](/visualstudio/ide/perform-quick-actions-with-light-bulbs) dans l’éditeur.  Certains se trouvent également dans le **Modifier > refactoriser** menu.  Ces fonctions incluent :

* [Renommer](refactoring/rename.md)
* [Extraire la fonction](refactoring/extract-function.md)
* [Implémenter les virtuels purs](refactoring/implement-pure-virtuals.md)
* [Créer la déclaration/la définition](refactoring/create-declaration-definition.md)
* [Définition de fonction move](refactoring/move-definition-location.md)
* [Convertir en littéral de chaîne brute](refactoring/convert-to-raw-string-literal.md)
* [Modifier la signature](refactoring/change-signature.md)

## <a name="navigate-and-understand"></a>Naviguer et comprendre

Visual C++ partage plusieurs fonctionnalités de navigation de code avec d’autres langages. Pour plus d’informations, consultez [navigation dans le Code](/visualstudio/ide/navigating-code) et [affichage de la Structure du Code](/visualstudio/ide/viewing-the-structure-of-code).

### <a name="quickinfo"></a>Info express

Placez le curseur sur une variable pour afficher des informations sur son type.

![Info Express Visual C++](../ide/media/vs2015_cpp_quickinfo.png "vs2015_cpp_quickInfo")

### <a name="open-document-navigate-to-header"></a>Ouvrir le document (accéder à l'en-tête)

Cliquez avec le bouton droit sur le nom d'en-tête dans une directive `#include` et ouvrez le fichier d'en-tête.

![Visual C&#43; &#43; option de menu Ouvrir un Document](../ide/media/vs2015_cpp_open_document.png "vs2015_cpp_open_document")

### <a name="peek-definition"></a>Aperçu de définition

Placez le curseur sur une variable ou une fonction déclaration, avec le bouton droit, puis choisissez **aperçu de définition** pour afficher une vue en ligne de sa définition. Pour plus d’informations, consultez [aperçu de définition (Alt + F12)](/visualstudio/ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12).

![Visual C&#43; &#43; aperçu de définition](../ide/media/vs2015_cpp_peek_definition.png "vs2015_cpp_peek_definition")

### <a name="go-to-definition"></a>Atteindre la définition

Placez le curseur sur une variable ou une fonction déclaration, avec le bouton droit, puis choisissez **atteindre la définition** pour ouvrir le document dans lequel l’objet est défini.

### <a name="view-call-hierarchy"></a>Afficher la hiérarchie d'appels

Cliquez avec le bouton droit sur un appel de fonction et affichez une liste récursive de toutes les fonctions qui sont appelées et de toutes les fonctions qui l'appellent. Chaque fonction de la liste peut être développée de la même façon. Pour plus d’informations, consultez [hiérarchie d’appels](/visualstudio/ide/reference/call-hierarchy).

![Visual C&#43; &#43; hiérarchie d’appels](../ide/media/vs2015_cpp_call_hierarchy.png "vs2015_cpp_call_hierarchy")

### <a name="toggle-header--code-file"></a>Afficher ou masquer l'en-tête / le fichier de code

Avec le bouton droit et choisissez **bascule en-tête / fichier de Code** pour basculer entre un fichier d’en-tête et de son fichier de code associé.

### <a name="outlining"></a>mode Plan

Avec le bouton droit n’importe où dans un fichier de code source et choisissez **mode plan** pour réduire ou développer les définitions et/ou les régions personnalisées pour faciliter la parcourir uniquement les parties qui vous intéressez. Pour plus d’informations, voir [Mode Plan](/visualstudio/ide/outlining).

![Visual C&#43; &#43; mise en relief](../ide/media/vs2015_cpp_outlining.png "vs2015_cpp_outlining")

### <a name="scroll-bar-map-mode"></a>Mode mappage pour la barre de défilement

Le mode mappage pour la barre de défilement vous permet de faire défiler et parcourir un fichier de code rapidement, sans avoir à quitter votre emplacement actuel. Ou cliquez n’importe où sur la carte du code pour accéder directement à cet emplacement.

![Code de mappage dans Visual C#&#43;&#43;](../ide/media/vs2015_cpp_code_map.png "vs2015_cpp_code_map")

### <a name="generate-graph-of-include-files"></a>Générer le graphique des fichiers Include

Cliquez avec le bouton droit sur un fichier de code dans votre projet et choisissez **générer le graphique des fichiers include** pour afficher un graphique montrant les fichiers sont inclus par d’autres fichiers.

![Visual C&#43; &#43; graphique des fichiers include](../ide/media/vs2015_cpp_include_graph.png "vs2015_cpp_include_graph")

### <a name="f1-help"></a>F1 Aide

Placez le curseur sur ou juste après un type, un mot clé ou une fonction et appuyez sur F1 pour accéder directement à la rubrique de référence MSDN associée. F1 fonctionne également sur les éléments de la liste d'erreurs et dans de nombreuses boîtes de dialogue.

### <a name="quick-launch"></a>Lancement rapide

Pour accéder facilement à une fenêtre ou à un outil dans Visual Studio, tapez simplement son nom dans la fenêtre de lancement rapide dans le coin supérieur droit de l'interface utilisateur. La liste de saisie semi-automatique est filtrée à mesure que vous tapez.

![Lancement rapide Visual Studio](../ide/media/vs2015_cpp_quick_launch.png "vs2015_cpp_quick_launch")
