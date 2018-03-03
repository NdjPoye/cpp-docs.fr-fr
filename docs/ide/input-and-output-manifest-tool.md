---
title: "Manifeste d’outil Propriétés d’entrée et sortie (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
dev_langs:
- C++
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 77137e9bc0a4af60080234aac85afa59034d2c6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Entrée et sortie, outil, les propriétés de Configuration, manifeste &lt;nom_projet&gt; boîte de dialogue Pages de propriétés
Utilisez cette boîte de dialogue pour spécifier les options d’entrée et de sortie pour [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Pour accéder à cette boîte de dialogue de page de propriétés, ouvrez les pages de propriétés pour votre projet ou votre feuille de propriétés. Développez le **outil manifeste** nœud sous **propriétés de Configuration**, puis sélectionnez **d’entrée et sortie**.  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Fichiers manifeste supplémentaires**  
 Utilise le **de manifeste** permettant de spécifier les chemins complets des fichiers manifeste supplémentaires que l’outil manifeste traitera ou de fusion. Chemins d’accès complets sont délimités par un point-virgule.  
  
 **Manifestes de ressource d’entrée**  
 Utilise le **/inputresource** permettant de spécifier le chemin d’accès complet d’une ressource de type RT_MANIFEST, à entrer dans l’outil manifeste. Le chemin d’accès peut être suivi par l’ID de ressource spécifiée. Exemple :  
  
 `dll_with_manifest.dll;#1`  
  
 L’ID de ressource est facultatif et les paramètres par défaut pour la valeur CREATEPROCESS_MANIFEST_RESOURCE_ID dans winuser.h.  
  
 **Incorporer le manifeste**  
 **Oui** Spécifie que le système de projet sera incorporer le fichier manifeste d’application dans l’assembly.  
  
 **Ne** indique que le système de projet créera le fichier manifeste d’application en tant que fichier autonome.  
  
 **Fichier manifeste de sortie**  
 Spécifie le nom du fichier manifeste de sortie. Cette propriété est facultative lorsque qu’un seul fichier manifest est traité par l’outil manifeste.  
  
 **Fichier de ressource de manifeste**  
 Spécifie la sortie des fichiers de ressources utilisés pour incorporer le manifeste dans la sortie du projet.  
  
 **Générer des fichiers de catalogue**  
 Utilise le **/makecdfs** option pour spécifier que l’outil manifeste générera des fichiers de définition de catalogue (fichiers .cdf), qui sont utilisés pour faire des catalogues.  
  
 **Générer un manifeste à partir d’un assembly managé**  
 Génère un manifeste à partir d’un assembly managé. (**- managedassemblyname :***fichier*).  
  
 **Supprimer l’élément de dépendance**  
 Utilisé avec le **- managedassembly** option. Cette balise supprime la génération des éléments de dépendance dans le manifeste final.  
  
 **Générer des balises de catégorie**  
 Utilisé avec le **- managedassembly** option. Cette balise entraîne les génération des balises de catégorie.  
  
 **Prise en charge DPI**  
 Spécifie si l’application prend en charge DPI. Par défaut, le paramètre est **Oui** pour les projets MFC et **non** sinon parce que seuls les projets MFC possèdent une reconnaissance de résolution intégrée. Vous pouvez remplacer le paramètre à **Oui** si vous ajoutez du code pour gérer différents paramètres DPI. Votre application peut apparaître floue ou petite si vous le définissez comme reconnaissant les résolutions lorsqu’il n’est pas.  
  
## <a name="see-also"></a>Voir aussi  
 [Manifeste d’Application ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Pages de propriétés outil manifeste](../ide/manifest-tool-property-pages.md)   
 [Utilisation des propriétés de projet](../ide/working-with-project-properties.md)   