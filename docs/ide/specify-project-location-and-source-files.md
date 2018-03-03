---
title: "Nouveau projet à partir de Code existant - fichiers de code Source (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.importwiz.location
dev_langs:
- C++
ms.assetid: 29ddffb9-5918-4d72-8c7a-a365f9de96dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04f73f89745f797658029eac2331d1764af4c065
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="specify-project-location-and-source-files-create-new-project-from-existing-code-files-wizard"></a>Spécifier l'emplacement du projet et les fichiers sources, Assistant Créer un projet à partir de fichiers de code existants
Utilisez cette page de l’Assistant créer un projet à partir de fichiers de Code existants pour spécifier :  
  
-   Le chemin d’accès du répertoire du nouveau projet  
  
-   Les répertoires pour rechercher des fichiers de code source existant  
  
-   Les types de fichiers que l’Assistant va importer dans le nouveau projet  
  
## <a name="task-list"></a>Liste des tâches  
 [Guide pratique pour créer un projet C++ à partir d’un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Emplacement du fichier projet**  
 Spécifie le chemin d’accès du répertoire du nouveau projet. Cet emplacement est où l’Assistant sera déposer tous les fichiers (et dans les sous-répertoires) du nouveau projet.  
  
 **Parcourir**  
 Affiche la **emplacement du fichier de projet** boîte de dialogue qui vous permet de spécifier le répertoire qui contiendra le nouveau projet. Ce contrôle vous permet de naviguer vers le dossier de votre choix.  
  
 **Nom du projet**  
 Spécifie le nom du nouveau projet. Fichiers de projet, qui ont les extensions de fichier .vcxproj adoptent ce nom. Fichiers de code existants conserve son nom d’origine.  
  
 **Ajouter des fichiers au projet à partir de ces dossiers.**  
 Lorsqu’elle est activée, définit l’Assistant pour copier des fichiers de code existants à partir de leurs répertoires d’origine (qui sont spécifiés dans la zone de liste sous ce contrôle) dans le nouveau projet.  
  
 **Ajouter les sous-dossiers**  
 Spécifie pour copier des fichiers de code à partir de tous les sous-répertoires du répertoire répertoriées **dossier** colonne dans le nouveau projet.  
  
 **Dossier**  
 Indique le chemin d’accès au répertoire qui contient les fichiers de code existants à copier dans le nouveau projet. Cette colonne répertorie tous les répertoires que l’Assistant recherche les fichiers de code existants.  
  
 **Ajouter**  
 Affiche la **ajouter des fichiers au projet à partir de ce dossier** boîte de dialogue qui vous permet de spécifier les répertoires dans laquelle l’Assistant recherche les fichiers de code existants.  
  
 **Supprimer**  
 Supprime le chemin d’accès du répertoire est sélectionné dans la liste case à gauche de ce contrôle.  
  
 **Types de fichiers à ajouter au projet**  
 Spécifie les types de fichiers que l’Assistant ajoutera dans le nouveau projet basé sur les extensions de fichier donné. Extensions de fichier sont précédées du caractère générique astérisque et sont délimitées dans la liste des extensions de fichier par un point-virgule.  
  
 **Afficher tous les fichiers dans l’Explorateur de solutions**  
 Spécifie que tous les fichiers dans le nouveau projet pour être visible et affichée dans la fenêtre de l’Explorateur de solutions. Cette option est activée par défaut.