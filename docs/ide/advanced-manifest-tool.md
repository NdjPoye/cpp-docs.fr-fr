---
title: "Avanc&#233;, Outil Manifeste, Propri&#233;t&#233;s de configuration, bo&#238;te de dialogue Pages de propri&#233;t&#233;s de &lt;NomProjet&gt; | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.KeyFile"
  - "VC.Project.VCManifestTool.UpdateFileHashes"
  - "VC.Project.VCManifestTool.UpdateFileHashesSearchPath"
  - "VC.Project.VCManifestTool.ValidateSignature"
  - "VC.Project.VCManifestTool.KeyContainer"
dev_langs: 
  - "C++"
ms.assetid: 3d587366-05ea-4956-a978-313069660735
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Avanc&#233;, Outil Manifeste, Propri&#233;t&#233;s de configuration, bo&#238;te de dialogue Pages de propri&#233;t&#233;s de &lt;NomProjet&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette boîte de dialogue afin de spécifier des options avancées pour [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Pour accéder à cette boîte de dialogue de page de propriétés, ouvrez les pages de propriétés pour votre projet ou votre feuille de propriétés.  Développez le nœud **Outil Manifeste** sous **Propriétés de configuration**, puis sélectionnez **Avancées**.  
  
## Liste UIElement  
 **Mettre à jour les fichiers à hacher**  
 Utilise l'option \/hashupdate pour spécifier que l'outil manifeste calculera le hachage des fichiers spécifiés dans les éléments `<file>`, puis mettre à jour les attributs de hachage avec la valeur calculée.  
  
 **Chemin de recherche de mise à jour des fichiers à hacher**  
 Spécifie le chemin de recherche des fichiers qui sont référencés dans les éléments `<file>`.  Cette option utilise également l'option \/hashupdate.  
  
## Voir aussi  
 [\<file\> Element](../Topic/%3Cfile%3E%20Element%20\(ClickOnce%20Application\).md)   
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Pages de propriétés de l'outil Manifeste](../ide/manifest-tool-property-pages.md)   
 [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md)   
 [Comment : modifier les feuilles de propriétés d'un projet](../misc/how-to-edit-project-property-sheets.md)