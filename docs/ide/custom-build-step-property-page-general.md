---
title: "&#201;tape de g&#233;n&#233;ration personnalis&#233;e, page de propri&#233;t&#233;s&#160;: g&#233;n&#233;ral | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCustomBuildStep.AdditionalInputs"
  - "VC.Project.VCCustomBuildStep.CustomBuildAfterTargets"
  - "VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets"
  - "VC.Project.VCCustomBuildStep.Outputs"
  - "VC.Project.VCCustomBuildStep.Message"
  - "VC.Project.VCCustomBuildStep.Command"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propriétés du projet, étape de génération personnalisée"
  - "étape de génération personnalisée (général)"
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# &#201;tape de g&#233;n&#233;ration personnalis&#233;e, page de propri&#233;t&#233;s&#160;: g&#233;n&#233;ral
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour chaque combinaison de configuration de projet et de plateforme cible dans votre projet, vous pouvez spécifier une étape personnalisée à effectuer lors de la génération du projet.  
  
## Liste UIElement  
 **Ligne de commande**  
 Commande à exécuter par l'étape de génération personnalisée.  
  
 **Description**  
 Message qui s'affiche lors de l'exécution de l'étape de génération personnalisée.  
  
 **Outputs**  
 Fichier de sortie généré lors de l'étape de génération personnalisée.  Ce paramètre est requis afin que les générations incrémentielles fonctionnent correctement.  
  
 **Dépendances supplémentaires**  
 Liste délimitée par les points\-virgules de tous les fichiers d'entrée supplémentaires à utiliser pour l'étape de génération personnalisée.  
  
 **Exécutez après et exécutez avant**  
 Ces options définissent le moment de l'exécution de l'étape de génération personnalisée dans le processus de génération, par rapport aux cibles répertoriées.  Les cibles le plus souvent répertoriées sont BuildGenerateSources, BuildCompile, et BuildLink, car elles constituent des étapes majeures dans le processus de génération.  Les cibles souvent répertoriées sont Midl, CLCompile, et Link.  
  
 Considérer la sortie en tant que contenu  
 Cette option n'est significative que pour Windows Store ou les applications Windows Phone, qui incluent tous les fichiers de contenu du package .appx.  
  
### Pour spécifier une étape de génération personnalisée  
  
1.  Dans la barre de menus, choisissez **Projet**, **Propriétés**.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md).  
  
2.  Dans la boîte de dialogue **Pages de propriétés**, naviguez jusqu'à la page **Propriétés de configuration**, **Étape de génération personnalisée**, **Général**.  
  
3.  Modifier les paramètres du site.  
  
## Voir aussi  
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)