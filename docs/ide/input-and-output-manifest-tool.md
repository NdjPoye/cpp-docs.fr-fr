---
title: "Entr&#233;e et sortie, Outil Manifeste, Propri&#233;t&#233;s de configuration, bo&#238;te de dialogue Pages de propri&#233;t&#233;s de &lt;NomProjet&gt; | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.OutputManifestFile"
  - "VC.Project.VCManifestTool.InputResourceManifests"
  - "VC.Project.VCManifestTool.EmbedManifest"
  - "VC.Project.VCManifestTool.AdditionalManifestFiles"
  - "VC.Project.VCManifestTool.DependencyInformationFile"
  - "VC.Project.VCManifestTool.OutputResourceManifest"
  - "VC.Project.VCManifestTool.GenerateCatalogFiles"
dev_langs: 
  - "C++"
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Entr&#233;e et sortie, Outil Manifeste, Propri&#233;t&#233;s de configuration, bo&#238;te de dialogue Pages de propri&#233;t&#233;s de &lt;NomProjet&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette boîte de dialogue afin de spécifier les options d'entrée et de sortie pour [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Pour accéder à cette boîte de dialogue de page de propriétés, ouvrez les pages de propriétés pour votre projet ou votre feuille de propriétés.  Développez le nœud **Outil Manifeste** sous **Propriétés de configuration**, puis sélectionnez **Entrée et sortie**.  
  
## Liste UIElement  
 **Fichiers manifeste supplémentaires**  
 Utilise l'option **\/manifest** pour spécifier les chemins d'accès complets des fichiers manifeste supplémentaires que l'outil Manifeste traitera ou fusionnera.  Les chemins d'accès complets sont délimités par un point\-virgule.  
  
 **Manifestes de ressource d'entrée**  
 Utilise l'option **\/inputresource** pour spécifier le chemin d'accès complet d'une ressource de type RT\_MANIFEST, à entrer dans l'outil Manifeste.  Le chemin d'accès peut être suivi par l'ID de ressource spécifié.  Par exemple :  
  
 `dll_with_manifest.dll;#1`  
  
 L'ID de ressource est facultatif et a par défaut la valeur CREATEPROCESS\_MANIFEST\_RESOURCE\_ID in winuser.h.  
  
 **Incorporer le manifeste**  
 **Oui** spécifie que le système de projet incorporera le fichier manifeste d'application dans l'assembly.  
  
 **Aucun** spécifie que le système de projet créera le fichier manifeste d'application en tant que fichier autonome.  
  
 **Fichier manifeste de sortie**  
 Spécifie le nom du fichier manifeste de sortie.  Cette propriété est facultative lorsqu'un seul fichier manifeste est traité par l'outil Manifeste.  
  
 **Fichier de ressources du manifeste**  
 Spécifie les fichiers de ressources de sortie utilisés pour incorporer le manifeste dans la sortie de projet.  
  
 **Génération de fichiers catalogue**  
 Utilise l'option **\/makecdfs** pour spécifier que l'outil Manifeste générera des fichiers de définition de catalogue \(fichiers .cdf\), qui sont utilisés pour faire des catalogues.  
  
 **Générer un manifeste à partir d'un assembly managé**  
 Génère un manifeste à partir d'un assembly managé.  \(**\-managedassemblyname:***fichier*\).  
  
 **Supprimer l'élément de dépendance**  
 Utilisé avec l'option **\-managedassembly**.  Cette balise supprime la génération des éléments de dépendance dans le dernier manifeste.  
  
 **Générer des balises de catégorie**  
 Utilisé avec l'option **\-managedassembly**.  Cette balise engendre la génération des balises de catégorie.  
  
 **Prise en charge DPI**  
 Spécifie si l'application prend en charge DPI.  Par défaut, le paramètre est **Yes** pour les projets MFC et **No** pour les autres projets parce que seuls les projets MFC possèdent une reconnaissance de résolution intégrée.  Vous pouvez substituer le paramètre à **Yes** si vous ajoutez le code pour gérer différents paramètres DPI.  Votre application peut apparaître floue ou petite si vous la définissez comme reconnaissant les résolutions si ce n'est pas le cas.  
  
## Voir aussi  
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Pages de propriétés de l'outil Manifeste](../ide/manifest-tool-property-pages.md)   
 [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md)   
 [Comment : modifier les feuilles de propriétés d'un projet](../misc/how-to-edit-project-property-sheets.md)