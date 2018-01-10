---
title: "Page de propriétés NMake (Windows C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
dev_langs: C++
helpviewer_keywords: NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7cc9f6dc7c5fec4a184ed189cfaae230df3f1e9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-property-page"></a>NMake (page de propriétés)
Le **NMake** page de propriétés vous permet de spécifier les paramètres de génération pour les projets NMake.  
  
 Pour plus d’informations sur les projets NMake, consultez [création d’un projet Makefile](../ide/creating-a-makefile-project.md). Pour non_Windows projets MakeFile, consultez [propriétés de projet MakeFile (C++ Linux)](../linux/prop-pages/makefile-linux.md), [général des propriétés de projet (Android C++ Makefile)](/visualstudio/cross-platform/general-makefile-android-prop-page) ou [NMake propriétés (C++ Android)](/visualstudio/cross-platform/nmake-android-prop-page).
  
 Le **NMake** page de propriétés contient les propriétés suivantes.  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Ligne de commande build**  
 Spécifie la commande à exécuter lorsque **générer** un clic sur le **générer** menu.  
  
 **Tous les de ligne de commande Rebuild**  
 Spécifie la commande à exécuter lorsque **tout reconstruire** un clic sur le **générer** menu.  
  
 **Ligne de commande Clean**  
 Spécifie la commande à exécuter lorsque **Clean** un clic sur le **générer** menu.  
  
 **Sortie**  
 Spécifie le nom du fichier qui contiendra la sortie de la ligne de commande. Par défaut, ce nom de fichier est basé sur le nom du projet.  
  
 **Définitions de préprocesseur**  
 Spécifie que les fichiers sources utilisent des définitions de préprocesseur. La valeur par défaut est déterminée par la plateforme actuelle et la configuration.  
  
 **Chemin de recherche Include**  
 Spécifie les répertoires dans lesquels le compilateur recherche les fichiers include.  
  
 **Forcé inclut**  
 Spécifie les fichiers que le préprocesseur traite automatiquement même si elles ne figurent pas dans les fichiers projet.  
  
 **Chemin de recherche**  
 Spécifie les répertoires où .NET Framework recherche lorsqu’il essaye de résoudre des assemblys .NET.  
  
 **Utilisation forcée des assemblys**  
 Spécifie les assemblys .NET Framework traite automatiquement.  
  
 **Options supplémentaires**  
 Spécifie les commutateurs de compilation supplémentaires pour IntelliSense à utiliser lors de l’analyse des fichiers C++.  
  
 Pour plus d’informations sur l’accès à la **NMake** page de propriétés, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
 Pour plus d’informations sur la façon d’accéder par programme aux membres de cet objet, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.  
  
## <a name="see-also"></a>Voir aussi  
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)   
 [Guide pratique pour activer IntelliSense pour des projets Makefile](../ide/how-to-enable-intellisense-for-makefile-projects.md)