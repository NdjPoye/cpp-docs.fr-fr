---
title: "COM isol&#233;, Outil Manifeste, Propri&#233;t&#233;s de configuration, bo&#238;te de dialogue Pages de propri&#233;t&#233;s de &lt;NomProjet&gt; | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.RegistrarScriptFile"
  - "VC.Project.VCManifestTool.ComponentFileName"
  - "VC.Project.VCManifestTool.TypeLibraryFile"
  - "VC.Project.VCManifestTool.ReplacementsFile"
dev_langs: 
  - "C++"
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM isol&#233;, Outil Manifeste, Propri&#233;t&#233;s de configuration, bo&#238;te de dialogue Pages de propri&#233;t&#233;s de &lt;NomProjet&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette boîte de dialogue pour spécifier les options **Isolated COM** pour [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Pour accéder à cette boîte de dialogue de page de propriétés, ouvrez les pages de propriétés pour votre projet ou votre feuille de propriétés.  Développez le nœud **Outil Manifeste** sous **Propriétés communes**, puis sélectionnez **COM isolé**.  
  
## Liste des tâches  
  
-   [Comment : générer des applications isolées pour consommer des composants COM](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
## Liste UIElement  
 **Fichier bibliothèque de types**  
 Utilise l'option \/tlb pour spécifier le nom du fichier bibliothèque de types \(fichier .tlb\) que l'outil Manifeste utilisera pour générer le fichier manifeste.  
  
 **Fichier de script d'inscription**  
 Utilise l'option \/rgs pour spécifier le nom du fichier de script d'inscription \(fichier .rgs\) que l'outil Manifeste utilisera pour générer le fichier manifeste.  
  
 **Nom de fichier du composant**  
 Utilise l'option \/dll pour spécifier le nom de la ressource que l'outil Manifeste générera.  Vous devez entrer une valeur pour cette propriété lorsque des valeurs sont spécifiées pour **Fichier bibliothèque de types** ou **Fichier de script d'inscription**.  
  
 **Fichier de remplacement**  
 Utilise l'option \/replacements pour spécifier le chemin d'accès complet au fichier qui contient des valeurs pour les chaînes remplaçables dans le fichier .rgs.  
  
## Voir aussi  
 [Applications isolées](http://msdn.microsoft.com/library/aa375190)   
 [Assemblys côte à côte](_win32_side_by_side_assemblies)   
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Pages de propriétés de l'outil Manifeste](../ide/manifest-tool-property-pages.md)   
 [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md)   
 [Comment : modifier les feuilles de propriétés d'un projet](../misc/how-to-edit-project-property-sheets.md)