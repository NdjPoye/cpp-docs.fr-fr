---
title: "Sp&#233;cifier les param&#232;tres de configuration Debug, Assistant Cr&#233;er un projet &#224; partir de fichiers de code existants | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.importwiz.debugsettings"
dev_langs: 
  - "C++"
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cifier les param&#232;tres de configuration Debug, Assistant Cr&#233;er un projet &#224; partir de fichiers de code existants
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant Créer un projet à partir de fichiers de code existants pour spécifier les paramètres du projet en configuration Debug.  
  
## Liste des tâches  
 [Comment : créer un projet C\+\+ à partir d'un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## Liste UIElement  
 **Ligne de commande build**  
 Spécifie la ligne de commande qui génère le nouveau projet.  Par exemple, entrez le nom du compilateur \(avec tous ses commutateurs et arguments\) ou les scripts de génération que vous souhaitez utiliser pour générer le nouveau projet.  Cette option est activée lorsque l'option **Utiliser un système de génération externe** est sélectionnée dans la page **Spécifier les paramètres du projet**. Autrement, elle n'est pas disponible.  
  
 **Ligne de commande Rebuild**  
 Spécifie la ligne de commande qui régénère le nouveau projet.  Cette option est activée lorsque l'option **Utiliser un système de génération externe** est sélectionnée dans la page **Spécifier les paramètres du projet**. Autrement, elle n'est pas disponible.  
  
 **Ligne de commande Clean**  
 Spécifie la ligne de commande pour supprimer les fichiers de prise en charge générés par les outils de génération du nouveau projet.  Cette option est activée lorsque l'option **Utiliser un système de génération externe** est sélectionnée dans la page **Spécifier les paramètres du projet**. Autrement, elle n'est pas disponible.  
  
 **Sortie \(pour le débogage\)**  
 Spécifie le chemin d'accès au répertoire des fichiers de sortie pour la configuration Debug du nouveau projet.  Cette option est activée lorsque l'option **Utiliser un système de génération externe** est sélectionnée dans la page **Spécifier les paramètres du projet**. Autrement, elle n'est pas disponible.  
  
 **Définitions de préprocesseur \(\/D\)**  
 Définit des symboles de préprocesseur pour le nouveau projet.  Pour plus d'informations, consultez [\/D \(Définitions de préprocesseur\)](../build/reference/d-preprocessor-definitions.md).  
  
 **Chemins de recherche Include \(\/I\)**  
 Spécifie les chemins d'accès à ajouter à la liste des répertoires dans lesquels le compilateur effectuera des recherches pour résoudre les références de fichier passées aux directives de préprocesseur dans le nouveau projet.  Pour plus d'informations, consultez [\/I \(Autres répertoires Include\)](../build/reference/i-additional-include-directories.md).  
  
 **Fichiers Include forcés \(\/FI\)**  
 Spécifie les fichiers d'en\-tête à traiter lors de la génération du nouveau projet.  Pour plus d'informations, consultez [\/FI \(Nom du fichier Include imposé\)](../build/reference/fi-name-forced-include-file.md).  
  
 **Chemins de recherche des assemblys .NET \(\/AI\)**  
 Spécifie les chemins d'accès dans lesquels le compilateur effectuera ses recherches pour résoudre les références d'assembly .NET passées aux directives de préprocesseur dans le nouveau projet.  Pour plus d'informations, consultez [\/AI \(Spécifier les répertoires des métadonnées\)](../build/reference/ai-specify-metadata-directories.md).  
  
 **Utilisation forcée des assemblys .NET \(\/FU\)**  
 Spécifie les assemblys .NET à traiter lors de la génération du nouveau projet.  Pour plus d'informations, consultez [\/FU \(Nom du fichier \#using imposé\)](../build/reference/fu-name-forced-hash-using-file.md).  
  
## Voir aussi  
 [Spécifier les paramètres du projet, Assistant Créer un projet à partir de fichiers de code existants](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)