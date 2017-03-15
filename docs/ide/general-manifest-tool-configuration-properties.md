---
title: "G&#233;n&#233;ral, Outil Manifeste, Propri&#233;t&#233;s de configuration, bo&#238;te de dialogue Pages de propri&#233;t&#233;s de &lt;NomProjet&gt; | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.MergeRulesFile"
  - "VC.Project.VCManifestTool.UseUnicodeResponseFiles"
  - "VC.Project.VCManifestTool.SuppressStartupBanner"
  - "VC.Project.VCManifestTool.UseFAT32Workaround"
  - "VC.Project.VCManifestTool.VerboseOutput"
  - "VC.Project.VCManifestTool.AssemblyIdentity"
dev_langs: 
  - "C++"
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# G&#233;n&#233;ral, Outil Manifeste, Propri&#233;t&#233;s de configuration, bo&#238;te de dialogue Pages de propri&#233;t&#233;s de &lt;NomProjet&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette boîte de dialogue afin de spécifier des options générales pour [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Pour accéder à cette boîte de dialogue de page de propriétés, ouvrez les pages de propriétés pour votre projet ou votre feuille de propriétés.  Développez le nœud **Outil Manifeste** sous **Propriétés de configuration**, puis sélectionnez **Général**.  
  
## Liste UIElement  
 **Suppression de la bannière de démarrage**  
 **Oui \(\/nologo\)** spécifie que les données de copyright standard de Microsoft n'apparaîtront pas au démarrage de l'outil Manifeste.  Utilisez cette option pour supprimer les sorties dont vous ne voulez pas dans fichiers journaux, lorsque vous exécutez mt.exe dans le cadre d'un processus de génération ou à partir d'un environnement de génération.  
  
 **Sortie des commentaires**  
 **Oui \(\/verbose\)** spécifie que des informations de génération supplémentaires seront affichées pendant la génération du manifeste.  
  
 **Identité d'assembly**  
 Utilise l'option \/identity pour spécifier une chaîne d'identité qui comprend les attributs pour l'[\<assemblyIdentity\> Element](../Topic/%3CassemblyIdentity%3E%20Element%20\(ClickOnce%20Application\).md).  Une chaîne d'identité commence par la valeur de l'attribut `name`, suivie par les paires *attribut* \= *valeur*.  Les attributs dans une chaîne d'identité sont délimités par une virgule.  
  
 Voici un exemple de chaîne d'identité :  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## Voir aussi  
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Pages de propriétés de l'outil Manifeste](../ide/manifest-tool-property-pages.md)   
 [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md)   
 [Comment : modifier les feuilles de propriétés d'un projet](../misc/how-to-edit-project-property-sheets.md)