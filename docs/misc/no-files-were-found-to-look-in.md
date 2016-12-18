---
title: "No files were found to look in. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_FRLookInEmpty"
  - "vs.message.0x800A00DE"
ms.assetid: d560aef3-7a55-4fbb-a541-1a43fc13c18b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# No files were found to look in.
Cette erreur se produit généralement quand un nom de fichier ou un répertoire a été spécifié dans la liste Regarder dans alors que ce nom de fichier ou répertoire est inexistant ou introuvable.  Cette erreur peut également survenir si vous spécifiez un répertoire valide qui ne contient pas l'extension de fichier indiquée dans la liste Types de fichiers ou si le répertoire spécifié ne contient aucun fichier.  Ce message d'erreur peut également s'afficher lors d'une recherche dans un répertoire si l'attribut a pour valeur `Hidden` ou `System`.  
  
### Pour corriger cette erreur  
  
1.  Utilisez la boîte de dialogue **Personnaliser les répertoires** pour rechercher le répertoire ou le nom de fichier voulu plutôt que de taper le chemin ou le nom de fichier correspondant.  Pour accéder à la boîte de dialogue **Personnaliser les répertoires**, choisissez le bouton de sélection \(...\) situé en regard de la liste **Regarder dans**.  
  
2.  Remplacez l'extension de fichier spécifiée dans la liste **Types de fichiers** par \*.\* pour rechercher tous les fichiers dans le répertoire spécifié.  
  
### Pour ignorer cette erreur  
  
1.  Maintenez la touche CTRL enfoncée et appuyez sur ScrLk.  
  
     Ceci annule la boîte de dialogue.  
  
## Voir aussi  
 [Recherche et remplacement de texte](../Topic/Finding%20and%20Replacing%20Text.md)   
 [Rechercher dans les fichiers](../Topic/Find%20in%20Files.md)   
 [Choose Search Folders](http://msdn.microsoft.com/fr-fr/85af6458-dcde-4a84-9ea4-f5cc6550dc80)