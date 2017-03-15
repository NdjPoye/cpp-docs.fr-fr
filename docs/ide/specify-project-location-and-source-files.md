---
title: "Sp&#233;cifier l&#39;emplacement du projet et les fichiers sources, Assistant Cr&#233;er un projet &#224; partir de fichiers de code existants | Microsoft Docs"
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
  - "vc.appwiz.importwiz.location"
dev_langs: 
  - "C++"
ms.assetid: 29ddffb9-5918-4d72-8c7a-a365f9de96dd
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cifier l&#39;emplacement du projet et les fichiers sources, Assistant Cr&#233;er un projet &#224; partir de fichiers de code existants
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant Créer un projet à partir de fichiers de code existants pour spécifier :  
  
-   le chemin d'accès au répertoire du nouveau projet,  
  
-   les répertoires dans lesquels rechercher les fichiers source existants,  
  
-   les types de fichiers que l'Assistant importera dans le nouveau projet.  
  
## Liste des tâches  
 [Comment : créer un projet C\+\+ à partir d'un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## Liste UIElement  
 **Emplacement du fichier projet**  
 Spécifie le chemin d'accès au répertoire du nouveau projet.  Cet emplacement correspond à l'endroit où l'Assistant déposera tous les fichiers \(et les sous\-répertoires\) du nouveau projet.  
  
 **Parcourir**  
 Affiche la boîte de dialogue **Emplacement du fichier projet**, dans laquelle vous spécifiez le répertoire qui contiendra le nouveau projet.  Ce contrôle vous permet de naviguer jusqu'au dossier voulu.  
  
 **Nom du projet**  
 Spécifie le nom du nouveau projet.  Les fichiers de projet qui ont des extentions de fichier comme .vcxproj adopteront ce nom.  Les fichiers de code existants garderont leur nom d'origine.  
  
 **Ajouter les fichiers au projet à partir de ces dossiers**  
 Lorsque cette option est activée, l'Assistant copie les fichiers de code existants depuis leur répertoire d'origine \(qui sont spécifiés dans la zone de liste sous ce contrôle\) dans le nouveau projet.  
  
 **Ajouter les sous\-dossiers**  
 Spécifie de copier les fichiers de code à partir de tous les sous\-répertoires du répertoire figurant dans la colonne **Dossier** dans le nouveau projet.  
  
 **Dossier**  
 Indique le chemin d'accès au répertoire qui contient des fichiers de code existants à copier dans le nouveau projet.  Cette colonne répertorie tous les répertoires dans lesquels l'Assistant recherchera les fichiers de code existants.  
  
 **Ajouter**  
 Affiche la boîte de dialogue **Ajouter les fichiers au projet à partir de ce dossier**, dans laquelle vous pouvez spécifier les répertoires dans lesquels l'Assistant recherchera les fichiers de code existants.  
  
 **Supprimer**  
 Supprime le chemin d'accès au répertoire qui est sélectionné dans la zone de liste à gauche de ce contrôle.  
  
 **Types de fichiers à ajouter au projet**  
 Spécifie les types de fichiers que l'Assistant ajoutera dans le nouveau projet en fonction des extensions de fichier données.  Les extensions de fichier sont précédées du caractère générique astérisque, et sont délimitées dans la liste d'extensions de fichier par un point\-virgule.  
  
 **Afficher tous les fichiers dans l'Explorateur de solutions**  
 Spécifie que tous les fichiers du nouveau projet soient visibles et affichés dans la fenêtre Explorateur de solutions.  Cette option est activée par défaut.