---
title: "Spécifier les paramètres de projet, créez le projet à partir de l’Assistant de fichiers de Code existants | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.importwiz.appsettings
dev_langs:
- C++
helpviewer_keywords:
- Create New Project From Existing Code Files Wizard, project settings
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cf1e8eba11063f7f2e46f836cd2ef84cc70dfe8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="specify-project-settings-create-new-project-from-existing-code-files-wizard"></a>Spécifier les paramètres du projet, Assistant Créer un projet à partir de fichiers de code existants
Utilisez cette page de l’Assistant créer un projet à partir de fichiers de Code existants pour spécifier :  
  
-   L’environnement de génération pour le nouveau projet  
  
-   Créer des paramètres pour correspondre à un type spécifique de nouveau projet à générer  
  
## <a name="task-list"></a>Liste des tâches  
 [Guide pratique pour créer un projet C++ à partir d’un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>Liste UIElement  
 **Utilisez Visual Studio**  
 Spécifie l’utilisation des outils de génération qui sont inclus dans Visual Studio pour générer le nouveau projet. Cette option est activée par défaut.  
  
 **Type de projet**  
 Spécifie le type de projet que l’Assistant va générer.  
  
 **Projet d’application Windows**  
 Indique que l’Assistant générera un projet pour une application Windows exécutable. Cette option est disponible à partir de la **Type de projet** zone de liste déroulante.  
  
 **Projet d’application console**  
 Indique que l’Assistant générera un projet pour une application console. Cette option est disponible à partir de la **Type de projet** zone de liste déroulante.  
  
 **Projet de bibliothèque de liens dynamiques (DLL)**  
 Indique que l’Assistant générera un projet pour une application de bibliothèque de liens dynamiques vide. Cette option est disponible à partir de la **Type de projet** zone de liste déroulante.  
  
 **Projet de bibliothèque statique (LIB)**  
 Indique que l’Assistant générera un projet pour une application de bibliothèque statique. Cette option est disponible à partir de la **Type de projet** zone de liste déroulante.  
  
 **Ajouter la prise en charge ATL**  
 Ajoute la prise en charge ATL au nouveau projet.  
  
 **Ajouter la prise en charge des MFC**  
 Ajoute la prise en charge MFC pour le nouveau projet.  
  
 **Ajouter la prise en charge pour le Common Language Runtime**  
 Ajoute la prise en charge pour le nouveau projet de programmation du CLR.  
  
 **Common Language Runtime**  
 Spécifie le nouveau projet pour être conforme aux fonctionnalités CLR.  
  
 **Common Language Runtime (ancienne syntaxe)**  
 Spécifie le nouveau projet pour être compatibles avec les Extensions managées pour la syntaxe C++, qui est la syntaxe de programmation CLR avant Visual C++ 2005.  
  
 **Utiliser le système de génération externe**  
 Spécifie l’utilisation des outils de génération qui ne sont pas inclus dans Visual Studio pour générer le nouveau projet. Lorsque cette option est sélectionnée, vous pouvez spécifier les lignes de commande build sur la **spécifier les paramètres de Configuration Debug** et **spécifier les paramètres de Configuration Release** pages.  
  
> [!NOTE]
>  Lorsque le **utilisez un système de génération externe** option est activée, l’IDE ne génère pas le nouveau projet, donc la d, / I, / Fi, /AI ou /FU options ne sont pas requises pour la compilation. Toutefois, ces options doivent être définies correctement pour qu’IntelliSense fonctionne correctement.  
  
## <a name="see-also"></a>Voir aussi  
 [Spécifier les paramètres de Configuration Debug, créez un nouveau projet à partir de l’Assistant de fichiers de Code existants](../ide/specify-debug-configuration-settings.md)   
 [Spécifier les paramètres de configuration Release, Assistant Créer un projet à partir de fichiers de code existants](../ide/specify-release-configuration.md)