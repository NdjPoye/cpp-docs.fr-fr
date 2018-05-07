---
title: Outil manifeste isolé des propriétés de COM (Visual C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
dev_langs:
- C++
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c425a71f8bb8a7972ade29fb0d18cf3eab7debb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Isolé COM, outil manifeste, propriétés de Configuration, &lt;nom_projet&gt; boîte de dialogue Pages de propriétés
Utilisez cette boîte de dialogue pour spécifier **COM isolé** des options pour [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Pour accéder à cette boîte de dialogue de page de propriétés, ouvrez les pages de propriétés pour votre projet ou votre feuille de propriétés. Développez le **outil manifeste** nœud sous **propriétés communes**, puis sélectionnez **COM isolé**.  
  
## <a name="task-list"></a>Liste des tâches  
  
-   [Guide pratique pour générer des applications isolées pour consommer des composants COM](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Fichier bibliothèque de types**  
 Utilise l’option /tlb pour spécifier le nom de fichier de bibliothèque de types (fichier .tlb) que l’outil manifeste utilisera pour générer le fichier manifest.  
  
 **Fichier de Script d’inscription**  
 Utilise l’option /rgs pour spécifier le nom du fichier de script d’inscription (fichier .rgs) que l’outil manifeste utilisera pour générer le fichier manifest.  
  
 **Nom de fichier de composant**  
 Utilise l’option /dll pour spécifier le nom de la ressource qui génère l’outil manifeste. Vous devez entrer une valeur pour cette propriété lorsque les valeurs pour une **fichier bibliothèque de types** ou **fichier de Script de** sont spécifiés.  
  
 **Fichier de remplacement**  
 Utilise l’option /replacements pour spécifier le chemin d’accès complet au fichier qui contient des valeurs pour les chaînes dans le fichier .rgs.  
  
## <a name="see-also"></a>Voir aussi  
 [Applications isolées](http://msdn.microsoft.com/library/aa375190)   
 [Manifeste d’Application ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Pages de propriétés outil manifeste](../ide/manifest-tool-property-pages.md)   
 [Utilisation des propriétés de projet](../ide/working-with-project-properties.md)   