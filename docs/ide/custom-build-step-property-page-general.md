---
title: "Page de propriétés d’étape de génération personnalisée : Général | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
dev_langs:
- C++
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e57d6cf00843cd6604ef269235602ea1b5b5e9b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="custom-build-step-property-page-general"></a>Étape de génération personnalisée, page de propriétés : général
Pour chaque combinaison de configuration de projet et de plateforme cible dans votre projet, vous pouvez spécifier une étape personnalisée à effectuer lors de la génération du projet.  

Pour la version Linux de cette page, consultez [propriétés de l’étape génération personnalisée (C++ Linux)](../linux/prop-pages/custom-build-step-linux.md).
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Ligne de commande**  
 Commande à exécuter par l'étape de génération personnalisée.  
  
 **Description**  
 Message qui s'affiche lors de l'exécution de l'étape de génération personnalisée.  
  
 **Outputs**  
 Fichier de sortie généré lors de l'étape de génération personnalisée. Ce paramètre est requis afin que les générations incrémentielles fonctionnent correctement.  
  
 **Dépendances supplémentaires**  
 Liste délimitée par les points-virgules de tous les fichiers d'entrée supplémentaires à utiliser pour l'étape de génération personnalisée.  
  
 **Exécutez après et exécutez avant**  
 Ces options définissent le moment de l'exécution de l'étape de génération personnalisée dans le processus de génération, par rapport aux cibles répertoriées. Les cibles le plus souvent répertoriées sont BuildGenerateSources, BuildCompile, et BuildLink, car elles constituent des étapes majeures dans le processus de génération. Les cibles souvent répertoriées sont Midl, CLCompile, et Link.  
  
 Considérer la sortie en tant que contenu  
 Cette option est uniquement explicite pour les applications de plateforme Windows universelle ou Windows Phone, qui incluent tous les fichiers de contenu dans le package .appx.  
  
### <a name="to-specify-a-custom-build-step"></a>Pour spécifier une étape de génération personnalisée  
  
1.  Dans la barre de menus, choisissez **Projet**, **Propriétés**. Pour plus d’informations, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
2.  Dans le **Pages de propriétés** boîte de dialogue, accédez à la **propriétés de Configuration**, **étape de génération personnalisée**, **général** page.  
  
3.  Modifier les paramètres du site.  
  
## <a name="see-also"></a>Voir aussi  
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)