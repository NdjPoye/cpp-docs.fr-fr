---
title: "Avancé, outil manifeste, propriétés de Configuration, &lt;nom_projet&gt; boîte de dialogue Pages de propriétés | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
dev_langs: C++
ms.assetid: 3d587366-05ea-4956-a978-313069660735
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 83f78603825cc8880063c8cfb4d750f6109c5d6c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Avancé, outil manifeste, propriétés de Configuration, &lt;nom_projet&gt; boîte de dialogue Pages de propriétés
Utilisez cette boîte de dialogue pour spécifier des options avancées pour [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Pour accéder à cette boîte de dialogue de page de propriétés, ouvrez les pages de propriétés pour votre projet ou votre feuille de propriétés. Développez le **outil manifeste** nœud sous **propriétés de Configuration**, puis sélectionnez **avancé**.  
  
## <a name="uielement-list"></a>Liste UIElement  
 **Mettre à jour les fichiers à hacher**  
 Utilise l’option /hashupdate pour spécifier que l’outil manifeste calculera le hachage des fichiers spécifiés dans `<file>` éléments, puis mettez à jour le code de hachage d’attributs avec la valeur calculée.  
  
 **Mettre à jour le chemin de recherche de hachages de fichier**  
 Spécifie le chemin de recherche des fichiers qui sont référencés dans `<file>` éléments. Cette option utilise également l’option /hashupdate.  
  
## <a name="see-also"></a>Voir aussi  
 [\<fichier > élément](/visualstudio/deployment/file-element-clickonce-application)   
 [Manifeste d’Application ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Pages de propriétés outil manifeste](../ide/manifest-tool-property-pages.md)   
 [Utilisation des propriétés de projet](../ide/working-with-project-properties.md)   