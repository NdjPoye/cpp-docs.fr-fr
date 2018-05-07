---
title: Création d’un projet Makefile | Documents Microsoft
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc854f96f1c41baf28a5af4ca1f253e47d9a8914
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-makefile-project"></a>Création d'un projet Makefile

Si vous avez un projet de code source existant que vous générez à partir de la ligne de commande à l’aide d’un makefile, l’environnement de développement Visual Studio dispose de plusieurs méthodes de lui affecter la valeur dans un projet qui peut tirer pleinement parti des fonctionnalités de l’IDE de Visual Studio. Cet article décrit comment créer un projet Makefile de Visual Studio qui utilise votre makefile existant pour générer votre code dans l’IDE. Vous pouvez également utiliser le **créer un projet à partir de fichiers de Code existants** Assistant pour créer un projet MSBuild natif à partir de votre code source. Pour plus d’informations, consultez [Guide pratique pour créer un projet C++ à partir d’un code existant](how-to-create-a-cpp-project-from-existing-code.md). À partir de Visual Studio 2017, vous pouvez également utiliser le **ouvrir le dossier** fonctionnalité, qui peut utiliser plusieurs systèmes de build existants comme s’ils étaient les projets natifs Visual Studio. Pour plus d’informations, consultez [Open Folder projects in Visual C++](non-msbuild-projects.md).

Pour utiliser Visual Studio pour ouvrir et générer votre code source à l’aide de votre makefile existant, vous créez tout d’abord un nouveau projet en sélectionnant le modèle de projet MakeFile. Un Assistant vous permet de spécifier les commandes et l’environnement utilisé par votre makefile. Vous pouvez ensuite utiliser ce projet pour générer votre code dans l’environnement de développement Visual Studio.

Par défaut, le projet makefile n’affiche aucun fichier dans l’Explorateur de solutions. Le projet makefile spécifie les paramètres de génération, qui sont répercutées dans la page de propriétés du projet.

Le fichier de sortie que vous spécifiez dans le projet n'a pas d'incidence sur le nom que le script génère ; il déclare uniquement une intention. Votre fichier Make toujours contrôle le processus de génération et spécifie les cibles de génération.

## <a name="to-create-a-makefile-project"></a>Pour créer un projet Makefile

1. Suivez les instructions de la rubrique d’aide [création d’un projet avec l’Assistant Application Visual C++](../ide/creating-desktop-projects-by-using-application-wizards.md).

1. Dans le **nouveau projet** boîte de dialogue, développez **Visual C++** > **général** , puis sélectionnez **projet Makefile** dans le Volet Modèles pour ouvrir l’Assistant de projet.

1. Dans le [paramètres de l’Application](../ide/application-settings-makefile-project-wizard.md) , fournissez la commande de sortie, nettoyer et génère des informations de reconstruction pour le débogage et de la vente au détail.

1. Cliquez sur **Terminer** pour fermer l’Assistant et ouvrir le projet nouvellement créé dans **l’Explorateur de solutions**.

Vous pouvez afficher et modifier les propriétés du projet dans sa page de propriétés. Consultez [définition des propriétés de projet Visual C++](../ide/working-with-project-properties.md) pour plus d’informations sur l’affichage de la page de propriétés.

## <a name="see-also"></a>Voir aussi

[Projet Makefile (Assistant)](../ide/makefile-project-wizard.md)<br/>
[Caractères spéciaux dans un makefile](../build/special-characters-in-a-makefile.md)<br/>
[Contenu d’un makefile](../build/contents-of-a-makefile.md)<br/>
