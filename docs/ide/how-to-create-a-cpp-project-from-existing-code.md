---
title: 'Comment : créer un projet C++ à partir de Code existant | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++, creating projects from existing code
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1786e5704d7afd07576ab738d907eb841518f8be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>Comment : créer un projet C++ à partir d'un code existant

Dans Visual Studio, vous pouvez déplacer vos fichiers de code existants dans un projet Visual C++ à l’aide de la **créer un projet à partir de fichiers de Code existants** Assistant. Cet Assistant n’est pas disponible dans les anciennes éditions Express de Visual Studio. Cet Assistant crée une solution et un projet qui utilise le système MSBuild pour gérer vos fichiers sources et de configuration de build.  
  
Portage de vos fichiers de code existants dans un projet Visual C++ vous permet d’utiliser toutes les fonctionnalités de gestion de projet MSBuild natives intégrées à l’IDE. Si vous préférez utiliser votre système de génération existants, tels que des makefiles nmake, CMake ou alternatives, vous pouvez utiliser l’option Ouvrir le dossier à la place. Pour plus d’informations, consultez [Open Folder projects in Visual C++](../ide/non-msbuild-projects.md). Les deux options vous permettent d’utiliser les fonctionnalités de l’IDE comme [IntelliSense](/visualstudio/ide/using-intellisense) et [propriétés du projet](../ide/working-with-project-properties.md).  
  
### <a name="to-create-a-c-project-from-existing-code"></a>Pour créer un projet C++ à partir de code existant  
  
1.  Sur le **fichier** menu, pointez sur **nouveau**, puis cliquez sur **projet à partir de Code existant**.  
  
1.  Sur la première page de la **créer un projet à partir de fichiers de Code existants** Assistant, sélectionnez **Visual C++** dans les **quel type de projet voulez-vous créer** liste. Choisissez **Suivant** pour continuer. 
  
1.  Spécifiez l’emplacement de votre projet et le répertoire de vos fichiers sources. Pour plus d’informations sur cette page, consultez [spécifier un emplacement de projet et les fichiers sources, Assistant créer un projet à partir d’existants Code fichiers](../ide/specify-project-location-and-source-files.md). Choisissez **Suivant** pour continuer.  
  
1.  Spécifiez les paramètres de projet à utiliser. Pour plus d’informations sur cette page, consultez [spécifier les paramètres de projet, Assistant créer un projet à partir d’existants Code fichiers](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md). Choisissez **Suivant** pour continuer.  

1.  Spécifiez les paramètres de configuration de débogage à utiliser. Pour plus d’informations sur cette page, consultez [spécifier les paramètres de Configuration Debug, Assistant créer un projet à partir d’existants Code fichiers](../ide/specify-debug-configuration-settings.md). Choisissez **Suivant** pour continuer.  

1.  Spécifiez les paramètres de configuration de version à utiliser. Pour plus d’informations sur cette page, consultez [spécifier les paramètres de Configuration Release, Assistant créer un projet à partir d’existants Code fichiers](../ide/specify-release-configuration.md). Choisissez **Terminer** pour générer le nouveau projet.  
  
## <a name="see-also"></a>Voir aussi  

[Spécifier le projet d’emplacement et les fichiers sources, créer un nouveau projet à partir de l’Assistant de fichiers de Code existants](../ide/specify-project-location-and-source-files.md)   
[Spécifier les paramètres de projet, de créer un nouveau projet à partir de l’Assistant de fichiers de Code existants](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)   
[Spécifier les paramètres de Configuration Debug, créez un nouveau projet à partir de l’Assistant de fichiers de Code existants](../ide/specify-debug-configuration-settings.md)   
[Spécifier les paramètres de configuration Release, Assistant Créer un projet à partir de fichiers de code existants](../ide/specify-release-configuration.md)