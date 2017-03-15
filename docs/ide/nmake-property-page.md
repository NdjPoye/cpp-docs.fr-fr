---
title: "Nmake, page de propri&#233;t&#233;s | Microsoft Docs"
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
  - "VC.Project.VCNMakeTool.ReBuildCommandLine"
  - "VC.Project.VCNMakeTool.CleanCommandLine"
  - "VC.Project.VCNMakeTool.Output"
  - "VC.Project.VCNMakeTool.BuildCommandLine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMake (page de propriétés)"
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Nmake, page de propri&#233;t&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La page de propriétés **NMake** vous permet de spécifier les paramètres de génération pour les projets NMake.  
  
 Pour plus d'informations sur les projets NMake, consultez [Création d'un projet Makefile](../ide/creating-a-makefile-project.md).  
  
 La page de propriétés **NMake** comporte les propriétés suivantes.  
  
## Liste UIElement  
 **Ligne de commande Build**  
 Spécifie la commande à exécuter lorsque **Générer** est sélectionné dans le menu **Générer**.  
  
 **Ligne de commande Régénérer tout**  
 Spécifie la commande à exécuter lorsque **Regénérer tout** est sélectionné dans le menu **Générer**.  
  
 **Ligne de commande Clean**  
 Spécifie la commande à exécuter lorsque **Nettoyer** est sélectionné dans le menu **Générer**.  
  
 **Sortie**  
 Affiche le nom du fichier qui doit contenir le fichier de sortie de la ligne de commande.  Par défaut, ce nom de fichier est basé sur le nom du projet.  
  
 **Définitions de préprocesseur**  
 Spécifie toutes les définitions de préprocesseur que les fichiers sources utilisent.  La valeur par défaut est déterminée par la plateforme et la configuration actuelle.  
  
 **Chemin de recherche Include**  
 Spécifie les répertoires où le compilateur recherche des fichiers Include.  
  
 **Fichiers Include forcés**  
 Spécifie les fichiers que le préprocesseur traite automatiquement même s'ils ne sont pas inclus dans les fichiers projet.  
  
 **Chemin de recherche des assemblys**  
 Spécifie les répertoires où .NET Framework recherche lorsqu'il essaye de résoudre des assemblys .NET.  
  
 **Utilisation forcée des assemblys**  
 Spécifie les assemblys que le .NET Framework traite automatiquement.  
  
 **Options supplémentaires**  
 Spécifie tous les commutateurs de compilation supplémentaires pour IntelliSense à utiliser lorsqu'il analyse des fichiers C\+\+.  
  
 Pour plus d'informations sur l'accès à la page de propriétés **NMake**, consultez [Comment : spécifier des propriétés de projet avec des pages de propriétés](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
 Pour plus d'informations sur comment accéder par programmation aux membres de cet objet, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.  
  
## Voir aussi  
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)   
 [Comment : activer IntelliSense pour des projets Makefile](../ide/how-to-enable-intellisense-for-makefile-projects.md)