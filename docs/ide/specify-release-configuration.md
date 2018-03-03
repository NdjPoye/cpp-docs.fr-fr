---
title: "Configuration de version du nouveau projet à partir de Code existant | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.importwiz.releasesettings
dev_langs:
- C++
ms.assetid: 3e2fc73c-bdbd-4790-b2bd-d31731f0cece
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff208af8bb89dbcb7df00b37ce542a5adae5fa23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="specify-release-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Spécifier les paramètres de configuration Release, Assistant Créer un projet à partir de fichiers de code existants
Utilisez cette page de l’Assistant créer un projet à partir de fichiers de Code existants pour spécifier les paramètres de configuration Release.  
  
## <a name="task-list"></a>Liste des tâches  
 [Guide pratique pour créer un projet C++ à partir d’un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Identique à la configuration Debug**  
 Spécifie que l’Assistant générera les paramètres de configuration Release identiques pour les paramètres de configuration Debug. Cette option est activée par défaut. Toutes les autres options de cette page sont inactives, sauf si vous décochez cette case.  
  
 **Ligne de commande build**  
 Spécifie la ligne de commande qui génère le nouveau projet. Entrez le nom du compilateur ainsi que les commutateurs ou les arguments que vous souhaitez utiliser pour générer le nouveau projet. Cette option est activée lorsque le **système de génération externe de l’utilisation** option est sélectionnée dans le **spécifier les paramètres de projet** page.  
  
 **Ligne de commande Rebuild**  
 Spécifie la ligne de commande qui reconstruit le nouveau projet. Cette option est activée lorsque le **système de génération externe de l’utilisation** option est sélectionnée dans le **spécifier les paramètres de projet** page.  
  
 **Ligne de commande Clean**  
 Spécifie la ligne de commande pour supprimer les fichiers de prise en charge générés par les outils de génération pour le nouveau projet. Cette option est activée lorsque le **système de génération externe de l’utilisation** option est sélectionnée dans le **spécifier les paramètres de projet** page.  
  
 **Sortie (pour le débogage)**  
 Spécifie le chemin d’accès du répertoire des fichiers de sortie pour la configuration Debug du nouveau projet. Cette option est activée lorsque le **système de génération externe de l’utilisation** option est sélectionnée dans le **spécifier les paramètres de projet** page.  
  
 **Définitions de préprocesseur (/ D)**  
 Définit les symboles de préprocesseur pour le nouveau projet. Pour plus d'informations, consultez [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md).  
  
 **Chemin de recherche Include (/ I)**  
 Spécifie les chemins d’accès pour l’ajouter à la liste des répertoires dans lesquels le compilateur recherche pour résoudre les références de fichier passées aux directives de préprocesseur dans le nouveau projet. Pour plus d’informations, consultez l’article [/I (Autres répertoires Include)](../build/reference/i-additional-include-directories.md).  
  
 **Fichiers Include forcés (/ Fi)**  
 Spécifie les fichiers d’en-tête à traiter lors de la création du nouveau projet. Pour plus d’informations, consultez l’article [/FI (Nom du fichier Include imposé)](../build/reference/fi-name-forced-include-file.md).  
  
 **Chemin de recherche des assemblys .NET (/ AI)**  
 Spécifie les chemins d’accès de répertoire que le compilateur recherche pour résoudre les références d’assembly .NET passées aux directives de préprocesseur dans le nouveau projet. Pour plus d’informations, consultez l’article [/AI (Spécifier les répertoires des métadonnées)](../build/reference/ai-specify-metadata-directories.md).  
  
 **Utilisation forcée des assemblys du .NET (/ /FU)**  
 Spécifie les assemblys .NET à traiter lors de la création du nouveau projet. Pour plus d’informations, consultez l’article [/FU (Nom du fichier #using imposé)](../build/reference/fu-name-forced-hash-using-file.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Spécifier les paramètres du projet, Assistant Créer un projet à partir de fichiers de code existants](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)