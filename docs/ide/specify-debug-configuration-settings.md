---
title: Nouveau projet à partir de Code existant déboguer paramètre (Visual C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.debugsettings
dev_langs:
- C++
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b40bafe817ebf1dd25cc40115635b895502e0df8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="specify-debug-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Spécifier les paramètres de configuration Debug, Assistant Créer un projet à partir de fichiers de code existants
Utilisez cette page de l’Assistant créer un projet à partir de fichiers de Code existants pour spécifier les paramètres de projet de configuration Debug.  
  
## <a name="task-list"></a>Liste des tâches  
 [Guide pratique pour créer un projet C++ à partir d’un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Ligne de commande build**  
 Spécifie la ligne de commande qui génère le nouveau projet. Par exemple, entrez le nom du compilateur (ainsi que les commutateurs et arguments) ou les scripts de génération que vous souhaitez utiliser pour générer le nouveau projet. Cette option est activée lorsque le **système de génération externe de l’utilisation** option est sélectionnée dans le **spécifier les paramètres de projet** page ; sinon, il n’est pas disponible.  
  
 **Ligne de commande Rebuild**  
 Spécifie la ligne de commande qui reconstruit le nouveau projet. Cette option est activée lorsque le **système de génération externe de l’utilisation** option est sélectionnée dans le **spécifier les paramètres de projet** page ; sinon, il n’est pas disponible.  
  
 **Ligne de commande Clean**  
 Spécifie la ligne de commande pour supprimer les fichiers de prise en charge générés par les outils de génération pour le nouveau projet. Cette option est activée lorsque le **système de génération externe de l’utilisation** option est sélectionnée dans le **spécifier les paramètres de projet** page ; sinon, il n’est pas disponible.  
  
 **Sortie (pour le débogage)**  
 Spécifie le chemin d’accès du répertoire des fichiers de sortie pour la configuration Debug du nouveau projet. Cette option est activée lorsque le **système de génération externe de l’utilisation** option est sélectionnée dans le **spécifier les paramètres de projet** page ; sinon, il n’est pas disponible.  
  
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
