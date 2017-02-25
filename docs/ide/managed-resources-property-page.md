---
title: "Ressources manag&#233;es, page de propri&#233;t&#233;s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCManagedResourceCompilerTool.ResourceFileName"
  - "VC.Project.VCManagedResourceCompilerTool.OutputFileName"
  - "VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ressources managées (page de propriétés)"
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Ressources manag&#233;es, page de propri&#233;t&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active les paramètres du compilateur de ressources.  
  
 La page de propriétés **Ressources managées** contient les propriétés suivantes :  
  
 **Nom logique de la ressource**  
 Spécifie le *nom logique* du fichier .resources intermédiaire généré.  Le nom logique est le nom utilisé pour charger la ressource.  Si aucun nom logique n'est spécifié, le nom du fichier de ressources \(.resx\) est utilisé comme nom logique.  
  
 **Nom du fichier de sortie**  
 Spécifie le nom du dernier fichier de sortie auquel le fichier de ressources \(.resx\) contribue.  
  
 **Ressources localisées par défaut**  
 Spécifie si le fichier .resx donné contribue aux ressources par défaut ou à un .dll satellite.  
  
 Pour plus d'informations sur la façon d'accéder à la page de propriétés **Ressources managées**, consultez [Comment : spécifier des propriétés de projet avec des pages de propriétés](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
## Voir aussi  
 [Using RC \(The RC Command Line\)](http://msdn.microsoft.com/library/windows/desktop/aa381055)   
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)   
 [\/ASSEMBLYRESOURCE \(Incorporer une ressource managée\)](../build/reference/assemblyresource-embed-a-managed-resource.md)