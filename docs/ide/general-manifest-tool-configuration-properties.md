---
title: Manifeste des propriétés de Configuration d’outil (Visual C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.MergeRulesFile
- VC.Project.VCManifestTool.UseUnicodeResponseFiles
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.UseFAT32Workaround
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
dev_langs:
- C++
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1953e7c37c07f66845510efe037015a537aa7baa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="general-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Général, outil manifeste, propriétés de Configuration, &lt;nom_projet&gt; boîte de dialogue Pages de propriétés
Utilisez cette boîte de dialogue pour spécifier les options générales [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Pour accéder à cette boîte de dialogue de page de propriétés, ouvrez les pages de propriétés pour votre projet ou votre feuille de propriétés. Développez le **outil manifeste** nœud sous **propriétés de Configuration**, puis sélectionnez **général**.  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Suppression de la bannière de démarrage**  
 **Oui (/ nologo)** Spécifie que les données de copyright Microsoft standards seront être au démarrage de l’outil manifeste. Utilisez cette option pour supprimer une sortie indésirable dans les fichiers journaux, lorsque vous exécutez mt.exe dans le cadre du processus de génération ou à partir d’un environnement de génération.  
  
 **Sortie des commentaires**  
 **Oui (/verbose)** Spécifie que les informations de génération supplémentaires seront affichées pendant la génération du manifeste.  
  
 **Identité de l’assembly**  
 Utilise l’option /identity pour spécifier une chaîne d’identité, qui comprend les attributs pour le [ \<assemblyIdentity > élément](/visualstudio/deployment/assemblyidentity-element-clickonce-application). Une chaîne d’identité commence par la valeur de la `name` d’attribut et est suivi par *attribut* = *valeur* paires. Les attributs dans une chaîne d’identité sont délimités par une virgule.  
  
 Voici un exemple de chaîne d’identité :  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## <a name="see-also"></a>Voir aussi  
 [Manifeste d’Application ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Pages de propriétés outil manifeste](../ide/manifest-tool-property-pages.md)   
 [Utilisation des propriétés de projet](../ide/working-with-project-properties.md)   